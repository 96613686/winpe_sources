# Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::.ctor_0

- ea: `0x9c660`
- end: `0x9c705`
- name: `Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::.ctor_0`
- size: `165`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x9c230`
- `0x9c3b0`

## callees

- `0x115b0`
- `0x9c5e0`
- `0x9c5f0`
- `0x9c600`
- `0x9c620`
- `0x9c640`
- `0x9c660`

## string_xrefs

- `0x9c681`: `Invalid key string passed to AppFormFilterCacheKey constructor`
- `0x9c6de`: `Invalid key string passed to AppFormFilterCacheKey constructor`

## pseudocode

```c

```

## disassembly

```asm
0x9c660  ldarg.0
0x9c661  call     instance void [mscorlib]System.Object::.ctor()
0x9c666  ldarg.1
0x9c667  ldc.i4.1
0x9c668  newarr   [mscorlib]System.Char
0x9c66d  dup
0x9c66e  ldc.i4.0
0x9c66f  ldc.i4.s 0x2F
0x9c671  stelem.i2
0x9c672  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x9c677  stloc.0
0x9c678  ldloc.0
0x9c679  ldlen
0x9c67a  conv.i4
0x9c67b  ldc.i4.2
0x9c67c  clt
0x9c67e  ldc.i4.0
0x9c67f  ceq
0x9c681  ldstr    aInvalidKeyStri_2// "Invalid key string passed to AppFormFil"...
0x9c686  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x9c68b  ldarg.0
0x9c68c  ldloc.0
0x9c68d  ldc.i4.0
0x9c68e  ldelem.ref
0x9c68f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9c694  call     int32 [mscorlib]System.Int32::Parse(string, class [mscorlib]System.IFormatProvider)
0x9c699  call     instance void Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::set_EntityTypeCode(int32 value)
0x9c69e  ldarg.0
0x9c69f  ldtoken  Microsoft.Crm.Application.FormType
0x9c6a4  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x9c6a9  ldloc.0
0x9c6aa  ldc.i4.1
0x9c6ab  ldelem.ref
0x9c6ac  call     object [mscorlib]System.Enum::Parse(class [mscorlib]System.Type, string)
0x9c6b1  unbox.any Microsoft.Crm.Application.FormType
0x9c6b6  call     instance void Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::set_FormType(valuetype Microsoft.Crm.Application.FormType value)
0x9c6bb  ldarg.0
0x9c6bc  call     instance valuetype Microsoft.Crm.Application.FormType Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::get_FormType()
0x9c6c1  ldc.i4.s 9
0x9c6c3  bne.un.s loc_9C6D8
0x9c6c5  ldarg.0
0x9c6c6  ldc.i4.0
0x9c6c7  call     instance void Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::set_UseSystemUserContext(bool value)
0x9c6cc  ldarg.0
0x9c6cd  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x9c6d2  call     instance void Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::set_UserId(valuetype [mscorlib]System.Guid value)
0x9c6d7  ret
0x9c6d8  ldloc.0
0x9c6d9  ldlen
0x9c6da  conv.i4
0x9c6db  ldc.i4.4
0x9c6dc  ceq
0x9c6de  ldstr    aInvalidKeyStri_2// "Invalid key string passed to AppFormFil"...
0x9c6e3  call     void Microsoft.Crm.Diagnostics.Debug::AssertEx(bool assert, string message)
0x9c6e8  ldarg.0
0x9c6e9  ldloc.0
0x9c6ea  ldc.i4.2
0x9c6eb  ldelem.ref
0x9c6ec  call     bool [mscorlib]System.Boolean::Parse(string)
0x9c6f1  call     instance void Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::set_UseSystemUserContext(bool value)
0x9c6f6  ldarg.0
0x9c6f7  ldloc.0
0x9c6f8  ldc.i4.3
0x9c6f9  ldelem.ref
0x9c6fa  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Parse(string)
0x9c6ff  call     instance void Microsoft.Crm.Application.Components.Platform.ClientCacheLoaders.AppFormFilterCacheKey::set_UserId(valuetype [mscorlib]System.Guid value)
0x9c704  ret
```
