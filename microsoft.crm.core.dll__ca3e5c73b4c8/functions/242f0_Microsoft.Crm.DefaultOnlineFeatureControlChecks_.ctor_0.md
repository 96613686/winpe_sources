# Microsoft.Crm.DefaultOnlineFeatureControlChecks::.ctor_0

- ea: `0x242f0`
- end: `0x24336`
- name: `Microsoft.Crm.DefaultOnlineFeatureControlChecks::.ctor_0`
- size: `70`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x242d0`
- `0x24a10`

## callees

- `0x242f0`
- `0x33930`
- `0x34190`

## string_xrefs

- `0x242f9`: `featureControlCheckCache`
- `0x24307`: `locatorService`

## pseudocode

```c

```

## disassembly

```asm
0x242f0  ldarg.0
0x242f1  call     instance void [mscorlib]System.Object::.ctor()
0x242f6  ldarg.1
0x242f7  brtrue.s loc_24304
0x242f9  ldstr    aFeaturecontrol_2// "featureControlCheckCache"
0x242fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24303  throw
0x24304  ldarg.2
0x24305  brtrue.s loc_24312
0x24307  ldstr    aLocatorservice_3// "locatorService"
0x2430c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x24311  throw
0x24312  ldarg.0
0x24313  call     bool Microsoft.Crm.RegControl::IsInClientContext()
0x24318  brtrue.s loc_24321
0x2431a  call     bool Microsoft.Crm.RegControl::IsInOfflineClientContext()
0x2431f  br.s     loc_24322
0x24321  ldc.i4.1
0x24322  stfld    bool Microsoft.Crm.DefaultOnlineFeatureControlChecks::shouldNotCheckForFeatureEnabled
0x24327  ldarg.0
0x24328  ldarg.1
0x24329  stfld    class Microsoft.Crm.IFeatureControlCheckCache Microsoft.Crm.DefaultOnlineFeatureControlChecks::featureControlCheckCache
0x2432e  ldarg.0
0x2432f  ldarg.2
0x24330  stfld    class Microsoft.Crm.ILocatorService Microsoft.Crm.DefaultOnlineFeatureControlChecks::locatorService
0x24335  ret
```
