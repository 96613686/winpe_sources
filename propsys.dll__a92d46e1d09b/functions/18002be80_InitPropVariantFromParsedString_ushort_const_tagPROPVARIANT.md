# _InitPropVariantFromParsedString(ushort const *,tagPROPVARIANT *)

- ea: `0x18002be80`
- end: `0x18002c283`
- name: `?_InitPropVariantFromParsedString@@YAJPEBGPEAUtagPROPVARIANT@@@Z`
- size: `1027`
- prototype: `__int64 __fastcall(const unsigned __int16 *, struct tagPROPVARIANT *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002bcd0`
- `0x18002bd14`

## callees

- `0x180007f40`
- `0x18002be80`
- `0x18002d070`
- `0x18006ed20`
- `0x18006fb98`

## import_xrefs

- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002bfbe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002c05d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002bfbe`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrChrW` at `0x18002c05d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x18002c079`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrTrimW` at `0x18002c079`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002bec5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002c082`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002bec5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18002c082`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c1c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002bfa4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c1b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002c1c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c00e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c1d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c00e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002c1d2`

## pseudocode

```c
__int64 __fastcall _InitPropVariantFromParsedString(const unsigned __int16 *a1, struct tagPROPVARIANT *a2)
{
  WCHAR *v2; // r12
  const unsigned __int16 *v3; // rbx
  unsigned int v4; // eax
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // rdx
  _WORD *v8; // rax
  _WORD *v9; // rdx
  int v10; // esi
  int v12; // ebx
  const WCHAR *v13; // r8
  PWSTR v14; // rax
  int v15; // ecx
  bool v16; // zf
  unsigned int v17; // ebx
  void *v18; // rax
  void *v19; // r13
  size_t v20; // rax
  WCHAR *v21; // rdi
  __int64 v22; // rbp
  PWSTR v23; // rax
  WCHAR *v24; // r15
  unsigned __int64 v25; // rbx
  unsigned __int64 v26; // r14
  _WORD *v27; // r10
  unsigned __int64 v28; // rdx
  _WORD *v29; // r8
  __int64 v30; // rcx
  __int64 v31; // r9
  _WORD *v32; // rcx
  __int64 v33; // r14
  bool v34; // cf
  unsigned __int64 i; // rbx
  _WORD *v36; // rax
  int v37; // eax
  struct tagPROPVARIANT *v38; // rax
  WCHAR *v39; // [rsp+20h] [rbp-278h] BYREF
  struct tagPROPVARIANT *v40; // [rsp+28h] [rbp-270h]
  __int64 v41; // [rsp+30h] [rbp-268h]
  _BYTE pv[528]; // [rsp+40h] [rbp-258h] BYREF

  v2 = (WCHAR *)pv;
  v40 = a2;
  *(_OWORD *)&a2->vt = 0;
  a2->bstrblobVal.pData = 0;
  v3 = a1;
  v39 = (WCHAR *)pv;
  v4 = lstrlenW(a1);
  v6 = 260;
  if ( v4 >= 0x104 )
  {
    v37 = _AllocString<CTCoAllocPolicy>(260, v5, v3, &v39);
    v2 = v39;
    v10 = v37;
  }
  else
  {
    v7 = 2147483646;
    v8 = pv;
    do
    {
      if ( !v7 )
        break;
      if ( !*v3 )
        break;
      *v8++ = *v3++;
      --v7;
      --v6;
    }
    while ( v6 );
    v9 = v8 - 1;
    v10 = -2147024774;
    if ( v6 )
    {
      v9 = v8;
      v10 = 0;
    }
    *v9 = 0;
  }
  if ( v10 < 0 )
    goto LABEL_10;
  v12 = 0;
  v13 = v2;
  while ( v13 )
  {
    v14 = StrChrW(v13, 0x3Bu);
    v15 = v12 + 1;
    if ( !v14 )
      v15 = v12;
    v13 = v14 + 1;
    v12 = v15;
    if ( !v14 )
      v13 = 0;
  }
  v16 = v12 == -1;
  v17 = v12 + 1;
  LODWORD(v39) = v17;
  if ( v16 )
    goto LABEL_10;
  v41 = 0;
  if ( !is_mul_ok(v17, 8u) )
  {
    v10 = -2147024362;
    goto LABEL_10;
  }
  v18 = CoTaskMemAlloc(8LL * v17);
  v19 = v18;
  if ( v18 )
  {
    v20 = CTCoAllocPolicy::_CoTaskMemSize(v18);
    memset_0(v19, 0, v20);
    v10 = 0;
  }
  else
  {
    v10 = -2147024882;
  }
  if ( v10 < 0 )
    goto LABEL_10;
  v21 = v2;
  v22 = 0;
  while ( v21 && (unsigned int)v22 < v17 )
  {
    v23 = StrChrW(v21, 0x3Bu);
    v24 = v23;
    if ( v23 )
    {
      *v23 = 0;
      v24 = v23 + 1;
    }
    StrTrimW(v21, L" ");
    if ( lstrlenW(v21) <= 0 )
      goto LABEL_65;
    v25 = -1;
    do
      ++v25;
    while ( v21[v25] );
    v26 = v25 + 1;
    *((_QWORD *)v19 + v22) = 0;
    if ( v25 + 1 < v25 )
    {
      v10 = -2147024362;
      goto LABEL_54;
    }
    v41 = 0;
    if ( is_mul_ok(v26, 2u) )
    {
      v36 = CoTaskMemAlloc(2 * v26);
      v10 = 0;
      *((_QWORD *)v19 + v22) = v36;
      v27 = v36;
      if ( !v36 )
        v10 = -2147024882;
    }
    else
    {
      v27 = 0;
      v10 = -2147024362;
    }
    if ( v10 < 0 )
    {
      v17 = (unsigned int)v39;
LABEL_65:
      v21 = v24;
      if ( v10 < 0 )
        goto LABEL_54;
    }
    else
    {
      if ( !v27 && v25 != -1 || v26 > 0x7FFFFFFF )
      {
        *v27 = 0;
        goto LABEL_71;
      }
      if ( v25 >= 0x7FFFFFFF )
      {
        if ( v25 != -1 )
          *v27 = 0;
LABEL_71:
        v17 = (unsigned int)v39;
        v22 = (unsigned int)(v22 + 1);
        v21 = v24;
      }
      else
      {
        v28 = v25 + 1;
        v29 = v27;
        v30 = 0;
        do
        {
          if ( !v25 )
            break;
          if ( !*v21 )
            break;
          *v29++ = *v21++;
          --v25;
          ++v30;
          --v28;
        }
        while ( v28 );
        v31 = v30 - 1;
        if ( v28 )
          v31 = v30;
        v32 = v29 - 1;
        if ( v28 )
          v32 = v29;
        *v32 = 0;
        if ( !v28 )
          goto LABEL_71;
        v34 = v26 == v31;
        v33 = v26 - v31;
        if ( v34 || v33 == 1 || (unsigned __int64)(2 * v33) <= 2 )
          goto LABEL_71;
        memset_0(&v27[v31 + 1], 0, 2 * v33 - 2);
        v17 = (unsigned int)v39;
        v22 = (unsigned int)(v22 + 1);
        v21 = v24;
      }
    }
  }
  if ( (_DWORD)v22 )
  {
    v38 = v40;
    v40->vt = 4127;
    v38->lVal = v22;
    v38->bstrblobVal.pData = (BYTE *)v19;
    goto LABEL_10;
  }
LABEL_54:
  for ( i = 0; i < (unsigned int)v22; CoTaskMemFree(*((LPVOID *)v19 + i++)) )
    ;
  CoTaskMemFree(v19);
LABEL_10:
  if ( v2 && v2 != (WCHAR *)pv )
    CoTaskMemFree(v2);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18002be80  mov     r11, rsp
0x18002be83  push    rsi
0x18002be84  push    r12
0x18002be86  sub     rsp, 288h
0x18002be8d  mov     rax, cs:__security_cookie
0x18002be94  xor     rax, rsp
0x18002be97  mov     [rsp+298h+var_48], rax
0x18002be9f  mov     [r11+18h], rbx
0x18002bea3  lea     r12, [rsp+298h+pv]
0x18002bea8  xorps   xmm0, xmm0
0x18002beab  mov     [r11-30h], r14
0x18002beaf  xor     eax, eax
0x18002beb1  mov     [rsp+298h+var_270], rdx
0x18002beb6  movups  xmmword ptr [rdx], xmm0
0x18002beb9  mov     [rdx+10h], rax
0x18002bebd  mov     rbx, rcx
0x18002bec0  mov     [rsp+298h+var_278], r12
0x18002bec5  call    cs:__imp_lstrlenW
0x18002becb  mov     ecx, 104h
0x18002bed0  cmp     eax, ecx
0x18002bed2  jnb     loc_18002C1F2
0x18002bed8  mov     edx, 7FFFFFFEh
0x18002bedd  lea     rax, [rsp+298h+pv]
0x18002bee2  test    rdx, rdx
0x18002bee5  jz      short loc_18002BF06
0x18002bee7  movzx   r8d, word ptr [rbx]
0x18002beeb  test    r8w, r8w
0x18002beef  jz      short loc_18002BF06
0x18002bef1  mov     [rax], r8w
0x18002bef5  add     rbx, 2
0x18002bef9  add     rax, 2
0x18002befd  dec     rdx
0x18002bf00  sub     rcx, 1
0x18002bf04  jnz     short loc_18002BEE2
0x18002bf06  test    rcx, rcx
0x18002bf09  lea     rdx, [rax-2]
0x18002bf0d  mov     esi, 8007007Ah
0x18002bf12  cmovnz  rdx, rax
0x18002bf16  xor     eax, eax
0x18002bf18  test    rcx, rcx
0x18002bf1b  cmovnz  esi, eax
0x18002bf1e  mov     [rdx], ax
0x18002bf21  mov     [rsp+298h+var_18], rbp
0x18002bf29  mov     [rsp+298h+var_20], rdi
0x18002bf31  mov     [rsp+298h+var_28], r13
0x18002bf39  mov     [rsp+298h+var_38], r15
0x18002bf41  test    esi, esi
0x18002bf43  jns     short loc_18002BFAC
0x18002bf45  mov     r15, [rsp+298h+var_38]
0x18002bf4d  mov     r14, [rsp+298h+var_30]
0x18002bf55  mov     r13, [rsp+298h+var_28]
0x18002bf5d  mov     rdi, [rsp+298h+var_20]
0x18002bf65  mov     rbp, [rsp+298h+var_18]
0x18002bf6d  mov     rbx, [rsp+298h+arg_10]
0x18002bf75  test    r12, r12
0x18002bf78  jnz     short loc_18002BF97
0x18002bf7a  mov     eax, esi
0x18002bf7c  mov     rcx, [rsp+298h+var_48]
0x18002bf84  xor     rcx, rsp; StackCookie
0x18002bf87  call    __security_check_cookie
0x18002bf8c  add     rsp, 288h
0x18002bf93  pop     r12
0x18002bf95  pop     rsi
0x18002bf96  retn
0x18002bf97  lea     rax, [rsp+298h+pv]
0x18002bf9c  cmp     r12, rax
0x18002bf9f  jz      short loc_18002BF7A
0x18002bfa1  mov     rcx, r12; pv
0x18002bfa4  call    cs:__imp_CoTaskMemFree
0x18002bfaa  jmp     short loc_18002BF7A
0x18002bfac  xor     ebx, ebx
0x18002bfae  mov     r8, r12
0x18002bfb1  test    r12, r12
0x18002bfb4  jz      short loc_18002BFDC
0x18002bfb6  mov     edx, 3Bh ; ';'; wMatch
0x18002bfbb  mov     rcx, r8; pszStart
0x18002bfbe  call    cs:__imp_StrChrW
0x18002bfc4  test    rax, rax
0x18002bfc7  lea     ecx, [rbx+1]
0x18002bfca  cmovz   ecx, ebx
0x18002bfcd  lea     r8, [rax+2]
0x18002bfd1  mov     ebx, ecx
0x18002bfd3  cmovz   r8, rax
0x18002bfd7  test    r8, r8
0x18002bfda  jnz     short loc_18002BFB6
0x18002bfdc  add     ebx, 1
0x18002bfdf  mov     dword ptr [rsp+298h+var_278], ebx
0x18002bfe3  jz      loc_18002BF45
0x18002bfe9  mov     ecx, ebx
0x18002bfeb  mov     eax, 8
0x18002bff0  mul     rcx
0x18002bff3  mov     [rsp+298h+var_268], 0
0x18002bffc  test    rdx, rdx
0x18002bfff  jz      short loc_18002C00B
0x18002c001  mov     esi, 80070216h
0x18002c006  jmp     loc_18002BF45
0x18002c00b  mov     rcx, rax; cb
0x18002c00e  call    cs:__imp_CoTaskMemAlloc
0x18002c014  mov     r13, rax
0x18002c017  test    rax, rax
0x18002c01a  jz      loc_18002C229
0x18002c020  mov     rcx, rax; void *
0x18002c023  call    ?_CoTaskMemSize@CTCoAllocPolicy@@CA_KPEAX@Z; CTCoAllocPolicy::_CoTaskMemSize(void *)
0x18002c028  mov     r8, rax; Size
0x18002c02b  xor     edx, edx; Val
0x18002c02d  mov     rcx, r13; void *
0x18002c030  call    memset_0
0x18002c035  xor     esi, esi
0x18002c037  test    esi, esi
0x18002c039  js      loc_18002BF45
0x18002c03f  mov     rdi, r12
0x18002c042  xor     ebp, ebp
0x18002c044  test    rdi, rdi
0x18002c047  jz      loc_18002C20F
0x18002c04d  cmp     ebp, ebx
0x18002c04f  jnb     loc_18002C20B
0x18002c055  mov     edx, 3Bh ; ';'; wMatch
0x18002c05a  mov     rcx, rdi; pszStart
0x18002c05d  call    cs:__imp_StrChrW
0x18002c063  mov     r15, rax
0x18002c066  test    rax, rax
0x18002c069  jnz     loc_18002C233
0x18002c06f  lea     rdx, pszTrimChars; " "
0x18002c076  mov     rcx, rdi; psz
0x18002c079  call    cs:__imp_StrTrimW
0x18002c07f  mov     rcx, rdi; lpString
0x18002c082  call    cs:__imp_lstrlenW
0x18002c088  test    eax, eax
0x18002c08a  jle     loc_18002C249
0x18002c090  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x18002c097  nop     word ptr [rax+rax+00000000h]
0x18002c0a0  inc     rbx
0x18002c0a3  cmp     word ptr [rdi+rbx*2], 0
0x18002c0a8  jnz     short loc_18002C0A0
0x18002c0aa  lea     r14, [rbx+1]
0x18002c0ae  mov     qword ptr [r13+rbp*8+0], 0
0x18002c0b7  cmp     r14, rbx
0x18002c0ba  jb      loc_18002C1A1
0x18002c0c0  mov     eax, 2
0x18002c0c5  mov     [rsp+298h+var_268], 0
0x18002c0ce  mul     r14
0x18002c0d1  test    rdx, rdx
0x18002c0d4  jz      loc_18002C1CF
0x18002c0da  xor     r10d, r10d
0x18002c0dd  mov     esi, 80070216h
0x18002c0e2  mov     eax, esi
0x18002c0e4  test    esi, esi
0x18002c0e6  js      loc_18002C241
0x18002c0ec  test    r10, r10
0x18002c0ef  jz      loc_18002C259
0x18002c0f5  cmp     r14, 7FFFFFFFh
0x18002c0fc  ja      loc_18002C262
0x18002c102  cmp     rbx, 7FFFFFFFh
0x18002c109  jnb     loc_18002C26A
0x18002c10f  test    r14, r14
0x18002c112  jz      loc_18002C275
0x18002c118  mov     rdx, r14
0x18002c11b  mov     r8, r10
0x18002c11e  xor     ecx, ecx
0x18002c120  test    rbx, rbx
0x18002c123  jz      short loc_18002C145
0x18002c125  movzx   eax, word ptr [rdi]
0x18002c128  test    ax, ax
0x18002c12b  jz      short loc_18002C145
0x18002c12d  mov     [r8], ax
0x18002c131  add     rdi, 2
0x18002c135  add     r8, 2
0x18002c139  dec     rbx
0x18002c13c  inc     rcx
0x18002c13f  sub     rdx, 1
0x18002c143  jnz     short loc_18002C120
0x18002c145  test    rdx, rdx
0x18002c148  lea     r9, [rcx-1]
0x18002c14c  cmovnz  r9, rcx
0x18002c150  lea     rcx, [r8-2]
0x18002c154  cmovnz  rcx, r8
0x18002c158  xor     eax, eax
0x18002c15a  mov     [rcx], ax
0x18002c15d  test    rdx, rdx
0x18002c160  jz      loc_18002C275
0x18002c166  sub     r14, r9
0x18002c169  cmp     r14, 1
0x18002c16d  jbe     loc_18002C275
0x18002c173  lea     r8, [r14+r14]
0x18002c177  cmp     r8, 2
0x18002c17b  jbe     loc_18002C275
0x18002c181  inc     r9
0x18002c184  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18002c188  xor     edx, edx; Val
0x18002c18a  lea     rcx, [r10+r9*2]; void *
0x18002c18e  call    memset_0
0x18002c193  mov     ebx, dword ptr [rsp+298h+var_278]
0x18002c197  inc     ebp
0x18002c199  mov     rdi, r15
0x18002c19c  jmp     loc_18002C044
0x18002c1a1  mov     esi, 80070216h
0x18002c1a6  xor     ebx, ebx
0x18002c1a8  mov     edi, ebp
0x18002c1aa  test    ebp, ebp
0x18002c1ac  jz      short loc_18002C1C1
0x18002c1ae  mov     rcx, [r13+rbx*8+0]; pv
0x18002c1b3  call    cs:__imp_CoTaskMemFree
0x18002c1b9  inc     rbx
0x18002c1bc  cmp     rbx, rdi
0x18002c1bf  jb      short loc_18002C1AE
0x18002c1c1  mov     rcx, r13; pv
0x18002c1c4  call    cs:__imp_CoTaskMemFree
0x18002c1ca  jmp     loc_18002BF45
0x18002c1cf  mov     rcx, rax; cb
0x18002c1d2  call    cs:__imp_CoTaskMemAlloc
0x18002c1d8  xor     esi, esi
0x18002c1da  mov     [r13+rbp*8+0], rax
0x18002c1df  test    rax, rax
0x18002c1e2  mov     r10, rax
0x18002c1e5  mov     eax, 8007000Eh
0x18002c1ea  cmovz   esi, eax
0x18002c1ed  jmp     loc_18002C0E2
0x18002c1f2  lea     r9, [rsp+298h+var_278]
0x18002c1f7  mov     r8, rbx
0x18002c1fa  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEBGPEAPEAG@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,ushort const *,ushort * *)
0x18002c1ff  mov     r12, [rsp+298h+var_278]
0x18002c204  mov     esi, eax
0x18002c206  jmp     loc_18002BF21
0x18002c20b  test    esi, esi
0x18002c20d  js      short loc_18002C1A6
0x18002c20f  test    ebp, ebp
0x18002c211  jz      short loc_18002C1A6
0x18002c213  mov     rax, [rsp+298h+var_270]
0x18002c218  mov     word ptr [rax], 101Fh
0x18002c21d  mov     [rax+8], ebp
0x18002c220  mov     [rax+10h], r13
0x18002c224  jmp     loc_18002BF45
0x18002c229  mov     esi, 8007000Eh
0x18002c22e  jmp     loc_18002C037
0x18002c233  xor     ecx, ecx
0x18002c235  mov     [rax], cx
0x18002c238  add     r15, 2
0x18002c23c  jmp     loc_18002C06F
0x18002c241  test    eax, eax
0x18002c243  jns     short loc_18002C275
0x18002c245  mov     ebx, dword ptr [rsp+298h+var_278]
0x18002c249  mov     rdi, r15
0x18002c24c  test    esi, esi
0x18002c24e  jns     loc_18002C044
0x18002c254  jmp     loc_18002C1A6
0x18002c259  test    r14, r14
0x18002c25c  jz      loc_18002C0F5
0x18002c262  xor     eax, eax
0x18002c264  mov     [r10], ax
0x18002c268  jmp     short loc_18002C275
0x18002c26a  test    r14, r14
0x18002c26d  jz      short loc_18002C275
0x18002c26f  xor     eax, eax
0x18002c271  mov     [r10], ax
0x18002c275  mov     ebx, dword ptr [rsp+298h+var_278]
0x18002c279  inc     ebp
0x18002c27b  mov     rdi, r15
0x18002c27e  jmp     loc_18002C044
```
