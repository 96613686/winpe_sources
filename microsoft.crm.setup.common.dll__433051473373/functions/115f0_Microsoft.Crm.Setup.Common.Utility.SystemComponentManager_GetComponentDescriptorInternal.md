# Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::GetComponentDescriptorInternal

- ea: `0x115f0`
- end: `0x11620`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::GetComponentDescriptorInternal`
- size: `48`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11350`
- `0x113e0`
- `0x11620`

## callees

- `0x115f0`
- `0x116e0`

## string_xrefs

- `0x1160a`: `Specified component {0} not found in SystemComponentMap`

## pseudocode

```c

```

## disassembly

```asm
0x115f0  ldnull
0x115f1  stloc.0
0x115f2  ldarg.1
0x115f3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x115f8  brtrue.s loc_1161E
0x115fa  ldarg.0
0x115fb  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x11600  ldarg.1
0x11601  ldloca.s 0
0x11603  callvirt instance bool class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor>::TryGetValue(var<u1>, !!T0)
0x11608  brtrue.s loc_1161E
0x1160a  ldstr    aSpecifiedCompo// "Specified component {0} not found in Sy"...
0x1160f  ldc.i4.1
0x11610  newarr   [mscorlib]System.Object
0x11615  dup
0x11616  ldc.i4.0
0x11617  ldarg.1
0x11618  stelem.ref
0x11619  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfoFormat(string, object[])
0x1161e  ldloc.0
0x1161f  ret
```
