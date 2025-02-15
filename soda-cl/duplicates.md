---
layout: default
title: Duplicate checks
description: Use a SodaCL (Beta) duplicate count check to count the distinct values that occur more than once in a column.
parent: SodaCL (Beta)
---

# Duplicate checks ![beta](/assets/images/beta.png){:height="50px" width="50px" align="top"}

Use a `duplicate_count` check to count the distinct values that occur more than once in a column.

The following checks that the column `email_address` does not contain any duplicates.

```yaml
checks for CUSTOMERS:
  - duplicate_count(email_address) = 0
```

The following executes the `duplicate_count` check on two columns. If either column contains a duplicate value relative to itself, the check fails.
```yaml
checks for CUSTOMERS:
  - duplicate_count(email_address, last_name) = 0
```

### Notes

* You cannot use `duplicate_count` with filters.
* If you have defined global column configurations for missing and valid values, you cannot use `duplicate_count` to check for those globally-configured values in columns in a table.

---
{% include docs-footer.md %}
