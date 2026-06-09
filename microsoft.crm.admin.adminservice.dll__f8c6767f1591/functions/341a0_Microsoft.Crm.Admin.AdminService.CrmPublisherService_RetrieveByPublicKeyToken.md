# Microsoft.Crm.Admin.AdminService.CrmPublisherService::RetrieveByPublicKeyToken

- ea: `0x341a0`
- end: `0x341d2`
- name: `Microsoft.Crm.Admin.AdminService.CrmPublisherService::RetrieveByPublicKeyToken`
- size: `50`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x34350`

## string_xrefs

- `0x341bc`: `publicKeyToken`
- `0x341a7`: `RetrieveByPublicKeyToken: publicKeyToken = {0}`
- `0x341c6`: `PublicKeyToken`

## pseudocode

```c

```

## disassembly

```asm
0x341a0  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0x341a5  ldc.i4.s 0x14
0x341a7  ldstr    aRetrievebypubl// "RetrieveByPublicKeyToken: publicKeyToke"...
0x341ac  ldc.i4.1
0x341ad  newarr   [mscorlib]System.Object
0x341b2  dup
0x341b3  ldc.i4.0
0x341b4  ldarg.1
0x341b5  stelem.ref
0x341b6  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceVerbose(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x341bb  ldarg.1
0x341bc  ldstr    aPublickeytoken// "publicKeyToken"
0x341c1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x341c6  ldstr    aPublickeytoken_0// "PublicKeyToken"
0x341cb  ldarg.1
0x341cc  call     class Microsoft.Crm.Admin.AdminService.PublisherData Microsoft.Crm.Admin.AdminService.CrmPublisherService::RetrieveFromUniqueConstraint(string key, string value)
0x341d1  ret
```
