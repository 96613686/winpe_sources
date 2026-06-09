# Microsoft.Crm.WebServices.OfflineSyncHelper::CreateBcpFileHeader

- ea: `0xf8f0`
- end: `0xf9c2`
- name: `Microsoft.Crm.WebServices.OfflineSyncHelper::CreateBcpFileHeader`
- size: `210`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xf770`

## callees

- `0xf8f0`

## pseudocode

```c

```

## disassembly

```asm
0xf8f0  ldc.i4.0
0xf8f1  stloc.0
0xf8f2  ldc.i4.0
0xf8f3  conv.i8
0xf8f4  stloc.1
0xf8f5  ldarg.0
0xf8f6  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.OrganizationContext::.ctor(valuetype [mscorlib]System.Guid)
0xf8fb  call     class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.MetadataCache::GetInstance(class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext)
0xf900  callvirt instance string [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.DynamicMetadataCache::get_TimeStamp()
0xf905  stloc.2
0xf906  ldloc.2
0xf907  ldc.i4.7
0xf908  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf90d  ldloca.s 0
0xf90f  call     bool [mscorlib]System.Int32::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int32&)
0xf914  stloc.3
0xf915  ldloc.3
0xf916  brtrue.s loc_F955
0xf918  ldarg.0
0xf919  ldc.i4.s 0x14
0xf91b  ldstr    aThisOrganizati// "This organization's timestamp of {0} is"...
0xf920  ldc.i4.1
0xf921  newarr   [mscorlib]System.Object
0xf926  dup
0xf927  ldc.i4.0
0xf928  ldloc.2
0xf929  stelem.ref
0xf92a  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceInfo(valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xf92f  ldloc.2
0xf930  ldc.i4.7
0xf931  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xf936  ldloca.s 1
0xf938  call     bool [mscorlib]System.Int64::TryParse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider, int64&)
0xf93d  brtrue.s loc_F955
0xf93f  ldstr    aMetadataTimest// "Metadata timestamp "
0xf944  ldloc.2
0xf945  ldstr    aCouldNotBePars// " could not be parsed as an Int32 or a L"...
0xf94a  call     string [mscorlib]System.String::Concat(string, string, string)
0xf94f  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string)
0xf954  throw
0xf955  ldloc.3
0xf956  brtrue.s loc_F961
0xf958  ldc.i4.s 0x18
0xf95a  newarr   [mscorlib]System.Byte
0xf95f  br.s     loc_F968
0xf961  ldc.i4.s 0x10
0xf963  newarr   [mscorlib]System.Byte
0xf968  stloc.s  4
0xf96a  ldc.i4.1
0xf96b  newarr   [mscorlib]System.Int32
0xf970  dup
0xf971  ldc.i4.0
0xf972  ldarg.1
0xf973  stelem.i4
0xf974  ldc.i4.0
0xf975  ldloc.s  4
0xf977  ldc.i4.0
0xf978  ldc.i4.4
0xf979  call     void [mscorlib]System.Buffer::BlockCopy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0xf97e  ldc.i4.1
0xf97f  newarr   [mscorlib]System.Int64
0xf984  dup
0xf985  ldc.i4.0
0xf986  ldarg.2
0xf987  stelem.i8
0xf988  ldc.i4.0
0xf989  ldloc.s  4
0xf98b  ldc.i4.4
0xf98c  ldc.i4.8
0xf98d  call     void [mscorlib]System.Buffer::BlockCopy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0xf992  ldc.i4.1
0xf993  newarr   [mscorlib]System.Int32
0xf998  dup
0xf999  ldc.i4.0
0xf99a  ldloc.0
0xf99b  stelem.i4
0xf99c  ldc.i4.0
0xf99d  ldloc.s  4
0xf99f  ldc.i4.s 0xC
0xf9a1  ldc.i4.4
0xf9a2  call     void [mscorlib]System.Buffer::BlockCopy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0xf9a7  ldloc.3
0xf9a8  brtrue.s loc_F9BF
0xf9aa  ldc.i4.1
0xf9ab  newarr   [mscorlib]System.Int64
0xf9b0  dup
0xf9b1  ldc.i4.0
0xf9b2  ldloc.1
0xf9b3  stelem.i8
0xf9b4  ldc.i4.0
0xf9b5  ldloc.s  4
0xf9b7  ldc.i4.s 0x10
0xf9b9  ldc.i4.8
0xf9ba  call     void [mscorlib]System.Buffer::BlockCopy(class [mscorlib]System.Array, int32, class [mscorlib]System.Array, int32, int32)
0xf9bf  ldloc.s  4
0xf9c1  ret
```
