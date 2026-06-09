# RxUnload

- ea: `0x1400499a0`
- end: `0x140049b2f`
- name: `RxUnload`
- size: `399`
- prototype: `void __stdcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `0`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140016e20`
- `0x140016e70`
- `0x14001c894`
- `0x14001fc70`
- `0x140020954`
- `0x1400491d4`
- `0x1400499a0`
- `0x140049b38`
- `0x14004a03c`

## import_xrefs

- `ntoskrnl!ExDeleteResourceLite` at `0x1400499f7`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400499f7`
- `ntoskrnl!EtwUnregister` at `0x140049a86`
- `ntoskrnl!EtwUnregister` at `0x140049a86`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a56`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a18`
- `ntoskrnl!ExFreePoolWithTag` at `0x140049a56`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140049a36`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x140049a36`

## pseudocode

```c
void __stdcall RxUnload(PDRIVER_OBJECT DriverObject)
{
  __int64 i; // rbx
  void *v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // r8
  unsigned int v6; // eax
  unsigned int v7; // eax

  RxTearDownRxTimer();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_7b7fb28597d5336b708e27863935177e_Traceguids, DriverObject);
  }
  ExDeleteResourceLite(&Resource);
  if ( P != RxpNodes )
    ExFreePoolWithTag(P, 0);
  P = 0;
  ExDeleteNPagedLookasideList(&RxWorkItemLookasideList);
  for ( i = 0; i != 8; ++i )
  {
    v3 = (void *)MustSucceedRxContexts[i];
    if ( v3 )
    {
      ExFreePoolWithTag(v3, 0);
      MustSucceedRxContexts[i] = 0;
    }
  }
  RxFreeTurboIoResources();
  RxInitUnwind(v4, 0, v5);
  v6 = EtwUnregister(Microsoft_Windows_Networking_CorrelationHandle);
  Microsoft_Windows_Networking_CorrelationHandle = 0;
  if ( v6
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_7b7fb28597d5336b708e27863935177e_Traceguids, v6);
  }
  v7 = McGenEventUnregister_EtwUnregister();
  if ( v7
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_7b7fb28597d5336b708e27863935177e_Traceguids, v7);
  }
  WppCleanupKm();
  wil_UninitializeFeatureStaging();
  RxIsLoadedAsDriver = 0;
}

```

## disassembly

```asm
0x1400499a0  mov     [rsp+arg_0], rbx
0x1400499a5  mov     [rsp+arg_8], r14
0x1400499aa  push    r15
0x1400499ac  sub     rsp, 20h
0x1400499b0  mov     rbx, rcx
0x1400499b3  call    RxTearDownRxTimer
0x1400499b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400499bf  lea     r15, WPP_GLOBAL_Control
0x1400499c6  cmp     rcx, r15
0x1400499c9  jz      short loc_1400499F0
0x1400499cb  mov     eax, [rcx+2Ch]
0x1400499ce  test    al, 2
0x1400499d0  jz      short loc_1400499F0
0x1400499d2  cmp     byte ptr [rcx+29h], 4
0x1400499d6  jb      short loc_1400499F0
0x1400499d8  mov     rcx, [rcx+18h]
0x1400499dc  lea     r8, WPP_7b7fb28597d5336b708e27863935177e_Traceguids
0x1400499e3  mov     edx, 0Ch
0x1400499e8  mov     r9, rbx
0x1400499eb  call    WPP_SF_q
0x1400499f0  lea     rcx, Resource; Resource
0x1400499f7  call    cs:__imp_ExDeleteResourceLite
0x1400499fe  nop     dword ptr [rax+rax+00h]
0x140049a03  mov     rcx, cs:P; P
0x140049a0a  lea     rax, RxpNodes
0x140049a11  cmp     rcx, rax
0x140049a14  jz      short loc_140049A24
0x140049a16  xor     edx, edx; Tag
0x140049a18  call    cs:__imp_ExFreePoolWithTag
0x140049a1f  nop     dword ptr [rax+rax+00h]
0x140049a24  lea     rcx, RxWorkItemLookasideList; Lookaside
0x140049a2b  mov     cs:P, 0
0x140049a36  call    cs:__imp_ExDeleteNPagedLookasideList
0x140049a3d  nop     dword ptr [rax+rax+00h]
0x140049a42  xor     ebx, ebx
0x140049a44  lea     r14, MustSucceedRxContexts
0x140049a4b  mov     rcx, [r14+rbx*8]; P
0x140049a4f  test    rcx, rcx
0x140049a52  jz      short loc_140049A6A
0x140049a54  xor     edx, edx; Tag
0x140049a56  call    cs:__imp_ExFreePoolWithTag
0x140049a5d  nop     dword ptr [rax+rax+00h]
0x140049a62  mov     qword ptr [r14+rbx*8], 0
0x140049a6a  inc     rbx
0x140049a6d  cmp     rbx, 8
0x140049a71  jnz     short loc_140049A44
0x140049a73  call    RxFreeTurboIoResources
0x140049a78  xor     edx, edx
0x140049a7a  call    RxInitUnwind
0x140049a7f  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x140049a86  call    cs:__imp_EtwUnregister
0x140049a8d  nop     dword ptr [rax+rax+00h]
0x140049a92  mov     cs:Microsoft_Windows_Networking_CorrelationHandle, 0
0x140049a9d  test    eax, eax
0x140049a9f  jz      short loc_140049AD1
0x140049aa1  mov     rcx, cs:WPP_GLOBAL_Control
0x140049aa8  cmp     rcx, r15
0x140049aab  jz      short loc_140049AD1
0x140049aad  mov     edx, [rcx+2Ch]
0x140049ab0  test    dl, 2
0x140049ab3  jz      short loc_140049AD1
0x140049ab5  cmp     byte ptr [rcx+29h], 4
0x140049ab9  jb      short loc_140049AD1
0x140049abb  mov     rcx, [rcx+18h]
0x140049abf  lea     edx, [rbx+5]
0x140049ac2  mov     r9d, eax
0x140049ac5  lea     r8, WPP_7b7fb28597d5336b708e27863935177e_Traceguids
0x140049acc  call    WPP_SF_d
0x140049ad1  call    McGenEventUnregister_EtwUnregister
0x140049ad6  test    eax, eax
0x140049ad8  jz      short loc_140049B0C
0x140049ada  mov     rcx, cs:WPP_GLOBAL_Control
0x140049ae1  cmp     rcx, r15
0x140049ae4  jz      short loc_140049B0C
0x140049ae6  mov     edx, [rcx+2Ch]
0x140049ae9  test    dl, 2
0x140049aec  jz      short loc_140049B0C
0x140049aee  cmp     byte ptr [rcx+29h], 4
0x140049af2  jb      short loc_140049B0C
0x140049af4  mov     rcx, [rcx+18h]
0x140049af8  lea     r8, WPP_7b7fb28597d5336b708e27863935177e_Traceguids
0x140049aff  mov     edx, 0Eh
0x140049b04  mov     r9d, eax
0x140049b07  call    WPP_SF_d
0x140049b0c  call    WppCleanupKm
0x140049b11  call    wil_UninitializeFeatureStaging
0x140049b16  mov     rbx, [rsp+28h+arg_0]
0x140049b1b  mov     r14, [rsp+28h+arg_8]
0x140049b20  mov     cs:RxIsLoadedAsDriver, 0
0x140049b27  add     rsp, 20h
0x140049b2b  pop     r15
0x140049b2d  retn
```
