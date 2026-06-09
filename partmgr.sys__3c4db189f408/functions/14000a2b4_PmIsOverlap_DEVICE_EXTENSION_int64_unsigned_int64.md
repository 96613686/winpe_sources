# PmIsOverlap(_DEVICE_EXTENSION *,__int64,unsigned __int64)

- ea: `0x14000a2b4`
- end: `0x14000a336`
- name: `?PmIsOverlap@@YAEPEAU_DEVICE_EXTENSION@@_J_K@Z`
- size: `130`
- prototype: `unsigned __int8 __fastcall(struct _DEVICE_EXTENSION *, __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140002550`
- `0x14001ed38`

## callees

- `0x14000a2b4`

## import_xrefs

- `ntoskrnl!KeReleaseSpinLock` at `0x14000a31b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000a31b`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a2d2`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000a2d2`

## pseudocode

```c
bool __fastcall PmIsOverlap(KSPIN_LOCK *a1, __int64 a2, __int64 a3)
{
  KSPIN_LOCK *v3; // rbp
  bool v6; // di
  _QWORD *v7; // rbx
  KIRQL v8; // dl
  _QWORD *i; // r9
  __int64 v10; // rcx

  v3 = a1 + 14;
  v6 = 0;
  v7 = a1 + 112;
  v8 = KeAcquireSpinLockRaiseToDpc(a1 + 14);
  for ( i = (_QWORD *)*v7; i != v7; i = (_QWORD *)*i )
  {
    v10 = i[4];
    if ( v10 > a2 )
    {
      v6 = a3 > v10 - a2;
      break;
    }
    if ( a2 - v10 < i[5] )
    {
      v6 = 1;
      break;
    }
  }
  KeReleaseSpinLock(v3, v8);
  return v6;
}

```

## disassembly

```asm
0x14000a2b4  push    rbx
0x14000a2b6  push    rbp
0x14000a2b7  push    rsi
0x14000a2b8  push    rdi
0x14000a2b9  push    r14
0x14000a2bb  sub     rsp, 20h
0x14000a2bf  lea     rbp, [rcx+70h]
0x14000a2c3  mov     rbx, rcx
0x14000a2c6  mov     rcx, rbp; SpinLock
0x14000a2c9  mov     r14, r8
0x14000a2cc  mov     rsi, rdx
0x14000a2cf  xor     dil, dil
0x14000a2d2  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14000a2d9  nop     dword ptr [rax+rax+00h]
0x14000a2de  add     rbx, 380h
0x14000a2e5  mov     dl, al; NewIrql
0x14000a2e7  mov     r9, [rbx]
0x14000a2ea  cmp     r9, rbx
0x14000a2ed  jz      short loc_14000A318
0x14000a2ef  mov     rcx, [r9+20h]
0x14000a2f3  cmp     rcx, rsi
0x14000a2f6  jg      short loc_14000A30E
0x14000a2f8  mov     rax, rsi
0x14000a2fb  sub     rax, rcx
0x14000a2fe  cmp     rax, [r9+28h]
0x14000a302  jl      short loc_14000A309
0x14000a304  mov     r9, [r9]
0x14000a307  jmp     short loc_14000A2EA
0x14000a309  mov     dil, 1
0x14000a30c  jmp     short loc_14000A318
0x14000a30e  sub     rcx, rsi
0x14000a311  cmp     r14, rcx
0x14000a314  setnle  dil
0x14000a318  mov     rcx, rbp; SpinLock
0x14000a31b  call    cs:__imp_KeReleaseSpinLock
0x14000a322  nop     dword ptr [rax+rax+00h]
0x14000a327  mov     al, dil
0x14000a32a  add     rsp, 20h
0x14000a32e  pop     r14
0x14000a330  pop     rdi
0x14000a331  pop     rsi
0x14000a332  pop     rbp
0x14000a333  pop     rbx
0x14000a334  retn
```
