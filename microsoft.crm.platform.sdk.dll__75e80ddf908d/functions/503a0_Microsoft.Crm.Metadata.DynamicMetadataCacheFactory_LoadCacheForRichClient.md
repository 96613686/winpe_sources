# Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheForRichClient

- ea: `0x503a0`
- end: `0x504af`
- name: `Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheForRichClient`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x4fd60`

## callees

- `0x503a0`
- `0x504b0`
- `0x50700`
- `0x509a0`
- `0x50e20`
- `0x523d0`

## string_xrefs

- `0x503a8`: `LoadCacheForRichClient - LoadMethod=`
- `0x5046b`: `LoadCacheForRichClient() got exception message: {0} Detais: {1}.`

## pseudocode

```c

```

## disassembly

```asm
0x503a0  ldc.i4.8
0x503a1  newarr   [mscorlib]System.Object
0x503a6  dup
0x503a7  ldc.i4.0
0x503a8  ldstr    aLoadcacheforri// "LoadCacheForRichClient - LoadMethod="
0x503ad  stelem.ref
0x503ae  dup
0x503af  ldc.i4.1
0x503b0  ldarg.0
0x503b1  box      Microsoft.Crm.Metadata.LoadMethod
0x503b6  stelem.ref
0x503b7  dup
0x503b8  ldc.i4.2
0x503b9  ldstr    aLoadmasks// " LoadMasks="
0x503be  stelem.ref
0x503bf  dup
0x503c0  ldc.i4.3
0x503c1  ldarg.2
0x503c2  box      Microsoft.Crm.Metadata.LoadMasks
0x503c7  stelem.ref
0x503c8  dup
0x503c9  ldc.i4.4
0x503ca  ldstr    aIsinofflinecli// " IsInOfflineClientContext="
0x503cf  stelem.ref
0x503d0  dup
0x503d1  ldc.i4.5
0x503d2  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInOfflineClientContext()
0x503d7  stloc.1
0x503d8  ldloca.s 1
0x503da  call     instance string [mscorlib]System.Boolean::ToString()
0x503df  stelem.ref
0x503e0  dup
0x503e1  ldc.i4.6
0x503e2  ldstr    aIsinhostercont// " IsInHosterContext="
0x503e7  stelem.ref
0x503e8  dup
0x503e9  ldc.i4.7
0x503ea  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x503ef  stloc.1
0x503f0  ldloca.s 1
0x503f2  call     instance string [mscorlib]System.Boolean::ToString()
0x503f7  stelem.ref
0x503f8  call     string [mscorlib]System.String::Concat(object[])
0x503fd  ldarg.s  4
0x503ff  call     class [Microsoft.Crm.Core]Microsoft.Crm.CounterList Microsoft.Crm.Metadata.Helpers::LogPerfWithCounterList(string name, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList parentCounter)
0x50404  dup
0x50405  starg.s  4
0x50407  stloc.0
0x50408  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInOfflineClientContext()
0x5040d  brfalse.s loc_50425
0x5040f  call     bool [Microsoft.Crm.Core]Microsoft.Crm.RegControl::IsInHosterContext()
0x50414  brfalse.s loc_50425
0x50416  ldarg.1
0x50417  ldarg.2
0x50418  ldarg.s  4
0x5041a  callvirt instance class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheLoader::LoadCacheFromDatabase(valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5041f  stloc.2
0x50420  leave    loc_504AD
0x50425  ldnull
0x50426  stloc.3
0x50427  ldc.i4.3
0x50428  stloc.s  4
0x5042a  ldarg.0
0x5042b  ldc.i4.5
0x5042c  beq.s    loc_50439
0x5042e  ldarg.1
0x5042f  ldarg.2
0x50430  ldarg.3
0x50431  ldarg.s  4
0x50433  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheFromLocalFile(class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader loader, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x50438  stloc.3
0x50439  ldloc.3
0x5043a  brfalse.s loc_5044D
0x5043c  ldarg.0
0x5043d  ldc.i4.4
0x5043e  beq.s    loc_5044D
0x50440  ldloc.3
0x50441  ldarg.3
0x50442  ldarg.s  4
0x50444  call     bool Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::CheckIfServerVersionIsDifferent(class Microsoft.Crm.Metadata.DynamicMetadataCache cache, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, [opt] class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x50449  brfalse.s loc_5044D
0x5044b  ldnull
0x5044c  stloc.3
0x5044d  ldloc.3
0x5044e  brtrue.s loc_5049F
0x50450  nop
0x50451  ldarg.1
0x50452  ldarg.2
0x50453  ldarg.3
0x50454  ldc.i4.1
0x50455  ldarg.s  4
0x50457  call     class Microsoft.Crm.Metadata.DynamicMetadataCache Microsoft.Crm.Metadata.DynamicMetadataCacheFactory::LoadCacheFromWebService(class Microsoft.Crm.Metadata.DynamicMetadataCacheLoader loader, valuetype Microsoft.Crm.Metadata.LoadMasks masks, class [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext context, bool writeCacheToLocalFile, class [Microsoft.Crm.Core]Microsoft.Crm.CounterList counter)
0x5045c  stloc.3
0x5045d  leave.s  loc_5049F
0x5045f  stloc.s  5
0x50461  ldloc.s  5
0x50463  ldarg.3
0x50464  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.Crm.Core]Microsoft.Crm.IOrganizationContext::get_OrganizationId()
0x50469  ldc.i4.s 0x19
0x5046b  ldstr    aLoadcacheforri_0// "LoadCacheForRichClient() got exception "...
0x50470  ldc.i4.2
0x50471  newarr   [mscorlib]System.Object
0x50476  dup
0x50477  ldc.i4.0
0x50478  ldloc.s  5
0x5047a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x5047f  stelem.ref
0x50480  dup
0x50481  ldc.i4.1
0x50482  ldloc.s  5
0x50484  stelem.ref
0x50485  call     void [Microsoft.Crm.Core]Microsoft.Crm.CrmTrace::TraceError(class [mscorlib]System.Exception, valuetype [mscorlib]System.Guid, valuetype [Microsoft.Crm.Core]Microsoft.Crm.TraceCategory, string, object[])
0x5048a  ldloc.s  4
0x5048c  ldc.i4.1
0x5048d  sub
0x5048e  stloc.s  4
0x50490  ldloc.s  4
0x50492  brtrue.s loc_50496
0x50494  rethrow
0x50496  ldc.i4.s 0x64
0x50498  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x5049d  leave.s  loc_5042A
0x5049f  ldloc.3
0x504a0  stloc.2
0x504a1  leave.s  loc_504AD
0x504a3  ldloc.0
0x504a4  brfalse.s loc_504AC
0x504a6  ldloc.0
0x504a7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x504ac  endfinally
0x504ad  ldloc.2
0x504ae  ret
```
