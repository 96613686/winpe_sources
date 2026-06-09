# Microsoft.Crm.CrmPluginAssemblyMetadata::ProcessType

- ea: `0x1e050`
- end: `0x1e13e`
- name: `Microsoft.Crm.CrmPluginAssemblyMetadata::ProcessType`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1df20`
- `0x1e160`
- `0x1e4f0`

## callees

- `0x1e020`
- `0x1e030`
- `0x1e050`
- `0x1e140`
- `0x1e160`
- `0x1e4f0`

## string_xrefs

- `0x1e057`: `ProcessType: token: {0}`
- `0x1e10f`: `ProcessType: ignoring token type: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1e050  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e055  ldc.i4.s 0x14
0x1e057  ldstr    aProcesstypeTok// "ProcessType: token: {0}"
0x1e05c  ldc.i4.1
0x1e05d  newarr   [mscorlib]System.Object
0x1e062  dup
0x1e063  ldc.i4.0
0x1e064  ldarg.0
0x1e065  ldarg.1
0x1e066  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::Hex(unsigned int32 value)
0x1e06b  stelem.ref
0x1e06c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e071  ldarg.1
0x1e072  call     bool Microsoft.Crm.CrmPluginAssemblyMetadata::IsNullToken(unsigned int32 token)
0x1e077  brfalse.s loc_1E07B
0x1e079  ldnull
0x1e07a  ret
0x1e07b  ldnull
0x1e07c  stloc.0
0x1e07d  ldarg.0
0x1e07e  ldarg.0
0x1e07f  ldfld    int32 Microsoft.Crm.CrmPluginAssemblyMetadata::_recursionCount
0x1e084  stloc.1
0x1e085  ldloc.1
0x1e086  ldc.i4.1
0x1e087  add
0x1e088  stfld    int32 Microsoft.Crm.CrmPluginAssemblyMetadata::_recursionCount
0x1e08d  ldloc.1
0x1e08e  conv.i8
0x1e08f  ldc.i4.s 0x64
0x1e091  conv.i8
0x1e092  ble.s    loc_1E0BD
0x1e094  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e099  ldc.i4.s 0x14
0x1e09b  ldstr    aProcesstypeRec// "ProcessType: recursion count exceeded: "...
0x1e0a0  ldc.i4.1
0x1e0a1  newarr   [mscorlib]System.Object
0x1e0a6  dup
0x1e0a7  ldc.i4.0
0x1e0a8  ldarg.0
0x1e0a9  ldfld    int32 Microsoft.Crm.CrmPluginAssemblyMetadata::_recursionCount
0x1e0ae  box      [mscorlib]System.Int32
0x1e0b3  stelem.ref
0x1e0b4  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceWarning(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e0b9  ldnull
0x1e0ba  stloc.2
0x1e0bb  leave.s  loc_1E13C
0x1e0bd  ldarg.0
0x1e0be  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedTypes
0x1e0c3  ldarg.1
0x1e0c4  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata>::ContainsKey(var<u1>)
0x1e0c9  brfalse.s loc_1E0DA
0x1e0cb  ldarg.0
0x1e0cc  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata> Microsoft.Crm.CrmPluginAssemblyMetadata::_processedTypes
0x1e0d1  ldarg.1
0x1e0d2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<unsigned int32, class Microsoft.Crm.CrmPluginTypeMetadata>::get_Item(void)
0x1e0d7  stloc.2
0x1e0d8  leave.s  loc_1E13C
0x1e0da  ldarg.1
0x1e0db  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1e0e0  ldc.i4   0x2000000
0x1e0e5  bne.un.s loc_1E0F1
0x1e0e7  ldarg.0
0x1e0e8  ldarg.1
0x1e0e9  call     instance class Microsoft.Crm.CrmPluginTypeMetadata Microsoft.Crm.CrmPluginAssemblyMetadata::ProcessTypeDef(unsigned int32 typeDef)
0x1e0ee  stloc.0
0x1e0ef  br.s     loc_1E129
0x1e0f1  ldarg.1
0x1e0f2  call     valuetype Microsoft.Crm.CorTokenType Microsoft.Crm.CrmPluginAssemblyMetadata::TokenType(unsigned int32 token)
0x1e0f7  ldc.i4   0x1000000
0x1e0fc  bne.un.s loc_1E108
0x1e0fe  ldarg.0
0x1e0ff  ldarg.1
0x1e100  call     instance class Microsoft.Crm.CrmPluginTypeMetadata Microsoft.Crm.CrmPluginAssemblyMetadata::ProcessTypeRef(unsigned int32 typeRef)
0x1e105  stloc.0
0x1e106  br.s     loc_1E129
0x1e108  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x1e10d  ldc.i4.s 0x14
0x1e10f  ldstr    aProcesstypeIgn// "ProcessType: ignoring token type: {0}"
0x1e114  ldc.i4.1
0x1e115  newarr   [mscorlib]System.Object
0x1e11a  dup
0x1e11b  ldc.i4.0
0x1e11c  ldarg.0
0x1e11d  ldarg.1
0x1e11e  call     instance string Microsoft.Crm.CrmPluginAssemblyMetadata::Hex(unsigned int32 value)
0x1e123  stelem.ref
0x1e124  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x1e129  ldloc.0
0x1e12a  stloc.2
0x1e12b  leave.s  loc_1E13C
0x1e12d  ldarg.0
0x1e12e  ldarg.0
0x1e12f  ldfld    int32 Microsoft.Crm.CrmPluginAssemblyMetadata::_recursionCount
0x1e134  ldc.i4.1
0x1e135  sub
0x1e136  stfld    int32 Microsoft.Crm.CrmPluginAssemblyMetadata::_recursionCount
0x1e13b  endfinally
0x1e13c  ldloc.2
0x1e13d  ret
```
