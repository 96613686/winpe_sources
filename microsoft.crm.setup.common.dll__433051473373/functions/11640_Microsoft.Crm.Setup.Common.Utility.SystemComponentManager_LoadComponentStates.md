# Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::LoadComponentStates

- ea: `0x11640`
- end: `0x11693`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::LoadComponentStates`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callees

- `0x11640`
- `0x116a0`
- `0x116e0`
- `0x11700`
- `0x11720`
- `0x11740`

## pseudocode

```c

```

## disassembly

```asm
0x11640  ldarg.0
0x11641  ldnull
0x11642  call     instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::set_ExceptionThrownDuringComponentLoad(class [mscorlib]System.Exception value)
0x11647  ldarg.0
0x11648  ldc.i4.1
0x11649  call     instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::set_LoadingComponentStates(bool value)
0x1164e  ldarg.0
0x1164f  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x11654  stloc.0
0x11655  ldc.i4.0
0x11656  stloc.1
0x11657  ldloc.0
0x11658  ldloca.s 1
0x1165a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1165f  ldarg.0
0x11660  ldarg.1
0x11661  isinst   class [mscorlib]System.Collections.Generic.IEnumerable`1<string>
0x11666  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::LoadComponentStatesInternal(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> systemComponentNames)
0x1166b  ldarg.0
0x1166c  ldc.i4.1
0x1166d  call     instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::set_ComponentStatesLoaded(bool value)
0x11672  leave.s  loc_1167E
0x11674  ldloc.1
0x11675  brfalse.s loc_1167D
0x11677  ldloc.0
0x11678  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1167d  endfinally
0x1167e  leave.s  loc_11692
0x11680  stloc.2
0x11681  ldarg.0
0x11682  ldloc.2
0x11683  call     instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::set_ExceptionThrownDuringComponentLoad(class [mscorlib]System.Exception value)
0x11688  leave.s  loc_11692
0x1168a  ldarg.0
0x1168b  ldc.i4.0
0x1168c  call     instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::set_LoadingComponentStates(bool value)
0x11691  endfinally
0x11692  ret
```
