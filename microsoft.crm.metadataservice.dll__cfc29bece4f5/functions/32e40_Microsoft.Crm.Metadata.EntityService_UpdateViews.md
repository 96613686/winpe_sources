# Microsoft.Crm.Metadata.EntityService::UpdateViews

- ea: `0x32e40`
- end: `0x32ee8`
- name: `Microsoft.Crm.Metadata.EntityService::UpdateViews`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x32b80`

## callees

- `0x2cb00`
- `0x32e40`

## string_xrefs

- `0x32e6e`: `fetchxml`
- `0x32eab`: `fetchxml`

## pseudocode

```c

```

## disassembly

```asm
0x32e40  newobj   instance void [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::.ctor()
0x32e45  stloc.0
0x32e46  ldloc.0
0x32e47  ldc.i4.1
0x32e48  newarr   [mscorlib]System.Int32
0x32e4d  dup
0x32e4e  ldc.i4.0
0x32e4f  ldarg.1
0x32e50  callvirt instance int32 Microsoft.Crm.Metadata.EntityCreateInfo::get_ObjectTypeCode()
0x32e55  stelem.i4
0x32e56  ldc.i4.3
0x32e57  newarr   [mscorlib]System.String
0x32e5c  dup
0x32e5d  ldc.i4.0
0x32e5e  ldstr    aQuerytype// "querytype"
0x32e63  stelem.ref
0x32e64  dup
0x32e65  ldc.i4.1
0x32e66  ldstr    aReturnedtypeco// "returnedtypecode"
0x32e6b  stelem.ref
0x32e6c  dup
0x32e6d  ldc.i4.2
0x32e6e  ldstr    aFetchxml// "fetchxml"
0x32e73  stelem.ref
0x32e74  ldc.i4.5
0x32e75  newarr   [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryType
0x32e7a  dup
0x32e7b  ldtoken  valuetype __StaticArrayInitTypeSize=20 <PrivateImplementationDetails>::'4C4C420FC78EEB8D0E5448C144F4A8B5986D8CB7'
0x32e80  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::InitializeArray(class [mscorlib]System.Array, valuetype [mscorlib]System.RuntimeFieldHandle)
0x32e85  ldarg.2
0x32e86  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService::RetrieveSavedQueryForEntities(int32[], string[], valuetype [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryType[], class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32e8b  stloc.1
0x32e8c  ldloc.1
0x32e8d  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x32e92  ldc.i4.0
0x32e93  ble.s    loc_32EE7
0x32e95  ldloc.1
0x32e96  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.CollectionBase::GetEnumerator()
0x32e9b  stloc.2
0x32e9c  br.s     loc_32EC9
0x32e9e  ldloc.2
0x32e9f  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x32ea4  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity
0x32ea9  stloc.3
0x32eaa  ldloc.3
0x32eab  ldstr    aFetchxml// "fetchxml"
0x32eb0  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Item(string)
0x32eb5  castclass [mscorlib]System.String
0x32eba  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32ebf  brtrue.s loc_32EC9
0x32ec1  ldloc.0
0x32ec2  ldloc.3
0x32ec3  ldarg.2
0x32ec4  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::Update(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x32ec9  ldloc.2
0x32eca  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x32ecf  brtrue.s loc_32E9E
0x32ed1  leave.s  loc_32EE7
0x32ed3  ldloc.2
0x32ed4  isinst   [mscorlib]System.IDisposable
0x32ed9  stloc.s  4
0x32edb  ldloc.s  4
0x32edd  brfalse.s loc_32EE6
0x32edf  ldloc.s  4
0x32ee1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32ee6  endfinally
0x32ee7  ret
```
