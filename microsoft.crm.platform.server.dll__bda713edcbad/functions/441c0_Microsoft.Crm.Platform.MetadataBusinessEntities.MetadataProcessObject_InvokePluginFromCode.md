# Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::InvokePluginFromCode

- ea: `0x441c0`
- end: `0x441fd`
- name: `Microsoft.Crm.Platform.MetadataBusinessEntities.MetadataProcessObject::InvokePluginFromCode`
- size: `61`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x435d0`
- `0x43650`
- `0x44150`

## string_xrefs

- `0x441ca`: `Microsoft.Crm.AuditMetadataPlugin`
- `0x441d4`: `InvokePluginFromCode`

## pseudocode

```c

```

## disassembly

```asm
0x441c0  ldstr    aMicrosoftCrmAu// "Microsoft.Crm.Audit"
0x441c5  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::Load(string)
0x441ca  ldstr    aMicrosoftCrmAu_0// "Microsoft.Crm.AuditMetadataPlugin"
0x441cf  callvirt instance class [mscorlib]System.Type [mscorlib]System.Reflection.Assembly::GetType(string)
0x441d4  ldstr    aInvokepluginfr// "InvokePluginFromCode"
0x441d9  callvirt instance class [mscorlib]System.Reflection.MethodInfo [mscorlib]System.Type::GetMethod(string)
0x441de  ldnull
0x441df  ldc.i4.4
0x441e0  newarr   [mscorlib]System.Object
0x441e5  dup
0x441e6  ldc.i4.0
0x441e7  ldarg.1
0x441e8  stelem.ref
0x441e9  dup
0x441ea  ldc.i4.1
0x441eb  ldarg.2
0x441ec  stelem.ref
0x441ed  dup
0x441ee  ldc.i4.2
0x441ef  ldarg.3
0x441f0  stelem.ref
0x441f1  dup
0x441f2  ldc.i4.3
0x441f3  ldarg.s  4
0x441f5  stelem.ref
0x441f6  callvirt instance object [mscorlib]System.Reflection.MethodBase::Invoke(object, object[])
0x441fb  pop
0x441fc  ret
```
