# CSchedule::CheckJobName(ushort const *,ushort * *)

- ea: `0x180006120`
- end: `0x1800064e8`
- name: `?CheckJobName@CSchedule@@AEAAJPEBGPEAPEAG@Z`
- size: `968`
- prototype: `int(CSchedule *__hidden this, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f610`
- `0x18000f700`
- `0x18000f9e0`

## callees

- `0x180006120`
- `0x180009ef8`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800064d2`
- `msvcrt!_wcsicmp` at `0x1800064d2`
- `msvcrt!wcsrchr` at `0x1800061b7`
- `msvcrt!wcsrchr` at `0x1800061b7`

## pseudocode

```c
__int64 __fastcall CSchedule::CheckJobName(CSchedule *this, const unsigned __int16 *a2, unsigned __int16 **a3)
{
  __int64 v4; // rbx
  const unsigned __int16 *v5; // rdi
  unsigned __int16 v7; // ax
  int v8; // r15d
  int v9; // ebp
  unsigned __int16 v10; // cx
  wchar_t *v11; // rax
  unsigned __int64 v12; // rbx
  unsigned __int16 *v13; // r11
  __int64 v14; // r10
  unsigned __int16 *v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // r9
  unsigned __int16 *v18; // r8
  unsigned __int16 *v19; // rcx
  unsigned __int64 v20; // rcx
  unsigned __int16 *v21; // rax
  unsigned __int64 v22; // r9
  const unsigned __int16 *v23; // r8
  unsigned __int16 *v24; // rdx
  __int64 v25; // rax
  unsigned __int16 *v26; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // rax
  unsigned __int64 v29; // r8
  unsigned __int16 *v30; // rdx
  unsigned __int16 *v31; // rcx
  unsigned __int64 v32; // rcx
  unsigned __int16 *v33; // rax
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rbx
  const unsigned __int16 *v36; // rdx
  unsigned __int16 *j; // rax
  unsigned __int16 *v38; // rcx
  unsigned __int16 *v40; // rax
  unsigned __int64 v41; // rcx
  unsigned __int64 v42; // r8
  unsigned __int16 *v43; // rax
  __int64 v44; // rcx
  unsigned __int64 i; // rdx
  __int64 v46; // rax

  v4 = -1;
  v5 = a2;
  do
    ++v4;
  while ( a2[v4] );
  if ( !(_DWORD)v4 )
    return 2147942487LL;
  if ( (unsigned int)v4 > 1 )
  {
    v7 = a2[(unsigned int)(v4 - 1)];
    if ( v7 == 92 || v7 == 47 )
      return 2147942487LL;
  }
  v8 = 1;
  v9 = 1;
  if ( (unsigned int)v4 <= 2 )
    goto LABEL_11;
  v10 = a2[1];
  if ( v10 == 58 )
    goto LABEL_81;
  if ( *a2 == 92 )
  {
    if ( v10 != 92 )
      goto LABEL_11;
    goto LABEL_81;
  }
  if ( *a2 == 47 && v10 == 47 )
LABEL_81:
    v9 = 0;
LABEL_11:
  v11 = wcsrchr(a2, 0x2Eu);
  if ( !v11 || (unsigned __int64)(unsigned int)v4 - (v11 - v5) > 4 )
  {
    LODWORD(v4) = v4 + 4;
    goto LABEL_13;
  }
  if ( _wcsicmp(v11 + 1, L"job") )
    return 2147942487LL;
  v8 = 0;
LABEL_13:
  if ( v9 )
  {
    v46 = -1;
    do
      ++v46;
    while ( *(_WORD *)(*((_QWORD *)this + 8) + 2 * v46) );
    LODWORD(v4) = v46 + v4 + 1;
  }
  v12 = (unsigned int)(v4 + 1);
  v13 = (unsigned __int16 *)operator new(saturated_mul(v12, 2u));
  if ( !v13 )
    return 2147942414LL;
  v14 = 2147483646;
  *v13 = 0;
  if ( !v9 )
  {
    if ( !v12 || v12 > 0x7FFFFFFF )
      goto LABEL_44;
    v28 = 2147483646;
    v29 = v12;
    v30 = v13;
    do
    {
      if ( !v28 )
        break;
      if ( !*v5 )
        break;
      *v30++ = *v5++;
      --v28;
      --v29;
    }
    while ( v29 );
    v31 = v30 - 1;
    if ( v29 )
      v31 = v30;
    goto LABEL_43;
  }
  if ( v12 )
  {
    if ( v12 > 0x7FFFFFFF )
      goto LABEL_44;
    v15 = (unsigned __int16 *)*((_QWORD *)this + 8);
    v16 = 2147483646;
    v17 = (unsigned int)v12;
    v18 = v13;
    do
    {
      if ( !v16 )
        break;
      if ( !*v15 )
        break;
      *v18++ = *v15++;
      --v16;
      --v17;
    }
    while ( v17 );
    v19 = v18 - 1;
    if ( v17 )
      v19 = v18;
    *v19 = 0;
    v20 = v12;
    v21 = v13;
    do
    {
      if ( !*v21 )
        break;
      ++v21;
      --v20;
    }
    while ( v20 );
    if ( v20 )
    {
      v22 = v20;
      v23 = L"\\";
      v24 = &v13[v12 - v20];
      v25 = 2147483646;
      do
      {
        if ( !v25 )
          break;
        if ( !*v23 )
          break;
        *v24++ = *v23++;
        --v25;
        --v22;
      }
      while ( v22 );
      v26 = v24 - 1;
      if ( v22 )
        v26 = v24;
      v27 = v12;
      *v26 = 0;
      goto LABEL_63;
    }
  }
  v27 = v12;
  if ( v12 )
  {
LABEL_63:
    v40 = v13;
    v41 = v12;
    do
    {
      if ( !*v40 )
        break;
      ++v40;
      --v41;
    }
    while ( v41 );
    v42 = v27 - v41;
    if ( !v41 )
      goto LABEL_44;
    v43 = &v13[v42];
    v44 = 2147483646;
    for ( i = v27 - v42; i; --i )
    {
      if ( !v44 )
        break;
      if ( !*v5 )
        break;
      *v43++ = *v5++;
      --v44;
    }
    v31 = v43 - 1;
    if ( i )
      v31 = v43;
LABEL_43:
    *v31 = 0;
  }
LABEL_44:
  if ( v8 && v12 && v12 <= 0x7FFFFFFF )
  {
    v32 = v12;
    v33 = v13;
    while ( *v33 )
    {
      ++v33;
      if ( !--v32 )
      {
        v34 = 0;
        goto LABEL_51;
      }
    }
    v34 = v12 - v32;
LABEL_51:
    if ( v32 )
    {
      v35 = v12 - v34;
      v36 = L".job";
      for ( j = &v13[v34]; v35; --v35 )
      {
        if ( !v14 )
          break;
        if ( !*v36 )
          break;
        *j++ = *v36++;
        --v14;
      }
      v38 = j - 1;
      if ( v35 )
        v38 = j;
      *v38 = 0;
    }
  }
  *a3 = v13;
  return 0;
}

```

## disassembly

```asm
0x180006120  push    rbx
0x180006122  push    rdi
0x180006123  push    r12
0x180006125  push    r13
0x180006127  push    r14
0x180006129  sub     rsp, 20h
0x18000612d  mov     r13, 0FFFFFFFFFFFFFFFFh
0x180006134  mov     r12, r8
0x180006137  mov     rbx, r13
0x18000613a  mov     rdi, rdx
0x18000613d  mov     r14, rcx
0x180006140  inc     rbx
0x180006143  cmp     word ptr [rdx+rbx*2], 0
0x180006148  jnz     short loc_180006140
0x18000614a  mov     [rsp+48h+arg_0], rbp
0x18000614f  mov     [rsp+48h+arg_10], r15
0x180006154  test    ebx, ebx
0x180006156  jz      loc_1800063D3
0x18000615c  cmp     ebx, 1
0x18000615f  jbe     short loc_18000617C
0x180006161  lea     eax, [rbx-1]
0x180006164  movzx   eax, word ptr [rdx+rax*2]
0x180006168  cmp     ax, 5Ch ; '\'
0x18000616c  jz      loc_1800063D3
0x180006172  cmp     ax, 2Fh ; '/'
0x180006176  jz      loc_1800063D3
0x18000617c  mov     r15d, 1
0x180006182  mov     ebp, r15d
0x180006185  cmp     ebx, 2
0x180006188  jbe     short loc_1800061AF
0x18000618a  movzx   ecx, word ptr [rdx+2]
0x18000618e  cmp     cx, 3Ah ; ':'
0x180006192  jz      loc_1800064A8
0x180006198  movzx   eax, word ptr [rdx]
0x18000619b  cmp     ax, 5Ch ; '\'
0x18000619f  jz      loc_180006493
0x1800061a5  cmp     ax, 2Fh ; '/'
0x1800061a9  jz      loc_18000649E
0x1800061af  mov     edx, 2Eh ; '.'; Ch
0x1800061b4  mov     rcx, rdi; Str
0x1800061b7  call    cs:__imp_wcsrchr
0x1800061bd  test    rax, rax
0x1800061c0  jnz     loc_1800064AF
0x1800061c6  add     ebx, 4
0x1800061c9  mov     [rsp+48h+arg_8], rsi
0x1800061ce  test    ebp, ebp
0x1800061d0  jnz     loc_180006470
0x1800061d6  inc     ebx
0x1800061d8  mov     eax, 2
0x1800061dd  mul     rbx
0x1800061e0  mov     esi, 40h ; '@'
0x1800061e5  cmovb   rax, r13
0x1800061e9  mov     rcx, rax; Size
0x1800061ec  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800061f1  mov     r11, rax
0x1800061f4  test    rax, rax
0x1800061f7  jz      loc_1800063DA
0x1800061fd  xor     eax, eax
0x1800061ff  mov     r10d, 7FFFFFFEh
0x180006205  mov     [r11], ax
0x180006209  test    ebp, ebp
0x18000620b  jz      loc_1800062E2
0x180006211  test    rbx, rbx
0x180006214  jz      loc_1800063E1
0x18000621a  cmp     rbx, 7FFFFFFFh
0x180006221  ja      loc_180006331
0x180006227  mov     rdx, [rsi+r14]
0x18000622b  mov     ecx, r10d
0x18000622e  mov     r9d, ebx
0x180006231  mov     r8, r11
0x180006234  test    rcx, rcx
0x180006237  jz      short loc_180006256
0x180006239  movzx   eax, word ptr [rdx]
0x18000623c  test    ax, ax
0x18000623f  jz      short loc_180006256
0x180006241  mov     [r8], ax
0x180006245  add     rdx, 2
0x180006249  add     r8, 2
0x18000624d  dec     rcx
0x180006250  sub     r9, 1
0x180006254  jnz     short loc_180006234
0x180006256  test    r9, r9
0x180006259  lea     rcx, [r8-2]
0x18000625d  mov     r9, rbx
0x180006260  cmovnz  rcx, r8
0x180006264  xor     eax, eax
0x180006266  mov     [rcx], ax
0x180006269  mov     rcx, rbx
0x18000626c  mov     rax, r11
0x18000626f  nop
0x180006270  cmp     word ptr [rax], 0
0x180006274  jz      short loc_180006280
0x180006276  add     rax, 2
0x18000627a  sub     rcx, 1
0x18000627e  jnz     short loc_180006270
0x180006280  xor     eax, eax
0x180006282  mov     rdx, r9
0x180006285  sub     rdx, rcx
0x180006288  test    rcx, rcx
0x18000628b  cmovz   rdx, rax
0x18000628f  jz      loc_1800063E1
0x180006295  sub     r9, rdx
0x180006298  lea     r8, asc_18001D98C; "\\"
0x18000629f  lea     rdx, [r11+rdx*2]
0x1800062a3  mov     rax, r10
0x1800062a6  jz      short loc_1800062CA
0x1800062a8  test    rax, rax
0x1800062ab  jz      short loc_1800062CA
0x1800062ad  movzx   ecx, word ptr [r8]
0x1800062b1  test    cx, cx
0x1800062b4  jz      short loc_1800062CA
0x1800062b6  mov     [rdx], cx
0x1800062b9  add     r8, 2
0x1800062bd  add     rdx, 2
0x1800062c1  dec     rax
0x1800062c4  sub     r9, 1
0x1800062c8  jnz     short loc_1800062A8
0x1800062ca  test    r9, r9
0x1800062cd  lea     rcx, [rdx-2]
0x1800062d1  cmovnz  rcx, rdx
0x1800062d5  xor     eax, eax
0x1800062d7  mov     rdx, rbx
0x1800062da  mov     [rcx], ax
0x1800062dd  jmp     loc_1800063FA
0x1800062e2  test    rbx, rbx
0x1800062e5  jz      short loc_180006331
0x1800062e7  cmp     rbx, 7FFFFFFFh
0x1800062ee  ja      short loc_180006331
0x1800062f0  mov     rax, r10
0x1800062f3  mov     r8, rbx
0x1800062f6  mov     rdx, r11
0x1800062f9  nop     dword ptr [rax+00000000h]
0x180006300  test    rax, rax
0x180006303  jz      short loc_180006321
0x180006305  movzx   ecx, word ptr [rdi]
0x180006308  test    cx, cx
0x18000630b  jz      short loc_180006321
0x18000630d  mov     [rdx], cx
0x180006310  add     rdi, 2
0x180006314  add     rdx, 2
0x180006318  dec     rax
0x18000631b  sub     r8, 1
0x18000631f  jnz     short loc_180006300
0x180006321  test    r8, r8
0x180006324  lea     rcx, [rdx-2]
0x180006328  cmovnz  rcx, rdx
0x18000632c  xor     eax, eax
0x18000632e  mov     [rcx], ax
0x180006331  test    r15d, r15d
0x180006334  jz      short loc_1800063B1
0x180006336  test    rbx, rbx
0x180006339  jz      short loc_1800063B1
0x18000633b  cmp     rbx, 7FFFFFFFh
0x180006342  ja      short loc_1800063B1
0x180006344  mov     rcx, rbx
0x180006347  mov     rax, r11
0x18000634a  nop     word ptr [rax+rax+00h]
0x180006350  cmp     word ptr [rax], 0
0x180006354  jz      loc_180006465
0x18000635a  add     rax, 2
0x18000635e  sub     rcx, 1
0x180006362  jnz     short loc_180006350
0x180006364  xor     eax, eax
0x180006366  test    rcx, rcx
0x180006369  jz      short loc_1800063B1
0x18000636b  sub     rbx, rax
0x18000636e  lea     rdx, aJob; ".job"
0x180006375  lea     rax, [r11+rax*2]
0x180006379  jz      short loc_1800063A1
0x18000637b  nop     dword ptr [rax+rax+00h]
0x180006380  test    r10, r10
0x180006383  jz      short loc_1800063A1
0x180006385  movzx   ecx, word ptr [rdx]
0x180006388  test    cx, cx
0x18000638b  jz      short loc_1800063A1
0x18000638d  mov     [rax], cx
0x180006390  add     rdx, 2
0x180006394  add     rax, 2
0x180006398  dec     r10
0x18000639b  sub     rbx, 1
0x18000639f  jnz     short loc_180006380
0x1800063a1  test    rbx, rbx
0x1800063a4  lea     rcx, [rax-2]
0x1800063a8  cmovnz  rcx, rax
0x1800063ac  xor     eax, eax
0x1800063ae  mov     [rcx], ax
0x1800063b1  mov     [r12], r11
0x1800063b5  xor     eax, eax
0x1800063b7  mov     rsi, [rsp+48h+arg_8]
0x1800063bc  mov     r15, [rsp+48h+arg_10]
0x1800063c1  mov     rbp, [rsp+48h+arg_0]
0x1800063c6  add     rsp, 20h
0x1800063ca  pop     r14
0x1800063cc  pop     r13
0x1800063ce  pop     r12
0x1800063d0  pop     rdi
0x1800063d1  pop     rbx
0x1800063d2  retn
0x1800063d3  mov     eax, 80070057h
0x1800063d8  jmp     short loc_1800063BC
0x1800063da  mov     eax, 8007000Eh
0x1800063df  jmp     short loc_1800063B7
0x1800063e1  mov     rdx, rbx
0x1800063e4  test    rbx, rbx
0x1800063e7  jz      loc_180006331
0x1800063ed  cmp     rbx, 7FFFFFFFh
0x1800063f4  ja      loc_180006331
0x1800063fa  mov     rax, r11
0x1800063fd  mov     rcx, rbx
0x180006400  cmp     word ptr [rax], 0
0x180006404  jz      short loc_180006410
0x180006406  add     rax, 2
0x18000640a  sub     rcx, 1
0x18000640e  jnz     short loc_180006400
0x180006410  xor     eax, eax
0x180006412  mov     r8, rdx
0x180006415  sub     r8, rcx
0x180006418  test    rcx, rcx
0x18000641b  cmovz   r8, rax
0x18000641f  jz      loc_180006331
0x180006425  lea     rax, [r11+r8*2]
0x180006429  mov     rcx, r10
0x18000642c  sub     rdx, r8
0x18000642f  jz      short loc_180006455
0x180006431  test    rcx, rcx
0x180006434  jz      short loc_180006455
0x180006436  movzx   r8d, word ptr [rdi]
0x18000643a  test    r8w, r8w
0x18000643e  jz      short loc_180006455
0x180006440  mov     [rax], r8w
0x180006444  add     rdi, 2
0x180006448  add     rax, 2
0x18000644c  dec     rcx
0x18000644f  sub     rdx, 1
0x180006453  jnz     short loc_180006431
0x180006455  test    rdx, rdx
0x180006458  lea     rcx, [rax-2]
0x18000645c  cmovnz  rcx, rax
0x180006460  jmp     loc_18000632C
0x180006465  mov     rax, rbx
0x180006468  sub     rax, rcx
0x18000646b  jmp     loc_180006366
0x180006470  mov     rcx, [r14+40h]
0x180006474  mov     rax, r13
0x180006477  nop     word ptr [rax+rax+00000000h]
0x180006480  inc     rax
0x180006483  cmp     word ptr [rcx+rax*2], 0
0x180006488  jnz     short loc_180006480
0x18000648a  inc     ebx
0x18000648c  add     ebx, eax
0x18000648e  jmp     loc_1800061D6
0x180006493  cmp     cx, 5Ch ; '\'
0x180006497  jz      short loc_1800064A8
0x180006499  jmp     loc_1800061AF
0x18000649e  cmp     cx, 2Fh ; '/'
0x1800064a2  jnz     loc_1800061AF
0x1800064a8  xor     ebp, ebp
0x1800064aa  jmp     loc_1800061AF
0x1800064af  mov     rdx, rax
0x1800064b2  mov     ecx, ebx
0x1800064b4  sub     rdx, rdi
0x1800064b7  sar     rdx, 1
0x1800064ba  sub     rcx, rdx
0x1800064bd  cmp     rcx, 4
0x1800064c1  ja      loc_1800061C6
0x1800064c7  lea     rcx, [rax+2]; String1
0x1800064cb  lea     rdx, aJob_0; "job"
0x1800064d2  call    cs:__imp__wcsicmp
0x1800064d8  test    eax, eax
0x1800064da  jnz     loc_1800063D3
0x1800064e0  xor     r15d, r15d
0x1800064e3  jmp     loc_1800061C9
```
