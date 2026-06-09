# Microsoft.Crm.Application.WebServices.WorkflowWebService::CanElevateToSystemUserForSystemJobRetrieve

- ea: `0x1e90`
- end: `0x1ff9`
- name: `Microsoft.Crm.Application.WebServices.WorkflowWebService::CanElevateToSystemUserForSystemJobRetrieve`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2000`

## callees

- `0x1e90`

## pseudocode

```c

```

## disassembly

```asm
0x1e90  ldstr    aAsyncoperation// "asyncoperation"
0x1e95  ldc.i4.1
0x1e96  ldc.i4.0
0x1e97  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1e9c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ea1  brfalse.s loc_1EB6
0x1ea3  ldstr    aWorkflow// "workflow"
0x1ea8  ldc.i4.1
0x1ea9  ldc.i4.0
0x1eaa  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1eaf  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::HasPrivilege(string, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.AccessRights, valuetype [Microsoft.Crm.Sdk]Microsoft.Crm.Sdk.PrivilegeDepth, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1eb4  brtrue.s loc_1EB8
0x1eb6  ldc.i4.0
0x1eb7  ret
0x1eb8  ldstr    aAsyncoperation// "asyncoperation"
0x1ebd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ec2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ec7  stloc.0
0x1ec8  ldloc.0
0x1ec9  ldarg.0
0x1eca  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1ecf  ldloc.0
0x1ed0  ldstr    aColumnsetColum// "<columnset><column>"
0x1ed5  ldloc.0
0x1ed6  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_PrimaryField()
0x1edb  ldstr    aColumnColumnWo// "</column><column>workflowactivationid</"...
0x1ee0  call     string [mscorlib]System.String::Concat(string, string, string)
0x1ee5  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x1eea  ldstr    aWorkflow// "workflow"
0x1eef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1ef4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(string, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1ef9  stloc.1
0x1efa  ldloc.0
0x1efb  ldstr    aWorkflowactiva// "workflowactivationid"
0x1f00  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1f05  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1f0a  stloc.2
0x1f0b  ldloc.1
0x1f0c  ldloc.2
0x1f0d  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x1f12  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Id(string)
0x1f17  ldloc.1
0x1f18  ldstr    aColumnsetColum// "<columnset><column>"
0x1f1d  ldloc.1
0x1f1e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_PrimaryField()
0x1f23  ldstr    aColumnColumnse// "</column></columnset>"
0x1f28  call     string [mscorlib]System.String::Concat(string, string, string)
0x1f2d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x1f32  ldc.i4.0
0x1f33  stloc.3
0x1f34  leave    loc_1FF7
0x1f39  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1f3e  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::.ctor(class [mscorlib]System.Exception, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1f43  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Errors.ErrorInformation::get_ErrorCode()
0x1f48  ldc.i4   0x80048306
0x1f4d  bne.un   loc_1FF3
0x1f52  ldloc.0
0x1f53  ldc.i4.1
0x1f54  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.AutoSystemUserImpersonatorForEntity::.ctor(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity, bool)
0x1f59  stloc.s  6
0x1f5b  ldloc.0
0x1f5c  ldstr    aColumnsetColum_0// "<columnset><column>regardingobjectid</c"...
0x1f61  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string)
0x1f66  leave.s  loc_1F74
0x1f68  ldloc.s  6
0x1f6a  brfalse.s loc_1F73
0x1f6c  ldloc.s  6
0x1f6e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f73  endfinally
0x1f74  ldloc.0
0x1f75  ldstr    aRegardingobjec// "regardingobjectid"
0x1f7a  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x1f7f  isinst   [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue
0x1f84  stloc.s  4
0x1f86  ldloc.s  4
0x1f88  ldnull
0x1f89  cgt.un
0x1f8b  ldstr    aSystemjob0Does// "SystemJob {0} does not have a regarding"...
0x1f90  ldc.i4.1
0x1f91  newarr   [mscorlib]System.Object
0x1f96  dup
0x1f97  ldc.i4.0
0x1f98  ldloc.0
0x1f99  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x1f9e  stelem.ref
0x1f9f  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string, object[])
0x1fa4  ldloc.s  4
0x1fa6  brtrue.s loc_1FAC
0x1fa8  ldc.i4.0
0x1fa9  stloc.3
0x1faa  leave.s  loc_1FF7
0x1fac  ldloc.s  4
0x1fae  callvirt instance int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_Type()
0x1fb3  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x1fb8  newobj   instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::.ctor(int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x1fbd  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityFactory::CreateEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x1fc2  stloc.s  5
0x1fc4  ldloc.s  5
0x1fc6  ldloc.s  4
0x1fc8  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.LookupValue::get_ID()
0x1fcd  ldstr    aColumnsetColum// "<columnset><column>"
0x1fd2  ldloc.s  5
0x1fd4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_PrimaryField()
0x1fd9  ldstr    aColumnColumnse// "</column></columnset>"
0x1fde  call     string [mscorlib]System.String::Concat(string, string, string)
0x1fe3  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve(string, string)
0x1fe8  leave.s  loc_1FEF
0x1fea  pop
0x1feb  ldc.i4.0
0x1fec  stloc.3
0x1fed  leave.s  loc_1FF7
0x1fef  ldc.i4.1
0x1ff0  stloc.3
0x1ff1  leave.s  loc_1FF7
0x1ff3  leave.s  loc_1FF5
0x1ff5  ldc.i4.0
0x1ff6  ret
0x1ff7  ldloc.3
0x1ff8  ret
```
