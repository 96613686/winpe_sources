# VmbusTlConnectIoRequestCompleted

- ea: `0x140007794`
- end: `0x140007af8`
- name: `VmbusTlConnectIoRequestCompleted`
- size: `868`
- prototype: `__int64 __fastcall(char *P, char *)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140006260`
- `0x14000aa50`
- `0x14000b740`

## callees

- `0x140003bc8`
- `0x1400048f4`
- `0x1400058d0`
- `0x1400076d0`
- `0x140007794`
- `0x140009834`
- `0x14000a048`
- `0x14000bfe0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400077bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007851`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400077bf`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140007851`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400077f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000788a`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400077f8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000788a`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ad5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400079c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007ad5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400079b0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007abf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400079b0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140007abf`

## string_xrefs

- `0x140007950`: `VmbusTlConnectIoRequestCompleted`
- `0x1400079f8`: `VmbusTlConnectIoRequestCompleted`
- `0x140007a67`: `VmbusTlConnectIoRequestCompleted`

## pseudocode

```c
__int64 __fastcall VmbusTlConnectIoRequestCompleted(char *P, char *a2)
{
  _QWORD *v2; // rsi
  KSPIN_LOCK *v5; // rbp
  KIRQL v6; // al
  __int64 v7; // r8
  _QWORD *v8; // rdx
  __int64 v9; // rcx
  volatile signed __int32 *v10; // rax
  KSPIN_LOCK *v11; // rbp
  KIRQL v12; // al
  __int64 v13; // r8
  _QWORD *v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // rax
  void (__fastcall *v17)(char *); // rax
  __int64 v18; // rax
  __int64 v19; // rax
  void (__fastcall *v20)(char *); // rax

  v2 = a2 + 104;
  if ( *((_DWORD *)a2 + 30) == 1 )
  {
    v5 = (KSPIN_LOCK *)(P + 816);
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 102);
    v7 = *v2;
    if ( *(_QWORD **)(*v2 + 8LL) == v2 )
    {
      v8 = (_QWORD *)v2[1];
      if ( (_QWORD *)*v8 == v2 )
      {
        *v8 = v7;
        *(_QWORD *)(v7 + 8) = v8;
        v2[1] = v2;
        *v2 = v2;
        KeReleaseSpinLock(v5, v6);
        VmbusTlCompleteIoRequestToClient(v9, a2, *(unsigned int *)(*((_QWORD *)a2 + 28) + 48LL));
        if ( !*(_DWORD *)(*((_QWORD *)a2 + 28) + 48LL) )
          _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)P + 14) + 1120LL), *((_QWORD *)a2 + 25));
        v10 = (volatile signed __int32 *)(*((_QWORD *)P + 14) + 1272LL);
        goto LABEL_21;
      }
    }
LABEL_52:
    __fastfail(3u);
  }
  v11 = (KSPIN_LOCK *)(P + 848);
  v12 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)P + 106);
  v13 = *v2;
  if ( *(_QWORD **)(*v2 + 8LL) != v2 )
    goto LABEL_52;
  v14 = (_QWORD *)v2[1];
  if ( (_QWORD *)*v14 != v2 )
    goto LABEL_52;
  *v14 = v13;
  *(_QWORD *)(v13 + 8) = v14;
  v2[1] = v2;
  *v2 = v2;
  KeReleaseSpinLock(v11, v12);
  if ( (unsigned int)(*((_DWORD *)P + 131) - 17) <= 2 )
  {
    v15 = *(unsigned int *)(*((_QWORD *)a2 + 28) + 48LL);
    if ( ((_DWORD)v15 == -1073741247 || (_DWORD)v15 == -1073741536) && !(unsigned __int8)VmbusTlIsDisconnectAbortive(P) )
      *(_DWORD *)(*((_QWORD *)a2 + 28) + 48LL) = 0;
  }
  VmbusTlCompleteIoRequestToClient(v15, a2, *(unsigned int *)(*((_QWORD *)a2 + 28) + 48LL));
  if ( *((_DWORD *)a2 + 30) == 2 && (*(_DWORD *)(*((_QWORD *)a2 + 28) + 48LL) || *((_QWORD *)a2 + 23)) )
    VmbusTlpActivateDeliveryQueue((__int64)P, 0);
  if ( !*(_DWORD *)(*((_QWORD *)a2 + 28) + 48LL) )
    _InterlockedAdd64((volatile signed __int64 *)(*((_QWORD *)P + 14) + 1128LL), *((_QWORD *)a2 + 23));
  v10 = (volatile signed __int32 *)(*((_QWORD *)P + 14) + 1276LL);
LABEL_21:
  _InterlockedIncrement(v10);
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlConnectIoRequestCompleted",
      776,
      (_DWORD)a2,
      *((_QWORD *)a2 + 1),
      (__int64)"Dereference object");
  v16 = _InterlockedDecrement64((volatile signed __int64 *)a2 + 1);
  if ( v16 <= 0 )
  {
    if ( v16 )
      __fastfail(0xEu);
    v17 = (void (__fastcall *)(char *))*((_QWORD *)a2 + 10);
    if ( v17 )
      v17(a2);
    if ( *((_DWORD *)a2 + 22) == 1 )
    {
      ExFreePoolWithTag(a2, 0x69706E56u);
    }
    else if ( *((_DWORD *)a2 + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)a2 + 12), a2);
    }
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlConnectIoRequestCompleted",
      782,
      (_DWORD)P,
      *((_QWORD *)P + 38),
      (__int64)"Pending I/O request guard. (deref)");
  v18 = _InterlockedDecrement64((volatile signed __int64 *)P + 38);
  if ( v18 <= 0 )
  {
    if ( v18 )
      __fastfail(0xEu);
    if ( (unsigned int)dword_140013058 > 4 )
      HvsocketTraceEndpointEvent("VmbusTlDereferenceEndpointInternal cleaning up the endpoint.", P, 9);
    VmbusTlQueueEndpointAction(P, P + 200, 9, 0);
  }
  if ( (unsigned int)dword_140013058 > 5 )
    HvsocketTraceReferenceCount(
      (unsigned int)"VmbusTlConnectIoRequestCompleted",
      787,
      (_DWORD)P,
      *((_QWORD *)P + 1),
      (__int64)"Dereference object");
  v19 = _InterlockedDecrement64((volatile signed __int64 *)P + 1);
  if ( v19 <= 0 )
  {
    if ( v19 )
      __fastfail(0xEu);
    v20 = (void (__fastcall *)(char *))*((_QWORD *)P + 10);
    if ( v20 )
      v20(P);
    if ( *((_DWORD *)P + 22) == 1 )
    {
      ExFreePoolWithTag(P, 0x69706E56u);
    }
    else if ( *((_DWORD *)P + 22) == 2 )
    {
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)P + 12), P);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140007794  push    rbx
0x140007796  push    rbp
0x140007797  push    rsi
0x140007798  push    rdi
0x140007799  push    r13
0x14000779b  push    r14
0x14000779d  sub     rsp, 38h
0x1400077a1  cmp     dword ptr [rdx+78h], 1
0x1400077a5  lea     rsi, [rdx+68h]
0x1400077a9  mov     rdi, rdx
0x1400077ac  mov     rbx, rcx
0x1400077af  jnz     loc_140007847
0x1400077b5  lea     rbp, [rcx+330h]
0x1400077bc  mov     rcx, rbp; SpinLock
0x1400077bf  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400077c6  nop     dword ptr [rax+rax+00h]
0x1400077cb  mov     r8, [rsi]
0x1400077ce  cmp     [r8+8], rsi
0x1400077d2  jnz     loc_140007AF1
0x1400077d8  mov     rdx, [rsi+8]
0x1400077dc  cmp     [rdx], rsi
0x1400077df  jnz     loc_140007AF1
0x1400077e5  mov     [rdx], r8
0x1400077e8  mov     rcx, rbp; SpinLock
0x1400077eb  mov     [r8+8], rdx
0x1400077ef  mov     dl, al; NewIrql
0x1400077f1  mov     [rsi+8], rsi
0x1400077f5  mov     [rsi], rsi
0x1400077f8  call    cs:__imp_KeReleaseSpinLock
0x1400077ff  nop     dword ptr [rax+rax+00h]
0x140007804  mov     r8, [rdi+0E0h]
0x14000780b  mov     rdx, rdi
0x14000780e  mov     r8d, [r8+30h]
0x140007812  call    VmbusTlCompleteIoRequestToClient
0x140007817  mov     rax, [rdi+0E0h]
0x14000781e  xor     esi, esi
0x140007820  cmp     [rax+30h], esi
0x140007823  jnz     short loc_140007838
0x140007825  mov     rcx, [rbx+70h]
0x140007829  mov     rax, [rdi+0C8h]
0x140007830  lock add [rcx+460h], rax
0x140007838  mov     rax, [rbx+70h]
0x14000783c  add     rax, 4F8h
0x140007842  jmp     loc_140007937
0x140007847  lea     rbp, [rcx+350h]
0x14000784e  mov     rcx, rbp; SpinLock
0x140007851  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140007858  nop     dword ptr [rax+rax+00h]
0x14000785d  mov     r8, [rsi]
0x140007860  cmp     [r8+8], rsi
0x140007864  jnz     loc_140007AF1
0x14000786a  mov     rdx, [rsi+8]
0x14000786e  cmp     [rdx], rsi
0x140007871  jnz     loc_140007AF1
0x140007877  mov     [rdx], r8
0x14000787a  mov     rcx, rbp; SpinLock
0x14000787d  mov     [r8+8], rdx
0x140007881  mov     dl, al; NewIrql
0x140007883  mov     [rsi+8], rsi
0x140007887  mov     [rsi], rsi
0x14000788a  call    cs:__imp_KeReleaseSpinLock
0x140007891  nop     dword ptr [rax+rax+00h]
0x140007896  mov     eax, [rbx+20Ch]
0x14000789c  xor     esi, esi
0x14000789e  sub     eax, 11h
0x1400078a1  cmp     eax, 2
0x1400078a4  ja      short loc_1400078D6
0x1400078a6  mov     rax, [rdi+0E0h]
0x1400078ad  mov     ecx, [rax+30h]
0x1400078b0  cmp     ecx, 0C0000241h
0x1400078b6  jz      short loc_1400078C0
0x1400078b8  cmp     ecx, 0C0000120h
0x1400078be  jnz     short loc_1400078D6
0x1400078c0  mov     rcx, rbx
0x1400078c3  call    VmbusTlIsDisconnectAbortive
0x1400078c8  test    al, al
0x1400078ca  jnz     short loc_1400078D6
0x1400078cc  mov     rax, [rdi+0E0h]
0x1400078d3  mov     [rax+30h], esi
0x1400078d6  mov     r8, [rdi+0E0h]
0x1400078dd  mov     rdx, rdi
0x1400078e0  mov     r8d, [r8+30h]
0x1400078e4  call    VmbusTlCompleteIoRequestToClient
0x1400078e9  cmp     dword ptr [rdi+78h], 2
0x1400078ed  jnz     short loc_14000790E
0x1400078ef  mov     rax, [rdi+0E0h]
0x1400078f6  cmp     [rax+30h], esi
0x1400078f9  jnz     short loc_140007904
0x1400078fb  cmp     [rdi+0B8h], rsi
0x140007902  jz      short loc_14000790E
0x140007904  xor     edx, edx
0x140007906  mov     rcx, rbx
0x140007909  call    VmbusTlpActivateDeliveryQueue
0x14000790e  mov     rax, [rdi+0E0h]
0x140007915  cmp     [rax+30h], esi
0x140007918  jnz     short loc_14000792D
0x14000791a  mov     rcx, [rbx+70h]
0x14000791e  mov     rax, [rdi+0B8h]
0x140007925  lock add [rcx+468h], rax
0x14000792d  mov     rax, [rbx+70h]
0x140007931  add     rax, 4FCh
0x140007937  lock inc dword ptr [rax]
0x14000793a  mov     eax, cs:dword_140013058
0x140007940  lea     r13, aDereferenceObj; "Dereference object"
0x140007947  cmp     eax, 5
0x14000794a  jbe     short loc_140007969
0x14000794c  mov     r9, [rdi+8]
0x140007950  lea     rcx, aVmbustlconnect_7; "VmbusTlConnectIoRequestCompleted"
0x140007957  mov     r8, rdi
0x14000795a  mov     [rsp+68h+var_48], r13
0x14000795f  mov     edx, 308h
0x140007964  call    HvsocketTraceReferenceCount
0x140007969  or      rbp, 0FFFFFFFFFFFFFFFFh
0x14000796d  mov     rax, rbp
0x140007970  lock xadd [rdi+8], rax
0x140007976  add     rax, rbp
0x140007979  lea     r14d, [rbp+0Fh]
0x14000797d  test    rax, rax
0x140007980  jg      short loc_1400079D2
0x140007982  jz      short loc_14000798B
0x140007984  mov     ecx, r14d
0x140007987  int     29h; Win8: RtlFailFast(ecx)
0x140007989  jmp     short loc_1400079D2
0x14000798b  mov     rax, [rdi+50h]
0x14000798f  test    rax, rax
0x140007992  jz      short loc_14000799C
0x140007994  mov     rcx, rdi
0x140007997  call    _guard_dispatch_icall
0x14000799c  mov     ecx, [rdi+58h]
0x14000799f  sub     ecx, 1
0x1400079a2  jz      short loc_1400079BE
0x1400079a4  cmp     ecx, 1
0x1400079a7  jnz     short loc_1400079D2
0x1400079a9  mov     rcx, [rdi+60h]; Lookaside
0x1400079ad  mov     rdx, rdi; Entry
0x1400079b0  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400079b7  nop     dword ptr [rax+rax+00h]
0x1400079bc  jmp     short loc_1400079D2
0x1400079be  mov     edx, 69706E56h; Tag
0x1400079c3  mov     rcx, rdi; P
0x1400079c6  call    cs:__imp_ExFreePoolWithTag
0x1400079cd  nop     dword ptr [rax+rax+00h]
0x1400079d2  mov     eax, cs:dword_140013058
0x1400079d8  cmp     eax, 5
0x1400079db  jbe     short loc_140007A04
0x1400079dd  mov     r9, [rbx+130h]
0x1400079e4  lea     rax, aPendingIOReque_0; "Pending I/O request guard. (deref)"
0x1400079eb  mov     r8, rbx
0x1400079ee  mov     [rsp+68h+var_48], rax
0x1400079f3  mov     edx, 30Eh
0x1400079f8  lea     rcx, aVmbustlconnect_7; "VmbusTlConnectIoRequestCompleted"
0x1400079ff  call    HvsocketTraceReferenceCount
0x140007a04  mov     rax, rbp
0x140007a07  lock xadd [rbx+130h], rax
0x140007a10  add     rax, rbp
0x140007a13  test    rax, rax
0x140007a16  jg      short loc_140007A58
0x140007a18  jz      short loc_140007A21
0x140007a1a  mov     rcx, r14
0x140007a1d  int     29h; Win8: RtlFailFast(ecx)
0x140007a1f  jmp     short loc_140007A58
0x140007a21  mov     eax, cs:dword_140013058
0x140007a27  mov     edi, 9
0x140007a2c  cmp     eax, 4
0x140007a2f  jbe     short loc_140007A43
0x140007a31  mov     r8d, edi
0x140007a34  lea     rcx, aVmbustlderefer; "VmbusTlDereferenceEndpointInternal clea"...
0x140007a3b  mov     rdx, rbx
0x140007a3e  call    HvsocketTraceEndpointEvent
0x140007a43  lea     rdx, [rbx+0C8h]
0x140007a4a  xor     r9d, r9d
0x140007a4d  mov     r8d, edi
0x140007a50  mov     rcx, rbx
0x140007a53  call    VmbusTlQueueEndpointAction
0x140007a58  mov     eax, cs:dword_140013058
0x140007a5e  cmp     eax, 5
0x140007a61  jbe     short loc_140007A80
0x140007a63  mov     r9, [rbx+8]
0x140007a67  lea     rcx, aVmbustlconnect_7; "VmbusTlConnectIoRequestCompleted"
0x140007a6e  mov     r8, rbx
0x140007a71  mov     [rsp+68h+var_48], r13
0x140007a76  mov     edx, 313h
0x140007a7b  call    HvsocketTraceReferenceCount
0x140007a80  mov     rax, rbp
0x140007a83  lock xadd [rbx+8], rax
0x140007a89  add     rax, rbp
0x140007a8c  test    rax, rax
0x140007a8f  jg      short loc_140007AE1
0x140007a91  jz      short loc_140007A9A
0x140007a93  mov     rcx, r14
0x140007a96  int     29h; Win8: RtlFailFast(ecx)
0x140007a98  jmp     short loc_140007AE1
0x140007a9a  mov     rax, [rbx+50h]
0x140007a9e  test    rax, rax
0x140007aa1  jz      short loc_140007AAB
0x140007aa3  mov     rcx, rbx
0x140007aa6  call    _guard_dispatch_icall
0x140007aab  mov     ecx, [rbx+58h]
0x140007aae  sub     ecx, 1
0x140007ab1  jz      short loc_140007ACD
0x140007ab3  cmp     ecx, 1
0x140007ab6  jnz     short loc_140007AE1
0x140007ab8  mov     rcx, [rbx+60h]; Lookaside
0x140007abc  mov     rdx, rbx; Entry
0x140007abf  call    cs:__imp_ExFreeToNPagedLookasideList
0x140007ac6  nop     dword ptr [rax+rax+00h]
0x140007acb  jmp     short loc_140007AE1
0x140007acd  mov     edx, 69706E56h; Tag
0x140007ad2  mov     rcx, rbx; P
0x140007ad5  call    cs:__imp_ExFreePoolWithTag
0x140007adc  nop     dword ptr [rax+rax+00h]
0x140007ae1  xor     eax, eax
0x140007ae3  add     rsp, 38h
0x140007ae7  pop     r14
0x140007ae9  pop     r13
0x140007aeb  pop     rdi
0x140007aec  pop     rsi
0x140007aed  pop     rbp
0x140007aee  pop     rbx
0x140007aef  retn
0x140007af1  mov     ecx, 3
0x140007af6  int     29h; Win8: RtlFailFast(ecx)
```
