# Microsoft.Crm.Reporting.RuntimeReportServer::IsDataConnectorConfigured_0

- ea: `0x5c70`
- end: `0x5d3f`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::IsDataConnectorConfigured_0`
- size: `207`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4be0`
- `0x5c70`

## pseudocode

```c

```

## disassembly

```asm
0x5c70  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x5c75  brtrue.s loc_5CA6
0x5c77  volatile.
0x5c79  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) object Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfiguredLock
0x5c7e  stloc.1
0x5c7f  ldc.i4.0
0x5c80  stloc.2
0x5c81  ldloc.1
0x5c82  ldloca.s 2
0x5c84  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5c89  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x5c8e  brtrue.s loc_5C9A
0x5c90  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>>::.ctor()
0x5c95  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x5c9a  leave.s  loc_5CA6
0x5c9c  ldloc.2
0x5c9d  brfalse.s loc_5CA5
0x5c9f  ldloc.1
0x5ca0  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5ca5  endfinally
0x5ca6  volatile.
0x5ca8  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) object Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfiguredLock
0x5cad  stloc.1
0x5cae  ldc.i4.0
0x5caf  stloc.2
0x5cb0  ldloc.1
0x5cb1  ldloca.s 2
0x5cb3  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5cb8  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x5cbd  ldarg.1
0x5cbe  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_OrganizationName()
0x5cc3  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>>::ContainsKey(var<u1>)
0x5cc8  brtrue.s loc_5CDF
0x5cca  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x5ccf  ldarg.1
0x5cd0  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_OrganizationName()
0x5cd5  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::.ctor()
0x5cda  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>>::set_Item(var<u1>, !!T0)
0x5cdf  leave.s  loc_5CEB
0x5ce1  ldloc.2
0x5ce2  brfalse.s loc_5CEA
0x5ce4  ldloc.1
0x5ce5  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5cea  endfinally
0x5ceb  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x5cf0  ldarg.1
0x5cf1  callvirt instance string [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext::get_OrganizationName()
0x5cf6  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>>::get_Item(void)
0x5cfb  stloc.0
0x5cfc  volatile.
0x5cfe  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) object Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfiguredLock
0x5d03  stloc.1
0x5d04  ldc.i4.0
0x5d05  stloc.2
0x5d06  ldloc.1
0x5d07  ldloca.s 2
0x5d09  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5d0e  ldloc.0
0x5d0f  ldarg.2
0x5d10  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::ContainsKey(var<u1>)
0x5d15  brtrue.s loc_5D2B
0x5d17  ldloc.0
0x5d18  ldarg.2
0x5d19  ldarg.0
0x5d1a  ldarg.0
0x5d1b  ldfld    class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext Microsoft.Crm.Reporting.RuntimeReportServer::_organizationContext
0x5d20  ldarg.2
0x5d21  call     instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorConfigured(class [Microsoft.Crm.ReportObjectModel]Microsoft.Crm.ReportObjectModel.ReportServerOrganizationContext organizationContext, valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x5d26  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::set_Item(var<u1>, !!T0)
0x5d2b  leave.s  loc_5D37
0x5d2d  ldloc.2
0x5d2e  brfalse.s loc_5D36
0x5d30  ldloc.1
0x5d31  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5d36  endfinally
0x5d37  ldloc.0
0x5d38  ldarg.2
0x5d39  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::get_Item(void)
0x5d3e  ret
```
