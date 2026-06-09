# lldpDetachOpenPort

- ea: `0x1400063bc`
- end: `0x140006458`
- name: `lldpDetachOpenPort`
- size: `156`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14000ed90`

## callees

- `0x140004320`
- `0x1400063bc`
- `0x14000fca0`
- `0x140012568`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400063d6`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400063d6`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006417`
- `ntoskrnl!KeReleaseSpinLock` at `0x140006417`

## pseudocode

```c
__int64 __fastcall lldpDetachOpenPort(_QWORD *P)
{
  __int64 v1; // rbx
  _QWORD *v3; // rax
  _QWORD *v4; // rcx

  v1 = P[3];
  *(_BYTE *)(v1 + 80) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v1 + 72));
  v3 = *(_QWORD **)(v1 + 88);
  if ( v3 == P )
  {
    *(_QWORD *)(v1 + 88) = P[1];
  }
  else
  {
    while ( v3 )
    {
      v4 = v3 + 1;
      v3 = (_QWORD *)v3[1];
      if ( v3 == P )
      {
        *v4 = P[1];
        break;
      }
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v1 + 72), *(_BYTE *)(v1 + 80));
  lldpAcquireInterLock(v1 + 56, 1);
  lldpReleaseInterLock(v1 + 56);
  P[1] = 0;
  return lldpDeleteOpenPort(P);
}

```

## disassembly

```asm
0x1400063bc  mov     [rsp+arg_0], rbx
0x1400063c1  mov     [rsp+arg_8], rsi
0x1400063c6  push    rdi
0x1400063c7  sub     rsp, 20h
0x1400063cb  mov     rbx, [rcx+18h]
0x1400063cf  mov     rdi, rcx
0x1400063d2  lea     rcx, [rbx+48h]; SpinLock
0x1400063d6  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400063dd  nop     dword ptr [rax+rax+00h]
0x1400063e2  mov     [rbx+50h], al
0x1400063e5  mov     rax, [rbx+58h]
0x1400063e9  cmp     rax, rdi
0x1400063ec  jnz     short loc_1400063F8
0x1400063ee  mov     rax, [rdi+8]
0x1400063f2  mov     [rbx+58h], rax
0x1400063f6  jmp     short loc_140006410
0x1400063f8  test    rax, rax
0x1400063fb  jz      short loc_140006410
0x1400063fd  lea     rcx, [rax+8]
0x140006401  mov     rax, [rcx]
0x140006404  cmp     rax, rdi
0x140006407  jnz     short loc_1400063F8
0x140006409  mov     rax, [rdi+8]
0x14000640d  mov     [rcx], rax
0x140006410  mov     dl, [rbx+50h]; NewIrql
0x140006413  lea     rcx, [rbx+48h]; SpinLock
0x140006417  call    cs:__imp_KeReleaseSpinLock
0x14000641e  nop     dword ptr [rax+rax+00h]
0x140006423  mov     dl, 1
0x140006425  lea     rcx, [rbx+38h]
0x140006429  call    lldpAcquireInterLock
0x14000642e  lea     rcx, [rbx+38h]
0x140006432  call    lldpReleaseInterLock
0x140006437  mov     rcx, rdi; P
0x14000643a  mov     qword ptr [rdi+8], 0
0x140006442  call    lldpDeleteOpenPort
0x140006447  mov     rbx, [rsp+28h+arg_0]
0x14000644c  mov     rsi, [rsp+28h+arg_8]
0x140006451  add     rsp, 20h
0x140006455  pop     rdi
0x140006456  retn
```
