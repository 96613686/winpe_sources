# Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::EnqueueScriptReference

- ea: `0xa77b0`
- end: `0xa7941`
- name: `Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::EnqueueScriptReference`
- size: `401`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0xa7450`

## string_xrefs

- `0xa7836`: `/_static/_common/scripts/CrmInternalUtility.js`
- `0xa7846`: `/_static/_common/scripts/Mscrm.Caching.js`
- `0xa78e6`: `/_static/_common/scripts/InlineEditCommon.js`
- `0xa77e6`: `/_static/_common/scripts/SalesCommonImported.js`
- `0xa77f6`: `/_static/_common/scripts/SalesCommonFramework.js`
- `0xa77b6`: `/_static/_common/scripts/underscore.js`
- `0xa77c6`: `/_static/_common/scripts/backbone.js`
- `0xa7816`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0xa77d6`: `/_static/_common/scripts/jquery.owa.touch.js`
- `0xa7806`: `/_static/_common/scripts/CrmServiceProxy.js`
- `0xa7826`: `/_static/_common/scripts/SalesCrmSoapProxyService.js`

## pseudocode

```c

```

## disassembly

```asm
0xa77b0  ldarg.0
0xa77b1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa77b6  ldstr    aStaticCommonSc_32// "/_static/_common/scripts/underscore.js"
0xa77bb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa77c0  ldarg.0
0xa77c1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa77c6  ldstr    aStaticCommonSc_33// "/_static/_common/scripts/backbone.js"
0xa77cb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa77d0  ldarg.0
0xa77d1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa77d6  ldstr    aStaticCommonSc_38// "/_static/_common/scripts/jquery.owa.tou"...
0xa77db  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa77e0  ldarg.0
0xa77e1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa77e6  ldstr    aStaticCommonSc_29// "/_static/_common/scripts/SalesCommonImp"...
0xa77eb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa77f0  ldarg.0
0xa77f1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa77f6  ldstr    aStaticCommonSc_30// "/_static/_common/scripts/SalesCommonFra"...
0xa77fb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7800  ldarg.0
0xa7801  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7806  ldstr    aStaticCommonSc_39// "/_static/_common/scripts/CrmServiceProx"...
0xa780b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7810  ldarg.0
0xa7811  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7816  ldstr    aStaticCommonSc_34// "/_static/_common/scripts/CrmServiceProx"...
0xa781b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7820  ldarg.0
0xa7821  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7826  ldstr    aStaticCommonSc_40// "/_static/_common/scripts/SalesCrmSoapPr"...
0xa782b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7830  ldarg.0
0xa7831  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7836  ldstr    aStaticCommonSc// "/_static/_common/scripts/CrmInternalUti"...
0xa783b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7840  ldarg.0
0xa7841  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7846  ldstr    aStaticCommonSc_13// "/_static/_common/scripts/Mscrm.Caching."...
0xa784b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7850  ldarg.0
0xa7851  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7856  ldstr    aStaticControls_23// "/_static/_controls/ProcessControl/Proce"...
0xa785b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7860  ldarg.0
0xa7861  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7866  ldstr    aStaticFormsSel// "/_static/_forms/select.js"
0xa786b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7870  ldarg.0
0xa7871  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7876  ldstr    aStaticFormsTex// "/_static/_forms/TextInputBehavior.js"
0xa787b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7880  ldarg.0
0xa7881  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7886  ldstr    aStaticFormsLoo_0// "/_static/_forms/LookupBehavior.js"
0xa788b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7890  ldarg.0
0xa7891  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7896  ldstr    aStaticFormsNum// "/_static/_forms/NumberInputBehavior.js"
0xa789b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa78a0  ldarg.0
0xa78a1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa78a6  ldstr    aStaticFormsDat// "/_static/_forms/DateTime.js"
0xa78ab  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa78b0  ldarg.0
0xa78b1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa78b6  ldstr    aStaticFormsChe// "/_static/_forms/Checkbox.js"
0xa78bb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa78c0  ldarg.0
0xa78c1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa78c6  ldstr    aStaticFormsTab// "/_static/_forms/tabs.js"
0xa78cb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa78d0  ldarg.0
0xa78d1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa78d6  ldstr    aStaticFormsFor// "/_static/_forms/form.js"
0xa78db  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa78e0  ldarg.0
0xa78e1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa78e6  ldstr    aStaticCommonSc_15// "/_static/_common/scripts/InlineEditComm"...
0xa78eb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa78f0  ldarg.0
0xa78f1  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa78f6  ldstr    aStaticControls_8// "/_static/_controls/inlineedit/InlineEdi"...
0xa78fb  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7900  ldarg.0
0xa7901  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7906  ldstr    aStaticControls_22// "/_static/_controls/inlineedit/inlineedi"...
0xa790b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7910  ldarg.0
0xa7911  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7916  ldstr    aStaticControls_28// "/_static/_controls/FlyOutDialog/FlyOutD"...
0xa791b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7920  ldarg.0
0xa7921  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7926  ldstr    aStaticToolsSys_2// "/_static/tools/systemcustomization/busi"...
0xa792b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7930  ldarg.0
0xa7931  ldfld    class [System]System.Collections.Generic.Queue`1<string> Microsoft.Crm.Web.Tools.SystemCustomization.Process.ProcessDesignerViewModel::_requiredScriptsQueue
0xa7936  ldstr    aStaticToolsSys_18// "/_static/tools/systemcustomization/proc"...
0xa793b  callvirt instance void class [System]System.Collections.Generic.Queue`1<string>::Enqueue(var<u1>)
0xa7940  ret
```
