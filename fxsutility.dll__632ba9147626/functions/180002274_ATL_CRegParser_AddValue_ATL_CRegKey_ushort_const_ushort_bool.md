# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x180002274`
- end: `0x18000288a`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1558`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800039f4`

## callees

- `0x180002274`
- `0x180003040`
- `0x180004808`
- `0x180015cbe`
- `0x180015cf0`
- `0x180015db0`

## import_xrefs

- `msvcrt!malloc` at `0x1800022b6`
- `msvcrt!malloc` at `0x180002326`
- `msvcrt!malloc` at `0x180002486`
- `msvcrt!malloc` at `0x18000260b`
- `msvcrt!malloc` at `0x1800022b6`
- `msvcrt!malloc` at `0x180002326`
- `msvcrt!malloc` at `0x180002486`
- `msvcrt!malloc` at `0x18000260b`
- `msvcrt!free` at `0x180002380`
- `msvcrt!free` at `0x180002409`
- `msvcrt!free` at `0x1800024a6`
- `msvcrt!free` at `0x1800024b7`
- `msvcrt!free` at `0x1800025f9`
- `msvcrt!free` at `0x18000261f`
- `msvcrt!free` at `0x18000262d`
- `msvcrt!free` at `0x1800026c2`
- `msvcrt!free` at `0x180002840`
- `msvcrt!free` at `0x18000284f`
- `msvcrt!free` at `0x180002860`
- `msvcrt!free` at `0x180002380`
- `msvcrt!free` at `0x180002409`
- `msvcrt!free` at `0x1800024a6`
- `msvcrt!free` at `0x1800024b7`
- `msvcrt!free` at `0x1800025f9`
- `msvcrt!free` at `0x18000261f`
- `msvcrt!free` at `0x18000262d`
- `msvcrt!free` at `0x1800026c2`
- `msvcrt!free` at `0x180002840`
- `msvcrt!free` at `0x18000284f`
- `msvcrt!free` at `0x180002860`
- `msvcrt!wcscat_s` at `0x1800027ca`
- `msvcrt!wcscat_s` at `0x1800027d9`
- `msvcrt!wcscat_s` at `0x1800027ec`
- `msvcrt!wcscat_s` at `0x18000280c`
- `msvcrt!wcscat_s` at `0x1800027ca`
- `msvcrt!wcscat_s` at `0x1800027d9`
- `msvcrt!wcscat_s` at `0x1800027ec`
- `msvcrt!wcscat_s` at `0x18000280c`
- `KERNEL32!lstrcmpiW` at `0x1800022ff`
- `KERNEL32!lstrcmpiW` at `0x18000265f`
- `KERNEL32!lstrcmpiW` at `0x1800022ff`
- `KERNEL32!lstrcmpiW` at `0x18000265f`
- `KERNEL32!lstrcpynW` at `0x1800027b1`
- `KERNEL32!lstrcpynW` at `0x1800027b1`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800023b9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800023b9`
- `USER32!CharPrevW` at `0x18000278a`
- `USER32!CharPrevW` at `0x18000278a`
- `USER32!CharNextW` at `0x18000235e`
- `USER32!CharNextW` at `0x180002709`
- `USER32!CharNextW` at `0x180002716`
- `USER32!CharNextW` at `0x18000273a`
- `USER32!CharNextW` at `0x18000235e`
- `USER32!CharNextW` at `0x180002709`
- `USER32!CharNextW` at `0x180002716`
- `USER32!CharNextW` at `0x18000273a`
- `ADVAPI32!RegSetValueExW` at `0x1800023e6`
- `ADVAPI32!RegSetValueExW` at `0x1800026b0`
- `ADVAPI32!RegSetValueExW` at `0x1800023e6`
- `ADVAPI32!RegSetValueExW` at `0x1800026b0`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  const WCHAR *v6; // r15
  unsigned __int16 *v8; // rax
  WCHAR *v9; // r12
  int Token; // ebx
  int v12; // ebx
  unsigned __int16 *v13; // rdi
  __int16 v14; // si
  WCHAR *v15; // rbx
  HKEY v16; // rcx
  unsigned __int16 *v17; // rsi
  int v18; // esi
  WCHAR *v19; // rcx
  __int64 v20; // r14
  unsigned __int64 cbData; // r13
  __int64 v22; // rax
  void *v23; // rsp
  unsigned __int16 **lpData; // r15
  _QWORD *v25; // rax
  WCHAR *v26; // rcx
  unsigned int v27; // r9d
  unsigned int v28; // r8d
  char v29; // r8
  unsigned __int64 v30; // rdx
  char v31; // al
  __int64 v32; // rax
  const BYTE *v33; // rcx
  WCHAR *v34; // r13
  __int64 v35; // r14
  int v36; // esi
  const wchar_t *v37; // r12
  unsigned __int16 *v38; // r14
  const WCHAR *v39; // rsi
  const WCHAR *v40; // r15
  __int64 v41; // rax
  WCHAR *v42; // rcx
  unsigned __int16 *v43; // [rsp+30h] [rbp+0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp+8h] BYREF
  LPCWSTR v45; // [rsp+40h] [rbp+10h]
  ULONG pulOut; // [rsp+48h] [rbp+18h] BYREF
  HKEY *v47; // [rsp+50h] [rbp+20h]
  LPWSTR v48; // [rsp+58h] [rbp+28h]
  ATL::CRegParser *v49; // [rsp+60h] [rbp+30h]

  v49 = this;
  v43 = a4;
  v6 = a3;
  v45 = a3;
  v47 = a2;
  v8 = (unsigned __int16 *)malloc(0x2000u);
  *(_QWORD *)Data = v8;
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  Token = ATL::CRegParser::NextToken(this, v8);
  if ( Token < 0 )
    goto LABEL_76;
  v12 = 0;
  while ( lstrcmpiW(v9, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v12]) )
  {
    if ( (unsigned int)++v12 >= 3 )
    {
      Token = -2147352567;
      goto LABEL_76;
    }
  }
  v13 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v13 )
    goto LABEL_75;
  v14 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v12 + 4);
  while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
    *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  Token = ATL::CRegParser::NextToken(this, v13);
  if ( Token < 0 )
  {
    free(v13);
LABEL_76:
    free(v9);
    return (unsigned int)Token;
  }
  pulOut = 0;
  v15 = 0;
  if ( v14 == 8 )
  {
    v32 = -1;
    v33 = (const BYTE *)v13;
    v34 = 0;
    if ( a5 )
    {
      do
        ++v32;
      while ( v13[v32] );
      if ( (int)v32 > 4094 )
        goto LABEL_72;
      v34 = (WCHAR *)malloc(0x2000u);
      if ( !v34 )
      {
        free(v13);
LABEL_75:
        Token = -2147024882;
        goto LABEL_76;
      }
      v35 = *((_QWORD *)this + 1);
      v36 = 0;
      if ( *(int *)(v35 + 8) > 0 )
      {
        while ( lstrcmpiW(**(LPCWSTR **)(*(_QWORD *)v35 + 8LL * v36), L"Module") )
        {
          if ( ++v36 >= *(_DWORD *)(v35 + 8) )
            goto LABEL_80;
        }
        v37 = *(const wchar_t **)(*(_QWORD *)(*(_QWORD *)v35 + 8LL * v36) + 8LL);
        if ( v37 )
        {
          v38 = v13;
          if ( !*v37 )
          {
LABEL_100:
            v17 = v43;
            if ( v38 != v43 && *CharPrevW(v13, v38) == 34 )
            {
              v33 = (const BYTE *)v13;
            }
            else
            {
              *v34 = 0;
              lstrcpynW(v34, v13, v38 - v13);
              wcscat_s(v34, 0x1000u, L"\"");
              wcscat_s(v34, 0x1000u, v37);
              wcscat_s(v34, 0x1000u, L"\"");
              v41 = -1;
              do
                ++v41;
              while ( v37[v41] );
              wcscat_s(v34, 0x1000u, &v38[v41]);
              v33 = (const BYTE *)v34;
            }
            v9 = *(WCHAR **)Data;
            v32 = -1;
            v6 = v45;
            do
LABEL_82:
              ++v32;
            while ( *(_WORD *)&v33[2 * v32] );
            RegSetValueExW(*v47, v6, 0, 1u, v33, 2 * v32 + 2);
            if ( v34 )
              free(v34);
            goto LABEL_22;
          }
          if ( *v13 )
          {
LABEL_88:
            v39 = v38;
            v40 = v37;
            while ( *v40 )
            {
              if ( *v39 == *v40 )
              {
                v48 = CharNextW(v39);
                if ( (char *)v48 - (char *)v39 == (char *)CharNextW(v40) - (char *)v40 )
                {
                  do
                  {
                    if ( v39 >= v48 )
                      break;
                    ++v40;
                    ++v39;
                  }
                  while ( *v39 != *v40 );
                  if ( *v39 )
                    continue;
                }
              }
              if ( *v40 )
              {
                v38 = CharNextW(v38);
                if ( *v38 )
                  goto LABEL_88;
                goto LABEL_94;
              }
              break;
            }
            if ( !v38 )
              goto LABEL_94;
            goto LABEL_100;
          }
        }
LABEL_94:
        v9 = *(WCHAR **)Data;
LABEL_80:
        v6 = v45;
        v33 = (const BYTE *)v13;
        v32 = -1;
        goto LABEL_81;
      }
      v32 = -1;
      v33 = (const BYTE *)v13;
    }
LABEL_81:
    v17 = v43;
    goto LABEL_82;
  }
  if ( v14 != 17 )
  {
    if ( v14 == 19 )
    {
      VarUI4FromStr(v13, 0, 0, &pulOut);
      v16 = *a2;
      *(_DWORD *)Data = pulOut;
      RegSetValueExW(v16, v6, 0, 4u, Data, 4u);
    }
    goto LABEL_21;
  }
  v20 = -1;
  do
    ++v20;
  while ( v13[v20] );
  if ( (v20 & 1) != 0 )
  {
LABEL_72:
    free(v13);
    Token = -2147467259;
    goto LABEL_76;
  }
  cbData = (int)v20 / 2;
  if ( cbData <= 0x400
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(
         (ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v20 / 2),
         (unsigned int)((int)v20 >> 31)) )
  {
    v22 = cbData + 15;
    if ( cbData + 15 < cbData )
      v22 = 0xFFFFFFFFFFFFFF0LL;
    v23 = alloca(v22 & 0xFFFFFFFFFFFFFFF0uLL);
    lpData = &v43;
  }
  else if ( cbData + 16 >= cbData && (v25 = malloc(cbData + 16)) != 0 )
  {
    *v25 = 0;
    lpData = (unsigned __int16 **)(v25 + 2);
    v15 = (WCHAR *)v25;
  }
  else
  {
    lpData = 0;
  }
  if ( lpData )
  {
    memset_0(lpData, 0, cbData);
    v27 = 0;
    if ( (int)v20 <= 0 )
    {
LABEL_68:
      RegSetValueExW(*v47, v45, 0, 3u, (const BYTE *)lpData, cbData);
LABEL_21:
      v17 = v43;
LABEL_22:
      v18 = ATL::CRegParser::NextToken(v49, v17);
      if ( v18 >= 0 )
      {
        free(v13);
        v42 = v9;
        while ( 1 )
        {
          free(v42);
          if ( !v15 )
            break;
          v42 = v15;
          v15 = *(WCHAR **)v15;
        }
        return 0;
      }
      else
      {
        free(v13);
        v19 = v9;
        while ( 1 )
        {
          free(v19);
          if ( !v15 )
            break;
          v19 = v15;
          v15 = *(WCHAR **)v15;
        }
        return (unsigned int)v18;
      }
    }
    while ( 1 )
    {
      v28 = v13[v27];
      if ( v28 > 0x61 )
      {
        if ( v28 == 98 || v28 == 99 || v28 == 100 || v28 - 101 < 2 )
        {
LABEL_66:
          v29 = v28 - 87;
          goto LABEL_67;
        }
LABEL_65:
        v29 = 0;
        goto LABEL_67;
      }
      if ( v28 == 97 )
        goto LABEL_66;
      if ( v28 <= 0x38 )
        break;
      if ( v28 == 57 )
        goto LABEL_53;
      if ( v28 != 65 && v28 != 66 && v28 != 67 && v28 != 68 && v28 - 69 > 1 )
        goto LABEL_65;
      v29 = v28 - 55;
LABEL_67:
      v30 = (unsigned __int64)v27 >> 1;
      v31 = 4 * (v27++ & 1);
      *((_BYTE *)lpData + v30) |= v29 << (4 - v31);
      if ( (int)v27 >= (int)v20 )
        goto LABEL_68;
    }
    if ( v28 != 56 && v28 != 48 && v28 != 49 && v28 != 50 && v28 != 51 && v28 != 52 && v28 != 53 && v28 - 54 > 1 )
      goto LABEL_65;
LABEL_53:
    v29 = v28 - 48;
    goto LABEL_67;
  }
  free(v13);
  v26 = v9;
  while ( 1 )
  {
    free(v26);
    if ( !v15 )
      break;
    v26 = v15;
    v15 = *(WCHAR **)v15;
  }
  return 2147500037LL;
}

```

## disassembly

```asm
0x180002274  push    rbp
0x180002276  push    rbx
0x180002277  push    rsi
0x180002278  push    rdi
0x180002279  push    r12
0x18000227b  push    r13
0x18000227d  push    r14
0x18000227f  push    r15
0x180002281  sub     rsp, 78h
0x180002285  lea     rbp, [rsp+30h]
0x18000228a  mov     rax, cs:__security_cookie
0x180002291  xor     rax, rbp
0x180002294  mov     [rbp+80h+var_48], rax
0x180002298  mov     r14, rcx
0x18000229b  mov     [rbp+80h+var_50], rcx
0x18000229f  mov     ecx, 2000h; Size
0x1800022a4  mov     [rbp+80h+var_80], r9
0x1800022a8  mov     r15, r8
0x1800022ab  mov     [rbp+80h+var_70], r8
0x1800022af  mov     r13, rdx
0x1800022b2  mov     [rbp+80h+var_60], rdx
0x1800022b6  call    cs:__imp_malloc
0x1800022bc  xor     edi, edi
0x1800022be  mov     qword ptr [rbp+80h+Data], rax
0x1800022c2  mov     r12, rax
0x1800022c5  test    rax, rax
0x1800022c8  jnz     short loc_1800022D4
0x1800022ca  mov     eax, 8007000Eh
0x1800022cf  jmp     loc_18000286D
0x1800022d4  mov     rdx, r12; unsigned __int16 *
0x1800022d7  mov     rcx, r14; this
0x1800022da  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800022df  mov     ebx, eax
0x1800022e1  test    eax, eax
0x1800022e3  js      loc_18000262A
0x1800022e9  mov     ebx, edi
0x1800022eb  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800022f2  movsxd  rsi, ebx
0x1800022f5  mov     rcx, r12; lpString1
0x1800022f8  add     rsi, rsi
0x1800022fb  mov     rdx, [rax+rsi*8]; lpString2
0x1800022ff  call    cs:__imp_lstrcmpiW
0x180002305  test    eax, eax
0x180002307  jz      short loc_180002321
0x180002309  inc     ebx
0x18000230b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002312  cmp     ebx, 3
0x180002315  jb      short loc_1800022F2
0x180002317  mov     ebx, 80020009h
0x18000231c  jmp     loc_18000262A
0x180002321  mov     ecx, 2000h; Size
0x180002326  call    cs:__imp_malloc
0x18000232c  mov     rdi, rax
0x18000232f  test    rax, rax
0x180002332  jz      loc_180002625
0x180002338  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000233f  movzx   esi, word ptr [rax+rsi*8+8]
0x180002344  mov     rcx, [r14]; lpsz
0x180002347  movzx   edx, word ptr [rcx]
0x18000234a  sub     edx, 9
0x18000234d  jz      short loc_18000235E
0x18000234f  sub     edx, 1
0x180002352  jz      short loc_18000235E
0x180002354  sub     edx, 3
0x180002357  jz      short loc_18000235E
0x180002359  cmp     edx, 13h
0x18000235c  jnz     short loc_180002369
0x18000235e  call    cs:__imp_CharNextW
0x180002364  mov     [r14], rax
0x180002367  jmp     short loc_180002344
0x180002369  mov     rdx, rdi; unsigned __int16 *
0x18000236c  mov     rcx, r14; this
0x18000236f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002374  xor     r8d, r8d; dwFlags
0x180002377  mov     ebx, eax
0x180002379  test    eax, eax
0x18000237b  jns     short loc_18000238B
0x18000237d  mov     rcx, rdi; Block
0x180002380  call    cs:__imp_free
0x180002386  jmp     loc_18000262A
0x18000238b  mov     eax, 8
0x180002390  mov     [rbp+80h+pulOut], r8d
0x180002394  mov     rbx, r8
0x180002397  cmp     si, ax
0x18000239a  jz      loc_1800025CE
0x1800023a0  cmp     si, 11h
0x1800023a4  jz      short loc_180002417
0x1800023a6  mov     eax, 13h
0x1800023ab  cmp     si, ax
0x1800023ae  jnz     short loc_1800023EC
0x1800023b0  lea     r9, [rbp+80h+pulOut]; pulOut
0x1800023b4  xor     edx, edx; lcid
0x1800023b6  mov     rcx, rdi; strIn
0x1800023b9  call    cs:__imp_VarUI4FromStr
0x1800023bf  mov     eax, [rbp+80h+pulOut]
0x1800023c2  mov     r9d, 4; dwType
0x1800023c8  mov     rcx, [r13+0]; hKey
0x1800023cc  mov     rdx, r15; lpValueName
0x1800023cf  mov     dword ptr [rbp+80h+Data], eax
0x1800023d2  lea     rax, [rbp+80h+Data]
0x1800023d6  mov     [rsp+0B0h+cbData], 4; cbData
0x1800023de  mov     [rsp+0B0h+lpData], rax; lpData
0x1800023e3  xor     r8d, r8d; Reserved
0x1800023e6  call    cs:__imp_RegSetValueExW
0x1800023ec  mov     rsi, [rbp+80h+var_80]
0x1800023f0  mov     rcx, [rbp+80h+var_50]; this
0x1800023f4  mov     rdx, rsi; unsigned __int16 *
0x1800023f7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800023fc  mov     esi, eax
0x1800023fe  mov     rcx, rdi; Block
0x180002401  test    eax, eax
0x180002403  jns     loc_18000284F
0x180002409  call    cs:__imp_free
0x18000240f  mov     rcx, r12
0x180002412  jmp     loc_180002840
0x180002417  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000241b  inc     r14
0x18000241e  cmp     [rdi+r14*2], r8w
0x180002423  jnz     short loc_18000241B
0x180002425  test    r14b, 1
0x180002429  jnz     loc_1800025F6
0x18000242f  mov     eax, r14d
0x180002432  cdq; unsigned __int64
0x180002433  sub     eax, edx
0x180002435  sar     eax, 1
0x180002437  movsxd  r13, eax
0x18000243a  cmp     r13, 400h
0x180002441  ja      short loc_180002478
0x180002443  mov     rcx, r13; this
0x180002446  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000244b  xor     r8d, r8d
0x18000244e  test    al, al
0x180002450  jz      short loc_180002478
0x180002452  lea     rax, [r13+0Fh]
0x180002456  cmp     rax, r13
0x180002459  ja      short loc_180002465
0x18000245b  mov     rax, 0FFFFFFFFFFFFFF0h
0x180002465  and     rax, 0FFFFFFFFFFFFFFF0h
0x180002469  call    _alloca_probe
0x18000246e  sub     rsp, rax
0x180002471  lea     r15, [rsp+0B0h+var_80]
0x180002476  jmp     short loc_18000249E
0x180002478  lea     rcx, [r13+10h]; Size
0x18000247c  cmp     rcx, r13
0x18000247f  jnb     short loc_180002486
0x180002481  mov     r15, r8
0x180002484  jmp     short loc_18000249E
0x180002486  call    cs:__imp_malloc
0x18000248c  xor     r8d, r8d
0x18000248f  test    rax, rax
0x180002492  jz      short loc_180002481
0x180002494  mov     [rax], r8
0x180002497  lea     r15, [rax+10h]
0x18000249b  mov     rbx, rax
0x18000249e  test    r15, r15
0x1800024a1  jnz     short loc_1800024CC
0x1800024a3  mov     rcx, rdi; Block
0x1800024a6  call    cs:__imp_free
0x1800024ac  mov     rcx, r12
0x1800024af  jmp     short loc_1800024B7
0x1800024b1  mov     rcx, rbx; Block
0x1800024b4  mov     rbx, [rbx]
0x1800024b7  call    cs:__imp_free
0x1800024bd  test    rbx, rbx
0x1800024c0  jnz     short loc_1800024B1
0x1800024c2  mov     eax, 80004005h
0x1800024c7  jmp     loc_18000286D
0x1800024cc  mov     r8, r13; Size
0x1800024cf  xor     edx, edx; Val
0x1800024d1  mov     rcx, r15; void *
0x1800024d4  call    memset_0
0x1800024d9  xor     eax, eax
0x1800024db  mov     r9d, eax
0x1800024de  test    r14d, r14d
0x1800024e1  jle     loc_1800025AE
0x1800024e7  mov     eax, r9d
0x1800024ea  movzx   r8d, word ptr [rdi+rax*2]
0x1800024ef  cmp     r8d, 61h ; 'a'
0x1800024f3  ja      short loc_180002560
0x1800024f5  jz      loc_180002581
0x1800024fb  cmp     r8d, 38h ; '8'
0x1800024ff  ja      short loc_180002534
0x180002501  jz      short loc_18000252E
0x180002503  mov     ecx, r8d
0x180002506  sub     ecx, 30h ; '0'
0x180002509  jz      short loc_18000252E
0x18000250b  sub     ecx, 1
0x18000250e  jz      short loc_18000252E
0x180002510  sub     ecx, 1
0x180002513  jz      short loc_18000252E
0x180002515  sub     ecx, 1
0x180002518  jz      short loc_18000252E
0x18000251a  sub     ecx, 1
0x18000251d  jz      short loc_18000252E
0x18000251f  sub     ecx, 1
0x180002522  jz      short loc_18000252E
0x180002524  sub     ecx, 1
0x180002527  jz      short loc_18000252E
0x180002529  cmp     ecx, 1
0x18000252c  jnz     short loc_18000257C
0x18000252e  sub     r8b, 30h ; '0'
0x180002532  jmp     short loc_180002585
0x180002534  mov     ecx, r8d
0x180002537  sub     ecx, 39h ; '9'
0x18000253a  jz      short loc_18000252E
0x18000253c  sub     ecx, 8
0x18000253f  jz      short loc_18000255A
0x180002541  sub     ecx, 1
0x180002544  jz      short loc_18000255A
0x180002546  sub     ecx, 1
0x180002549  jz      short loc_18000255A
0x18000254b  sub     ecx, 1
0x18000254e  jz      short loc_18000255A
0x180002550  sub     ecx, 1
0x180002553  jz      short loc_18000255A
0x180002555  cmp     ecx, 1
0x180002558  jnz     short loc_18000257C
0x18000255a  sub     r8b, 37h ; '7'
0x18000255e  jmp     short loc_180002585
0x180002560  mov     ecx, r8d
0x180002563  sub     ecx, 62h ; 'b'
0x180002566  jz      short loc_180002581
0x180002568  sub     ecx, 1
0x18000256b  jz      short loc_180002581
0x18000256d  sub     ecx, 1
0x180002570  jz      short loc_180002581
0x180002572  sub     ecx, 1
0x180002575  jz      short loc_180002581
0x180002577  cmp     ecx, 1
0x18000257a  jz      short loc_180002581
0x18000257c  xor     r8b, r8b
0x18000257f  jmp     short loc_180002585
0x180002581  sub     r8b, 57h ; 'W'
0x180002585  mov     eax, r9d
0x180002588  mov     edx, r9d
0x18000258b  and     eax, 1
0x18000258e  shr     rdx, 1
0x180002591  shl     eax, 2
0x180002594  mov     ecx, 4
0x180002599  sub     ecx, eax
0x18000259b  inc     r9d
0x18000259e  shl     r8b, cl
0x1800025a1  or      [rdx+r15], r8b
0x1800025a5  cmp     r9d, r14d
0x1800025a8  jl      loc_1800024E7
0x1800025ae  mov     rcx, [rbp+80h+var_60]
0x1800025b2  mov     r9d, 3
0x1800025b8  mov     rdx, [rbp+80h+var_70]
0x1800025bc  mov     [rsp+0B0h+cbData], r13d
0x1800025c1  mov     [rsp+0B0h+lpData], r15
0x1800025c6  mov     rcx, [rcx]
0x1800025c9  jmp     loc_1800023E3
0x1800025ce  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800025d2  mov     rcx, rdi
0x1800025d5  mov     r13, r8
0x1800025d8  cmp     [rbp+80h+arg_20], r8b
0x1800025df  jz      loc_18000267F
0x1800025e5  inc     rax
0x1800025e8  cmp     [rdi+rax*2], r8w
0x1800025ed  jnz     short loc_1800025E5
0x1800025ef  cmp     eax, 0FFEh
0x1800025f4  jle     short loc_180002606
0x1800025f6  mov     rcx, rdi; Block
0x1800025f9  call    cs:__imp_free
0x1800025ff  mov     ebx, 80004005h
0x180002604  jmp     short loc_18000262A
0x180002606  mov     ecx, 2000h; Size
0x18000260b  call    cs:__imp_malloc
0x180002611  xor     r8d, r8d
0x180002614  mov     r13, rax
0x180002617  test    rax, rax
0x18000261a  jnz     short loc_18000263A
0x18000261c  mov     rcx, rdi; Block
0x18000261f  call    cs:__imp_free
0x180002625  mov     ebx, 8007000Eh
0x18000262a  mov     rcx, r12; Block
0x18000262d  call    cs:__imp_free
0x180002633  mov     eax, ebx
0x180002635  jmp     loc_18000286D
0x18000263a  mov     r14, [r14+8]
0x18000263e  mov     esi, r8d
0x180002641  cmp     [r14+8], r8d
0x180002645  jle     loc_180002829
0x18000264b  mov     rax, [r14]
0x18000264e  lea     rdx, String2; "Module"
0x180002655  movsxd  r15, esi
0x180002658  mov     rcx, [rax+r15*8]
0x18000265c  mov     rcx, [rcx]; lpString1
0x18000265f  call    cs:__imp_lstrcmpiW
0x180002665  xor     r8d, r8d
0x180002668  test    eax, eax
0x18000266a  jz      short loc_1800026CD
0x18000266c  inc     esi
0x18000266e  cmp     esi, [r14+8]
0x180002672  jl      short loc_18000264B
0x180002674  mov     r15, [rbp+80h+var_70]
0x180002678  mov     rcx, rdi
0x18000267b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000267f  mov     rsi, [rbp+80h+var_80]
0x180002683  inc     rax
  ... truncated ...
```
