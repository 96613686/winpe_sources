# Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::ParseQueryFile

- ea: `0x119d0`
- end: `0x11ae6`
- name: `Microsoft.Crm.Setup.Common.Utility.ServerManagerCommandSystemComponentManager::ParseQueryFile`
- size: `278`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x11790`

## callees

- `0x116e0`
- `0x119d0`
- `0x11e20`
- `0x11e30`
- `0x11e50`
- `0x11e70`
- `0x11e90`
- `0x11eb0`
- `0x11ed0`
- `0x11f00`

## string_xrefs

- `0x11a4f`: `Installed`

## pseudocode

```c

```

## disassembly

```asm
0x119d0  ldarg.1
0x119d1  call     class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XElement::Load(string)
0x119d6  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement> [System.Xml.Linq]System.Xml.Linq.XElement::DescendantsAndSelf()
0x119db  ldsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool> <>c::<>9__7_0
0x119e0  dup
0x119e1  brtrue.s loc_119FA
0x119e3  pop
0x119e4  ldsfld   class <>c <>c::<>9
0x119e9  ldftn    instance bool <>c::<ParseQueryFile>b__7_0(class [System.Xml.Linq]System.Xml.Linq.XElement element)
0x119ef  newobj   instance void class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool>::.ctor(object, native int)
0x119f4  dup
0x119f5  stsfld   class [mscorlib]System.Func`2<class [System.Xml.Linq]System.Xml.Linq.XElement, bool> <>c::<>9__7_0
0x119fa  call     T0x2B000010
0x119ff  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::GetEnumerator()
0x11a04  stloc.0
0x11a05  br       loc_11ACE
0x11a0a  ldloc.0
0x11a0b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [System.Xml.Linq]System.Xml.Linq.XElement>::get_Current()
0x11a10  stloc.1
0x11a11  newobj   instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::.ctor()
0x11a16  stloc.2
0x11a17  ldloc.2
0x11a18  ldloc.1
0x11a19  ldstr    aId// "Id"
0x11a1e  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x11a23  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x11a28  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x11a2d  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Name(string value)
0x11a32  ldloc.2
0x11a33  ldloc.1
0x11a34  ldstr    aDisplayname// "DisplayName"
0x11a39  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x11a3e  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x11a43  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x11a48  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_DisplayName(string value)
0x11a4d  ldloc.2
0x11a4e  ldloc.1
0x11a4f  ldstr    aInstalled// "Installed"
0x11a54  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x11a59  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x11a5e  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x11a63  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11a68  call     bool [mscorlib]System.Convert::ToBoolean(string, class [mscorlib]System.IFormatProvider)
0x11a6d  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Installed(bool value)
0x11a72  ldloc.2
0x11a73  ldc.i4.0
0x11a74  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Removed(bool value)
0x11a79  ldloc.2
0x11a7a  ldc.i4.0
0x11a7b  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_PendingReboot(bool value)
0x11a80  ldloc.1
0x11a81  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XObject::get_Parent()
0x11a86  brfalse.s loc_11ABC
0x11a88  ldloc.1
0x11a89  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XElement [System.Xml.Linq]System.Xml.Linq.XObject::get_Parent()
0x11a8e  ldstr    aId// "Id"
0x11a93  call     class [System.Xml.Linq]System.Xml.Linq.XName [System.Xml.Linq]System.Xml.Linq.XName::op_Implicit(string)
0x11a98  callvirt instance class [System.Xml.Linq]System.Xml.Linq.XAttribute [System.Xml.Linq]System.Xml.Linq.XElement::Attribute(class [System.Xml.Linq]System.Xml.Linq.XName)
0x11a9d  stloc.3
0x11a9e  ldloc.3
0x11a9f  brfalse.s loc_11ABC
0x11aa1  ldloc.3
0x11aa2  callvirt instance string [System.Xml.Linq]System.Xml.Linq.XAttribute::get_Value()
0x11aa7  stloc.s  4
0x11aa9  ldloc.2
0x11aaa  ldarg.0
0x11aab  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x11ab0  ldloc.s  4
0x11ab2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor>::get_Item(void)
0x11ab7  callvirt instance void Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::set_Parent(class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor value)
0x11abc  ldarg.0
0x11abd  call     instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor> Microsoft.Crm.Setup.Common.Utility.SystemComponentManager::get_SystemComponentMap()
0x11ac2  ldloc.2
0x11ac3  callvirt instance string Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor::get_Name()
0x11ac8  ldloc.2
0x11ac9  callvirt instance void class [mscorlib]System.Collections.Generic.IDictionary`2<string, class Microsoft.Crm.Setup.Common.Utility.SystemComponentDescriptor>::set_Item(var<u1>, !!T0)
0x11ace  ldloc.0
0x11acf  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x11ad4  brtrue   loc_11A0A
0x11ad9  leave.s  loc_11AE5
0x11adb  ldloc.0
0x11adc  brfalse.s loc_11AE4
0x11ade  ldloc.0
0x11adf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x11ae4  endfinally
0x11ae5  ret
```
