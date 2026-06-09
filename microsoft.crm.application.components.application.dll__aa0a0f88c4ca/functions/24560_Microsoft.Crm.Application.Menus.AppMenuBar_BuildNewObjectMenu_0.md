# Microsoft.Crm.Application.Menus.AppMenuBar::BuildNewObjectMenu_0

- ea: `0x24560`
- end: `0x24945`
- name: `Microsoft.Crm.Application.Menus.AppMenuBar::BuildNewObjectMenu_0`
- size: `997`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x24550`

## callees

- `0x24210`
- `0x24560`
- `0x46e30`

## string_xrefs

- `0x246db`: `new Mscrm.CrmDialog(Mscrm.CrmUri.create('/cs/contracts/lookup_template.aspx'),window,{0},{1}).show();`
- `0x246ad`: `cs/contracts/lookup_template.aspx_WINDOW_WIDTH`
- `0x246be`: `cs/contracts/lookup_template.aspx_WINDOW_HEIGHT`
- `0x24700`: `cs/articles/lookup_template.aspx_WINDOW_WIDTH`
- `0x24711`: `cs/articles/lookup_template.aspx_WINDOW_HEIGHT`
- `0x2473e`: `openStdDlg(Mscrm.CrmUri.create('/cs/articles/lookup_template.aspx'),null,`

## pseudocode

```c

```

## disassembly

```asm
0x24560  ldarg.2
0x24561  brfalse.s loc_24585
0x24563  ldarg.0
0x24564  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::_menuBar
0x24569  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager::get_Default()
0x2456e  ldstr    aMenuitemLabelN// "MenuItem_Label_New"
0x24573  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24578  ldstr    aNewsub// "newSub"
0x2457d  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::CreateMenu(string, string)
0x24582  stloc.0
0x24583  br.s     loc_24587
0x24585  ldarg.1
0x24586  stloc.0
0x24587  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateLead()
0x2458c  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24591  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24596  brfalse.s loc_245AC
0x24598  ldloc.0
0x24599  ldc.i4.4
0x2459a  ldc.i4.1
0x2459b  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x245a0  ldc.i4.4
0x245a1  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x245a6  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x245ab  pop
0x245ac  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOpportunity()
0x245b1  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x245b6  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x245bb  brfalse.s loc_245D1
0x245bd  ldloc.0
0x245be  ldc.i4.3
0x245bf  ldc.i4.1
0x245c0  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x245c5  ldc.i4.3
0x245c6  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x245cb  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x245d0  pop
0x245d1  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateQuote()
0x245d6  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x245db  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x245e0  brfalse.s loc_245FE
0x245e2  ldloc.0
0x245e3  ldc.i4   0x43C
0x245e8  ldc.i4.1
0x245e9  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x245ee  ldc.i4   0x43C
0x245f3  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x245f8  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x245fd  pop
0x245fe  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateOrder()
0x24603  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24608  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2460d  brfalse.s loc_2462B
0x2460f  ldloc.0
0x24610  ldc.i4   0x440
0x24615  ldc.i4.1
0x24616  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x2461b  ldc.i4   0x440
0x24620  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x24625  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x2462a  pop
0x2462b  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateInvoice()
0x24630  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24635  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2463a  brfalse.s loc_24658
0x2463c  ldloc.0
0x2463d  ldc.i4   0x442
0x24642  ldc.i4.1
0x24643  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x24648  ldc.i4   0x442
0x2464d  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x24652  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x24657  pop
0x24658  ldloc.0
0x24659  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x2465e  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateIncident()
0x24663  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24668  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2466d  brfalse.s loc_24685
0x2466f  ldloc.0
0x24670  ldc.i4.s 0x70
0x24672  ldc.i4.1
0x24673  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x24678  ldc.i4.s 0x70
0x2467a  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x2467f  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x24684  pop
0x24685  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateContract()
0x2468a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2468f  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24694  brfalse.s loc_246FA
0x24696  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_ReadContractTemplate()
0x2469b  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x246a0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x246a5  brfalse.s loc_246FA
0x246a7  ldarg.0
0x246a8  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x246ad  ldstr    aCsContractsLoo_0// "cs/contracts/lookup_template.aspx_WINDO"...
0x246b2  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x246b7  stloc.3
0x246b8  ldarg.0
0x246b9  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x246be  ldstr    aCsContractsLoo_1// "cs/contracts/lookup_template.aspx_WINDO"...
0x246c3  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x246c8  stloc.s  4
0x246ca  ldloc.0
0x246cb  ldc.i4   0x3F2
0x246d0  ldc.i4.1
0x246d1  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x246d6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x246db  ldstr    aNewMscrmCrmdia_0// "new Mscrm.CrmDialog(Mscrm.CrmUri.create"...
0x246e0  ldc.i4.2
0x246e1  newarr   [mscorlib]System.Object
0x246e6  dup
0x246e7  ldc.i4.0
0x246e8  ldloc.3
0x246e9  stelem.ref
0x246ea  dup
0x246eb  ldc.i4.1
0x246ec  ldloc.s  4
0x246ee  stelem.ref
0x246ef  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x246f4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x246f9  pop
0x246fa  ldarg.0
0x246fb  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x24700  ldstr    aCsArticlesLook_0// "cs/articles/lookup_template.aspx_WINDOW"...
0x24705  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2470a  stloc.1
0x2470b  ldarg.0
0x2470c  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x24711  ldstr    aCsArticlesLook_1// "cs/articles/lookup_template.aspx_WINDOW"...
0x24716  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x2471b  stloc.2
0x2471c  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateArticle()
0x24721  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24726  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2472b  brfalse.s loc_24767
0x2472d  ldloc.0
0x2472e  ldc.i4.s 0x7F
0x24730  ldc.i4.1
0x24731  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x24736  ldc.i4.5
0x24737  newarr   [mscorlib]System.String
0x2473c  dup
0x2473d  ldc.i4.0
0x2473e  ldstr    aOpenstddlgMscr_2// "openStdDlg(Mscrm.CrmUri.create('/cs/art"...
0x24743  stelem.ref
0x24744  dup
0x24745  ldc.i4.1
0x24746  ldloc.1
0x24747  stelem.ref
0x24748  dup
0x24749  ldc.i4.2
0x2474a  ldstr    asc_11387C// ","
0x2474f  stelem.ref
0x24750  dup
0x24751  ldc.i4.3
0x24752  ldloc.2
0x24753  stelem.ref
0x24754  dup
0x24755  ldc.i4.4
0x24756  ldstr    asc_11632C// ");"
0x2475b  stelem.ref
0x2475c  call     string [mscorlib]System.String::Concat(string[])
0x24761  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x24766  pop
0x24767  ldloc.0
0x24768  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x2476d  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateAccount()
0x24772  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24777  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2477c  brfalse.s loc_24792
0x2477e  ldloc.0
0x2477f  ldc.i4.1
0x24780  ldc.i4.1
0x24781  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x24786  ldc.i4.1
0x24787  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x2478c  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x24791  pop
0x24792  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateContact()
0x24797  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2479c  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x247a1  brfalse.s loc_247B7
0x247a3  ldloc.0
0x247a4  ldc.i4.2
0x247a5  ldc.i4.1
0x247a6  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x247ab  ldc.i4.2
0x247ac  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x247b1  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x247b6  pop
0x247b7  ldloc.0
0x247b8  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.CommandBar::AddSpacer()
0x247bd  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateCampaign()
0x247c2  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x247c7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x247cc  brfalse.s loc_247EA
0x247ce  ldloc.0
0x247cf  ldc.i4   0x1130
0x247d4  ldc.i4.1
0x247d5  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x247da  ldc.i4   0x1130
0x247df  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x247e4  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x247e9  pop
0x247ea  call     class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition [Microsoft.Crm.Privileges]Microsoft.Crm.Privileges::get_CreateList()
0x247ef  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x247f4  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(class [Microsoft.Crm.Privileges]Microsoft.Crm.PrivilegeDefinition, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x247f9  brfalse.s loc_24817
0x247fb  ldloc.0
0x247fc  ldc.i4   0x10CC
0x24801  ldc.i4.1
0x24802  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x24807  ldc.i4   0x10CC
0x2480c  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x24811  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x24816  pop
0x24817  ldarg.2
0x24818  brfalse.s loc_2482A
0x2481a  ldloc.0
0x2481b  callvirt instance int32 [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::get_Length()
0x24820  ldc.i4.0
0x24821  ble.s    loc_2482A
0x24823  ldarg.1
0x24824  ldloc.0
0x24825  callvirt instance void [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu)
0x2482a  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x2482f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x24834  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x24839  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x2483e  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_CustomEntities()
0x24843  callvirt instance int32 [mscorlib]System.Collections.ICollection::get_Count()
0x24848  ldc.i4.0
0x24849  ble      loc_24944
0x2484e  ldarg.0
0x2484f  ldfld    class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar Microsoft.Crm.Application.Menus.AppMenuBar::_menuBar
0x24854  ldarg.0
0x24855  call     instance class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Utility.AppResourceManager Microsoft.Crm.Application.Menus.AppMenuBar::get_CurrentResourceManager()
0x2485a  ldstr    aWebMore// "Web.More"
0x2485f  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.ResourceManager.BasicResourceManager::GetString(string)
0x24864  ldstr    aNewadd// "newAdd"
0x24869  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.MenuBar::CreateMenu(string, string)
0x2486e  stloc.s  5
0x24870  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x24875  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x2487a  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x2487f  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x24884  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_CustomEntities()
0x24889  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.IDictionary::get_Keys()
0x2488e  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x24893  stloc.s  6
0x24895  br.s     loc_2490F
0x24897  ldloc.s  6
0x24899  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x2489e  stloc.s  7
0x248a0  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x248a5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_OrganizationId()
0x248aa  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0x248af  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x248b4  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IEntityMetadataCollection [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_CustomEntities()
0x248b9  ldloc.s  7
0x248bb  callvirt instance var<u1> class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.IMetadataHashtable`1<class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata>::get_Item(!!T0)
0x248c0  stloc.s  8
0x248c2  ldloc.s  8
0x248c4  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x248c9  ldc.i4.s 0x20
0x248cb  call     class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Security.UserInformation::get_Current()
0x248d0  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Security.User::GetPrivilege(int32, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Types.PrivilegeId, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0x248d5  brfalse.s loc_2490F
0x248d7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x248dc  brtrue.s loc_248E7
0x248de  ldloc.s  8
0x248e0  callvirt instance bool [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_IsReplicated()
0x248e5  brtrue.s loc_248EE
0x248e7  call     bool [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.Util::IsOnline()
0x248ec  brfalse.s loc_2490F
0x248ee  ldloc.s  5
0x248f0  ldloc.s  8
0x248f2  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x248f7  ldc.i4.1
0x248f8  call     string Microsoft.Crm.Application.Utility.WebUtility::GetFmtObjName(int32 objectTypeCode, valuetype [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.NameFormatStyle formatStyle)
0x248fd  ldloc.s  8
0x248ff  callvirt instance int32 [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.EntityMetadata::get_Code()
0x24904  call     string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Script::BuildOpenObject(int32)
0x24909  callvirt instance class [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.ICrmCommandBarControl [Microsoft.Crm.Application.Components.UI]Microsoft.Crm.Controls.Menu::AddItem(string, string)
0x2490e  pop
0x2490f  ldloc.s  6
0x24911  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x24916  brtrue   loc_24897
0x2491b  leave.s  loc_24932
0x2491d  ldloc.s  6
0x2491f  isinst   [mscorlib]System.IDisposable
0x24924  stloc.s  9
0x24926  ldloc.s  9
0x24928  brfalse.s loc_24931
0x2492a  ldloc.s  9
0x2492c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x24931  endfinally
  ... truncated ...
```
