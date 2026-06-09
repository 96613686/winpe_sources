# Microsoft.Crm.MobileOfflineUtility::UpsertProvisioningSubState

- ea: `0x21470`
- end: `0x214b0`
- name: `Microsoft.Crm.MobileOfflineUtility::UpsertProvisioningSubState`
- size: `64`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x21130`
- `0x21470`
- `0x214c0`
- `0x214d0`
- `0x21530`

## string_xrefs

- `0x21490`: `Invalid request for mobile offline status update.`

## pseudocode

```c

```

## disassembly

```asm
0x21470  ldarg.0
0x21471  ldc.i4.0
0x21472  ldnull
0x21473  call     class Microsoft.Crm.IMobileOfflineState Microsoft.Crm.MobileOfflineUtility::Read(valuetype [mscorlib]System.Guid organizationId, [opt] bool retrieveFromLocatorCache, [opt] string isTrial)
0x21478  stloc.0
0x21479  ldarg.1
0x2147a  brtrue.s loc_21484
0x2147c  ldloc.0
0x2147d  call     void Microsoft.Crm.MobileOfflineUtility::ValidateStateForProvision(class Microsoft.Crm.IMobileOfflineState offlineState)
0x21482  br.s     loc_2149B
0x21484  ldarg.1
0x21485  ldc.i4.5
0x21486  bne.un.s loc_21490
0x21488  ldloc.0
0x21489  call     void Microsoft.Crm.MobileOfflineUtility::ValidateStateForDeprovision(class Microsoft.Crm.IMobileOfflineState offlineState)
0x2148e  br.s     loc_2149B
0x21490  ldstr    aInvalidRequest// "Invalid request for mobile offline stat"...
0x21495  newobj   instance void [Microsoft.Crm.Core]Microsoft.Crm.CrmException::.ctor(string)
0x2149a  throw
0x2149b  ldarg.0
0x2149c  call     valuetype [Microsoft.Crm.Constants]Microsoft.Crm.OrgApplicationType Microsoft.Crm.MobileOfflineUtility::GetOrgApplicationType(valuetype [mscorlib]System.Guid organizationId)
0x214a1  stloc.1
0x214a2  call     class [Microsoft.Crm.Core]Microsoft.Crm.LocatorService [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::get_Instance()
0x214a7  ldarg.0
0x214a8  ldarg.1
0x214a9  ldloc.1
0x214aa  callvirt instance void [Microsoft.Crm.Core]Microsoft.Crm.LocatorService::UpsertProvisioningSubState(valuetype [mscorlib]System.Guid, int32, int32)
0x214af  ret
```
