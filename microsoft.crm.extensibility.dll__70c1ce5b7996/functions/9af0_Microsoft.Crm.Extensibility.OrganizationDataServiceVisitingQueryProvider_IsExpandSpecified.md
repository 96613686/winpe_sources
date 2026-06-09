# Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::IsExpandSpecified

- ea: `0x9af0`
- end: `0x9b4f`
- name: `Microsoft.Crm.Extensibility.OrganizationDataServiceVisitingQueryProvider::IsExpandSpecified`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9b50`

## callees

- `0x6df0`
- `0x9af0`

## string_xrefs

- `0x9af5`: `RequestUri`

## pseudocode

```c

```

## disassembly

```asm
0x9af0  call     class [System]System.Uri Microsoft.Crm.Extensibility.OrganizationDataService::get_RequestUri()
0x9af5  ldstr    aRequesturi// "RequestUri"
0x9afa  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x9aff  ldc.i4.0
0x9b00  stloc.0
0x9b01  call     class [System]System.Uri Microsoft.Crm.Extensibility.OrganizationDataService::get_RequestUri()
0x9b06  call     class [System]System.Collections.Specialized.NameValueCollection [Microsoft.Crm.Core]Microsoft.Crm.CrmEncodeDecode::ParseQueryString(class [System]System.Uri)
0x9b0b  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x9b10  callvirt instance class [mscorlib]System.Collections.IEnumerator [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection::GetEnumerator()
0x9b15  stloc.1
0x9b16  br.s     loc_9B32
0x9b18  ldloc.1
0x9b19  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x9b1e  castclass [mscorlib]System.String
0x9b23  ldstr    aExpand// "$expand"
0x9b28  ldc.i4.4
0x9b29  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x9b2e  brfalse.s loc_9B32
0x9b30  ldc.i4.1
0x9b31  stloc.0
0x9b32  ldloc.1
0x9b33  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x9b38  brtrue.s loc_9B18
0x9b3a  leave.s  loc_9B4D
0x9b3c  ldloc.1
0x9b3d  isinst   [mscorlib]System.IDisposable
0x9b42  stloc.2
0x9b43  ldloc.2
0x9b44  brfalse.s loc_9B4C
0x9b46  ldloc.2
0x9b47  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9b4c  endfinally
0x9b4d  ldloc.0
0x9b4e  ret
```
