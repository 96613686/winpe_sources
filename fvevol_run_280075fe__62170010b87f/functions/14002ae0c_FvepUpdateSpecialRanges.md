# FvepUpdateSpecialRanges

- ea: `0x14002ae0c`
- end: `0x14002afa2`
- name: `FvepUpdateSpecialRanges`
- size: `406`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14002a550`
- `0x14002a9a8`

## callees

- `0x14002ae0c`
- `0x14002afa8`

## import_xrefs

- `ntoskrnl!KeDelayExecutionThread` at `0x14002af8a`
- `ntoskrnl!KeDelayExecutionThread` at `0x14002af8a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002aed2`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14002aed2`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ae96`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aee8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002af50`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002ae96`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002aee8`
- `ntoskrnl!KeReleaseSpinLock` at `0x14002af50`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ae32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002af1e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002ae32`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14002af1e`
- `ntoskrnl!KeSetEvent` at `0x14002af3a`
- `ntoskrnl!KeSetEvent` at `0x14002af3a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002af0f`
- `ntoskrnl!KeWaitForSingleObject` at `0x14002af0f`

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
    if ( *(int *)(*(_QWORD *)(a1 + 8) + 9676LL) < 0 )
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
0x14002ae0c  mov     [rsp+arg_8], rbx
0x14002ae11  mov     [rsp+arg_10], rbp
0x14002ae16  push    rsi
0x14002ae17  push    rdi
0x14002ae18  push    r14
0x14002ae1a  sub     rsp, 70h
0x14002ae1e  mov     rsi, rcx
0x14002ae21  lea     rbp, [rcx+240h]
0x14002ae28  lea     rbx, [rcx+230h]
0x14002ae2f  mov     rcx, rbp; SpinLock
0x14002ae32  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002ae39  nop     dword ptr [rax+rax+00h]
0x14002ae3e  mov     r14b, al
0x14002ae41  cmp     [rbx], rbx
0x14002ae44  jz      loc_14002AEE3
0x14002ae4a  mov     rdi, [rbx]
0x14002ae4d  cmp     [rdi+8], rbx
0x14002ae51  jnz     loc_14002AF9B
0x14002ae57  mov     rax, [rdi]
0x14002ae5a  cmp     [rax+8], rdi
0x14002ae5e  jnz     loc_14002AF9B
0x14002ae64  mov     [rbx], rax
0x14002ae67  mov     dl, r14b; NewIrql
0x14002ae6a  mov     [rax+8], rbx
0x14002ae6e  mov     rcx, rbp; SpinLock
0x14002ae71  movups  xmm0, xmmword ptr [rdi]
0x14002ae74  movups  xmm1, xmmword ptr [rdi+10h]
0x14002ae78  movups  [rsp+88h+var_58], xmm0
0x14002ae7d  movups  xmm0, xmmword ptr [rdi+20h]
0x14002ae81  movups  [rsp+88h+var_48], xmm1
0x14002ae86  movsd   xmm1, qword ptr [rdi+30h]
0x14002ae8b  movups  [rsp+88h+var_38], xmm0
0x14002ae90  movsd   [rsp+88h+var_28], xmm1
0x14002ae96  call    cs:__imp_KeReleaseSpinLock
0x14002ae9d  nop     dword ptr [rax+rax+00h]
0x14002aea2  mov     rax, [rsi+8]
0x14002aea6  cmp     dword ptr [rax+25CCh], 0
0x14002aead  jl      loc_14002AF72
0x14002aeb3  lea     rcx, [rsp+88h+var_58]
0x14002aeb8  call    FvepUpdateSpecialRange
0x14002aebd  cmp     byte ptr [rsp+88h+var_28], 0
0x14002aec2  jz      loc_14002AE2F
0x14002aec8  mov     rcx, [rsi+248h]; Lookaside
0x14002aecf  mov     rdx, rdi; Entry
0x14002aed2  call    cs:__imp_ExFreeToLookasideListEx
0x14002aed9  nop     dword ptr [rax+rax+00h]
0x14002aede  jmp     loc_14002AE2F
0x14002aee3  mov     dl, al; NewIrql
0x14002aee5  mov     rcx, rbp; SpinLock
0x14002aee8  call    cs:__imp_KeReleaseSpinLock
0x14002aeef  nop     dword ptr [rax+rax+00h]
0x14002aef4  lea     rdi, [rsi+260h]
0x14002aefb  mov     [rsp+88h+Timeout], 0; Timeout
0x14002af04  mov     rcx, rdi; Object
0x14002af07  xor     r9d, r9d; Alertable
0x14002af0a  xor     r8d, r8d; WaitMode
0x14002af0d  xor     edx, edx; WaitReason
0x14002af0f  call    cs:__imp_KeWaitForSingleObject
0x14002af16  nop     dword ptr [rax+rax+00h]
0x14002af1b  mov     rcx, rbp; SpinLock
0x14002af1e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14002af25  nop     dword ptr [rax+rax+00h]
0x14002af2a  mov     r14b, al
0x14002af2d  cmp     [rbx], rbx
0x14002af30  jz      short loc_14002AF4B
0x14002af32  xor     r8d, r8d; Wait
0x14002af35  xor     edx, edx; Increment
0x14002af37  mov     rcx, rdi; Event
0x14002af3a  call    cs:__imp_KeSetEvent
0x14002af41  nop     dword ptr [rax+rax+00h]
0x14002af46  jmp     loc_14002AE4A
0x14002af4b  mov     dl, al; NewIrql
0x14002af4d  mov     rcx, rbp; SpinLock
0x14002af50  call    cs:__imp_KeReleaseSpinLock
0x14002af57  nop     dword ptr [rax+rax+00h]
0x14002af5c  lea     r11, [rsp+88h+var_18]
0x14002af61  mov     rbx, [r11+28h]
0x14002af65  mov     rbp, [r11+30h]
0x14002af69  mov     rsp, r11
0x14002af6c  pop     r14
0x14002af6e  pop     rdi
0x14002af6f  pop     rsi
0x14002af70  retn
0x14002af72  lea     r8, [rsp+88h+Interval]; Interval
0x14002af7a  mov     qword ptr [rsp+88h+Interval], 0FFFFFFFFEE1E5D00h
0x14002af86  xor     edx, edx; Alertable
0x14002af88  xor     ecx, ecx; WaitMode
0x14002af8a  call    cs:__imp_KeDelayExecutionThread
0x14002af91  nop     dword ptr [rax+rax+00h]
0x14002af96  jmp     loc_14002AEB3
0x14002af9b  mov     ecx, 3
0x14002afa0  int     29h; Win8: RtlFailFast(ecx)
```
