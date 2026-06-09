# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x18000e3f4`
- end: `0x18000ea0a`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1558`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180011038`

## callees

- `0x18000e3f4`
- `0x1800101d0`
- `0x1800124b0`
- `0x180012b02`
- `0x180012b40`
- `0x180012c00`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000e94a`
- `msvcrt!wcscat_s` at `0x18000e959`
- `msvcrt!wcscat_s` at `0x18000e96c`
- `msvcrt!wcscat_s` at `0x18000e98c`
- `msvcrt!wcscat_s` at `0x18000e94a`
- `msvcrt!wcscat_s` at `0x18000e959`
- `msvcrt!wcscat_s` at `0x18000e96c`
- `msvcrt!wcscat_s` at `0x18000e98c`
- `msvcrt!free` at `0x18000e500`
- `msvcrt!free` at `0x18000e589`
- `msvcrt!free` at `0x18000e626`
- `msvcrt!free` at `0x18000e637`
- `msvcrt!free` at `0x18000e779`
- `msvcrt!free` at `0x18000e79f`
- `msvcrt!free` at `0x18000e7ad`
- `msvcrt!free` at `0x18000e842`
- `msvcrt!free` at `0x18000e9c0`
- `msvcrt!free` at `0x18000e9cf`
- `msvcrt!free` at `0x18000e9e0`
- `msvcrt!free` at `0x18000e500`
- `msvcrt!free` at `0x18000e589`
- `msvcrt!free` at `0x18000e626`
- `msvcrt!free` at `0x18000e637`
- `msvcrt!free` at `0x18000e779`
- `msvcrt!free` at `0x18000e79f`
- `msvcrt!free` at `0x18000e7ad`
- `msvcrt!free` at `0x18000e842`
- `msvcrt!free` at `0x18000e9c0`
- `msvcrt!free` at `0x18000e9cf`
- `msvcrt!free` at `0x18000e9e0`
- `msvcrt!malloc` at `0x18000e436`
- `msvcrt!malloc` at `0x18000e4a6`
- `msvcrt!malloc` at `0x18000e606`
- `msvcrt!malloc` at `0x18000e78b`
- `msvcrt!malloc` at `0x18000e436`
- `msvcrt!malloc` at `0x18000e4a6`
- `msvcrt!malloc` at `0x18000e606`
- `msvcrt!malloc` at `0x18000e78b`
- `USER32!CharNextW` at `0x18000e4de`
- `USER32!CharNextW` at `0x18000e889`
- `USER32!CharNextW` at `0x18000e896`
- `USER32!CharNextW` at `0x18000e8ba`
- `USER32!CharNextW` at `0x18000e4de`
- `USER32!CharNextW` at `0x18000e889`
- `USER32!CharNextW` at `0x18000e896`
- `USER32!CharNextW` at `0x18000e8ba`
- `USER32!CharPrevW` at `0x18000e90a`
- `USER32!CharPrevW` at `0x18000e90a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000e539`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000e539`
- `KERNEL32!lstrcmpiW` at `0x18000e47f`
- `KERNEL32!lstrcmpiW` at `0x18000e7df`
- `KERNEL32!lstrcmpiW` at `0x18000e47f`
- `KERNEL32!lstrcmpiW` at `0x18000e7df`
- `KERNEL32!lstrcpynW` at `0x18000e931`
- `KERNEL32!lstrcpynW` at `0x18000e931`
- `ADVAPI32!RegSetValueExW` at `0x18000e566`
- `ADVAPI32!RegSetValueExW` at `0x18000e830`
- `ADVAPI32!RegSetValueExW` at `0x18000e566`
- `ADVAPI32!RegSetValueExW` at `0x18000e830`

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
0x18000e3f4  push    rbp
0x18000e3f6  push    rbx
0x18000e3f7  push    rsi
0x18000e3f8  push    rdi
0x18000e3f9  push    r12
0x18000e3fb  push    r13
0x18000e3fd  push    r14
0x18000e3ff  push    r15
0x18000e401  sub     rsp, 78h
0x18000e405  lea     rbp, [rsp+30h]
0x18000e40a  mov     rax, cs:__security_cookie
0x18000e411  xor     rax, rbp
0x18000e414  mov     [rbp+80h+var_48], rax
0x18000e418  mov     r14, rcx
0x18000e41b  mov     [rbp+80h+var_50], rcx
0x18000e41f  mov     ecx, 2000h; Size
0x18000e424  mov     [rbp+80h+var_80], r9
0x18000e428  mov     r15, r8
0x18000e42b  mov     [rbp+80h+var_70], r8
0x18000e42f  mov     r13, rdx
0x18000e432  mov     [rbp+80h+var_60], rdx
0x18000e436  call    cs:__imp_malloc
0x18000e43c  xor     edi, edi
0x18000e43e  mov     qword ptr [rbp+80h+Data], rax
0x18000e442  mov     r12, rax
0x18000e445  test    rax, rax
0x18000e448  jnz     short loc_18000E454
0x18000e44a  mov     eax, 8007000Eh
0x18000e44f  jmp     loc_18000E9ED
0x18000e454  mov     rdx, r12; unsigned __int16 *
0x18000e457  mov     rcx, r14; this
0x18000e45a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e45f  mov     ebx, eax
0x18000e461  test    eax, eax
0x18000e463  js      loc_18000E7AA
0x18000e469  mov     ebx, edi
0x18000e46b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000e472  movsxd  rsi, ebx
0x18000e475  mov     rcx, r12; lpString1
0x18000e478  add     rsi, rsi
0x18000e47b  mov     rdx, [rax+rsi*8]; lpString2
0x18000e47f  call    cs:__imp_lstrcmpiW
0x18000e485  test    eax, eax
0x18000e487  jz      short loc_18000E4A1
0x18000e489  inc     ebx
0x18000e48b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000e492  cmp     ebx, 3
0x18000e495  jb      short loc_18000E472
0x18000e497  mov     ebx, 80020009h
0x18000e49c  jmp     loc_18000E7AA
0x18000e4a1  mov     ecx, 2000h; Size
0x18000e4a6  call    cs:__imp_malloc
0x18000e4ac  mov     rdi, rax
0x18000e4af  test    rax, rax
0x18000e4b2  jz      loc_18000E7A5
0x18000e4b8  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000e4bf  movzx   esi, word ptr [rax+rsi*8+8]
0x18000e4c4  mov     rcx, [r14]; lpsz
0x18000e4c7  movzx   edx, word ptr [rcx]
0x18000e4ca  sub     edx, 9
0x18000e4cd  jz      short loc_18000E4DE
0x18000e4cf  sub     edx, 1
0x18000e4d2  jz      short loc_18000E4DE
0x18000e4d4  sub     edx, 3
0x18000e4d7  jz      short loc_18000E4DE
0x18000e4d9  cmp     edx, 13h
0x18000e4dc  jnz     short loc_18000E4E9
0x18000e4de  call    cs:__imp_CharNextW
0x18000e4e4  mov     [r14], rax
0x18000e4e7  jmp     short loc_18000E4C4
0x18000e4e9  mov     rdx, rdi; unsigned __int16 *
0x18000e4ec  mov     rcx, r14; this
0x18000e4ef  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e4f4  xor     r8d, r8d; dwFlags
0x18000e4f7  mov     ebx, eax
0x18000e4f9  test    eax, eax
0x18000e4fb  jns     short loc_18000E50B
0x18000e4fd  mov     rcx, rdi; Block
0x18000e500  call    cs:__imp_free
0x18000e506  jmp     loc_18000E7AA
0x18000e50b  mov     eax, 8
0x18000e510  mov     [rbp+80h+pulOut], r8d
0x18000e514  mov     rbx, r8
0x18000e517  cmp     si, ax
0x18000e51a  jz      loc_18000E74E
0x18000e520  cmp     si, 11h
0x18000e524  jz      short loc_18000E597
0x18000e526  mov     eax, 13h
0x18000e52b  cmp     si, ax
0x18000e52e  jnz     short loc_18000E56C
0x18000e530  lea     r9, [rbp+80h+pulOut]; pulOut
0x18000e534  xor     edx, edx; lcid
0x18000e536  mov     rcx, rdi; strIn
0x18000e539  call    cs:__imp_VarUI4FromStr
0x18000e53f  mov     eax, [rbp+80h+pulOut]
0x18000e542  mov     r9d, 4; dwType
0x18000e548  mov     rcx, [r13+0]; hKey
0x18000e54c  mov     rdx, r15; lpValueName
0x18000e54f  mov     dword ptr [rbp+80h+Data], eax
0x18000e552  lea     rax, [rbp+80h+Data]
0x18000e556  mov     [rsp+0B0h+cbData], 4; cbData
0x18000e55e  mov     [rsp+0B0h+lpData], rax; lpData
0x18000e563  xor     r8d, r8d; Reserved
0x18000e566  call    cs:__imp_RegSetValueExW
0x18000e56c  mov     rsi, [rbp+80h+var_80]
0x18000e570  mov     rcx, [rbp+80h+var_50]; this
0x18000e574  mov     rdx, rsi; unsigned __int16 *
0x18000e577  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e57c  mov     esi, eax
0x18000e57e  mov     rcx, rdi; Block
0x18000e581  test    eax, eax
0x18000e583  jns     loc_18000E9CF
0x18000e589  call    cs:__imp_free
0x18000e58f  mov     rcx, r12
0x18000e592  jmp     loc_18000E9C0
0x18000e597  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000e59b  inc     r14
0x18000e59e  cmp     [rdi+r14*2], r8w
0x18000e5a3  jnz     short loc_18000E59B
0x18000e5a5  test    r14b, 1
0x18000e5a9  jnz     loc_18000E776
0x18000e5af  mov     eax, r14d
0x18000e5b2  cdq; unsigned __int64
0x18000e5b3  sub     eax, edx
0x18000e5b5  sar     eax, 1
0x18000e5b7  movsxd  r13, eax
0x18000e5ba  cmp     r13, 400h
0x18000e5c1  ja      short loc_18000E5F8
0x18000e5c3  mov     rcx, r13; this
0x18000e5c6  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000e5cb  xor     r8d, r8d
0x18000e5ce  test    al, al
0x18000e5d0  jz      short loc_18000E5F8
0x18000e5d2  lea     rax, [r13+0Fh]
0x18000e5d6  cmp     rax, r13
0x18000e5d9  ja      short loc_18000E5E5
0x18000e5db  mov     rax, 0FFFFFFFFFFFFFF0h
0x18000e5e5  and     rax, 0FFFFFFFFFFFFFFF0h
0x18000e5e9  call    _alloca_probe
0x18000e5ee  sub     rsp, rax
0x18000e5f1  lea     r15, [rsp+0B0h+var_80]
0x18000e5f6  jmp     short loc_18000E61E
0x18000e5f8  lea     rcx, [r13+10h]; Size
0x18000e5fc  cmp     rcx, r13
0x18000e5ff  jnb     short loc_18000E606
0x18000e601  mov     r15, r8
0x18000e604  jmp     short loc_18000E61E
0x18000e606  call    cs:__imp_malloc
0x18000e60c  xor     r8d, r8d
0x18000e60f  test    rax, rax
0x18000e612  jz      short loc_18000E601
0x18000e614  mov     [rax], r8
0x18000e617  lea     r15, [rax+10h]
0x18000e61b  mov     rbx, rax
0x18000e61e  test    r15, r15
0x18000e621  jnz     short loc_18000E64C
0x18000e623  mov     rcx, rdi; Block
0x18000e626  call    cs:__imp_free
0x18000e62c  mov     rcx, r12
0x18000e62f  jmp     short loc_18000E637
0x18000e631  mov     rcx, rbx; Block
0x18000e634  mov     rbx, [rbx]
0x18000e637  call    cs:__imp_free
0x18000e63d  test    rbx, rbx
0x18000e640  jnz     short loc_18000E631
0x18000e642  mov     eax, 80004005h
0x18000e647  jmp     loc_18000E9ED
0x18000e64c  mov     r8, r13; Size
0x18000e64f  xor     edx, edx; Val
0x18000e651  mov     rcx, r15; void *
0x18000e654  call    memset_0
0x18000e659  xor     eax, eax
0x18000e65b  mov     r9d, eax
0x18000e65e  test    r14d, r14d
0x18000e661  jle     loc_18000E72E
0x18000e667  mov     eax, r9d
0x18000e66a  movzx   r8d, word ptr [rdi+rax*2]
0x18000e66f  cmp     r8d, 61h ; 'a'
0x18000e673  ja      short loc_18000E6E0
0x18000e675  jz      loc_18000E701
0x18000e67b  cmp     r8d, 38h ; '8'
0x18000e67f  ja      short loc_18000E6B4
0x18000e681  jz      short loc_18000E6AE
0x18000e683  mov     ecx, r8d
0x18000e686  sub     ecx, 30h ; '0'
0x18000e689  jz      short loc_18000E6AE
0x18000e68b  sub     ecx, 1
0x18000e68e  jz      short loc_18000E6AE
0x18000e690  sub     ecx, 1
0x18000e693  jz      short loc_18000E6AE
0x18000e695  sub     ecx, 1
0x18000e698  jz      short loc_18000E6AE
0x18000e69a  sub     ecx, 1
0x18000e69d  jz      short loc_18000E6AE
0x18000e69f  sub     ecx, 1
0x18000e6a2  jz      short loc_18000E6AE
0x18000e6a4  sub     ecx, 1
0x18000e6a7  jz      short loc_18000E6AE
0x18000e6a9  cmp     ecx, 1
0x18000e6ac  jnz     short loc_18000E6FC
0x18000e6ae  sub     r8b, 30h ; '0'
0x18000e6b2  jmp     short loc_18000E705
0x18000e6b4  mov     ecx, r8d
0x18000e6b7  sub     ecx, 39h ; '9'
0x18000e6ba  jz      short loc_18000E6AE
0x18000e6bc  sub     ecx, 8
0x18000e6bf  jz      short loc_18000E6DA
0x18000e6c1  sub     ecx, 1
0x18000e6c4  jz      short loc_18000E6DA
0x18000e6c6  sub     ecx, 1
0x18000e6c9  jz      short loc_18000E6DA
0x18000e6cb  sub     ecx, 1
0x18000e6ce  jz      short loc_18000E6DA
0x18000e6d0  sub     ecx, 1
0x18000e6d3  jz      short loc_18000E6DA
0x18000e6d5  cmp     ecx, 1
0x18000e6d8  jnz     short loc_18000E6FC
0x18000e6da  sub     r8b, 37h ; '7'
0x18000e6de  jmp     short loc_18000E705
0x18000e6e0  mov     ecx, r8d
0x18000e6e3  sub     ecx, 62h ; 'b'
0x18000e6e6  jz      short loc_18000E701
0x18000e6e8  sub     ecx, 1
0x18000e6eb  jz      short loc_18000E701
0x18000e6ed  sub     ecx, 1
0x18000e6f0  jz      short loc_18000E701
0x18000e6f2  sub     ecx, 1
0x18000e6f5  jz      short loc_18000E701
0x18000e6f7  cmp     ecx, 1
0x18000e6fa  jz      short loc_18000E701
0x18000e6fc  xor     r8b, r8b
0x18000e6ff  jmp     short loc_18000E705
0x18000e701  sub     r8b, 57h ; 'W'
0x18000e705  mov     eax, r9d
0x18000e708  mov     edx, r9d
0x18000e70b  and     eax, 1
0x18000e70e  shr     rdx, 1
0x18000e711  shl     eax, 2
0x18000e714  mov     ecx, 4
0x18000e719  sub     ecx, eax
0x18000e71b  inc     r9d
0x18000e71e  shl     r8b, cl
0x18000e721  or      [rdx+r15], r8b
0x18000e725  cmp     r9d, r14d
0x18000e728  jl      loc_18000E667
0x18000e72e  mov     rcx, [rbp+80h+var_60]
0x18000e732  mov     r9d, 3
0x18000e738  mov     rdx, [rbp+80h+var_70]
0x18000e73c  mov     [rsp+0B0h+cbData], r13d
0x18000e741  mov     [rsp+0B0h+lpData], r15
0x18000e746  mov     rcx, [rcx]
0x18000e749  jmp     loc_18000E563
0x18000e74e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e752  mov     rcx, rdi
0x18000e755  mov     r13, r8
0x18000e758  cmp     [rbp+80h+arg_20], r8b
0x18000e75f  jz      loc_18000E7FF
0x18000e765  inc     rax
0x18000e768  cmp     [rdi+rax*2], r8w
0x18000e76d  jnz     short loc_18000E765
0x18000e76f  cmp     eax, 0FFEh
0x18000e774  jle     short loc_18000E786
0x18000e776  mov     rcx, rdi; Block
0x18000e779  call    cs:__imp_free
0x18000e77f  mov     ebx, 80004005h
0x18000e784  jmp     short loc_18000E7AA
0x18000e786  mov     ecx, 2000h; Size
0x18000e78b  call    cs:__imp_malloc
0x18000e791  xor     r8d, r8d
0x18000e794  mov     r13, rax
0x18000e797  test    rax, rax
0x18000e79a  jnz     short loc_18000E7BA
0x18000e79c  mov     rcx, rdi; Block
0x18000e79f  call    cs:__imp_free
0x18000e7a5  mov     ebx, 8007000Eh
0x18000e7aa  mov     rcx, r12; Block
0x18000e7ad  call    cs:__imp_free
0x18000e7b3  mov     eax, ebx
0x18000e7b5  jmp     loc_18000E9ED
0x18000e7ba  mov     r14, [r14+8]
0x18000e7be  mov     esi, r8d
0x18000e7c1  cmp     [r14+8], r8d
0x18000e7c5  jle     loc_18000E9A9
0x18000e7cb  mov     rax, [r14]
0x18000e7ce  lea     rdx, aModule; "Module"
0x18000e7d5  movsxd  r15, esi
0x18000e7d8  mov     rcx, [rax+r15*8]
0x18000e7dc  mov     rcx, [rcx]; lpString1
0x18000e7df  call    cs:__imp_lstrcmpiW
0x18000e7e5  xor     r8d, r8d
0x18000e7e8  test    eax, eax
0x18000e7ea  jz      short loc_18000E84D
0x18000e7ec  inc     esi
0x18000e7ee  cmp     esi, [r14+8]
0x18000e7f2  jl      short loc_18000E7CB
0x18000e7f4  mov     r15, [rbp+80h+var_70]
0x18000e7f8  mov     rcx, rdi
0x18000e7fb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e7ff  mov     rsi, [rbp+80h+var_80]
0x18000e803  inc     rax
  ... truncated ...
```
