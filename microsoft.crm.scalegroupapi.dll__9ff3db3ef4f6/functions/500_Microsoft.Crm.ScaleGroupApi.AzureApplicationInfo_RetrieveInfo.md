# Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::RetrieveInfo

- ea: `0x500`
- end: `0x50b`
- name: `Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::RetrieveInfo`
- size: `11`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0xa70`
- `0xc10`
- `0xdc0`

## pseudocode

```c

```

## disassembly

```asm
0x500  ldsfld   class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo> Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::_cachedInfo
0x505  callvirt instance var<u1> class [mscorlib]System.Lazy`1<class Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo>::get_Value()
0x50a  ret
```
