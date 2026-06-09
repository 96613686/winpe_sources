# Microsoft.Crm.Metadata.Dependency.DependencyProcessor::RetrieveViewData

- ea: `0x643a0`
- end: `0x6448a`
- name: `Microsoft.Crm.Metadata.Dependency.DependencyProcessor::RetrieveViewData`
- size: `234`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x642b0`

## callees

- `0x643a0`

## string_xrefs

- `0x643df`: `fetchxml`
- `0x6440f`: `layoutxml`
- `0x643f7`: `columnsetxml`

## pseudocode

```c

```

## disassembly

```asm
0x643a0  ldstr    aSavedquery// "SavedQuery"
0x643a5  ldarg.2
0x643a6  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::.ctor(string, class [Microsoft.Crm.Core]Microsoft.Crm.IUserAndOrganizationContext)
0x643ab  stloc.0
0x643ac  ldloc.0
0x643ad  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_Criteria()
0x643b2  ldarg.1
0x643b3  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_Metadata()
0x643b8  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_PrimaryKey()
0x643bd  ldc.i4.0
0x643be  ldarg.1
0x643bf  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::get_PrimaryKey()
0x643c4  callvirt instance string [mscorlib]System.Object::ToString()
0x643c9  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ConditionExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.FilterExpression::AddCondition(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata, valuetype [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ConditionOperator, object)
0x643ce  pop
0x643cf  ldc.i4.8
0x643d0  newarr   [mscorlib]System.String
0x643d5  dup
0x643d6  ldc.i4.0
0x643d7  ldstr    aSavedqueryid// "savedqueryid"
0x643dc  stelem.ref
0x643dd  dup
0x643de  ldc.i4.1
0x643df  ldstr    aFetchxml// "fetchxml"
0x643e4  stelem.ref
0x643e5  dup
0x643e6  ldc.i4.2
0x643e7  ldstr    aReturnedtypeco// "returnedtypecode"
0x643ec  stelem.ref
0x643ed  dup
0x643ee  ldc.i4.3
0x643ef  ldstr    aQueryapi// "queryapi"
0x643f4  stelem.ref
0x643f5  dup
0x643f6  ldc.i4.4
0x643f7  ldstr    aColumnsetxml_0// "columnsetxml"
0x643fc  stelem.ref
0x643fd  dup
0x643fe  ldc.i4.5
0x643ff  ldstr    aName// "name"
0x64404  stelem.ref
0x64405  dup
0x64406  ldc.i4.6
0x64407  ldstr    aQuerytype// "querytype"
0x6440c  stelem.ref
0x6440d  dup
0x6440e  ldc.i4.7
0x6440f  ldstr    aLayoutxml_0// "layoutxml"
0x64414  stelem.ref
0x64415  stloc.1
0x64416  ldloc.0
0x64417  callvirt instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression::get_ColumnSet()
0x6441c  ldloc.1
0x6441d  callvirt instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.ColumnSetExpression::AddColumns(string[])
0x64422  ldarg.0
0x64423  ldfld    class [Microsoft.Crm.ObjectModel]Microsoft.Crm.ObjectModel.SavedQueryService Microsoft.Crm.Metadata.Dependency.DependencyProcessor::_savedQueryService
0x64428  ldloc.0
0x64429  ldarg.2
0x6442a  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x6442f  stloc.2
0x64430  ldarg.2
0x64431  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x64436  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SerializationState::set_UserId(valuetype [mscorlib]System.Guid)
0x6443b  ldarg.2
0x6443c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x64441  call     void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SerializationState::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x64446  ldarg.2
0x64447  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x6444c  ldarg.2
0x6444d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_UserId()
0x64452  ldc.i4.0
0x64453  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ConversionContext::.ctor(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, int32)
0x64458  stloc.3
0x64459  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionToEntityCollectionConverter::.ctor()
0x6445e  ldloc.3
0x6445f  ldloc.2
0x64460  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollectionToEntityCollectionConverter::Convert(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.ICrmConversionContext, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection)
0x64465  stloc.s  4
0x64467  ldloc.s  4
0x64469  brfalse.s loc_6447A
0x6446b  ldloc.s  4
0x6446d  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x64472  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Count()
0x64477  ldc.i4.0
0x64478  bgt.s    loc_6447C
0x6447a  ldnull
0x6447b  ret
0x6447c  ldloc.s  4
0x6447e  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x64483  ldc.i4.0
0x64484  callvirt instance var<u1> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Item(!!T0)
0x64489  ret
```
