# NgcUtils::CombineSeparateStrings(ushort const *,ushort const *,ushort const *,ushort * *)

- ea: `0x180006150`
- end: `0x180006530`
- name: `?CombineSeparateStrings@NgcUtils@@YAJPEBG00PEAPEAG@Z`
- size: `992`
- prototype: `__int64 __fastcall(NgcUtils *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180027f54`

## callees

- `0x180006150`
- `0x180006538`
- `0x180031894`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000646f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800062b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000646f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006251`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180006251`

## string_xrefs

- `0x180006268`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800062a0`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x18000645d`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800064cd`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x1800064f0`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180006515`: `onecore\ds\security\ngc\utils\common\lib\stringutils.cpp`
- `0x180006490`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
__int64 __fastcall NgcUtils::CombineSeparateStrings(
        NgcUtils *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        char *a4)
{
  const unsigned __int16 *v5; // r14
  NgcUtils *v6; // rbx
  NgcUtils *v7; // rax
  __int64 v8; // rcx
  int v9; // r12d
  __int64 v10; // r8
  int v11; // edi
  __int64 v12; // rcx
  const unsigned __int16 *v13; // rax
  __int64 v14; // rdx
  int v15; // edi
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  __int64 v18; // r10
  int v19; // edi
  unsigned __int64 v20; // rdi
  char *v21; // rax
  char *v22; // r15
  char *v24; // rax
  unsigned int v25; // ebp
  __int64 v26; // r9
  unsigned __int64 v27; // rdx
  __int64 v28; // rcx
  char *v29; // r8
  char *v30; // rax
  unsigned int v31; // ebx
  unsigned __int64 v32; // rcx
  _WORD *v33; // rax
  unsigned __int64 v34; // rax
  char *v35; // r8
  __int64 v36; // rcx
  unsigned __int64 v37; // rdx
  char *v38; // rax
  unsigned __int64 v39; // rcx
  _WORD *v40; // rax
  unsigned __int64 v41; // rax
  char *v42; // rcx
  unsigned __int64 i; // rdi
  __int64 v44; // rdx
  int v45; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v5 = a2;
  v6 = this;
  if ( !this )
  {
    v11 = -2147024809;
LABEL_79:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB3,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)(unsigned int)v11,
      v45);
    return (unsigned int)v11;
  }
  v7 = this;
  v8 = 260;
  while ( *(_WORD *)v7 )
  {
    v7 = (NgcUtils *)((char *)v7 + 2);
    if ( !--v8 )
    {
      v9 = -2147024809;
      v10 = 0;
      v11 = -2147024809;
      goto LABEL_7;
    }
  }
  v9 = -2147024809;
  v10 = 260 - v8;
  v11 = 0;
LABEL_7:
  if ( v11 < 0 )
    goto LABEL_79;
  if ( !a2 )
  {
    v15 = -2147024809;
LABEL_77:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)(unsigned int)v15,
      v45);
    return (unsigned int)v15;
  }
  v12 = 260;
  v13 = a2;
  while ( *v13 )
  {
    ++v13;
    if ( !--v12 )
    {
      v14 = 0;
      v15 = -2147024809;
      goto LABEL_14;
    }
  }
  v15 = 0;
  v14 = 260 - v12;
LABEL_14:
  if ( v15 < 0 )
    goto LABEL_77;
  if ( !a3 )
  {
    v19 = -2147024809;
LABEL_75:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBF,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)(unsigned int)v19,
      v45);
    return (unsigned int)v19;
  }
  v16 = 260;
  v17 = a3;
  while ( *v17 )
  {
    ++v17;
    if ( !--v16 )
    {
      v18 = 0;
      v19 = -2147024809;
      goto LABEL_21;
    }
  }
  v18 = 260 - v16;
  v19 = 0;
LABEL_21:
  if ( v19 < 0 )
    goto LABEL_75;
  v20 = v10 + v18 + v14 + 1;
  if ( v20 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v21 = (char *)LocalAlloc(0, 2 * v20 + 2);
  v22 = v21;
  if ( !v21 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)0x8007000ELL,
      v45);
    return 2147942414LL;
  }
  *(_WORD *)v21 = 0;
  *(_WORD *)&v21[2 * v20] = 0;
  if ( !v20 )
  {
    v31 = -2147024809;
    goto LABEL_65;
  }
  if ( v20 > 0x7FFFFFFF )
  {
    v31 = -2147024809;
    *(_WORD *)v21 = 0;
LABEL_65:
    v44 = 205;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v44,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v31,
      v45);
    LocalFree(v22);
    return v31;
  }
  v26 = 2147483646;
  v27 = v20;
  v28 = 2147483646;
  v29 = v21;
  do
  {
    if ( !v28 )
      break;
    if ( !*(_WORD *)v6 )
      break;
    *(_WORD *)v29 = *(_WORD *)v6;
    v6 = (NgcUtils *)((char *)v6 + 2);
    v29 += 2;
    --v28;
    --v27;
  }
  while ( v27 );
  v30 = v29 - 2;
  v25 = -2147024774;
  if ( v27 )
    v30 = v29;
  v31 = -2147024774;
  if ( v27 )
    v31 = 0;
  *(_WORD *)v30 = 0;
  if ( !v27 )
    goto LABEL_65;
  v32 = v20;
  v33 = v22;
  do
  {
    if ( !*v33 )
      break;
    ++v33;
    --v32;
  }
  while ( v32 );
  v31 = -2147024809;
  if ( v32 )
  {
    v31 = 0;
    v34 = v20 - v32;
  }
  else
  {
    v34 = 0;
  }
  if ( !v32 )
    goto LABEL_67;
  v35 = &v22[2 * v34];
  v36 = 2147483646;
  v37 = v20 - v34;
  if ( v20 != v34 )
  {
    do
    {
      if ( !v36 )
        break;
      if ( !*v5 )
        break;
      *(_WORD *)v35 = *v5++;
      v35 += 2;
      --v36;
      --v37;
    }
    while ( v37 );
  }
  v38 = v35 - 2;
  v31 = -2147024774;
  if ( v37 )
  {
    v38 = v35;
    v31 = 0;
  }
  *(_WORD *)v38 = 0;
  if ( !v37 )
  {
LABEL_67:
    v44 = 210;
    goto LABEL_66;
  }
  v39 = v20;
  v40 = v22;
  do
  {
    if ( !*v40 )
      break;
    ++v40;
    --v39;
  }
  while ( v39 );
  if ( v39 )
  {
    v9 = 0;
    v41 = v20 - v39;
  }
  else
  {
    v41 = 0;
  }
  if ( !v39 )
  {
    v25 = v9;
LABEL_28:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD7,
      (unsigned int)"onecore\\ds\\security\\ngc\\utils\\common\\lib\\stringutils.cpp",
      (const char *)v25,
      v45);
    LocalFree(v22);
    return v25;
  }
  v42 = &v22[2 * v41];
  for ( i = v20 - v41; i; --i )
  {
    if ( !v26 )
      break;
    if ( !*a3 )
      break;
    *(_WORD *)v42 = *a3++;
    v42 += 2;
    --v26;
  }
  v24 = v42 - 2;
  if ( i )
  {
    v24 = v42;
    v25 = 0;
  }
  *(_WORD *)v24 = 0;
  if ( !i )
    goto LABEL_28;
  *(_QWORD *)a4 = v22;
  return 0;
}

```

## disassembly

```asm
0x180006150  mov     [rsp+arg_10], rbx
0x180006155  mov     [rsp+arg_18], r9
0x18000615a  push    rsi
0x18000615b  push    rdi
0x18000615c  push    r12
0x18000615e  push    r13
0x180006160  push    r14; int
0x180006162  sub     rsp, 20h
0x180006166  mov     rsi, r8
0x180006169  mov     r14, rdx
0x18000616c  mov     rbx, rcx
0x18000616f  test    rcx, rcx
0x180006172  jz      loc_18000650B
0x180006178  mov     r10d, 104h
0x18000617e  mov     rax, rbx
0x180006181  mov     ecx, r10d
0x180006184  cmp     word ptr [rax], 0
0x180006188  jz      short loc_1800061A5
0x18000618a  add     rax, 2
0x18000618e  sub     rcx, 1
0x180006192  jnz     short loc_180006184
0x180006194  xor     r13d, r13d
0x180006197  mov     r12d, 80070057h
0x18000619d  mov     r8d, r13d
0x1800061a0  mov     edi, r12d
0x1800061a3  jmp     short loc_1800061B7
0x1800061a5  mov     r8, r10
0x1800061a8  mov     r12d, 80070057h
0x1800061ae  sub     r8, rcx
0x1800061b1  xor     r13d, r13d
0x1800061b4  mov     edi, r13d
0x1800061b7  test    edi, edi
0x1800061b9  js      loc_180006510
0x1800061bf  test    rdx, rdx
0x1800061c2  jz      loc_1800064E8
0x1800061c8  mov     rcx, r10
0x1800061cb  mov     rax, rdx
0x1800061ce  xchg    ax, ax
0x1800061d0  cmp     word ptr [rax], 0
0x1800061d4  jz      short loc_1800061E8
0x1800061d6  add     rax, 2
0x1800061da  sub     rcx, 1
0x1800061de  jnz     short loc_1800061D0
0x1800061e0  mov     rdx, r13
0x1800061e3  mov     edi, r12d
0x1800061e6  jmp     short loc_1800061F1
0x1800061e8  mov     rdx, r10
0x1800061eb  mov     edi, r13d
0x1800061ee  sub     rdx, rcx
0x1800061f1  test    edi, edi
0x1800061f3  js      loc_1800064EB
0x1800061f9  test    rsi, rsi
0x1800061fc  jz      loc_1800064C5
0x180006202  mov     rcx, r10
0x180006205  mov     rax, rsi
0x180006208  cmp     word ptr [rax], 0
0x18000620c  jz      short loc_180006220
0x18000620e  add     rax, 2
0x180006212  sub     rcx, 1
0x180006216  jnz     short loc_180006208
0x180006218  mov     r10, r13
0x18000621b  mov     edi, r12d
0x18000621e  jmp     short loc_180006226
0x180006220  sub     r10, rcx
0x180006223  mov     edi, r13d
0x180006226  test    edi, edi
0x180006228  js      loc_1800064C8
0x18000622e  lea     rdi, [rdx+1]
0x180006232  add     rdi, r10
0x180006235  add     rdi, r8
0x180006238  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x18000623c  jz      loc_18000648B
0x180006242  lea     rdx, ds:2[rdi*2]; uBytes
0x18000624a  mov     [rsp+48h+arg_8], r15
0x18000624f  xor     ecx, ecx; uFlags
0x180006251  call    cs:__imp_LocalAlloc
0x180006257  mov     r15, rax
0x18000625a  test    rax, rax
0x18000625d  jnz     loc_1800062E7
0x180006263  mov     rcx, [rsp+48h]; this
0x180006268  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000626f  mov     r9d, 8007000Eh; char *
0x180006275  mov     edx, 0C7h; void *
0x18000627a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000627f  mov     eax, 8007000Eh
0x180006284  jmp     short loc_1800062C4
0x180006286  test    rdi, rdi
0x180006289  lea     rax, [rcx-2]
0x18000628d  cmovnz  rax, rcx
0x180006291  cmovnz  ebp, r13d
0x180006295  mov     [rax], r13w
0x180006299  jnz     short loc_1800062DB
0x18000629b  mov     rcx, [rsp+48h]; this
0x1800062a0  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800062a7  mov     r9d, ebp; char *
0x1800062aa  mov     edx, 0D7h; void *
0x1800062af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800062b4  mov     rcx, r15; hMem
0x1800062b7  call    cs:__imp_LocalFree
0x1800062bd  mov     eax, ebp
0x1800062bf  mov     rbp, [rsp+48h+arg_0]
0x1800062c4  mov     r15, [rsp+48h+arg_8]
0x1800062c9  mov     rbx, [rsp+48h+arg_10]
0x1800062ce  add     rsp, 20h
0x1800062d2  pop     r14
0x1800062d4  pop     r13
0x1800062d6  pop     r12
0x1800062d8  pop     rdi
0x1800062d9  pop     rsi
0x1800062da  retn
0x1800062db  mov     rax, [rsp+48h+arg_18]
0x1800062e0  mov     [rax], r15
0x1800062e3  xor     eax, eax
0x1800062e5  jmp     short loc_1800062BF
0x1800062e7  mov     [rax], r13w
0x1800062eb  mov     [rax+rdi*2], r13w
0x1800062f0  mov     [rsp+48h+arg_0], rbp
0x1800062f5  test    rdi, rdi
0x1800062f8  jz      loc_1800064B7
0x1800062fe  cmp     rdi, 7FFFFFFFh
0x180006305  ja      loc_1800064A2
0x18000630b  mov     r9d, 7FFFFFFEh
0x180006311  mov     rdx, rdi
0x180006314  mov     ecx, r9d
0x180006317  mov     r8, r15
0x18000631a  nop     word ptr [rax+rax+00h]
0x180006320  test    rcx, rcx
0x180006323  jz      short loc_180006342
0x180006325  movzx   eax, word ptr [rbx]
0x180006328  test    ax, ax
0x18000632b  jz      short loc_180006342
0x18000632d  mov     [r8], ax
0x180006331  add     rbx, 2
0x180006335  add     r8, 2
0x180006339  dec     rcx
0x18000633c  sub     rdx, 1
0x180006340  jnz     short loc_180006320
0x180006342  test    rdx, rdx
0x180006345  lea     rax, [r8-2]
0x180006349  mov     ebp, 8007007Ah
0x18000634e  cmovnz  rax, r8
0x180006352  mov     ebx, ebp
0x180006354  cmovnz  ebx, r13d
0x180006358  mov     [rax], r13w
0x18000635c  jz      loc_180006453
0x180006362  mov     rcx, rdi
0x180006365  mov     rax, r15
0x180006368  cmp     word ptr [rax], 0
0x18000636c  jz      short loc_180006378
0x18000636e  add     rax, 2
0x180006372  sub     rcx, 1
0x180006376  jnz     short loc_180006368
0x180006378  test    rcx, rcx
0x18000637b  mov     ebx, r12d
0x18000637e  cmovnz  ebx, r13d
0x180006382  jz      loc_1800064A7
0x180006388  mov     rax, rdi
0x18000638b  sub     rax, rcx
0x18000638e  test    rcx, rcx
0x180006391  jz      loc_18000647C
0x180006397  mov     rdx, rdi
0x18000639a  lea     r8, [r15+rax*2]
0x18000639e  mov     rcx, r9
0x1800063a1  sub     rdx, rax
0x1800063a4  jz      short loc_1800063C9
0x1800063a6  test    rcx, rcx
0x1800063a9  jz      short loc_1800063C9
0x1800063ab  movzx   eax, word ptr [r14]
0x1800063af  test    ax, ax
0x1800063b2  jz      short loc_1800063C9
0x1800063b4  mov     [r8], ax
0x1800063b8  add     r14, 2
0x1800063bc  add     r8, 2
0x1800063c0  dec     rcx
0x1800063c3  sub     rdx, 1
0x1800063c7  jnz     short loc_1800063A6
0x1800063c9  test    rdx, rdx
0x1800063cc  lea     rax, [r8-2]
0x1800063d0  mov     ebx, ebp
0x1800063d2  cmovnz  rax, r8
0x1800063d6  cmovnz  ebx, r13d
0x1800063da  mov     [rax], r13w
0x1800063de  jz      loc_18000647C
0x1800063e4  mov     rcx, rdi
0x1800063e7  mov     rax, r15
0x1800063ea  nop     word ptr [rax+rax+00h]
0x1800063f0  cmp     word ptr [rax], 0
0x1800063f4  jz      short loc_180006400
0x1800063f6  add     rax, 2
0x1800063fa  sub     rcx, 1
0x1800063fe  jnz     short loc_1800063F0
0x180006400  test    rcx, rcx
0x180006403  cmovnz  r12d, r13d
0x180006407  jz      loc_1800064AF
0x18000640d  mov     rax, rdi
0x180006410  sub     rax, rcx
0x180006413  test    rcx, rcx
0x180006416  jz      short loc_180006483
0x180006418  lea     rcx, [r15+rax*2]
0x18000641c  sub     rdi, rax
0x18000641f  jz      loc_180006286
0x180006425  test    r9, r9
0x180006428  jz      loc_180006286
0x18000642e  movzx   eax, word ptr [rsi]
0x180006431  test    ax, ax
0x180006434  jz      loc_180006286
0x18000643a  mov     [rcx], ax
0x18000643d  add     rsi, 2
0x180006441  add     rcx, 2
0x180006445  dec     r9
0x180006448  sub     rdi, 1
0x18000644c  jnz     short loc_180006425
0x18000644e  jmp     loc_180006286
0x180006453  mov     edx, 0CDh; void *
0x180006458  mov     rcx, [rsp+48h]; this
0x18000645d  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x180006464  mov     r9d, ebx; char *
0x180006467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000646c  mov     rcx, r15; hMem
0x18000646f  call    cs:__imp_LocalFree
0x180006475  mov     eax, ebx
0x180006477  jmp     loc_1800062BF
0x18000647c  mov     edx, 0D2h
0x180006481  jmp     short loc_180006458
0x180006483  mov     ebp, r12d
0x180006486  jmp     loc_18000629B
0x18000648b  mov     rcx, [rsp+48h]; this
0x180006490  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006497  mov     edx, 0F89h; void *
0x18000649c  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800064a2  mov     ebx, r12d
0x1800064a5  jmp     short loc_1800064BF
0x1800064a7  mov     rax, r13
0x1800064aa  jmp     loc_18000638E
0x1800064af  mov     rax, r13
0x1800064b2  jmp     loc_180006413
0x1800064b7  mov     ebx, r12d
0x1800064ba  test    rdi, rdi
0x1800064bd  jz      short loc_180006453
0x1800064bf  mov     [rax], r13w
0x1800064c3  jmp     short loc_180006453
0x1800064c5  mov     edi, r12d
0x1800064c8  mov     rcx, [rsp+48h]; this
0x1800064cd  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800064d4  mov     r9d, edi; char *
0x1800064d7  mov     edx, 0BFh; void *
0x1800064dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800064e1  mov     eax, edi
0x1800064e3  jmp     loc_1800062C9
0x1800064e8  mov     edi, r12d
0x1800064eb  mov     rcx, [rsp+48h]; this
0x1800064f0  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x1800064f7  mov     r9d, edi; char *
0x1800064fa  mov     edx, 0B9h; void *
0x1800064ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006504  mov     eax, edi
0x180006506  jmp     loc_1800062C9
0x18000650b  mov     edi, 80070057h
0x180006510  mov     rcx, [rsp+48h]; this
0x180006515  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\ngc\\utils\\comm"...
0x18000651c  mov     r9d, edi; char *
0x18000651f  mov     edx, 0B3h; void *
0x180006524  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180006529  mov     eax, edi
0x18000652b  jmp     loc_1800062C9
```
