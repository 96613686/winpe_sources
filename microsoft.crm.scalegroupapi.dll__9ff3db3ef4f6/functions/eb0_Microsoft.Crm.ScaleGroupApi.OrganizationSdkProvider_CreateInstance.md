# Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance

- ea: `0xeb0`
- end: `0xebc`
- name: `Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance`
- size: `12`
- prototype: ``
- caller_count: `11`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x2b60`
- `0x2cf0`
- `0x30e0`
- `0x3320`
- `0x42e0`
- `0x44d0`
- `0x4590`
- `0x4640`
- `0x4b60`
- `0x4d80`
- `0x4fd0`

## callees

- `0xec0`

## pseudocode

```c

```

## disassembly

```asm
0xeb0  ldarg.0
0xeb1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xeb6  call     class Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider Microsoft.Crm.ScaleGroupApi.OrganizationSdkProvider::CreateInstance(valuetype [mscorlib]System.Guid orgId, valuetype [mscorlib]System.Guid crmUserId)
0xebb  ret
```
