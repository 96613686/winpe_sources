# Microsoft.Crm.BusinessEntities.CrmDateTime::Deserialize

- ea: `0x9fc60`
- end: `0x9fe05`
- name: `Microsoft.Crm.BusinessEntities.CrmDateTime::Deserialize`
- size: `421`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x9f690`
- `0x9f960`

## callees

- `0x9fc60`
- `0x9fe10`
- `0x9ff30`
- `0xa0150`
- `0xa8e40`
- `0xa8f30`

## string_xrefs

- `0x9fcbb`: `The date-time format for {0} is invalid, or value is outside the supported range.`
- `0x9fd0b`: `The date-time format for {0} is invalid, or value is outside the supported range.`

## pseudocode

```c

```

## disassembly

```asm
0x9fc60  ldarg.1
0x9fc61  callvirt instance string [mscorlib]System.String::Trim()
0x9fc66  stloc.0
0x9fc67  ldarg.0
0x9fc68  ldarg.3
0x9fc69  stfld    string Microsoft.Crm.BusinessEntities.CrmDateTime::_formattedDate
0x9fc6e  ldarg.0
0x9fc6f  ldarg.s  4
0x9fc71  stfld    string Microsoft.Crm.BusinessEntities.CrmDateTime::_formattedTime
0x9fc76  ldloc.0
0x9fc77  callvirt instance int32 [mscorlib]System.String::get_Length()
0x9fc7c  stloc.1
0x9fc7d  ldloc.1
0x9fc7e  brtrue.s loc_9FC8B
0x9fc80  ldstr    aEmptyStringIsN// "Empty string is not a valid representat"...
0x9fc85  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentNullException::.ctor(string)
0x9fc8a  throw
0x9fc8b  ldloc.0
0x9fc8c  ldloc.1
0x9fc8d  ldc.i4.1
0x9fc8e  sub
0x9fc8f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9fc94  ldc.i4.s 0x5A
0x9fc96  beq.s    loc_9FCA5
0x9fc98  ldloc.0
0x9fc99  ldloc.1
0x9fc9a  ldc.i4.1
0x9fc9b  sub
0x9fc9c  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9fca1  ldc.i4.s 0x7A
0x9fca3  bne.un.s loc_9FCF6
0x9fca5  ldloc.0
0x9fca6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fcab  ldc.i4.s 0x10
0x9fcad  ldloca.s 2
0x9fcaf  call     bool [mscorlib]System.DateTime::TryParse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles, valuetype [mscorlib]System.DateTime&)
0x9fcb4  brtrue.s loc_9FCDA
0x9fcb6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fcbb  ldstr    aTheDateTimeFor// "The date-time format for {0} is invalid"...
0x9fcc0  ldc.i4.1
0x9fcc1  newarr   [mscorlib]System.Object
0x9fcc6  dup
0x9fcc7  ldc.i4.0
0x9fcc8  ldloc.0
0x9fcc9  stelem.ref
0x9fcca  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9fccf  ldc.i4   0x80040239
0x9fcd4  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x9fcd9  throw
0x9fcda  ldarg.2
0x9fcdb  ldc.i4.2
0x9fcdc  beq.s    loc_9FCE2
0x9fcde  ldarg.2
0x9fcdf  ldc.i4.3
0x9fce0  bne.un.s loc_9FCEC
0x9fce2  ldarg.0
0x9fce3  ldc.i4.1
0x9fce4  ldloc.2
0x9fce5  ldarg.2
0x9fce6  call     instance void Microsoft.Crm.BusinessEntities.CrmDateTime::Initialize(valuetype Style style, valuetype [mscorlib]System.DateTime dateTime, valuetype Microsoft.Crm.Metadata.Behavior dateTimeBehavior)
0x9fceb  ret
0x9fcec  ldarg.0
0x9fced  ldc.i4.2
0x9fcee  ldloc.2
0x9fcef  ldarg.2
0x9fcf0  call     instance void Microsoft.Crm.BusinessEntities.CrmDateTime::Initialize(valuetype Style style, valuetype [mscorlib]System.DateTime dateTime, valuetype Microsoft.Crm.Metadata.Behavior dateTimeBehavior)
0x9fcf5  ret
0x9fcf6  ldloc.0
0x9fcf7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fcfc  ldc.i4.0
0x9fcfd  ldloca.s 2
0x9fcff  call     bool [mscorlib]System.DateTime::TryParse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles, valuetype [mscorlib]System.DateTime&)
0x9fd04  brtrue.s loc_9FD2A
0x9fd06  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fd0b  ldstr    aTheDateTimeFor// "The date-time format for {0} is invalid"...
0x9fd10  ldc.i4.1
0x9fd11  newarr   [mscorlib]System.Object
0x9fd16  dup
0x9fd17  ldc.i4.0
0x9fd18  ldloc.0
0x9fd19  stelem.ref
0x9fd1a  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x9fd1f  ldc.i4   0x80040239
0x9fd24  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string, int32)
0x9fd29  throw
0x9fd2a  ldloc.1
0x9fd2b  ldc.i4.6
0x9fd2c  ble      loc_9FDBB
0x9fd31  ldloc.0
0x9fd32  ldloc.1
0x9fd33  ldc.i4.6
0x9fd34  sub
0x9fd35  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9fd3a  ldc.i4.s 0x2B
0x9fd3c  beq.s    loc_9FD4B
0x9fd3e  ldloc.0
0x9fd3f  ldloc.1
0x9fd40  ldc.i4.6
0x9fd41  sub
0x9fd42  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9fd47  ldc.i4.s 0x2D
0x9fd49  bne.un.s loc_9FDBB
0x9fd4b  ldloc.0
0x9fd4c  ldloc.1
0x9fd4d  ldc.i4.3
0x9fd4e  sub
0x9fd4f  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x9fd54  ldc.i4.s 0x3A
0x9fd56  bne.un.s loc_9FDBB
0x9fd58  ldloc.0
0x9fd59  ldc.i4.s 0x3A
0x9fd5b  ldc.i4.0
0x9fd5c  ldloc.1
0x9fd5d  ldc.i4.6
0x9fd5e  sub
0x9fd5f  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32, int32)
0x9fd64  ldc.i4.0
0x9fd65  blt.s    loc_9FDBB
0x9fd67  ldloc.0
0x9fd68  ldc.i4.0
0x9fd69  ldloc.1
0x9fd6a  ldc.i4.6
0x9fd6b  sub
0x9fd6c  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x9fd71  stloc.3
0x9fd72  ldarg.2
0x9fd73  ldc.i4.2
0x9fd74  beq.s    loc_9FD7A
0x9fd76  ldarg.2
0x9fd77  ldc.i4.3
0x9fd78  bne.un.s loc_9FD93
0x9fd7a  ldloc.3
0x9fd7b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fd80  ldc.i4.0
0x9fd81  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles)
0x9fd86  stloc.s  4
0x9fd88  ldarg.0
0x9fd89  ldc.i4.1
0x9fd8a  ldloc.s  4
0x9fd8c  ldarg.2
0x9fd8d  call     instance void Microsoft.Crm.BusinessEntities.CrmDateTime::Initialize(valuetype Style style, valuetype [mscorlib]System.DateTime dateTime, valuetype Microsoft.Crm.Metadata.Behavior dateTimeBehavior)
0x9fd92  ret
0x9fd93  ldloc.3
0x9fd94  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fd99  ldc.i4.s 0x10
0x9fd9b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles)
0x9fda0  stloc.s  4
0x9fda2  ldloc.0
0x9fda3  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x9fda8  ldc.i4.s 0x10
0x9fdaa  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::Parse(string, class [mscorlib]System.IFormatProvider, valuetype [mscorlib]System.Globalization.DateTimeStyles)
0x9fdaf  stloc.2
0x9fdb0  ldarg.0
0x9fdb1  ldloc.s  4
0x9fdb3  ldloc.2
0x9fdb4  ldarg.2
0x9fdb5  call     instance void Microsoft.Crm.BusinessEntities.CrmDateTime::Initialize(valuetype [mscorlib]System.DateTime userTime, valuetype [mscorlib]System.DateTime universalTime, valuetype Microsoft.Crm.Metadata.Behavior dateTimeBehavior)
0x9fdba  ret
0x9fdbb  ldloc.2
0x9fdbc  stloc.s  5
0x9fdbe  ldarg.2
0x9fdbf  ldc.i4.2
0x9fdc0  beq.s    loc_9FDC6
0x9fdc2  ldarg.2
0x9fdc3  ldc.i4.3
0x9fdc4  bne.un.s loc_9FDD1
0x9fdc6  ldarg.0
0x9fdc7  ldc.i4.1
0x9fdc8  ldloc.s  5
0x9fdca  ldarg.2
0x9fdcb  call     instance void Microsoft.Crm.BusinessEntities.CrmDateTime::Initialize(valuetype Style style, valuetype [mscorlib]System.DateTime dateTime, valuetype Microsoft.Crm.Metadata.Behavior dateTimeBehavior)
0x9fdd0  ret
0x9fdd1  ldarg.2
0x9fdd2  ldc.i4.1
0x9fdd3  bne.un.s loc_9FE04
0x9fdd5  call     bool Microsoft.Crm.BusinessEntities.SerializationState::get_IsInPlatformContext()
0x9fdda  brfalse.s loc_9FDFA
0x9fddc  ldloc.s  5
0x9fdde  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.BusinessEntities.SerializationState::ConvertUserTimeToUtcTime(valuetype [mscorlib]System.DateTime userTime)
0x9fde3  stloc.s  6
0x9fde5  ldloc.s  6
0x9fde7  call     valuetype [mscorlib]System.DateTime Microsoft.Crm.BusinessEntities.CrmDateTime::AdjustToLimits(valuetype [mscorlib]System.DateTime value)
0x9fdec  stloc.s  6
0x9fdee  ldarg.0
0x9fdef  ldloc.s  5
0x9fdf1  ldloc.s  6
0x9fdf3  ldarg.2
0x9fdf4  call     instance void Microsoft.Crm.BusinessEntities.CrmDateTime::Initialize(valuetype [mscorlib]System.DateTime userTime, valuetype [mscorlib]System.DateTime universalTime, valuetype Microsoft.Crm.Metadata.Behavior dateTimeBehavior)
0x9fdf9  ret
0x9fdfa  ldarg.0
0x9fdfb  ldc.i4.1
0x9fdfc  ldloc.s  5
0x9fdfe  ldarg.2
0x9fdff  call     instance void Microsoft.Crm.BusinessEntities.CrmDateTime::Initialize(valuetype Style style, valuetype [mscorlib]System.DateTime dateTime, valuetype Microsoft.Crm.Metadata.Behavior dateTimeBehavior)
0x9fe04  ret
```
