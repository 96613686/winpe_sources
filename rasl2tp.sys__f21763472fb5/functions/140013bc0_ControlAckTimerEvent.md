# ControlAckTimerEvent

- ea: `0x140013bc0`
- end: `0x140013c6c`
- name: `ControlAckTimerEvent`
- size: `172`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x140013bc0`
- `0x14001ac30`
- `0x14001c050`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x140013c0f`
- `ntoskrnl!KeReleaseSpinLock` at `0x140013c0f`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013c4c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013c4c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013bde`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140013bde`

## pseudocode

```c
__int64 __fastcall ControlAckTimerEvent(PVOID Entry, __int64 a2, int a3)
{
  __int64 v3; // r14
  KIRQL v6; // al
  char v7; // di
  __int64 v9; // [rsp+28h] [rbp-50h]
  __int64 v10; // [rsp+30h] [rbp-48h]

  v3 = *(_QWORD *)(a2 + 24);
  if ( !a3 )
  {
    v6 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a2 + 32));
    *(_BYTE *)(a2 + 40) = v6;
    if ( Entry == *(PVOID *)(a2 + 256) )
    {
      *(_QWORD *)(a2 + 256) = 0;
      v7 = 1;
    }
    else
    {
      v7 = 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a2 + 32), v6);
    if ( v7 )
      ScheduleTunnelWork(a2, 0, (__int64)SendControlAck, 0, 0, v9, v10, 0);
  }
  ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(v3 + 576), Entry);
  return DereferenceTunnel(a2);
}

```

## disassembly

```asm
0x140013bc0  push    rbx
0x140013bc2  push    rbp
0x140013bc3  push    rsi
0x140013bc4  push    rdi
0x140013bc5  push    r14
0x140013bc7  sub     rsp, 50h
0x140013bcb  mov     r14, [rdx+18h]
0x140013bcf  mov     rbx, rdx
0x140013bd2  mov     rsi, rcx
0x140013bd5  test    r8d, r8d
0x140013bd8  jnz     short loc_140013C42
0x140013bda  lea     rcx, [rdx+20h]; SpinLock
0x140013bde  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140013be5  nop     dword ptr [rax+rax+00h]
0x140013bea  mov     [rbx+28h], al
0x140013bed  cmp     rsi, [rbx+100h]
0x140013bf4  jnz     short loc_140013C06
0x140013bf6  mov     qword ptr [rbx+100h], 0
0x140013c01  mov     dil, 1
0x140013c04  jmp     short loc_140013C09
0x140013c06  xor     dil, dil
0x140013c09  mov     dl, al; NewIrql
0x140013c0b  lea     rcx, [rbx+20h]; SpinLock
0x140013c0f  call    cs:__imp_KeReleaseSpinLock
0x140013c16  nop     dword ptr [rax+rax+00h]
0x140013c1b  test    dil, dil
0x140013c1e  jz      short loc_140013C42
0x140013c20  mov     [rsp+78h+var_40], 0
0x140013c25  lea     r8, SendControlAck
0x140013c2c  xor     r9d, r9d
0x140013c2f  mov     [rsp+78h+var_58], 0
0x140013c38  xor     edx, edx
0x140013c3a  mov     rcx, rbx
0x140013c3d  call    ScheduleTunnelWork
0x140013c42  lea     rcx, [r14+240h]; Lookaside
0x140013c49  mov     rdx, rsi; Entry
0x140013c4c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013c53  nop     dword ptr [rax+rax+00h]
0x140013c58  mov     rcx, rbx
0x140013c5b  call    DereferenceTunnel
0x140013c60  add     rsp, 50h
0x140013c64  pop     r14
0x140013c66  pop     rdi
0x140013c67  pop     rsi
0x140013c68  pop     rbp
0x140013c69  pop     rbx
0x140013c6a  retn
```
