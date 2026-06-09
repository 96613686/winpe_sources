# Microsoft.Crm.Transformations.Replace::get_Name

- ea: `0x1db0`
- end: `0x1dbb`
- name: `Microsoft.Crm.Transformations.Replace::get_Name`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2740`

## string_xrefs

- `0x1db0`: `Microsoft.Crm.Transformations.Replace.Name`

## pseudocode

```c

```

## disassembly

```asm
0x1db0  ldstr    aMicrosoftCrmTr_101// "Microsoft.Crm.Transformations.Replace.N"...
0x1db5  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1dba  ret
```
