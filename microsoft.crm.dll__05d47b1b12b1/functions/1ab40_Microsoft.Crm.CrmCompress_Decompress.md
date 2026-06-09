# Microsoft.Crm.CrmCompress::Decompress

- ea: `0x1ab40`
- end: `0x1abfb`
- name: `Microsoft.Crm.CrmCompress::Decompress`
- size: `187`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1ab40`

## string_xrefs

- `0x1ab7f`: `Decompressed data too big! Uncompressed data size: {0} MB. Please make sure that the uncompressed data is within 200 MB`

## pseudocode

```c

```

## disassembly

```asm
0x1ab40  ldarg.0
0x1ab41  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor(unsigned int8[])
0x1ab46  stloc.0
0x1ab47  ldloc.0
0x1ab48  stloc.1
0x1ab49  ldloc.0
0x1ab4a  ldc.i4.0
0x1ab4b  ldc.i4.0
0x1ab4c  newobj   instance void [System]System.IO.Compression.DeflateStream::.ctor(class [mscorlib]System.IO.Stream, valuetype [System]System.IO.Compression.CompressionMode, bool)
0x1ab51  stloc.2
0x1ab52  ldloc.2
0x1ab53  stloc.3
0x1ab54  ldc.i4   0x1000
0x1ab59  newarr   [mscorlib]System.Byte
0x1ab5e  stloc.s  4
0x1ab60  newobj   instance void [mscorlib]System.IO.MemoryStream::.ctor()
0x1ab65  stloc.s  5
0x1ab67  ldloc.s  5
0x1ab69  stloc.s  6
0x1ab6b  ldloc.s  5
0x1ab6d  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1ab72  ldc.i4   0xC800000
0x1ab77  conv.i8
0x1ab78  ble.s    loc_1ABAB
0x1ab7a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1ab7f  ldstr    aDecompressedDa// "Decompressed data too big! Uncompressed"...
0x1ab84  ldc.i4.1
0x1ab85  newarr   [mscorlib]System.Object
0x1ab8a  dup
0x1ab8b  ldc.i4.0
0x1ab8c  ldloc.s  5
0x1ab8e  callvirt instance int64 [mscorlib]System.IO.Stream::get_Length()
0x1ab93  ldc.i4   0x100000
0x1ab98  conv.i8
0x1ab99  div
0x1ab9a  box      [mscorlib]System.Int64
0x1ab9f  stelem.ref
0x1aba0  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1aba5  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentOutOfRangeException::.ctor(string)
0x1abaa  throw
0x1abab  ldloc.2
0x1abac  ldloc.s  4
0x1abae  ldc.i4.0
0x1abaf  ldloc.s  4
0x1abb1  ldlen
0x1abb2  conv.i4
0x1abb3  callvirt instance int32 [mscorlib]System.IO.Stream::Read(unsigned int8[], int32, int32)
0x1abb8  stloc.s  7
0x1abba  ldloc.s  7
0x1abbc  ldc.i4.0
0x1abbd  bgt.s    loc_1ABCA
0x1abbf  ldloc.s  5
0x1abc1  callvirt instance unsigned int8[] [mscorlib]System.IO.MemoryStream::ToArray()
0x1abc6  stloc.s  8
0x1abc8  leave.s  loc_1ABF8
0x1abca  ldloc.s  5
0x1abcc  ldloc.s  4
0x1abce  ldc.i4.0
0x1abcf  ldloc.s  7
0x1abd1  callvirt instance void [mscorlib]System.IO.Stream::Write(unsigned int8[], int32, int32)
0x1abd6  br.s     loc_1AB6B
0x1abd8  ldloc.s  6
0x1abda  brfalse.s loc_1ABE3
0x1abdc  ldloc.s  6
0x1abde  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1abe3  endfinally
0x1abe4  ldloc.3
0x1abe5  brfalse.s loc_1ABED
0x1abe7  ldloc.3
0x1abe8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1abed  endfinally
0x1abee  ldloc.1
0x1abef  brfalse.s loc_1ABF7
0x1abf1  ldloc.1
0x1abf2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1abf7  endfinally
0x1abf8  ldloc.s  8
0x1abfa  ret
```
