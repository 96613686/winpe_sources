# Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateUserMetadataFromDataBase

- ea: `0x7000`
- end: `0x719f`
- name: `Microsoft.Crm.Asynchronous.ImportFileHelperData::PopulateUserMetadataFromDataBase`
- size: `415`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x6e60`
- `0x7f70`

## callees

- `0x5d80`
- `0x5da0`
- `0x5dc0`
- `0x5dd0`
- `0x7000`

## string_xrefs

- `0x700f`: `sourceuseridentifierforsourcecrmuserlink`
- `0x70f0`: `sourceuseridentifierforsourcecrmuserlink`
- `0x7100`: `sourceuseridentifierforsourcecrmuserlink`
- `0x716f`: `sourceuseridentifierforsourcecrmuserlink`
- `0x7017`: `sourceuseridentifierforsourcedatasourceuserlink`
- `0x711f`: `sourceuseridentifierforsourcedatasourceuserlink`
- `0x712c`: `sourceuseridentifierforsourcedatasourceuserlink`
- `0x718a`: `sourceuseridentifierforsourcedatasourceuserlink`
- `0x701f`: `targetuseridentifierforsourcecrmuserlink`
- `0x70c1`: `targetuseridentifierforsourcecrmuserlink`
- `0x70d1`: `targetuseridentifierforsourcecrmuserlink`
- `0x7154`: `targetuseridentifierforsourcecrmuserlink`

## pseudocode

```c

```

## disassembly

```asm
0x7000  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::.ctor()
0x7005  stloc.0
0x7006  ldloc.0
0x7007  ldc.i4.3
0x7008  newarr   [mscorlib]System.String
0x700d  dup
0x700e  ldc.i4.0
0x700f  ldstr    aSourceuseriden// "sourceuseridentifierforsourcecrmuserlin"...
0x7014  stelem.ref
0x7015  dup
0x7016  ldc.i4.1
0x7017  ldstr    aSourceuseriden_0// "sourceuseridentifierforsourcedatasource"...
0x701c  stelem.ref
0x701d  dup
0x701e  ldc.i4.2
0x701f  ldstr    aTargetuseriden// "targetuseridentifierforsourcecrmuserlin"...
0x7024  stelem.ref
0x7025  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x702a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_ColumnSet(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x702f  ldloc.0
0x7030  ldstr    aImportmap// "importmap"
0x7035  ldarg.0
0x7036  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity Microsoft.Crm.Asynchronous.ImportFileHelperData::_importFile
0x703b  ldstr    aImportmapid// "importmapid"
0x7040  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7045  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x704a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x704f  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x7054  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference)
0x7059  ldnull
0x705a  stloc.1
0x705b  ldarg.0
0x705c  ldfld    class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService Microsoft.Crm.Asynchronous.ImportFileHelperData::_crmService
0x7061  ldloc.0
0x7062  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.IOrganizationService::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x7067  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse
0x706c  stloc.1
0x706d  leave.s  loc_70AE
0x706f  stloc.2
0x7070  ldloc.2
0x7071  ldarg.0
0x7072  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportFileHelperData::_organizationId
0x7077  ldc.i4.s 0x18
0x7079  ldstr    aErrorWhileRetr// "Error while retrieving user metadata"
0x707e  ldc.i4.1
0x707f  newarr   [mscorlib]System.Object
0x7084  dup
0x7085  ldc.i4.0
0x7086  ldloc.2
0x7087  call     string [Microsoft.Crm.Core]Microsoft.Crm.CrmException::ExceptionToString(class [mscorlib]System.Exception)
0x708c  stelem.ref
0x708d  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x7092  leave.s  loc_70AE
0x7094  ldarg.0
0x7095  ldfld    valuetype [mscorlib]System.Guid Microsoft.Crm.Asynchronous.ImportFileHelperData::_organizationId
0x709a  ldc.i4.s 0x18
0x709c  ldstr    aErrorWhileRetr// "Error while retrieving user metadata"
0x70a1  ldc.i4.0
0x70a2  newarr   [mscorlib]System.Object
0x70a7  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x70ac  leave.s  loc_70AE
0x70ae  ldloc.1
0x70af  brfalse  loc_719E
0x70b4  ldloc.1
0x70b5  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Messages.RetrieveResponse::get_Entity()
0x70ba  stloc.3
0x70bb  ldloc.3
0x70bc  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x70c1  ldstr    aTargetuseriden// "targetuseridentifierforsourcecrmuserlin"...
0x70c6  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x70cb  brfalse  loc_719E
0x70d0  ldloc.3
0x70d1  ldstr    aTargetuseriden// "targetuseridentifierforsourcecrmuserlin"...
0x70d6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x70db  castclass [mscorlib]System.String
0x70e0  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x70e5  brtrue   loc_719E
0x70ea  ldloc.3
0x70eb  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x70f0  ldstr    aSourceuseriden// "sourceuseridentifierforsourcecrmuserlin"...
0x70f5  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x70fa  brfalse  loc_719E
0x70ff  ldloc.3
0x7100  ldstr    aSourceuseriden// "sourceuseridentifierforsourcecrmuserlin"...
0x7105  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x710a  castclass [mscorlib]System.String
0x710f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7114  brtrue   loc_719E
0x7119  ldloc.3
0x711a  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x711f  ldstr    aSourceuseriden_0// "sourceuseridentifierforsourcedatasource"...
0x7124  callvirt instance bool class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::Contains(var<u1>)
0x7129  brfalse.s loc_719E
0x712b  ldloc.3
0x712c  ldstr    aSourceuseriden_0// "sourceuseridentifierforsourcedatasource"...
0x7131  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7136  castclass [mscorlib]System.String
0x713b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x7140  brtrue.s loc_719E
0x7142  ldarg.0
0x7143  newobj   instance void Microsoft.Crm.Asynchronous.UserMetadataInfo::.ctor()
0x7148  stfld    class Microsoft.Crm.Asynchronous.UserMetadataInfo Microsoft.Crm.Asynchronous.ImportFileHelperData::_userMetadataInMap
0x714d  ldarg.0
0x714e  ldfld    class Microsoft.Crm.Asynchronous.UserMetadataInfo Microsoft.Crm.Asynchronous.ImportFileHelperData::_userMetadataInMap
0x7153  ldloc.3
0x7154  ldstr    aTargetuseriden// "targetuseridentifierforsourcecrmuserlin"...
0x7159  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x715e  castclass [mscorlib]System.String
0x7163  callvirt instance void Microsoft.Crm.Asynchronous.UserMetadataInfo::set_CrmSystemUserColumn(string value)
0x7168  ldarg.0
0x7169  ldfld    class Microsoft.Crm.Asynchronous.UserMetadataInfo Microsoft.Crm.Asynchronous.ImportFileHelperData::_userMetadataInMap
0x716e  ldloc.3
0x716f  ldstr    aSourceuseriden// "sourceuseridentifierforsourcecrmuserlin"...
0x7174  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7179  castclass [mscorlib]System.String
0x717e  callvirt instance void Microsoft.Crm.Asynchronous.UserMetadataInfo::set_SourceUsersColumnForCrmSystemUser(string value)
0x7183  ldarg.0
0x7184  ldfld    class Microsoft.Crm.Asynchronous.UserMetadataInfo Microsoft.Crm.Asynchronous.ImportFileHelperData::_userMetadataInMap
0x7189  ldloc.3
0x718a  ldstr    aSourceuseriden_0// "sourceuseridentifierforsourcedatasource"...
0x718f  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x7194  castclass [mscorlib]System.String
0x7199  callvirt instance void Microsoft.Crm.Asynchronous.UserMetadataInfo::set_SourceUsersColumnForSourceData(string value)
0x719e  ret
```
