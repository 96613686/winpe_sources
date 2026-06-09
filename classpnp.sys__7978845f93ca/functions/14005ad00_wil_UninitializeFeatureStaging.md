# wil_UninitializeFeatureStaging

- ea: `0x14005ad00`
- end: `0x14005ad5a`
- name: `wil_UninitializeFeatureStaging`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140058d20`

## callees

- `0x14005ad00`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14005ad33`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14005ad33`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14005ad10`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14005ad10`

## pseudocode

```c
__int64 wil_UninitializeFeatureStaging()
{
  __int64 result; // rax

  if ( WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  *(_DWORD *)&WPP_MAIN_CB.SectorSize = 0;
  return result;
}

```

## disassembly

```asm
0x14005ad00  sub     rsp, 28h
0x14005ad04  mov     rcx, cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink
0x14005ad0b  test    rcx, rcx
0x14005ad0e  jz      short loc_14005AD27
0x14005ad10  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14005ad17  nop     dword ptr [rax+rax+00h]
0x14005ad1c  mov     cs:WPP_MAIN_CB.DeviceLock.Header.WaitListHead.Flink, 0
0x14005ad27  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14005ad2e  test    rcx, rcx
0x14005ad31  jz      short loc_14005AD4A
0x14005ad33  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14005ad3a  nop     dword ptr [rax+rax+00h]
0x14005ad3f  mov     cs:g_wil_details_featureUsageProvider, 0
0x14005ad4a  mov     dword ptr cs:WPP_MAIN_CB.SectorSize, 0
0x14005ad54  add     rsp, 28h
0x14005ad58  retn
```
