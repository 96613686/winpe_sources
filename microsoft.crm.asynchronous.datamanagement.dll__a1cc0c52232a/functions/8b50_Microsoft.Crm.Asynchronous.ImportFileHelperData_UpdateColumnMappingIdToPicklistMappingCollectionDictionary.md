# Microsoft.Crm.Asynchronous.ImportFileHelperData::UpdateColumnMappingIdToPicklistMappingCollectionDictionary

- ea: `0x8b50`
- end: `0x8bd8`
- name: `Microsoft.Crm.Asynchronous.ImportFileHelperData::UpdateColumnMappingIdToPicklistMappingCollectionDictionary`
- size: `136`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x8640`

## callees

- `0x8b50`
- `0x8db0`

## pseudocode

```c

```

## disassembly

```asm
0x8b50  ldarg.0
0x8b51  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportFileHelperData::_organizationId
0x8b56  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x8b5b  stloc.0
0x8b5c  ldarg.2
0x8b5d  brfalse.s loc_8BD7
0x8b5f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::.ctor()
0x8b64  stloc.1
0x8b65  ldarg.2
0x8b66  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x8b6b  stloc.2
0x8b6c  br.s     loc_8BAC
0x8b6e  ldloc.2
0x8b6f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x8b74  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption
0x8b79  stloc.3
0x8b7a  ldloc.3
0x8b7b  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Labels()
0x8b80  ldarg.0
0x8b81  ldfld    int32 Microsoft.Crm.Asynchronous.ImportFileHelperData::_languageCode
0x8b86  ldloc.0
0x8b87  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.ILabelCollection::TryGetDescription(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x8b8c  stloc.s  4
0x8b8e  ldloc.s  4
0x8b90  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8b95  brtrue.s loc_8BAC
0x8b97  ldloc.1
0x8b98  ldarg.0
0x8b99  ldarg.1
0x8b9a  ldloc.s  4
0x8b9c  ldloc.3
0x8b9d  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EnumOption::get_Value()
0x8ba2  call     instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::GetPicklistMappingObject(valuetype [mscorlib]System.Guid columnMappingId, string sourceValue, int32 targetValue)
0x8ba7  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::Add(var<u1>)
0x8bac  ldloc.2
0x8bad  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8bb2  brtrue.s loc_8B6E
0x8bb4  leave.s  loc_8BCA
0x8bb6  ldloc.2
0x8bb7  isinst   [mscorlib]System.IDisposable
0x8bbc  stloc.s  5
0x8bbe  ldloc.s  5
0x8bc0  brfalse.s loc_8BC9
0x8bc2  ldloc.s  5
0x8bc4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8bc9  endfinally
0x8bca  ldarg.0
0x8bcb  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>> Microsoft.Crm.Asynchronous.ImportFileHelperData::_columnMappingIdToPicklistMappingCollectionDictionary
0x8bd0  ldarg.1
0x8bd1  ldloc.1
0x8bd2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [mscorlib]System.Guid, class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>>::Add(var<u1>, !!T0)
0x8bd7  ret
```
