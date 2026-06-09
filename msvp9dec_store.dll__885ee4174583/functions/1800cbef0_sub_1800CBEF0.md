# sub_1800CBEF0

- ea: `0x1800cbef0`
- end: `0x1800cbfaf`
- name: `sub_1800CBEF0`
- size: `191`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x180005eb0`
- `0x1800060c0`
- `0x180006e40`
- `0x180018290`
- `0x18001b920`
- `0x18001c4a0`
- `0x180021a10`
- `0x180022a60`
- `0x180023b40`
- `0x180025848`
- `0x180025968`
- `0x180026de0`
- `0x1800274c4`
- `0x18002774c`
- `0x1800281a0`
- `0x18002afd0`
- `0x180137c10`

## callees

- `0x1800cbef0`
- `0x1800cc030`
- `0x180139010`

## pseudocode

```c
__int64 __fastcall sub_1800CBEF0(__int64 a1, __int64 a2, __int64 a3, void (__fastcall *a4)(__int64))
{
  __int64 i; // [rsp+50h] [rbp+8h]
  __int64 v8; // [rsp+60h] [rbp+18h]

  v8 = a3;
  for ( i = a3 * a2 + a1; v8--; a4(i) )
    i -= a2;
  return 1;
}

```

## disassembly

```asm
0x1800cbef0  mov     [rsp+arg_18], r9
0x1800cbef5  mov     [rsp+arg_10], r8
0x1800cbefa  mov     [rsp+arg_8], rdx
0x1800cbeff  mov     [rsp+arg_0], rcx
0x1800cbf04  sub     rsp, 48h
0x1800cbf08  mov     [rsp+48h+var_28], 0
0x1800cbf0d  mov     rax, [rsp+48h+arg_8]
0x1800cbf12  imul    rax, [rsp+48h+arg_10]
0x1800cbf18  mov     rcx, [rsp+48h+arg_0]
0x1800cbf1d  add     rcx, rax
0x1800cbf20  mov     rax, rcx
0x1800cbf23  mov     [rsp+48h+arg_0], rax
0x1800cbf28  mov     rax, [rsp+48h+arg_10]
0x1800cbf2d  mov     [rsp+48h+var_20], rax
0x1800cbf32  mov     rax, [rsp+48h+arg_10]
0x1800cbf37  dec     rax
0x1800cbf3a  mov     [rsp+48h+arg_10], rax
0x1800cbf3f  cmp     [rsp+48h+var_20], 0
0x1800cbf45  jbe     short loc_1800CBF82
0x1800cbf47  mov     rax, [rsp+48h+arg_8]
0x1800cbf4c  mov     rcx, [rsp+48h+arg_0]
0x1800cbf51  sub     rcx, rax
0x1800cbf54  mov     rax, rcx
0x1800cbf57  mov     [rsp+48h+arg_0], rax
0x1800cbf5c  mov     rax, [rsp+48h+arg_18]
0x1800cbf61  mov     [rsp+48h+var_18], rax
0x1800cbf66  mov     rax, [rsp+48h+var_18]
0x1800cbf6b  mov     [rsp+48h+var_10], rax
0x1800cbf70  mov     rcx, [rsp+48h+arg_0]
0x1800cbf75  mov     rax, [rsp+48h+var_10]
0x1800cbf7a  call    j_j__guard_dispatch_icall_nop
0x1800cbf7f  nop
0x1800cbf80  jmp     short loc_1800CBF28
0x1800cbf82  mov     [rsp+48h+var_28], 1
0x1800cbf87  movzx   eax, [rsp+48h+var_28]
0x1800cbf8c  test    eax, eax
0x1800cbf8e  jnz     short loc_1800CBFAA
0x1800cbf90  mov     r9, [rsp+48h+arg_18]
0x1800cbf95  mov     r8, [rsp+48h+arg_10]
0x1800cbf9a  mov     rdx, [rsp+48h+arg_8]
0x1800cbf9f  mov     rcx, [rsp+48h+arg_0]
0x1800cbfa4  call    sub_1800CC030
0x1800cbfa9  nop
0x1800cbfaa  add     rsp, 48h
0x1800cbfae  retn
```
