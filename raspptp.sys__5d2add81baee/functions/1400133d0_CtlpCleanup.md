# CtlpCleanup

- ea: `0x1400133d0`
- end: `0x1400137a6`
- name: `CtlpCleanup`
- size: `982`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `broker_com_uri`

## callees

- `0x140001a70`
- `0x140002e78`
- `0x1400039f8`
- `0x140003e08`
- `0x140003e38`
- `0x140004204`
- `0x140007710`
- `0x1400133d0`
- `0x1400157f4`
- `0x14001587c`
- `0x14001c1a0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140013701`
- `ntoskrnl!KeSetEvent` at `0x140013731`
- `ntoskrnl!KeSetEvent` at `0x140013701`
- `ntoskrnl!KeSetEvent` at `0x140013731`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001364b`
- `ntoskrnl!ExWaitForRundownProtectionRelease` at `0x14001364b`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140013780`
- `ntoskrnl!KeWaitForMultipleObjects` at `0x140013780`
- `ntoskrnl!ExRundownCompleted` at `0x14001365b`
- `ntoskrnl!ExRundownCompleted` at `0x14001365b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001348b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001358b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013607`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400136d1`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001348b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001358b`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013607`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400136d1`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013422`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013550`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400135ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013790`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013422`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013550`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400135ad`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013790`
- `NDIS!NdisCancelTimerObject` at `0x14001359e`
- `NDIS!NdisCancelTimerObject` at `0x1400136e4`
- `NDIS!NdisCancelTimerObject` at `0x140013714`
- `NDIS!NdisCancelTimerObject` at `0x14001359e`
- `NDIS!NdisCancelTimerObject` at `0x1400136e4`
- `NDIS!NdisCancelTimerObject` at `0x140013714`

## pseudocode

```c
__int64 __fastcall CtlpCleanup(__int64 a1)
{
  __int64 v1; // rdi
  KIRQL v2; // al
  _QWORD *v3; // rbp
  char v4; // si
  KIRQL v5; // dl
  __int64 v6; // r8
  __int64 i; // rax
  __int64 v8; // r8
  __int64 v9; // rbx
  KIRQL v10; // al
  __int64 v11; // r9
  __int64 result; // rax
  PVOID Object[2]; // [rsp+40h] [rbp-38h] BYREF
  __int64 v14; // [rsp+50h] [rbp-28h]

  v1 = *(_QWORD *)(a1 + 24);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
  }
  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  v3 = (_QWORD *)(v1 + 56);
  *(_BYTE *)(v1 + 104) = v2;
  v4 = 1;
  v5 = v2;
  if ( (_QWORD *)*v3 != v3 )
  {
    *(_OWORD *)Object = 0;
    v14 = 0;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids);
    }
    _InterlockedAdd((volatile signed __int32 *)(v1 + 16), 1u);
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), *(_BYTE *)(v1 + 104));
    v6 = *(_QWORD *)(v1 + 40) + 8LL;
    Object[1] = 0;
    Object[0] = 0;
    LODWORD(v14) = 1297436229;
    for ( i = EnumListEntry(v1 + 56, Object, v6, 0); i; i = EnumListEntry(
                                                              v1 + 56,
                                                              Object,
                                                              *(_QWORD *)(v1 + 40) + 8LL,
                                                              0) )
    {
      v9 = i - 16;
      if ( i != 16 && *(_DWORD *)(v9 + 48) == 1129337936 )
      {
        CallSetState(i - 16, 11, v8, 0);
        CallCleanup(v9);
        DereferenceRefCount(v9);
      }
    }
    EnumComplete(Object, *(_QWORD *)(v1 + 40) + 8LL);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(__int64))(v1 + 24))(v1);
    v10 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
    *(_BYTE *)(v1 + 104) = v10;
    v5 = v10;
    if ( (_QWORD *)*v3 != v3 )
      goto LABEL_26;
  }
  if ( *(_QWORD *)(v1 + 120) != v1 + 120 )
    goto LABEL_26;
  if ( !*(_BYTE *)(v1 + 589) )
  {
    *(_BYTE *)(v1 + 589) = 1;
    KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v5);
    NdisCancelTimerObject(*(NDIS_HANDLE *)(v1 + 576));
    v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
    *(_BYTE *)(v1 + 104) = v5;
  }
  v11 = *(unsigned int *)(v1 + 16);
  if ( (_DWORD)v11 != 2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, v11);
      v5 = *(_BYTE *)(v1 + 104);
    }
LABEL_26:
    v4 = 0;
    *(_BYTE *)(v1 + 112) = 0;
    goto LABEL_27;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v5);
  if ( NdisCancelTimerObject(*(NDIS_HANDLE *)(v1 + 592)) == 1 )
    KeSetEvent((PRKEVENT)(v1 + 608), 0, 0);
  if ( NdisCancelTimerObject(*(NDIS_HANDLE *)(v1 + 600)) == 1 )
    KeSetEvent((PRKEVENT)(v1 + 632), 0, 0);
  Object[0] = (PVOID)(v1 + 608);
  Object[1] = (PVOID)(v1 + 632);
  KeWaitForMultipleObjects(2u, Object, WaitAll, Executive, 0, 0, 0, 0);
  v5 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 96));
  *(_BYTE *)(v1 + 104) = v5;
LABEL_27:
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 96), v5);
  result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF);
  if ( (_DWORD)result == 1 )
    result = (*(__int64 (__fastcall **)(__int64))(v1 + 24))(v1);
  if ( v4 )
  {
    if ( !*(_BYTE *)(v1 + 72) )
      DeleteHostRoute(v1 + 368);
    ExWaitForRundownProtectionRelease((PEX_RUNDOWN_REF)(v1 + 88));
    ExRundownCompleted((PEX_RUNDOWN_REF)(v1 + 88));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids, v1);
    }
    result = (unsigned int)_InterlockedExchangeAdd((volatile signed __int32 *)(v1 + 16), 0xFFFFFFFF);
    if ( (_DWORD)result == 1 )
      return (*(__int64 (__fastcall **)(__int64))(v1 + 24))(v1);
  }
  return result;
}

```

## disassembly

```asm
0x1400133d0  mov     [rsp+arg_8], rbx
0x1400133d5  mov     [rsp+arg_10], rbp
0x1400133da  push    rsi
0x1400133db  push    rdi
0x1400133dc  push    r14
0x1400133de  sub     rsp, 60h
0x1400133e2  mov     rdi, [rcx+18h]
0x1400133e6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400133ed  lea     rbx, WPP_GLOBAL_Control
0x1400133f4  cmp     rcx, rbx
0x1400133f7  jz      short loc_14001341B
0x1400133f9  mov     eax, [rcx+2Ch]
0x1400133fc  test    al, 8
0x1400133fe  jz      short loc_14001341B
0x140013400  cmp     byte ptr [rcx+29h], 2
0x140013404  jb      short loc_14001341B
0x140013406  mov     rcx, [rcx+18h]
0x14001340a  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140013411  mov     edx, 12h
0x140013416  call    WPP_SF_
0x14001341b  lea     r14, [rdi+60h]
0x14001341f  mov     rcx, r14; SpinLock
0x140013422  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013429  nop     dword ptr [rax+rax+00h]
0x14001342e  lea     rbp, [rdi+38h]
0x140013432  mov     [rdi+68h], al
0x140013435  mov     esi, 1
0x14001343a  mov     dl, al
0x14001343c  cmp     [rbp+0], rbp
0x140013440  jz      loc_14001356B
0x140013446  xorps   xmm0, xmm0
0x140013449  xor     eax, eax
0x14001344b  movups  xmmword ptr [rsp+78h+Object], xmm0
0x140013450  mov     [rsp+78h+var_28], rax
0x140013455  mov     rcx, cs:WPP_GLOBAL_Control
0x14001345c  cmp     rcx, rbx
0x14001345f  jz      short loc_140013481
0x140013461  mov     eax, [rcx+2Ch]
0x140013464  test    al, 8
0x140013466  jz      short loc_140013481
0x140013468  cmp     byte ptr [rcx+29h], 2
0x14001346c  jb      short loc_140013481
0x14001346e  mov     rcx, [rcx+18h]
0x140013472  lea     edx, [rsi+12h]
0x140013475  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x14001347c  call    WPP_SF_
0x140013481  lock add [rdi+10h], esi
0x140013485  mov     dl, [rdi+68h]; NewIrql
0x140013488  mov     rcx, r14; SpinLock
0x14001348b  call    cs:__imp_KeReleaseSpinLock
0x140013492  nop     dword ptr [rax+rax+00h]
0x140013497  mov     r8, [rdi+28h]
0x14001349b  lea     rdx, [rsp+78h+Object]
0x1400134a0  add     r8, 8
0x1400134a4  mov     [rsp+78h+Object+8], 0
0x1400134ad  xor     r9d, r9d
0x1400134b0  mov     [rsp+78h+Object], 0
0x1400134b9  mov     rcx, rbp
0x1400134bc  mov     dword ptr [rsp+78h+var_28], 4D554E45h
0x1400134c4  call    EnumListEntry
0x1400134c9  test    rax, rax
0x1400134cc  jz      short loc_140013523
0x1400134ce  lea     rbx, [rax-10h]
0x1400134d2  test    rbx, rbx
0x1400134d5  jz      short loc_1400134FF
0x1400134d7  cmp     dword ptr [rbx+30h], 43505450h
0x1400134de  jnz     short loc_1400134FF
0x1400134e0  xor     r9d, r9d
0x1400134e3  mov     rcx, rbx
0x1400134e6  lea     edx, [r9+0Bh]
0x1400134ea  call    CallSetState
0x1400134ef  mov     rcx, rbx
0x1400134f2  call    CallCleanup
0x1400134f7  mov     rcx, rbx
0x1400134fa  call    DereferenceRefCount
0x1400134ff  mov     r8, [rdi+28h]
0x140013503  lea     rdx, [rsp+78h+Object]
0x140013508  add     r8, 8
0x14001350c  xor     r9d, r9d
0x14001350f  mov     rcx, rbp
0x140013512  call    EnumListEntry
0x140013517  test    rax, rax
0x14001351a  jnz     short loc_1400134CE
0x14001351c  lea     rbx, WPP_GLOBAL_Control
0x140013523  mov     rdx, [rdi+28h]
0x140013527  lea     rcx, [rsp+78h+Object]
0x14001352c  add     rdx, 8
0x140013530  call    EnumComplete
0x140013535  or      eax, 0FFFFFFFFh
0x140013538  lock xadd [rdi+10h], eax
0x14001353d  cmp     eax, esi
0x14001353f  jnz     short loc_14001354D
0x140013541  mov     rax, [rdi+18h]
0x140013545  mov     rcx, rdi
0x140013548  call    _guard_dispatch_icall
0x14001354d  mov     rcx, r14; SpinLock
0x140013550  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013557  nop     dword ptr [rax+rax+00h]
0x14001355c  mov     [rdi+68h], al
0x14001355f  mov     dl, al; NewIrql
0x140013561  cmp     [rbp+0], rbp
0x140013565  jnz     loc_1400135FD
0x14001356b  lea     rax, [rdi+78h]
0x14001356f  cmp     [rax], rax
0x140013572  jnz     loc_1400135FD
0x140013578  cmp     byte ptr [rdi+24Dh], 0
0x14001357f  jnz     short loc_1400135BE
0x140013581  mov     rcx, r14; SpinLock
0x140013584  mov     [rdi+24Dh], sil
0x14001358b  call    cs:__imp_KeReleaseSpinLock
0x140013592  nop     dword ptr [rax+rax+00h]
0x140013597  mov     rcx, [rdi+240h]; TimerObject
0x14001359e  call    cs:__imp_NdisCancelTimerObject
0x1400135a5  nop     dword ptr [rax+rax+00h]
0x1400135aa  mov     rcx, r14; SpinLock
0x1400135ad  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400135b4  nop     dword ptr [rax+rax+00h]
0x1400135b9  mov     dl, al; NewIrql
0x1400135bb  mov     [rdi+68h], al
0x1400135be  mov     r9d, [rdi+10h]
0x1400135c2  cmp     r9d, 2
0x1400135c6  jz      loc_1400136CE
0x1400135cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1400135d3  cmp     rcx, rbx
0x1400135d6  jz      short loc_1400135FD
0x1400135d8  mov     eax, [rcx+2Ch]
0x1400135db  test    al, 8
0x1400135dd  jz      short loc_1400135FD
0x1400135df  cmp     byte ptr [rcx+29h], 2
0x1400135e3  jb      short loc_1400135FD
0x1400135e5  mov     rcx, [rcx+18h]
0x1400135e9  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x1400135f0  mov     edx, 14h
0x1400135f5  call    WPP_SF_d
0x1400135fa  mov     dl, [rdi+68h]; NewIrql
0x1400135fd  xor     sil, sil
0x140013600  mov     [rdi+70h], sil
0x140013604  mov     rcx, r14; SpinLock
0x140013607  call    cs:__imp_KeReleaseSpinLock
0x14001360e  nop     dword ptr [rax+rax+00h]
0x140013613  or      eax, 0FFFFFFFFh
0x140013616  lock xadd [rdi+10h], eax
0x14001361b  cmp     eax, 1
0x14001361e  jnz     short loc_14001362C
0x140013620  mov     rax, [rdi+18h]
0x140013624  mov     rcx, rdi
0x140013627  call    _guard_dispatch_icall
0x14001362c  test    sil, sil
0x14001362f  jz      loc_1400136B8
0x140013635  cmp     byte ptr [rdi+48h], 0
0x140013639  jnz     short loc_140013647
0x14001363b  lea     rcx, [rdi+170h]
0x140013642  call    DeleteHostRoute
0x140013647  lea     rcx, [rdi+58h]; RunRef
0x14001364b  call    cs:__imp_ExWaitForRundownProtectionRelease
0x140013652  nop     dword ptr [rax+rax+00h]
0x140013657  lea     rcx, [rdi+58h]; RunRef
0x14001365b  call    cs:__imp_ExRundownCompleted
0x140013662  nop     dword ptr [rax+rax+00h]
0x140013667  mov     rcx, cs:WPP_GLOBAL_Control
0x14001366e  lea     rax, WPP_GLOBAL_Control
0x140013675  cmp     rcx, rax
0x140013678  jz      short loc_14001369F
0x14001367a  mov     eax, [rcx+2Ch]
0x14001367d  test    al, 8
0x14001367f  jz      short loc_14001369F
0x140013681  cmp     byte ptr [rcx+29h], 4
0x140013685  jb      short loc_14001369F
0x140013687  mov     rcx, [rcx+18h]
0x14001368b  lea     r8, WPP_241c3b8731ba33e7c3b6eb57ebf1758d_Traceguids
0x140013692  mov     edx, 15h
0x140013697  mov     r9, rdi
0x14001369a  call    WPP_SF_q
0x14001369f  or      eax, 0FFFFFFFFh
0x1400136a2  lock xadd [rdi+10h], eax
0x1400136a7  cmp     eax, 1
0x1400136aa  jnz     short loc_1400136B8
0x1400136ac  mov     rax, [rdi+18h]
0x1400136b0  mov     rcx, rdi
0x1400136b3  call    _guard_dispatch_icall
0x1400136b8  lea     r11, [rsp+78h+var_18]
0x1400136bd  mov     rbx, [r11+28h]
0x1400136c1  mov     rbp, [r11+30h]
0x1400136c5  mov     rsp, r11
0x1400136c8  pop     r14
0x1400136ca  pop     rdi
0x1400136cb  pop     rsi
0x1400136cc  retn
0x1400136ce  mov     rcx, r14; SpinLock
0x1400136d1  call    cs:__imp_KeReleaseSpinLock
0x1400136d8  nop     dword ptr [rax+rax+00h]
0x1400136dd  mov     rcx, [rdi+250h]; TimerObject
0x1400136e4  call    cs:__imp_NdisCancelTimerObject
0x1400136eb  nop     dword ptr [rax+rax+00h]
0x1400136f0  cmp     al, sil
0x1400136f3  jnz     short loc_14001370D
0x1400136f5  lea     rcx, [rdi+260h]; Event
0x1400136fc  xor     r8d, r8d; Wait
0x1400136ff  xor     edx, edx; Increment
0x140013701  call    cs:__imp_KeSetEvent
0x140013708  nop     dword ptr [rax+rax+00h]
0x14001370d  mov     rcx, [rdi+258h]; TimerObject
0x140013714  call    cs:__imp_NdisCancelTimerObject
0x14001371b  nop     dword ptr [rax+rax+00h]
0x140013720  cmp     al, sil
0x140013723  jnz     short loc_14001373D
0x140013725  lea     rcx, [rdi+278h]; Event
0x14001372c  xor     r8d, r8d; Wait
0x14001372f  xor     edx, edx; Increment
0x140013731  call    cs:__imp_KeSetEvent
0x140013738  nop     dword ptr [rax+rax+00h]
0x14001373d  mov     [rsp+78h+WaitBlockArray], 0; WaitBlockArray
0x140013746  lea     rax, [rdi+260h]
0x14001374d  xor     r9d, r9d; WaitReason
0x140013750  mov     [rsp+78h+Object], rax
0x140013755  lea     rax, [rdi+278h]
0x14001375c  mov     [rsp+78h+Timeout], 0; Timeout
0x140013765  mov     [rsp+78h+Alertable], 0; Alertable
0x14001376a  lea     rdx, [rsp+78h+Object]; Object
0x14001376f  xor     r8d, r8d; WaitType
0x140013772  mov     [rsp+78h+Object+8], rax
0x140013777  lea     ecx, [r9+2]; Count
0x14001377b  mov     [rsp+78h+WaitMode], 0; WaitMode
0x140013780  call    cs:__imp_KeWaitForMultipleObjects
0x140013787  nop     dword ptr [rax+rax+00h]
0x14001378c  lea     rcx, [rdi+60h]; SpinLock
0x140013790  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013797  nop     dword ptr [rax+rax+00h]
0x14001379c  mov     dl, al
0x14001379e  mov     [rdi+68h], al
0x1400137a1  jmp     loc_140013604
```
