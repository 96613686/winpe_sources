# Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::Post

- ea: `0x3dd0`
- end: `0x42d6`
- name: `Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::Post`
- size: `1286`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x42e0`

## callees

- `0x1850`
- `0x1870`
- `0x1890`
- `0x18b0`
- `0x18d0`
- `0x18f0`
- `0x1950`
- `0x1970`
- `0x1990`
- `0x19d0`
- `0x3dd0`
- `0x44a0`
- `0x46a0`
- `0x4a70`
- `0x54d0`

## string_xrefs

- `0x3e1d`: `value.Initiator.DirectoryObjectId`
- `0x3e60`: `No CrmUserId found for DirectoryObjectId : `
- `0x3fca`: `Cannot re-install with a different packageUrl from the original. OrgId [{0}] SolutionId [{1}] ExistingUrl [{2}] NewUrl [{3}]`
- `0x4082`: `This solution is currently being installed. You must wait for it to complete or fail before attempting installation again. OrgId [{0}] SolutionId [{1}] State [{2}]`

## pseudocode

```c

```

## disassembly

```asm
0x3dd0  newobj   instance void <>c__DisplayClass4_0::.ctor()
0x3dd5  stloc.0
0x3dd6  ldloc.0
0x3dd7  ldarg.2
0x3dd8  stfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3ddd  ldarg.1
0x3dde  ldstr    aOrganizationid// "organizationId"
0x3de3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3de8  ldloc.0
0x3de9  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3dee  ldstr    aValue// "value"
0x3df3  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3df8  ldloc.0
0x3df9  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3dfe  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x3e03  ldstr    aValueInitiator// "value.Initiator"
0x3e08  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNull(object, string)
0x3e0d  ldloc.0
0x3e0e  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3e13  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x3e18  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x3e1d  ldstr    aValueInitiator_0// "value.Initiator.DirectoryObjectId"
0x3e22  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3e27  ldloc.0
0x3e28  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3e2d  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_PackageUrl()
0x3e32  ldstr    aValuePackageur// "value.PackageUrl"
0x3e37  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3e3c  ldarg.1
0x3e3d  ldloc.0
0x3e3e  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3e43  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x3e48  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x3e4d  call     valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Controllers.UserController::GetCrmUserId(valuetype [mscorlib]System.Guid organizationId, valuetype [mscorlib]System.Guid directoryObjectId)
0x3e52  stloc.1
0x3e53  ldloc.1
0x3e54  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3e59  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3e5e  brfalse.s loc_3E8F
0x3e60  ldstr    aNoCrmuseridFou// "No CrmUserId found for DirectoryObjectI"...
0x3e65  ldloc.0
0x3e66  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3e6b  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x3e70  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x3e75  stloc.s  5
0x3e77  ldloca.s 5
0x3e79  constrained. [mscorlib]System.Guid
0x3e7f  callvirt instance string [mscorlib]System.Object::ToString()
0x3e84  call     string [mscorlib]System.String::Concat(string, string)
0x3e89  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3e8e  throw
0x3e8f  ldarg.1
0x3e90  call     string Microsoft.Crm.ScaleGroupApi.Controllers.ImportSolutionGroupIdCreator::CreateGroupIdForOrganization(valuetype [mscorlib]System.Guid organizationId)
0x3e95  stloc.2
0x3e96  ldloc.0
0x3e97  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3e9c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_InstancePackageId()
0x3ea1  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3ea6  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3eab  brfalse  loc_4212
0x3eb0  ldloc.0
0x3eb1  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3eb6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_SolutionId()
0x3ebb  ldstr    aValueSolutioni// "value.SolutionId"
0x3ec0  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfGuidEmpty(valuetype [mscorlib]System.Guid, string)
0x3ec5  ldloc.0
0x3ec6  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3ecb  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_UniqueName()
0x3ed0  ldstr    aValueUniquenam// "value.UniqueName"
0x3ed5  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3eda  ldloc.0
0x3edb  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3ee0  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Version()
0x3ee5  ldstr    aValueVersion// "value.Version"
0x3eea  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrEmpty(string, string)
0x3eef  ldarg.1
0x3ef0  call     class [Microsoft.Crm]Microsoft.Crm.Data.IBasicOrganizationDataContext [Microsoft.Crm]Microsoft.Crm.Data.BasicOrganizationDataContext::New(valuetype [mscorlib]System.Guid)
0x3ef5  stloc.s  6
0x3ef7  ldloc.s  6
0x3ef9  callvirt instance class [System.Data.Linq]System.Data.Linq.ITable`1<class [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage> [Microsoft.Crm]Microsoft.Crm.Data.IBasicOrganizationDataContext::get_SolutionPackageTable()
0x3efe  ldtoken  [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage
0x3f03  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f08  ldstr    aSol// "sol"
0x3f0d  call     class [System.Core]System.Linq.Expressions.ParameterExpression [System.Core]System.Linq.Expressions.Expression::Parameter(class [mscorlib]System.Type, string)
0x3f12  stloc.s  0xB
0x3f14  ldloc.s  0xB
0x3f16  ldtoken  instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_SolutionId()
0x3f1b  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x3f20  castclass [mscorlib]System.Reflection.MethodInfo
0x3f25  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x3f2a  ldloc.0
0x3f2b  ldtoken  <>c__DisplayClass4_0
0x3f30  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x3f35  call     class [System.Core]System.Linq.Expressions.ConstantExpression [System.Core]System.Linq.Expressions.Expression::Constant(object, class [mscorlib]System.Type)
0x3f3a  ldtoken  class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3f3f  call     class [mscorlib]System.Reflection.FieldInfo [mscorlib]System.Reflection.FieldInfo::GetFieldFromHandle(valuetype [mscorlib]System.RuntimeFieldHandle)
0x3f44  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Field(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.FieldInfo)
0x3f49  ldtoken  instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_SolutionId()
0x3f4e  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x3f53  castclass [mscorlib]System.Reflection.MethodInfo
0x3f58  call     class [System.Core]System.Linq.Expressions.MemberExpression [System.Core]System.Linq.Expressions.Expression::Property(class [System.Core]System.Linq.Expressions.Expression, class [mscorlib]System.Reflection.MethodInfo)
0x3f5d  ldc.i4.0
0x3f5e  ldtoken  bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x3f63  call     class [mscorlib]System.Reflection.MethodBase [mscorlib]System.Reflection.MethodBase::GetMethodFromHandle(valuetype [mscorlib]System.RuntimeMethodHandle)
0x3f68  castclass [mscorlib]System.Reflection.MethodInfo
0x3f6d  call     class [System.Core]System.Linq.Expressions.BinaryExpression [System.Core]System.Linq.Expressions.Expression::Equal(class [System.Core]System.Linq.Expressions.Expression, class [System.Core]System.Linq.Expressions.Expression, bool, class [mscorlib]System.Reflection.MethodInfo)
0x3f72  ldc.i4.1
0x3f73  newarr   [System.Core]System.Linq.Expressions.ParameterExpression
0x3f78  dup
0x3f79  ldc.i4.0
0x3f7a  ldloc.s  0xB
0x3f7c  stelem.ref
0x3f7d  call     T0x2B00001A
0x3f82  call     T0x2B00001B
0x3f87  call     T0x2B000024
0x3f8c  stloc.s  7
0x3f8e  ldloc.s  7
0x3f90  brfalse  loc_40C3
0x3f95  ldloc.s  7
0x3f97  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackageState [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_State()
0x3f9c  ldc.i4.3
0x3f9d  beq.s    loc_3FAC
0x3f9f  ldloc.s  7
0x3fa1  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackageState [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_State()
0x3fa6  ldc.i4.2
0x3fa7  bne.un   loc_407D
0x3fac  ldloc.s  7
0x3fae  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_PackageUrl()
0x3fb3  ldloc.0
0x3fb4  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3fb9  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_PackageUrl()
0x3fbe  call     bool Microsoft.Crm.ScaleGroupApi.Controllers.SolutionController::UrlsHaveSamePath(string url1, string url2)
0x3fc3  brtrue.s loc_4014
0x3fc5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3fca  ldstr    aCannotReInstal// "Cannot re-install with a different pack"...
0x3fcf  ldc.i4.4
0x3fd0  newarr   [mscorlib]System.Object
0x3fd5  dup
0x3fd6  ldc.i4.0
0x3fd7  ldarg.1
0x3fd8  box      [mscorlib]System.Guid
0x3fdd  stelem.ref
0x3fde  dup
0x3fdf  ldc.i4.1
0x3fe0  ldloc.0
0x3fe1  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x3fe6  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_SolutionId()
0x3feb  box      [mscorlib]System.Guid
0x3ff0  stelem.ref
0x3ff1  dup
0x3ff2  ldc.i4.2
0x3ff3  ldloc.s  7
0x3ff5  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_PackageUrl()
0x3ffa  stelem.ref
0x3ffb  dup
0x3ffc  ldc.i4.3
0x3ffd  ldloc.0
0x3ffe  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x4003  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_PackageUrl()
0x4008  stelem.ref
0x4009  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x400e  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x4013  throw
0x4014  ldloc.s  7
0x4016  ldloc.1
0x4017  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_InitiatorCrmUserId(valuetype [mscorlib]System.Guid)
0x401c  ldloc.s  7
0x401e  ldloc.0
0x401f  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x4024  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x4029  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x402e  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_InitiatorObjectId(valuetype [mscorlib]System.Guid)
0x4033  ldloc.s  7
0x4035  ldc.i4.0
0x4036  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_State(valuetype [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackageState)
0x403b  ldloc.s  7
0x403d  ldloc.0
0x403e  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x4043  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_PackageUrl()
0x4048  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_PackageUrl(string)
0x404d  ldloc.s  7
0x404f  ldloc.0
0x4050  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x4055  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_UniqueName()
0x405a  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_UniqueName(string)
0x405f  ldloc.s  7
0x4061  ldloc.0
0x4062  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x4067  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Version()
0x406c  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_Version(string)
0x4071  ldloc.s  6
0x4073  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.IBasicOrganizationDataContext::SubmitChanges()
0x4078  br       loc_414E
0x407d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4082  ldstr    aThisSolutionIs// "This solution is currently being instal"...
0x4087  ldc.i4.3
0x4088  newarr   [mscorlib]System.Object
0x408d  dup
0x408e  ldc.i4.0
0x408f  ldarg.1
0x4090  box      [mscorlib]System.Guid
0x4095  stelem.ref
0x4096  dup
0x4097  ldc.i4.1
0x4098  ldloc.0
0x4099  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x409e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_SolutionId()
0x40a3  box      [mscorlib]System.Guid
0x40a8  stelem.ref
0x40a9  dup
0x40aa  ldc.i4.2
0x40ab  ldloc.s  7
0x40ad  callvirt instance valuetype [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackageState [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_State()
0x40b2  box      [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackageState
0x40b7  stelem.ref
0x40b8  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x40bd  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x40c2  throw
0x40c3  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::.ctor()
0x40c8  stloc.s  7
0x40ca  ldloc.s  7
0x40cc  ldloc.1
0x40cd  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_InitiatorCrmUserId(valuetype [mscorlib]System.Guid)
0x40d2  ldloc.s  7
0x40d4  ldloc.0
0x40d5  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x40da  callvirt instance class Microsoft.Crm.ScaleGroupApi.Models.SGUserContext Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Initiator()
0x40df  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGUserContext::get_DirectoryObjectId()
0x40e4  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_InitiatorObjectId(valuetype [mscorlib]System.Guid)
0x40e9  ldloc.s  7
0x40eb  ldloc.0
0x40ec  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x40f1  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_PackageUrl()
0x40f6  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_PackageUrl(string)
0x40fb  ldloc.s  7
0x40fd  ldloc.0
0x40fe  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x4103  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_SolutionId()
0x4108  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_SolutionId(valuetype [mscorlib]System.Guid)
0x410d  ldloc.s  7
0x410f  ldc.i4.0
0x4110  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_State(valuetype [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackageState)
0x4115  ldloc.s  7
0x4117  ldloc.0
0x4118  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x411d  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_UniqueName()
0x4122  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_UniqueName(string)
0x4127  ldloc.s  7
0x4129  ldloc.0
0x412a  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x412f  callvirt instance string Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_Version()
0x4134  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::set_Version(string)
0x4139  ldloc.s  6
0x413b  callvirt instance class [System.Data.Linq]System.Data.Linq.ITable`1<class [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage> [Microsoft.Crm]Microsoft.Crm.Data.IBasicOrganizationDataContext::get_SolutionPackageTable()
0x4140  ldloc.s  7
0x4142  callvirt instance void class [System.Data.Linq]System.Data.Linq.ITable`1<class [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage>::InsertOnSubmit(var<u1>)
0x4147  ldloc.s  6
0x4149  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Data.IBasicOrganizationDataContext::SubmitChanges()
0x414e  newobj   instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::.ctor()
0x4153  stloc.s  8
0x4155  ldloc.s  8
0x4157  ldc.i4   0x83
0x415c  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemType(int32)
0x4161  newobj   instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.OrganizationImportSolutionInfoXml::.ctor()
0x4166  stloc.s  9
0x4168  ldloc.s  9
0x416a  ldloc.s  7
0x416c  callvirt instance string [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_PackageUrl()
0x4171  callvirt instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.OrganizationImportSolutionInfoXml::set_PackageUrl(string)
0x4176  ldloc.s  9
0x4178  ldloc.s  7
0x417a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_SolutionId()
0x417f  callvirt instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.OrganizationImportSolutionInfoXml::set_SolutionId(valuetype [mscorlib]System.Guid)
0x4184  ldloc.s  9
0x4186  ldloc.s  7
0x4188  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Data.SolutionPackage::get_InitiatorCrmUserId()
0x418d  callvirt instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.OrganizationImportSolutionInfoXml::set_UserId(valuetype [mscorlib]System.Guid)
0x4192  ldloc.s  9
0x4194  ldloc.0
0x4195  ldfld    class Microsoft.Crm.ScaleGroupApi.Models.SGSolution <>c__DisplayClass4_0::value
0x419a  callvirt instance bool Microsoft.Crm.ScaleGroupApi.Models.SGSolution::get_AllowPackageCodeExecution()
0x419f  callvirt instance void [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.OrganizationImportSolutionInfoXml::set_AllowPackageCodeExecution(bool)
0x41a4  ldloc.s  8
0x41a6  ldloc.s  9
0x41a8  callvirt instance string [Microsoft.Crm.CrmLive.ScaleGroupProvisioningTaskExecutor]Microsoft.Crm.CrmLive.Provisioning.OrganizationImportSolutionInfoXml::Serialize()
0x41ad  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ItemData(string)
0x41b2  ldloc.s  8
0x41b4  ldarg.1
0x41b5  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_OrganizationId(valuetype [mscorlib]System.Guid)
0x41ba  ldloc.s  8
0x41bc  call     class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider [Microsoft.Crm.Core]Microsoft.Crm.OrganizationMetadataProvider::get_Instance()
0x41c1  ldarg.1
0x41c2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationMetadataProvider::GetOrganizationScaleGroupId(valuetype [mscorlib]System.Guid)
0x41c7  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_ScaleGroupId(valuetype [mscorlib]System.Guid)
0x41cc  ldloc.s  8
0x41ce  ldloc.2
0x41cf  callvirt instance void [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase::set_GroupId(string)
0x41d4  call     class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::NewRequest()
0x41d9  ldloc.s  8
0x41db  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemRequest::CreateReady(class [Microsoft.Crm.ProvisioningQueue]Microsoft.Crm.ProvisioningQueue.QueueItemBase)
  ... truncated ...
```
