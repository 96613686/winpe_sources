# MRxSmbUnload

- ea: `0x140032a30`
- end: `0x140032d54`
- name: `MRxSmbUnload`
- size: `804`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000fa54`
- `0x140011de4`
- `0x140032a30`
- `0x1400335cc`
- `0x140033604`
- `0x140033b0c`
- `0x14003562c`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x140032b73`
- `ntoskrnl!EtwUnregister` at `0x140032b73`
- `ntoskrnl!MmResetDriverPaging` at `0x140032a46`
- `ntoskrnl!MmResetDriverPaging` at `0x140032a46`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140032d36`
- `ntoskrnl!KeFlushQueuedDpcs` at `0x140032d36`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ce3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032d08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032b59`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c05`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c26`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c47`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032c8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032cb8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032ce3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140032d08`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032a99`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032ab4`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032acf`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032aea`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032b05`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032b20`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032a99`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032ab4`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032acf`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032aea`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032b05`
- `mrxsmb!MRxSmbDeregisterDialect` at `0x140032b20`
- `mrxsmb!MRxSmbDeregisterSubRedirector` at `0x140032b3d`
- `mrxsmb!MRxSmbDeregisterSubRedirector` at `0x140032b3d`
- `mrxsmb!MRxSmbShutdownRecurrentService` at `0x140032d2a`
- `mrxsmb!MRxSmbShutdownRecurrentService` at `0x140032d2a`
- `mrxsmb!MRxSmbDeviceObject` at `0x140032a8d`
- `mrxsmb!MRxSmbDeviceObject` at `0x140032aa5`
- `mrxsmb!MRxSmbDeviceObject` at `0x140032ac0`
- `mrxsmb!MRxSmbDeviceObject` at `0x140032adb`
- `mrxsmb!MRxSmbDeviceObject` at `0x140032af6`
- `mrxsmb!MRxSmbDeviceObject` at `0x140032b11`
- `mrxsmb!MRxSmbDeviceObject` at `0x140032b2c`

## pseudocode

```c
void MRxSmbUnload()
{
  unsigned int v0; // eax
  unsigned int v1; // eax

  wil_UninitializeFeatureStaging();
  MmResetDriverPaging(MRxSmbUnload);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids);
  SmbCeDbTearDown();
  SmbMmTearDown();
  MRxSmbDeregisterDialect(MRxSmbDeviceObject, 0);
  MRxSmbDeregisterDialect(MRxSmbDeviceObject, 1);
  MRxSmbDeregisterDialect(MRxSmbDeviceObject, 2);
  MRxSmbDeregisterDialect(MRxSmbDeviceObject, 3);
  MRxSmbDeregisterDialect(MRxSmbDeviceObject, 4);
  MRxSmbDeregisterDialect(MRxSmbDeviceObject, 5);
  MRxSmbDeregisterSubRedirector(MRxSmbDeviceObject, MRxSmb10SubRdrHandle);
  if ( MrxSmbCeGlobalPadding )
  {
    ExFreePoolWithTag(MrxSmbCeGlobalPadding, 0);
    MrxSmbCeGlobalPadding = 0;
  }
  v0 = EtwUnregister(Microsoft_Windows_Networking_CorrelationHandle);
  Microsoft_Windows_Networking_CorrelationHandle = 0;
  if ( v0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids, v0);
  }
  v1 = McGenEventUnregister_EtwUnregister();
  if ( v1
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids, v1);
  }
  TraceLoggingUnregister_EtwUnregister();
  WppCleanupKm();
  if ( DestinationString.Buffer )
  {
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    DestinationString.Buffer = 0;
  }
  if ( stru_1400202E0.Buffer )
  {
    ExFreePoolWithTag(stru_1400202E0.Buffer, 0);
    stru_1400202E0.Buffer = 0;
  }
  if ( stru_1400202F0.Buffer )
  {
    ExFreePoolWithTag(stru_1400202F0.Buffer, 0);
    stru_1400202F0.Buffer = 0;
  }
  if ( SmbCeContext.Buffer )
  {
    ExFreePoolWithTag(SmbCeContext.Buffer, 0);
    SmbCeContext.Buffer = 0;
  }
  if ( stru_140020300.Buffer )
  {
    ExFreePoolWithTag(stru_140020300.Buffer - 6, 0);
    stru_140020300.Buffer = 0;
    *(_DWORD *)&stru_140020300.Length = 0;
  }
  if ( stru_140020310.Buffer )
  {
    ExFreePoolWithTag(stru_140020310.Buffer - 6, 0);
    stru_140020310.Buffer = 0;
    *(_DWORD *)&stru_140020310.Length = 0;
  }
  if ( s_pNegotiateSmb )
  {
    ExFreePoolWithTag((char *)s_pNegotiateSmb - 32, 0);
    s_pNegotiateSmb = 0;
  }
  if ( s_pNegotiateSmbRemoteBoot )
  {
    ExFreePoolWithTag((PVOID)(s_pNegotiateSmbRemoteBoot - 32), 0);
    s_pNegotiateSmbRemoteBoot = 0;
  }
  if ( MRxSmbSMB1UninstallServiceInitialized )
  {
    MRxSmbShutdownRecurrentService(MRxSmbSMB1UninstallServiceContext);
    KeFlushQueuedDpcs();
    MRxSmbSMB1UninstallServiceInitialized = 0;
  }
}

```

## disassembly

```asm
0x140032a30  mov     [rsp+arg_0], rbx
0x140032a35  push    rsi
0x140032a36  sub     rsp, 20h
0x140032a3a  call    wil_UninitializeFeatureStaging
0x140032a3f  lea     rcx, MRxSmbUnload; AddressWithinSection
0x140032a46  call    cs:__imp_MmResetDriverPaging
0x140032a4d  nop     dword ptr [rax+rax+00h]
0x140032a52  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140032a59  lea     rsi, WPP_GLOBAL_Control
0x140032a60  cmp     rcx, rsi
0x140032a63  jz      short loc_140032A83
0x140032a65  test    dword ptr [rcx+2Ch], 400h
0x140032a6c  jz      short loc_140032A83
0x140032a6e  mov     rcx, [rcx+18h]
0x140032a72  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x140032a79  mov     edx, 0Fh
0x140032a7e  call    WPP_SF_
0x140032a83  call    SmbCeDbTearDown
0x140032a88  call    SmbMmTearDown
0x140032a8d  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140032a94  xor     edx, edx
0x140032a96  mov     rcx, [rcx]
0x140032a99  call    cs:__imp_MRxSmbDeregisterDialect
0x140032aa0  nop     dword ptr [rax+rax+00h]
0x140032aa5  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140032aac  mov     edx, 1
0x140032ab1  mov     rcx, [rcx]
0x140032ab4  call    cs:__imp_MRxSmbDeregisterDialect
0x140032abb  nop     dword ptr [rax+rax+00h]
0x140032ac0  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140032ac7  mov     edx, 2
0x140032acc  mov     rcx, [rcx]
0x140032acf  call    cs:__imp_MRxSmbDeregisterDialect
0x140032ad6  nop     dword ptr [rax+rax+00h]
0x140032adb  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140032ae2  mov     edx, 3
0x140032ae7  mov     rcx, [rcx]
0x140032aea  call    cs:__imp_MRxSmbDeregisterDialect
0x140032af1  nop     dword ptr [rax+rax+00h]
0x140032af6  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140032afd  mov     edx, 4
0x140032b02  mov     rcx, [rcx]
0x140032b05  call    cs:__imp_MRxSmbDeregisterDialect
0x140032b0c  nop     dword ptr [rax+rax+00h]
0x140032b11  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140032b18  mov     edx, 5
0x140032b1d  mov     rcx, [rcx]
0x140032b20  call    cs:__imp_MRxSmbDeregisterDialect
0x140032b27  nop     dword ptr [rax+rax+00h]
0x140032b2c  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x140032b33  mov     rdx, cs:MRxSmb10SubRdrHandle
0x140032b3a  mov     rcx, [rcx]
0x140032b3d  call    cs:__imp_MRxSmbDeregisterSubRedirector
0x140032b44  nop     dword ptr [rax+rax+00h]
0x140032b49  mov     rcx, cs:MrxSmbCeGlobalPadding; P
0x140032b50  xor     ebx, ebx
0x140032b52  test    rcx, rcx
0x140032b55  jz      short loc_140032B6C
0x140032b57  xor     edx, edx; Tag
0x140032b59  call    cs:__imp_ExFreePoolWithTag
0x140032b60  nop     dword ptr [rax+rax+00h]
0x140032b65  mov     cs:MrxSmbCeGlobalPadding, rbx
0x140032b6c  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140032b73  call    cs:__imp_EtwUnregister
0x140032b7a  nop     dword ptr [rax+rax+00h]
0x140032b7f  mov     cs:Microsoft_Windows_Networking_CorrelationHandle, rbx
0x140032b86  test    eax, eax
0x140032b88  jz      short loc_140032BB7
0x140032b8a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140032b91  cmp     rcx, rsi
0x140032b94  jz      short loc_140032BB7
0x140032b96  test    dword ptr [rcx+2Ch], 400h
0x140032b9d  jz      short loc_140032BB7
0x140032b9f  mov     rcx, [rcx+18h]
0x140032ba3  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x140032baa  mov     edx, 0Dh
0x140032baf  mov     r9d, eax
0x140032bb2  call    WPP_SF_d
0x140032bb7  call    McGenEventUnregister_EtwUnregister
0x140032bbc  test    eax, eax
0x140032bbe  jz      short loc_140032BED
0x140032bc0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140032bc7  cmp     rcx, rsi
0x140032bca  jz      short loc_140032BED
0x140032bcc  test    dword ptr [rcx+2Ch], 400h
0x140032bd3  jz      short loc_140032BED
0x140032bd5  mov     rcx, [rcx+18h]
0x140032bd9  lea     r8, WPP_3ef6dccc05f63d6d417ef27503099bef_Traceguids
0x140032be0  mov     edx, 0Eh
0x140032be5  mov     r9d, eax
0x140032be8  call    WPP_SF_d
0x140032bed  call    TraceLoggingUnregister_EtwUnregister
0x140032bf2  call    WppCleanupKm
0x140032bf7  mov     rcx, cs:DestinationString.Buffer; P
0x140032bfe  test    rcx, rcx
0x140032c01  jz      short loc_140032C18
0x140032c03  xor     edx, edx; Tag
0x140032c05  call    cs:__imp_ExFreePoolWithTag
0x140032c0c  nop     dword ptr [rax+rax+00h]
0x140032c11  mov     cs:DestinationString.Buffer, rbx
0x140032c18  mov     rcx, cs:stru_1400202E0.Buffer; P
0x140032c1f  test    rcx, rcx
0x140032c22  jz      short loc_140032C39
0x140032c24  xor     edx, edx; Tag
0x140032c26  call    cs:__imp_ExFreePoolWithTag
0x140032c2d  nop     dword ptr [rax+rax+00h]
0x140032c32  mov     cs:stru_1400202E0.Buffer, rbx
0x140032c39  mov     rcx, cs:stru_1400202F0.Buffer; P
0x140032c40  test    rcx, rcx
0x140032c43  jz      short loc_140032C5A
0x140032c45  xor     edx, edx; Tag
0x140032c47  call    cs:__imp_ExFreePoolWithTag
0x140032c4e  nop     dword ptr [rax+rax+00h]
0x140032c53  mov     cs:stru_1400202F0.Buffer, rbx
0x140032c5a  mov     rcx, cs:SmbCeContext.Buffer; P
0x140032c61  test    rcx, rcx
0x140032c64  jz      short loc_140032C7B
0x140032c66  xor     edx, edx; Tag
0x140032c68  call    cs:__imp_ExFreePoolWithTag
0x140032c6f  nop     dword ptr [rax+rax+00h]
0x140032c74  mov     cs:SmbCeContext.Buffer, rbx
0x140032c7b  mov     rcx, cs:stru_140020300.Buffer
0x140032c82  test    rcx, rcx
0x140032c85  jz      short loc_140032CA6
0x140032c87  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x140032c8b  xor     edx, edx; Tag
0x140032c8d  call    cs:__imp_ExFreePoolWithTag
0x140032c94  nop     dword ptr [rax+rax+00h]
0x140032c99  mov     cs:stru_140020300.Buffer, rbx
0x140032ca0  mov     dword ptr cs:stru_140020300.Length, ebx
0x140032ca6  mov     rcx, cs:stru_140020310.Buffer
0x140032cad  test    rcx, rcx
0x140032cb0  jz      short loc_140032CD1
0x140032cb2  add     rcx, 0FFFFFFFFFFFFFFF4h; P
0x140032cb6  xor     edx, edx; Tag
0x140032cb8  call    cs:__imp_ExFreePoolWithTag
0x140032cbf  nop     dword ptr [rax+rax+00h]
0x140032cc4  mov     cs:stru_140020310.Buffer, rbx
0x140032ccb  mov     dword ptr cs:stru_140020310.Length, ebx
0x140032cd1  mov     rcx, cs:s_pNegotiateSmb
0x140032cd8  test    rcx, rcx
0x140032cdb  jz      short loc_140032CF6
0x140032cdd  add     rcx, 0FFFFFFFFFFFFFFE0h; P
0x140032ce1  xor     edx, edx; Tag
0x140032ce3  call    cs:__imp_ExFreePoolWithTag
0x140032cea  nop     dword ptr [rax+rax+00h]
0x140032cef  mov     cs:s_pNegotiateSmb, rbx
0x140032cf6  mov     rcx, cs:s_pNegotiateSmbRemoteBoot
0x140032cfd  test    rcx, rcx
0x140032d00  jz      short loc_140032D1B
0x140032d02  add     rcx, 0FFFFFFFFFFFFFFE0h; P
0x140032d06  xor     edx, edx; Tag
0x140032d08  call    cs:__imp_ExFreePoolWithTag
0x140032d0f  nop     dword ptr [rax+rax+00h]
0x140032d14  mov     cs:s_pNegotiateSmbRemoteBoot, rbx
0x140032d1b  cmp     cs:MRxSmbSMB1UninstallServiceInitialized, bl
0x140032d21  jz      short loc_140032D48
0x140032d23  lea     rcx, MRxSmbSMB1UninstallServiceContext
0x140032d2a  call    cs:__imp_MRxSmbShutdownRecurrentService
0x140032d31  nop     dword ptr [rax+rax+00h]
0x140032d36  call    cs:__imp_KeFlushQueuedDpcs
0x140032d3d  nop     dword ptr [rax+rax+00h]
0x140032d42  mov     cs:MRxSmbSMB1UninstallServiceInitialized, bl
0x140032d48  mov     rbx, [rsp+28h+arg_0]
0x140032d4d  add     rsp, 20h
0x140032d51  pop     rsi
0x140032d52  retn
```
