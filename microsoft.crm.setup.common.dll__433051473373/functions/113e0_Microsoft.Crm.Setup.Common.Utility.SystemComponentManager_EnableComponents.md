# Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::EnableComponents

- ea: `0x113e0`
- end: `0x114ce`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::EnableComponents`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callees

- `0x113e0`
- `0x115d0`
- `0x115f0`
- `0x116b0`
- `0x116e0`
- `0x11e20`
- `0x11e60`
- `0x11e70`

## string_xrefs

- `0x113e6`: `EnableComponents`
- `0x114bd`: `EnableComponents`

## pseudocode

```c

```

## disassembly

```asm
0x113e0  ldarg.0
0x113e1  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x113e6  ldstr    aEnablecomponen// "EnableComponents"
0x113eb  ldc.i4.0
0x113ec  newarr   [mscorlib]System.Object
0x113f1  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodEntry(class [mscorlib]System.Type, string, object[])
0x113f6  ldarg.0
0x113f7  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x113fc  stloc.0
0x113fd  ldc.i4.0
0x113fe  stloc.1
0x113ff  ldloc.0
0x11400  ldloca.s 1
0x11402  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x11407  ldarg.0
0x11408  call     instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::ThrowComponentStateLoadExceptionIfNecessary()
0x1140d  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x11412  stloc.2
0x11413  ldarg.1
0x11414  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x11419  stloc.3
0x1141a  br.s     loc_11448
0x1141c  ldloc.3
0x1141d  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x11422  stloc.s  4
0x11424  ldarg.0
0x11425  ldloc.s  4
0x11427  call     instance class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::GetComponentDescriptorInternal(string componentName)
0x1142c  stloc.s  5
0x1142e  ldloc.s  5
0x11430  brfalse.s loc_11448
0x11432  ldloc.s  5
0x11434  callvirt instance bool Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::get_Installed()
0x11439  brtrue.s loc_11448
0x1143b  ldloc.2
0x1143c  ldloc.s  5
0x1143e  callvirt instance string Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::get_Name()
0x11443  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x11448  ldloc.3
0x11449  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1144e  brtrue.s loc_1141C
0x11450  leave.s  loc_1145C
0x11452  ldloc.3
0x11453  brfalse.s loc_1145B
0x11455  ldloc.3
0x11456  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1145b  endfinally
0x1145c  ldloc.2
0x1145d  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<string>::get_Count()
0x11462  ldc.i4.0
0x11463  ble.s    loc_114AB
0x11465  ldarg.0
0x11466  ldloc.2
0x11467  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::EnableComponentsInternal(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> requiredComponents)
0x1146c  ldloc.2
0x1146d  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x11472  stloc.s  6
0x11474  br.s     loc_11492
0x11476  ldloca.s 6
0x11478  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x1147d  stloc.s  7
0x1147f  ldarg.0
0x11480  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::_systemComponentMap
0x11485  ldloc.s  7
0x11487  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor>::get_Item(void)
0x1148c  ldc.i4.1
0x1148d  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Installed(bool value)
0x11492  ldloca.s 6
0x11494  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x11499  brtrue.s loc_11476
0x1149b  leave.s  loc_114B7
0x1149d  ldloca.s 6
0x1149f  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x114a5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x114aa  endfinally
0x114ab  leave.s  loc_114B7
0x114ad  ldloc.1
0x114ae  brfalse.s loc_114B6
0x114b0  ldloc.0
0x114b1  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x114b6  endfinally
0x114b7  ldarg.0
0x114b8  call     instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x114bd  ldstr    aEnablecomponen// "EnableComponents"
0x114c2  ldc.i4.0
0x114c3  newarr   [mscorlib]System.Object
0x114c8  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteMethodExit(class [mscorlib]System.Type, string, object[])
0x114cd  ret
```
