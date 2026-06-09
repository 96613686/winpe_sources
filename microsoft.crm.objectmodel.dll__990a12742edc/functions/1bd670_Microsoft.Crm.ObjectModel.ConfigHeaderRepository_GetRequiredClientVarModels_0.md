# Microsoft.Crm.ObjectModel.ConfigHeaderRepository::GetRequiredClientVarModels_0

- ea: `0x1bd670`
- end: `0x1becb4`
- name: `Microsoft.Crm.ObjectModel.ConfigHeaderRepository::GetRequiredClientVarModels_0`
- size: `5700`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1bd600`
- `0x1bd660`

## callees

- `0x1bd670`
- `0x1becc0`
- `0x1bed60`

## string_xrefs

- `0x1bd7d5`: `skipInitialXMLValue`
- `0x1bdadb`: `serviceactivity_edit_aspx_genericservererror`
- `0x1bdc9b`: `serviceactivity_edit_aspx_genericservererror`
- `0x1bddde`: `serviceactivity_edit_aspx_genericservererror`
- `0x1bdfe5`: `LOCID_WRITEIN_PRODUCT_TOOLTIP`
- `0x1be9ef`: `LOCID_WRITEIN_PRODUCT_TOOLTIP`
- `0x1bdff0`: `InlineEditGrid.ProductTaxonomy.Write-inProductToolTip`
- `0x1be9fa`: `InlineEditGrid.ProductTaxonomy.Write-inProductToolTip`
- `0x1be224`: `LOCID_DELETEBUTTON_TOOLTIP`
- `0x1be72e`: `LOCID_DELETEBUTTON_TOOLTIP`
- `0x1bea67`: `LOCID_DELETEBUTTON_TOOLTIP`
- `0x1beb83`: `LOCID_DELETEBUTTON_TOOLTIP`
- `0x1be22f`: `ToolTip_GridDeleteAction`
- `0x1be739`: `ToolTip_GridDeleteAction`
- `0x1bea72`: `ToolTip_GridDeleteAction`
- `0x1beb8e`: `ToolTip_GridDeleteAction`
- `0x1be252`: `LOCID_NO_READ_ON_PRICELIST`
- `0x1be25d`: `Web.SFA.pricelevel.noread.aspx_155`
- `0x1be27f`: `LOCID_ERR_NO_CREATE_FOR_SOCIAL`
- `0x1be2ac`: `TEAM_ACCESS_NO_APPLY_WITH_ROLES`
- `0x1be2b7`: `AccessTypeCannotBeSetForTeamWithRolesErrorMessage`
- `0x1beb59`: `LOCID_HELPLINK_TEXT`
- `0x1beb64`: `Web.ConvertRule.Propertybag.HelpLink.Text`

## pseudocode

```c

```

## disassembly

```asm
0x1bd670  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::.ctor()
0x1bd675  stloc.0
0x1bd676  ldc.i4.0
0x1bd677  stloc.1
0x1bd678  ldarg.0
0x1bd679  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_CanBeSecured()
0x1bd67e  brfalse.s loc_1BD6F3
0x1bd680  ldarg.0
0x1bd681  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IAttributeMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_AttributesByName()
0x1bd686  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Values()
0x1bd68b  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x1bd690  stloc.2
0x1bd691  br.s     loc_1BD6D8
0x1bd693  ldloc.2
0x1bd694  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x1bd699  castclass [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata
0x1bd69e  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_IsSecured()
0x1bd6a3  brfalse.s loc_1BD6D8
0x1bd6a5  ldc.i4.1
0x1bd6a6  stloc.1
0x1bd6a7  ldloc.0
0x1bd6a8  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd6ad  dup
0x1bd6ae  ldstr    aHasSecuredFiel// "HAS_SECURED_FIELDS"
0x1bd6b3  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd6b8  dup
0x1bd6b9  ldloca.s 1
0x1bd6bb  call     instance string [mscorlib]System.Boolean::ToString()
0x1bd6c0  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1bd6c5  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd6ca  dup
0x1bd6cb  ldc.i4.1
0x1bd6cc  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd6d1  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd6d6  leave.s  loc_1BD6F3
0x1bd6d8  ldloc.2
0x1bd6d9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1bd6de  brtrue.s loc_1BD693
0x1bd6e0  leave.s  loc_1BD6F3
0x1bd6e2  ldloc.2
0x1bd6e3  isinst   [mscorlib]System.IDisposable
0x1bd6e8  stloc.3
0x1bd6e9  ldloc.3
0x1bd6ea  brfalse.s loc_1BD6F2
0x1bd6ec  ldloc.3
0x1bd6ed  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1bd6f2  endfinally
0x1bd6f3  ldloc.0
0x1bd6f4  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd6f9  dup
0x1bd6fa  ldstr    aLocidActionNoi// "LOCID_ACTION_NOITEMSELECTED"
0x1bd6ff  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd704  dup
0x1bd705  ldstr    aErrorMessageAc// "Error_Message_Action_NoItemSelected"
0x1bd70a  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd70f  dup
0x1bd710  ldc.i4.2
0x1bd711  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd716  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd71b  ldloc.0
0x1bd71c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd721  dup
0x1bd722  ldstr    aLocidMaxRecord// "LOCID_MAX_RECORDS_ERROR"
0x1bd727  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd72c  dup
0x1bd72d  ldstr    aErrorMaxShortc// "Error_Max_Shortcut_Record_Reached"
0x1bd732  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd737  dup
0x1bd738  ldc.i4.2
0x1bd739  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd73e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd743  ldloc.0
0x1bd744  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd749  dup
0x1bd74a  ldstr    aFormSectionNoT// "Form_Section_No_Tabs"
0x1bd74f  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd754  dup
0x1bd755  ldstr    aFormsections// "FormSections"
0x1bd75a  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd75f  dup
0x1bd760  ldc.i4.2
0x1bd761  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd766  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd76b  ldarg.0
0x1bd76c  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsCollaboration()
0x1bd771  brfalse.s loc_1BD7C3
0x1bd773  ldloc.0
0x1bd774  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd779  dup
0x1bd77a  ldstr    aRecordAddedToN// "RECORD_ADDED_TO_NO_QUEUE"
0x1bd77f  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd784  dup
0x1bd785  ldstr    aMessageViewque// "Message_ViewQueueItem_NoQueue"
0x1bd78a  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd78f  dup
0x1bd790  ldc.i4.2
0x1bd791  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd796  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd79b  ldloc.0
0x1bd79c  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd7a1  dup
0x1bd7a2  ldstr    aRecordAddedToM// "RECORD_ADDED_TO_MULTIPLE_QUEUES"
0x1bd7a7  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd7ac  dup
0x1bd7ad  ldstr    aMessageViewque_0// "Message_ViewQueueItem_InMultipleQueues"
0x1bd7b2  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd7b7  dup
0x1bd7b8  ldc.i4.2
0x1bd7b9  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd7be  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd7c3  ldarg.0
0x1bd7c4  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsActivity()
0x1bd7c9  brfalse  loc_1BD956
0x1bd7ce  ldloc.0
0x1bd7cf  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd7d4  dup
0x1bd7d5  ldstr    aSkipinitialxml// "skipInitialXMLValue"
0x1bd7da  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd7df  dup
0x1bd7e0  ldc.i4.1
0x1bd7e1  stloc.s  6
0x1bd7e3  ldloca.s 6
0x1bd7e5  call     instance string [mscorlib]System.Boolean::ToString()
0x1bd7ea  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1bd7ef  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd7f4  dup
0x1bd7f5  ldc.i4.1
0x1bd7f6  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd7fb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd800  ldloc.0
0x1bd801  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd806  dup
0x1bd807  ldstr    aIsSchedulableA// "IS_SCHEDULABLE_ACTIVITY"
0x1bd80c  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd811  dup
0x1bd812  ldc.i4.0
0x1bd813  stloc.s  6
0x1bd815  ldloca.s 6
0x1bd817  call     instance string [mscorlib]System.Boolean::ToString()
0x1bd81c  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1bd821  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd826  dup
0x1bd827  ldc.i4.1
0x1bd828  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd82d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd832  ldloc.0
0x1bd833  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd838  dup
0x1bd839  ldstr    aLocidActivityC// "LOCID_ACTIVITY_CLOSED_WARNING"
0x1bd83e  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd843  dup
0x1bd844  ldstr    aActivityclosed// "ActivityClosedSaveWarning"
0x1bd849  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd84e  dup
0x1bd84f  ldc.i4.2
0x1bd850  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd855  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd85a  ldloc.0
0x1bd85b  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd860  dup
0x1bd861  ldstr    aLocidConvActSa// "LOCID_CONV_ACT_SAVE_WARNING"
0x1bd866  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd86b  dup
0x1bd86c  ldstr    aConvactsavewar// "ConvActSaveWarning"
0x1bd871  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd876  dup
0x1bd877  ldc.i4.2
0x1bd878  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd87d  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd882  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1bd887  stloc.s  4
0x1bd889  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1bd88e  stloc.s  5
0x1bd890  call     bool [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_IsAvailable()
0x1bd895  brfalse.s loc_1BD8B9
0x1bd897  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x1bd89c  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x1bd8a1  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetUserId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x1bd8a6  stloc.s  4
0x1bd8a8  call     class [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Current()
0x1bd8ad  callvirt instance class [mscorlib]System.Security.Claims.ClaimsPrincipal [Microsoft.Crm.Authentication]Microsoft.Crm.Authentication.UserIdentityContext::get_Principal()
0x1bd8b2  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]IdentityExtensions::GetOrganizationId(class [mscorlib]System.Security.Claims.ClaimsPrincipal)
0x1bd8b7  stloc.s  5
0x1bd8b9  ldloc.s  4
0x1bd8bb  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1bd8c0  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1bd8c5  brfalse  loc_1BD956
0x1bd8ca  ldloc.s  5
0x1bd8cc  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1bd8d1  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x1bd8d6  brfalse.s loc_1BD956
0x1bd8d8  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.UserDataCache::Instance()
0x1bd8dd  ldloc.s  4
0x1bd8df  ldloc.s  5
0x1bd8e1  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x1bd8e6  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.CrmMultiOrgCacheBase`2<valuetype [mscorlib]System.Guid, class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser>::LookupEntry(void, var<u1>)
0x1bd8eb  callvirt instance class [mscorlib]System.TimeZone [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Caching.IUser::get_TimeZone()
0x1bd8f0  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1bd8f5  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.TimeZone::ToLocalTime(valuetype [mscorlib]System.DateTime)
0x1bd8fa  stloc.s  8
0x1bd8fc  ldloca.s 8
0x1bd8fe  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1bd903  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1bd908  stloc.s  8
0x1bd90a  ldloca.s 8
0x1bd90c  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x1bd911  sub
0x1bd912  newobj   instance void [mscorlib]System.TimeSpan::.ctor(int64)
0x1bd917  stloc.s  9
0x1bd919  ldloca.s 9
0x1bd91b  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMinutes()
0x1bd920  stloc.s  7
0x1bd922  ldloc.0
0x1bd923  newobj   instance void [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::.ctor()
0x1bd928  dup
0x1bd929  ldstr    aOrgTimezoneOff// "ORG_TIMEZONE_OFFSET_STRING"
0x1bd92e  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceName
0x1bd933  dup
0x1bd934  ldloca.s 7
0x1bd936  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1bd93b  call     instance string [mscorlib]System.Double::ToString(class [mscorlib]System.IFormatProvider)
0x1bd940  callvirt instance string [mscorlib]System.String::ToLowerInvariant()
0x1bd945  stfld    string [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::ResourceValue
0x1bd94a  dup
0x1bd94b  ldc.i4.1
0x1bd94c  stfld    valuetype [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringType [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel::Type
0x1bd951  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel>::Add(var<u1>)
0x1bd956  ldarg.0
0x1bd957  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x1bd95c  stloc.s  0xA
0x1bd95e  ldloc.s  0xA
0x1bd960  ldc.i4   0x443
0x1bd965  bgt      loc_1BDA1C
0x1bd96a  ldloc.s  0xA
0x1bd96c  ldc.i4.s 0x70
0x1bd96e  bgt.s    loc_1BD9B4
0x1bd970  ldloc.s  0xA
0x1bd972  ldc.i4.1
0x1bd973  sub
0x1bd974  switch   loc_1BEBA4, loc_1BEBA4, loc_1BDF16, loc_1BEBA4, loc_1BEBA4, loc_1BEBA4, loc_1BEBA4, loc_1BEBA4, loc_1BE2A5
0x1bd99d  ldloc.s  0xA
0x1bd99f  ldc.i4.s 0x63
0x1bd9a1  beq      loc_1BE278
0x1bd9a6  ldloc.s  0xA
0x1bd9a8  ldc.i4.s 0x70
0x1bd9aa  beq      loc_1BDE49
0x1bd9af  br       loc_1BEBA4
0x1bd9b4  ldloc.s  0xA
0x1bd9b6  ldc.i4   0x401
0x1bd9bb  bgt.s    loc_1BD9DA
0x1bd9bd  ldloc.s  0xA
0x1bd9bf  ldc.i4   0x400
0x1bd9c4  beq      loc_1BE4CA
0x1bd9c9  ldloc.s  0xA
0x1bd9cb  ldc.i4   0x401
0x1bd9d0  beq      loc_1BE754
0x1bd9d5  br       loc_1BEBA4
0x1bd9da  ldloc.s  0xA
0x1bd9dc  ldc.i4   0x418
0x1bd9e1  beq      loc_1BE727
0x1bd9e6  ldloc.s  0xA
0x1bd9e8  ldc.i4   0x43B
0x1bd9ed  sub
0x1bd9ee  switch   loc_1BE460, loc_1BE7D1, loc_1BE3DC, loc_1BEBA4, loc_1BEBA4, loc_1BE7D1, loc_1BE41E, loc_1BE7D1, loc_1BE39A
0x1bda17  br       loc_1BEBA4
0x1bda1c  ldloc.s  0xA
0x1bda1e  ldc.i4   0x106F
0x1bda23  bgt.s    loc_1BDA4B
0x1bda25  ldloc.s  0xA
0x1bda27  ldc.i4   0x1069
0x1bda2c  beq.s    loc_1BDAA3
0x1bda2e  ldloc.s  0xA
0x1bda30  ldc.i4   0x106A
0x1bda35  beq      loc_1BDBBE
0x1bda3a  ldloc.s  0xA
0x1bda3c  ldc.i4   0x106F
0x1bda41  beq      loc_1BEBA4
0x1bda46  br       loc_1BEBA4
0x1bda4b  ldloc.s  0xA
0x1bda4d  ldc.i4   0x109B
0x1bda52  bgt.s    loc_1BDA86
0x1bda54  ldloc.s  0xA
0x1bda56  ldc.i4   0x1072
0x1bda5b  sub
0x1bda5c  switch   loc_1BEBA4, loc_1BEBA4, loc_1BEBA4, loc_1BEBA4, loc_1BDDA6
0x1bda75  ldloc.s  0xA
0x1bda77  ldc.i4   0x109B
0x1bda7c  beq      loc_1BDC63
0x1bda81  br       loc_1BEBA4
0x1bda86  ldloc.s  0xA
0x1bda88  ldc.i4   0x2454
0x1bda8d  beq      loc_1BEB52
0x1bda92  ldloc.s  0xA
0x1bda94  ldc.i4   0x25E4
0x1bda99  beq      loc_1BEB7C
0x1bda9e  br       loc_1BEBA4
0x1bdaa3  ldloc.0
0x1bdaa4  ldsfld   class [mscorlib]System.Predicate`1<class [Microsoft.Crm.Client.Shared]Microsoft.Crm.Client.Core.Models.ResourceStringModel> <>c::<>9__5_0
0x1bdaa9  dup
0x1bdaaa  brtrue.s loc_1BDAC3
  ... truncated ...
```
