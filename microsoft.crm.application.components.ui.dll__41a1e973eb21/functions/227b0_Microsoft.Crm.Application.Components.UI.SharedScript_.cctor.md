# Microsoft.Crm.Application.Components.UI.SharedScript::.cctor

- ea: `0x227b0`
- end: `0x22869`
- name: `Microsoft.Crm.Application.Components.UI.SharedScript::.cctor`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x142c0`
- `0x226f0`
- `0x22710`
- `0x227a0`

## string_xrefs

- `0x227b6`: `/_static/_common/scripts/CrmServiceProxy.js`
- `0x2280c`: `/_static/_common/scripts/CrmServiceProxy.js`
- `0x227d6`: `/_static/_common/scripts/CrmServiceProxyFramework.js`
- `0x22848`: `/_static/_common/scripts/CrmServiceProxyFramework.js`

## pseudocode

```c

```

## disassembly

```asm
0x227b0  newobj   instance void Microsoft.Crm.Application.Components.UI.SharedScript::.ctor()
0x227b5  dup
0x227b6  ldstr    aStaticCommonSc_47// "/_static/_common/scripts/CrmServiceProx"...
0x227bb  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_Url(string value)
0x227c0  dup
0x227c1  ldstr    aFunctionHostTy// "function(host){\r\n\tType.registerNames"...
0x227c6  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_ImportJavaScript(string value)
0x227cb  stsfld   class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::crmServiceProxy
0x227d0  newobj   instance void Microsoft.Crm.Application.Components.UI.SharedScript::.ctor()
0x227d5  dup
0x227d6  ldstr    aStaticCommonSc_48// "/_static/_common/scripts/CrmServiceProx"...
0x227db  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_Url(string value)
0x227e0  dup
0x227e1  ldstr    aFunctionHostTy_0// "function(host){\r\n\tType.registerNames"...
0x227e6  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_ImportJavaScript(string value)
0x227eb  stsfld   class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::crmServiceProxyFramework
0x227f0  newobj   instance void Microsoft.Crm.Application.Components.UI.SharedScript::.ctor()
0x227f5  stloc.0
0x227f6  ldloc.0
0x227f7  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x227fc  ldc.i4.1
0x227fd  newarr   [mscorlib]System.Char
0x22802  dup
0x22803  ldc.i4.0
0x22804  ldc.i4.s 0x2F
0x22806  stelem.i2
0x22807  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x2280c  ldstr    aStaticCommonSc_47// "/_static/_common/scripts/CrmServiceProx"...
0x22811  call     string [mscorlib]System.String::Concat(string, string)
0x22816  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_Url(string value)
0x2281b  ldloc.0
0x2281c  ldstr    aFunctionHostTy// "function(host){\r\n\tType.registerNames"...
0x22821  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_ImportJavaScript(string value)
0x22826  ldloc.0
0x22827  stsfld   class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::crmServiceProxyCDN
0x2282c  newobj   instance void Microsoft.Crm.Application.Components.UI.SharedScript::.ctor()
0x22831  stloc.0
0x22832  ldloc.0
0x22833  call     string Microsoft.Crm.Application.ContentDelivery.HostBasedContentDeliveryService::GetCDNUrl()
0x22838  ldc.i4.1
0x22839  newarr   [mscorlib]System.Char
0x2283e  dup
0x2283f  ldc.i4.0
0x22840  ldc.i4.s 0x2F
0x22842  stelem.i2
0x22843  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x22848  ldstr    aStaticCommonSc_48// "/_static/_common/scripts/CrmServiceProx"...
0x2284d  call     string [mscorlib]System.String::Concat(string, string)
0x22852  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_Url(string value)
0x22857  ldloc.0
0x22858  ldstr    aFunctionHostTy_0// "function(host){\r\n\tType.registerNames"...
0x2285d  callvirt instance void Microsoft.Crm.Application.Components.UI.SharedScript::set_ImportJavaScript(string value)
0x22862  ldloc.0
0x22863  stsfld   class Microsoft.Crm.Application.Components.UI.SharedScript Microsoft.Crm.Application.Components.UI.SharedScript::crmServiceProxyFrameworkCDN
0x22868  ret
```
