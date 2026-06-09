# Microsoft.Crm.Reporting.RuntimeReportServer::IsDataConnectorInstalled

- ea: `0x5600`
- end: `0x5691`
- name: `Microsoft.Crm.Reporting.RuntimeReportServer::IsDataConnectorInstalled`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callees

- `0x47f0`
- `0x5600`

## pseudocode

```c

```

## disassembly

```asm
0x5600  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x5605  brtrue.s loc_5636
0x5607  volatile.
0x5609  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) object Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalledLock
0x560e  stloc.0
0x560f  ldc.i4.0
0x5610  stloc.1
0x5611  ldloc.0
0x5612  ldloca.s 1
0x5614  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5619  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x561e  brtrue.s loc_562A
0x5620  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::.ctor()
0x5625  stsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x562a  leave.s  loc_5636
0x562c  ldloc.1
0x562d  brfalse.s loc_5635
0x562f  ldloc.0
0x5630  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5635  endfinally
0x5636  volatile.
0x5638  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) object Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalledLock
0x563d  stloc.0
0x563e  ldc.i4.0
0x563f  stloc.1
0x5640  ldloc.0
0x5641  ldloca.s 1
0x5643  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x5648  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x564d  ldarg.1
0x564e  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::ContainsKey(var<u1>)
0x5653  brtrue.s loc_5679
0x5655  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.AutoReimpersonator::.ctor()
0x565a  stloc.2
0x565b  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x5660  ldarg.1
0x5661  ldarg.0
0x5662  ldarg.1
0x5663  call     instance bool Microsoft.Crm.Reporting.ReportServer::IsDataConnectorInstalled(valuetype Microsoft.Crm.Reporting.DataProviderType dataProviderType)
0x5668  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::set_Item(var<u1>, !!T0)
0x566d  leave.s  loc_5685
0x566f  ldloc.2
0x5670  brfalse.s loc_5678
0x5672  ldloc.2
0x5673  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5678  endfinally
0x5679  leave.s  loc_5685
0x567b  ldloc.1
0x567c  brfalse.s loc_5684
0x567e  ldloc.0
0x567f  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x5684  endfinally
0x5685  ldsfld   class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool> Microsoft.Crm.Reporting.RuntimeReportServer::_isDataConnectorInstalled
0x568a  ldarg.1
0x568b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<valuetype Microsoft.Crm.Reporting.DataProviderType, bool>::get_Item(void)
0x5690  ret
```
