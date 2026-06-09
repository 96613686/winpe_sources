# Microsoft.Crm.ObjectModel.AppModuleService::RemoveAppComponents

- ea: `0x97b50`
- end: `0x980d6`
- name: `Microsoft.Crm.ObjectModel.AppModuleService::RemoveAppComponents`
- size: `1414`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callees

- `0x8f9b0`
- `0x93f40`
- `0x946c0`
- `0x94a50`
- `0x958c0`
- `0x97140`
- `0x972d0`
- `0x97400`
- `0x97480`
- `0x97550`
- `0x97b50`
- `0x235ed0`

## string_xrefs

- `0x97d1d`: `componenttype`
- `0x97d9c`: `componenttype`
- `0x97de4`: `componenttype`
- `0x97ecb`: `componenttype`
- `0x97d2d`: `appmodulecomponentid`
- `0x97be6`: `AppModuleComponent`
- `0x97cfc`: `AppModuleComponent`
- `0x97c21`: `componentstate`
- `0x97cd7`: `componentstate`
- `0x97c6a`: `descriptor`
- `0x97bca`: `AppModule_BEGIN_{0}.AddAppComponents`
- `0x97b68`: `appComponents`
- `0x97b78`: `appComponents`
- `0x97caf`: `AppModuleService.RemoveAppComponents(): AppModule with [appmoduleid:{0}] not found, Exception: {0}`
- `0x97e59`: `AppModuleService.RemoveAppComponents(): [appmoduleid:{0}] No components to be removed.`
- `0x98058`: `AppModuleService.RemoveAppComponents(): [appmoduleid:{0}], Exception: {1}`
- `0x98085`: `Exception while executing RemoveAppComponents : {0}`
- `0x980b2`: `AppModule_END_{0}.RemoveAppComponents(appModule={1})`

## pseudocode

```c

```

## disassembly

```asm
0x97b50  ldarg.0
0x97b51  ldarg.3
0x97b52  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::ThrowExceptionIfFeatureNotEnabled(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x97b57  ldarg.1
0x97b58  box      [mscorlib]System.Guid
0x97b5d  ldstr    aAppid// "appId"
0x97b62  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x97b67  ldarg.2
0x97b68  ldstr    aAppcomponents_0// "appComponents"
0x97b6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x97b72  ldarg.2
0x97b73  call     T0x2B0000B2
0x97b78  ldstr    aAppcomponents_0// "appComponents"
0x97b7d  call     T0x2B00016C
0x97b82  ldarg.2
0x97b83  call     T0x2B00016D
0x97b88  call     T0x2B0000B2
0x97b8d  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>)
0x97b92  starg.s  2
0x97b94  ldarg.3
0x97b95  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97b9a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x97b9f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x97ba4  stloc.0
0x97ba5  ldarg.0
0x97ba6  ldloc.0
0x97ba7  ldarg.3
0x97ba8  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AppModuleService::getListOfAppModuleEntities(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x97bad  stloc.1
0x97bae  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x97bb3  stloc.2
0x97bb4  ldc.i4.m1
0x97bb5  stloc.s  5
0x97bb7  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x97bbc  stloc.s  6
0x97bbe  newobj   instance void Microsoft.Crm.ObjectModel.AppModuleComponentService::.ctor()
0x97bc3  stloc.s  8
0x97bc5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x97bca  ldstr    aAppmoduleBegin_0// "AppModule_BEGIN_{0}.AddAppComponents"
0x97bcf  ldc.i4.1
0x97bd0  newarr   [mscorlib]System.Object
0x97bd5  dup
0x97bd6  ldc.i4.0
0x97bd7  ldarg.0
0x97bd8  stelem.ref
0x97bd9  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x97bde  call     void [Microsoft.Crm.Core]Microsoft.Crm.PerfControl::LogPerf(string)
0x97be3  ldnull
0x97be4  stloc.s  9
0x97be6  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x97beb  ldarg.3
0x97bec  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97bf1  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::.ctor(string, valuetype [mscorlib]System.Guid)
0x97bf6  stloc.s  0xA
0x97bf8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor()
0x97bfd  stloc.s  0xB
0x97bff  ldarg.0
0x97c00  ldstr    aAppmodule// "AppModule"
0x97c05  ldstr    aAppmoduleid// "appmoduleid"
0x97c0a  ldc.i4.1
0x97c0b  newarr   [mscorlib]System.Guid
0x97c10  dup
0x97c11  ldc.i4.0
0x97c12  ldarg.1
0x97c13  stelem   [mscorlib]System.Guid
0x97c18  ldc.i4.s 0xA
0x97c1a  newarr   [mscorlib]System.String
0x97c1f  dup
0x97c20  ldc.i4.0
0x97c21  ldstr    aComponentstate_0// "componentstate"
0x97c26  stelem.ref
0x97c27  dup
0x97c28  ldc.i4.1
0x97c29  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x97c2e  stelem.ref
0x97c2f  dup
0x97c30  ldc.i4.2
0x97c31  ldstr    aSolutionid// "solutionid"
0x97c36  stelem.ref
0x97c37  dup
0x97c38  ldc.i4.3
0x97c39  ldstr    aUniquename// "uniquename"
0x97c3e  stelem.ref
0x97c3f  dup
0x97c40  ldc.i4.4
0x97c41  ldstr    aName// "name"
0x97c46  stelem.ref
0x97c47  dup
0x97c48  ldc.i4.5
0x97c49  ldstr    aDescription// "description"
0x97c4e  stelem.ref
0x97c4f  dup
0x97c50  ldc.i4.6
0x97c51  ldstr    aModifiedon_0// "modifiedon"
0x97c56  stelem.ref
0x97c57  dup
0x97c58  ldc.i4.7
0x97c59  ldstr    aUrl// "url"
0x97c5e  stelem.ref
0x97c5f  dup
0x97c60  ldc.i4.8
0x97c61  ldstr    aClienttype// "clienttype"
0x97c66  stelem.ref
0x97c67  dup
0x97c68  ldc.i4.s 9
0x97c6a  ldstr    aDescriptor// "descriptor"
0x97c6f  stelem.ref
0x97c70  ldarg.3
0x97c71  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x97c76  stloc.s  7
0x97c78  ldarg.0
0x97c79  ldarg.1
0x97c7a  ldstr    aAppmodule// "AppModule"
0x97c7f  ldarg.3
0x97c80  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97c85  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker::.ctor(valuetype [mscorlib]System.Guid, string, valuetype [mscorlib]System.Guid)
0x97c8a  ldloc.s  7
0x97c8c  ldarg.3
0x97c8d  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveUnpublished(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityMoniker, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x97c92  stloc.s  0xC
0x97c94  ldloc.s  0xC
0x97c96  brtrue.s loc_97CD5
0x97c98  ldstr    aAppmodule// "AppModule"
0x97c9d  ldarg.1
0x97c9e  newobj   instance void [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.CrmObjectNotFoundException::.ctor(string, valuetype [mscorlib]System.Guid)
0x97ca3  stloc.s  0xE
0x97ca5  ldloc.s  0xE
0x97ca7  ldarg.3
0x97ca8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97cad  ldc.i4.s 0x47
0x97caf  ldstr    aAppmoduleservi_119// "AppModuleService.RemoveAppComponents():"...
0x97cb4  ldc.i4.2
0x97cb5  newarr   [mscorlib]System.Object
0x97cba  dup
0x97cbb  ldc.i4.0
0x97cbc  ldarg.1
0x97cbd  box      [mscorlib]System.Guid
0x97cc2  stelem.ref
0x97cc3  dup
0x97cc4  ldc.i4.1
0x97cc5  ldloc.s  0xE
0x97cc7  callvirt instance string [mscorlib]System.Exception::get_Message()
0x97ccc  stelem.ref
0x97ccd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x97cd2  ldloc.s  0xE
0x97cd4  throw
0x97cd5  ldloc.s  0xC
0x97cd7  ldstr    aComponentstate_0// "componentstate"
0x97cdc  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x97ce1  unbox.any [mscorlib]System.Int32
0x97ce6  stloc.s  5
0x97ce8  ldloc.s  0xC
0x97cea  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x97cef  callvirt instance object [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::GetAttributeValue(string)
0x97cf4  unbox.any [mscorlib]System.Guid
0x97cf9  stloc.s  6
0x97cfb  ldarg.0
0x97cfc  ldstr    aAppmodulecompo_1// "AppModuleComponent"
0x97d01  ldstr    aAppmoduleiduni// "appmoduleidunique"
0x97d06  ldc.i4.1
0x97d07  newarr   [mscorlib]System.Guid
0x97d0c  dup
0x97d0d  ldc.i4.0
0x97d0e  ldloc.s  6
0x97d10  stelem   [mscorlib]System.Guid
0x97d15  ldc.i4.3
0x97d16  newarr   [mscorlib]System.String
0x97d1b  dup
0x97d1c  ldc.i4.0
0x97d1d  ldstr    aComponenttype// "componenttype"
0x97d22  stelem.ref
0x97d23  dup
0x97d24  ldc.i4.1
0x97d25  ldstr    aObjectid// "objectid"
0x97d2a  stelem.ref
0x97d2b  dup
0x97d2c  ldc.i4.2
0x97d2d  ldstr    aAppmodulecompo// "appmodulecomponentid"
0x97d32  stelem.ref
0x97d33  ldarg.3
0x97d34  call     instance class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression Microsoft.Crm.ObjectModel.AppModuleService::GetEntityExpression(string platformName, string atrributeName, valuetype [mscorlib]System.Guid[] attributeValue, string[] columnNamesToBeRetrieved, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x97d39  stloc.s  7
0x97d3b  ldloc.s  8
0x97d3d  ldloc.s  7
0x97d3f  ldarg.3
0x97d40  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.BusinessProcessObject::RetrieveMultiple(class [Microsoft.Crm.Platform.Server]Microsoft.Crm.Query.EntityExpression, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext)
0x97d45  stloc.s  9
0x97d47  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReferenceCollection::.ctor()
0x97d4c  stloc.s  0xD
0x97d4e  ldarg.2
0x97d4f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::GetEnumerator()
0x97d54  stloc.s  0xF
0x97d56  br       loc_97E2E
0x97d5b  ldloc.s  0xF
0x97d5d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Current()
0x97d62  stloc.s  0x10
0x97d64  ldarg.0
0x97d65  ldloc.1
0x97d66  ldloc.s  0x10
0x97d68  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::appModuleOdataPayloadTransalation(class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype [mscorlib]System.Guid> entitiesName, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference)
0x97d6d  ldc.i4.0
0x97d6e  stloc.s  0x11
0x97d70  br       loc_97E20
0x97d75  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x97d7a  stloc.2
0x97d7b  ldc.i4.m1
0x97d7c  stloc.3
0x97d7d  ldloc.s  9
0x97d7f  ldloc.s  0x11
0x97d81  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x97d86  ldstr    aObjectid// "objectid"
0x97d8b  ldloca.s 2
0x97d8d  callvirt T0x2B00003B
0x97d92  pop
0x97d93  ldloc.s  9
0x97d95  ldloc.s  0x11
0x97d97  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::get_Item(int32)
0x97d9c  ldstr    aComponenttype// "componenttype"
0x97da1  ldloca.s 3
0x97da3  callvirt T0x2B00003C
0x97da8  pop
0x97da9  ldarg.0
0x97daa  ldloc.s  0x10
0x97dac  call     instance int32 Microsoft.Crm.ObjectModel.AppModuleService::getComponentTypeFromLogicalName(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference entityReference)
0x97db1  ldloc.3
0x97db2  bne.un.s loc_97E1A
0x97db4  ldloc.s  0x10
0x97db6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x97dbb  ldloc.2
0x97dbc  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x97dc1  brfalse.s loc_97E1A
0x97dc3  ldarg.3
0x97dc4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97dc9  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AppModuleComponent::.ctor(valuetype [mscorlib]System.Guid)
0x97dce  stloc.s  0x12
0x97dd0  ldloc.s  0x12
0x97dd2  ldstr    aObjectid// "objectid"
0x97dd7  ldloc.2
0x97dd8  box      [mscorlib]System.Guid
0x97ddd  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x97de2  ldloc.s  0x12
0x97de4  ldstr    aComponenttype// "componenttype"
0x97de9  ldloc.3
0x97dea  box      [mscorlib]System.Int32
0x97def  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x97df4  ldloc.s  0xD
0x97df6  ldloc.s  0x10
0x97df8  callvirt instance string [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_LogicalName()
0x97dfd  ldloc.s  0x10
0x97dff  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x97e04  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x97e09  callvirt instance void class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::Add(var<u1>)
0x97e0e  ldloc.s  0xA
0x97e10  ldloc.s  0x12
0x97e12  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntityCollection::Add(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity)
0x97e17  pop
0x97e18  br.s     loc_97E2E
0x97e1a  ldloc.s  0x11
0x97e1c  ldc.i4.1
0x97e1d  add
0x97e1e  stloc.s  0x11
0x97e20  ldloc.s  0x11
0x97e22  ldloc.s  9
0x97e24  callvirt instance int32 [mscorlib]System.Collections.CollectionBase::get_Count()
0x97e29  blt      loc_97D75
0x97e2e  ldloc.s  0xF
0x97e30  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x97e35  brtrue   loc_97D5B
0x97e3a  leave.s  loc_97E48
0x97e3c  ldloc.s  0xF
0x97e3e  brfalse.s loc_97E47
0x97e40  ldloc.s  0xF
0x97e42  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x97e47  endfinally
0x97e48  ldloc.s  0xD
0x97e4a  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference>::get_Count()
0x97e4f  brtrue.s loc_97E77
0x97e51  ldarg.3
0x97e52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x97e57  ldc.i4.s 0x47
0x97e59  ldstr    aAppmoduleservi_120// "AppModuleService.RemoveAppComponents():"...
0x97e5e  ldc.i4.1
0x97e5f  newarr   [mscorlib]System.Object
0x97e64  dup
0x97e65  ldc.i4.0
0x97e66  ldarg.1
0x97e67  box      [mscorlib]System.Guid
0x97e6c  stelem.ref
0x97e6d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x97e72  leave    loc_980D5
0x97e77  ldarg.3
0x97e78  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Transaction()
0x97e7d  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmTransaction::StartTransaction()
0x97e82  ldarg.0
0x97e83  ldloc.s  0xC
0x97e85  ldarg.3
0x97e86  call     instance void Microsoft.Crm.ObjectModel.AppModuleService::UpdateApp(class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.IBusinessEntity entity, class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext context)
0x97e8b  ldarg.0
0x97e8c  ldarg.1
0x97e8d  ldarg.3
  ... truncated ...
```
