# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x180002fe8`
- end: `0x1800035fe`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1558`
- prototype: `__int64 __usercall@<rax>(ATL::CRegParser *__hidden this@<rcx>, struct ATL::CRegKey *@<rdx>, const unsigned __int16 *@<r8>, unsigned __int16 *@<r9>, bool)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180005130`

## callees

- `0x180002fe8`
- `0x180004598`
- `0x180006510`
- `0x18000a582`
- `0x18000a5b0`
- `0x18000a670`

## import_xrefs

- `msvcrt!wcscat_s` at `0x18000353e`
- `msvcrt!wcscat_s` at `0x18000354d`
- `msvcrt!wcscat_s` at `0x180003560`
- `msvcrt!wcscat_s` at `0x180003580`
- `msvcrt!wcscat_s` at `0x18000353e`
- `msvcrt!wcscat_s` at `0x18000354d`
- `msvcrt!wcscat_s` at `0x180003560`
- `msvcrt!wcscat_s` at `0x180003580`
- `msvcrt!malloc` at `0x18000302a`
- `msvcrt!malloc` at `0x18000309a`
- `msvcrt!malloc` at `0x1800031fa`
- `msvcrt!malloc` at `0x18000337f`
- `msvcrt!malloc` at `0x18000302a`
- `msvcrt!malloc` at `0x18000309a`
- `msvcrt!malloc` at `0x1800031fa`
- `msvcrt!malloc` at `0x18000337f`
- `msvcrt!free` at `0x1800030f4`
- `msvcrt!free` at `0x18000317d`
- `msvcrt!free` at `0x18000321a`
- `msvcrt!free` at `0x18000322b`
- `msvcrt!free` at `0x18000336d`
- `msvcrt!free` at `0x180003393`
- `msvcrt!free` at `0x1800033a1`
- `msvcrt!free` at `0x180003436`
- `msvcrt!free` at `0x1800035b4`
- `msvcrt!free` at `0x1800035c3`
- `msvcrt!free` at `0x1800035d4`
- `msvcrt!free` at `0x1800030f4`
- `msvcrt!free` at `0x18000317d`
- `msvcrt!free` at `0x18000321a`
- `msvcrt!free` at `0x18000322b`
- `msvcrt!free` at `0x18000336d`
- `msvcrt!free` at `0x180003393`
- `msvcrt!free` at `0x1800033a1`
- `msvcrt!free` at `0x180003436`
- `msvcrt!free` at `0x1800035b4`
- `msvcrt!free` at `0x1800035c3`
- `msvcrt!free` at `0x1800035d4`
- `USER32!CharNextW` at `0x1800030d2`
- `USER32!CharNextW` at `0x18000347d`
- `USER32!CharNextW` at `0x18000348a`
- `USER32!CharNextW` at `0x1800034ae`
- `USER32!CharNextW` at `0x1800030d2`
- `USER32!CharNextW` at `0x18000347d`
- `USER32!CharNextW` at `0x18000348a`
- `USER32!CharNextW` at `0x1800034ae`
- `USER32!CharPrevW` at `0x1800034fe`
- `USER32!CharPrevW` at `0x1800034fe`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000315a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003424`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000315a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180003424`
- `KERNEL32!lstrcpynW` at `0x180003525`
- `KERNEL32!lstrcpynW` at `0x180003525`
- `KERNEL32!lstrcmpiW` at `0x180003073`
- `KERNEL32!lstrcmpiW` at `0x1800033d3`
- `KERNEL32!lstrcmpiW` at `0x180003073`
- `KERNEL32!lstrcmpiW` at `0x1800033d3`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000312d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000312d`

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
0x180002fe8  push    rbp
0x180002fea  push    rbx
0x180002feb  push    rsi
0x180002fec  push    rdi
0x180002fed  push    r12
0x180002fef  push    r13
0x180002ff1  push    r14
0x180002ff3  push    r15
0x180002ff5  sub     rsp, 78h
0x180002ff9  lea     rbp, [rsp+30h]
0x180002ffe  mov     rax, cs:__security_cookie
0x180003005  xor     rax, rbp
0x180003008  mov     [rbp+80h+var_48], rax
0x18000300c  mov     r14, rcx
0x18000300f  mov     [rbp+80h+var_50], rcx
0x180003013  mov     ecx, 2000h; Size
0x180003018  mov     [rbp+80h+var_80], r9
0x18000301c  mov     r15, r8
0x18000301f  mov     [rbp+80h+var_70], r8
0x180003023  mov     r13, rdx
0x180003026  mov     [rbp+80h+var_60], rdx
0x18000302a  call    cs:__imp_malloc
0x180003030  xor     edi, edi
0x180003032  mov     qword ptr [rbp+80h+Data], rax
0x180003036  mov     r12, rax
0x180003039  test    rax, rax
0x18000303c  jnz     short loc_180003048
0x18000303e  mov     eax, 8007000Eh
0x180003043  jmp     loc_1800035E1
0x180003048  mov     rdx, r12; unsigned __int16 *
0x18000304b  mov     rcx, r14; this
0x18000304e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003053  mov     ebx, eax
0x180003055  test    eax, eax
0x180003057  js      loc_18000339E
0x18000305d  mov     ebx, edi
0x18000305f  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003066  movsxd  rsi, ebx
0x180003069  mov     rcx, r12; lpString1
0x18000306c  add     rsi, rsi
0x18000306f  mov     rdx, [rax+rsi*8]; lpString2
0x180003073  call    cs:__imp_lstrcmpiW
0x180003079  test    eax, eax
0x18000307b  jz      short loc_180003095
0x18000307d  inc     ebx
0x18000307f  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180003086  cmp     ebx, 3
0x180003089  jb      short loc_180003066
0x18000308b  mov     ebx, 80020009h
0x180003090  jmp     loc_18000339E
0x180003095  mov     ecx, 2000h; Size
0x18000309a  call    cs:__imp_malloc
0x1800030a0  mov     rdi, rax
0x1800030a3  test    rax, rax
0x1800030a6  jz      loc_180003399
0x1800030ac  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800030b3  movzx   esi, word ptr [rax+rsi*8+8]
0x1800030b8  mov     rcx, [r14]; lpsz
0x1800030bb  movzx   edx, word ptr [rcx]
0x1800030be  sub     edx, 9
0x1800030c1  jz      short loc_1800030D2
0x1800030c3  sub     edx, 1
0x1800030c6  jz      short loc_1800030D2
0x1800030c8  sub     edx, 3
0x1800030cb  jz      short loc_1800030D2
0x1800030cd  cmp     edx, 13h
0x1800030d0  jnz     short loc_1800030DD
0x1800030d2  call    cs:__imp_CharNextW
0x1800030d8  mov     [r14], rax
0x1800030db  jmp     short loc_1800030B8
0x1800030dd  mov     rdx, rdi; unsigned __int16 *
0x1800030e0  mov     rcx, r14; this
0x1800030e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800030e8  xor     r8d, r8d; dwFlags
0x1800030eb  mov     ebx, eax
0x1800030ed  test    eax, eax
0x1800030ef  jns     short loc_1800030FF
0x1800030f1  mov     rcx, rdi; Block
0x1800030f4  call    cs:__imp_free
0x1800030fa  jmp     loc_18000339E
0x1800030ff  mov     eax, 8
0x180003104  mov     [rbp+80h+pulOut], r8d
0x180003108  mov     rbx, r8
0x18000310b  cmp     si, ax
0x18000310e  jz      loc_180003342
0x180003114  cmp     si, 11h
0x180003118  jz      short loc_18000318B
0x18000311a  mov     eax, 13h
0x18000311f  cmp     si, ax
0x180003122  jnz     short loc_180003160
0x180003124  lea     r9, [rbp+80h+pulOut]; pulOut
0x180003128  xor     edx, edx; lcid
0x18000312a  mov     rcx, rdi; strIn
0x18000312d  call    cs:__imp_VarUI4FromStr
0x180003133  mov     eax, [rbp+80h+pulOut]
0x180003136  mov     r9d, 4; dwType
0x18000313c  mov     rcx, [r13+0]; hKey
0x180003140  mov     rdx, r15; lpValueName
0x180003143  mov     dword ptr [rbp+80h+Data], eax
0x180003146  lea     rax, [rbp+80h+Data]
0x18000314a  mov     [rsp+0B0h+cbData], 4; cbData
0x180003152  mov     [rsp+0B0h+lpData], rax; lpData
0x180003157  xor     r8d, r8d; Reserved
0x18000315a  call    cs:__imp_RegSetValueExW
0x180003160  mov     rsi, [rbp+80h+var_80]
0x180003164  mov     rcx, [rbp+80h+var_50]; this
0x180003168  mov     rdx, rsi; unsigned __int16 *
0x18000316b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180003170  mov     esi, eax
0x180003172  mov     rcx, rdi; Block
0x180003175  test    eax, eax
0x180003177  jns     loc_1800035C3
0x18000317d  call    cs:__imp_free
0x180003183  mov     rcx, r12
0x180003186  jmp     loc_1800035B4
0x18000318b  or      r14, 0FFFFFFFFFFFFFFFFh
0x18000318f  inc     r14
0x180003192  cmp     [rdi+r14*2], r8w
0x180003197  jnz     short loc_18000318F
0x180003199  test    r14b, 1
0x18000319d  jnz     loc_18000336A
0x1800031a3  mov     eax, r14d
0x1800031a6  cdq; unsigned __int64
0x1800031a7  sub     eax, edx
0x1800031a9  sar     eax, 1
0x1800031ab  movsxd  r13, eax
0x1800031ae  cmp     r13, 400h
0x1800031b5  ja      short loc_1800031EC
0x1800031b7  mov     rcx, r13; this
0x1800031ba  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x1800031bf  xor     r8d, r8d
0x1800031c2  test    al, al
0x1800031c4  jz      short loc_1800031EC
0x1800031c6  lea     rax, [r13+0Fh]
0x1800031ca  cmp     rax, r13
0x1800031cd  ja      short loc_1800031D9
0x1800031cf  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800031d9  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800031dd  call    _alloca_probe
0x1800031e2  sub     rsp, rax
0x1800031e5  lea     r15, [rsp+0B0h+var_80]
0x1800031ea  jmp     short loc_180003212
0x1800031ec  lea     rcx, [r13+10h]; Size
0x1800031f0  cmp     rcx, r13
0x1800031f3  jnb     short loc_1800031FA
0x1800031f5  mov     r15, r8
0x1800031f8  jmp     short loc_180003212
0x1800031fa  call    cs:__imp_malloc
0x180003200  xor     r8d, r8d
0x180003203  test    rax, rax
0x180003206  jz      short loc_1800031F5
0x180003208  mov     [rax], r8
0x18000320b  lea     r15, [rax+10h]
0x18000320f  mov     rbx, rax
0x180003212  test    r15, r15
0x180003215  jnz     short loc_180003240
0x180003217  mov     rcx, rdi; Block
0x18000321a  call    cs:__imp_free
0x180003220  mov     rcx, r12
0x180003223  jmp     short loc_18000322B
0x180003225  mov     rcx, rbx; Block
0x180003228  mov     rbx, [rbx]
0x18000322b  call    cs:__imp_free
0x180003231  test    rbx, rbx
0x180003234  jnz     short loc_180003225
0x180003236  mov     eax, 80004005h
0x18000323b  jmp     loc_1800035E1
0x180003240  mov     r8, r13; Size
0x180003243  xor     edx, edx; Val
0x180003245  mov     rcx, r15; void *
0x180003248  call    memset_0
0x18000324d  xor     eax, eax
0x18000324f  mov     r9d, eax
0x180003252  test    r14d, r14d
0x180003255  jle     loc_180003322
0x18000325b  mov     eax, r9d
0x18000325e  movzx   r8d, word ptr [rdi+rax*2]
0x180003263  cmp     r8d, 61h ; 'a'
0x180003267  ja      short loc_1800032D4
0x180003269  jz      loc_1800032F5
0x18000326f  cmp     r8d, 38h ; '8'
0x180003273  ja      short loc_1800032A8
0x180003275  jz      short loc_1800032A2
0x180003277  mov     ecx, r8d
0x18000327a  sub     ecx, 30h ; '0'
0x18000327d  jz      short loc_1800032A2
0x18000327f  sub     ecx, 1
0x180003282  jz      short loc_1800032A2
0x180003284  sub     ecx, 1
0x180003287  jz      short loc_1800032A2
0x180003289  sub     ecx, 1
0x18000328c  jz      short loc_1800032A2
0x18000328e  sub     ecx, 1
0x180003291  jz      short loc_1800032A2
0x180003293  sub     ecx, 1
0x180003296  jz      short loc_1800032A2
0x180003298  sub     ecx, 1
0x18000329b  jz      short loc_1800032A2
0x18000329d  cmp     ecx, 1
0x1800032a0  jnz     short loc_1800032F0
0x1800032a2  sub     r8b, 30h ; '0'
0x1800032a6  jmp     short loc_1800032F9
0x1800032a8  mov     ecx, r8d
0x1800032ab  sub     ecx, 39h ; '9'
0x1800032ae  jz      short loc_1800032A2
0x1800032b0  sub     ecx, 8
0x1800032b3  jz      short loc_1800032CE
0x1800032b5  sub     ecx, 1
0x1800032b8  jz      short loc_1800032CE
0x1800032ba  sub     ecx, 1
0x1800032bd  jz      short loc_1800032CE
0x1800032bf  sub     ecx, 1
0x1800032c2  jz      short loc_1800032CE
0x1800032c4  sub     ecx, 1
0x1800032c7  jz      short loc_1800032CE
0x1800032c9  cmp     ecx, 1
0x1800032cc  jnz     short loc_1800032F0
0x1800032ce  sub     r8b, 37h ; '7'
0x1800032d2  jmp     short loc_1800032F9
0x1800032d4  mov     ecx, r8d
0x1800032d7  sub     ecx, 62h ; 'b'
0x1800032da  jz      short loc_1800032F5
0x1800032dc  sub     ecx, 1
0x1800032df  jz      short loc_1800032F5
0x1800032e1  sub     ecx, 1
0x1800032e4  jz      short loc_1800032F5
0x1800032e6  sub     ecx, 1
0x1800032e9  jz      short loc_1800032F5
0x1800032eb  cmp     ecx, 1
0x1800032ee  jz      short loc_1800032F5
0x1800032f0  xor     r8b, r8b
0x1800032f3  jmp     short loc_1800032F9
0x1800032f5  sub     r8b, 57h ; 'W'
0x1800032f9  mov     eax, r9d
0x1800032fc  mov     edx, r9d
0x1800032ff  and     eax, 1
0x180003302  shr     rdx, 1
0x180003305  shl     eax, 2
0x180003308  mov     ecx, 4
0x18000330d  sub     ecx, eax
0x18000330f  inc     r9d
0x180003312  shl     r8b, cl
0x180003315  or      [rdx+r15], r8b
0x180003319  cmp     r9d, r14d
0x18000331c  jl      loc_18000325B
0x180003322  mov     rcx, [rbp+80h+var_60]
0x180003326  mov     r9d, 3
0x18000332c  mov     rdx, [rbp+80h+var_70]
0x180003330  mov     [rsp+0B0h+cbData], r13d
0x180003335  mov     [rsp+0B0h+lpData], r15
0x18000333a  mov     rcx, [rcx]
0x18000333d  jmp     loc_180003157
0x180003342  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003346  mov     rcx, rdi
0x180003349  mov     r13, r8
0x18000334c  cmp     [rbp+80h+arg_20], r8b
0x180003353  jz      loc_1800033F3
0x180003359  inc     rax
0x18000335c  cmp     [rdi+rax*2], r8w
0x180003361  jnz     short loc_180003359
0x180003363  cmp     eax, 0FFEh
0x180003368  jle     short loc_18000337A
0x18000336a  mov     rcx, rdi; Block
0x18000336d  call    cs:__imp_free
0x180003373  mov     ebx, 80004005h
0x180003378  jmp     short loc_18000339E
0x18000337a  mov     ecx, 2000h; Size
0x18000337f  call    cs:__imp_malloc
0x180003385  xor     r8d, r8d
0x180003388  mov     r13, rax
0x18000338b  test    rax, rax
0x18000338e  jnz     short loc_1800033AE
0x180003390  mov     rcx, rdi; Block
0x180003393  call    cs:__imp_free
0x180003399  mov     ebx, 8007000Eh
0x18000339e  mov     rcx, r12; Block
0x1800033a1  call    cs:__imp_free
0x1800033a7  mov     eax, ebx
0x1800033a9  jmp     loc_1800035E1
0x1800033ae  mov     r14, [r14+8]
0x1800033b2  mov     esi, r8d
0x1800033b5  cmp     [r14+8], r8d
0x1800033b9  jle     loc_18000359D
0x1800033bf  mov     rax, [r14]
0x1800033c2  lea     rdx, String2; "Module"
0x1800033c9  movsxd  r15, esi
0x1800033cc  mov     rcx, [rax+r15*8]
0x1800033d0  mov     rcx, [rcx]; lpString1
0x1800033d3  call    cs:__imp_lstrcmpiW
0x1800033d9  xor     r8d, r8d
0x1800033dc  test    eax, eax
0x1800033de  jz      short loc_180003441
0x1800033e0  inc     esi
0x1800033e2  cmp     esi, [r14+8]
0x1800033e6  jl      short loc_1800033BF
0x1800033e8  mov     r15, [rbp+80h+var_70]
0x1800033ec  mov     rcx, rdi
0x1800033ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800033f3  mov     rsi, [rbp+80h+var_80]
0x1800033f7  inc     rax
  ... truncated ...
```
