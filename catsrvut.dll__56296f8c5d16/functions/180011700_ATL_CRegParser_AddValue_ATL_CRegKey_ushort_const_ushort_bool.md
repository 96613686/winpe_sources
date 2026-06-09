# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *,bool)

- ea: `0x180011700`
- end: `0x180011bcf`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG_N@Z`
- size: `1231`
- prototype: `__int64 __fastcall(ATL::CRegObject **this, HKEY *, const unsigned __int16 *, unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config`

## callers

- `0x18000a980`

## callees

- `0x18000b2d8`
- `0x180011700`
- `0x180011bd8`
- `0x1800139a8`
- `0x180014cf8`
- `0x180014d84`
- `0x180014e24`
- `0x1800153c8`
- `0x18005583a`
- `0x180055880`
- `0x180055940`

## import_xrefs

- `msvcrt!wcscat_s` at `0x180011aa8`
- `msvcrt!wcscat_s` at `0x180011ab9`
- `msvcrt!wcscat_s` at `0x180011ace`
- `msvcrt!wcscat_s` at `0x180011aed`
- `msvcrt!wcscat_s` at `0x180011aa8`
- `msvcrt!wcscat_s` at `0x180011ab9`
- `msvcrt!wcscat_s` at `0x180011ace`
- `msvcrt!wcscat_s` at `0x180011aed`
- `msvcrt!malloc` at `0x180011748`
- `msvcrt!malloc` at `0x18001179d`
- `msvcrt!malloc` at `0x180011a0f`
- `msvcrt!malloc` at `0x180011748`
- `msvcrt!malloc` at `0x18001179d`
- `msvcrt!malloc` at `0x180011a0f`
- `msvcrt!free` at `0x1800117ae`
- `msvcrt!free` at `0x1800119f1`
- `msvcrt!free` at `0x1800119fa`
- `msvcrt!free` at `0x180011a22`
- `msvcrt!free` at `0x180011b45`
- `msvcrt!free` at `0x180011b60`
- `msvcrt!free` at `0x180011b69`
- `msvcrt!free` at `0x180011b80`
- `msvcrt!free` at `0x180011b89`
- `msvcrt!free` at `0x180011b9d`
- `msvcrt!free` at `0x1800117ae`
- `msvcrt!free` at `0x1800119f1`
- `msvcrt!free` at `0x1800119fa`
- `msvcrt!free` at `0x180011a22`
- `msvcrt!free` at `0x180011b45`
- `msvcrt!free` at `0x180011b60`
- `msvcrt!free` at `0x180011b69`
- `msvcrt!free` at `0x180011b80`
- `msvcrt!free` at `0x180011b89`
- `msvcrt!free` at `0x180011b9d`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180011a71`
- `api-ms-win-core-string-l2-1-0!CharPrevW` at `0x180011a71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800119ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011b37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800119ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180011b37`
- `KERNEL32!lstrcmpiW` at `0x18001178a`
- `KERNEL32!lstrcmpiW` at `0x18001178a`
- `KERNEL32!lstrcpynW` at `0x180011a93`
- `KERNEL32!lstrcpynW` at `0x180011a93`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180011818`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180011818`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegObject **this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  const WCHAR *v5; // r15
  ATL::CRegObject **v7; // r12
  unsigned __int16 *v8; // rax
  unsigned __int16 *v9; // rsi
  int Token; // ebx
  unsigned int i; // ebx
  unsigned __int16 *v12; // rdi
  __int16 v13; // r14
  __int64 v14; // rbx
  unsigned __int64 v15; // rdx
  unsigned __int64 cbData; // r13
  __int64 v17; // rax
  void *v18; // rsp
  LPCWSTR *lpData; // r15
  unsigned int v20; // r9d
  unsigned int v21; // edx
  char v22; // r8
  const BYTE *v23; // r13
  _WORD *v24; // r14
  __int64 v25; // rbx
  __int64 v26; // rax
  const WCHAR *v27; // rax
  const wchar_t *v28; // r12
  unsigned __int16 *v29; // rax
  unsigned __int16 *v30; // r15
  __int64 v31; // rax
  LPCWSTR lpValueName; // [rsp+30h] [rbp+0h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp+8h] BYREF
  _QWORD *v35; // [rsp+40h] [rbp+10h] BYREF
  HKEY *v36; // [rsp+48h] [rbp+18h]
  unsigned __int16 *v37; // [rsp+50h] [rbp+20h]
  _QWORD *v38; // [rsp+58h] [rbp+28h] BYREF
  ATL::CRegParser *v39; // [rsp+60h] [rbp+30h]

  v37 = a4;
  v5 = a3;
  lpValueName = a3;
  v36 = a2;
  v7 = this;
  v39 = (ATL::CRegParser *)this;
  v35 = 0;
  v8 = (unsigned __int16 *)malloc(0x2000u);
  v9 = v8;
  if ( !v8 )
    goto LABEL_9;
  Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v7, v8);
  if ( Token < 0 )
  {
LABEL_74:
    free(v9);
    goto LABEL_75;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 3 )
    {
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v35);
      return 2147614729LL;
    }
    if ( !lstrcmpiW(v9, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v12 = (unsigned __int16 *)malloc(0x2000u);
  if ( !v12 )
    goto LABEL_8;
  v13 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace((ATL::CRegParser *)v7);
  Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v7, v12);
  if ( Token < 0 )
  {
LABEL_73:
    free(v12);
    goto LABEL_74;
  }
  pulOut = 0;
  if ( v13 != 8 )
  {
    if ( v13 != 17 )
    {
      if ( v13 == 19 )
      {
        VarUI4FromStr(v12, 0, 0, &pulOut);
        LODWORD(lpValueName) = pulOut;
        RegSetValueExW(*a2, v5, 0, 4u, (const BYTE *)&lpValueName, 4u);
      }
      goto LABEL_72;
    }
    v14 = -1;
    do
      ++v14;
    while ( v12[v14] );
    if ( (v14 & 1) == 0 )
    {
      v15 = (unsigned int)((int)v14 >> 31);
      cbData = (int)v14 / 2;
      if ( cbData <= 0x400
        && (LODWORD(v15) = (int)v14 % 2,
            ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)((int)v14 / 2), v15)) )
      {
        v17 = cbData + 15;
        if ( cbData + 15 < cbData )
          v17 = 0xFFFFFFFFFFFFFF0LL;
        v18 = alloca(v17 & 0xFFFFFFFFFFFFFFF0uLL);
        lpData = &lpValueName;
      }
      else
      {
        lpData = (LPCWSTR *)ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(
                              &v35,
                              cbData);
      }
      if ( lpData )
      {
        memset_0(lpData, 0, cbData);
        v20 = 0;
        if ( (int)v14 <= 0 )
        {
LABEL_52:
          RegSetValueExW(*v36, lpValueName, 0, 3u, (const BYTE *)lpData, cbData);
          goto LABEL_72;
        }
        while ( 2 )
        {
          v21 = v12[v20];
          if ( v21 > 0x61 )
          {
            if ( v21 != 98 && v21 != 99 && v21 != 100 && v21 - 101 >= 2 )
              goto LABEL_49;
          }
          else if ( v21 != 97 )
          {
            if ( v21 > 0x38 )
            {
              if ( v21 == 57 )
                goto LABEL_37;
              if ( v21 != 65 && v21 != 66 && v21 != 67 && v21 != 68 && v21 - 69 > 1 )
                goto LABEL_49;
              v22 = v21 - 55;
            }
            else
            {
              if ( v21 == 56
                || v21 == 48
                || v21 == 49
                || v21 == 50
                || v21 == 51
                || v21 == 52
                || v21 == 53
                || v21 - 54 <= 1 )
              {
LABEL_37:
                v22 = v21 - 48;
                goto LABEL_51;
              }
LABEL_49:
              v22 = 0;
            }
LABEL_51:
            *((_BYTE *)lpData + ((unsigned __int64)v20 >> 1)) |= v22 << (4 - 4 * (v20 & 1));
            if ( (int)++v20 >= (int)v14 )
              goto LABEL_52;
            continue;
          }
          break;
        }
        v22 = v21 - 87;
        goto LABEL_51;
      }
    }
    goto LABEL_57;
  }
  v23 = (const BYTE *)v12;
  v24 = 0;
  v25 = -1;
  if ( !a5 )
  {
    do
LABEL_69:
      ++v25;
    while ( *(_WORD *)&v23[2 * v25] );
    RegSetValueExW(*v36, v5, 0, 1u, v23, 2 * v25 + 2);
    if ( v24 )
      free(v24);
LABEL_72:
    Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v7, v37);
    if ( Token >= 0 )
    {
      free(v12);
      free(v9);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v35);
      return 0;
    }
    goto LABEL_73;
  }
  v26 = -1;
  do
    ++v26;
  while ( v12[v26] );
  if ( (int)v26 > 4094 )
  {
LABEL_57:
    free(v12);
    free(v9);
    Token = -2147467259;
    goto LABEL_75;
  }
  v24 = malloc(0x2000u);
  if ( v24 )
  {
    v38 = 0;
    v27 = ATL::CRegObject::StrFromMap(v7[1], L"Module");
    v28 = v27;
    if ( v27 )
    {
      v29 = (unsigned __int16 *)ATL::CRegParser::StrStrW(v12, v27);
      v30 = v29;
      if ( v29 && (v29 == v37 || *CharPrevW(v12, v29) != 34) )
      {
        *v24 = 0;
        lstrcpynW(v24, v12, v30 - v12);
        wcscat_s(v24, 0x1000u, L"\"");
        wcscat_s(v24, 0x1000u, v28);
        wcscat_s(v24, 0x1000u, L"\"");
        v31 = -1;
        do
          ++v31;
        while ( v28[v31] );
        wcscat_s(v24, 0x1000u, &v30[v31]);
        v23 = (const BYTE *)v24;
      }
      v5 = lpValueName;
    }
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v38);
    v7 = (ATL::CRegObject **)v39;
    goto LABEL_69;
  }
  free(v12);
LABEL_8:
  free(v9);
LABEL_9:
  Token = -2147024882;
LABEL_75:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(&v35);
  return (unsigned int)Token;
}

```

## disassembly

```asm
0x180011700  push    rbp
0x180011702  push    rbx
0x180011703  push    rsi
0x180011704  push    rdi
0x180011705  push    r12
0x180011707  push    r13
0x180011709  push    r14
0x18001170b  push    r15
0x18001170d  sub     rsp, 78h
0x180011711  lea     rbp, [rsp+30h]
0x180011716  mov     rax, cs:__security_cookie
0x18001171d  xor     rax, rbp
0x180011720  mov     [rbp+80h+var_48], rax
0x180011724  mov     [rbp+80h+var_60], r9
0x180011728  mov     r15, r8
0x18001172b  mov     [rbp+80h+lpValueName], r8
0x18001172f  mov     r13, rdx
0x180011732  mov     [rbp+80h+var_68], rdx
0x180011736  mov     r12, rcx
0x180011739  mov     [rbp+80h+var_50], rcx
0x18001173d  xor     edi, edi
0x18001173f  mov     [rbp+80h+var_70], rdi
0x180011743  mov     ecx, 2000h; Size
0x180011748  call    cs:__imp_malloc
0x18001174e  mov     rsi, rax
0x180011751  test    rax, rax
0x180011754  jz      short loc_1800117B4
0x180011756  mov     rdx, rax; unsigned __int16 *
0x180011759  mov     rcx, r12; this
0x18001175c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011761  mov     ebx, eax
0x180011763  test    eax, eax
0x180011765  js      loc_180011B66
0x18001176b  mov     ebx, edi
0x18001176d  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180011774  mov     rcx, rsi; Block
0x180011777  cmp     ebx, 3
0x18001177a  jnb     loc_180011B9D
0x180011780  movsxd  r14, ebx
0x180011783  add     r14, r14
0x180011786  mov     rdx, [rax+r14*8]; lpString2
0x18001178a  call    cs:__imp_lstrcmpiW
0x180011790  test    eax, eax
0x180011792  jz      short loc_180011798
0x180011794  inc     ebx
0x180011796  jmp     short loc_18001176D
0x180011798  mov     ecx, 2000h; Size
0x18001179d  call    cs:__imp_malloc
0x1800117a3  mov     rdi, rax
0x1800117a6  test    rax, rax
0x1800117a9  jnz     short loc_1800117BE
0x1800117ab  mov     rcx, rsi; Block
0x1800117ae  call    cs:__imp_free
0x1800117b4  mov     ebx, 8007000Eh
0x1800117b9  jmp     loc_180011B70
0x1800117be  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800117c5  movzx   r14d, word ptr [rax+r14*8+8]
0x1800117cb  mov     rcx, r12; this
0x1800117ce  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800117d3  mov     rdx, rdi; unsigned __int16 *
0x1800117d6  mov     rcx, r12; this
0x1800117d9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800117de  mov     ebx, eax
0x1800117e0  xor     ecx, ecx
0x1800117e2  test    eax, eax
0x1800117e4  js      loc_180011B5D
0x1800117ea  mov     [rbp+80h+pulOut], ecx
0x1800117ed  lea     eax, [rcx+8]
0x1800117f0  cmp     r14w, ax
0x1800117f4  jz      loc_1800119C5
0x1800117fa  cmp     r14w, 11h
0x1800117ff  jz      short loc_180011847
0x180011801  cmp     r14w, 13h
0x180011806  jnz     loc_180011B4B
0x18001180c  lea     r9, [rbp+80h+pulOut]; pulOut
0x180011810  xor     r8d, r8d; dwFlags
0x180011813  xor     edx, edx; lcid
0x180011815  mov     rcx, rdi; strIn
0x180011818  call    cs:__imp_VarUI4FromStr
0x18001181e  mov     eax, [rbp+80h+pulOut]
0x180011821  mov     dword ptr [rbp+80h+lpValueName], eax
0x180011824  mov     [rsp+0B0h+cbData], 4
0x18001182c  lea     rax, [rbp+80h+lpValueName]
0x180011830  mov     [rsp+0B0h+lpData], rax
0x180011835  mov     r9d, 4
0x18001183b  mov     rdx, r15
0x18001183e  mov     rcx, [r13+0]
0x180011842  jmp     loc_1800119B7
0x180011847  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001184b  inc     rbx
0x18001184e  cmp     [rdi+rbx*2], cx
0x180011852  jnz     short loc_18001184B
0x180011854  test    bl, 1
0x180011857  jnz     loc_1800119EE
0x18001185d  mov     eax, ebx
0x18001185f  cdq; unsigned __int64
0x180011860  mov     ecx, 2
0x180011865  idiv    ecx
0x180011867  movsxd  r13, eax
0x18001186a  cmp     r13, 400h
0x180011871  ja      short loc_1800118A5
0x180011873  mov     rcx, r13; this
0x180011876  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18001187b  test    al, al
0x18001187d  jz      short loc_1800118A5
0x18001187f  lea     rax, [r13+0Fh]
0x180011883  cmp     rax, r13
0x180011886  ja      short loc_180011892
0x180011888  mov     rax, 0FFFFFFFFFFFFFF0h
0x180011892  and     rax, 0FFFFFFFFFFFFFFF0h
0x180011896  call    _alloca_probe
0x18001189b  sub     rsp, rax
0x18001189e  lea     r15, [rsp+0B0h+lpValueName]
0x1800118a3  jmp     short loc_1800118B4
0x1800118a5  mov     rdx, r13
0x1800118a8  lea     rcx, [rbp+80h+var_70]
0x1800118ac  call    ?Allocate@?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAAPEAX_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::Allocate(unsigned __int64)
0x1800118b1  mov     r15, rax
0x1800118b4  test    r15, r15
0x1800118b7  jz      loc_1800119EE
0x1800118bd  mov     r8, r13; Size
0x1800118c0  xor     edx, edx; Val
0x1800118c2  mov     rcx, r15; void *
0x1800118c5  call    memset_0
0x1800118ca  xor     r10d, r10d
0x1800118cd  mov     r9d, r10d
0x1800118d0  test    ebx, ebx
0x1800118d2  jle     loc_18001199C
0x1800118d8  mov     eax, r9d
0x1800118db  movzx   edx, word ptr [rdi+rax*2]
0x1800118df  cmp     edx, 61h ; 'a'
0x1800118e2  ja      short loc_18001194F
0x1800118e4  jz      loc_18001196F
0x1800118ea  cmp     edx, 38h ; '8'
0x1800118ed  ja      short loc_180011921
0x1800118ef  jz      short loc_18001191B
0x1800118f1  mov     ecx, edx
0x1800118f3  sub     ecx, 30h ; '0'
0x1800118f6  jz      short loc_18001191B
0x1800118f8  sub     ecx, 1
0x1800118fb  jz      short loc_18001191B
0x1800118fd  sub     ecx, 1
0x180011900  jz      short loc_18001191B
0x180011902  sub     ecx, 1
0x180011905  jz      short loc_18001191B
0x180011907  sub     ecx, 1
0x18001190a  jz      short loc_18001191B
0x18001190c  sub     ecx, 1
0x18001190f  jz      short loc_18001191B
0x180011911  sub     ecx, 1
0x180011914  jz      short loc_18001191B
0x180011916  cmp     ecx, 1
0x180011919  jnz     short loc_18001196A
0x18001191b  lea     r8d, [rdx-30h]
0x18001191f  jmp     short loc_180011973
0x180011921  mov     r8d, edx
0x180011924  mov     ecx, edx
0x180011926  sub     ecx, 39h ; '9'
0x180011929  jz      short loc_18001191B
0x18001192b  sub     ecx, 8
0x18001192e  jz      short loc_180011949
0x180011930  sub     ecx, 1
0x180011933  jz      short loc_180011949
0x180011935  sub     ecx, 1
0x180011938  jz      short loc_180011949
0x18001193a  sub     ecx, 1
0x18001193d  jz      short loc_180011949
0x18001193f  sub     ecx, 1
0x180011942  jz      short loc_180011949
0x180011944  cmp     ecx, 1
0x180011947  jnz     short loc_18001196A
0x180011949  add     r8d, 0FFFFFFC9h
0x18001194d  jmp     short loc_180011973
0x18001194f  mov     ecx, edx
0x180011951  sub     ecx, 62h ; 'b'
0x180011954  jz      short loc_18001196F
0x180011956  sub     ecx, 1
0x180011959  jz      short loc_18001196F
0x18001195b  sub     ecx, 1
0x18001195e  jz      short loc_18001196F
0x180011960  sub     ecx, 1
0x180011963  jz      short loc_18001196F
0x180011965  cmp     ecx, 1
0x180011968  jz      short loc_18001196F
0x18001196a  mov     r8d, r10d
0x18001196d  jmp     short loc_180011973
0x18001196f  lea     r8d, [rdx-57h]
0x180011973  mov     edx, r9d
0x180011976  shr     rdx, 1
0x180011979  mov     eax, r9d
0x18001197c  and     eax, 1
0x18001197f  shl     eax, 2
0x180011982  mov     ecx, 4
0x180011987  sub     ecx, eax
0x180011989  shl     r8b, cl
0x18001198c  or      [rdx+r15], r8b
0x180011990  inc     r9d
0x180011993  cmp     r9d, ebx
0x180011996  jl      loc_1800118D8
0x18001199c  mov     [rsp+0B0h+cbData], r13d; cbData
0x1800119a1  mov     [rsp+0B0h+lpData], r15; lpData
0x1800119a6  mov     r9d, 3; dwType
0x1800119ac  mov     rdx, [rbp+80h+lpValueName]; lpValueName
0x1800119b0  mov     rcx, [rbp+80h+var_68]
0x1800119b4  mov     rcx, [rcx]; hKey
0x1800119b7  xor     r8d, r8d; Reserved
0x1800119ba  call    cs:__imp_RegSetValueExW
0x1800119c0  jmp     loc_180011B4B
0x1800119c5  mov     r13, rdi
0x1800119c8  mov     r14, rcx
0x1800119cb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800119cf  cmp     [rbp+80h+arg_20], cl
0x1800119d5  jz      loc_180011B09
0x1800119db  mov     rax, rbx
0x1800119de  inc     rax
0x1800119e1  cmp     [rdi+rax*2], cx
0x1800119e5  jnz     short loc_1800119DE
0x1800119e7  cmp     eax, 0FFEh
0x1800119ec  jle     short loc_180011A0A
0x1800119ee  mov     rcx, rdi; Block
0x1800119f1  call    cs:__imp_free
0x1800119f7  mov     rcx, rsi; Block
0x1800119fa  call    cs:__imp_free
0x180011a00  mov     ebx, 80004005h
0x180011a05  jmp     loc_180011B70
0x180011a0a  mov     ecx, 2000h; Size
0x180011a0f  call    cs:__imp_malloc
0x180011a15  mov     r14, rax
0x180011a18  xor     eax, eax
0x180011a1a  test    r14, r14
0x180011a1d  jnz     short loc_180011A2D
0x180011a1f  mov     rcx, rdi; Block
0x180011a22  call    cs:__imp_free
0x180011a28  jmp     loc_1800117AB
0x180011a2d  mov     [rbp+80h+var_58], rax
0x180011a31  lea     rdx, aModule; "Module"
0x180011a38  mov     rcx, [r12+8]; this
0x180011a3d  call    ?StrFromMap@CRegObject@ATL@@QEAAPEBGPEAG@Z; ATL::CRegObject::StrFromMap(ushort *)
0x180011a42  mov     r12, rax
0x180011a45  test    rax, rax
0x180011a48  jz      loc_180011AFA
0x180011a4e  mov     rdx, rax; LPCWSTR
0x180011a51  mov     rcx, rdi; lpsz
0x180011a54  call    ?StrStrW@CRegParser@ATL@@KAPEBGPEBG0@Z; ATL::CRegParser::StrStrW(ushort const *,ushort const *)
0x180011a59  mov     r15, rax
0x180011a5c  test    rax, rax
0x180011a5f  jz      loc_180011AF6
0x180011a65  cmp     rax, [rbp+80h+var_60]
0x180011a69  jz      short loc_180011A7D
0x180011a6b  mov     rdx, rax; lpszCurrent
0x180011a6e  mov     rcx, rdi; lpszStart
0x180011a71  call    cs:__imp_CharPrevW
0x180011a77  cmp     word ptr [rax], 22h ; '"'
0x180011a7b  jz      short loc_180011AF6
0x180011a7d  xor     r13d, r13d
0x180011a80  mov     [r14], r13w
0x180011a84  mov     r8, r15
0x180011a87  sub     r8, rdi
0x180011a8a  sar     r8, 1; iMaxLength
0x180011a8d  mov     rdx, rdi; lpString2
0x180011a90  mov     rcx, r14; lpString1
0x180011a93  call    cs:__imp_lstrcpynW
0x180011a99  lea     r8, Source; "\""
0x180011aa0  mov     edx, 1000h; SizeInWords
0x180011aa5  mov     rcx, r14; Destination
0x180011aa8  call    cs:__imp_wcscat_s
0x180011aae  mov     r8, r12; Source
0x180011ab1  mov     edx, 1000h; SizeInWords
0x180011ab6  mov     rcx, r14; Destination
0x180011ab9  call    cs:__imp_wcscat_s
0x180011abf  lea     r8, Source; "\""
0x180011ac6  mov     edx, 1000h; SizeInWords
0x180011acb  mov     rcx, r14; Destination
0x180011ace  call    cs:__imp_wcscat_s
0x180011ad4  mov     rax, rbx
0x180011ad7  inc     rax
0x180011ada  cmp     [r12+rax*2], r13w
0x180011adf  jnz     short loc_180011AD7
0x180011ae1  lea     r8, [r15+rax*2]; Source
0x180011ae5  mov     edx, 1000h; SizeInWords
0x180011aea  mov     rcx, r14; Destination
0x180011aed  call    cs:__imp_wcscat_s
0x180011af3  mov     r13, r14
0x180011af6  mov     r15, [rbp+80h+lpValueName]
0x180011afa  lea     rcx, [rbp+80h+var_58]
0x180011afe  call    ??1?$CAtlSafeAllocBufferManager@V_CCRTAllocator@_ATL_SAFE_ALLOCA_IMPL@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::_ATL_SAFE_ALLOCA_IMPL::_CCRTAllocator>(void)
0x180011b03  mov     r12, [rbp+80h+var_50]
0x180011b07  xor     ecx, ecx
0x180011b09  inc     rbx
0x180011b0c  cmp     [r13+rbx*2+0], cx
0x180011b12  jnz     short loc_180011B09
0x180011b14  lea     eax, ds:2[rbx*2]
0x180011b1b  mov     [rsp+0B0h+cbData], eax; cbData
0x180011b1f  mov     [rsp+0B0h+lpData], r13; lpData
0x180011b24  mov     r9d, 1; dwType
0x180011b2a  xor     r8d, r8d; Reserved
0x180011b2d  mov     rdx, r15; lpValueName
0x180011b30  mov     rcx, [rbp+80h+var_68]
0x180011b34  mov     rcx, [rcx]; hKey
0x180011b37  call    cs:__imp_RegSetValueExW
  ... truncated ...
```
