# Microsoft.Crm.Asynchronous.ImportOperationImportFile::CaptureStateStatusForUpdate

- ea: `0x13900`
- end: `0x13983`
- name: `Microsoft.Crm.Asynchronous.ImportOperationImportFile::CaptureStateStatusForUpdate`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0xea10`

## callees

- `0x5bf0`
- `0x5c10`
- `0x5c20`
- `0x5c40`
- `0x8f40`
- `0x13900`

## pseudocode

```c

```

## disassembly

```asm
0x13900  ldarg.0
0x13901  ldfld    class Microsoft.Crm.Asynchronous.ImportHelperData Microsoft.Crm.Asynchronous.ImportOperation::_importDataStructure
0x13906  callvirt instance int32 Microsoft.Crm.Asynchronous.ImportHelperData::get_ImportMode()
0x1390b  ldc.i4.1
0x1390c  beq.s    loc_1390F
0x1390e  ret
0x1390f  ldarg.s  4
0x13911  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x13916  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x1391b  ldc.i4.s 0xE
0x1391d  ceq
0x1391f  stloc.0
0x13920  ldarg.s  4
0x13922  callvirt instance class [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeMetadata::get_Type()
0x13927  callvirt instance valuetype [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeType [Microsoft.Crm.Platform.Sdk]Microsoft.Crm.Metadata.AttributeTypeInfo::get_AttributeType()
0x1392c  ldc.i4.s 0xF
0x1392e  ceq
0x13930  stloc.1
0x13931  ldloc.0
0x13932  ldloc.1
0x13933  or
0x13934  brtrue.s loc_13937
0x13936  ret
0x13937  ldloc.0
0x13938  brfalse.s loc_1395D
0x1393a  ldarg.3
0x1393b  brtrue.s loc_1394B
0x1393d  ldarg.1
0x1393e  ldarg.1
0x1393f  callvirt instance int32 Microsoft.Crm.Asynchronous.StateStatusHelper::get_OldStateCode()
0x13944  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_StateCode(int32 value)
0x13949  br.s     loc_1395D
0x1394b  ldarg.1
0x1394c  ldarg.2
0x1394d  ldc.i4.7
0x1394e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13953  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x13958  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_StateCode(int32 value)
0x1395d  ldloc.1
0x1395e  brfalse.s loc_13982
0x13960  ldarg.3
0x13961  brtrue.s loc_13970
0x13963  ldarg.1
0x13964  ldarg.1
0x13965  callvirt instance int32 Microsoft.Crm.Asynchronous.StateStatusHelper::get_OldStatusCode()
0x1396a  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_StatusCode(int32 value)
0x1396f  ret
0x13970  ldarg.1
0x13971  ldarg.2
0x13972  ldc.i4.7
0x13973  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13978  call     int32 [mscorlib]System.Int32::Parse(string, valuetype [mscorlib]System.Globalization.NumberStyles, class [mscorlib]System.IFormatProvider)
0x1397d  callvirt instance void Microsoft.Crm.Asynchronous.StateStatusHelper::set_StatusCode(int32 value)
0x13982  ret
```
