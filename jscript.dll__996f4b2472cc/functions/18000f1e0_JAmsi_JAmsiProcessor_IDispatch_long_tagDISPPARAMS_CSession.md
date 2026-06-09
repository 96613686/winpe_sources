# JAmsi::JAmsiProcessor(IDispatch *,long,tagDISPPARAMS *,CSession *)

- ea: `0x18000f1e0`
- end: `0x18000fa26`
- name: `?JAmsiProcessor@JAmsi@@QEAAJPEAUIDispatch@@JPEAUtagDISPPARAMS@@PEAVCSession@@@Z`
- size: `2118`
- prototype: `__int64 __fastcall(JAmsi *this, struct IDispatch *, unsigned int, struct tagDISPPARAMS *, struct CSession *)`
- caller_count: `4`
- callee_count: `14`
- tags: `file_ops, installer_update`

## callers

- `0x18000cbcc`
- `0x18000da30`
- `0x18000e778`
- `0x18000fd70`

## callees

- `0x18000f1e0`
- `0x18000fa30`
- `0x18000fb08`
- `0x1800405c8`
- `0x180042c20`
- `0x180043d14`
- `0x1800476f4`
- `0x1800585c4`
- `0x1800585d0`
- `0x180058610`
- `0x18005861c`
- `0x1800966aa`
- `0x1800966e0`
- `0x180098010`

## import_xrefs

- `msvcrt!wcsncpy_s` at `0x18000f4c8`
- `msvcrt!wcsncpy_s` at `0x18000f4c8`
- `msvcrt!wcsncat_s` at `0x18000f406`
- `msvcrt!wcsncat_s` at `0x18000f406`
- `msvcrt!wcscat_s` at `0x18000f433`
- `msvcrt!wcscat_s` at `0x18000f846`
- `msvcrt!wcscat_s` at `0x18000f433`
- `msvcrt!wcscat_s` at `0x18000f846`
- `msvcrt!wcscpy_s` at `0x18000f95a`
- `msvcrt!wcscpy_s` at `0x18000f95a`
- `msvcrt!_snwprintf_s` at `0x18000f3a1`
- `msvcrt!_snwprintf_s` at `0x18000f3a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f8af`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f8d4`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f8af`
- `OLEAUT32!__imp_SysFreeString` at `0x18000f8d4`

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
0x18000f1e0  push    rbx
0x18000f1e2  push    rbp
0x18000f1e3  push    rsi
0x18000f1e4  push    rdi
0x18000f1e5  push    r12
0x18000f1e7  push    r13
0x18000f1e9  push    r14
0x18000f1eb  push    r15
0x18000f1ed  sub     rsp, 0B8h
0x18000f1f4  mov     rax, cs:__security_cookie
0x18000f1fb  xor     rax, rsp
0x18000f1fe  mov     [rsp+0F8h+var_50], rax
0x18000f206  mov     rax, [rsp+0F8h+arg_20]
0x18000f20e  xor     r11d, r11d
0x18000f211  cmp     dword ptr [rcx+4], 1
0x18000f215  mov     r12d, r8d
0x18000f218  mov     [rsp+0F8h+var_A8], r9
0x18000f21d  mov     r10, rdx
0x18000f220  mov     r8, rcx
0x18000f223  mov     [rsp+0F8h+var_A0], rcx
0x18000f228  mov     [rsp+0F8h+var_70], rax
0x18000f230  mov     [rsp+0F8h+var_90], r11
0x18000f235  mov     [rsp+0F8h+var_78], r11
0x18000f23d  mov     [rsp+0F8h+bstrString], r11
0x18000f242  jnz     loc_18000FA1F
0x18000f248  test    rdx, rdx
0x18000f24b  jz      loc_18000FA1F
0x18000f251  test    r9, r9
0x18000f254  jz      loc_18000FA1F
0x18000f25a  test    rax, rax
0x18000f25d  jz      loc_18000FA1F
0x18000f263  mov     rax, [rcx+18h]
0x18000f267  mov     ebp, r12d
0x18000f26a  xor     ebp, [rdx]
0x18000f26c  mov     r15d, r11d
0x18000f26f  mov     [rsp+0F8h+var_B8], r11d
0x18000f274  mov     esi, r11d
0x18000f277  mov     [rsp+0F8h+Block], r11
0x18000f27c  mov     ebx, r11d
0x18000f27f  mov     rcx, [rax]
0x18000f282  test    rcx, rcx
0x18000f285  jz      loc_18000F5BE
0x18000f28b  cmp     ebp, [rcx+18h]
0x18000f28e  jz      short loc_18000F2A1
0x18000f290  jbe     short loc_18000F29B
0x18000f292  add     rcx, 10h
0x18000f296  mov     rcx, [rcx]
0x18000f299  jmp     short loc_18000F282
0x18000f29b  add     rcx, 8
0x18000f29f  jmp     short loc_18000F296
0x18000f2a1  mov     r14, [rcx+20h]
0x18000f2a5  test    r14, r14
0x18000f2a8  jz      loc_18000F5C1
0x18000f2ae  mov     rbx, [r14]
0x18000f2b1  mov     rsi, [r14+8]
0x18000f2b5  test    rbx, rbx
0x18000f2b8  jz      loc_18000F5C1
0x18000f2be  test    rsi, rsi
0x18000f2c1  jz      loc_18000F5C1
0x18000f2c7  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f2ce  mov     rax, rdi
0x18000f2d1  cmp     [rbx+rax*2+2], r15w
0x18000f2d7  lea     rax, [rax+1]
0x18000f2db  jnz     short loc_18000F2D1
0x18000f2dd  lea     edx, [rax+rax]
0x18000f2e0  mov     rax, rdi
0x18000f2e3  mov     [rsp+0F8h+var_98], edx
0x18000f2e7  nop     word ptr [rax+rax+00000000h]
0x18000f2f0  cmp     [rsi+rax*2+2], r15w
0x18000f2f6  lea     rax, [rax+1]
0x18000f2fa  jnz     short loc_18000F2F0
0x18000f2fc  mov     r14d, [r8+10h]
0x18000f300  lea     r13d, [rax+rax]
0x18000f304  cmp     [r9+10h], r14d
0x18000f308  lea     ecx, [rdx+r13]
0x18000f30c  mov     rax, [r8+8]
0x18000f310  cmovbe  r14d, [r9+10h]
0x18000f315  add     rcx, 0Ch
0x18000f319  mov     [rsp+0F8h+var_88], r13d
0x18000f31e  mov     r12d, [rax+4]
0x18000f322  cmp     rcx, r12
0x18000f325  jnb     loc_18000F5B3
0x18000f32b  sub     r12d, r13d
0x18000f32e  sub     r12d, edx
0x18000f331  sub     r12d, 0Ch
0x18000f335  test    r14d, r14d
0x18000f338  jnz     loc_18000F6E5
0x18000f33e  mov     [rsp+0F8h+var_A8], r11
0x18000f343  mov     r10d, r11d
0x18000f346  mov     [rsp+0F8h+Block], r11
0x18000f34b  add     edx, 10h
0x18000f34e  lea     ebp, ds:0[r14*4]
0x18000f356  add     ebp, r13d
0x18000f359  mov     eax, 2
0x18000f35e  add     ebp, edx
0x18000f360  add     ebp, r10d
0x18000f363  shr     rbp, 1
0x18000f366  mul     rbp
0x18000f369  cmovb   rax, rdi
0x18000f36d  mov     rcx, rax; unsigned __int64
0x18000f370  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f375  mov     r15, rax
0x18000f378  test    rax, rax
0x18000f37b  jz      loc_18000F4F9
0x18000f381  xor     eax, eax
0x18000f383  mov     [rsp+0F8h+var_D0], rsi
0x18000f388  lea     r9, aSS_0; "%s.%s("
0x18000f38f  mov     [r15], ax
0x18000f393  mov     r8, rdi; MaxCount
0x18000f396  mov     [rsp+0F8h+var_D8], rbx
0x18000f39b  mov     rdx, rbp; BufferCount
0x18000f39e  mov     rcx, r15; Buffer
0x18000f3a1  call    cs:__imp__snwprintf_s
0x18000f3a8  nop     dword ptr [rax+rax+00h]
0x18000f3ad  cmp     eax, 0FFFFFFFFh
0x18000f3b0  jz      loc_18000F4F9
0x18000f3b6  mov     r13, [rsp+0F8h+var_A8]
0x18000f3bb  lea     ebx, [r14-1]
0x18000f3bf  test    ebx, ebx
0x18000f3c1  js      short loc_18000F426
0x18000f3c3  movsxd  rax, ebx
0x18000f3c6  mov     r10, rdi
0x18000f3c9  mov     r8, [r13+rax*8+0]; Source
0x18000f3ce  xchg    ax, ax
0x18000f3d0  inc     r10
0x18000f3d3  cmp     word ptr [r8+r10*2], 0
0x18000f3d9  jnz     short loc_18000F3D0
0x18000f3db  xor     edx, edx
0x18000f3dd  add     r10d, r10d
0x18000f3e0  mov     eax, r12d
0x18000f3e3  mov     ecx, r10d
0x18000f3e6  div     r14d
0x18000f3e9  add     rcx, 4
0x18000f3ed  mov     rdx, rbp; SizeInWords
0x18000f3f0  mov     r9d, eax
0x18000f3f3  add     eax, 0FFFFFFFCh
0x18000f3f6  cmp     rcx, r9
0x18000f3f9  mov     rcx, r15; Destination
0x18000f3fc  cmovbe  eax, r10d
0x18000f400  mov     r9d, eax
0x18000f403  shr     r9, 1; MaxCount
0x18000f406  call    cs:__imp_wcsncat_s
0x18000f40d  nop     dword ptr [rax+rax+00h]
0x18000f412  test    eax, eax
0x18000f414  jnz     loc_18000F4F9
0x18000f41a  test    ebx, ebx
0x18000f41c  jg      loc_18000F839
0x18000f422  dec     ebx
0x18000f424  jmp     short loc_18000F3BF
0x18000f426  lea     r8, asc_1800A2128; ");\r\n"
0x18000f42d  mov     rdx, rbp; SizeInWords
0x18000f430  mov     rcx, r15; Destination
0x18000f433  call    cs:__imp_wcscat_s
0x18000f43a  nop     dword ptr [rax+rax+00h]
0x18000f43f  test    eax, eax
0x18000f441  jnz     loc_18000F4F9
0x18000f447  nop     word ptr [rax+rax+00000000h]
0x18000f450  inc     rdi
0x18000f453  cmp     word ptr [r15+rdi*2], 0
0x18000f459  jnz     short loc_18000F450
0x18000f45b  mov     r13, [rsp+0F8h+var_A0]
0x18000f460  add     edi, edi
0x18000f462  jz      loc_18000F4E9
0x18000f468  mov     rbx, [r13+8]
0x18000f46c  mov     ebp, [rbx+4]
0x18000f46f  cmp     edi, ebp
0x18000f471  mov     ecx, [rbx+10h]
0x18000f474  mov     eax, [rbx]
0x18000f476  cmovbe  ebp, edi
0x18000f479  sub     eax, ecx
0x18000f47b  lea     r8d, [rbp+4]
0x18000f47f  cmp     eax, r8d
0x18000f482  jbe     loc_18000F7D5
0x18000f488  mov     edx, [rbx+14h]
0x18000f48b  cmp     ecx, edx
0x18000f48d  jnb     short loc_18000F49C
0x18000f48f  mov     eax, edx
0x18000f491  sub     eax, ecx
0x18000f493  cmp     eax, r8d
0x18000f496  jbe     loc_18000F9F8
0x18000f49c  mov     ecx, [rbx+10h]
0x18000f49f  mov     rax, [rbx+8]
0x18000f4a3  mov     edx, r8d
0x18000f4a6  mov     r8, r15; Source
0x18000f4a9  sub     rdx, 2
0x18000f4ad  mov     r9d, ebp
0x18000f4b0  shr     r9, 1; MaxCount
0x18000f4b3  mov     [rcx+rax], bp
0x18000f4b7  mov     rax, [rbx+8]
0x18000f4bb  mov     ecx, [rbx+10h]
0x18000f4be  add     rax, 2
0x18000f4c2  add     rcx, rax; Destination
0x18000f4c5  shr     rdx, 1; SizeInWords
0x18000f4c8  call    cs:__imp_wcsncpy_s
0x18000f4cf  nop     dword ptr [rax+rax+00h]
0x18000f4d4  lea     eax, [rbp+2]
0x18000f4d7  add     [rbx+10h], eax
0x18000f4da  mov     r8d, [rbx+10h]
0x18000f4de  mov     rax, [rbx+8]
0x18000f4e2  mov     word ptr [r8+rax], 0FFFFh
0x18000f4e9  mov     rdx, rsi; unsigned __int16 *
0x18000f4ec  call    ?JAmsiIsScannerNeeded@JAmsi@@QEAA_NQEAG@Z; JAmsi::JAmsiIsScannerNeeded(ushort * const)
0x18000f4f1  test    al, al
0x18000f4f3  jnz     loc_18000FA03
0x18000f4f9  mov     r9, [rsp+0F8h+Block]
0x18000f4fe  mov     edi, [rsp+0F8h+var_B8]
0x18000f502  mov     rcx, [rsp+0F8h+var_90]
0x18000f507  test    rcx, rcx
0x18000f50a  jz      short loc_18000F51D
0x18000f50c  mov     rax, [rcx]
0x18000f50f  mov     rax, [rax+10h]
0x18000f513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f518  mov     r9, [rsp+0F8h+Block]
0x18000f51d  test    r9, r9
0x18000f520  jnz     loc_18000F86C
0x18000f526  test    r15, r15
0x18000f529  jz      short loc_18000F533
0x18000f52b  mov     rcx, r15; Block
0x18000f52e  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000f533  mov     eax, edi
0x18000f535  mov     rcx, [rsp+0F8h+var_50]
0x18000f53d  xor     rcx, rsp; StackCookie
0x18000f540  call    __security_check_cookie
0x18000f545  add     rsp, 0B8h
0x18000f54c  pop     r15
0x18000f54e  pop     r14
0x18000f550  pop     r13
0x18000f552  pop     r12
0x18000f554  pop     rdi
0x18000f555  pop     rsi
0x18000f556  pop     rbp
0x18000f557  pop     rbx
0x18000f558  retn
0x18000f55a  mov     ecx, 10h; Size
0x18000f55f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f564  mov     r14, rax
0x18000f567  test    rax, rax
0x18000f56a  jz      loc_18000F6D3
0x18000f570  mov     [rax], rbx
0x18000f573  mov     [rax+8], rsi
0x18000f577  test    rbx, rbx
0x18000f57a  jz      short loc_18000F585
0x18000f57c  test    rsi, rsi
0x18000f57f  jnz     loc_18000F9DD
0x18000f585  mov     rcx, rbx; Block
0x18000f588  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f58d  mov     rcx, rsi; Block
0x18000f590  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f595  mov     rcx, [r14]; Block
0x18000f598  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f59d  mov     rcx, [r14+8]; Block
0x18000f5a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f5a6  mov     rcx, r14; Block
0x18000f5a9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f5ae  mov     r14d, [rsp+0F8h+var_98]
0x18000f5b3  mov     r9, r15
0x18000f5b6  mov     edi, r9d
0x18000f5b9  jmp     loc_18000F502
0x18000f5be  mov     r14, r11
0x18000f5c1  mov     rax, [rdx]
0x18000f5c4  lea     r9, [rsp+0F8h+var_90]
0x18000f5c9  xor     r8d, r8d
0x18000f5cc  xor     edx, edx
0x18000f5ce  mov     rcx, r10
0x18000f5d1  mov     rax, [rax+20h]
0x18000f5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5da  test    eax, eax
0x18000f5dc  js      loc_18000FA1F
0x18000f5e2  mov     rcx, [rsp+0F8h+var_90]
0x18000f5e7  test    rcx, rcx
0x18000f5ea  jz      loc_18000FA1F
0x18000f5f0  test    rbx, rbx
0x18000f5f3  jnz     loc_18000F97D
0x18000f5f9  mov     rax, [rcx]
0x18000f5fc  lea     r8, [rsp+0F8h+bstrString]
0x18000f601  mov     rdi, 0FFFFFFFFFFFFFFFFh
0x18000f608  mov     [rsp+0F8h+var_D0], r15
0x18000f60d  xor     r9d, r9d
0x18000f610  mov     [rsp+0F8h+var_D8], r15
0x18000f615  mov     edx, edi
0x18000f617  mov     rax, [rax+60h]
0x18000f61b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f620  mov     rdx, [rsp+0F8h+bstrString]; unsigned __int16 *
0x18000f625  test    rdx, rdx
0x18000f628  jnz     loc_18000F89A
0x18000f62e  test    eax, eax
0x18000f630  js      loc_18000F991
0x18000f636  test    rbx, rbx
0x18000f639  jz      loc_18000F99E
0x18000f63f  mov     rax, rdi
0x18000f642  inc     rax
0x18000f645  cmp     [rbx+rax*2], r15w
0x18000f64a  jnz     short loc_18000F642
0x18000f64c  test    rax, rax
0x18000f64f  jz      loc_18000F991
0x18000f655  test    rsi, rsi
0x18000f658  jnz     loc_18000F9B2
0x18000f65e  mov     rcx, [rsp+0F8h+var_90]
0x18000f663  lea     r8, [rsp+0F8h+var_78]
0x18000f66b  mov     [rsp+0F8h+var_D0], r15
  ... truncated ...
```
