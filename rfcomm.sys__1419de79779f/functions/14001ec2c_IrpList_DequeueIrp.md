# IrpList_DequeueIrp

- ea: `0x14001ec2c`
- end: `0x14001ecdf`
- name: `IrpList_DequeueIrp`
- size: `179`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140001eec`
- `0x14000aca0`
- `0x140011050`
- `0x140013d20`
- `0x140013fb4`

## callees

- `0x14001ec2c`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ec45`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001ec45`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ec7d`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001ec7d`

## pseudocode

```c
char __fastcall IrpList_DequeueIrp(__int64 a1, _QWORD *a2)
{
  KIRQL v4; // al
  _QWORD *v5; // r8
  char v6; // di
  KIRQL v7; // r9
  _QWORD *v8; // rcx
  _QWORD *v9; // rdx
  _QWORD *v11; // rax

  v4 = KeAcquireSpinLockRaiseToDpc(*(PKSPIN_LOCK *)(a1 + 24));
  v5 = *(_QWORD **)a1;
  v6 = 0;
  v7 = v4;
  if ( *(_QWORD *)a1 != a1 )
  {
    while ( 1 )
    {
      v8 = (_QWORD *)*v5;
      v9 = v5 - 21;
      if ( v5 - 21 == a2 )
        break;
      v5 = (_QWORD *)*v5;
      if ( v8 == (_QWORD *)a1 )
        goto LABEL_4;
    }
    if ( (_QWORD *)v8[1] != v5 || (v11 = (_QWORD *)v5[1], (_QWORD *)*v11 != v5) )
      __fastfail(3u);
    *v11 = v8;
    v8[1] = v11;
    --*(_DWORD *)(a1 + 32);
    if ( _InterlockedExchange64(v9 + 13, 0) )
    {
      v9[18] = 0;
      v6 = 1;
    }
    v5[1] = v5;
    *v5 = v5;
  }
LABEL_4:
  KeReleaseSpinLock(*(PKSPIN_LOCK *)(a1 + 24), v7);
  return v6;
}

```

## disassembly

```asm
0x14001ec2c  mov     [rsp+arg_0], rbx
0x14001ec31  mov     [rsp+arg_8], rsi
0x14001ec36  push    rdi
0x14001ec37  sub     rsp, 20h
0x14001ec3b  mov     rbx, rcx
0x14001ec3e  mov     rsi, rdx
0x14001ec41  mov     rcx, [rcx+18h]; SpinLock
0x14001ec45  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001ec4c  nop     dword ptr [rax+rax+00h]
0x14001ec51  mov     r8, [rbx]
0x14001ec54  xor     dil, dil
0x14001ec57  mov     r9b, al
0x14001ec5a  cmp     r8, rbx
0x14001ec5d  jz      short loc_14001EC76
0x14001ec5f  mov     rcx, [r8]
0x14001ec62  lea     rdx, [r8-0A8h]
0x14001ec69  cmp     rdx, rsi
0x14001ec6c  jz      short loc_14001EC9D
0x14001ec6e  mov     r8, rcx
0x14001ec71  cmp     rcx, rbx
0x14001ec74  jnz     short loc_14001EC5F
0x14001ec76  mov     rcx, [rbx+18h]; SpinLock
0x14001ec7a  mov     dl, r9b; NewIrql
0x14001ec7d  call    cs:__imp_KeReleaseSpinLock
0x14001ec84  nop     dword ptr [rax+rax+00h]
0x14001ec89  mov     rbx, [rsp+28h+arg_0]
0x14001ec8e  mov     al, dil
0x14001ec91  mov     rsi, [rsp+28h+arg_8]
0x14001ec96  add     rsp, 20h
0x14001ec9a  pop     rdi
0x14001ec9b  retn
0x14001ec9d  cmp     [rcx+8], r8
0x14001eca1  jnz     short loc_14001ECD8
0x14001eca3  mov     rax, [r8+8]
0x14001eca7  cmp     [rax], r8
0x14001ecaa  jnz     short loc_14001ECD8
0x14001ecac  mov     [rax], rcx
0x14001ecaf  mov     [rcx+8], rax
0x14001ecb3  xor     eax, eax
0x14001ecb5  dec     dword ptr [rbx+20h]
0x14001ecb8  xchg    rax, [rdx+68h]
0x14001ecbc  test    rax, rax
0x14001ecbf  jz      short loc_14001ECCF
0x14001ecc1  mov     qword ptr [rdx+90h], 0
0x14001eccc  mov     dil, 1
0x14001eccf  mov     [r8+8], r8
0x14001ecd3  mov     [r8], r8
0x14001ecd6  jmp     short loc_14001EC76
0x14001ecd8  mov     ecx, 3
0x14001ecdd  int     29h; Win8: RtlFailFast(ecx)
```
