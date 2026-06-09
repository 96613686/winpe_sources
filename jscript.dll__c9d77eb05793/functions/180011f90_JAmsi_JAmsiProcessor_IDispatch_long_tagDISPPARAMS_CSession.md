# JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)

- ea: `0x180011f90`
- end: `0x1800127b1`
- name: `?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z`
- size: `2081`
- prototype: `__int64 __fastcall(JAmsi *this, struct IDispatch *, unsigned int, struct tagDISPPARAMS *, struct CSession *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x18000f91c`
- `0x1800107c0`
- `0x18001154c`
- `0x180012ae4`

## callees

- `0x180011f90`
- `0x1800127c0`
- `0x180012898`
- `0x18004045c`
- `0x1800416a8`
- `0x180042ad8`
- `0x1800468c0`
- `0x180057694`
- `0x1800576a0`
- `0x1800576e0`
- `0x1800576ec`
- `0x18009429a`
- `0x1800942d0`
- `0x180096010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x180012264`
- `msvcrt!wcsncpy_s` at `0x180012264`
- `msvcrt!wcsncat_s` at `0x1800121b6`
- `msvcrt!wcsncat_s` at `0x1800121b6`
- `msvcrt!wcscat_s` at `0x1800121dd`
- `msvcrt!wcscat_s` at `0x1800125e6`
- `msvcrt!wcscat_s` at `0x1800121dd`
- `msvcrt!wcscat_s` at `0x1800125e6`
- `msvcrt!wcscpy_s` at `0x1800126eb`
- `msvcrt!wcscpy_s` at `0x1800126eb`
- `msvcrt!_snwprintf_s` at `0x180012151`
- `msvcrt!_snwprintf_s` at `0x180012151`
- `OLEAUT32!__imp_SysFreeString` at `0x18001264c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001266b`
- `OLEAUT32!__imp_SysFreeString` at `0x18001264c`
- `OLEAUT32!__imp_SysFreeString` at `0x18001266b`

## pseudocode

```c
__int64 __fastcall JAmsi::JAmsiProcessor(
        JAmsi *this,
        struct IDispatch *a2,
        unsigned int a3,
        struct tagDISPPARAMS *a4,
        struct CSession *a5)
{
  bool v5; // zf
  JAmsi *v7; // r8
  unsigned int v8; // ebp
  wchar_t *v9; // r15
  unsigned __int16 *v10; // rsi
  unsigned __int16 *StringCopy; // rbx
  __int64 i; // rcx
  __int64 *v13; // rcx
  unsigned __int16 **v14; // r14
  __int64 v15; // rdi
  __int64 v16; // rax
  __int64 v17; // rdx
  __int64 v18; // rax
  unsigned __int64 cArgs; // r14
  int v20; // r13d
  __int64 v21; // rax
  unsigned __int64 v22; // r12
  unsigned int v23; // r12d
  int v24; // r10d
  unsigned __int64 v25; // rbp
  int j; // ebx
  __int64 v27; // r10
  const wchar_t *v28; // r8
  unsigned int v29; // r10d
  unsigned __int64 v30; // r9
  unsigned int v31; // eax
  JAmsi *v32; // rcx
  unsigned int v33; // edi
  __int64 v34; // rbx
  unsigned int v35; // ebp
  __int64 v36; // rcx
  unsigned int v37; // r8d
  unsigned int v38; // edx
  _QWORD *v39; // r9
  unsigned int v40; // edi
  void **v42; // rax
  __int64 v43; // rcx
  int v44; // eax
  JAmsi *v45; // rcx
  __int64 v46; // rax
  int v47; // eax
  JAmsi *v48; // rcx
  __int64 v49; // rax
  _QWORD *v50; // rax
  __int64 v51; // rbp
  unsigned __int64 v52; // rbp
  __int64 v53; // r9
  __int64 v54; // rax
  __int64 v55; // rcx
  int v56; // r8d
  int v57; // r9d
  unsigned __int64 v58; // rdx
  __int64 k; // rbx
  void *v60; // rcx
  __int64 v61; // r12
  wchar_t *v62; // rax
  unsigned int v63; // eax
  _QWORD *Block; // [rsp+48h] [rbp-B0h]
  struct tagDISPPARAMS *v65; // [rsp+50h] [rbp-A8h]
  _QWORD *v66; // [rsp+50h] [rbp-A8h]
  int v68; // [rsp+60h] [rbp-98h]
  int v69; // [rsp+60h] [rbp-98h]
  __int64 v70; // [rsp+68h] [rbp-90h] BYREF
  int v71; // [rsp+70h] [rbp-88h]
  BSTR bstrString; // [rsp+78h] [rbp-80h] BYREF
  BSTR v73; // [rsp+80h] [rbp-78h] BYREF
  struct CSession *v74; // [rsp+88h] [rbp-70h]
  wchar_t Source[12]; // [rsp+90h] [rbp-68h] BYREF

  v5 = *((_DWORD *)this + 1) == 1;
  v65 = a4;
  v7 = this;
  v74 = a5;
  v70 = 0;
  v73 = 0;
  bstrString = 0;
  if ( !v5 || !a2 || !a4 || !a5 )
    return 0;
  v8 = LODWORD(a2->lpVtbl) ^ a3;
  v9 = 0;
  v10 = 0;
  Block = 0;
  StringCopy = 0;
  for ( i = **((_QWORD **)this + 3); ; i = *v13 )
  {
    if ( !i )
    {
      v14 = 0;
      goto LABEL_59;
    }
    if ( v8 == *(_DWORD *)(i + 24) )
      break;
    if ( v8 <= *(_DWORD *)(i + 24) )
      v13 = (__int64 *)(i + 8);
    else
      v13 = (__int64 *)(i + 16);
  }
  v14 = *(unsigned __int16 ***)(i + 32);
  if ( !v14 || (StringCopy = *v14, v10 = v14[1], !*v14) || !v10 )
  {
LABEL_59:
    if ( ((int (__fastcall *)(struct IDispatch *, _QWORD, _QWORD, __int64 *))a2->lpVtbl->GetTypeInfo)(a2, 0, 0, &v70) < 0 )
      return 0;
    v43 = v70;
    if ( !v70 )
      return 0;
    if ( StringCopy )
    {
      operator delete(StringCopy);
      v43 = v70;
      StringCopy = 0;
    }
    v15 = -1;
    v44 = (*(__int64 (__fastcall **)(__int64, __int64, BSTR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v43 + 96LL))(
            v43,
            0xFFFFFFFFLL,
            &bstrString,
            0,
            0,
            0);
    if ( bstrString )
    {
      if ( v44 < 0 )
        goto LABEL_122;
      StringCopy = JAmsi::JAmsiGetStringCopy(v45, bstrString);
      SysFreeString(bstrString);
    }
    else if ( v44 < 0 )
    {
      goto LABEL_122;
    }
    if ( !StringCopy )
    {
LABEL_124:
      StringCopy = JAmsi::JAmsiGetStringCopy(v45, L"unkcls");
      goto LABEL_69;
    }
    v46 = -1;
    do
      ++v46;
    while ( StringCopy[v46] );
    if ( v46 )
    {
LABEL_69:
      if ( v10 )
      {
        operator delete(v10);
        v10 = 0;
      }
      v47 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)v70 + 96LL))(
              v70,
              a3,
              &v73,
              0,
              0,
              0);
      if ( v73 )
      {
        if ( v47 < 0 )
          goto LABEL_112;
        v10 = JAmsi::JAmsiGetStringCopy(v48, v73);
        SysFreeString(v73);
      }
      else if ( v47 < 0 )
      {
        goto LABEL_112;
      }
      if ( !v10 )
      {
LABEL_114:
        StringCchPrintfW(Source, 0xCu, L"_%08x", a3);
        v61 = -1;
        do
          ++v61;
        while ( Source[v61] );
        if ( (_DWORD)v61 )
        {
          v62 = (wchar_t *)operator new[](saturated_mul((unsigned int)(v61 + 1), 2u));
          v10 = v62;
          if ( v62 )
          {
            if ( wcscpy_s(v62, (unsigned int)(v61 + 1), Source) )
            {
              operator delete[](v10);
              v10 = 0;
            }
            else
            {
              v10[(unsigned int)v61] = 0;
            }
          }
          else
          {
            v10 = 0;
          }
        }
        else
        {
          v10 = 0;
        }
        goto LABEL_77;
      }
      v49 = -1;
      do
        ++v49;
      while ( v10[v49] );
      if ( v49 )
      {
LABEL_77:
        if ( v14 )
        {
          *v14 = StringCopy;
          v14[1] = v10;
        }
        else
        {
          v42 = (void **)operator new(0x10u);
          cArgs = (unsigned __int64)v42;
          if ( v42 )
          {
            *v42 = StringCopy;
            v42[1] = v10;
            if ( !StringCopy || !v10 )
            {
              operator delete(StringCopy);
              operator delete(v10);
              operator delete(*(void **)cArgs);
              operator delete(*(void **)(cArgs + 8));
              operator delete((void *)cArgs);
              LODWORD(cArgs) = v68;
              goto LABEL_57;
            }
            HashMap::Insert(*((HashMap **)this + 3), v8, v42);
            v7 = this;
LABEL_80:
            a4 = v65;
            goto LABEL_16;
          }
        }
        v7 = this;
        goto LABEL_80;
      }
LABEL_112:
      if ( v10 )
        operator delete(v10);
      goto LABEL_114;
    }
LABEL_122:
    if ( StringCopy )
      operator delete(StringCopy);
    goto LABEL_124;
  }
  v15 = -1;
LABEL_16:
  v16 = -1;
  do
    v5 = StringCopy[++v16] == 0;
  while ( !v5 );
  v17 = (unsigned int)(2 * v16);
  v18 = -1;
  v69 = v17;
  do
    v5 = v10[++v18] == 0;
  while ( !v5 );
  cArgs = *((unsigned int *)v7 + 4);
  v20 = 2 * v18;
  v21 = *((_QWORD *)v7 + 1);
  if ( a4->cArgs <= (unsigned int)cArgs )
    cArgs = a4->cArgs;
  v71 = v20;
  v22 = *(unsigned int *)(v21 + 4);
  if ( (unsigned __int64)(unsigned int)(v17 + v20) + 12 >= v22 )
    goto LABEL_57;
  v23 = v22 - v20 - v17 - 12;
  if ( !(_DWORD)cArgs )
  {
    v66 = 0;
    v24 = 0;
    Block = 0;
    goto LABEL_25;
  }
  if ( v23 < 2 * (unsigned __int64)(unsigned int)(12 * cArgs) )
  {
LABEL_57:
    v39 = 0;
    v40 = 0;
    goto LABEL_47;
  }
  v50 = operator new[](saturated_mul((unsigned int)cArgs, 8u));
  Block = v50;
  v39 = v50;
  if ( v50 )
  {
    memset_0(v50, 0, 8 * cArgs);
    v51 = 0;
    do
    {
      if ( !JAmsi::JAmsiVarParameterToString(
              (JAmsi *)(3 * v51),
              (const struct VAR *)&v65->rgvarg[v51],
              (unsigned __int16 **)&Block[v51]) )
      {
        v39 = Block;
        goto LABEL_102;
      }
      v51 = (unsigned int)(v51 + 1);
    }
    while ( (unsigned int)v51 < (unsigned int)cArgs );
    v66 = Block;
    v24 = 0;
    v52 = v23 / (unsigned int)cArgs;
    v53 = 0;
    do
    {
      v54 = -1;
      v55 = Block[v53];
      do
        v5 = *(_WORD *)(v55 + 2 * v54++ + 2) == 0;
      while ( !v5 );
      v56 = 2 * v54;
      if ( (unsigned __int64)(unsigned int)(2 * v54) + 4 > v52 )
      {
        v56 = v52 - 4;
        v58 = (unsigned __int64)(unsigned int)(v52 - 4) >> 1;
        *(_WORD *)(v55 + 2 * v58 - 4) = 34;
        *(_WORD *)(Block[v53] + 2 * v58 - 2) = 0;
      }
      v24 += v56;
      v53 = (unsigned int)(v53 + 1);
    }
    while ( (unsigned int)v53 < (unsigned int)cArgs );
    v20 = v71;
    LODWORD(v17) = v69;
LABEL_25:
    v25 = (unsigned __int64)(unsigned int)(v24 + v17 + 16 + v20 + 4 * cArgs) >> 1;
    v9 = (wchar_t *)operator new[](saturated_mul(v25, 2u));
    if ( !v9 )
      goto LABEL_46;
    *v9 = 0;
    if ( _snwprintf_s(v9, v25, 0xFFFFFFFFFFFFFFFFuLL, L"%s.%s(", StringCopy, v10) == -1 )
      goto LABEL_46;
    for ( j = cArgs - 1; j >= 0; --j )
    {
      v27 = -1;
      v28 = (const wchar_t *)v66[j];
      do
        ++v27;
      while ( v28[v27] );
      v29 = 2 * v27;
      v30 = v23 / (unsigned int)cArgs;
      v31 = v30 - 4;
      if ( (unsigned __int64)v29 + 4 <= v30 )
        v31 = v29;
      if ( wcsncat_s(v9, v25, v28, (unsigned __int64)v31 >> 1) || j > 0 && wcscat_s(v9, v25, L", ") )
        goto LABEL_46;
    }
    if ( wcscat_s(v9, v25, L");\r\n") )
      goto LABEL_46;
    do
      ++v15;
    while ( v9[v15] );
    v33 = 2 * v15;
    if ( v33 )
    {
      v34 = *((_QWORD *)this + 1);
      v35 = *(_DWORD *)(v34 + 4);
      v36 = *(unsigned int *)(v34 + 16);
      if ( v33 <= v35 )
        v35 = v33;
      v37 = v35 + 4;
      if ( *(_DWORD *)v34 - (int)v36 <= v35 + 4 )
      {
        v38 = 0;
        *(_WORD *)(v36 + *(_QWORD *)(v34 + 8)) = -2;
        LODWORD(v36) = 0;
        *(_DWORD *)(v34 + 16) = 0;
        goto LABEL_94;
      }
      v38 = *(_DWORD *)(v34 + 20);
      if ( (unsigned int)v36 < v38 && v38 - (unsigned int)v36 <= v37 )
      {
LABEL_94:
        while ( v38 <= v37 + (unsigned int)v36 )
        {
          v57 = *(unsigned __int16 *)(v38 + *(_QWORD *)(v34 + 8));
          if ( (_WORD)v57 == 0xFFFE )
          {
            v38 = 0;
            break;
          }
          v38 += v57 + 2;
        }
        *(_DWORD *)(v34 + 20) = v38;
      }
      *(_WORD *)(*(unsigned int *)(v34 + 16) + *(_QWORD *)(v34 + 8)) = v35;
      wcsncpy_s(
        (wchar_t *)(*(_QWORD *)(v34 + 8) + 2LL + *(unsigned int *)(v34 + 16)),
        ((unsigned __int64)v37 - 2) >> 1,
        v9,
        (unsigned __int64)v35 >> 1);
      *(_DWORD *)(v34 + 16) += v35 + 2;
      *(_WORD *)(*(unsigned int *)(v34 + 16) + *(_QWORD *)(v34 + 8)) = -1;
    }
    if ( JAmsi::JAmsiIsScannerNeeded(v32, v10) )
    {
      v63 = JAmsi::JAmsiRunScanner(this, v74);
      v39 = Block;
      v40 = v63;
    }
    else
    {
LABEL_46:
      v39 = Block;
      v40 = 0;
    }
  }
  else
  {
LABEL_102:
    v40 = 0;
  }
LABEL_47:
  if ( v70 )
  {
    (*(void (__fastcall **)(__int64, __int64, JAmsi *, _QWORD *))(*(_QWORD *)v70 + 16LL))(v70, v17, v7, v39);
    v39 = Block;
  }
  if ( v39 )
  {
    for ( k = 0; (unsigned int)k < (unsigned int)cArgs; k = (unsigned int)(k + 1) )
    {
      v60 = (void *)v39[k];
      if ( v60 )
      {
        operator delete(v60);
        v39 = Block;
      }
    }
    operator delete[](v39);
  }
  if ( v9 )
    operator delete[](v9);
  return v40;
}

```

## disassembly

```asm
0x180011f90  push    rbx
0x180011f92  push    rbp
0x180011f93  push    rsi
0x180011f94  push    rdi
0x180011f95  push    r12
0x180011f97  push    r13
0x180011f99  push    r14
0x180011f9b  push    r15
0x180011f9d  sub     rsp, 0B8h
0x180011fa4  mov     rax, cs:__security_cookie
0x180011fab  xor     rax, rsp
0x180011fae  mov     [rsp+0F8h+var_50], rax
0x180011fb6  mov     rax, [rsp+0F8h+arg_20]
0x180011fbe  xor     r11d, r11d
0x180011fc1  cmp     dword ptr [rcx+4], 1
0x180011fc5  mov     r12d, r8d
0x180011fc8  mov     [rsp+0F8h+var_A8], r9
0x180011fcd  mov     r10, rdx
0x180011fd0  mov     r8, rcx
0x180011fd3  mov     [rsp+0F8h+var_A0], rcx
0x180011fd8  mov     [rsp+0F8h+var_70], rax
0x180011fe0  mov     [rsp+0F8h+var_90], r11
0x180011fe5  mov     [rsp+0F8h+var_78], r11
0x180011fed  mov     [rsp+0F8h+bstrString], r11
0x180011ff2  jnz     loc_1800127AA
0x180011ff8  test    rdx, rdx
0x180011ffb  jz      loc_1800127AA
0x180012001  test    r9, r9
0x180012004  jz      loc_1800127AA
0x18001200a  test    rax, rax
0x18001200d  jz      loc_1800127AA
0x180012013  mov     rax, [rcx+18h]
0x180012017  mov     ebp, r12d
0x18001201a  xor     ebp, [rdx]
0x18001201c  mov     r15d, r11d
0x18001201f  mov     [rsp+0F8h+var_B8], r11d
0x180012024  mov     esi, r11d
0x180012027  mov     [rsp+0F8h+Block], r11
0x18001202c  mov     ebx, r11d
0x18001202f  mov     rcx, [rax]
0x180012032  test    rcx, rcx
0x180012035  jz      loc_180012353
0x18001203b  cmp     ebp, [rcx+18h]
0x18001203e  jz      short loc_180012051
0x180012040  jbe     short loc_18001204B
0x180012042  add     rcx, 10h
0x180012046  mov     rcx, [rcx]
0x180012049  jmp     short loc_180012032
0x18001204b  add     rcx, 8
0x18001204f  jmp     short loc_180012046
0x180012051  mov     r14, [rcx+20h]
0x180012055  test    r14, r14
0x180012058  jz      loc_180012356
0x18001205e  mov     rbx, [r14]
0x180012061  mov     rsi, [r14+8]
0x180012065  test    rbx, rbx
0x180012068  jz      loc_180012356
0x18001206e  test    rsi, rsi
0x180012071  jz      loc_180012356
0x180012077  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001207e  mov     rax, rdi
0x180012081  cmp     [rbx+rax*2+2], r15w
0x180012087  lea     rax, [rax+1]
0x18001208b  jnz     short loc_180012081
0x18001208d  lea     edx, [rax+rax]
0x180012090  mov     rax, rdi
0x180012093  mov     [rsp+0F8h+var_98], edx
0x180012097  nop     word ptr [rax+rax+00000000h]
0x1800120a0  cmp     [rsi+rax*2+2], r15w
0x1800120a6  lea     rax, [rax+1]
0x1800120aa  jnz     short loc_1800120A0
0x1800120ac  mov     r14d, [r8+10h]
0x1800120b0  lea     r13d, [rax+rax]
0x1800120b4  cmp     [r9+10h], r14d
0x1800120b8  lea     ecx, [rdx+r13]
0x1800120bc  mov     rax, [r8+8]
0x1800120c0  cmovbe  r14d, [r9+10h]
0x1800120c5  add     rcx, 0Ch
0x1800120c9  mov     [rsp+0F8h+var_88], r13d
0x1800120ce  mov     r12d, [rax+4]
0x1800120d2  cmp     rcx, r12
0x1800120d5  jnb     loc_180012348
0x1800120db  sub     r12d, r13d
0x1800120de  sub     r12d, edx
0x1800120e1  sub     r12d, 0Ch
0x1800120e5  test    r14d, r14d
0x1800120e8  jnz     loc_180012485
0x1800120ee  mov     [rsp+0F8h+var_A8], r11
0x1800120f3  mov     r10d, r11d
0x1800120f6  mov     [rsp+0F8h+Block], r11
0x1800120fb  add     edx, 10h
0x1800120fe  lea     ebp, ds:0[r14*4]
0x180012106  add     ebp, r13d
0x180012109  mov     eax, 2
0x18001210e  add     ebp, edx
0x180012110  add     ebp, r10d
0x180012113  shr     rbp, 1
0x180012116  mul     rbp
0x180012119  cmovb   rax, rdi
0x18001211d  mov     rcx, rax; unsigned __int64
0x180012120  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012125  mov     r15, rax
0x180012128  test    rax, rax
0x18001212b  jz      loc_18001228F
0x180012131  xor     eax, eax
0x180012133  mov     [rsp+0F8h+var_D0], rsi
0x180012138  lea     r9, aSS_0; "%s.%s("
0x18001213f  mov     [r15], ax
0x180012143  mov     r8, rdi; MaxCount
0x180012146  mov     [rsp+0F8h+var_D8], rbx
0x18001214b  mov     rdx, rbp; BufferCount
0x18001214e  mov     rcx, r15; Buffer
0x180012151  call    cs:__imp__snwprintf_s
0x180012157  cmp     eax, 0FFFFFFFFh
0x18001215a  jz      loc_18001228F
0x180012160  mov     r13, [rsp+0F8h+var_A8]
0x180012165  lea     ebx, [r14-1]
0x180012169  test    ebx, ebx
0x18001216b  js      short loc_1800121D0
0x18001216d  movsxd  rax, ebx
0x180012170  mov     r10, rdi
0x180012173  mov     r8, [r13+rax*8+0]; Source
0x180012178  nop     dword ptr [rax+rax+00000000h]
0x180012180  inc     r10
0x180012183  cmp     word ptr [r8+r10*2], 0
0x180012189  jnz     short loc_180012180
0x18001218b  xor     edx, edx
0x18001218d  add     r10d, r10d
0x180012190  mov     eax, r12d
0x180012193  mov     ecx, r10d
0x180012196  div     r14d
0x180012199  add     rcx, 4
0x18001219d  mov     rdx, rbp; SizeInWords
0x1800121a0  mov     r9d, eax
0x1800121a3  add     eax, 0FFFFFFFCh
0x1800121a6  cmp     rcx, r9
0x1800121a9  mov     rcx, r15; Destination
0x1800121ac  cmovbe  eax, r10d
0x1800121b0  mov     r9d, eax
0x1800121b3  shr     r9, 1; MaxCount
0x1800121b6  call    cs:__imp_wcsncat_s
0x1800121bc  test    eax, eax
0x1800121be  jnz     loc_18001228F
0x1800121c4  test    ebx, ebx
0x1800121c6  jg      loc_1800125D9
0x1800121cc  dec     ebx
0x1800121ce  jmp     short loc_180012169
0x1800121d0  lea     r8, asc_1800A01D8; ");\r\n"
0x1800121d7  mov     rdx, rbp; SizeInWords
0x1800121da  mov     rcx, r15; Destination
0x1800121dd  call    cs:__imp_wcscat_s
0x1800121e3  test    eax, eax
0x1800121e5  jnz     loc_18001228F
0x1800121eb  nop     dword ptr [rax+rax+00h]
0x1800121f0  inc     rdi
0x1800121f3  cmp     word ptr [r15+rdi*2], 0
0x1800121f9  jnz     short loc_1800121F0
0x1800121fb  mov     r13, [rsp+0F8h+var_A0]
0x180012200  add     edi, edi
0x180012202  jz      short loc_18001227F
0x180012204  mov     rbx, [r13+8]
0x180012208  mov     ebp, [rbx+4]
0x18001220b  cmp     edi, ebp
0x18001220d  mov     ecx, [rbx+10h]
0x180012210  mov     eax, [rbx]
0x180012212  cmovbe  ebp, edi
0x180012215  sub     eax, ecx
0x180012217  lea     r8d, [rbp+4]
0x18001221b  cmp     eax, r8d
0x18001221e  jbe     loc_180012575
0x180012224  mov     edx, [rbx+14h]
0x180012227  cmp     ecx, edx
0x180012229  jnb     short loc_180012238
0x18001222b  mov     eax, edx
0x18001222d  sub     eax, ecx
0x18001222f  cmp     eax, r8d
0x180012232  jbe     loc_180012783
0x180012238  mov     ecx, [rbx+10h]
0x18001223b  mov     rax, [rbx+8]
0x18001223f  mov     edx, r8d
0x180012242  mov     r8, r15; Source
0x180012245  sub     rdx, 2
0x180012249  mov     r9d, ebp
0x18001224c  shr     r9, 1; MaxCount
0x18001224f  mov     [rcx+rax], bp
0x180012253  mov     rax, [rbx+8]
0x180012257  mov     ecx, [rbx+10h]
0x18001225a  add     rax, 2
0x18001225e  add     rcx, rax; Destination
0x180012261  shr     rdx, 1; SizeInWords
0x180012264  call    cs:__imp_wcsncpy_s
0x18001226a  lea     eax, [rbp+2]
0x18001226d  add     [rbx+10h], eax
0x180012270  mov     r8d, [rbx+10h]
0x180012274  mov     rax, [rbx+8]
0x180012278  mov     word ptr [r8+rax], 0FFFFh
0x18001227f  mov     rdx, rsi; unsigned __int16 *
0x180012282  call    ?JAmsiIsScannerNeeded@JAmsi@@QEAA_NQEAG@Z; JAmsi::JAmsiIsScannerNeeded(ushort * const)
0x180012287  test    al, al
0x180012289  jnz     loc_18001278E
0x18001228f  mov     r9, [rsp+0F8h+Block]
0x180012294  mov     edi, [rsp+0F8h+var_B8]
0x180012298  mov     rcx, [rsp+0F8h+var_90]
0x18001229d  test    rcx, rcx
0x1800122a0  jz      short loc_1800122B3
0x1800122a2  mov     rax, [rcx]
0x1800122a5  mov     rax, [rax+10h]
0x1800122a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800122ae  mov     r9, [rsp+0F8h+Block]
0x1800122b3  test    r9, r9
0x1800122b6  jnz     loc_180012606
0x1800122bc  test    r15, r15
0x1800122bf  jz      short loc_1800122C9
0x1800122c1  mov     rcx, r15; Block
0x1800122c4  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800122c9  mov     eax, edi
0x1800122cb  mov     rcx, [rsp+0F8h+var_50]
0x1800122d3  xor     rcx, rsp; StackCookie
0x1800122d6  call    __security_check_cookie
0x1800122db  add     rsp, 0B8h
0x1800122e2  pop     r15
0x1800122e4  pop     r14
0x1800122e6  pop     r13
0x1800122e8  pop     r12
0x1800122ea  pop     rdi
0x1800122eb  pop     rsi
0x1800122ec  pop     rbp
0x1800122ed  pop     rbx
0x1800122ee  retn
0x1800122ef  mov     ecx, 10h; Size
0x1800122f4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800122f9  mov     r14, rax
0x1800122fc  test    rax, rax
0x1800122ff  jz      loc_180012473
0x180012305  mov     [rax], rbx
0x180012308  mov     [rax+8], rsi
0x18001230c  test    rbx, rbx
0x18001230f  jz      short loc_18001231A
0x180012311  test    rsi, rsi
0x180012314  jnz     loc_180012768
0x18001231a  mov     rcx, rbx; Block
0x18001231d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012322  mov     rcx, rsi; Block
0x180012325  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001232a  mov     rcx, [r14]; Block
0x18001232d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012332  mov     rcx, [r14+8]; Block
0x180012336  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001233b  mov     rcx, r14; Block
0x18001233e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180012343  mov     r14d, [rsp+0F8h+var_98]
0x180012348  mov     r9, r15
0x18001234b  mov     edi, r9d
0x18001234e  jmp     loc_180012298
0x180012353  mov     r14, r11
0x180012356  mov     rax, [rdx]
0x180012359  lea     r9, [rsp+0F8h+var_90]
0x18001235e  xor     r8d, r8d
0x180012361  xor     edx, edx
0x180012363  mov     rcx, r10
0x180012366  mov     rax, [rax+20h]
0x18001236a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001236f  test    eax, eax
0x180012371  js      loc_1800127AA
0x180012377  mov     rcx, [rsp+0F8h+var_90]
0x18001237c  test    rcx, rcx
0x18001237f  jz      loc_1800127AA
0x180012385  test    rbx, rbx
0x180012388  jnz     loc_180012708
0x18001238e  mov     rax, [rcx]
0x180012391  lea     r8, [rsp+0F8h+bstrString]
0x180012396  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18001239d  mov     [rsp+0F8h+var_D0], r15
0x1800123a2  xor     r9d, r9d
0x1800123a5  mov     [rsp+0F8h+var_D8], r15
0x1800123aa  mov     edx, edi
0x1800123ac  mov     rax, [rax+60h]
0x1800123b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800123b5  mov     rdx, [rsp+0F8h+bstrString]; unsigned __int16 *
0x1800123ba  test    rdx, rdx
0x1800123bd  jnz     loc_180012637
0x1800123c3  test    eax, eax
0x1800123c5  js      loc_18001271C
0x1800123cb  test    rbx, rbx
0x1800123ce  jz      loc_180012729
0x1800123d4  mov     rax, rdi
0x1800123d7  nop     word ptr [rax+rax+00000000h]
0x1800123e0  inc     rax
0x1800123e3  cmp     [rbx+rax*2], r15w
0x1800123e8  jnz     short loc_1800123E0
0x1800123ea  test    rax, rax
0x1800123ed  jz      loc_18001271C
0x1800123f3  test    rsi, rsi
0x1800123f6  jnz     loc_18001273D
0x1800123fc  mov     rcx, [rsp+0F8h+var_90]
0x180012401  lea     r8, [rsp+0F8h+var_78]
0x180012409  mov     [rsp+0F8h+var_D0], r15
0x18001240e  xor     r9d, r9d
0x180012411  mov     edx, r12d
0x180012414  mov     [rsp+0F8h+var_D8], r15
  ... truncated ...
```
