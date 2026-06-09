# MRxSmb20Unload

- ea: `0x14002c110`
- end: `0x14002c2fb`
- name: `MRxSmb20Unload`
- size: `491`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x140029764`
- `0x1400297fc`
- `0x14002c110`
- `0x14002c58c`
- `0x140035e9c`
- `0x140051c00`
- `0x1400549a0`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x14002c25d`
- `ntoskrnl!EtwUnregister` at `0x14002c25d`
- `ntoskrnl!MmResetDriverPaging` at `0x14002c17a`
- `ntoskrnl!MmResetDriverPaging` at `0x14002c17a`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002c12f`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x14002c12f`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002c152`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x14002c152`
- `mrxsmb!MRxSmbDeregisterSubRedirector` at `0x14002c241`
- `mrxsmb!MRxSmbDeregisterSubRedirector` at `0x14002c241`
- `mrxsmb!SmbCryptoKeyedHashUninitialize` at `0x14002c1be`
- `mrxsmb!SmbCryptoKeyedHashUninitialize` at `0x14002c1be`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002c1dc`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002c1f0`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002c228`

## pseudocode

```c
__int64 __fastcall MRxSmb20Unload(__int64 a1)
{
  _QWORD *i; // rbx
  void *v3; // rdi
  PVOID DeviceExtension; // rdx
  unsigned int v5; // eax
  unsigned int v6; // eax

  if ( WPP_MAIN_CB.Dpc.DpcData )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DpcData = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  WPP_MAIN_CB.ActiveThreadCount = 0;
  MmResetDriverPaging(MRxSmb20Unload);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids, a1);
  }
  SmbCryptoKeyedHashUninitialize();
  if ( (__int64 *)GlobalDirCacheObjectList != &GlobalDirCacheObjectList )
    __int2c();
  for ( i = *(_QWORD **)(*(_QWORD *)(MRxSmbDeviceObject + 8LL) + 8LL); i; i = (_QWORD *)i[2] )
  {
    if ( i[44] == *(_QWORD *)(MRxSmbDeviceObject + 352LL) )
    {
      v3 = (void *)i[278];
      if ( i[292] )
        Smb2TeardownResilientHandleDatabase(i);
      if ( v3 )
      {
        DeviceExtension = WPP_MAIN_CB.DeviceExtension;
        if ( i != (_QWORD *)MRxSmbDeviceObject )
          DeviceExtension = v3;
        MRxSmbDeregisterSubRedirector(i, DeviceExtension);
      }
    }
  }
  v5 = EtwUnregister(Microsoft_Windows_Networking_CorrelationHandle);
  Microsoft_Windows_Networking_CorrelationHandle = 0;
  if ( v5
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids, v5);
  }
  v6 = McGenEventUnregister_EtwUnregister();
  if ( v6
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids, v6);
  }
  TlgUnregisterAggregateProvider();
  return WppCleanupKm();
}

```

## disassembly

```asm
0x14002c110  mov     [rsp+arg_0], rbx
0x14002c115  mov     [rsp+arg_8], rdi
0x14002c11a  push    r15
0x14002c11c  sub     rsp, 20h
0x14002c120  mov     rbx, rcx
0x14002c123  mov     rcx, cs:WPP_MAIN_CB.Dpc.DpcData
0x14002c12a  test    rcx, rcx
0x14002c12d  jz      short loc_14002C146
0x14002c12f  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x14002c136  nop     dword ptr [rax+rax+00h]
0x14002c13b  mov     cs:WPP_MAIN_CB.Dpc.DpcData, 0
0x14002c146  mov     rcx, cs:g_wil_details_featureUsageProvider
0x14002c14d  test    rcx, rcx
0x14002c150  jz      short loc_14002C169
0x14002c152  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x14002c159  nop     dword ptr [rax+rax+00h]
0x14002c15e  mov     cs:g_wil_details_featureUsageProvider, 0
0x14002c169  lea     rcx, MRxSmb20Unload; AddressWithinSection
0x14002c170  mov     cs:WPP_MAIN_CB.ActiveThreadCount, 0
0x14002c17a  call    cs:__imp_MmResetDriverPaging
0x14002c181  nop     dword ptr [rax+rax+00h]
0x14002c186  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c18d  lea     r15, WPP_GLOBAL_Control
0x14002c194  cmp     rcx, r15
0x14002c197  jz      short loc_14002C1BE
0x14002c199  mov     eax, [rcx+2Ch]
0x14002c19c  test    al, 2
0x14002c19e  jz      short loc_14002C1BE
0x14002c1a0  cmp     byte ptr [rcx+29h], 4
0x14002c1a4  jb      short loc_14002C1BE
0x14002c1a6  mov     rcx, [rcx+18h]
0x14002c1aa  lea     r8, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids
0x14002c1b1  mov     edx, 0Ah
0x14002c1b6  mov     r9, rbx
0x14002c1b9  call    WPP_SF_q
0x14002c1be  call    cs:__imp_SmbCryptoKeyedHashUninitialize
0x14002c1c5  nop     dword ptr [rax+rax+00h]
0x14002c1ca  lea     rax, GlobalDirCacheObjectList
0x14002c1d1  cmp     cs:GlobalDirCacheObjectList, rax
0x14002c1d8  jz      short loc_14002C1DC
0x14002c1da  int     2Ch; Windows NT - assertion failure
0x14002c1dc  mov     rax, cs:__imp_MRxSmbDeviceObject
0x14002c1e3  mov     rcx, [rax]
0x14002c1e6  mov     rax, [rcx+8]
0x14002c1ea  mov     rbx, [rax+8]
0x14002c1ee  jmp     short loc_14002C251
0x14002c1f0  mov     rax, cs:__imp_MRxSmbDeviceObject
0x14002c1f7  mov     rcx, [rax]
0x14002c1fa  mov     rax, [rcx+160h]
0x14002c201  cmp     [rbx+160h], rax
0x14002c208  jnz     short loc_14002C24D
0x14002c20a  cmp     qword ptr [rbx+920h], 0
0x14002c212  mov     rdi, [rbx+8B0h]
0x14002c219  jz      short loc_14002C223
0x14002c21b  mov     rcx, rbx
0x14002c21e  call    Smb2TeardownResilientHandleDatabase
0x14002c223  test    rdi, rdi
0x14002c226  jz      short loc_14002C24D
0x14002c228  mov     rax, cs:__imp_MRxSmbDeviceObject
0x14002c22f  mov     rcx, rbx
0x14002c232  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x14002c239  cmp     rbx, [rax]
0x14002c23c  jz      short loc_14002C241
0x14002c23e  mov     rdx, rdi
0x14002c241  call    cs:__imp_MRxSmbDeregisterSubRedirector
0x14002c248  nop     dword ptr [rax+rax+00h]
0x14002c24d  mov     rbx, [rbx+10h]
0x14002c251  test    rbx, rbx
0x14002c254  jnz     short loc_14002C1F0
0x14002c256  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14002c25d  call    cs:__imp_EtwUnregister
0x14002c264  nop     dword ptr [rax+rax+00h]
0x14002c269  mov     cs:Microsoft_Windows_Networking_CorrelationHandle, rbx
0x14002c270  test    eax, eax
0x14002c272  jz      short loc_14002C2A4
0x14002c274  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c27b  cmp     rcx, r15
0x14002c27e  jz      short loc_14002C2A4
0x14002c280  mov     edx, [rcx+2Ch]
0x14002c283  test    dl, 2
0x14002c286  jz      short loc_14002C2A4
0x14002c288  cmp     byte ptr [rcx+29h], 4
0x14002c28c  jb      short loc_14002C2A4
0x14002c28e  mov     rcx, [rcx+18h]
0x14002c292  lea     edx, [rbx+0Bh]
0x14002c295  mov     r9d, eax
0x14002c298  lea     r8, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids
0x14002c29f  call    WPP_SF_d
0x14002c2a4  call    McGenEventUnregister_EtwUnregister
0x14002c2a9  test    eax, eax
0x14002c2ab  jz      short loc_14002C2DF
0x14002c2ad  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002c2b4  cmp     rcx, r15
0x14002c2b7  jz      short loc_14002C2DF
0x14002c2b9  mov     edx, [rcx+2Ch]
0x14002c2bc  test    dl, 2
0x14002c2bf  jz      short loc_14002C2DF
0x14002c2c1  cmp     byte ptr [rcx+29h], 4
0x14002c2c5  jb      short loc_14002C2DF
0x14002c2c7  mov     rcx, [rcx+18h]
0x14002c2cb  lea     r8, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids
0x14002c2d2  mov     edx, 0Ch
0x14002c2d7  mov     r9d, eax
0x14002c2da  call    WPP_SF_d
0x14002c2df  call    TlgUnregisterAggregateProvider
0x14002c2e4  call    WppCleanupKm
0x14002c2e9  mov     rbx, [rsp+28h+arg_0]
0x14002c2ee  mov     rdi, [rsp+28h+arg_8]
0x14002c2f3  add     rsp, 20h
0x14002c2f7  pop     r15
0x14002c2f9  retn
```
