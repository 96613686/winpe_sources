# RtlCompareUnicodeStrings

- ea: `0x180029590`
- end: `0x1800296d0`
- name: `RtlCompareUnicodeStrings`
- size: `320`
- prototype: ``
- caller_count: `21`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180012c8c`
- `0x18001a590`
- `0x180028110`
- `0x180028620`
- `0x180029120`
- `0x180029364`
- `0x18005aaa8`
- `0x180073ac0`
- `0x1800741c8`
- `0x1800be6e0`
- `0x1800bfb6c`
- `0x1800dce64`
- `0x1800dd080`
- `0x1800e7544`
- `0x1800ff4c0`
- `0x18010e8ac`
- `0x180123b28`
- `0x18013a768`
- `0x18014d40c`
- `0x18014d654`
- `0x18015b97c`

## callees

- `0x180029590`
- `0x180162550`

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
0x180029590  push    rbx
0x180029592  push    rbp
0x180029593  push    rsi
0x180029594  push    rdi
0x180029595  push    r14
0x180029597  sub     rsp, 20h
0x18002959b  mov     r11, cs:qword_1801C5038
0x1800295a2  cmp     rdx, r9
0x1800295a5  mov     rsi, rdx
0x1800295a8  mov     rdi, r8
0x1800295ab  cmova   rsi, r9
0x1800295af  mov     r14, r9
0x1800295b2  cmp     [rsp+48h+arg_20], 0
0x1800295b7  mov     rbp, rdx
0x1800295ba  mov     rbx, rcx
0x1800295bd  lea     r8, [rsi+rsi]; Length
0x1800295c1  lea     r10, [r8+rcx]
0x1800295c5  jnz     short loc_1800295E5
0x1800295c7  mov     rdx, rdi; Source2
0x1800295ca  call    RtlCompareMemory
0x1800295cf  mov     rcx, rax
0x1800295d2  shr     rcx, 1
0x1800295d5  cmp     rcx, rsi
0x1800295d8  jb      loc_1800296BA
0x1800295de  sub     ebp, r14d
0x1800295e1  mov     eax, ebp
0x1800295e3  jmp     short loc_18002963F
0x1800295e5  mov     esi, 0C0h
0x1800295ea  nop     word ptr [rax+rax+00h]
0x1800295f0  cmp     rbx, r10
0x1800295f3  jnb     short loc_1800295DE
0x1800295f5  movzx   r8d, word ptr [rbx]
0x1800295f9  movzx   r9d, word ptr [rdi]
0x1800295fd  cmp     r8w, r9w
0x180029601  jnz     short loc_18002960D
0x180029603  add     rbx, 2
0x180029607  add     rdi, 2
0x18002960b  jmp     short loc_1800295F0
0x18002960d  cmp     r8d, 61h ; 'a'
0x180029611  jb      short loc_18002961E
0x180029613  cmp     r8d, 7Ah ; 'z'
0x180029617  ja      short loc_18002964B
0x180029619  sub     r8w, 20h ; ' '
0x18002961e  cmp     r9d, 61h ; 'a'
0x180029622  jb      short loc_18002962F
0x180029624  cmp     r9d, 7Ah ; 'z'
0x180029628  ja      short loc_180029681
0x18002962a  sub     r9w, 20h ; ' '
0x18002962f  cmp     r8w, r9w
0x180029633  jz      short loc_180029603
0x180029635  movzx   ecx, r9w
0x180029639  movzx   eax, r8w
0x18002963d  sub     eax, ecx
0x18002963f  add     rsp, 20h
0x180029643  pop     r14
0x180029645  pop     rdi
0x180029646  pop     rsi
0x180029647  pop     rbp
0x180029648  pop     rbx
0x180029649  retn
0x18002964b  test    r11, r11
0x18002964e  jz      short loc_18002961E
0x180029650  cmp     r8w, si
0x180029654  jb      short loc_18002961E
0x180029656  mov     rax, r8
0x180029659  mov     edx, r8d
0x18002965c  shr     rax, 8
0x180029660  and     edx, 0Fh
0x180029663  movzx   ecx, word ptr [r11+rax*2]
0x180029668  mov     eax, r8d
0x18002966b  shr     eax, 4
0x18002966e  and     eax, 0Fh
0x180029671  add     ecx, eax
0x180029673  movzx   ecx, word ptr [r11+rcx*2]
0x180029678  add     ecx, edx
0x18002967a  add     r8w, [r11+rcx*2]
0x18002967f  jmp     short loc_18002961E
0x180029681  test    r11, r11
0x180029684  jz      short loc_18002962F
0x180029686  cmp     r9w, si
0x18002968a  jb      short loc_18002962F
0x18002968c  mov     rax, r9
0x18002968f  mov     edx, r9d
0x180029692  shr     rax, 8
0x180029696  and     edx, 0Fh
0x180029699  movzx   ecx, word ptr [r11+rax*2]
0x18002969e  mov     eax, r9d
0x1800296a1  shr     eax, 4
0x1800296a4  and     eax, 0Fh
0x1800296a7  add     ecx, eax
0x1800296a9  movzx   ecx, word ptr [r11+rcx*2]
0x1800296ae  add     ecx, edx
0x1800296b0  add     r9w, [r11+rcx*2]
0x1800296b5  jmp     loc_18002962F
0x1800296ba  movzx   eax, word ptr [rbx+rcx*2]
0x1800296be  movzx   ecx, word ptr [rdi+rcx*2]
0x1800296c2  sub     eax, ecx
0x1800296c4  add     rsp, 20h
0x1800296c8  pop     r14
0x1800296ca  pop     rdi
0x1800296cb  pop     rsi
0x1800296cc  pop     rbp
0x1800296cd  pop     rbx
0x1800296ce  retn
```
