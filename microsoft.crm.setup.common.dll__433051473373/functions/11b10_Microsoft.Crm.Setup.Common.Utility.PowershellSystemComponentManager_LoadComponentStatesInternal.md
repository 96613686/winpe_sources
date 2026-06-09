# Microsoft.Crm.Setup.Common.Utility.PowershellSystemComponentManager::LoadComponentStatesInternal

- ea: `0x11b10`
- end: `0x11c6a`
- name: `Microsoft.Crm.Setup.Common.Utility.PowershellSystemComponentManager::LoadComponentStatesInternal`
- size: `346`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callees

- `0x116e0`
- `0x11b10`
- `0x11e20`
- `0x11e30`
- `0x11e50`
- `0x11e70`
- `0x11e90`
- `0x11eb0`
- `0x11ed0`
- `0x11f00`

## string_xrefs

- `0x11b16`: `LoadComponentStatesInternal`
- `0x11c59`: `LoadComponentStatesInternal`
- `0x11b26`: `import-module servermanager;$featureList = new-object system.collections.generic.list['system.tuple[string,string,bool,string, int]'];get-windowsfeature | foreach { $featureList.Add((new-object 'system.tuple[string,string,bool,string, int]'($_.Name,$_.DisplayName,$_.Installed,$_.Parent,[int]$_.InstallState))) };`

## pseudocode

```c

```

## disassembly

```asm
0x11b10  ldarg.0
0x11b11  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11b16  ldstr    aLoadcomponents// "LoadComponentStatesInternal"
0x11b1b  ldc.i4.0
0x11b1c  newarr   [mscorlib]System.Object
0x11b21  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodEntry(class [mscorlib]System.Type, string, object[])
0x11b26  ldstr    aImportModuleSe// "import-module servermanager;$featureLis"...
0x11b2b  stloc.0
0x11b2c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`5<string, string, bool, string, int32>>::.ctor()
0x11b31  stloc.1
0x11b32  newobj   instance void [Microsoft.Crm.SystemManagement]Microsoft.Crm.SystemManagement.PowerShellExecutionHelper::.ctor()
0x11b37  stloc.2
0x11b38  ldloc.2
0x11b39  ldloc.0
0x11b3a  callvirt instance void [Microsoft.Crm.SystemManagement]Microsoft.Crm.SystemManagement.PowerShellExecutionHelper::SetScriptToExecute(string)
0x11b3f  ldloc.2
0x11b40  callvirt instance void [Microsoft.Crm.SystemManagement]Microsoft.Crm.SystemManagement.PowerShellExecutionHelper::Execute()
0x11b45  ldloc.2
0x11b46  ldstr    aFeaturelist// "featureList"
0x11b4b  callvirt instance object [Microsoft.Crm.SystemManagement]Microsoft.Crm.SystemManagement.PowerShellExecutionHelper::GetSessionVariable(string)
0x11b50  castclass [System.Management.Automation]System.Management.Automation.PSObject
0x11b55  callvirt instance object [System.Management.Automation]System.Management.Automation.PSObject::get_ImmediateBaseObject()
0x11b5a  castclass class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`5<string, string, bool, string, int32>>
0x11b5f  stloc.1
0x11b60  leave.s  loc_11B6C
0x11b62  ldloc.2
0x11b63  brfalse.s loc_11B6B
0x11b65  ldloc.2
0x11b66  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11b6b  endfinally
0x11b6c  ldloc.1
0x11b6d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class [mscorlib]System.Tuple`5<string, string, bool, string, int32>>::GetEnumerator()
0x11b72  stloc.3
0x11b73  br       loc_11C37
0x11b78  ldloca.s 3
0x11b7a  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`5<string, string, bool, string, int32>>::get_Current()
0x11b7f  stloc.s  4
0x11b81  newobj   instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::.ctor()
0x11b86  stloc.s  5
0x11b88  ldloc.s  5
0x11b8a  ldloc.s  4
0x11b8c  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item1()
0x11b91  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Name(string value)
0x11b96  ldloc.s  5
0x11b98  ldloc.s  4
0x11b9a  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item2()
0x11b9f  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_DisplayName(string value)
0x11ba4  ldloc.s  5
0x11ba6  ldloc.s  4
0x11ba8  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item3()
0x11bad  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Installed(bool value)
0x11bb2  ldloc.s  5
0x11bb4  ldc.i4.0
0x11bb5  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_PendingReboot(bool value)
0x11bba  ldloc.s  5
0x11bbc  ldc.i4.0
0x11bbd  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Removed(bool value)
0x11bc2  ldloc.s  4
0x11bc4  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item5()
0x11bc9  ldc.i4.3
0x11bca  bne.un.s loc_11BD6
0x11bcc  ldloc.s  5
0x11bce  ldc.i4.1
0x11bcf  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_PendingReboot(bool value)
0x11bd4  br.s     loc_11BE8
0x11bd6  ldloc.s  4
0x11bd8  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item5()
0x11bdd  ldc.i4.5
0x11bde  bne.un.s loc_11BE8
0x11be0  ldloc.s  5
0x11be2  ldc.i4.1
0x11be3  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Removed(bool value)
0x11be8  ldloc.s  4
0x11bea  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item4()
0x11bef  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x11bf4  brtrue.s loc_11C23
0x11bf6  ldarg.0
0x11bf7  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x11bfc  ldloc.s  4
0x11bfe  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item4()
0x11c03  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor>::ContainsKey(var<u1>)
0x11c08  brfalse.s loc_11C23
0x11c0a  ldloc.s  5
0x11c0c  ldarg.0
0x11c0d  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x11c12  ldloc.s  4
0x11c14  callvirt instance var<u1> class [mscorlib]System.Tuple`5<string, string, bool, string, int32>::get_Item4()
0x11c19  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor>::get_Item(void)
0x11c1e  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Parent(class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor value)
0x11c23  ldarg.0
0x11c24  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x11c29  ldloc.s  5
0x11c2b  callvirt instance string Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::get_Name()
0x11c30  ldloc.s  5
0x11c32  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor>::set_Item(var<u1>, !!T0)
0x11c37  ldloca.s 3
0x11c39  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`5<string, string, bool, string, int32>>::MoveNext()
0x11c3e  brtrue   loc_11B78
0x11c43  leave.s  loc_11C53
0x11c45  ldloca.s 3
0x11c47  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class [mscorlib]System.Tuple`5<string, string, bool, string, int32>>
0x11c4d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11c52  endfinally
0x11c53  ldarg.0
0x11c54  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x11c59  ldstr    aLoadcomponents// "LoadComponentStatesInternal"
0x11c5e  ldc.i4.0
0x11c5f  newarr   [mscorlib]System.Object
0x11c64  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodExit(class [mscorlib]System.Type, string, object[])
0x11c69  ret
```
