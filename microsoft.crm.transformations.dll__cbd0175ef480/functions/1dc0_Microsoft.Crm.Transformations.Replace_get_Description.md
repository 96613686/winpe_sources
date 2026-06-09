# Microsoft.Crm.Transformations.Replace::get_Description

- ea: `0x1dc0`
- end: `0x1dcb`
- name: `Microsoft.Crm.Transformations.Replace::get_Description`
- size: `11`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x2740`

## string_xrefs

- `0x1dc0`: `Microsoft.Crm.Transformations.Replace.Description`

## pseudocode

```c

```

## disassembly

```asm
0x1dc0  ldstr    aMicrosoftCrmTr_102// "Microsoft.Crm.Transformations.Replace.D"...
0x1dc5  call     string Microsoft.Crm.Transformations.ResourceProvider::GetString(string id)
0x1dca  ret
```
