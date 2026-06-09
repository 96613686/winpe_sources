# Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::ConfigureFormHandler

- ea: `0x12430`
- end: `0x1262b`
- name: `Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::ConfigureFormHandler`
- size: `507`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x12430`

## pseudocode

```c

```

## disassembly

```asm
0x12430  ldarg.0
0x12431  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x12436  ldc.i4.5
0x12437  ldarg.0
0x12438  dup
0x12439  ldvirtftn instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ChangeState(object, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs)
0x1243f  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x12444  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x12449  ldarg.0
0x1244a  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x1244f  ldc.i4.6
0x12450  ldarg.0
0x12451  dup
0x12452  ldvirtftn instance void [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::ChangeState(object, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs)
0x12458  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x1245d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x12462  ldarg.0
0x12463  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x12468  ldc.i4.s 0x23
0x1246a  ldarg.0
0x1246b  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::ConvertKit(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x12471  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x12476  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x1247b  ldarg.0
0x1247c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x12481  ldc.i4.s 0x24
0x12483  ldarg.0
0x12484  ldftn    instance void Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::ConvertKit(object sender, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventArgs e)
0x1248a  newobj   instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler::.ctor(object, native int)
0x1248f  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::RegisterDataEvent(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.FormEventId, class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.DataEventHandler)
0x12494  ldarg.0
0x12495  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CrmForm()
0x1249a  ldarg.0
0x1249b  callvirt instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Components.PageHandlers.PageHandler::get_CurrentEntity()
0x124a0  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::Execute(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.Entity)
0x124a5  ldarg.0
0x124a6  ldarg.0
0x124a7  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x124ac  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_DataXml()
0x124b1  ldstr    aIskit// "iskit"
0x124b6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsBool(string, string)
0x124bb  stfld    bool Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::bIsKit
0x124c0  ldarg.0
0x124c1  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x124c6  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_DataXml()
0x124cb  ldstr    aProductstructu// "productstructure"
0x124d0  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValue(string, string)
0x124d5  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x124da  brtrue.s loc_124F7
0x124dc  ldarg.0
0x124dd  ldarg.0
0x124de  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x124e3  callvirt instance string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_DataXml()
0x124e8  ldstr    aProductstructu// "productstructure"
0x124ed  call     int32 [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::GetNodeValueAsInt(string, string)
0x124f2  stfld    int32 Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::productStructure
0x124f7  ldarg.0
0x124f8  ldfld    int32 Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::productStructure
0x124fd  ldc.i4.3
0x124fe  bne.un.s loc_12556
0x12500  ldarg.0
0x12501  ldarg.0
0x12502  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x12507  ldstr    aObjectSingular// "Object_Singular_Bundle"
0x1250c  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12511  stfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x12516  ldarg.0
0x12517  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x1251c  ldarg.0
0x1251d  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x12522  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::get_Title()
0x12527  ldarg.0
0x12528  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentType()
0x1252d  ldc.i4.1
0x1252e  ldnull
0x1252f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x12534  ldarg.0
0x12535  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x1253a  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1253f  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x12544  ldarg.0
0x12545  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x1254a  ldarg.0
0x1254b  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x12550  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_FormTitleLabel(string)
0x12555  ret
0x12556  ldarg.0
0x12557  ldfld    int32 Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::productStructure
0x1255c  ldc.i4.2
0x1255d  bne.un.s loc_125B5
0x1255f  ldarg.0
0x12560  ldarg.0
0x12561  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x12566  ldstr    aObjectSingular_0// "Object_Singular_Product_Family"
0x1256b  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x12570  stfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x12575  ldarg.0
0x12576  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x1257b  ldarg.0
0x1257c  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x12581  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::get_Title()
0x12586  ldarg.0
0x12587  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentType()
0x1258c  ldc.i4.1
0x1258d  ldnull
0x1258e  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x12593  ldarg.0
0x12594  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x12599  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x1259e  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x125a3  ldarg.0
0x125a4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x125a9  ldarg.0
0x125aa  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x125af  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_FormTitleLabel(string)
0x125b4  ret
0x125b5  ldarg.0
0x125b6  ldfld    bool Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::bIsKit
0x125bb  brfalse.s loc_12613
0x125bd  ldarg.0
0x125be  ldarg.0
0x125bf  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentResourceManager()
0x125c4  ldstr    aObjectSingular_1// "Object_Singular_Kit"
0x125c9  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x125ce  stfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x125d3  ldarg.0
0x125d4  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x125d9  ldarg.0
0x125da  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Controls.AppHeader [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentHeader()
0x125df  callvirt instance string [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::get_Title()
0x125e4  ldarg.0
0x125e5  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentType()
0x125ea  ldc.i4.1
0x125eb  ldnull
0x125ec  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Platform.EntityType::GetDisplayName(valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle, class [mscorlib]System.Globalization.CultureInfo)
0x125f1  ldarg.0
0x125f2  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x125f7  callvirt instance string [mscorlib]System.String::Replace(string, string)
0x125fc  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.PageResourceManager::set_Title(string)
0x12601  ldarg.0
0x12602  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x12607  ldarg.0
0x12608  ldfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x1260d  callvirt instance void [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::set_FormTitleLabel(string)
0x12612  ret
0x12613  ldarg.0
0x12614  ldarg.0
0x12615  call     instance class [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm [Microsoft.Crm.Application.Pages]Microsoft.Crm.Application.Components.PageHandlers.RecordPageHandler::get_CurrentForm()
0x1261a  callvirt instance int32 [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Forms.AppForm::get_EntityTypeCode()
0x1261f  ldc.i4.1
0x12620  call     string [Microsoft.Crm.Application.Components.Application]Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle)
0x12625  stfld    string Microsoft.Crm.Common.Application.Components.PageHandlers.ProductRecordPageHandler::sObjectTypeName
0x1262a  ret
```
