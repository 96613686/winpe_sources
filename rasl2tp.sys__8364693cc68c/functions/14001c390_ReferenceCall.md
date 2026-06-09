# ReferenceCall

- ea: `0x14001c390`
- end: `0x14001c3f1`
- name: `ReferenceCall`
- size: `97`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1400109d0`
- `0x140011518`
- `0x140015190`
- `0x1400175f0`
- `0x140017b90`

## callees

- `0x14001c390`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14001c3cb`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001c3cb`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c3a6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001c3a6`

## pseudocode

```c
__int64 __fastcall ReferenceCall(__int64 a1)
{
  KIRQL v2; // al
  bool v3; // zf
  unsigned __int8 v4; // si

  v2 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 72));
  v3 = (*(_DWORD *)(a1 + 60) & 0x200) == 0;
  *(_BYTE *)(a1 + 80) = v2;
  if ( v3 )
  {
    v4 = 0;
  }
  else
  {
    ++*(_DWORD *)(a1 + 64);
    v4 = 1;
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 72), v2);
  return v4;
}

```

## disassembly

```asm
0x14001c390  mov     [rsp+arg_0], rbx
0x14001c395  mov     [rsp+arg_8], rsi
0x14001c39a  push    rdi
0x14001c39b  sub     rsp, 20h
0x14001c39f  mov     rbx, rcx
0x14001c3a2  add     rcx, 48h ; 'H'; SpinLock
0x14001c3a6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001c3ad  nop     dword ptr [rax+rax+00h]
0x14001c3b2  test    dword ptr [rbx+3Ch], 200h
0x14001c3b9  mov     [rbx+50h], al
0x14001c3bc  jz      short loc_14001C3EC
0x14001c3be  inc     dword ptr [rbx+40h]
0x14001c3c1  mov     sil, 1
0x14001c3c4  movzx   edx, al; NewIrql
0x14001c3c7  lea     rcx, [rbx+48h]; SpinLock
0x14001c3cb  call    cs:__imp_KeReleaseSpinLock
0x14001c3d2  nop     dword ptr [rax+rax+00h]
0x14001c3d7  mov     rbx, [rsp+28h+arg_0]
0x14001c3dc  movzx   eax, sil
0x14001c3e0  mov     rsi, [rsp+28h+arg_8]
0x14001c3e5  add     rsp, 20h
0x14001c3e9  pop     rdi
0x14001c3ea  retn
0x14001c3ec  xor     sil, sil
0x14001c3ef  jmp     short loc_14001C3C4
```
