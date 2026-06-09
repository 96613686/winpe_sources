# RtlCompareUnicodeStrings

- ea: `0x180029480`
- end: `0x1800295c0`
- name: `RtlCompareUnicodeStrings`
- size: `320`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012c8c`
- `0x18001a590`
- `0x180028000`
- `0x180028510`
- `0x180029010`
- `0x180029254`
- `0x180077488`
- `0x1800c29c0`
- `0x1800c3e4c`
- `0x1800d4d20`
- `0x1800d5428`
- `0x1800dcf84`
- `0x1800dd1a0`
- `0x1800e78c4`
- `0x1800ffae0`
- `0x18010fc0c`
- `0x180124618`
- `0x18013b258`
- `0x18014dd6c`
- `0x18014dfb4`
- `0x18015c188`

## callees

- `0x180029480`
- `0x180162d60`

## pseudocode

```c
__int64 __fastcall RtlCompareUnicodeStrings(unsigned __int16 *a1, SIZE_T a2, unsigned __int16 *a3, SIZE_T a4, char a5)
{
  SIZE_T v5; // rsi
  unsigned __int16 *v6; // rdi
  int v7; // r14d
  int v8; // ebp
  unsigned __int16 *v9; // rbx
  SIZE_T v10; // rcx
  unsigned __int64 v12; // r8
  unsigned __int64 v13; // r9

  v5 = a2;
  v6 = a3;
  if ( a2 > a4 )
    v5 = a4;
  v7 = a4;
  v8 = a2;
  v9 = a1;
  if ( a5 )
  {
    while ( v9 < &a1[v5] )
    {
      v12 = *v9;
      v13 = *v6;
      if ( (_WORD)v12 != (_WORD)v13 )
      {
        if ( (unsigned int)v12 >= 0x61 )
        {
          if ( (unsigned int)v12 > 0x7A )
          {
            if ( qword_1801C5038 && (unsigned __int16)v12 >= 0xC0u )
              LOWORD(v12) = *(_WORD *)(qword_1801C5038
                                     + 2
                                     * ((v12 & 0xF)
                                      + *(unsigned __int16 *)(qword_1801C5038
                                                            + 2LL
                                                            * (((unsigned __int8)v12 >> 4)
                                                             + (unsigned int)*(unsigned __int16 *)(qword_1801C5038
                                                                                                 + 2 * (v12 >> 8))))))
                          + v12;
          }
          else
          {
            LOWORD(v12) = v12 - 32;
          }
        }
        if ( (unsigned int)v13 >= 0x61 )
        {
          if ( (unsigned int)v13 > 0x7A )
          {
            if ( qword_1801C5038 )
            {
              if ( (unsigned __int16)v13 >= 0xC0u )
                LOWORD(v13) = *(_WORD *)(qword_1801C5038
                                       + 2
                                       * ((v13 & 0xF)
                                        + *(unsigned __int16 *)(qword_1801C5038
                                                              + 2LL
                                                              * (((unsigned __int8)v13 >> 4)
                                                               + (unsigned int)*(unsigned __int16 *)(qword_1801C5038 + 2 * (v13 >> 8))))))
                            + v13;
            }
          }
          else
          {
            LOWORD(v13) = v13 - 32;
          }
        }
        if ( (_WORD)v12 != (_WORD)v13 )
          return (unsigned __int16)v12 - (unsigned int)(unsigned __int16)v13;
      }
      ++v9;
      ++v6;
    }
    return (unsigned int)(v8 - v7);
  }
  v10 = RtlCompareMemory(a1, a3, 2 * v5) >> 1;
  if ( v10 >= v5 )
    return (unsigned int)(v8 - v7);
  return v9[v10] - (unsigned int)v6[v10];
}

```

## disassembly

```asm
0x180029480  push    rbx
0x180029482  push    rbp
0x180029483  push    rsi
0x180029484  push    rdi
0x180029485  push    r14
0x180029487  sub     rsp, 20h
0x18002948b  mov     r11, cs:qword_1801C5038
0x180029492  cmp     rdx, r9
0x180029495  mov     rsi, rdx
0x180029498  mov     rdi, r8
0x18002949b  cmova   rsi, r9
0x18002949f  mov     r14, r9
0x1800294a2  cmp     [rsp+48h+arg_20], 0
0x1800294a7  mov     rbp, rdx
0x1800294aa  mov     rbx, rcx
0x1800294ad  lea     r8, [rsi+rsi]; Length
0x1800294b1  lea     r10, [r8+rcx]
0x1800294b5  jnz     short loc_1800294D5
0x1800294b7  mov     rdx, rdi; Source2
0x1800294ba  call    RtlCompareMemory
0x1800294bf  mov     rcx, rax
0x1800294c2  shr     rcx, 1
0x1800294c5  cmp     rcx, rsi
0x1800294c8  jb      loc_1800295AA
0x1800294ce  sub     ebp, r14d
0x1800294d1  mov     eax, ebp
0x1800294d3  jmp     short loc_18002952F
0x1800294d5  mov     esi, 0C0h
0x1800294da  nop     word ptr [rax+rax+00h]
0x1800294e0  cmp     rbx, r10
0x1800294e3  jnb     short loc_1800294CE
0x1800294e5  movzx   r8d, word ptr [rbx]
0x1800294e9  movzx   r9d, word ptr [rdi]
0x1800294ed  cmp     r8w, r9w
0x1800294f1  jnz     short loc_1800294FD
0x1800294f3  add     rbx, 2
0x1800294f7  add     rdi, 2
0x1800294fb  jmp     short loc_1800294E0
0x1800294fd  cmp     r8d, 61h ; 'a'
0x180029501  jb      short loc_18002950E
0x180029503  cmp     r8d, 7Ah ; 'z'
0x180029507  ja      short loc_18002953B
0x180029509  sub     r8w, 20h ; ' '
0x18002950e  cmp     r9d, 61h ; 'a'
0x180029512  jb      short loc_18002951F
0x180029514  cmp     r9d, 7Ah ; 'z'
0x180029518  ja      short loc_180029571
0x18002951a  sub     r9w, 20h ; ' '
0x18002951f  cmp     r8w, r9w
0x180029523  jz      short loc_1800294F3
0x180029525  movzx   ecx, r9w
0x180029529  movzx   eax, r8w
0x18002952d  sub     eax, ecx
0x18002952f  add     rsp, 20h
0x180029533  pop     r14
0x180029535  pop     rdi
0x180029536  pop     rsi
0x180029537  pop     rbp
0x180029538  pop     rbx
0x180029539  retn
0x18002953b  test    r11, r11
0x18002953e  jz      short loc_18002950E
0x180029540  cmp     r8w, si
0x180029544  jb      short loc_18002950E
0x180029546  mov     rax, r8
0x180029549  mov     edx, r8d
0x18002954c  shr     rax, 8
0x180029550  and     edx, 0Fh
0x180029553  movzx   ecx, word ptr [r11+rax*2]
0x180029558  mov     eax, r8d
0x18002955b  shr     eax, 4
0x18002955e  and     eax, 0Fh
0x180029561  add     ecx, eax
0x180029563  movzx   ecx, word ptr [r11+rcx*2]
0x180029568  add     ecx, edx
0x18002956a  add     r8w, [r11+rcx*2]
0x18002956f  jmp     short loc_18002950E
0x180029571  test    r11, r11
0x180029574  jz      short loc_18002951F
0x180029576  cmp     r9w, si
0x18002957a  jb      short loc_18002951F
0x18002957c  mov     rax, r9
0x18002957f  mov     edx, r9d
0x180029582  shr     rax, 8
0x180029586  and     edx, 0Fh
0x180029589  movzx   ecx, word ptr [r11+rax*2]
0x18002958e  mov     eax, r9d
0x180029591  shr     eax, 4
0x180029594  and     eax, 0Fh
0x180029597  add     ecx, eax
0x180029599  movzx   ecx, word ptr [r11+rcx*2]
0x18002959e  add     ecx, edx
0x1800295a0  add     r9w, [r11+rcx*2]
0x1800295a5  jmp     loc_18002951F
0x1800295aa  movzx   eax, word ptr [rbx+rcx*2]
0x1800295ae  movzx   ecx, word ptr [rdi+rcx*2]
0x1800295b2  sub     eax, ecx
0x1800295b4  add     rsp, 20h
0x1800295b8  pop     r14
0x1800295ba  pop     rdi
0x1800295bb  pop     rsi
0x1800295bc  pop     rbp
0x1800295bd  pop     rbx
0x1800295be  retn
```
