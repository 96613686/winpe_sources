# NdisWanTapiRequestProc

- ea: `0x140010b40`
- end: `0x140010dec`
- name: `NdisWanTapiRequestProc`
- size: `684`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation`

## callees

- `0x14000a290`
- `0x14000a2c0`
- `0x14000a5f4`
- `0x140010640`
- `0x140010b40`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x140010cf2`
- `ntoskrnl!KeInitializeEvent` at `0x140010cf2`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c48`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010dc7`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c2f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c48`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c63`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010c7c`
- `ntoskrnl!KeReleaseSpinLock` at `0x140010dc7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bc7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010c10`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010bc7`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140010c10`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010c8f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140010c8f`
- `NDIS!NdisSetEvent` at `0x140010cb7`
- `NDIS!NdisSetEvent` at `0x140010daa`
- `NDIS!NdisSetEvent` at `0x140010cb7`
- `NDIS!NdisSetEvent` at `0x140010daa`

## pseudocode

```c
__int64 __fastcall NdisWanTapiRequestProc(__int64 a1, __int64 a2)
{
  KIRQL v4; // al
  __int64 v5; // rbx
  __int64 v6; // rax
  KIRQL v7; // al
  int v8; // edx
  KSPIN_LOCK *v9; // rcx
  struct _KEVENT *v10; // rax
  struct _KEVENT *v11; // rdi
  unsigned int v13; // eax
  unsigned int v14; // edi

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u) && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_19c4b30392dd32e174279c73e079de55_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        11,
        WPP_19c4b30392dd32e174279c73e079de55_Traceguids,
        *(unsigned int *)(a2 + 32),
        *(_DWORD *)(a2 + 40));
    }
  }
  v4 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved);
  v5 = qword_14001E1B8;
  *((_BYTE *)&WPP_MAIN_CB.Reserved + 8) = v4;
  while ( 1 )
  {
    if ( (__int64 *)v5 == &qword_14001E1B8 )
    {
      KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, *((KIRQL *)&WPP_MAIN_CB.Reserved + 8));
      _InterlockedIncrement(&gulNdistapiMissedCount);
      return 3221225473LL;
    }
    v6 = *(_QWORD *)(v5 + 520);
    if ( v6 )
    {
      if ( v6 == a1 )
        break;
    }
    v5 = *(_QWORD *)v5;
  }
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v5 + 504));
  v8 = *(_DWORD *)(v5 + 20);
  v9 = (KSPIN_LOCK *)(v5 + 504);
  *(_BYTE *)(v5 + 512) = v7;
  if ( (v8 & 2) != 0 )
  {
    KeReleaseSpinLock(v9, v7);
    KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, *((KIRQL *)&WPP_MAIN_CB.Reserved + 8));
    return 3221225473LL;
  }
  _InterlockedIncrement((volatile signed __int32 *)(v5 + 16));
  KeReleaseSpinLock(v9, *(_BYTE *)(v5 + 512));
  KeReleaseSpinLock((PKSPIN_LOCK)&WPP_MAIN_CB.Reserved, *((KIRQL *)&WPP_MAIN_CB.Reserved + 8));
  v10 = (struct _KEVENT *)ExAllocateFromNPagedLookasideList(&WanRequestLegacyList);
  v11 = v10;
  if ( v10 )
  {
    LODWORD(v10->Header.WaitListHead.Blink) = 0;
    HIDWORD(v10->Header.WaitListHead.Blink) = 1;
    *(_QWORD *)&v10[1].Header.Lock = v5;
    v10[9].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)a2;
    KeInitializeEvent(v10 + 10, NotificationEvent, 0);
    LODWORD(v11[3].Header.WaitListHead.Flink) = *(_DWORD *)(a2 + 32);
    if ( *(_DWORD *)(a2 + 32) <= 1u )
    {
      LODWORD(v11[3].Header.WaitListHead.Blink) = *(_DWORD *)(a2 + 40);
      *(_QWORD *)&v11[4].Header.Lock = *(_QWORD *)(a2 + 48);
      LODWORD(v11[4].Header.WaitListHead.Flink) = *(_DWORD *)(a2 + 56);
      HIDWORD(v11[4].Header.WaitListHead.Flink) = *(_DWORD *)(a2 + 60);
    }
    v13 = NdisWanSubmitNdisRequestLegacy(v5, v11);
    v14 = v13;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
      if ( _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_19c4b30392dd32e174279c73e079de55_Traceguids, v13);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && _bittest((const signed __int32 *)&WPP_GLOBAL_Control->Timer + 1, 8u)
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 13, WPP_19c4b30392dd32e174279c73e079de55_Traceguids);
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 16), 0xFFFFFFFF) == 1 )
      NdisSetEvent((PNDIS_EVENT)(v5 + 552));
    return v14;
  }
  else
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v5 + 16), 0xFFFFFFFF) == 1 )
      NdisSetEvent((PNDIS_EVENT)(v5 + 552));
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140010b40  push    rbx
0x140010b42  push    rsi
0x140010b43  push    rdi
0x140010b44  push    r14
0x140010b46  push    r15
0x140010b48  sub     rsp, 30h
0x140010b4c  mov     rsi, rdx
0x140010b4f  mov     rdi, rcx
0x140010b52  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b59  lea     r15, WPP_GLOBAL_Control
0x140010b60  cmp     rcx, r15
0x140010b63  jz      short loc_140010BC0
0x140010b65  bt      dword ptr [rcx+2Ch], 8
0x140010b6a  jnb     short loc_140010B87
0x140010b6c  cmp     byte ptr [rcx+29h], 5
0x140010b70  jb      short loc_140010B87
0x140010b72  mov     rcx, [rcx+18h]
0x140010b76  lea     r8, WPP_19c4b30392dd32e174279c73e079de55_Traceguids
0x140010b7d  mov     edx, 0Ah
0x140010b82  call    WPP_SF_
0x140010b87  mov     rcx, cs:WPP_GLOBAL_Control
0x140010b8e  cmp     rcx, r15
0x140010b91  jz      short loc_140010BC0
0x140010b93  bt      dword ptr [rcx+2Ch], 8
0x140010b98  jnb     short loc_140010BC0
0x140010b9a  cmp     byte ptr [rcx+29h], 4
0x140010b9e  jb      short loc_140010BC0
0x140010ba0  mov     eax, [rsi+28h]
0x140010ba3  lea     r8, WPP_19c4b30392dd32e174279c73e079de55_Traceguids
0x140010baa  mov     r9d, [rsi+20h]
0x140010bae  mov     edx, 0Bh
0x140010bb3  mov     rcx, [rcx+18h]
0x140010bb7  mov     [rsp+58h+var_38], eax
0x140010bbb  call    WPP_SF_dd
0x140010bc0  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140010bc7  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010bce  nop     dword ptr [rax+rax+00h]
0x140010bd3  mov     rbx, cs:qword_14001E1B8
0x140010bda  mov     byte ptr cs:WPP_MAIN_CB+148h, al
0x140010be0  lea     rax, qword_14001E1B8
0x140010be7  cmp     rbx, rax
0x140010bea  jz      loc_140010DBA
0x140010bf0  mov     rax, [rbx+208h]
0x140010bf7  test    rax, rax
0x140010bfa  jz      short loc_140010C01
0x140010bfc  cmp     rax, rdi
0x140010bff  jz      short loc_140010C06
0x140010c01  mov     rbx, [rbx]
0x140010c04  jmp     short loc_140010BE0
0x140010c06  lea     rdi, [rbx+1F8h]
0x140010c0d  mov     rcx, rdi; SpinLock
0x140010c10  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140010c17  nop     dword ptr [rax+rax+00h]
0x140010c1c  mov     edx, [rbx+14h]
0x140010c1f  mov     rcx, rdi; SpinLock
0x140010c22  mov     [rbx+200h], al
0x140010c28  test    dl, 2
0x140010c2b  jz      short loc_140010C59
0x140010c2d  mov     dl, al; NewIrql
0x140010c2f  call    cs:__imp_KeReleaseSpinLock
0x140010c36  nop     dword ptr [rax+rax+00h]
0x140010c3b  mov     dl, byte ptr cs:WPP_MAIN_CB+148h; NewIrql
0x140010c41  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140010c48  call    cs:__imp_KeReleaseSpinLock
0x140010c4f  nop     dword ptr [rax+rax+00h]
0x140010c54  jmp     loc_140010DDA
0x140010c59  lock inc dword ptr [rbx+10h]
0x140010c5d  mov     dl, [rbx+200h]; NewIrql
0x140010c63  call    cs:__imp_KeReleaseSpinLock
0x140010c6a  nop     dword ptr [rax+rax+00h]
0x140010c6f  mov     dl, byte ptr cs:WPP_MAIN_CB+148h; NewIrql
0x140010c75  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140010c7c  call    cs:__imp_KeReleaseSpinLock
0x140010c83  nop     dword ptr [rax+rax+00h]
0x140010c88  lea     rcx, WanRequestLegacyList; Lookaside
0x140010c8f  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140010c96  nop     dword ptr [rax+rax+00h]
0x140010c9b  mov     rdi, rax
0x140010c9e  test    rax, rax
0x140010ca1  jnz     short loc_140010CCD
0x140010ca3  or      eax, 0FFFFFFFFh
0x140010ca6  lock xadd [rbx+10h], eax
0x140010cab  cmp     eax, 1
0x140010cae  jnz     short loc_140010CC3
0x140010cb0  lea     rcx, [rbx+228h]; Event
0x140010cb7  call    cs:__imp_NdisSetEvent
0x140010cbe  nop     dword ptr [rax+rax+00h]
0x140010cc3  mov     eax, 0C000009Ah
0x140010cc8  jmp     loc_140010DDF
0x140010ccd  lea     rcx, [rax+0F0h]; Event
0x140010cd4  mov     dword ptr [rax+10h], 0
0x140010cdb  xor     r8d, r8d; State
0x140010cde  mov     dword ptr [rax+14h], 1
0x140010ce5  xor     edx, edx; Type
0x140010ce7  mov     [rax+18h], rbx
0x140010ceb  mov     [rax+0E0h], rsi
0x140010cf2  call    cs:__imp_KeInitializeEvent
0x140010cf9  nop     dword ptr [rax+rax+00h]
0x140010cfe  mov     eax, [rsi+20h]
0x140010d01  mov     [rdi+50h], eax
0x140010d04  mov     eax, [rsi+20h]
0x140010d07  test    eax, eax
0x140010d09  jz      short loc_140010D10
0x140010d0b  cmp     eax, 1
0x140010d0e  jnz     short loc_140010D2A
0x140010d10  mov     eax, [rsi+28h]
0x140010d13  mov     [rdi+58h], eax
0x140010d16  mov     rax, [rsi+30h]
0x140010d1a  mov     [rdi+60h], rax
0x140010d1e  mov     eax, [rsi+38h]
0x140010d21  mov     [rdi+68h], eax
0x140010d24  mov     eax, [rsi+3Ch]
0x140010d27  mov     [rdi+6Ch], eax
0x140010d2a  mov     rdx, rdi
0x140010d2d  mov     rcx, rbx
0x140010d30  call    NdisWanSubmitNdisRequestLegacy
0x140010d35  mov     edi, eax
0x140010d37  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d3e  cmp     rcx, r15
0x140010d41  jz      short loc_140010D96
0x140010d43  bt      dword ptr [rcx+2Ch], 8
0x140010d48  jnb     short loc_140010D68
0x140010d4a  cmp     byte ptr [rcx+29h], 4
0x140010d4e  jb      short loc_140010D68
0x140010d50  mov     rcx, [rcx+18h]
0x140010d54  lea     r8, WPP_19c4b30392dd32e174279c73e079de55_Traceguids
0x140010d5b  mov     edx, 0Ch
0x140010d60  mov     r9d, eax
0x140010d63  call    WPP_SF_d
0x140010d68  mov     rcx, cs:WPP_GLOBAL_Control
0x140010d6f  cmp     rcx, r15
0x140010d72  jz      short loc_140010D96
0x140010d74  bt      dword ptr [rcx+2Ch], 8
0x140010d79  jnb     short loc_140010D96
0x140010d7b  cmp     byte ptr [rcx+29h], 5
0x140010d7f  jb      short loc_140010D96
0x140010d81  mov     rcx, [rcx+18h]
0x140010d85  lea     r8, WPP_19c4b30392dd32e174279c73e079de55_Traceguids
0x140010d8c  mov     edx, 0Dh
0x140010d91  call    WPP_SF_
0x140010d96  or      eax, 0FFFFFFFFh
0x140010d99  lock xadd [rbx+10h], eax
0x140010d9e  cmp     eax, 1
0x140010da1  jnz     short loc_140010DB6
0x140010da3  lea     rcx, [rbx+228h]; Event
0x140010daa  call    cs:__imp_NdisSetEvent
0x140010db1  nop     dword ptr [rax+rax+00h]
0x140010db6  mov     eax, edi
0x140010db8  jmp     short loc_140010DDF
0x140010dba  mov     dl, byte ptr cs:WPP_MAIN_CB+148h; NewIrql
0x140010dc0  lea     rcx, WPP_MAIN_CB.Reserved; SpinLock
0x140010dc7  call    cs:__imp_KeReleaseSpinLock
0x140010dce  nop     dword ptr [rax+rax+00h]
0x140010dd3  lock inc cs:gulNdistapiMissedCount
0x140010dda  mov     eax, 0C0000001h
0x140010ddf  add     rsp, 30h
0x140010de3  pop     r15
0x140010de5  pop     r14
0x140010de7  pop     rdi
0x140010de8  pop     rsi
0x140010de9  pop     rbx
0x140010dea  retn
```
