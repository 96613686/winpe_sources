# Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetCustomActivityInfo_0

- ea: `0x1bd20`
- end: `0x1bf65`
- name: `Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetCustomActivityInfo_0`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1c060`

## callees

- `0x1b9f0`
- `0x1bad0`
- `0x1bd20`
- `0x1c030`
- `0x1c040`
- `0x1c6d0`
- `0x1c6e0`
- `0x1c720`
- `0x1d580`
- `0x1d890`

## string_xrefs

- `0x1bdc6`: `pluginassemblyid`
- `0x1be39`: `publickeytoken`

## pseudocode

```c

```

## disassembly

```asm
0x1bd20  ldarg.0
0x1bd21  ldarg.1
0x1bd22  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetPluginTypeEntity(valuetype [mscorlib]System.Guid pluginTypeId)
0x1bd27  stloc.0
0x1bd28  ldloc.0
0x1bd29  ldstr    aName// "name"
0x1bd2e  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1bd33  brtrue.s loc_1BD38
0x1bd35  ldnull
0x1bd36  br.s     loc_1BD48
0x1bd38  ldloc.0
0x1bd39  ldstr    aName// "name"
0x1bd3e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bd43  isinst   [mscorlib]System.String
0x1bd48  stloc.1
0x1bd49  ldloc.0
0x1bd4a  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x1bd4f  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1bd54  brtrue.s loc_1BD59
0x1bd56  ldnull
0x1bd57  br.s     loc_1BD69
0x1bd59  ldloc.0
0x1bd5a  ldstr    aWorkflowactivi// "workflowactivitygroupname"
0x1bd5f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bd64  isinst   [mscorlib]System.String
0x1bd69  stloc.2
0x1bd6a  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::.ctor()
0x1bd6f  stloc.3
0x1bd70  ldloc.0
0x1bd71  ldstr    aCustomworkflow// "customworkflowactivityinfo"
0x1bd76  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1bd7b  brfalse.s loc_1BDC5
0x1bd7d  ldloc.0
0x1bd7e  ldstr    aCustomworkflow// "customworkflowactivityinfo"
0x1bd83  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bd88  brfalse.s loc_1BDC5
0x1bd8a  ldloc.0
0x1bd8b  ldstr    aCustomworkflow// "customworkflowactivityinfo"
0x1bd90  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bd95  castclass [mscorlib]System.String
0x1bd9a  call     class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::DeserializeCustomActivityInfo(string serializedCustomActivityInfo)
0x1bd9f  stloc.3
0x1bda0  ldloc.3
0x1bda1  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_CustomActivityInfo()
0x1bda6  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_PluginTypeId()
0x1bdab  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1bdb0  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1bdb5  brfalse.s loc_1BDC3
0x1bdb7  ldloc.3
0x1bdb8  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_CustomActivityInfo()
0x1bdbd  ldarg.1
0x1bdbe  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::set_PluginTypeId(valuetype [mscorlib]System.Guid)
0x1bdc3  ldloc.3
0x1bdc4  ret
0x1bdc5  ldloc.0
0x1bdc6  ldstr    aPluginassembly// "pluginassemblyid"
0x1bdcb  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bdd0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x1bdd5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x1bdda  stloc.s  4
0x1bddc  ldarg.0
0x1bddd  ldloc.s  4
0x1bddf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetPluginAssembly(valuetype [mscorlib]System.Guid assemblyId)
0x1bde4  stloc.s  5
0x1bde6  newobj   instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::.ctor()
0x1bdeb  stloc.s  6
0x1bded  ldloc.s  6
0x1bdef  ldloc.s  5
0x1bdf1  ldstr    aName// "name"
0x1bdf6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bdfb  castclass [mscorlib]System.String
0x1be00  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_Name(string)
0x1be05  ldloc.s  6
0x1be07  ldloc.s  5
0x1be09  ldstr    aVersion// "version"
0x1be0e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1be13  castclass [mscorlib]System.String
0x1be18  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_Version(string)
0x1be1d  ldloc.s  6
0x1be1f  ldloc.s  5
0x1be21  ldstr    aCulture// "culture"
0x1be26  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1be2b  castclass [mscorlib]System.String
0x1be30  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_Culture(string)
0x1be35  ldloc.s  6
0x1be37  ldloc.s  5
0x1be39  ldstr    aPublickeytoken// "publickeytoken"
0x1be3e  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1be43  castclass [mscorlib]System.String
0x1be48  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_PublicKeyToken(string)
0x1be4d  ldloc.s  6
0x1be4f  ldloc.0
0x1be50  ldstr    aTypename// "typename"
0x1be55  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1be5a  castclass [mscorlib]System.String
0x1be5f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_TypeName(string)
0x1be64  ldloc.s  6
0x1be66  ldloc.1
0x1be67  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_ActivityName(string)
0x1be6c  ldloc.s  6
0x1be6e  ldloc.2
0x1be6f  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_ActivityGroupName(string)
0x1be74  ldloc.s  6
0x1be76  ldarg.1
0x1be77  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_PluginTypeId(valuetype [mscorlib]System.Guid)
0x1be7c  ldloc.s  5
0x1be7e  ldstr    aContent// "content"
0x1be83  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1be88  brfalse.s loc_1BEA2
0x1be8a  ldloc.s  6
0x1be8c  ldloc.s  5
0x1be8e  ldstr    aContent// "content"
0x1be93  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1be98  isinst   [mscorlib]System.String
0x1be9d  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_Content(string)
0x1bea2  ldloc.s  6
0x1bea4  ldloc.s  5
0x1bea6  ldstr    aSourcetype// "sourcetype"
0x1beab  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1beb0  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x1beb5  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x1beba  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_SourceType(int32)
0x1bebf  ldloc.s  5
0x1bec1  ldstr    aPath// "path"
0x1bec6  callvirt instance bool [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::Contains(string)
0x1becb  brfalse.s loc_1BEE5
0x1becd  ldloc.s  6
0x1becf  ldloc.s  5
0x1bed1  ldstr    aPath// "path"
0x1bed6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bedb  castclass [mscorlib]System.String
0x1bee0  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo::set_Path(string)
0x1bee5  ldarg.0
0x1bee6  ldloc.s  6
0x1bee8  ldloc.s  5
0x1beea  ldstr    aIsolationmode// "isolationmode"
0x1beef  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x1bef4  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue
0x1bef9  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x1befe  ldloc.s  4
0x1bf00  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetCustomActivityInfo(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.ActivityInfo activityInfo, int32 isolationMode, valuetype [mscorlib]System.Guid pluginAssemblyId)
0x1bf05  stloc.3
0x1bf06  ldloc.3
0x1bf07  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfo [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_CustomActivityInfo()
0x1bf0c  callvirt instance bool [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoBase::get_IsNet4()
0x1bf11  brtrue.s loc_1BF2D
0x1bf13  ldloc.3
0x1bf14  ldarg.0
0x1bf15  ldarg.1
0x1bf16  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetInputsInfo(valuetype [mscorlib]System.Guid pluginType)
0x1bf1b  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_Inputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[])
0x1bf20  ldloc.3
0x1bf21  ldarg.0
0x1bf22  ldarg.1
0x1bf23  call     instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::GetOutputsInfo(valuetype [mscorlib]System.Guid pluginType)
0x1bf28  callvirt instance void [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::set_Outputs(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[])
0x1bf2d  ldloc.3
0x1bf2e  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_Inputs()
0x1bf33  stloc.s  7
0x1bf35  ldloc.s  7
0x1bf37  ldarg.0
0x1bf38  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Cache()
0x1bf3d  ldarg.0
0x1bf3e  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_OrganizationId()
0x1bf43  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::SetDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase[] parameters, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache, valuetype [mscorlib]System.Guid organizationId)
0x1bf48  ldloc.3
0x1bf49  callvirt instance class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomActivityParameterInfo[] [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.SandboxCustomActivityInfo::get_Outputs()
0x1bf4e  stloc.s  7
0x1bf50  ldloc.s  7
0x1bf52  ldarg.0
0x1bf53  call     instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_Cache()
0x1bf58  ldarg.0
0x1bf59  callvirt instance valuetype [mscorlib]System.Guid Microsoft.Crm.Workflow.ObjectModel.CustomActivityInfoMetadataBase::get_OrganizationId()
0x1bf5e  call     void Microsoft.Crm.Workflow.ObjectModel.CustomActivityHelper::SetDefaultValue(class [Microsoft.Crm]Microsoft.Crm.Workflow.ObjectModel.CustomParameterInfoBase[] parameters, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache metadataCache, valuetype [mscorlib]System.Guid organizationId)
0x1bf63  ldloc.3
0x1bf64  ret
```
