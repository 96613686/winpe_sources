# FvepUpdateSpecialRanges

- ea: `0x14002be0c`
- end: `0x14002bfa2`
- name: `FvepUpdateSpecialRanges`
- size: `406`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002b550`
- `0x14002b9a8`

## callees

- `0x14002be0c`
- `0x14002bfa8`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14002bf8a`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002bf8a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002bed2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002bed2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002be96`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bee8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bf50`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002be96`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bee8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002bf50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002be32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bf1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002be32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002bf1e`
- `ntoskrnl!KeSetEvent` at `0x14002bf3a`
- `ntoskrnl!KeSetEvent` at `0x14002bf3a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bf0f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002bf0f`

## pseudocode

```c
void __fastcall FvepUpdateSpecialRanges(__int64 a1)
{
  KSPIN_LOCK *v2; // rbp
  __int64 v3; // rbx
  KIRQL v4; // al
  KIRQL v5; // r14
  _OWORD *v6; // rdi
  __int64 v7; // rax
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  KIRQL v10; // al
  _OWORD v11[3]; // [rsp+30h] [rbp-58h] BYREF
  __int64 v12; // [rsp+60h] [rbp-28h]
  union _LARGE_INTEGER Interval; // [rsp+90h] [rbp+8h] BYREF

  v2 = (KSPIN_LOCK *)(a1 + 576);
  v3 = a1 + 560;
  while ( 1 )
  {
    v4 = KeAcquireSpinLockRaiseToDpc(v2);
    v5 = v4;
    if ( *(_QWORD *)v3 == v3 )
      break;
LABEL_3:
    v6 = *(_OWORD **)v3;
    if ( *(_QWORD *)(*(_QWORD *)v3 + 8LL) != v3 || (v7 = *(_QWORD *)v6, *(_OWORD **)(*(_QWORD *)v6 + 8LL) != v6) )
      __fastfail(3u);
    *(_QWORD *)v3 = v7;
    *(_QWORD *)(v7 + 8) = v3;
    v8 = v6[1];
    v11[0] = *v6;
    v9 = v6[2];
    v11[1] = v8;
    *(_QWORD *)&v8 = *((_QWORD *)v6 + 6);
    v11[2] = v9;
    v12 = v8;
    KeReleaseSpinLock(v2, v5);
    if ( *(int *)(*(_QWORD *)(a1 + 8) + 9924LL) < 0 )
    {
      Interval.QuadPart = -300000000;
      KeDelayExecutionThread(0, 0, &Interval);
    }
    FvepUpdateSpecialRange(v11);
    if ( (_BYTE)v12 )
      ExFreeToLookasideListEx(*(PLOOKASIDE_LIST_EX *)(a1 + 584), v6);
  }
  KeReleaseSpinLock(v2, v4);
  KeWaitForSingleObject((PVOID)(a1 + 608), Executive, 0, 0, 0);
  v10 = KeAcquireSpinLockRaiseToDpc(v2);
  v5 = v10;
  if ( *(_QWORD *)v3 != v3 )
  {
    KeSetEvent((PRKEVENT)(a1 + 608), 0, 0);
    goto LABEL_3;
  }
  KeReleaseSpinLock(v2, v10);
}

```

## disassembly

```asm
0x14002be0c  mov     [rsp+arg_8], rbx
0x14002be11  mov     [rsp+arg_10], rbp
0x14002be16  push    rsi
0x14002be17  push    rdi
0x14002be18  push    r14
0x14002be1a  sub     rsp, 70h
0x14002be1e  mov     rsi, rcx
0x14002be21  lea     rbp, [rcx+240h]
0x14002be28  lea     rbx, [rcx+230h]
0x14002be2f  mov     rcx, rbp; SpinLock
0x14002be32  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002be39  nop     dword ptr [rax+rax+00h]
0x14002be3e  mov     r14b, al
0x14002be41  cmp     [rbx], rbx
0x14002be44  jz      loc_14002BEE3
0x14002be4a  mov     rdi, [rbx]
0x14002be4d  cmp     [rdi+8], rbx
0x14002be51  jnz     loc_14002BF9B
0x14002be57  mov     rax, [rdi]
0x14002be5a  cmp     [rax+8], rdi
0x14002be5e  jnz     loc_14002BF9B
0x14002be64  mov     [rbx], rax
0x14002be67  mov     dl, r14b; NewIrql
0x14002be6a  mov     [rax+8], rbx
0x14002be6e  mov     rcx, rbp; SpinLock
0x14002be71  movups  xmm0, xmmword ptr [rdi]
0x14002be74  movups  xmm1, xmmword ptr [rdi+10h]
0x14002be78  movups  [rsp+88h+var_58], xmm0
0x14002be7d  movups  xmm0, xmmword ptr [rdi+20h]
0x14002be81  movups  [rsp+88h+var_48], xmm1
0x14002be86  movsd   xmm1, qword ptr [rdi+30h]
0x14002be8b  movups  [rsp+88h+var_38], xmm0
0x14002be90  movsd   [rsp+88h+var_28], xmm1
0x14002be96  call    cs:__imp_KeReleaseSpinLock
0x14002be9d  nop     dword ptr [rax+rax+00h]
0x14002bea2  mov     rax, [rsi+8]
0x14002bea6  cmp     dword ptr [rax+26C4h], 0
0x14002bead  jl      loc_14002BF72
0x14002beb3  lea     rcx, [rsp+88h+var_58]
0x14002beb8  call    FvepUpdateSpecialRange
0x14002bebd  cmp     byte ptr [rsp+88h+var_28], 0
0x14002bec2  jz      loc_14002BE2F
0x14002bec8  mov     rcx, [rsi+248h]; Lookaside
0x14002becf  mov     rdx, rdi; Entry
0x14002bed2  call    cs:__imp_ExFreeToLookasideListEx
0x14002bed9  nop     dword ptr [rax+rax+00h]
0x14002bede  jmp     loc_14002BE2F
0x14002bee3  mov     dl, al; NewIrql
0x14002bee5  mov     rcx, rbp; SpinLock
0x14002bee8  call    cs:__imp_KeReleaseSpinLock
0x14002beef  nop     dword ptr [rax+rax+00h]
0x14002bef4  lea     rdi, [rsi+260h]
0x14002befb  mov     [rsp+88h+Timeout], 0; Timeout
0x14002bf04  mov     rcx, rdi; Object
0x14002bf07  xor     r9d, r9d; Alertable
0x14002bf0a  xor     r8d, r8d; WaitMode
0x14002bf0d  xor     edx, edx; WaitReason
0x14002bf0f  call    cs:__imp_KeWaitForSingleObject
0x14002bf16  nop     dword ptr [rax+rax+00h]
0x14002bf1b  mov     rcx, rbp; SpinLock
0x14002bf1e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002bf25  nop     dword ptr [rax+rax+00h]
0x14002bf2a  mov     r14b, al
0x14002bf2d  cmp     [rbx], rbx
0x14002bf30  jz      short loc_14002BF4B
0x14002bf32  xor     r8d, r8d; Wait
0x14002bf35  xor     edx, edx; Increment
0x14002bf37  mov     rcx, rdi; Event
0x14002bf3a  call    cs:__imp_KeSetEvent
0x14002bf41  nop     dword ptr [rax+rax+00h]
0x14002bf46  jmp     loc_14002BE4A
0x14002bf4b  mov     dl, al; NewIrql
0x14002bf4d  mov     rcx, rbp; SpinLock
0x14002bf50  call    cs:__imp_KeReleaseSpinLock
0x14002bf57  nop     dword ptr [rax+rax+00h]
0x14002bf5c  lea     r11, [rsp+88h+var_18]
0x14002bf61  mov     rbx, [r11+28h]
0x14002bf65  mov     rbp, [r11+30h]
0x14002bf69  mov     rsp, r11
0x14002bf6c  pop     r14
0x14002bf6e  pop     rdi
0x14002bf6f  pop     rsi
0x14002bf70  retn
0x14002bf72  lea     r8, [rsp+88h+Interval]; Interval
0x14002bf7a  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFEE1E5D00h
0x14002bf86  xor     edx, edx; Alertable
0x14002bf88  xor     ecx, ecx; WaitMode
0x14002bf8a  call    cs:__imp_KeDelayExecutionThread
0x14002bf91  nop     dword ptr [rax+rax+00h]
0x14002bf96  jmp     loc_14002BEB3
0x14002bf9b  mov     ecx, 3
0x14002bfa0  int     29h; Win8: RtlFailFast(ecx)
```
