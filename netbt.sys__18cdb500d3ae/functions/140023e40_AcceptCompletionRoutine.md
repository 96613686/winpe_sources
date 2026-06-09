# AcceptCompletionRoutine

- ea: `0x140023e40`
- end: `0x1400240d6`
- name: `AcceptCompletionRoutine`
- size: `662`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x140006878`
- `0x14000da94`
- `0x14001e8f4`
- `0x140023e40`
- `0x1400400a4`
- `0x1400405d4`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140023e79`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140023e8c`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140023e79`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140023e8c`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023f41`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023f50`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023fe0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023fef`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140024088`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140024097`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023f41`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023f50`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023fe0`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140023fef`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140024088`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140024097`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023e60`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140023e60`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024005`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400240ad`
- `ntoskrnl!KeReleaseSpinLock` at `0x140024005`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400240ad`

## pseudocode

```c
__int64 __fastcall AcceptCompletionRoutine(__int64 a1, IRP *a2, __int64 a3)
{
  __int64 v3; // r15
  KIRQL v6; // r12
  IO_STATUS_BLOCK *p_IoStatus; // rdi
  int v8; // eax
  __int64 v9; // rax
  _QWORD *v10; // rcx
  __int64 v11; // rax
  __int64 *v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax

  v3 = *(_QWORD *)(a3 + 40);
  v6 = KeAcquireSpinLockRaiseToDpc(&SpinLock);
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(v3 + 848));
  KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)(a3 + 104));
  p_IoStatus = &a2->IoStatus;
  if ( (BYTE2(xmmword_140038420) & 0x10) != 0 )
    WPP_SF_qqD(1044, 48, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, a2, a3, p_IoStatus->Status);
  if ( p_IoStatus->Status >= 0 )
    goto LABEL_20;
  v8 = *(_DWORD *)(a3 + 88);
  if ( v8 == 4 )
  {
    v9 = *(_QWORD *)a3;
    if ( *(_QWORD *)(*(_QWORD *)a3 + 8LL) != a3
      || (v10 = *(_QWORD **)(a3 + 8), *v10 != a3)
      || (*v10 = v9,
          *(_QWORD *)(v9 + 8) = v10,
          v11 = *(_QWORD *)(a3 + 40) + 400LL,
          v12 = *(__int64 **)(*(_QWORD *)(a3 + 40) + 408LL),
          *v12 != v11) )
    {
      __fastfail(3u);
    }
    *(_QWORD *)(a3 + 8) = v12;
    *(_QWORD *)a3 = v11;
    *v12 = a3;
    *(_QWORD *)(v11 + 8) = a3;
    v13 = *(_QWORD *)(a3 + 40);
    *(_QWORD *)(a3 + 88) = 0;
    _InterlockedDecrement((volatile signed __int32 *)(v13 + 432));
    _InterlockedDecrement(&dword_14003975C);
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a3 + 104));
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 848));
    if ( (BYTE2(xmmword_140038420) & 0x10) != 0 )
      WPP_SF_d(1044, 49, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, (unsigned int)a2->IoStatus.Status);
    v14 = *(_QWORD *)(a3 + 40);
    if ( !v14 || *(_DWORD *)(v14 + 360) != 1131832644 )
      v3 = 0;
    NTQueueToWorkerThread(a3 + 128, (__int64)DelayedCleanupAfterDisconnect, 0, a3, 0, v3, 1, 245);
    goto LABEL_21;
  }
  if ( v8 != 7 )
  {
LABEL_20:
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a3 + 104));
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 848));
LABEL_21:
    KeReleaseSpinLock(&SpinLock, v6);
    goto LABEL_22;
  }
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(a3 + 104));
  KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)(v3 + 848));
  KeReleaseSpinLock(&SpinLock, v6);
  if ( (BYTE2(xmmword_140038420) & 0x10) != 0 )
  {
    WPP_SF_d(1044, 50, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, (unsigned int)p_IoStatus->Status);
    if ( (BYTE2(xmmword_140038420) & 0x10) != 0 )
      WPP_SF_d(1044, 51, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids, (unsigned int)p_IoStatus->Status);
  }
  DisconnectHndlrNotOs(0, a3, 0, 0, 0, 0, 2, 7u);
LABEL_22:
  NbtFreeIrp(a2);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140023e40  push    rbx
0x140023e42  push    rbp
0x140023e43  push    rsi
0x140023e44  push    rdi
0x140023e45  push    r12
0x140023e47  push    r14
0x140023e49  push    r15
0x140023e4b  sub     rsp, 40h
0x140023e4f  mov     r15, [r8+28h]
0x140023e53  lea     rcx, SpinLock; SpinLock
0x140023e5a  mov     rbx, r8
0x140023e5d  mov     rsi, rdx
0x140023e60  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140023e67  nop     dword ptr [rax+rax+00h]
0x140023e6c  lea     rbp, [r15+350h]
0x140023e73  mov     r12b, al
0x140023e76  mov     rcx, rbp; SpinLock
0x140023e79  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140023e80  nop     dword ptr [rax+rax+00h]
0x140023e85  lea     r14, [rbx+68h]
0x140023e89  mov     rcx, r14; SpinLock
0x140023e8c  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140023e93  nop     dword ptr [rax+rax+00h]
0x140023e98  test    byte ptr cs:xmmword_140038420+2, 10h
0x140023e9f  lea     rdi, [rsi+30h]
0x140023ea3  jz      short loc_140023EC9
0x140023ea5  mov     eax, [rdi]
0x140023ea7  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x140023eae  mov     dword ptr [rsp+78h+var_50], eax
0x140023eb2  mov     edx, 30h ; '0'
0x140023eb7  mov     ecx, 414h
0x140023ebc  mov     qword ptr [rsp+78h+var_58], rbx
0x140023ec1  mov     r9, rsi
0x140023ec4  call    WPP_SF_qqD
0x140023ec9  cmp     dword ptr [rdi], 0
0x140023ecc  jge     loc_140024085
0x140023ed2  mov     eax, [rbx+58h]
0x140023ed5  cmp     eax, 4
0x140023ed8  jnz     loc_140023FD4
0x140023ede  mov     rax, [rbx]
0x140023ee1  cmp     [rax+8], rbx
0x140023ee5  jnz     loc_140023FCD
0x140023eeb  mov     rcx, [rbx+8]
0x140023eef  cmp     [rcx], rbx
0x140023ef2  jnz     loc_140023FCD
0x140023ef8  mov     [rcx], rax
0x140023efb  mov     [rax+8], rcx
0x140023eff  mov     rax, [rbx+28h]
0x140023f03  add     rax, 190h
0x140023f09  mov     rcx, [rax+8]
0x140023f0d  cmp     [rcx], rax
0x140023f10  jnz     loc_140023FCD
0x140023f16  mov     [rbx+8], rcx
0x140023f1a  mov     [rbx], rax
0x140023f1d  mov     [rcx], rbx
0x140023f20  mov     rcx, r14; SpinLock
0x140023f23  mov     [rax+8], rbx
0x140023f27  mov     rax, [rbx+28h]
0x140023f2b  mov     qword ptr [rbx+58h], 0
0x140023f33  lock dec dword ptr [rax+1B0h]
0x140023f3a  lock dec cs:dword_14003975C
0x140023f41  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140023f48  nop     dword ptr [rax+rax+00h]
0x140023f4d  mov     rcx, rbp; SpinLock
0x140023f50  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140023f57  nop     dword ptr [rax+rax+00h]
0x140023f5c  test    byte ptr cs:xmmword_140038420+2, 10h
0x140023f63  jz      short loc_140023F7F
0x140023f65  mov     r9d, [rsi+30h]
0x140023f69  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x140023f70  mov     edx, 31h ; '1'
0x140023f75  mov     ecx, 414h
0x140023f7a  call    WPP_SF_d
0x140023f7f  mov     rax, [rbx+28h]
0x140023f83  test    rax, rax
0x140023f86  jz      short loc_140023F94
0x140023f88  cmp     dword ptr [rax+168h], 43766544h
0x140023f92  jz      short loc_140023F97
0x140023f94  xor     r15d, r15d
0x140023f97  mov     [rsp+78h+Irql], 0F5h
0x140023f9c  lea     rcx, [rbx+80h]
0x140023fa3  mov     byte ptr [rsp+78h+var_48], 1
0x140023fa8  lea     rdx, DelayedCleanupAfterDisconnect
0x140023faf  mov     [rsp+78h+var_50], r15
0x140023fb4  mov     r9, rbx
0x140023fb7  xor     r8d, r8d
0x140023fba  mov     qword ptr [rsp+78h+var_58], 0
0x140023fc3  call    NTQueueToWorkerThread
0x140023fc8  jmp     loc_1400240A3
0x140023fcd  mov     ecx, 3
0x140023fd2  int     29h; Win8: RtlFailFast(ecx)
0x140023fd4  cmp     eax, 7
0x140023fd7  jnz     loc_140024085
0x140023fdd  mov     rcx, r14; SpinLock
0x140023fe0  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140023fe7  nop     dword ptr [rax+rax+00h]
0x140023fec  mov     rcx, rbp; SpinLock
0x140023fef  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140023ff6  nop     dword ptr [rax+rax+00h]
0x140023ffb  mov     dl, r12b; NewIrql
0x140023ffe  lea     rcx, SpinLock; SpinLock
0x140024005  call    cs:__imp_KeReleaseSpinLock
0x14002400c  nop     dword ptr [rax+rax+00h]
0x140024011  test    byte ptr cs:xmmword_140038420+2, 10h
0x140024018  jz      short loc_140024055
0x14002401a  mov     r9d, [rdi]
0x14002401d  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x140024024  mov     edx, 32h ; '2'
0x140024029  mov     ecx, 414h
0x14002402e  call    WPP_SF_d
0x140024033  test    byte ptr cs:xmmword_140038420+2, 10h
0x14002403a  jz      short loc_140024055
0x14002403c  mov     r9d, [rdi]
0x14002403f  lea     r8, WPP_e821b053d0733e5b06ead08bfa3e1f1d_Traceguids
0x140024046  mov     edx, 33h ; '3'
0x14002404b  mov     ecx, 414h
0x140024050  call    WPP_SF_d
0x140024055  mov     [rsp+78h+Irql], 7; Irql
0x14002405a  xor     r9d, r9d; int
0x14002405d  mov     [rsp+78h+var_48], 2; int
0x140024065  xor     r8d, r8d; int
0x140024068  mov     [rsp+78h+var_50], 0; __int64
0x140024071  mov     rdx, rbx; int
0x140024074  xor     ecx, ecx; int
0x140024076  mov     [rsp+78h+var_58], 0; int
0x14002407e  call    DisconnectHndlrNotOs
0x140024083  jmp     short loc_1400240B9
0x140024085  mov     rcx, r14; SpinLock
0x140024088  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002408f  nop     dword ptr [rax+rax+00h]
0x140024094  mov     rcx, rbp; SpinLock
0x140024097  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14002409e  nop     dword ptr [rax+rax+00h]
0x1400240a3  mov     dl, r12b; NewIrql
0x1400240a6  lea     rcx, SpinLock; SpinLock
0x1400240ad  call    cs:__imp_KeReleaseSpinLock
0x1400240b4  nop     dword ptr [rax+rax+00h]
0x1400240b9  mov     rcx, rsi; Irp
0x1400240bc  call    NbtFreeIrp
0x1400240c1  mov     eax, 0C0000016h
0x1400240c6  add     rsp, 40h
0x1400240ca  pop     r15
0x1400240cc  pop     r14
0x1400240ce  pop     r12
0x1400240d0  pop     rdi
0x1400240d1  pop     rsi
0x1400240d2  pop     rbp
0x1400240d3  pop     rbx
0x1400240d4  retn
```
