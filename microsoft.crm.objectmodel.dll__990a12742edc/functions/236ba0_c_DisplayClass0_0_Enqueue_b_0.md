# <>c__DisplayClass0_0::<Enqueue>b__0

- ea: `0x236ba0`
- end: `0x23708e`
- name: `<>c__DisplayClass0_0::<Enqueue>b__0`
- size: `1262`
- prototype: ``
- caller_count: `0`
- callee_count: `23`
- tags: `loader_planting, installer_update`

## callees

- `0xc0000`
- `0xc0010`
- `0xc0020`
- `0xc0030`
- `0xc0040`
- `0xc0050`
- `0xc0060`
- `0xc0070`
- `0xc0080`
- `0xc0090`
- `0xc00a0`
- `0xc00b0`
- `0xc00d0`
- `0xc00f0`
- `0xc0110`
- `0xc0130`
- `0xc0150`
- `0xc0200`
- `0xc0430`
- `0xc0db0`
- `0xc0dc0`
- `0xc12c0`
- `0x236ba0`

## string_xrefs

- `0x236c0c`: `dependencytoken`
- `0x236f27`: `owningextensionid`
- `0x236f77`: `owningextensionidname`
- `0x236f47`: `owningextensiontypecode`
- `0x236dc7`: `parentpluginexecutionid`
- `0x236dd4`: `parentpluginexecutionid`
- `0x236d87`: `correlationupdatedtime`

## pseudocode

```c

```

## disassembly

```asm
0x236ba0  ldarg.0
0x236ba1  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236ba6  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken Microsoft.Crm.ObjectModel.AsyncRequest::get_CorrelationToken()
0x236bab  callvirt instance int32 [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_Depth()
0x236bb0  ldc.i4.0
0x236bb1  bge.s    loc_236BC4
0x236bb3  ldarg.0
0x236bb4  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236bb9  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken Microsoft.Crm.ObjectModel.AsyncRequest::get_CorrelationToken()
0x236bbe  ldc.i4.0
0x236bbf  callvirt instance void [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::set_Depth(int32)
0x236bc4  ldarg.0
0x236bc5  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass0_0::context
0x236bca  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x236bcf  newobj   instance void [Microsoft.Crm.Entities]Microsoft.Crm.Entities.AsyncOperation::.ctor(valuetype [mscorlib]System.Guid)
0x236bd4  stloc.0
0x236bd5  ldloc.0
0x236bd6  ldstr    aOperationtype// "operationtype"
0x236bdb  ldarg.0
0x236bdc  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236be1  callvirt instance int32 Microsoft.Crm.ObjectModel.AsyncRequest::get_OperationType()
0x236be6  box      [mscorlib]System.Int32
0x236beb  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236bf0  ldloc.0
0x236bf1  ldstr    aData_0// "data"
0x236bf6  ldarg.0
0x236bf7  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236bfc  callvirt instance string Microsoft.Crm.ObjectModel.AsyncRequest::get_Data()
0x236c01  call     object Microsoft.Crm.ObjectModel.AsyncQueue::ConvertEmptyStringToNull(string value)
0x236c06  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236c0b  ldloc.0
0x236c0c  ldstr    aDependencytoke// "dependencytoken"
0x236c11  ldarg.0
0x236c12  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236c17  callvirt instance string Microsoft.Crm.ObjectModel.AsyncRequest::get_DependencyToken()
0x236c1c  call     object Microsoft.Crm.ObjectModel.AsyncQueue::ConvertEmptyStringToNull(string value)
0x236c21  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236c26  ldloc.0
0x236c27  ldstr    aPostponeuntil// "postponeuntil"
0x236c2c  ldarg.0
0x236c2d  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236c32  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime Microsoft.Crm.ObjectModel.AsyncRequest::get_PostponeUntil()
0x236c37  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236c3c  ldloc.0
0x236c3d  ldstr    aRequestid// "requestid"
0x236c42  ldarg.0
0x236c43  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236c48  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_RequestId()
0x236c4d  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>
0x236c52  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236c57  ldloc.0
0x236c58  ldstr    aName// "name"
0x236c5d  ldarg.0
0x236c5e  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236c63  callvirt instance string Microsoft.Crm.ObjectModel.AsyncRequest::get_Name()
0x236c68  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236c6d  ldarg.0
0x236c6e  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass0_0::context
0x236c73  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x236c78  ldc.i4   0x125C
0x236c7d  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(int32)
0x236c82  dup
0x236c83  ldstr    aRootexecutionc// "rootexecutioncontext"
0x236c88  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x236c8d  brfalse.s loc_236C9F
0x236c8f  ldloc.0
0x236c90  ldstr    aRootexecutionc// "rootexecutioncontext"
0x236c95  call     string [Microsoft.Xrm.Telemetry]Microsoft.Xrm.Telemetry.XrmTelemetryContext::CaptureRoot()
0x236c9a  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236c9f  dup
0x236ca0  ldstr    aSubtype// "subtype"
0x236ca5  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x236caa  brfalse.s loc_236CC7
0x236cac  ldloc.0
0x236cad  ldstr    aSubtype// "subtype"
0x236cb2  ldarg.0
0x236cb3  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236cb8  callvirt instance int32 Microsoft.Crm.ObjectModel.AsyncRequest::get_Subtype()
0x236cbd  box      [mscorlib]System.Int32
0x236cc2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236cc7  ldarg.0
0x236cc8  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236ccd  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_OwnerId()
0x236cd2  stloc.2
0x236cd3  ldloca.s 2
0x236cd5  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x236cda  brfalse.s loc_236D3A
0x236cdc  ldarg.0
0x236cdd  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236ce2  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_OwnerId()
0x236ce7  stloc.2
0x236ce8  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x236ced  stloc.3
0x236cee  ldloca.s 2
0x236cf0  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x236cf5  brtrue.s loc_236CFA
0x236cf7  ldc.i4.1
0x236cf8  br.s     loc_236D13
0x236cfa  ldloca.s 2
0x236cfc  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x236d01  brtrue.s loc_236D06
0x236d03  ldc.i4.0
0x236d04  br.s     loc_236D13
0x236d06  ldloca.s 2
0x236d08  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::GetValueOrDefault()
0x236d0d  ldloc.3
0x236d0e  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x236d13  brfalse.s loc_236D3A
0x236d15  ldloc.0
0x236d16  ldstr    aOwnerid// "ownerid"
0x236d1b  ldarg.0
0x236d1c  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236d21  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_OwnerId()
0x236d26  stloc.2
0x236d27  ldloca.s 2
0x236d29  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x236d2e  box      [mscorlib]System.Guid
0x236d33  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236d38  br.s     loc_236D55
0x236d3a  ldloc.0
0x236d3b  ldstr    aOwnerid// "ownerid"
0x236d40  ldarg.0
0x236d41  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass0_0::context
0x236d46  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext::get_Caller()
0x236d4b  box      [mscorlib]System.Guid
0x236d50  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236d55  ldloc.0
0x236d56  ldstr    aOwneridtype// "owneridtype"
0x236d5b  ldc.i4.8
0x236d5c  box      [mscorlib]System.Int32
0x236d61  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236d66  ldloc.0
0x236d67  ldstr    aCorrelationid_0// "correlationid"
0x236d6c  ldarg.0
0x236d6d  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236d72  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken Microsoft.Crm.ObjectModel.AsyncRequest::get_CorrelationToken()
0x236d77  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_CorrelationId()
0x236d7c  box      [mscorlib]System.Guid
0x236d81  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236d86  ldloc.0
0x236d87  ldstr    aCorrelationupd// "correlationupdatedtime"
0x236d8c  ldarg.0
0x236d8d  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236d92  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken Microsoft.Crm.ObjectModel.AsyncRequest::get_CorrelationToken()
0x236d97  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_CorrelationUpdatedTime()
0x236d9c  ldc.i4.1
0x236d9d  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.CrmDateTime::FromUniversal(valuetype [mscorlib]System.DateTime, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.Behavior)
0x236da2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236da7  ldloc.0
0x236da8  ldstr    aDepth// "depth"
0x236dad  ldarg.0
0x236dae  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236db3  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken Microsoft.Crm.ObjectModel.AsyncRequest::get_CorrelationToken()
0x236db8  callvirt instance int32 [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_Depth()
0x236dbd  box      [mscorlib]System.Int32
0x236dc2  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236dc7  ldstr    aParentpluginex// "parentpluginexecutionid"
0x236dcc  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::TryGetAttribute(string)
0x236dd1  brfalse.s loc_236DF3
0x236dd3  ldloc.0
0x236dd4  ldstr    aParentpluginex// "parentpluginexecutionid"
0x236dd9  ldarg.0
0x236dda  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236ddf  callvirt instance class [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken Microsoft.Crm.ObjectModel.AsyncRequest::get_CorrelationToken()
0x236de4  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core.WebServices]Microsoft.Crm.Extensibility.CorrelationToken::get_ParentPluginExecutionId()
0x236de9  box      [mscorlib]System.Guid
0x236dee  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236df3  ldarg.0
0x236df4  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236df9  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_WorkflowActivationId()
0x236dfe  stloc.2
0x236dff  ldloca.s 2
0x236e01  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x236e06  brfalse.s loc_236E2B
0x236e08  ldloc.0
0x236e09  ldstr    aWorkflowactiva// "workflowactivationid"
0x236e0e  ldarg.0
0x236e0f  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236e14  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_WorkflowActivationId()
0x236e19  stloc.2
0x236e1a  ldloca.s 2
0x236e1c  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x236e21  box      [mscorlib]System.Guid
0x236e26  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236e2b  ldloc.0
0x236e2c  ldstr    aMessagename// "messagename"
0x236e31  ldarg.0
0x236e32  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236e37  callvirt instance string Microsoft.Crm.ObjectModel.AsyncRequest::get_MessageName()
0x236e3c  call     object Microsoft.Crm.ObjectModel.AsyncQueue::ConvertEmptyStringToNull(string value)
0x236e41  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236e46  ldarg.0
0x236e47  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236e4c  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_AsyncOperationId()
0x236e51  stloc.2
0x236e52  ldloca.s 2
0x236e54  call     instance bool valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_HasValue()
0x236e59  brfalse.s loc_236E9D
0x236e5b  ldarg.0
0x236e5c  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236e61  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_AsyncOperationId()
0x236e66  stloc.2
0x236e67  ldloca.s 2
0x236e69  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x236e6e  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x236e73  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x236e78  brfalse.s loc_236E9D
0x236e7a  ldloc.0
0x236e7b  ldstr    aAsyncoperation_6// "asyncoperationid"
0x236e80  ldarg.0
0x236e81  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236e86  callvirt instance valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid> Microsoft.Crm.ObjectModel.AsyncRequest::get_AsyncOperationId()
0x236e8b  stloc.2
0x236e8c  ldloca.s 2
0x236e8e  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.Guid>::get_Value()
0x236e93  box      [mscorlib]System.Guid
0x236e98  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236e9d  ldarg.0
0x236e9e  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236ea3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference Microsoft.Crm.ObjectModel.AsyncRequest::get_PrimaryEntity()
0x236ea8  brfalse.s loc_236F07
0x236eaa  ldarg.0
0x236eab  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236eb0  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference Microsoft.Crm.ObjectModel.AsyncRequest::get_PrimaryEntity()
0x236eb5  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference::get_IsNull()
0x236eba  brtrue.s loc_236F07
0x236ebc  ldloc.0
0x236ebd  ldstr    aPrimaryentityt_1// "primaryentitytype"
0x236ec2  ldarg.0
0x236ec3  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass0_0::context
0x236ec8  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x236ecd  ldarg.0
0x236ece  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236ed3  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference Microsoft.Crm.ObjectModel.AsyncRequest::get_PrimaryEntity()
0x236ed8  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference::get_Value()
0x236edd  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SdkSerializationCommon::EntityNameToObjectTypeCode(valuetype [mscorlib]System.Guid, string)
0x236ee2  box      [mscorlib]System.Int32
0x236ee7  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236eec  ldloc.0
0x236eed  ldstr    aPrimaryentityt_3// "primaryentitytypename"
0x236ef2  ldarg.0
0x236ef3  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236ef8  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference Microsoft.Crm.ObjectModel.AsyncRequest::get_PrimaryEntity()
0x236efd  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.EntityNameReference::get_Value()
0x236f02  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236f07  ldarg.0
0x236f08  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236f0d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_OwningExtension()
0x236f12  brfalse.s loc_236F91
0x236f14  ldarg.0
0x236f15  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236f1a  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_OwningExtension()
0x236f1f  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_IsNull()
0x236f24  brtrue.s loc_236F91
0x236f26  ldloc.0
0x236f27  ldstr    aOwningextensio_3// "owningextensionid"
0x236f2c  ldarg.0
0x236f2d  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236f32  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_OwningExtension()
0x236f37  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x236f3c  box      [mscorlib]System.Guid
0x236f41  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236f46  ldloc.0
0x236f47  ldstr    aOwningextensio_5// "owningextensiontypecode"
0x236f4c  ldarg.0
0x236f4d  ldfld    class [Microsoft.Crm.Platform.Server]Microsoft.Crm.BusinessEntities.ExecutionContext <>c__DisplayClass0_0::context
0x236f52  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::get_OrganizationId()
0x236f57  ldarg.0
0x236f58  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236f5d  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_OwningExtension()
0x236f62  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x236f67  call     int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.SdkSerializationCommon::EntityNameToObjectTypeCode(valuetype [mscorlib]System.Guid, string)
0x236f6c  box      [mscorlib]System.Int32
0x236f71  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236f76  ldloc.0
0x236f77  ldstr    aOwningextensio_4// "owningextensionidname"
0x236f7c  ldarg.0
0x236f7d  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236f82  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_OwningExtension()
0x236f87  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_name()
0x236f8c  callvirt instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.BusinessEntities.BusinessEntity::set_Item(string, object)
0x236f91  ldarg.0
0x236f92  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236f97  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_RegardingObject()
0x236f9c  brfalse.s loc_236FEC
0x236f9e  ldarg.0
0x236f9f  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236fa4  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_RegardingObject()
0x236fa9  callvirt instance bool [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_IsNull()
0x236fae  brtrue.s loc_236FEC
0x236fb0  ldloc.0
0x236fb1  ldarg.0
0x236fb2  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236fb7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_RegardingObject()
0x236fbc  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_Value()
0x236fc1  ldarg.0
0x236fc2  ldfld    class Microsoft.Crm.ObjectModel.AsyncRequest <>c__DisplayClass0_0::request
0x236fc7  callvirt instance class [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.Lookup Microsoft.Crm.ObjectModel.AsyncRequest::get_RegardingObject()
0x236fcc  callvirt instance string [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.CrmReference::get_type()
0x236fd1  ldarg.0
  ... truncated ...
```
