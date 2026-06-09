# Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::DecryptManifest

- ea: `0xdf70`
- end: `0xe010`
- name: `Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::DecryptManifest`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14e90`

## callees

- `0xdf70`
- `0xe010`
- `0xe1d0`
- `0xe290`

## string_xrefs

- `0xdf71`: `manifestFileFullPath`
- `0xe003`: `manifestFileFullPath`
- `0xdfaf`: `Error occurred in DecryptManifest(). manifestFileFullPath = {0}. {1}`
- `0xdfef`: `DecryptManifest:Manifest file does not exist at path : {0}`

## pseudocode

```c

```

## disassembly

```asm
0xdf70  ldarg.0
0xdf71  ldstr    aManifestfilefu// "manifestFileFullPath"
0xdf76  call     void [Microsoft.Crm.Core]Microsoft.Crm.Exceptions::ThrowIfNullOrWhiteSpace(string, string)
0xdf7b  ldarg.0
0xdf7c  call     bool [mscorlib]System.IO.File::Exists(string)
0xdf81  brfalse.s loc_DFEA
0xdf83  ldarg.0
0xdf84  ldstr    aD// "_D"
0xdf89  call     string Microsoft.Crm.CrmLive.Provisioning.BackupRestoreExecutorUtility::GetNewManifestFileName(string manifestFileFullPath, string suffix)
0xdf8e  ldarg.0
0xdf8f  call     string [mscorlib]System.IO.File::ReadAllText(string)
0xdf94  stloc.0
0xdf95  dup
0xdf96  newobj   instance void Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionDecryptionHelper::.ctor()
0xdf9b  ldloc.0
0xdf9c  call     instance string Microsoft.Crm.CrmLive.Provisioning.ManifestEncryptionDecryptionHelper::DecryptSymmetric(string encryptedValue)
0xdfa1  call     void [mscorlib]System.IO.File::WriteAllText(string, string)
0xdfa6  stloc.1
0xdfa7  leave.s  loc_E00E
0xdfa9  stloc.2
0xdfaa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdfaf  ldstr    aErrorOccurredI_0// "Error occurred in DecryptManifest(). ma"...
0xdfb4  ldc.i4.2
0xdfb5  newarr   [mscorlib]System.Object
0xdfba  dup
0xdfbb  ldc.i4.0
0xdfbc  ldarg.0
0xdfbd  stelem.ref
0xdfbe  dup
0xdfbf  ldc.i4.1
0xdfc0  ldloc.2
0xdfc1  callvirt instance string [mscorlib]System.Exception::get_Message()
0xdfc6  stelem.ref
0xdfc7  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xdfcc  stloc.3
0xdfcd  ldloc.2
0xdfce  call     valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::get_DefaultTraceSetting()
0xdfd3  ldc.i4.s 0x12
0xdfd5  ldloc.3
0xdfd6  ldc.i4.0
0xdfd7  newarr   [mscorlib]System.Object
0xdfdc  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0xdfe1  rethrow
0xdfe3  ldarg.0
0xdfe4  call     void [mscorlib]System.IO.File::Delete(string)
0xdfe9  endfinally
0xdfea  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xdfef  ldstr    aDecryptmanifes// "DecryptManifest:Manifest file does not "...
0xdff4  ldc.i4.1
0xdff5  newarr   [mscorlib]System.Object
0xdffa  dup
0xdffb  ldc.i4.0
0xdffc  ldarg.0
0xdffd  stelem.ref
0xdffe  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0xe003  ldstr    aManifestfilefu// "manifestFileFullPath"
0xe008  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmArgumentException::.ctor(string, string)
0xe00d  throw
0xe00e  ldloc.1
0xe00f  ret
```
