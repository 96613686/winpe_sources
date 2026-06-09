# EmbeddedProperties::copyPZPWSTR(ushort * * *,ushort * * const,bool)

- ea: `0x180006078`
- end: `0x1800062c8`
- name: `?copyPZPWSTR@EmbeddedProperties@@AEAAJPEAPEAPEAGQEAPEAG_N@Z`
- size: `592`
- prototype: `__int64 __fastcall(EmbeddedProperties *this, unsigned __int16 ***, unsigned __int16 **const, char)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x1800075c0`

## callees

- `0x180005f00`
- `0x180005fc0`
- `0x180006078`
- `0x180008400`
- `0x180014ff0`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x18000629f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800062a8`
- `msvcrt!??_V@YAXPEAX@Z` at `0x18000629f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800062a8`

## pseudocode

```c
__int64 __fastcall EmbeddedProperties::copyPZPWSTR(
        EmbeddedProperties *this,
        unsigned __int16 ***a2,
        unsigned __int16 **const a3,
        char a4)
{
  unsigned __int16 **v4; // r15
  unsigned __int16 **v8; // rdi
  unsigned int v9; // eax
  unsigned int v10; // ebx
  unsigned int v11; // ecx
  int v12; // edx
  unsigned __int64 v13; // rbp
  unsigned __int64 v14; // rbx
  unsigned __int64 v15; // rsi
  unsigned __int16 **v16; // rax
  unsigned __int64 v17; // r10
  unsigned __int16 *v18; // r11
  unsigned __int16 *v19; // r8
  __int64 v20; // rcx
  unsigned __int64 v21; // rdx
  unsigned __int16 *v22; // rax
  unsigned __int16 *v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // r14
  __int64 v26; // r10
  __int64 v27; // r11
  __int64 v28; // rcx
  unsigned __int64 v30; // [rsp+20h] [rbp-48h]
  unsigned __int64 v31; // [rsp+70h] [rbp+8h] BYREF
  unsigned __int64 v32; // [rsp+78h] [rbp+10h] BYREF

  v31 = (unsigned __int64)this;
  v4 = *a2;
  *a2 = 0;
  v31 = 0;
  v32 = 0;
  v8 = 0;
  v9 = EmbeddedProperties::countStringsAndChars(&v31, &v32, a3);
  v10 = v9;
  if ( v9 )
  {
    v11 = 28312371;
LABEL_3:
    v12 = v9;
LABEL_4:
    CSPrintErrorLineFile(v11, v12);
    goto LABEL_40;
  }
  v13 = v31;
  v14 = v31;
  v30 = v31;
  if ( a4 && v4 )
  {
    v9 = EmbeddedProperties::countStringsAndChars(&v31, &v32, v4);
    v10 = v9;
    if ( v9 )
    {
      v11 = 28705587;
      goto LABEL_3;
    }
    v13 = v31;
    v14 = v30;
  }
  v15 = v32;
  v16 = (unsigned __int16 **)operator new[](2 * (v32 + 4 + 4 * v13), (const struct std::nothrow_t *)&std::nothrow);
  v8 = v16;
  if ( !v16 )
  {
    v10 = -2147024882;
    v11 = 29164339;
    v12 = -2147024882;
    goto LABEL_4;
  }
  v17 = 0;
  v18 = (unsigned __int16 *)&v16[v13 + 1];
  while ( v17 < v14 )
  {
    v8[v17] = v18;
    if ( v15 )
    {
      if ( v15 > 0x7FFFFFFF )
      {
        v12 = -2147024809;
        *v18 = 0;
        v10 = -2147024809;
LABEL_29:
        v11 = 29885235;
        goto LABEL_4;
      }
      v19 = a3[v17];
      v20 = 2147483646;
      v21 = v15;
      v22 = v18;
      do
      {
        if ( !v20 )
          break;
        if ( !*v19 )
          break;
        *v22++ = *v19++;
        --v20;
        --v21;
      }
      while ( v21 );
      v23 = v22 - 1;
      if ( v21 )
        v23 = v22;
      v12 = v21 == 0 ? 0x8007007A : 0;
      *v23 = 0;
    }
    else
    {
      v12 = -2147024809;
    }
    v10 = v12;
    if ( v12 )
      goto LABEL_29;
    v24 = -1;
    do
      ++v24;
    while ( a3[v17][v24] );
    v14 = v30;
    v18 += v24 + 1;
    v15 += -1 - v24;
    ++v17;
  }
  if ( a4 && v4 )
  {
    v25 = 0;
    while ( v17 < v13 )
    {
      v8[v17] = v18;
      v9 = StringCchCopyW(v18, v15, v4[v25]);
      v10 = v9;
      if ( v9 )
      {
        v11 = 30671667;
        goto LABEL_3;
      }
      v28 = -1;
      do
        ++v28;
      while ( v4[v25][v28] );
      v18 = (unsigned __int16 *)(v27 + 2 * v28 + 2);
      v15 += -1 - v28;
      v17 = v26 + 1;
      ++v25;
    }
  }
  v8[v13] = 0;
  v10 = 0;
  *a2 = v8;
  v8 = 0;
LABEL_40:
  operator delete[](v4);
  operator delete[](v8);
  return v10;
}

```

## disassembly

```asm
0x180006078  mov     rax, rsp
0x18000607b  mov     [rax+18h], rbx
0x18000607f  mov     [rax+8], rcx
0x180006083  push    rbp
0x180006084  push    rsi
0x180006085  push    rdi
0x180006086  push    r12
0x180006088  push    r13
0x18000608a  push    r14
0x18000608c  push    r15
0x18000608e  sub     rsp, 30h
0x180006092  mov     r15, [rdx]
0x180006095  lea     rcx, [rax+8]; unsigned __int64 *
0x180006099  xor     esi, esi
0x18000609b  mov     r13, rdx
0x18000609e  mov     [rdx], rsi
0x1800060a1  mov     r14b, r9b
0x1800060a4  lea     rdx, [rax+10h]; unsigned __int64 *
0x1800060a8  mov     [rax+8], rsi
0x1800060ac  mov     r12, r8
0x1800060af  mov     [rax+10h], rsi
0x1800060b3  mov     edi, esi
0x1800060b5  call    ?countStringsAndChars@EmbeddedProperties@@CAJAEA_K0QEAPEAG@Z; EmbeddedProperties::countStringsAndChars(unsigned __int64 &,unsigned __int64 &,ushort * * const)
0x1800060ba  mov     ebx, eax
0x1800060bc  test    eax, eax
0x1800060be  jz      short loc_1800060D1
0x1800060c0  mov     ecx, 1B00333h; unsigned int
0x1800060c5  mov     edx, eax; int
0x1800060c7  call    ?CSPrintErrorLineFile@@YAXKJ@Z; CSPrintErrorLineFile(ulong,long)
0x1800060cc  jmp     loc_18000629C
0x1800060d1  mov     rbp, [rsp+68h+arg_0]
0x1800060d6  mov     rbx, rbp
0x1800060d9  mov     [rsp+68h+var_48], rbx
0x1800060de  test    r14b, r14b
0x1800060e1  jz      short loc_180006111
0x1800060e3  test    r15, r15
0x1800060e6  jz      short loc_180006111
0x1800060e8  mov     r8, r15; unsigned __int16 **
0x1800060eb  lea     rdx, [rsp+68h+arg_8]; unsigned __int64 *
0x1800060f0  lea     rcx, [rsp+68h+arg_0]; unsigned __int64 *
0x1800060f5  call    ?countStringsAndChars@EmbeddedProperties@@CAJAEA_K0QEAPEAG@Z; EmbeddedProperties::countStringsAndChars(unsigned __int64 &,unsigned __int64 &,ushort * * const)
0x1800060fa  mov     ebx, eax
0x1800060fc  test    eax, eax
0x1800060fe  jz      short loc_180006107
0x180006100  mov     ecx, 1B60333h
0x180006105  jmp     short loc_1800060C5
0x180006107  mov     rbp, [rsp+68h+arg_0]
0x18000610c  mov     rbx, [rsp+68h+var_48]
0x180006111  mov     rsi, [rsp+68h+arg_8]
0x180006116  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000611d  lea     rcx, [rsi+4]
0x180006121  lea     rcx, [rcx+rbp*4]
0x180006125  add     rcx, rcx; unsigned __int64
0x180006128  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000612d  xor     r9d, r9d
0x180006130  mov     rdi, rax
0x180006133  test    rax, rax
0x180006136  jnz     short loc_180006146
0x180006138  mov     ebx, 8007000Eh
0x18000613d  mov     ecx, 1BD0333h
0x180006142  mov     edx, ebx
0x180006144  jmp     short loc_1800060C7
0x180006146  lea     r11, [rbp+1]
0x18000614a  mov     r10, r9
0x18000614d  lea     r11, [rax+r11*8]
0x180006151  or      r8, 0FFFFFFFFFFFFFFFFh
0x180006155  cmp     r10, rbx
0x180006158  jnb     loc_180006228
0x18000615e  mov     [rdi+r10*8], r11
0x180006162  test    rsi, rsi
0x180006165  jz      short loc_1800061D1
0x180006167  cmp     rsi, 7FFFFFFFh
0x18000616e  ja      loc_180006210
0x180006174  mov     r8, [r12+r10*8]
0x180006178  mov     ecx, 7FFFFFFEh
0x18000617d  mov     rdx, rsi
0x180006180  mov     rax, r11
0x180006183  test    rcx, rcx
0x180006186  jz      short loc_1800061AF
0x180006188  movzx   r9d, word ptr [r8]
0x18000618c  test    r9w, r9w
0x180006190  jz      short loc_1800061AC
0x180006192  mov     [rax], r9w
0x180006196  add     r8, 2
0x18000619a  add     rax, 2
0x18000619e  xor     r9d, r9d
0x1800061a1  dec     rcx
0x1800061a4  sub     rdx, 1
0x1800061a8  jnz     short loc_180006183
0x1800061aa  jmp     short loc_1800061AF
0x1800061ac  xor     r9d, r9d
0x1800061af  test    rdx, rdx
0x1800061b2  lea     rcx, [rax-2]
0x1800061b6  cmovnz  rcx, rax
0x1800061ba  neg     rdx
0x1800061bd  sbb     edx, edx
0x1800061bf  not     edx
0x1800061c1  and     edx, 8007007Ah
0x1800061c7  mov     [rcx], r9w
0x1800061cb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800061cf  jmp     short loc_1800061DB
0x1800061d1  mov     edx, 80070057h
0x1800061d6  test    rsi, rsi
0x1800061d9  jnz     short loc_180006215
0x1800061db  mov     ebx, edx
0x1800061dd  test    edx, edx
0x1800061df  jnz     short loc_18000621E
0x1800061e1  mov     rax, [r12+r10*8]
0x1800061e5  mov     rcx, r8
0x1800061e8  inc     rcx
0x1800061eb  cmp     [rax+rcx*2], r9w
0x1800061f0  jnz     short loc_1800061E8
0x1800061f2  mov     rbx, [rsp+68h+var_48]
0x1800061f7  lea     r11, [r11+rcx*2]
0x1800061fb  mov     rax, r8
0x1800061fe  add     r11, 2
0x180006202  sub     rax, rcx
0x180006205  add     rsi, rax
0x180006208  inc     r10
0x18000620b  jmp     loc_180006155
0x180006210  mov     edx, 80070057h
0x180006215  mov     [r11], r9w
0x180006219  mov     ebx, 80070057h
0x18000621e  mov     ecx, 1C80333h
0x180006223  jmp     loc_1800060C7
0x180006228  test    r14b, r14b
0x18000622b  jz      short loc_18000628E
0x18000622d  test    r15, r15
0x180006230  jz      short loc_18000628E
0x180006232  mov     r14, r9
0x180006235  cmp     r10, rbp
0x180006238  jnb     short loc_18000628E
0x18000623a  mov     [rdi+r10*8], r11
0x18000623e  mov     rdx, rsi; unsigned __int64
0x180006241  mov     r8, [r15+r14*8]; unsigned __int16 *
0x180006245  mov     rcx, r11; unsigned __int16 *
0x180006248  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000624d  xor     r9d, r9d
0x180006250  mov     ebx, eax
0x180006252  test    eax, eax
0x180006254  jnz     short loc_180006284
0x180006256  mov     rax, [r15+r14*8]
0x18000625a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000625e  mov     rcx, r8
0x180006261  inc     rcx
0x180006264  cmp     [rax+rcx*2], r9w
0x180006269  jnz     short loc_180006261
0x18000626b  mov     rax, r8
0x18000626e  lea     r11, [r11+rcx*2]
0x180006272  sub     rax, rcx
0x180006275  add     r11, 2
0x180006279  add     rsi, rax
0x18000627c  inc     r10
0x18000627f  inc     r14
0x180006282  jmp     short loc_180006235
0x180006284  mov     ecx, 1D40333h
0x180006289  jmp     loc_1800060C5
0x18000628e  mov     [rdi+rbp*8], r9
0x180006292  mov     ebx, r9d
0x180006295  mov     [r13+0], rdi
0x180006299  mov     rdi, r9
0x18000629c  mov     rcx, r15
0x18000629f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800062a5  mov     rcx, rdi
0x1800062a8  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800062ae  mov     eax, ebx
0x1800062b0  mov     rbx, [rsp+68h+arg_10]
0x1800062b8  add     rsp, 30h
0x1800062bc  pop     r15
0x1800062be  pop     r14
0x1800062c0  pop     r13
0x1800062c2  pop     r12
0x1800062c4  pop     rdi
0x1800062c5  pop     rsi
0x1800062c6  pop     rbp
0x1800062c7  retn
```
