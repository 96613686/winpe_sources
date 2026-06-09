# Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::WillContainerComponentBeActivated

- ea: `0x114d0`
- end: `0x11557`
- name: `Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::WillContainerComponentBeActivated`
- size: `135`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x11350`
- `0x114d0`
- `0x11e60`
- `0x11ee0`

## string_xrefs

- `0x114e8`: `Container component not recognized`

## pseudocode

```c

```

## disassembly

```asm
0x114d0  ldarg.1
0x114d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x114d6  brfalse.s loc_114DA
0x114d8  ldc.i4.0
0x114d9  ret
0x114da  ldc.i4.0
0x114db  stloc.0
0x114dc  ldarg.0
0x114dd  ldarg.1
0x114de  call     instance class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_Item(string componentName)
0x114e3  stloc.1
0x114e4  ldloc.1
0x114e5  ldnull
0x114e6  cgt.un
0x114e8  ldstr    aContainerCompo// "Container component not recognized"
0x114ed  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::Assert(bool, string)
0x114f2  ldloc.1
0x114f3  callvirt instance bool Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::get_Installed()
0x114f8  brfalse.s loc_114FE
0x114fa  ldc.i4.0
0x114fb  stloc.0
0x114fc  br.s     loc_11555
0x114fe  ldarg.2
0x114ff  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x11504  stloc.2
0x11505  br.s     loc_11541
0x11507  ldloc.2
0x11508  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x1150d  stloc.3
0x1150e  ldarg.0
0x1150f  ldloc.3
0x11510  call     instance class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_Item(string componentName)
0x11515  stloc.s  4
0x11517  ldloc.s  4
0x11519  brfalse.s loc_11541
0x1151b  ldloc.s  4
0x1151d  callvirt instance bool Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::get_Installed()
0x11522  brtrue.s loc_11541
0x11524  ldloc.s  4
0x11526  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::get_Ancestors()
0x1152b  ldloc.1
0x1152c  call     T0x2B00000F
0x11531  brtrue.s loc_1153D
0x11533  ldloc.3
0x11534  ldarg.1
0x11535  ldc.i4.5
0x11536  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1153b  brfalse.s loc_11541
0x1153d  ldc.i4.1
0x1153e  stloc.0
0x1153f  leave.s  loc_11555
0x11541  ldloc.2
0x11542  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11547  brtrue.s loc_11507
0x11549  leave.s  loc_11555
0x1154b  ldloc.2
0x1154c  brfalse.s loc_11554
0x1154e  ldloc.2
0x1154f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11554  endfinally
0x11555  ldloc.0
0x11556  ret
```
