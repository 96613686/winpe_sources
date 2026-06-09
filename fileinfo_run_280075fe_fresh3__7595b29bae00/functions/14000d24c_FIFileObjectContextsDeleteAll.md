# FIFileObjectContextsDeleteAll

- ea: `0x14000d24c`
- end: `0x14000d3c3`
- name: `FIFileObjectContextsDeleteAll`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000e370`

## callees

- `0x14000d24c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000d3a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000d3a2`

## pseudocode

```c
void FIFileObjectContextsDeleteAll()
{
  _QWORD *v0; // rbx
  _QWORD *j; // rbx
  void *v2; // r9
  _QWORD *i; // rdx
  __int64 v4; // [rsp+20h] [rbp-18h]

  if ( dword_140009650 )
  {
    if ( *(__int64 *)((char *)&qword_140009654 + 4)
      && (v0 = **(_QWORD ***)((char *)&qword_140009654 + 4), (**(_QWORD **)((char *)&qword_140009654 + 4) & 1) == 0) )
    {
LABEL_16:
      while ( v0 )
      {
        v2 = v0;
        v4 = v0[1] & (-1LL << (qword_140009654 & 0x1F));
        v0 = (_QWORD *)*v0;
        if ( ((unsigned __int8)v0 & 1) != 0 )
        {
          for ( i = (_QWORD *)(*(__int64 *)((char *)&qword_140009654 + 4)
                             + 8
                             + 8LL
                             * ((((unsigned int)qword_140009654 >> 5) - 1)
                              & (HIBYTE(v4)
                               + 37
                               * (BYTE6(v4)
                                + 37
                                * (BYTE5(v4)
                                 + 37
                                 * (BYTE4(v4)
                                  + 37
                                  * (BYTE3(v4)
                                   + 37 * (BYTE2(v4) + 37 * (BYTE1(v4) + 37 * ((unsigned __int8)v4 + 11623883))))))))));
                (unsigned __int64)i < *(__int64 *)((char *)&qword_140009654 + 4)
                                    + 8 * ((unsigned __int64)(unsigned int)qword_140009654 >> 5);
                ++i )
          {
            v0 = (_QWORD *)*i;
            if ( (*i & 1) == 0 )
              goto LABEL_15;
          }
          v0 = 0;
        }
LABEL_15:
        ExFreePoolWithTag(v2, 0);
      }
    }
    else
    {
      for ( j = (_QWORD *)(*(__int64 *)((char *)&qword_140009654 + 4) + 8);
            (unsigned __int64)j < *(__int64 *)((char *)&qword_140009654 + 4)
                                + 8 * ((unsigned __int64)(unsigned int)qword_140009654 >> 5);
            ++j )
      {
        if ( (*(_BYTE *)j & 1) == 0 )
        {
          _mm_lfence();
          v0 = (_QWORD *)*j;
          goto LABEL_16;
        }
      }
    }
  }
}

```

## disassembly

```asm
0x14000d24c  mov     [rsp+arg_0], rbx
0x14000d251  push    rdi
0x14000d252  sub     rsp, 30h
0x14000d256  cmp     cs:dword_140009650, 0
0x14000d25d  jz      loc_14000D3B7
0x14000d263  mov     rdx, cs:qword_140009654+4
0x14000d26a  mov     rdi, 8000000000000002h
0x14000d274  test    rdx, rdx
0x14000d277  jz      short loc_14000D295
0x14000d279  mov     rax, [rdx]
0x14000d27c  and     rax, rdi
0x14000d27f  cmp     rax, rdi
0x14000d282  jnz     short loc_14000D289
0x14000d284  xor     eax, eax
0x14000d286  mov     rcx, [rax]
0x14000d289  mov     rbx, [rdx]
0x14000d28c  test    bl, 1
0x14000d28f  jz      loc_14000D3AE
0x14000d295  mov     ecx, dword ptr cs:qword_140009654
0x14000d29b  lea     rbx, [rdx+8]
0x14000d29f  mov     rax, cs:qword_140009654+4
0x14000d2a6  shr     rcx, 5
0x14000d2aa  lea     rdx, [rax+rcx*8]
0x14000d2ae  cmp     rbx, rdx
0x14000d2b1  jnb     loc_14000D3B7
0x14000d2b7  test    byte ptr [rbx], 1
0x14000d2ba  jz      short loc_14000D2C2
0x14000d2bc  add     rbx, 8
0x14000d2c0  jmp     short loc_14000D2AE
0x14000d2c2  lfence
0x14000d2c5  mov     rbx, [rbx]
0x14000d2c8  jmp     loc_14000D3AE
0x14000d2cd  mov     r8, cs:qword_140009654
0x14000d2d4  lea     r10, [rsp+38h+var_18]
0x14000d2d9  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000d2dd  mov     ecx, r8d
0x14000d2e0  and     ecx, 1Fh
0x14000d2e3  shr     r8d, 5
0x14000d2e7  shl     rax, cl
0x14000d2ea  mov     r9, rbx
0x14000d2ed  and     rax, [rbx+8]
0x14000d2f1  mov     [rsp+38h+var_18], rax
0x14000d2f6  movzx   eax, byte ptr [r10]
0x14000d2fa  add     eax, 0B15DCBh
0x14000d2ff  imul    ecx, eax, 25h ; '%'
0x14000d302  movzx   eax, byte ptr [r10+1]
0x14000d307  add     ecx, eax
0x14000d309  movzx   eax, byte ptr [r10+2]
0x14000d30e  imul    edx, ecx, 25h ; '%'
0x14000d311  add     edx, eax
0x14000d313  movzx   eax, byte ptr [r10+3]
0x14000d318  imul    ecx, edx, 25h ; '%'
0x14000d31b  add     ecx, eax
0x14000d31d  movzx   eax, byte ptr [r10+4]
0x14000d322  imul    edx, ecx, 25h ; '%'
0x14000d325  add     edx, eax
0x14000d327  movzx   eax, byte ptr [r10+5]
0x14000d32c  imul    ecx, edx, 25h ; '%'
0x14000d32f  add     ecx, eax
0x14000d331  movzx   eax, byte ptr [r10+6]
0x14000d336  imul    edx, ecx, 25h ; '%'
0x14000d339  add     edx, eax
0x14000d33b  movzx   eax, byte ptr [r10+7]
0x14000d340  imul    edx, 25h ; '%'
0x14000d343  add     edx, eax
0x14000d345  lea     eax, [r8-1]
0x14000d349  mov     r8, cs:qword_140009654+4
0x14000d350  and     rdx, rax
0x14000d353  mov     rax, [rbx]
0x14000d356  and     rax, rdi
0x14000d359  cmp     rax, rdi
0x14000d35c  jnz     short loc_14000D363
0x14000d35e  xor     eax, eax
0x14000d360  mov     rcx, [rax]
0x14000d363  mov     rbx, [rbx]
0x14000d366  test    bl, 1
0x14000d369  jz      short loc_14000D39D
0x14000d36b  mov     ecx, dword ptr cs:qword_140009654
0x14000d371  add     r8, 8
0x14000d375  mov     rax, cs:qword_140009654+4
0x14000d37c  shr     rcx, 5
0x14000d380  lea     rdx, [r8+rdx*8]
0x14000d384  lea     r8, [rax+rcx*8]
0x14000d388  cmp     rdx, r8
0x14000d38b  jnb     short loc_14000D39B
0x14000d38d  mov     rbx, [rdx]
0x14000d390  test    bl, 1
0x14000d393  jz      short loc_14000D39D
0x14000d395  add     rdx, 8
0x14000d399  jmp     short loc_14000D388
0x14000d39b  xor     ebx, ebx
0x14000d39d  xor     edx, edx; Tag
0x14000d39f  mov     rcx, r9; P
0x14000d3a2  call    cs:__imp_ExFreePoolWithTag
0x14000d3a9  nop     dword ptr [rax+rax+00h]
0x14000d3ae  test    rbx, rbx
0x14000d3b1  jnz     loc_14000D2CD
0x14000d3b7  mov     rbx, [rsp+38h+arg_0]
0x14000d3bc  add     rsp, 30h
0x14000d3c0  pop     rdi
0x14000d3c1  retn
```
