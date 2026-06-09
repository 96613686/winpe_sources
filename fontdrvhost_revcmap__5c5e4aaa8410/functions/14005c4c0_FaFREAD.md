# FaFREAD

- ea: `0x14005c4c0`
- end: `0x14005c57c`
- name: `FaFREAD`
- size: `188`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x14005c4c0`
- `0x140076ef6`

## pseudocode

```c
unsigned __int64 __fastcall FaFREAD(__int64 a1, void *a2, unsigned __int64 a3, unsigned __int64 a4, __int64 a5)
{
  void *v7; // r9
  unsigned __int64 v9; // rsi
  int i; // ebx
  __int64 v11; // rcx

  v7 = a2;
  v9 = 0;
  if ( a1 && a3 )
  {
    for ( i = 0; (unsigned __int64)i < 2; ++i )
    {
      if ( a5 == *(_QWORD *)(a1 + 24LL * i) )
      {
        v11 = *(unsigned int *)(a1 + 24LL * i + 12);
        v9 = (unsigned int)(*(_DWORD *)(a1 + 24LL * i + 8) - v11) / a3;
        if ( a4 < v9 )
          v9 = a4;
        memmove_0(v7, (const void *)(*(_QWORD *)(a1 + 24LL * i) + v11), v9 * a3);
        *(_DWORD *)(a1 + 24LL * i + 12) += v9 * a3;
        v7 = a2;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x14005c4c0  mov     [rsp+arg_10], rbx
0x14005c4c5  mov     [rsp+arg_18], rsi
0x14005c4ca  mov     [rsp+arg_8], rdx
0x14005c4cf  push    rdi
0x14005c4d0  push    r12
0x14005c4d2  push    r13
0x14005c4d4  push    r14
0x14005c4d6  push    r15
0x14005c4d8  sub     rsp, 30h
0x14005c4dc  mov     r13, r9
0x14005c4df  mov     r15, r8
0x14005c4e2  mov     r9, rdx
0x14005c4e5  mov     rdi, rcx
0x14005c4e8  xor     esi, esi
0x14005c4ea  test    rcx, rcx
0x14005c4ed  jz      short loc_14005C561
0x14005c4ef  test    r8, r8
0x14005c4f2  jz      short loc_14005C561
0x14005c4f4  xor     ebx, ebx
0x14005c4f6  mov     r12, [rsp+58h+arg_20]
0x14005c4fe  mov     [rsp+58h+var_38], ebx
0x14005c502  movsxd  rax, ebx
0x14005c505  cmp     rax, 2
0x14005c509  jnb     short loc_14005C561
0x14005c50b  lea     r14, [rax+rax*2]
0x14005c50f  cmp     r12, [rdi+r14*8]
0x14005c513  jz      short loc_14005C519
0x14005c515  inc     ebx
0x14005c517  jmp     short loc_14005C4FE
0x14005c519  mov     ecx, [rdi+r14*8+0Ch]
0x14005c51e  mov     eax, [rdi+r14*8+8]
0x14005c523  sub     eax, ecx
0x14005c525  xor     edx, edx
0x14005c527  div     r15
0x14005c52a  mov     rsi, rax
0x14005c52d  cmp     r13, rax
0x14005c530  cmovb   rsi, r13
0x14005c534  mov     [rsp+58h+arg_0], rsi
0x14005c539  mov     r8, r15
0x14005c53c  imul    r8, rsi; Size
0x14005c540  add     rcx, [rdi+r14*8]
0x14005c544  mov     rdx, rcx; Src
0x14005c547  mov     rcx, r9; void *
0x14005c54a  call    memmove_0
0x14005c54f  mov     eax, r15d
0x14005c552  imul    eax, esi
0x14005c555  add     [rdi+r14*8+0Ch], eax
0x14005c55a  mov     r9, [rsp+58h+arg_8]
0x14005c55f  jmp     short loc_14005C515
0x14005c561  mov     rax, rsi
0x14005c564  mov     rbx, [rsp+58h+arg_10]
0x14005c569  mov     rsi, [rsp+58h+arg_18]
0x14005c56e  add     rsp, 30h
0x14005c572  pop     r15
0x14005c574  pop     r14
0x14005c576  pop     r13
0x14005c578  pop     r12
0x14005c57a  pop     rdi
0x14005c57b  retn
0x140097414  push    rbp
0x140097416  sub     rsp, 20h
0x14009741a  mov     rbp, rdx
0x14009741d  add     rsp, 20h
0x140097421  pop     rbp
0x140097422  retn
```
