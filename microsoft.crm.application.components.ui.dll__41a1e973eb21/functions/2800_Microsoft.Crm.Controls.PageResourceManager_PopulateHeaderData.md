# Microsoft.Crm.Controls.PageResourceManager::PopulateHeaderData

- ea: `0x2800`
- end: `0x2a36`
- name: `Microsoft.Crm.Controls.PageResourceManager::PopulateHeaderData`
- size: `566`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `broker_com_uri`

## callers

- `0x2ce0`

## callees

- `0x2330`
- `0x24f0`
- `0x2560`
- `0x25d0`
- `0x25e0`
- `0x25f0`
- `0x2600`
- `0x2610`
- `0x2620`
- `0x2750`
- `0x2800`
- `0x2a40`
- `0x2ad0`
- `0x2c70`
- `0x3e90`

## string_xrefs

- `0x2a1b`: `header_process_CaseResearch_LinkControl_casesconversations`

## pseudocode

```c

```

## disassembly

```asm
0x2800  ldarg.0
0x2801  callvirt instance void Microsoft.Crm.Controls.PageResourceManager::PrepareForRendering()
0x2806  ldarg.0
0x2807  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::get_Scripts()
0x280c  brfalse.s loc_281F
0x280e  ldarg.1
0x280f  ldarg.0
0x2810  call     instance class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair> Microsoft.Crm.Controls.PageResourceManager::GetScriptIncludesWithStage()
0x2815  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair>::ToArray()
0x281a  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ScriptIncludes
0x281f  ldarg.0
0x2820  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::get_Styles()
0x2825  brfalse.s loc_285C
0x2827  ldarg.1
0x2828  ldarg.0
0x2829  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::get_Styles()
0x282e  ldsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri, string> <>c::<>9__127_0
0x2833  dup
0x2834  brtrue.s loc_284D
0x2836  pop
0x2837  ldsfld   class <>c <>c::<>9
0x283c  ldftn    instance string <>c::<PopulateHeaderData>b__127_0(class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri headerInList)
0x2842  newobj   instance void class [mscorlib]System.Func`2<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri, string>::.ctor(object, native int)
0x2847  dup
0x2848  stsfld   class [mscorlib]System.Func`2<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri, string> <>c::<>9__127_0
0x284d  call     T0x2B000002
0x2852  call     T0x2B000003
0x2857  stfld    string[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::StyleIncludes
0x285c  ldarg.0
0x285d  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_ClientVars()
0x2862  brfalse.s loc_2890
0x2864  ldarg.1
0x2865  ldarg.0
0x2866  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_ClientVars()
0x286b  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x2870  call     T0x2B000004
0x2875  ldarg.0
0x2876  ldftn    instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair Microsoft.Crm.Controls.PageResourceManager::<PopulateHeaderData>b__127_1(string key)
0x287c  newobj   instance void class [mscorlib]System.Func`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair>::.ctor(object, native int)
0x2881  call     T0x2B000005
0x2886  call     T0x2B000006
0x288b  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ClientVariables
0x2890  ldarg.0
0x2891  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_Resources()
0x2896  brfalse.s loc_28F3
0x2898  ldarg.0
0x2899  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_Resources()
0x289e  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x28a3  call     T0x2B000004
0x28a8  ldarg.0
0x28a9  ldftn    instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair Microsoft.Crm.Controls.PageResourceManager::<PopulateHeaderData>b__127_2(string key)
0x28af  newobj   instance void class [mscorlib]System.Func`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair>::.ctor(object, native int)
0x28b4  call     T0x2B000005
0x28b9  stloc.s  4
0x28bb  ldarg.1
0x28bc  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ClientVariables
0x28c1  brfalse.s loc_28E6
0x28c3  ldarg.1
0x28c4  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ClientVariables
0x28c9  ldlen
0x28ca  brfalse.s loc_28E6
0x28cc  ldarg.1
0x28cd  ldarg.1
0x28ce  ldfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ClientVariables
0x28d3  ldloc.s  4
0x28d5  call     T0x2B000007
0x28da  call     T0x2B000006
0x28df  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ClientVariables
0x28e4  br.s     loc_28F3
0x28e6  ldarg.1
0x28e7  ldloc.s  4
0x28e9  call     T0x2B000006
0x28ee  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ClientVariables
0x28f3  ldarg.0
0x28f4  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_JQueryTemplates()
0x28f9  brfalse.s loc_2927
0x28fb  ldarg.1
0x28fc  ldarg.0
0x28fd  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_JQueryTemplates()
0x2902  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x2907  call     T0x2B000004
0x290c  ldarg.0
0x290d  ldftn    instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair Microsoft.Crm.Controls.PageResourceManager::<PopulateHeaderData>b__127_3(string key)
0x2913  newobj   instance void class [mscorlib]System.Func`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair>::.ctor(object, native int)
0x2918  call     T0x2B000005
0x291d  call     T0x2B000006
0x2922  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::JQueryTemplates
0x2927  ldarg.0
0x2928  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_ScriptBlocks()
0x292d  brfalse.s loc_295B
0x292f  ldarg.1
0x2930  ldarg.0
0x2931  call     instance class [System]System.Collections.Specialized.NameValueCollection Microsoft.Crm.Controls.PageResourceManager::get_ScriptBlocks()
0x2936  callvirt instance class [System]System.Collections.Specialized.NameObjectCollectionBase/KeysCollection [System]System.Collections.Specialized.NameObjectCollectionBase::get_Keys()
0x293b  call     T0x2B000004
0x2940  ldarg.0
0x2941  ldftn    instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair Microsoft.Crm.Controls.PageResourceManager::<PopulateHeaderData>b__127_4(string key)
0x2947  newobj   instance void class [mscorlib]System.Func`2<string, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair>::.ctor(object, native int)
0x294c  call     T0x2B000005
0x2951  call     T0x2B000006
0x2956  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ScriptBlocks
0x295b  ldarg.0
0x295c  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock> Microsoft.Crm.Controls.PageResourceManager::_scriptBlocksForOnLoad
0x2961  brfalse.s loc_299D
0x2963  ldarg.1
0x2964  ldarg.0
0x2965  ldfld    class [mscorlib]System.Collections.Generic.List`1<class Microsoft.Crm.Application.Components.UI.ScriptBlock> Microsoft.Crm.Controls.PageResourceManager::_scriptBlocksForOnLoad
0x296a  call     T0x2B000008
0x296f  ldsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Components.UI.ScriptBlock, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair> <>c::<>9__127_5
0x2974  dup
0x2975  brtrue.s loc_298E
0x2977  pop
0x2978  ldsfld   class <>c <>c::<>9
0x297d  ldftn    instance class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair <>c::<PopulateHeaderData>b__127_5(class Microsoft.Crm.Application.Components.UI.ScriptBlock sbfol)
0x2983  newobj   instance void class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Components.UI.ScriptBlock, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair>::.ctor(object, native int)
0x2988  dup
0x2989  stsfld   class [mscorlib]System.Func`2<class Microsoft.Crm.Application.Components.UI.ScriptBlock, class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair> <>c::<>9__127_5
0x298e  call     T0x2B000009
0x2993  call     T0x2B000006
0x2998  stfld    class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.NameValuePair[] [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ScriptBlocksOnLoad
0x299d  ldarg.0
0x299e  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::get_ActionPaths()
0x29a3  brfalse.s loc_29BA
0x29a5  ldarg.0
0x29a6  call     instance class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri> Microsoft.Crm.Controls.PageResourceManager::get_ActionPaths()
0x29ab  callvirt instance int32 class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri>::get_Count()
0x29b0  ldc.i4.0
0x29b1  ble.s    loc_29BA
0x29b3  ldarg.0
0x29b4  ldarg.1
0x29b5  call     instance void Microsoft.Crm.Controls.PageResourceManager::ProcessActionPaths(class [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData headerData)
0x29ba  ldarg.0
0x29bb  call     instance string Microsoft.Crm.Controls.PageResourceManager::get_ApplicationInitStatements()
0x29c0  stloc.0
0x29c1  ldloc.0
0x29c2  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29c7  brtrue.s loc_29D0
0x29c9  ldarg.1
0x29ca  ldloc.0
0x29cb  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ApplicationInitStatements
0x29d0  ldarg.0
0x29d1  call     instance string Microsoft.Crm.Controls.PageResourceManager::get_TurboApplicationInitStatements()
0x29d6  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29db  brtrue.s loc_29E9
0x29dd  ldarg.1
0x29de  ldarg.0
0x29df  call     instance string Microsoft.Crm.Controls.PageResourceManager::get_TurboApplicationInitStatements()
0x29e4  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::TurboApplicationInitStatements
0x29e9  ldarg.0
0x29ea  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetDeferredInitStatements()
0x29ef  stloc.1
0x29f0  ldloc.1
0x29f1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x29f6  brtrue.s loc_29FF
0x29f8  ldarg.1
0x29f9  ldloc.1
0x29fa  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::ApplicationInitDeferredStatements
0x29ff  ldarg.0
0x2a00  ldstr    aNotescontrol// "notescontrol"
0x2a05  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetSFATabsDeferredInitStatements(string containerId)
0x2a0a  stloc.2
0x2a0b  ldloc.2
0x2a0c  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a11  brtrue.s loc_2A1A
0x2a13  ldarg.1
0x2a14  ldloc.2
0x2a15  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::SFATabsInitDeferredStatements
0x2a1a  ldarg.0
0x2a1b  ldstr    aHeaderProcessC// "header_process_CaseResearch_LinkControl"...
0x2a20  call     instance string Microsoft.Crm.Controls.PageResourceManager::GetSFATabsDeferredInitStatements(string containerId)
0x2a25  stloc.3
0x2a26  ldloc.3
0x2a27  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2a2c  brtrue.s loc_2A35
0x2a2e  ldarg.1
0x2a2f  ldloc.3
0x2a30  stfld    string [Microsoft.Crm.Application.Components.Shared]Microsoft.Crm.Application.SharedObjects.MessageBar.PageHeaderData::CaseSFATabsInitDeferredStatements
0x2a35  ret
```
