# Microsoft.Crm.Workflow.WorkflowLoader::LoadWorkflow

- ea: `0x9ce0`
- end: `0x9fbd`
- name: `Microsoft.Crm.Workflow.WorkflowLoader::LoadWorkflow`
- size: `733`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x6900`
- `0x9ce0`
- `0xfc40`

## string_xrefs

- `0x9d1e`: `Creation of SdkService instance failed from the context - performing retry of service creation`
- `0x9d3a`: `Creation of SdkService instance failed from the context`
- `0x9d6c`: `asyncautodelete`
- `0x9e74`: `asyncautodelete`
- `0x9e84`: `asyncautodelete`

## pseudocode

```c

```

## disassembly

```asm
0x9ce0  ldarg.1
0x9ce1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9ce6  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x9ceb  ldstr    aWorkflowactiva// "workflowActivationId should not be empt"...
0x9cf0  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9cf5  ldarg.2
0x9cf6  ldnull
0x9cf7  cgt.un
0x9cf9  ldstr    aOrganizationco// "OrganizationContext should not be null"
0x9cfe  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9d03  ldarg.2
0x9d04  castclass Microsoft.Crm.Workflow.ICommonWorkflowContext
0x9d09  stloc.0
0x9d0a  ldloc.0
0x9d0b  ldc.i4.1
0x9d0c  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x9d11  stloc.1
0x9d12  ldloc.1
0x9d13  brtrue.s loc_9D44
0x9d15  ldnull
0x9d16  ldarg.2
0x9d17  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x9d1c  ldc.i4.s 0x14
0x9d1e  ldstr    aCreationOfSdks// "Creation of SdkService instance failed "...
0x9d23  ldc.i4.0
0x9d24  newarr   [mscorlib]System.Object
0x9d29  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x9d2e  ldloc.0
0x9d2f  ldc.i4.1
0x9d30  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Workflow.ICommonWorkflowContext::CreateSdkService(bool asAdminUser)
0x9d35  stloc.1
0x9d36  ldloc.1
0x9d37  ldnull
0x9d38  cgt.un
0x9d3a  ldstr    aCreationOfSdks_0// "Creation of SdkService instance failed "...
0x9d3f  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9d44  ldloc.1
0x9d45  ldstr    aWorkflow// "workflow"
0x9d4a  ldarg.1
0x9d4b  ldc.i4.s 0xA
0x9d4d  newarr   [mscorlib]System.String
0x9d52  dup
0x9d53  ldc.i4.0
0x9d54  ldstr    aXaml// "xaml"
0x9d59  stelem.ref
0x9d5a  dup
0x9d5b  ldc.i4.1
0x9d5c  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x9d61  stelem.ref
0x9d62  dup
0x9d63  ldc.i4.2
0x9d64  ldstr    aCategory// "category"
0x9d69  stelem.ref
0x9d6a  dup
0x9d6b  ldc.i4.3
0x9d6c  ldstr    aAsyncautodelet// "asyncautodelete"
0x9d71  stelem.ref
0x9d72  dup
0x9d73  ldc.i4.4
0x9d74  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x9d79  stelem.ref
0x9d7a  dup
0x9d7b  ldc.i4.5
0x9d7c  ldstr    aScope// "scope"
0x9d81  stelem.ref
0x9d82  dup
0x9d83  ldc.i4.6
0x9d84  ldstr    aOwnerid// "ownerid"
0x9d89  stelem.ref
0x9d8a  dup
0x9d8b  ldc.i4.7
0x9d8c  ldstr    aOwningbusiness// "owningbusinessunit"
0x9d91  stelem.ref
0x9d92  dup
0x9d93  ldc.i4.8
0x9d94  ldstr    aName// "name"
0x9d99  stelem.ref
0x9d9a  dup
0x9d9b  ldc.i4.s 9
0x9d9d  ldstr    aOndemand// "ondemand"
0x9da2  stelem.ref
0x9da3  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x9da8  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x9dad  stloc.2
0x9dae  ldloc.2
0x9daf  ldstr    aXaml// "xaml"
0x9db4  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9db9  isinst   [mscorlib]System.String
0x9dbe  stloc.3
0x9dbf  ldloc.3
0x9dc0  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x9dc5  ldc.i4.0
0x9dc6  ceq
0x9dc8  ldstr    aXamlShouldNotB// "xaml should not be null or white space"
0x9dcd  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x9dd2  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x9dd7  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x9ddc  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WorkflowXamlValidation()
0x9de1  ldarg.2
0x9de2  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9de7  stloc.s  4
0x9de9  call     class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl [Microsoft.Crm.Core]Microsoft.Crm.FeatureControl::get_Current()
0x9dee  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer [Microsoft.Crm.Core]Microsoft.Crm.IFeatureControl::get_Features()
0x9df3  callvirt instance class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetailContainer::get_WorkflowXamlValidationErrorReport()
0x9df8  ldarg.2
0x9df9  call     bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.FeatureEnabledHelper::IsFeatureEnabled(class [Microsoft.Crm.Core]Microsoft.Crm.IFeatureDetail, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x9dfe  stloc.s  5
0x9e00  ldnull
0x9e01  stloc.s  6
0x9e03  ldloc.3
0x9e04  newobj   instance void [mscorlib]System.IO.StringReader::.ctor(string)
0x9e09  stloc.s  0x10
0x9e0b  ldloc.s  0x10
0x9e0d  call     class [System.Xml]System.Xml.XmlReader [System.Xml]System.Xml.XmlReader::Create(class [mscorlib]System.IO.TextReader)
0x9e12  stloc.s  0x11
0x9e14  ldloc.s  0x11
0x9e16  ldloc.3
0x9e17  ldloc.s  4
0x9e19  ldloc.s  5
0x9e1b  newobj   instance void Microsoft.Crm.Workflow.Utility.XrmWorkflowXamlReader::.ctor(class [System.Xml]System.Xml.XmlReader xmlReader, string xaml, bool isValidateEnabled, bool isReportErrorEnabled)
0x9e20  stloc.s  0x12
0x9e22  ldloc.s  0x12
0x9e24  call     class [System.Activities]System.Activities.Activity [System.Activities]System.Activities.XamlIntegration.ActivityXamlServices::Load(class [System.Xaml]System.Xaml.XamlReader)
0x9e29  stloc.s  6
0x9e2b  leave.s  loc_9E51
0x9e2d  ldloc.s  0x12
0x9e2f  brfalse.s loc_9E38
0x9e31  ldloc.s  0x12
0x9e33  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9e38  endfinally
0x9e39  ldloc.s  0x11
0x9e3b  brfalse.s loc_9E44
0x9e3d  ldloc.s  0x11
0x9e3f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9e44  endfinally
0x9e45  ldloc.s  0x10
0x9e47  brfalse.s loc_9E50
0x9e49  ldloc.s  0x10
0x9e4b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x9e50  endfinally
0x9e51  ldloc.2
0x9e52  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x9e57  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9e5c  brtrue.s loc_9E61
0x9e5e  ldc.i4.0
0x9e5f  br.s     loc_9E71
0x9e61  ldloc.2
0x9e62  ldstr    aIscrmuiworkflo// "iscrmuiworkflow"
0x9e67  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9e6c  unbox.any [mscorlib]System.Boolean
0x9e71  stloc.s  7
0x9e73  ldloc.2
0x9e74  ldstr    aAsyncautodelet// "asyncautodelete"
0x9e79  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9e7e  brtrue.s loc_9E83
0x9e80  ldc.i4.0
0x9e81  br.s     loc_9E93
0x9e83  ldloc.2
0x9e84  ldstr    aAsyncautodelet// "asyncautodelete"
0x9e89  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9e8e  unbox.any [mscorlib]System.Boolean
0x9e93  stloc.s  8
0x9e95  ldloc.2
0x9e96  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x9e9b  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9ea0  brtrue.s loc_9EA5
0x9ea2  ldc.i4.0
0x9ea3  br.s     loc_9EB5
0x9ea5  ldloc.2
0x9ea6  ldstr    aSyncworkflowlo// "syncworkflowlogonfailure"
0x9eab  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9eb0  unbox.any [mscorlib]System.Boolean
0x9eb5  stloc.s  9
0x9eb7  ldloc.2
0x9eb8  ldstr    aOndemand// "ondemand"
0x9ebd  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9ec2  brtrue.s loc_9EC7
0x9ec4  ldc.i4.0
0x9ec5  br.s     loc_9ED7
0x9ec7  ldloc.2
0x9ec8  ldstr    aOndemand// "ondemand"
0x9ecd  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9ed2  unbox.any [mscorlib]System.Boolean
0x9ed7  stloc.s  0xA
0x9ed9  ldloc.2
0x9eda  ldstr    aCategory// "category"
0x9edf  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9ee4  brtrue.s loc_9EE9
0x9ee6  ldc.i4.0
0x9ee7  br.s     loc_9EFE
0x9ee9  ldloc.2
0x9eea  ldstr    aCategory// "category"
0x9eef  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9ef4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x9ef9  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x9efe  stloc.s  0xB
0x9f00  ldloc.2
0x9f01  ldstr    aName// "name"
0x9f06  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9f0b  brtrue.s loc_9F14
0x9f0d  ldsfld   string [mscorlib]System.String::Empty
0x9f12  br.s     loc_9F24
0x9f14  ldloc.2
0x9f15  ldstr    aName// "name"
0x9f1a  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9f1f  castclass [mscorlib]System.String
0x9f24  stloc.s  0xC
0x9f26  ldloc.2
0x9f27  ldstr    aScope// "scope"
0x9f2c  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9f31  brtrue.s loc_9F36
0x9f33  ldc.i4.1
0x9f34  br.s     loc_9F4B
0x9f36  ldloc.2
0x9f37  ldstr    aScope// "scope"
0x9f3c  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9f41  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x9f46  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x9f4b  stloc.s  0xD
0x9f4d  ldloc.2
0x9f4e  ldstr    aOwnerid// "ownerid"
0x9f53  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9f58  brtrue.s loc_9F61
0x9f5a  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9f5f  br.s     loc_9F76
0x9f61  ldloc.2
0x9f62  ldstr    aOwnerid// "ownerid"
0x9f67  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9f6c  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x9f71  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x9f76  stloc.s  0xE
0x9f78  ldloc.2
0x9f79  ldstr    aOwningbusiness// "owningbusinessunit"
0x9f7e  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x9f83  brtrue.s loc_9F8C
0x9f85  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9f8a  br.s     loc_9FA1
0x9f8c  ldloc.2
0x9f8d  ldstr    aOwningbusiness// "owningbusinessunit"
0x9f92  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x9f97  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x9f9c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x9fa1  stloc.s  0xF
0x9fa3  ldloc.s  6
0x9fa5  ldloc.s  7
0x9fa7  ldloc.s  0xB
0x9fa9  ldloc.s  8
0x9fab  ldloc.s  9
0x9fad  ldloc.s  0xD
0x9faf  ldloc.s  0xE
0x9fb1  ldloc.s  0xF
0x9fb3  ldloc.s  0xC
0x9fb5  ldloc.s  0xA
0x9fb7  newobj   instance void [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.WorkflowActivationData::.ctor(class [System.Activities]System.Activities.Activity, bool, int32, bool, bool, int32, valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid, string, bool)
0x9fbc  ret
```
