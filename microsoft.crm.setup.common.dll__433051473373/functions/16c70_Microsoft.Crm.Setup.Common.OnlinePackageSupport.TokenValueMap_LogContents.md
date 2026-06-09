# Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap::LogContents

- ea: `0x16c70`
- end: `0x16cfa`
- name: `Microsoft.Crm.Setup.Common.OnlinePackageSupport.TokenValueMap::LogContents`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x15250`

## callees

- `0x16c70`

## string_xrefs

- `0x16c77`: `Token-value mapping:`

## pseudocode

```c

```

## disassembly

```asm
0x16c70  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x16c75  stloc.0
0x16c76  ldloc.0
0x16c77  ldstr    aTokenValueMapp// "Token-value mapping:"
0x16c7c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendLine(string)
0x16c81  pop
0x16c82  ldarg.0
0x16c83  call     instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x16c88  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__3_0
0x16c8d  dup
0x16c8e  brtrue.s loc_16CA7
0x16c90  pop
0x16c91  ldsfld   class <>c <>c::<>9
0x16c96  ldftn    instance string <>c::<LogContents>b__3_0(string k)
0x16c9c  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x16ca1  dup
0x16ca2  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__3_0
0x16ca7  call     T0x2B000021
0x16cac  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x16cb1  stloc.1
0x16cb2  br.s     loc_16CD4
0x16cb4  ldloc.1
0x16cb5  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x16cba  stloc.2
0x16cbb  ldloc.0
0x16cbc  ldstr    a012// "        {0}: {1}{2}"
0x16cc1  ldloc.2
0x16cc2  ldarg.0
0x16cc3  ldloc.2
0x16cc4  call     instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Item(void)
0x16cc9  call     string [mscorlib]System.Environment::get_NewLine()
0x16cce  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object, object, object)
0x16cd3  pop
0x16cd4  ldloc.1
0x16cd5  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x16cda  brtrue.s loc_16CB4
0x16cdc  leave.s  loc_16CE8
0x16cde  ldloc.1
0x16cdf  brfalse.s loc_16CE7
0x16ce1  ldloc.1
0x16ce2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x16ce7  endfinally
0x16ce8  ldloc.0
0x16ce9  callvirt instance string [mscorlib]System.Object::ToString()
0x16cee  ldc.i4.0
0x16cef  newarr   [mscorlib]System.Object
0x16cf4  call     void [Microsoft.Crm.Core]Microsoft.Crm.Tools.Logging.Logger::WriteInfo(string, object[])
0x16cf9  ret
```
