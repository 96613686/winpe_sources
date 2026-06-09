# Microsoft.Crm.Metadata.LabelCache::Instance

- ea: `0x1e620`
- end: `0x1e6b6`
- name: `Microsoft.Crm.Metadata.LabelCache::Instance`
- size: `150`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x45dd0`
- `0x45e20`
- `0x45e90`
- `0x4e580`

## callees

- `0x1e620`
- `0x1e6c0`

## string_xrefs

- `0x1e64a`: `Microsoft.Crm.Caching.LabelDictionaryCacheLoaderFactory`
- `0x1e67f`: `Microsoft.Crm.Caching.LabelDictionaryCacheLoaderFactory`
- `0x1e672`: `Cache loader factory type is not derived from ILabelDictionaryCacheLoaderFactory: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x1e620  volatile.
0x1e622  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.Crm.Metadata.LabelCache Microsoft.Crm.Metadata.LabelCache::_innerCache
0x1e627  brtrue   loc_1E6AE
0x1e62c  ldsfld   object Microsoft.Crm.Metadata.LabelCache::_lock
0x1e631  stloc.0
0x1e632  ldc.i4.0
0x1e633  stloc.1
0x1e634  ldloc.0
0x1e635  ldloca.s 1
0x1e637  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1e63c  volatile.
0x1e63e  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.Crm.Metadata.LabelCache Microsoft.Crm.Metadata.LabelCache::_innerCache
0x1e643  brtrue.s loc_1E6A2
0x1e645  ldstr    aMicrosoftCrmOb// "Microsoft.Crm.ObjectModel"
0x1e64a  ldstr    aMicrosoftCrmCa// "Microsoft.Crm.Caching.LabelDictionaryCa"...
0x1e64f  ldc.i4.0
0x1e650  newarr   [mscorlib]System.Object
0x1e655  call     string [Microsoft.Crm.Core]Microsoft.Crm.ProductVersion::GetFullyQualifiedTypeName(string, string, object[])
0x1e65a  call     class [mscorlib]System.Type [mscorlib]System.Type::GetType(string)
0x1e65f  call     object [mscorlib]System.Activator::CreateInstance(class [mscorlib]System.Type)
0x1e664  isinst   Microsoft.Crm.Metadata.ILabelDictionaryCacheLoaderFactory
0x1e669  stloc.2
0x1e66a  ldloc.2
0x1e66b  brtrue.s loc_1E695
0x1e66d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1e672  ldstr    aCacheLoaderFac// "Cache loader factory type is not derive"...
0x1e677  ldc.i4.1
0x1e678  newarr   [mscorlib]System.Object
0x1e67d  dup
0x1e67e  ldc.i4.0
0x1e67f  ldstr    aMicrosoftCrmCa// "Microsoft.Crm.Caching.LabelDictionaryCa"...
0x1e684  stelem.ref
0x1e685  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1e68a  ldc.i4   0x80040203
0x1e68f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x1e694  throw
0x1e695  ldloc.2
0x1e696  newobj   instance void Microsoft.Crm.Metadata.LabelCache::.ctor(class Microsoft.Crm.Metadata.ILabelDictionaryCacheLoaderFactory labelSetCacheLoaderFactory)
0x1e69b  volatile.
0x1e69d  stsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.Crm.Metadata.LabelCache Microsoft.Crm.Metadata.LabelCache::_innerCache
0x1e6a2  leave.s  loc_1E6AE
0x1e6a4  ldloc.1
0x1e6a5  brfalse.s loc_1E6AD
0x1e6a7  ldloc.0
0x1e6a8  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1e6ad  endfinally
0x1e6ae  volatile.
0x1e6b0  ldsfld   modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class Microsoft.Crm.Metadata.LabelCache Microsoft.Crm.Metadata.LabelCache::_innerCache
0x1e6b5  ret
```
