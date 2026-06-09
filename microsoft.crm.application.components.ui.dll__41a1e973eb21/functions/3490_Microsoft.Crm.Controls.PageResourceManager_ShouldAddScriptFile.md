# Microsoft.Crm.Controls.PageResourceManager::ShouldAddScriptFile

- ea: `0x3490`
- end: `0x3549`
- name: `Microsoft.Crm.Controls.PageResourceManager::ShouldAddScriptFile`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x3550`

## callees

- `0x3490`

## string_xrefs

- `0x349d`: `/_STATIC/_COMMON/SCRIPTS/GLOBAL.JS`
- `0x34aa`: `/_COMMON/GLOBAL.ASHX`
- `0x34c4`: `/_STATIC/_COMMON/SCRIPTS/CRMSERVICEPROXY.JS`
- `0x34d1`: `/_STATIC/_COMMON/SCRIPTS/CRMSERVICEPROXYFRAMEWORK.JS`
- `0x34de`: `/_STATIC/_COMMON/SCRIPTS/SCRIPTCLIENTAPI.JS`
- `0x34eb`: `/_STATIC/_COMMON/SCRIPTS/CLIENTAPICOMMONUTILITIES.JS`
- `0x34fa`: `/_COMMON/SCRIPTRESX.ASHX`
- `0x3514`: `/_STATIC/_COMMON/SCRIPTS/JQUERY-2.1.1.MIN.JS`
- `0x352e`: `/_STATIC/_COMMON/SCRIPTS/JQUERY.TMPL.MIN.JS`
- `0x353b`: `jQuery template should loaded through LoadJQueryTemplate flag`

## pseudocode

```c

```

## disassembly

```asm
0x3490  ldarg.1
0x3491  callvirt instance string [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Application.Utility.CrmUri::get_Path()
0x3496  callvirt instance string [mscorlib]System.String::ToUpperInvariant()
0x349b  stloc.0
0x349c  ldloc.0
0x349d  ldstr    aStaticCommonSc// "/_STATIC/_COMMON/SCRIPTS/GLOBAL.JS"
0x34a2  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34a7  brtrue.s loc_34B6
0x34a9  ldloc.0
0x34aa  ldstr    aCommonGlobalAs// "/_COMMON/GLOBAL.ASHX"
0x34af  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34b4  brfalse.s loc_34C3
0x34b6  ldc.i4.0
0x34b7  ldstr    aGlobalAshxIsAu// "Global.ashx is automatically included i"...
0x34bc  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x34c1  ldc.i4.0
0x34c2  ret
0x34c3  ldloc.0
0x34c4  ldstr    aStaticCommonSc_0// "/_STATIC/_COMMON/SCRIPTS/CRMSERVICEPROX"...
0x34c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34ce  brtrue.s loc_34F7
0x34d0  ldloc.0
0x34d1  ldstr    aStaticCommonSc_1// "/_STATIC/_COMMON/SCRIPTS/CRMSERVICEPROX"...
0x34d6  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34db  brtrue.s loc_34F7
0x34dd  ldloc.0
0x34de  ldstr    aStaticCommonSc_2// "/_STATIC/_COMMON/SCRIPTS/SCRIPTCLIENTAP"...
0x34e3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34e8  brtrue.s loc_34F7
0x34ea  ldloc.0
0x34eb  ldstr    aStaticCommonSc_3// "/_STATIC/_COMMON/SCRIPTS/CLIENTAPICOMMO"...
0x34f0  call     bool [mscorlib]System.String::op_Equality(string, string)
0x34f5  brfalse.s loc_34F9
0x34f7  ldc.i4.0
0x34f8  ret
0x34f9  ldloc.0
0x34fa  ldstr    aCommonScriptre// "/_COMMON/SCRIPTRESX.ASHX"
0x34ff  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3504  brfalse.s loc_3513
0x3506  ldc.i4.0
0x3507  ldstr    aScriptresxAshx// "ScriptResx.ashx is automatically includ"...
0x350c  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x3511  ldc.i4.0
0x3512  ret
0x3513  ldloc.0
0x3514  ldstr    aStaticCommonSc_4// "/_STATIC/_COMMON/SCRIPTS/JQUERY-2.1.1.M"...
0x3519  call     bool [mscorlib]System.String::op_Equality(string, string)
0x351e  brfalse.s loc_352D
0x3520  ldc.i4.0
0x3521  ldstr    aJqueryShouldLo// "jQuery should loaded through LoadJQuery"...
0x3526  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x352b  ldc.i4.0
0x352c  ret
0x352d  ldloc.0
0x352e  ldstr    aStaticCommonSc_5// "/_STATIC/_COMMON/SCRIPTS/JQUERY.TMPL.MI"...
0x3533  call     bool [mscorlib]System.String::op_Equality(string, string)
0x3538  brfalse.s loc_3547
0x353a  ldc.i4.0
0x353b  ldstr    aJqueryTemplate// "jQuery template should loaded through L"...
0x3540  call     void [Microsoft.Crm.Application.Components.Platform]Microsoft.Crm.Diagnostics.Debug::AssertEx(bool, string)
0x3545  ldc.i4.0
0x3546  ret
0x3547  ldc.i4.1
0x3548  ret
```
