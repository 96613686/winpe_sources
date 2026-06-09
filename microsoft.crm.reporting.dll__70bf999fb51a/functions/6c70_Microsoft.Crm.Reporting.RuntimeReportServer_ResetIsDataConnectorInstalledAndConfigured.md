# Microsoft.Crm.Reporting.RuntimeReportServer::ResetIsDataConnectorInstalledAndConfigured

- ea: `0x6c70`
- end: `0x6cc7`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::ResetIsDataConnectorInstalledAndConfigured`
- size: `87`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x6c70`

## pseudocode

```c

```

## disassembly

```asm
0x6c70  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x6c75  brfalse.s loc_6C9B
0x6c77  volatile.
0x6c79  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) object Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfiguredLock
0x6c7e  stloc.0
0x6c7f  ldc.i4.0
0x6c80  stloc.1
0x6c81  ldloc.0
0x6c82  ldloca.s 1
0x6c84  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6c89  ldnull
0x6c8a  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<string, class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorConfigured
0x6c8f  leave.s  loc_6C9B
0x6c91  ldloc.1
0x6c92  brfalse.s loc_6C9A
0x6c94  ldloc.0
0x6c95  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6c9a  endfinally
0x6c9b  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x6ca0  brfalse.s loc_6CC6
0x6ca2  volatile.
0x6ca4  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) object Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalledLock
0x6ca9  stloc.0
0x6caa  ldc.i4.0
0x6cab  stloc.1
0x6cac  ldloc.0
0x6cad  ldloca.s 1
0x6caf  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x6cb4  ldnull
0x6cb5  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x6cba  leave.s  loc_6CC6
0x6cbc  ldloc.1
0x6cbd  brfalse.s loc_6CC5
0x6cbf  ldloc.0
0x6cc0  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x6cc5  endfinally
0x6cc6  ret
```
