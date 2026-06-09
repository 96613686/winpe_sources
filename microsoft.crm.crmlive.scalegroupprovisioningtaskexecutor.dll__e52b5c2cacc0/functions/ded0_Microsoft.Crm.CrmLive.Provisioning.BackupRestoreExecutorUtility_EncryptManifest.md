# Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::EncryptManifest

- ea: `0xded0`
- end: `0xdf69`
- name: `Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::EncryptManifest`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2da00`

## callees

- `0xded0`
- `0xe010`
- `0xe1d0`
- `0xe240`

## string_xrefs

- `0xded1`: `manifestFileFullPath`
- `0xdf5c`: `manifestFileFullPath`
- `0xdf0f`: `Error occurred in EncryptManifest(). manifestFileFullPath = {0}. {1}`
- `0xdf48`: `EncryptManifest:Manifest file does not exist at path : {0}`

## pseudocode

```c

```

## disassembly

```asm
0xded0  ldarg.0
0xded1  ldstr    aManifestfilefu// "manifestFileFullPath"
0xded6  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string, string)
0xdedb  ldarg.0
0xdedc  call     bool [mscorlib]System.IO.File::Exists(string)
0xdee1  brfalse.s loc_DF43
0xdee3  ldarg.0
0xdee4  ldstr    aE// "_E"
0xdee9  call     string Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::GetNewManifestFileName(string manifestFileFullPath, string suffix)
0xdeee  ldarg.0
0xdeef  call     string [mscorlib]System.IO.File::ReadAllText(string)
0xdef4  stloc.0
0xdef5  dup
0xdef6  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionDecryptionHelper::.ctor()
0xdefb  ldloc.0
0xdefc  call     instance string Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionDecryptionHelper::EncryptSymmetric(string plainText)
0xdf01  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0xdf06  stloc.1
0xdf07  leave.s  loc_DF67
0xdf09  stloc.2
0xdf0a  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdf0f  ldstr    aErrorOccurredI// "Error occurred in EncryptManifest(). ma"...
0xdf14  ldc.i4.2
0xdf15  newarr   [mscorlib]System.Object
0xdf1a  dup
0xdf1b  ldc.i4.0
0xdf1c  ldarg.0
0xdf1d  stelem.ref
0xdf1e  dup
0xdf1f  ldc.i4.1
0xdf20  ldloc.2
0xdf21  callvirt instance string [mscorlib]System.Exception::get_Message()
0xdf26  stelem.ref
0xdf27  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdf2c  stloc.3
0xdf2d  ldloc.2
0xdf2e  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdf33  ldc.i4.s 0x12
0xdf35  ldloc.3
0xdf36  ldc.i4.0
0xdf37  newarr   [mscorlib]System.Object
0xdf3c  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdf41  rethrow
0xdf43  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdf48  ldstr    aEncryptmanifes// "EncryptManifest:Manifest file does not "...
0xdf4d  ldc.i4.1
0xdf4e  newarr   [mscorlib]System.Object
0xdf53  dup
0xdf54  ldc.i4.0
0xdf55  ldarg.0
0xdf56  stelem.ref
0xdf57  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdf5c  ldstr    aManifestfilefu// "manifestFileFullPath"
0xdf61  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0xdf66  throw
0xdf67  ldloc.1
0xdf68  ret
```
