# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x180016dfc`
- end: `0x18001737c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001a7d4`

## callees

- `0x18000fcd0`
- `0x180010b2c`
- `0x180016554`
- `0x180016634`
- `0x180016734`
- `0x180016dfc`
- `0x180017384`
- `0x180017658`
- `0x1800179b4`
- `0x180019a40`
- `0x18001b960`
- `0x180024dc0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001708a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001708a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016fb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016fd5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016fb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180016fd5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001703e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800170d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017326`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001703e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800170d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800172cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017326`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016e97`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180016e97`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(ATL::CRegParser *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
{
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  HKEY *v14; // r13
  WCHAR *j; // r14
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // edi
  HRESULT v22; // edi
  __int64 v23; // rsi
  DWORD v24; // r14d
  size_t v25; // rdi
  unsigned __int64 v26; // rax
  BYTE *v27; // rcx
  HKEY *v28; // r15
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21B0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21A8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-21A0h]
  HKEY *v38; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v39; // [rsp+58h] [rbp-2190h]
  const WCHAR *v40; // [rsp+60h] [rbp-2188h]
  size_t v41; // [rsp+70h] [rbp-2178h]
  HKEY *v42; // [rsp+78h] [rbp-2170h]
  wchar_t *v43; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v38 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v39 = this;
  v42 = a2;
  v40 = a3;
  v43 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result < 0 )
    return result;
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
      return 2147614729LL;
    if ( !lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * (int)i]) )
      break;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * (int)i + 4);
  ATL::CRegParser::SkipWhiteSpace(v6);
  result = ATL::CRegParser::NextToken(v6, String1);
  if ( (int)result < 0 )
    return result;
  switch ( v10 )
  {
    case 8:
      v32 = -1;
      do
        ++v32;
      while ( String1[v32] );
      v21 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      goto LABEL_80;
    case 17:
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      *(_DWORD *)Data = v23;
      if ( (v23 & 1) != 0 )
        return 2147500037LL;
      v24 = (int)v23 / 2;
      lpData = 0;
      v25 = (int)v23 / 2;
      v41 = v25;
      try
      {
        v26 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v26 <= 0x100 )
        {
          v27 = v45;
          lpData = v45;
        }
        else
        {
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
          v27 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v23) = *(_DWORD *)Data;
        v27 = lpData;
        v25 = v41;
        v35 = v39;
        v28 = v42;
        lpValueName = v40;
        v24 = v41;
        goto LABEL_47;
      }
      v28 = v38;
LABEL_47:
      if ( !v27 )
      {
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_34;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_74:
            v31 = v30 - 87;
            goto LABEL_75;
          }
LABEL_73:
          v31 = 0;
          goto LABEL_75;
        }
        if ( v30 == 97 )
          goto LABEL_74;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_61;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_73;
        v31 = v30 - 55;
LABEL_75:
        lpData[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v23 )
          goto LABEL_76;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_73;
LABEL_61:
      v31 = v30 - 48;
      goto LABEL_75;
    case 19:
      pulOut = 0;
      v35 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
      return (unsigned int)v22;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      lpData = 0;
      try
      {
        v12 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v12 <= 0x100 )
        {
          v13 = v45;
          lpData = v45;
        }
        else
        {
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
          v13 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v13 = lpData;
        v14 = *(HKEY **)Data;
        v35 = v39;
        lpValueName = v40;
        goto LABEL_18;
      }
      v14 = v38;
LABEL_18:
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v16 = CharNextW(j);
          if ( *j == 92 && *v16 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v16);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v18 = lpData;
        do
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)&v18[2 * v19] );
          v20 = (unsigned int)(v19 + 1);
          v18 += 2 * v20;
          cbData += 2 * v20;
        }
        while ( (_DWORD)v20 != 1 );
        v21 = RegSetValueExW(*v14, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v35;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v43);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_82;
  }
}

```

## disassembly

```asm
0x180016dfc  push    rbx
0x180016dfe  push    rsi
0x180016dff  push    rdi
0x180016e00  push    r12
0x180016e02  push    r13
0x180016e04  push    r14
0x180016e06  push    r15
0x180016e08  mov     eax, 21B0h
0x180016e0d  call    _alloca_probe
0x180016e12  sub     rsp, rax
0x180016e15  mov     rax, cs:__security_cookie
0x180016e1c  xor     rax, rsp
0x180016e1f  mov     [rsp+21E8h+var_48], rax
0x180016e27  mov     r14, r8
0x180016e2a  mov     [rsp+21E8h+lpValueName], r8
0x180016e2f  mov     r12, rdx
0x180016e32  mov     [rsp+21E8h+var_2198], rdx
0x180016e37  mov     r15, rcx
0x180016e3a  mov     [rsp+21E8h+var_21B0], rcx
0x180016e3f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180016e44  mov     [rsp+21E8h+var_2190], rcx
0x180016e49  mov     [rsp+21E8h+var_2170], rdx
0x180016e4e  mov     [rsp+21E8h+var_2188], r8
0x180016e53  mov     [rsp+21E8h+var_2168], r9
0x180016e5b  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x180016e63  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180016e68  xor     ebx, ebx
0x180016e6a  test    eax, eax
0x180016e6c  js      loc_180017359
0x180016e72  mov     edi, ebx
0x180016e74  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x180016e7b  cmp     edi, 4
0x180016e7e  jnb     loc_180017354
0x180016e84  movsxd  rsi, edi
0x180016e87  add     rsi, rsi
0x180016e8a  mov     rdx, [r13+rsi*8+0]; lpString2
0x180016e8f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180016e97  call    cs:__imp_lstrcmpiW
0x180016e9d  test    eax, eax
0x180016e9f  jz      short loc_180016EA5
0x180016ea1  inc     edi
0x180016ea3  jmp     short loc_180016E7B
0x180016ea5  movzx   edi, word ptr [r13+rsi*8+8]
0x180016eab  mov     rcx, r15; this
0x180016eae  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180016eb3  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x180016ebb  mov     rcx, r15; this
0x180016ebe  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x180016ec3  test    eax, eax
0x180016ec5  js      loc_180017359
0x180016ecb  mov     r13d, 8
0x180016ed1  cmp     di, r13w
0x180016ed5  jz      loc_1800172E9
0x180016edb  cmp     di, 11h
0x180016edf  jz      loc_1800170E8
0x180016ee5  cmp     di, 13h
0x180016ee9  jz      loc_18001706F
0x180016eef  mov     eax, 4008h
0x180016ef4  cmp     di, ax
0x180016ef7  jnz     loc_18001733B
0x180016efd  lea     rcx, [rsp+21E8h+String1]
0x180016f05  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016f09  mov     rax, rsi
0x180016f0c  inc     rax
0x180016f0f  cmp     [rcx+rax*2], bx
0x180016f13  jnz     short loc_180016F0C
0x180016f15  add     eax, 2
0x180016f18  mov     [rsp+21E8h+var_2158], rbx
0x180016f20  movsxd  rcx, eax
0x180016f23  mov     r15d, 2
0x180016f29  mov     edx, r15d
0x180016f2c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180016f31  cmp     rax, 100h
0x180016f37  jbe     short loc_180016F53
0x180016f39  mov     rdx, rax
0x180016f3c  lea     rcx, [rsp+21E8h+var_2158]
0x180016f44  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180016f49  mov     rdi, [rsp+21E8h+var_2158]
0x180016f51  jmp     short loc_180016F63
0x180016f53  lea     rdi, [rsp+21E8h+var_2150]
0x180016f5b  mov     [rsp+21E8h+var_2158], rdi
0x180016f63  mov     r13, [rsp+21E8h+var_2198]
0x180016f68  jmp     short loc_180016F95
0x180016f6a  xor     ebx, ebx
0x180016f6c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180016f70  lea     r15d, [rbx+2]
0x180016f74  mov     rdi, [rsp+21E8h+var_2158]
0x180016f7c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180016f81  mov     rax, [rsp+21E8h+var_2190]
0x180016f86  mov     [rsp+21E8h+var_21B0], rax
0x180016f8b  mov     rax, [rsp+21E8h+var_2188]
0x180016f90  mov     [rsp+21E8h+lpValueName], rax
0x180016f95  test    rdi, rdi
0x180016f98  jz      loc_180017053
0x180016f9e  lea     r14, [rsp+21E8h+String1]
0x180016fa6  cmp     [rsp+21E8h+String1], bx
0x180016fae  jz      short loc_180016FEF
0x180016fb0  mov     r12d, 30h ; '0'
0x180016fb6  mov     rcx, r14; lpsz
0x180016fb9  call    cs:__imp_CharNextW
0x180016fbf  movzx   ecx, word ptr [r14]
0x180016fc3  cmp     cx, 5Ch ; '\'
0x180016fc7  jnz     short loc_180016FE0
0x180016fc9  cmp     [rax], r12w
0x180016fcd  jnz     short loc_180016FE0
0x180016fcf  mov     [rdi], bx
0x180016fd2  mov     rcx, rax; lpsz
0x180016fd5  call    cs:__imp_CharNextW
0x180016fdb  mov     r14, rax
0x180016fde  jmp     short loc_180016FE6
0x180016fe0  mov     [rdi], cx
0x180016fe3  add     r14, r15
0x180016fe6  add     rdi, r15
0x180016fe9  cmp     [r14], bx
0x180016fed  jnz     short loc_180016FB6
0x180016fef  mov     dword ptr [rdi], 0
0x180016ff5  mov     r8, [rsp+21E8h+var_2158]
0x180016ffd  test    r8, r8
0x180017000  jz      short loc_180017048
0x180017002  mov     r10d, ebx
0x180017005  mov     r9, r8
0x180017008  mov     rcx, rsi
0x18001700b  inc     rcx
0x18001700e  cmp     [r9+rcx*2], bx
0x180017013  jnz     short loc_18001700B
0x180017015  inc     ecx
0x180017017  lea     r9, [r9+rcx*2]
0x18001701b  lea     r10d, [r10+rcx*2]
0x18001701f  cmp     ecx, 1
0x180017022  jnz     short loc_180017008
0x180017024  mov     [rsp+21E8h+cbData], r10d; cbData
0x180017029  mov     [rsp+21E8h+lpData], r8; lpData
0x18001702e  lea     r9d, [rcx+6]; dwType
0x180017032  xor     r8d, r8d; Reserved
0x180017035  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18001703a  mov     rcx, [r13+0]; hKey
0x18001703e  call    cs:__imp_RegSetValueExW
0x180017044  mov     edi, eax
0x180017046  jmp     short loc_180017058
0x180017048  mov     ecx, 80004005h; int
0x18001704d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017053  mov     edi, 0Eh
0x180017058  lea     rcx, [rsp+21E8h+var_2158]
0x180017060  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x180017065  mov     r15, [rsp+21E8h+var_21B0]
0x18001706a  jmp     loc_18001732E
0x18001706f  mov     [rsp+21E8h+pulOut], ebx
0x180017073  mov     [rsp+21E8h+var_21B0], rbx
0x180017078  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18001707d  xor     r8d, r8d; dwFlags
0x180017080  xor     edx, edx; lcid
0x180017082  lea     rcx, [rsp+21E8h+String1]; strIn
0x18001708a  call    cs:__imp_VarUI4FromStr
0x180017090  mov     edi, eax
0x180017092  test    eax, eax
0x180017094  jns     short loc_1800170A7
0x180017096  lea     rcx, [rsp+21E8h+var_21B0]
0x18001709b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800170a0  mov     eax, edi
0x1800170a2  jmp     loc_180017359
0x1800170a7  mov     eax, [rsp+21E8h+pulOut]
0x1800170ab  mov     dword ptr [rsp+21E8h+Data], eax
0x1800170af  mov     [rsp+21E8h+cbData], 4; cbData
0x1800170b7  lea     rax, [rsp+21E8h+Data]
0x1800170bc  mov     [rsp+21E8h+lpData], rax; lpData
0x1800170c1  mov     r9d, 4; dwType
0x1800170c7  xor     r8d, r8d; Reserved
0x1800170ca  mov     rdx, r14; lpValueName
0x1800170cd  mov     rcx, [r12]; hKey
0x1800170d1  call    cs:__imp_RegSetValueExW
0x1800170d7  mov     edi, eax
0x1800170d9  lea     rcx, [rsp+21E8h+var_21B0]
0x1800170de  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800170e3  jmp     loc_18001732E
0x1800170e8  lea     rax, [rsp+21E8h+String1]
0x1800170f0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800170f4  inc     rsi
0x1800170f7  cmp     [rax+rsi*2], bx
0x1800170fb  jnz     short loc_1800170F4
0x1800170fd  mov     dword ptr [rsp+21E8h+Data], esi
0x180017101  test    sil, 1
0x180017105  jz      short loc_180017111
0x180017107  mov     eax, 80004005h
0x18001710c  jmp     loc_180017359
0x180017111  mov     eax, esi
0x180017113  cdq
0x180017114  mov     r15d, 2
0x18001711a  idiv    r15d
0x18001711d  movsxd  r14, eax
0x180017120  mov     [rsp+21E8h+var_2158], rbx
0x180017128  mov     rdi, r14
0x18001712b  mov     [rsp+21E8h+var_2178], r14
0x180017130  lea     edx, [r15-1]
0x180017134  mov     rcx, r14
0x180017137  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001713c  cmp     rax, 100h
0x180017142  jbe     short loc_18001715E
0x180017144  mov     rdx, rax
0x180017147  lea     rcx, [rsp+21E8h+var_2158]
0x18001714f  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180017154  mov     rcx, [rsp+21E8h+var_2158]
0x18001715c  jmp     short loc_18001716E
0x18001715e  lea     rcx, [rsp+21E8h+var_2150]
0x180017166  mov     [rsp+21E8h+var_2158], rcx
0x18001716e  mov     r15, [rsp+21E8h+var_2198]
0x180017173  jmp     short loc_1800171A8
0x180017175  xor     ebx, ebx
0x180017177  lea     r13d, [rbx+8]
0x18001717b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18001717f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180017187  mov     rdi, [rsp+21E8h+var_2178]
0x18001718c  mov     rax, [rsp+21E8h+var_2190]
0x180017191  mov     [rsp+21E8h+var_21B0], rax
0x180017196  mov     r15, [rsp+21E8h+var_2170]
0x18001719b  mov     rax, [rsp+21E8h+var_2188]
0x1800171a0  mov     [rsp+21E8h+lpValueName], rax
0x1800171a5  mov     r14d, edi
0x1800171a8  test    rcx, rcx
0x1800171ab  jnz     short loc_1800171BF
0x1800171ad  lea     rcx, [rsp+21E8h+var_2158]
0x1800171b5  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x1800171ba  jmp     loc_180017107
0x1800171bf  mov     r8, rdi; Size
0x1800171c2  xor     edx, edx; Val
0x1800171c4  call    memset_0
0x1800171c9  mov     r10d, ebx
0x1800171cc  test    esi, esi
0x1800171ce  jle     loc_1800172AC
0x1800171d4  mov     r12d, 30h ; '0'
0x1800171da  mov     eax, r10d
0x1800171dd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x1800171e5  cmp     edx, 61h ; 'a'
0x1800171e8  ja      short loc_180017257
0x1800171ea  jz      loc_180017277
0x1800171f0  cmp     edx, 38h ; '8'
0x1800171f3  ja      short loc_180017229
0x1800171f5  jz      short loc_180017221
0x1800171f7  mov     ecx, edx
0x1800171f9  sub     ecx, r12d
0x1800171fc  jz      short loc_180017221
0x1800171fe  sub     ecx, 1
0x180017201  jz      short loc_180017221
0x180017203  sub     ecx, 1
0x180017206  jz      short loc_180017221
0x180017208  sub     ecx, 1
0x18001720b  jz      short loc_180017221
0x18001720d  sub     ecx, 1
0x180017210  jz      short loc_180017221
0x180017212  sub     ecx, 1
0x180017215  jz      short loc_180017221
0x180017217  sub     ecx, 1
0x18001721a  jz      short loc_180017221
0x18001721c  cmp     ecx, 1
0x18001721f  jnz     short loc_180017272
0x180017221  mov     r9d, edx
0x180017224  sub     r9d, r12d
0x180017227  jmp     short loc_18001727B
0x180017229  mov     r9d, edx
0x18001722c  mov     ecx, edx
0x18001722e  sub     ecx, 39h ; '9'
0x180017231  jz      short loc_180017221
0x180017233  sub     ecx, r13d
0x180017236  jz      short loc_180017251
0x180017238  sub     ecx, 1
0x18001723b  jz      short loc_180017251
0x18001723d  sub     ecx, 1
0x180017240  jz      short loc_180017251
0x180017242  sub     ecx, 1
0x180017245  jz      short loc_180017251
0x180017247  sub     ecx, 1
0x18001724a  jz      short loc_180017251
0x18001724c  cmp     ecx, 1
0x18001724f  jnz     short loc_180017272
0x180017251  add     r9d, 0FFFFFFC9h
0x180017255  jmp     short loc_18001727B
0x180017257  mov     ecx, edx
0x180017259  sub     ecx, 62h ; 'b'
0x18001725c  jz      short loc_180017277
0x18001725e  sub     ecx, 1
0x180017261  jz      short loc_180017277
0x180017263  sub     ecx, 1
0x180017266  jz      short loc_180017277
0x180017268  sub     ecx, 1
0x18001726b  jz      short loc_180017277
0x18001726d  cmp     ecx, 1
0x180017270  jz      short loc_180017277
0x180017272  mov     r9d, ebx
0x180017275  jmp     short loc_18001727B
0x180017277  lea     r9d, [rdx-57h]
0x18001727b  mov     r8d, r10d
0x18001727e  shr     r8, 1
0x180017281  mov     rdx, [rsp+21E8h+var_2158]
0x180017289  mov     eax, r10d
0x18001728c  and     eax, 1
0x18001728f  shl     eax, 2
0x180017292  mov     ecx, 4
0x180017297  sub     ecx, eax
0x180017299  shl     r9b, cl
0x18001729c  or      [r8+rdx], r9b
0x1800172a0  inc     r10d
  ... truncated ...
```
