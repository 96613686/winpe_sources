# Microsoft.Crm.Asynchronous.JobDataAccess::GetPriorityTable

- ea: `0x3930`
- end: `0x3b6d`
- name: `Microsoft.Crm.Asynchronous.JobDataAccess::GetPriorityTable`
- size: `573`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x3290`

## callees

- `0x3930`
- `0x3c50`

## pseudocode

```c

```

## disassembly

```asm
0x3930  ldstr    aInsertIntoPrio// "\r\nINSERT INTO @priorityTable ( \r\n\t"...
0x3935  stloc.0
0x3936  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x393b  ldstr    aAsyncprioritym// "AsyncPriorityMapping"
0x3940  callvirt T0x2B000009
0x3945  stloc.1
0x3946  call     class [Microsoft.Crm.Core]Microsoft.Crm.IDeploymentInfoProvider [Microsoft.Crm.Core]Microsoft.Crm.DeploymentInfoProvider::get_Instance()
0x394b  ldstr    aAsynccapacitym// "AsyncCapacityMapping"
0x3950  callvirt T0x2B000009
0x3955  stloc.2
0x3956  ldloc.1
0x3957  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x395c  brfalse.s loc_3964
0x395e  ldstr    aDefault1// "Default=1;"
0x3963  stloc.1
0x3964  ldloc.2
0x3965  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x396a  brfalse.s loc_3972
0x396c  ldstr    aDefault1// "Default=1;"
0x3971  stloc.2
0x3972  ldloc.1
0x3973  ldsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::prioritySettingCache
0x3978  ldc.i4.5
0x3979  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x397e  brfalse.s loc_3991
0x3980  ldloc.2
0x3981  ldsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::capacitySettingCache
0x3986  ldc.i4.5
0x3987  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x398c  brtrue   loc_3B67
0x3991  ldstr    a1// "1"
0x3996  stloc.3
0x3997  ldloc.1
0x3998  ldarg.0
0x3999  ldftn    instance void Microsoft.Crm.Asynchronous.JobDataAccess::<GetPriorityTable>b__41_0(string x)
0x399f  newobj   instance void class [mscorlib]System.Action`1<string>::.ctor(object, native int)
0x39a4  call     class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Hashtable, string> Microsoft.Crm.Asynchronous.JobDataAccess::GetMappingsAndDefaultFromKeyValuePairs(string keyValuePairs, class [mscorlib]System.Action`1<string> onInvalidInput)
0x39a9  dup
0x39aa  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Hashtable, string>::get_Item1()
0x39af  stloc.s  4
0x39b1  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Hashtable, string>::get_Item2()
0x39b6  dup
0x39b7  brtrue.s loc_39BB
0x39b9  pop
0x39ba  ldloc.3
0x39bb  stloc.3
0x39bc  ldstr    a1// "1"
0x39c1  stloc.s  5
0x39c3  ldloc.2
0x39c4  ldarg.0
0x39c5  ldftn    instance void Microsoft.Crm.Asynchronous.JobDataAccess::<GetPriorityTable>b__41_1(string x)
0x39cb  newobj   instance void class [mscorlib]System.Action`1<string>::.ctor(object, native int)
0x39d0  call     class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Hashtable, string> Microsoft.Crm.Asynchronous.JobDataAccess::GetMappingsAndDefaultFromKeyValuePairs(string keyValuePairs, class [mscorlib]System.Action`1<string> onInvalidInput)
0x39d5  dup
0x39d6  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Hashtable, string>::get_Item1()
0x39db  stloc.s  6
0x39dd  callvirt instance var<u1> class [mscorlib]System.Tuple`2<class [mscorlib]System.Collections.Hashtable, string>::get_Item2()
0x39e2  dup
0x39e3  brtrue.s loc_39E8
0x39e5  pop
0x39e6  ldloc.s  5
0x39e8  stloc.s  5
0x39ea  ldtoken  [Microsoft.Crm.Constants]Microsoft.Crm.AsyncOperationType
0x39ef  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x39f4  call     instance class [mscorlib]System.Reflection.FieldInfo[] [mscorlib]System.Type::GetFields()
0x39f9  stloc.s  7
0x39fb  ldloc.s  7
0x39fd  stloc.s  9
0x39ff  ldc.i4.0
0x3a00  stloc.s  0xA
0x3a02  br.s     loc_3A50
0x3a04  ldloc.s  9
0x3a06  ldloc.s  0xA
0x3a08  ldelem.ref
0x3a09  stloc.s  0xB
0x3a0b  ldloc.s  4
0x3a0d  ldloc.s  0xB
0x3a0f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3a14  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x3a19  brtrue.s loc_3A2A
0x3a1b  ldloc.s  4
0x3a1d  ldloc.s  0xB
0x3a1f  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3a24  ldloc.3
0x3a25  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3a2a  ldloc.s  6
0x3a2c  ldloc.s  0xB
0x3a2e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3a33  callvirt instance bool [mscorlib]System.Collections.Hashtable::Contains(object)
0x3a38  brtrue.s loc_3A4A
0x3a3a  ldloc.s  6
0x3a3c  ldloc.s  0xB
0x3a3e  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3a43  ldloc.s  5
0x3a45  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x3a4a  ldloc.s  0xA
0x3a4c  ldc.i4.1
0x3a4d  add
0x3a4e  stloc.s  0xA
0x3a50  ldloc.s  0xA
0x3a52  ldloc.s  9
0x3a54  ldlen
0x3a55  conv.i4
0x3a56  blt.s    loc_3A04
0x3a58  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x3a5d  stloc.s  8
0x3a5f  ldloc.s  7
0x3a61  stloc.s  9
0x3a63  ldc.i4.0
0x3a64  stloc.s  0xA
0x3a66  br       loc_3B44
0x3a6b  ldloc.s  9
0x3a6d  ldloc.s  0xA
0x3a6f  ldelem.ref
0x3a70  dup
0x3a71  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0x3a76  stloc.s  0xC
0x3a78  ldloc.s  4
0x3a7a  ldloc.s  0xC
0x3a7c  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3a81  brfalse.s loc_3A93
0x3a83  ldloc.s  4
0x3a85  ldloc.s  0xC
0x3a87  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3a8c  castclass [mscorlib]System.String
0x3a91  br.s     loc_3A94
0x3a93  ldloc.3
0x3a94  ldloc.s  6
0x3a96  ldloc.s  0xC
0x3a98  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3a9d  brfalse.s loc_3AAF
0x3a9f  ldloc.s  6
0x3aa1  ldloc.s  0xC
0x3aa3  callvirt instance object [mscorlib]System.Collections.Hashtable::get_Item(object)
0x3aa8  castclass [mscorlib]System.String
0x3aad  br.s     loc_3AB1
0x3aaf  ldloc.s  5
0x3ab1  stloc.s  0xD
0x3ab3  ldc.i4.1
0x3ab4  stloc.s  0xE
0x3ab6  ldc.i4.1
0x3ab7  stloc.s  0xF
0x3ab9  ldloca.s 0x10
0x3abb  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x3ac0  brfalse.s loc_3AC6
0x3ac2  ldloc.s  0x10
0x3ac4  stloc.s  0xE
0x3ac6  ldloc.s  0xD
0x3ac8  ldloca.s 0x11
0x3aca  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x3acf  brfalse.s loc_3AD5
0x3ad1  ldloc.s  0x11
0x3ad3  stloc.s  0xF
0x3ad5  ldnull
0x3ad6  callvirt instance object [mscorlib]System.Reflection.FieldInfo::GetValue(object)
0x3adb  unbox.any [mscorlib]System.Int32
0x3ae0  stloc.s  0x12
0x3ae2  ldloc.s  8
0x3ae4  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x3ae9  brfalse.s loc_3AFA
0x3aeb  ldloc.s  8
0x3aed  ldstr    asc_10D10// ","
0x3af2  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3af7  pop
0x3af8  br.s     loc_3B03
0x3afa  ldloc.s  8
0x3afc  ldloc.0
0x3afd  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x3b02  pop
0x3b03  ldloc.s  8
0x3b05  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x3b0a  ldstr    a012// "\t({0}, {1}, {2})"
0x3b0f  ldc.i4.3
0x3b10  newarr   [mscorlib]System.Object
0x3b15  dup
0x3b16  ldc.i4.0
0x3b17  ldloc.s  0x12
0x3b19  box      [mscorlib]System.Int32
0x3b1e  stelem.ref
0x3b1f  dup
0x3b20  ldc.i4.1
0x3b21  ldloc.s  0xE
0x3b23  box      [mscorlib]System.Int32
0x3b28  stelem.ref
0x3b29  dup
0x3b2a  ldc.i4.2
0x3b2b  ldloc.s  0xF
0x3b2d  box      [mscorlib]System.Int32
0x3b32  stelem.ref
0x3b33  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x3b38  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x3b3d  pop
0x3b3e  ldloc.s  0xA
0x3b40  ldc.i4.1
0x3b41  add
0x3b42  stloc.s  0xA
0x3b44  ldloc.s  0xA
0x3b46  ldloc.s  9
0x3b48  ldlen
0x3b49  conv.i4
0x3b4a  blt      loc_3A6B
0x3b4f  ldloc.1
0x3b50  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::prioritySettingCache
0x3b55  ldloc.2
0x3b56  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::capacitySettingCache
0x3b5b  ldloc.s  8
0x3b5d  callvirt instance string [mscorlib]System.Object::ToString()
0x3b62  stsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::operationTypePriorityMapping
0x3b67  ldsfld   string Microsoft.Crm.Asynchronous.JobDataAccess::operationTypePriorityMapping
0x3b6c  ret
```
