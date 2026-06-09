# Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::ReassignWorkflows

- ea: `0x4790`
- end: `0x4b6c`
- name: `Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::ReassignWorkflows`
- size: `988`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x4720`

## callees

- `0x46f0`
- `0x4790`
- `0x4bc0`
- `0x4c10`
- `0x4c30`
- `0x4c90`
- `0x4ce0`
- `0x4d30`
- `0x4d50`
- `0x64b0`
- `0x9480`
- `0x23fd0`
- `0x30210`

## string_xrefs

- `0x4797`: `blank_1@crmdemo.dynamics.com`
- `0x486f`: `Will attempt workflow re-assign`
- `0x48f6`: `Considering workflow : `

## pseudocode

```c

```

## disassembly

```asm
0x4790  newobj   instance void <>c__DisplayClass9_0::.ctor()
0x4795  stloc.0
0x4796  ldloc.0
0x4797  ldstr    aBlank1CrmdemoD// "blank_1@crmdemo.dynamics.com"
0x479c  stfld    string <>c__DisplayClass9_0::blankProvisioningUserName
0x47a1  ldloc.0
0x47a2  ldarg.0
0x47a3  call     instance class Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgAction::get_OrganizationProperties()
0x47a8  callvirt instance class Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal Microsoft.Crm.CrmLive.Provisioning.ProvisionOrgProperties::get_OriginalCreateInfo()
0x47ad  callvirt instance string Microsoft.Crm.CrmLive.Provisioning.OrganizationCreateInfoLocal::get_InitialUserLiveId()
0x47b2  stfld    string <>c__DisplayClass9_0::actualUserName
0x47b7  ldarg.0
0x47b8  ldstr    aBlankprovision// "blankProvisioningUserName : "
0x47bd  ldloc.0
0x47be  ldfld    string <>c__DisplayClass9_0::blankProvisioningUserName
0x47c3  call     string [mscorlib]System.String::Concat(string, string)
0x47c8  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x47cd  ldarg.0
0x47ce  ldstr    aActualusername// "actualUserName : "
0x47d3  ldloc.0
0x47d4  ldfld    string <>c__DisplayClass9_0::actualUserName
0x47d9  call     string [mscorlib]System.String::Concat(string, string)
0x47de  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x47e3  ldstr    aSystemuser_0// "systemuser"
0x47e8  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x47ed  stloc.1
0x47ee  ldloc.1
0x47ef  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x47f4  ldc.i4.2
0x47f5  newarr   [mscorlib]System.String
0x47fa  dup
0x47fb  ldc.i4.0
0x47fc  ldstr    aDomainname_0// "domainname"
0x4801  stelem.ref
0x4802  dup
0x4803  ldc.i4.1
0x4804  ldstr    aIsdisabled// "isdisabled"
0x4809  stelem.ref
0x480a  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x480f  ldarg.1
0x4810  ldloc.1
0x4811  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x4816  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x481b  dup
0x481c  ldloc.0
0x481d  ldftn    instance bool <>c__DisplayClass9_0::<ReassignWorkflows>b__0(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity x)
0x4823  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x4828  call     T0x2B00001B
0x482d  stloc.2
0x482e  ldloc.0
0x482f  ldftn    instance bool <>c__DisplayClass9_0::<ReassignWorkflows>b__1(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity x)
0x4835  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity, bool>::.ctor(object, native int)
0x483a  call     T0x2B00001B
0x483f  stloc.3
0x4840  ldarg.0
0x4841  ldstr    aBlankprovision_0// "blankProvisioningUser : "
0x4846  ldloc.2
0x4847  call     string [mscorlib]System.String::Concat(object, object)
0x484c  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x4851  ldarg.0
0x4852  ldstr    aActualuser// "actualUser : "
0x4857  ldloc.3
0x4858  call     string [mscorlib]System.String::Concat(object, object)
0x485d  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x4862  ldloc.3
0x4863  brfalse  loc_4B6B
0x4868  ldloc.2
0x4869  brfalse  loc_4B6B
0x486e  ldarg.0
0x486f  ldstr    aWillAttemptWor// "Will attempt workflow re-assign"
0x4874  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x4879  ldstr    aWorkflow// "workflow"
0x487e  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::.ctor(string)
0x4883  stloc.s  4
0x4885  ldloc.s  4
0x4887  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryExpression::get_ColumnSet()
0x488c  ldc.i4.4
0x488d  newarr   [mscorlib]System.String
0x4892  dup
0x4893  ldc.i4.0
0x4894  ldstr    aName_0// "name"
0x4899  stelem.ref
0x489a  dup
0x489b  ldc.i4.1
0x489c  ldstr    aOwnerid// "ownerid"
0x48a1  stelem.ref
0x48a2  dup
0x48a3  ldc.i4.2
0x48a4  ldstr    aStatuscode// "statuscode"
0x48a9  stelem.ref
0x48aa  dup
0x48ab  ldc.i4.3
0x48ac  ldstr    aStatecode// "statecode"
0x48b1  stelem.ref
0x48b2  callvirt instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::AddColumns(string[])
0x48b7  ldarg.1
0x48b8  ldloc.s  4
0x48ba  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::RetrieveMultiple(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.QueryBase)
0x48bf  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity> [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityCollection::get_Entities()
0x48c4  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.Collection`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::GetEnumerator()
0x48c9  stloc.s  5
0x48cb  br       loc_4B51
0x48d0  ldloc.s  5
0x48d2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity>::get_Current()
0x48d7  stloc.s  6
0x48d9  ldloc.s  6
0x48db  ldstr    aOwnerid// "ownerid"
0x48e0  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x48e5  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x48ea  stloc.s  7
0x48ec  ldarg.0
0x48ed  ldc.i4.s 0xA
0x48ef  newarr   [mscorlib]System.Object
0x48f4  dup
0x48f5  ldc.i4.0
0x48f6  ldstr    aConsideringWor// "Considering workflow : "
0x48fb  stelem.ref
0x48fc  dup
0x48fd  ldc.i4.1
0x48fe  ldloc.s  6
0x4900  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x4905  ldstr    aName_0// "name"
0x490a  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x490f  stelem.ref
0x4910  dup
0x4911  ldc.i4.2
0x4912  ldstr    asc_37436// " , "
0x4917  stelem.ref
0x4918  dup
0x4919  ldc.i4.3
0x491a  ldloc.s  6
0x491c  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4921  box      [mscorlib]System.Guid
0x4926  stelem.ref
0x4927  dup
0x4928  ldc.i4.4
0x4929  ldstr    asc_37436// " , "
0x492e  stelem.ref
0x492f  dup
0x4930  ldc.i4.5
0x4931  ldloc.s  7
0x4933  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x4938  box      [mscorlib]System.Guid
0x493d  stelem.ref
0x493e  dup
0x493f  ldc.i4.6
0x4940  ldstr    asc_37436// " , "
0x4945  stelem.ref
0x4946  dup
0x4947  ldc.i4.7
0x4948  ldloc.s  6
0x494a  ldstr    aStatecode// "statecode"
0x494f  callvirt T0x2B00001C
0x4954  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x4959  box      [mscorlib]System.Int32
0x495e  stelem.ref
0x495f  dup
0x4960  ldc.i4.8
0x4961  ldstr    asc_37436// " , "
0x4966  stelem.ref
0x4967  dup
0x4968  ldc.i4.s 9
0x496a  ldloc.s  6
0x496c  ldstr    aStatuscode// "statuscode"
0x4971  callvirt T0x2B00001C
0x4976  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x497b  box      [mscorlib]System.Int32
0x4980  stelem.ref
0x4981  call     string [mscorlib]System.String::Concat(object[])
0x4986  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x498b  ldloc.s  7
0x498d  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x4992  ldloc.2
0x4993  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4998  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x499d  brfalse  loc_4B51
0x49a2  ldarg.0
0x49a3  ldstr    aReassigningWor// "Reassigning workflow!"
0x49a8  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x49ad  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.AssignRequest::.ctor()
0x49b2  dup
0x49b3  ldstr    aSystemuser_0// "systemuser"
0x49b8  ldloc.3
0x49b9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x49be  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x49c3  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.AssignRequest::set_Assignee(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x49c8  dup
0x49c9  ldstr    aWorkflow// "workflow"
0x49ce  ldloc.s  6
0x49d0  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x49d5  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x49da  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.AssignRequest::set_Target(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x49df  stloc.s  0xA
0x49e1  ldarg.1
0x49e2  ldloc.s  0xA
0x49e4  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x49e9  pop
0x49ea  ldloc.s  6
0x49ec  ldstr    aStatuscode// "statuscode"
0x49f1  callvirt T0x2B00001C
0x49f6  callvirt instance int32 [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::get_Value()
0x49fb  ldc.i4.2
0x49fc  bne.un.s loc_4A48
0x49fe  ldarg.0
0x49ff  ldstr    aRepublishingWo// "Republishing workflow!"
0x4a04  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x4a09  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.SetStateRequest::.ctor()
0x4a0e  dup
0x4a0f  ldstr    aWorkflow// "workflow"
0x4a14  ldloc.s  6
0x4a16  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4a1b  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::.ctor(string, valuetype [mscorlib]System.Guid)
0x4a20  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SetStateRequest::set_EntityMoniker(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference value)
0x4a25  dup
0x4a26  ldc.i4.1
0x4a27  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x4a2c  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SetStateRequest::set_State(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue value)
0x4a31  dup
0x4a32  ldc.i4.2
0x4a33  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue::.ctor(int32)
0x4a38  callvirt instance void Microsoft.Crm.CrmLive.Provisioning.SetStateRequest::set_Status(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OptionSetValue value)
0x4a3d  stloc.s  0xB
0x4a3f  ldarg.1
0x4a40  ldloc.s  0xB
0x4a42  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationResponse [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Execute(class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.OrganizationRequest)
0x4a47  pop
0x4a48  leave.s  loc_4A60
0x4a4a  stloc.s  0xC
0x4a4c  ldarg.0
0x4a4d  ldstr    aReassignOrRepu// "Reassign or republish failed with error"...
0x4a52  ldloc.s  0xC
0x4a54  call     string [mscorlib]System.String::Concat(object, object)
0x4a59  call     instance void Microsoft.Crm.CrmLive.Provisioning.DisableDemoUsersAction::Log(string text)
0x4a5e  leave.s  loc_4A60
0x4a60  ldarg.1
0x4a61  ldstr    aWorkflow// "workflow"
0x4a66  ldloc.s  6
0x4a68  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4a6d  ldc.i4.4
0x4a6e  newarr   [mscorlib]System.String
0x4a73  dup
0x4a74  ldc.i4.0
0x4a75  ldstr    aName_0// "name"
0x4a7a  stelem.ref
0x4a7b  dup
0x4a7c  ldc.i4.1
0x4a7d  ldstr    aOwnerid// "ownerid"
0x4a82  stelem.ref
0x4a83  dup
0x4a84  ldc.i4.2
0x4a85  ldstr    aStatuscode// "statuscode"
0x4a8a  stelem.ref
0x4a8b  dup
0x4a8c  ldc.i4.3
0x4a8d  ldstr    aStatecode// "statecode"
0x4a92  stelem.ref
0x4a93  newobj   instance void [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet::.ctor(string[])
0x4a98  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Client.OrganizationServiceProxy::Retrieve(string, valuetype [mscorlib]System.Guid, class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Query.ColumnSet)
0x4a9d  stloc.s  8
0x4a9f  ldloc.s  8
0x4aa1  ldstr    aOwnerid// "ownerid"
0x4aa6  callvirt instance object [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Item(string)
0x4aab  castclass [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference
0x4ab0  stloc.s  9
0x4ab2  ldarg.0
0x4ab3  ldc.i4.s 0xA
0x4ab5  newarr   [mscorlib]System.Object
0x4aba  dup
0x4abb  ldc.i4.0
0x4abc  ldstr    aNewWorkflowSta// "New workflow state : "
0x4ac1  stelem.ref
0x4ac2  dup
0x4ac3  ldc.i4.1
0x4ac4  ldloc.s  8
0x4ac6  callvirt instance class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.AttributeCollection [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Attributes()
0x4acb  ldstr    aName_0// "name"
0x4ad0  callvirt instance var<u1> class [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.DataCollection`2<string, object>::get_Item(void)
0x4ad5  stelem.ref
0x4ad6  dup
0x4ad7  ldc.i4.2
0x4ad8  ldstr    asc_37436// " , "
0x4add  stelem.ref
0x4ade  dup
0x4adf  ldc.i4.3
0x4ae0  ldloc.s  8
0x4ae2  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.Entity::get_Id()
0x4ae7  box      [mscorlib]System.Guid
0x4aec  stelem.ref
0x4aed  dup
0x4aee  ldc.i4.4
0x4aef  ldstr    asc_37436// " , "
0x4af4  stelem.ref
0x4af5  dup
0x4af6  ldc.i4.5
0x4af7  ldloc.s  9
0x4af9  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Xrm.Sdk]Microsoft.Xrm.Sdk.EntityReference::get_Id()
0x4afe  box      [mscorlib]System.Guid
0x4b03  stelem.ref
0x4b04  dup
0x4b05  ldc.i4.6
  ... truncated ...
```
