# Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::GetAllowedTenantAndClientIds

- ea: `0x6f0`
- end: `0x78e`
- name: `Microsoft.Crm.ScaleGroupApi.AzureApplicationInfo::GetAllowedTenantAndClientIds`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x510`

## callees

- `0x6f0`

## pseudocode

```c

```

## disassembly

```asm
0x6f0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x6f5  stloc.0
0x6f6  ldarg.0
0x6f7  brfalse  loc_78C
0x6fc  ldarg.0
0x6fd  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x702  brtrue   loc_78C
0x707  ldarg.0
0x708  ldc.i4.1
0x709  newarr   [mscorlib]System.Char
0x70e  dup
0x70f  ldc.i4.0
0x710  ldc.i4.s 0x2C
0x712  stelem.i2
0x713  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x718  ldsfld   class [mscorlib]System.Func`2<string, class <>f__AnonymousType2`2<string, string>> <>c::<>9__29_0
0x71d  dup
0x71e  brtrue.s loc_737
0x720  pop
0x721  ldsfld   class <>c <>c::<>9
0x726  ldftn    instance class <>f__AnonymousType2`2<string, string> <>c::<GetAllowedTenantAndClientIds>b__29_0(string clientAndTenantId)
0x72c  newobj   instance void class [mscorlib]System.Func`2<string, class <>f__AnonymousType2`2<string, string>>::.ctor(object, native int)
0x731  dup
0x732  stsfld   class [mscorlib]System.Func`2<string, class <>f__AnonymousType2`2<string, string>> <>c::<>9__29_0
0x737  call     T0x2B000001
0x73c  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType2`2<string, string>, bool> <>c::<>9__29_1
0x741  dup
0x742  brtrue.s loc_75B
0x744  pop
0x745  ldsfld   class <>c <>c::<>9
0x74a  ldftn    instance bool <>c::<GetAllowedTenantAndClientIds>b__29_1(class <>f__AnonymousType2`2<string, string> <>h__TransparentIdentifier0)
0x750  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType2`2<string, string>, bool>::.ctor(object, native int)
0x755  dup
0x756  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType2`2<string, string>, bool> <>c::<>9__29_1
0x75b  call     T0x2B000002
0x760  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType2`2<string, string>, string> <>c::<>9__29_2
0x765  dup
0x766  brtrue.s loc_77F
0x768  pop
0x769  ldsfld   class <>c <>c::<>9
0x76e  ldftn    instance string <>c::<GetAllowedTenantAndClientIds>b__29_2(class <>f__AnonymousType2`2<string, string> <>h__TransparentIdentifier0)
0x774  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType2`2<string, string>, string>::.ctor(object, native int)
0x779  dup
0x77a  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType2`2<string, string>, string> <>c::<>9__29_2
0x77f  call     T0x2B000003
0x784  stloc.1
0x785  ldloc.0
0x786  ldloc.1
0x787  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::AddRange(class [mscorlib]System.Collections.Generic.IEnumerable`1<var<u1>>)
0x78c  ldloc.0
0x78d  ret
```
