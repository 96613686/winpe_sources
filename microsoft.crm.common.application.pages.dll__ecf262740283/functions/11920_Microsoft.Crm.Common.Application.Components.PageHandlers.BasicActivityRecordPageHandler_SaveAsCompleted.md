# Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::SaveAsCompleted

- ea: `0x11920`
- end: `0x11af2`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::SaveAsCompleted`
- size: `466`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x11510`
- `0x11920`

## string_xrefs

- `0x11975`: `serviceappointment`
- `0x11a58`: `serviceappointment`

## pseudocode

```c

```

## disassembly

```asm
0x11920  ldarg.2
0x11921  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x11926  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_HasData()
0x1192b  brfalse  loc_11A36
0x11930  ldarg.2
0x11931  callvirt instance valuetype [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.FormState [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_State()
0x11936  ldarg.2
0x11937  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x1193c  callvirt instance bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_IsNew()
0x11941  brtrue.s loc_11946
0x11943  ldc.i4.2
0x11944  br.s     loc_11947
0x11946  ldc.i4.1
0x11947  ceq
0x11949  ldstr    aFormStateDoesN// "Form state does not match the state in "...
0x1194e  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x11953  ldarg.0
0x11954  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11959  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x1195e  ldstr    aAppointment// "appointment"
0x11963  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11968  brtrue.s loc_11984
0x1196a  ldarg.0
0x1196b  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11970  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x11975  ldstr    aServiceappoint// "serviceappointment"
0x1197a  call     bool [mscorlib]System.String::op_Equality(string, string)
0x1197f  brfalse  loc_11A22
0x11984  ldarg.0
0x11985  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x1198a  ldstr    aStatuscode// "statuscode"
0x1198f  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x11994  stloc.0
0x11995  ldloc.0
0x11996  brfalse  loc_11A22
0x1199b  ldloc.0
0x1199c  unbox.any [mscorlib]System.Int32
0x119a1  ldc.i4.m1
0x119a2  beq.s    loc_11A22
0x119a4  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x119a9  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x119ae  ldarg.0
0x119af  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x119b4  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x119b9  ldc.i4.1
0x119ba  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::GetEntity(string, valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.NameMappingType)
0x119bf  ldstr    aStatuscode// "statuscode"
0x119c4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::GetAttribute(string)
0x119c9  isinst   [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata
0x119ce  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IStatusOptionsByValueCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusAttributeMetadata::get_StatusOptions()
0x119d3  ldloc.0
0x119d4  unbox.any [mscorlib]System.Int32
0x119d9  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEnumOptionsByValueCollection`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption>::get_Item(!!T0)
0x119de  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.StatusOption::get_State()
0x119e3  stloc.1
0x119e4  ldarg.0
0x119e5  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x119ea  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x119ef  ldloc.1
0x119f0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::ConvertStateCodeToString(string, int32)
0x119f5  ldarg.2
0x119f6  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x119fb  ldstr    aStatecode// "statecode"
0x11a00  callvirt instance object [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Item(string)
0x11a05  isinst   [mscorlib]System.String
0x11a0a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x11a0f  brfalse.s loc_11A22
0x11a11  ldarg.2
0x11a12  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs::get_Entity()
0x11a17  ldstr    aStatuscode// "statuscode"
0x11a1c  ldnull
0x11a1d  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::set_Item(string, object)
0x11a22  ldarg.0
0x11a23  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x11a28  ldarg.0
0x11a29  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11a2e  callvirt instance bool [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::SaveEntity(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy)
0x11a33  brtrue.s loc_11A36
0x11a35  ret
0x11a36  ldarg.0
0x11a37  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11a3c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x11a41  ldstr    aCampaignrespon// "campaignresponse"
0x11a46  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11a4b  brtrue.s loc_11A64
0x11a4d  ldarg.0
0x11a4e  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11a53  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x11a58  ldstr    aServiceappoint// "serviceappointment"
0x11a5d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11a62  brfalse.s loc_11A9B
0x11a64  ldarg.0
0x11a65  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11a6a  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x11a6f  ldarg.0
0x11a70  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11a75  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x11a7a  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x11a7f  ldc.i4.1
0x11a80  stloc.2
0x11a81  ldloca.s 2
0x11a83  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.CampaignResponseState
0x11a89  callvirt instance string [mscorlib]System.Object::ToString()
0x11a8e  ldc.i4.m1
0x11a8f  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11a94  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState(string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11a99  br.s     loc_11AD0
0x11a9b  ldarg.0
0x11a9c  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11aa1  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::get_EntityName()
0x11aa6  ldarg.0
0x11aa7  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11aac  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_Id()
0x11ab1  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x11ab6  ldc.i4.1
0x11ab7  stloc.3
0x11ab8  ldloca.s 3
0x11aba  constrained. [Microsoft.Crm.Sdk.Reserved]Microsoft.Crm.Sdk.Types.ActivityPointerState
0x11ac0  callvirt instance string [mscorlib]System.Object::ToString()
0x11ac5  ldc.i4.m1
0x11ac6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x11acb  call     void [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase::SetState(string, valuetype [mscorlib]System.Guid, string, int32, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x11ad0  ldarg.0
0x11ad1  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11ad6  callvirt instance void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityProxy::Retrieve()
0x11adb  ldarg.0
0x11adc  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x11ae1  ldarg.0
0x11ae2  call     instance class [Microsoft.Crm.Common.Application.Platform]Microsoft.Crm.Common.Application.Platform.ActivityBase Microsoft.Crm.Common.Application.Components.PageHandlers.BasicActivityRecordPageHandler::get_CurrentActivity()
0x11ae7  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityBase::get_EntityType()
0x11aec  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RenderCloseWindow(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType)
0x11af1  ret
```
