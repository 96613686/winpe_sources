# <>c__DisplayClass66_1::<CleanupSolutionComponentEntries>b__1

- ea: `0x244010`
- end: `0x2441c7`
- name: `<>c__DisplayClass66_1::<CleanupSolutionComponentEntries>b__1`
- size: `439`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1943e0`
- `0x1b2450`
- `0x1b2b50`
- `0x244010`

## string_xrefs

- `0x2440c0`: `@ComponentType`
- `0x24411e`: `@ComponentType`
- `0x244161`: `@ComponentType`
- `0x24409e`: `Select (Stuff((Select ', ' + CONVERT(VARCHAR(max),sc.ObjectId) FROM SolutionComponentBase sc\n								LEFT OUTER JOIN [{0}] e ON e.[{1}] = sc.ObjectId\n								WHERE sc.ComponentType = @ComponentType and e.[{1}] is null FOR XML PATH('')),1,2,''))`
- `0x2440fc`: `DELETE SolutionComponentBase FROM SolutionComponentBase sc\n								LEFT OUTER JOIN [{0}] e ON e.[{1}] = sc.ObjectId\n								WHERE sc.ComponentType = @ComponentType and e.[{1}] is null`
- `0x244152`: `DELETE FROM SolutionComponentBase WHERE ComponentType = @ComponentType`

## pseudocode

```c

```
