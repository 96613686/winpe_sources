# Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSqmForSeriesandChartType

- ea: `0x7d60`
- end: `0x8067`
- name: `Microsoft.Crm.Asynchronous.SqmDatabaseAccessor::CollectSqmForSeriesandChartType`
- size: `775`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x7cf0`

## callees

- `0x7d60`
- `0xe0d0`

## pseudocode

```c

```

## disassembly

```asm
0x7d60  ldarg.2
0x7d61  ldstr    aChartSeriesSer// "Chart/Series/Series"
0x7d66  callvirt instance class [System.Xml]System.Xml.XmlNodeList [System.Xml]System.Xml.XmlNode::SelectNodes(string)
0x7d6b  stloc.0
0x7d6c  ldarg.3
0x7d6d  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x7d72  ldc.i4.1
0x7d73  bgt.s    loc_7DE4
0x7d75  ldloc.0
0x7d76  callvirt instance int32 [System.Xml]System.Xml.XmlNodeList::get_Count()
0x7d7b  stloc.1
0x7d7c  ldloc.1
0x7d7d  ldc.i4.1
0x7d7e  sub
0x7d7f  switch   loc_7D92, loc_7DAE, loc_7DCA
0x7d90  br.s     loc_7DE4
0x7d92  ldarg.1
0x7d93  dup
0x7d94  ldc.i4   0x1FD
0x7d99  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7d9e  stloc.2
0x7d9f  ldc.i4   0x1FD
0x7da4  ldloc.2
0x7da5  ldc.i4.1
0x7da6  add
0x7da7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7dac  br.s     loc_7DE4
0x7dae  ldarg.1
0x7daf  dup
0x7db0  ldc.i4   0x1FE
0x7db5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7dba  stloc.2
0x7dbb  ldc.i4   0x1FE
0x7dc0  ldloc.2
0x7dc1  ldc.i4.1
0x7dc2  add
0x7dc3  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7dc8  br.s     loc_7DE4
0x7dca  ldarg.1
0x7dcb  dup
0x7dcc  ldc.i4   0x1FF
0x7dd1  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7dd6  stloc.2
0x7dd7  ldc.i4   0x1FF
0x7ddc  ldloc.2
0x7ddd  ldc.i4.1
0x7dde  add
0x7ddf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7de4  ldloc.0
0x7de5  callvirt instance class [mscorlib]System.Collections.IEnumerator [System.Xml]System.Xml.XmlNodeList::GetEnumerator()
0x7dea  stloc.3
0x7deb  br       loc_803B
0x7df0  ldloc.3
0x7df1  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x7df6  castclass [System.Xml]System.Xml.XmlNode
0x7dfb  callvirt instance class [System.Xml]System.Xml.XmlAttributeCollection [System.Xml]System.Xml.XmlNode::get_Attributes()
0x7e00  ldstr    aCharttype// "ChartType"
0x7e05  callvirt instance class [System.Xml]System.Xml.XmlAttribute [System.Xml]System.Xml.XmlAttributeCollection::get_ItemOf(string)
0x7e0a  stloc.s  4
0x7e0c  ldloc.s  4
0x7e0e  brtrue.s loc_7E2F
0x7e10  ldarg.1
0x7e11  dup
0x7e12  ldc.i4   0x203
0x7e17  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7e1c  stloc.2
0x7e1d  ldc.i4   0x203
0x7e22  ldloc.2
0x7e23  ldc.i4.1
0x7e24  add
0x7e25  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7e2a  br       loc_803B
0x7e2f  ldloc.s  4
0x7e31  callvirt instance string [System.Xml]System.Xml.XmlNode::get_Value()
0x7e36  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x7e3b  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x7e40  stloc.s  5
0x7e42  ldloc.s  5
0x7e44  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x7e49  stloc.s  6
0x7e4b  ldloc.s  6
0x7e4d  ldc.i4   0x41E72127
0x7e52  bgt.un.s loc_7E97
0x7e54  ldloc.s  6
0x7e56  ldc.i4   0x152E7967
0x7e5b  bgt.un.s loc_7E7A
0x7e5d  ldloc.s  6
0x7e5f  ldc.i4   0xF41A814
0x7e64  beq      loc_7F46
0x7e69  ldloc.s  6
0x7e6b  ldc.i4   0x152E7967
0x7e70  beq      loc_7F7F
0x7e75  br       loc_8021
0x7e7a  ldloc.s  6
0x7e7c  ldc.i4   0x391A09B9
0x7e81  beq      loc_7F6C
0x7e86  ldloc.s  6
0x7e88  ldc.i4   0x41E72127
0x7e8d  beq      loc_7F30
0x7e92  br       loc_8021
0x7e97  ldloc.s  6
0x7e99  ldc.i4   0x888CF092
0x7e9e  bgt.un.s loc_7EBA
0x7ea0  ldloc.s  6
0x7ea2  ldc.i4   0x57954757
0x7ea7  beq      loc_7F59
0x7eac  ldloc.s  6
0x7eae  ldc.i4   0x888CF092
0x7eb3  beq.s    loc_7F1A
0x7eb5  br       loc_8021
0x7eba  ldloc.s  6
0x7ebc  ldc.i4   0xBB6E2C7A
0x7ec1  beq.s    loc_7EEE
0x7ec3  ldloc.s  6
0x7ec5  ldc.i4   0xC08050A7
0x7eca  beq.s    loc_7F04
0x7ecc  ldloc.s  6
0x7ece  ldc.i4   0xEEF812D5
0x7ed3  bne.un   loc_8021
0x7ed8  ldloc.s  5
0x7eda  ldstr    aPie// "PIE"
0x7edf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7ee4  brtrue   loc_7F92
0x7ee9  br       loc_8021
0x7eee  ldloc.s  5
0x7ef0  ldstr    aBar// "BAR"
0x7ef5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7efa  brtrue   loc_7FB1
0x7eff  br       loc_8021
0x7f04  ldloc.s  5
0x7f06  ldstr    aStackedbar// "STACKEDBAR"
0x7f0b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f10  brtrue   loc_7FB1
0x7f15  br       loc_8021
0x7f1a  ldloc.s  5
0x7f1c  ldstr    aStackedbar100// "STACKEDBAR100"
0x7f21  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f26  brtrue   loc_7FB1
0x7f2b  br       loc_8021
0x7f30  ldloc.s  5
0x7f32  ldstr    aColumn// "COLUMN"
0x7f37  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f3c  brtrue   loc_7FCD
0x7f41  br       loc_8021
0x7f46  ldloc.s  5
0x7f48  ldstr    aStackedcolumn// "STACKEDCOLUMN"
0x7f4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f52  brtrue.s loc_7FCD
0x7f54  br       loc_8021
0x7f59  ldloc.s  5
0x7f5b  ldstr    aStackedcolumn1// "STACKEDCOLUMN100"
0x7f60  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f65  brtrue.s loc_7FCD
0x7f67  br       loc_8021
0x7f6c  ldloc.s  5
0x7f6e  ldstr    aFunnel// "FUNNEL"
0x7f73  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f78  brtrue.s loc_7FE9
0x7f7a  br       loc_8021
0x7f7f  ldloc.s  5
0x7f81  ldstr    aLine// "LINE"
0x7f86  call     bool [mscorlib]System.String::op_Equality(string, string)
0x7f8b  brtrue.s loc_8005
0x7f8d  br       loc_8021
0x7f92  ldarg.1
0x7f93  dup
0x7f94  ldc.i4   0x206
0x7f99  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7f9e  stloc.2
0x7f9f  ldc.i4   0x206
0x7fa4  ldloc.2
0x7fa5  ldc.i4.1
0x7fa6  add
0x7fa7  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7fac  br       loc_803B
0x7fb1  ldarg.1
0x7fb2  dup
0x7fb3  ldc.i4   0x202
0x7fb8  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7fbd  stloc.2
0x7fbe  ldc.i4   0x202
0x7fc3  ldloc.2
0x7fc4  ldc.i4.1
0x7fc5  add
0x7fc6  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7fcb  br.s     loc_803B
0x7fcd  ldarg.1
0x7fce  dup
0x7fcf  ldc.i4   0x203
0x7fd4  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7fd9  stloc.2
0x7fda  ldc.i4   0x203
0x7fdf  ldloc.2
0x7fe0  ldc.i4.1
0x7fe1  add
0x7fe2  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x7fe7  br.s     loc_803B
0x7fe9  ldarg.1
0x7fea  dup
0x7feb  ldc.i4   0x205
0x7ff0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x7ff5  stloc.2
0x7ff6  ldc.i4   0x205
0x7ffb  ldloc.2
0x7ffc  ldc.i4.1
0x7ffd  add
0x7ffe  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x8003  br.s     loc_803B
0x8005  ldarg.1
0x8006  dup
0x8007  ldc.i4   0x204
0x800c  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x8011  stloc.2
0x8012  ldc.i4   0x204
0x8017  ldloc.2
0x8018  ldc.i4.1
0x8019  add
0x801a  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x801f  br.s     loc_803B
0x8021  ldarg.1
0x8022  dup
0x8023  ldc.i4   0x20F
0x8028  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::get_Item(void)
0x802d  stloc.2
0x802e  ldc.i4   0x20F
0x8033  ldloc.2
0x8034  ldc.i4.1
0x8035  add
0x8036  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<valuetype [Microsoft.Crm]Microsoft.Crm.SqmDataPointId, int32>::set_Item(var<u1>, !!T0)
0x803b  ldloc.3
0x803c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x8041  brtrue   loc_7DF0
0x8046  leave.s  loc_8066
0x8048  ldloc.3
0x8049  isinst   [mscorlib]System.IDisposable
0x804e  stloc.s  7
0x8050  ldloc.s  7
0x8052  brfalse.s loc_805B
0x8054  ldloc.s  7
0x8056  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x805b  endfinally
0x805c  ldloc.0
0x805d  brfalse.s loc_8065
0x805f  ldloc.0
0x8060  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x8065  endfinally
0x8066  ret
```
