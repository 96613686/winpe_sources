# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180006dfc`
- end: `0x18000737c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180008e68`

## callees

- `0x180006580`
- `0x180006688`
- `0x18000680c`
- `0x180006dfc`
- `0x180007384`
- `0x180007604`
- `0x180007a3c`
- `0x180008410`
- `0x180009760`
- `0x18002d1d2`
- `0x18002d200`
- `0x18002d2c0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fd5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fb9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006fd5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000703e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800070d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800072cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007326`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000703e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800070d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800072cf`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180007326`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e97`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006e97`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000708a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000708a`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
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
  unsigned __int16 *v43; // [rsp+80h] [rbp-2168h]
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
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
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
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
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
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
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
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
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
0x180006dfc  push    rbx
0x180006dfe  push    rsi
0x180006dff  push    rdi
0x180006e00  push    r12
0x180006e02  push    r13
0x180006e04  push    r14
0x180006e06  push    r15
0x180006e08  mov     eax, 21B0h
0x180006e0d  call    _alloca_probe
0x180006e12  sub     rsp, rax
0x180006e15  mov     rax, cs:__security_cookie
0x180006e1c  xor     rax, rsp
0x180006e1f  mov     [rsp+21E8h+var_48], rax
0x180006e27  mov     r14, r8
0x180006e2a  mov     [rsp+21E8h+lpValueName], r8
0x180006e2f  mov     r12, rdx
0x180006e32  mov     [rsp+21E8h+var_2198], rdx
0x180006e37  mov     r15, rcx
0x180006e3a  mov     [rsp+21E8h+var_21B0], rcx
0x180006e3f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180006e44  mov     [rsp+21E8h+var_2190], rcx
0x180006e49  mov     [rsp+21E8h+var_2170], rdx
0x180006e4e  mov     [rsp+21E8h+var_2188], r8
0x180006e53  mov     [rsp+21E8h+var_2168], r9
0x180006e5b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180006e63  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006e68  xor     ebx, ebx
0x180006e6a  test    eax, eax
0x180006e6c  js      loc_180007359
0x180006e72  mov     edi, ebx
0x180006e74  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180006e7b  cmp     edi, 4
0x180006e7e  jnb     loc_180007354
0x180006e84  movsxd  rsi, edi
0x180006e87  add     rsi, rsi
0x180006e8a  mov     rdx, [r13+rsi*8+0]; lpString2
0x180006e8f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180006e97  call    cs:__imp_lstrcmpiW
0x180006e9d  test    eax, eax
0x180006e9f  jz      short loc_180006EA5
0x180006ea1  inc     edi
0x180006ea3  jmp     short loc_180006E7B
0x180006ea5  movzx   edi, word ptr [r13+rsi*8+8]
0x180006eab  mov     rcx, r15; this
0x180006eae  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180006eb3  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180006ebb  mov     rcx, r15; this
0x180006ebe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006ec3  test    eax, eax
0x180006ec5  js      loc_180007359
0x180006ecb  mov     r13d, 8
0x180006ed1  cmp     di, r13w
0x180006ed5  jz      loc_1800072E9
0x180006edb  cmp     di, 11h
0x180006edf  jz      loc_1800070E8
0x180006ee5  cmp     di, 13h
0x180006ee9  jz      loc_18000706F
0x180006eef  mov     eax, 4008h
0x180006ef4  cmp     di, ax
0x180006ef7  jnz     loc_18000733B
0x180006efd  lea     rcx, [rsp+21E8h+String1]
0x180006f05  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006f09  mov     rax, rsi
0x180006f0c  inc     rax
0x180006f0f  cmp     [rcx+rax*2], bx
0x180006f13  jnz     short loc_180006F0C
0x180006f15  add     eax, 2
0x180006f18  mov     [rsp+21E8h+var_2158], rbx
0x180006f20  movsxd  rcx, eax
0x180006f23  mov     r15d, 2
0x180006f29  mov     edx, r15d
0x180006f2c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180006f31  cmp     rax, 100h
0x180006f37  jbe     short loc_180006F53
0x180006f39  mov     rdx, rax
0x180006f3c  lea     rcx, [rsp+21E8h+var_2158]
0x180006f44  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006f49  mov     rdi, [rsp+21E8h+var_2158]
0x180006f51  jmp     short loc_180006F63
0x180006f53  lea     rdi, [rsp+21E8h+var_2150]
0x180006f5b  mov     [rsp+21E8h+var_2158], rdi
0x180006f63  mov     r13, [rsp+21E8h+var_2198]
0x180006f68  jmp     short loc_180006F95
0x180006f6a  xor     ebx, ebx
0x180006f6c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006f70  lea     r15d, [rbx+2]
0x180006f74  mov     rdi, [rsp+21E8h+var_2158]
0x180006f7c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180006f81  mov     rax, [rsp+21E8h+var_2190]
0x180006f86  mov     [rsp+21E8h+var_21B0], rax
0x180006f8b  mov     rax, [rsp+21E8h+var_2188]
0x180006f90  mov     [rsp+21E8h+lpValueName], rax
0x180006f95  test    rdi, rdi
0x180006f98  jz      loc_180007053
0x180006f9e  lea     r14, [rsp+21E8h+String1]
0x180006fa6  cmp     [rsp+21E8h+String1], bx
0x180006fae  jz      short loc_180006FEF
0x180006fb0  mov     r12d, 30h ; '0'
0x180006fb6  mov     rcx, r14; lpsz
0x180006fb9  call    cs:__imp_CharNextW
0x180006fbf  movzx   ecx, word ptr [r14]
0x180006fc3  cmp     cx, 5Ch ; '\'
0x180006fc7  jnz     short loc_180006FE0
0x180006fc9  cmp     [rax], r12w
0x180006fcd  jnz     short loc_180006FE0
0x180006fcf  mov     [rdi], bx
0x180006fd2  mov     rcx, rax; lpsz
0x180006fd5  call    cs:__imp_CharNextW
0x180006fdb  mov     r14, rax
0x180006fde  jmp     short loc_180006FE6
0x180006fe0  mov     [rdi], cx
0x180006fe3  add     r14, r15
0x180006fe6  add     rdi, r15
0x180006fe9  cmp     [r14], bx
0x180006fed  jnz     short loc_180006FB6
0x180006fef  mov     dword ptr [rdi], 0
0x180006ff5  mov     r8, [rsp+21E8h+var_2158]
0x180006ffd  test    r8, r8
0x180007000  jz      short loc_180007048
0x180007002  mov     r10d, ebx
0x180007005  mov     r9, r8
0x180007008  mov     rcx, rsi
0x18000700b  inc     rcx
0x18000700e  cmp     [r9+rcx*2], bx
0x180007013  jnz     short loc_18000700B
0x180007015  inc     ecx
0x180007017  lea     r9, [r9+rcx*2]
0x18000701b  lea     r10d, [r10+rcx*2]
0x18000701f  cmp     ecx, 1
0x180007022  jnz     short loc_180007008
0x180007024  mov     [rsp+21E8h+cbData], r10d; cbData
0x180007029  mov     [rsp+21E8h+lpData], r8; lpData
0x18000702e  lea     r9d, [rcx+6]; dwType
0x180007032  xor     r8d, r8d; Reserved
0x180007035  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18000703a  mov     rcx, [r13+0]; hKey
0x18000703e  call    cs:__imp_RegSetValueExW
0x180007044  mov     edi, eax
0x180007046  jmp     short loc_180007058
0x180007048  mov     ecx, 80004005h; int
0x18000704d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180007053  mov     edi, 0Eh
0x180007058  lea     rcx, [rsp+21E8h+var_2158]
0x180007060  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180007065  mov     r15, [rsp+21E8h+var_21B0]
0x18000706a  jmp     loc_18000732E
0x18000706f  mov     [rsp+21E8h+pulOut], ebx
0x180007073  mov     [rsp+21E8h+var_21B0], rbx
0x180007078  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000707d  xor     r8d, r8d; dwFlags
0x180007080  xor     edx, edx; lcid
0x180007082  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000708a  call    cs:__imp_VarUI4FromStr
0x180007090  mov     edi, eax
0x180007092  test    eax, eax
0x180007094  jns     short loc_1800070A7
0x180007096  lea     rcx, [rsp+21E8h+var_21B0]
0x18000709b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800070a0  mov     eax, edi
0x1800070a2  jmp     loc_180007359
0x1800070a7  mov     eax, [rsp+21E8h+pulOut]
0x1800070ab  mov     dword ptr [rsp+21E8h+Data], eax
0x1800070af  mov     [rsp+21E8h+cbData], 4; cbData
0x1800070b7  lea     rax, [rsp+21E8h+Data]
0x1800070bc  mov     [rsp+21E8h+lpData], rax; lpData
0x1800070c1  mov     r9d, 4; dwType
0x1800070c7  xor     r8d, r8d; Reserved
0x1800070ca  mov     rdx, r14; lpValueName
0x1800070cd  mov     rcx, [r12]; hKey
0x1800070d1  call    cs:__imp_RegSetValueExW
0x1800070d7  mov     edi, eax
0x1800070d9  lea     rcx, [rsp+21E8h+var_21B0]
0x1800070de  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800070e3  jmp     loc_18000732E
0x1800070e8  lea     rax, [rsp+21E8h+String1]
0x1800070f0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800070f4  inc     rsi
0x1800070f7  cmp     [rax+rsi*2], bx
0x1800070fb  jnz     short loc_1800070F4
0x1800070fd  mov     dword ptr [rsp+21E8h+Data], esi
0x180007101  test    sil, 1
0x180007105  jz      short loc_180007111
0x180007107  mov     eax, 80004005h
0x18000710c  jmp     loc_180007359
0x180007111  mov     eax, esi
0x180007113  cdq
0x180007114  mov     r15d, 2
0x18000711a  idiv    r15d
0x18000711d  movsxd  r14, eax
0x180007120  mov     [rsp+21E8h+var_2158], rbx
0x180007128  mov     rdi, r14
0x18000712b  mov     [rsp+21E8h+var_2178], r14
0x180007130  lea     edx, [r15-1]
0x180007134  mov     rcx, r14
0x180007137  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000713c  cmp     rax, 100h
0x180007142  jbe     short loc_18000715E
0x180007144  mov     rdx, rax
0x180007147  lea     rcx, [rsp+21E8h+var_2158]
0x18000714f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180007154  mov     rcx, [rsp+21E8h+var_2158]
0x18000715c  jmp     short loc_18000716E
0x18000715e  lea     rcx, [rsp+21E8h+var_2150]
0x180007166  mov     [rsp+21E8h+var_2158], rcx
0x18000716e  mov     r15, [rsp+21E8h+var_2198]
0x180007173  jmp     short loc_1800071A8
0x180007175  xor     ebx, ebx
0x180007177  lea     r13d, [rbx+8]
0x18000717b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18000717f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180007187  mov     rdi, [rsp+21E8h+var_2178]
0x18000718c  mov     rax, [rsp+21E8h+var_2190]
0x180007191  mov     [rsp+21E8h+var_21B0], rax
0x180007196  mov     r15, [rsp+21E8h+var_2170]
0x18000719b  mov     rax, [rsp+21E8h+var_2188]
0x1800071a0  mov     [rsp+21E8h+lpValueName], rax
0x1800071a5  mov     r14d, edi
0x1800071a8  test    rcx, rcx
0x1800071ab  jnz     short loc_1800071BF
0x1800071ad  lea     rcx, [rsp+21E8h+var_2158]
0x1800071b5  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800071ba  jmp     loc_180007107
0x1800071bf  mov     r8, rdi; Size
0x1800071c2  xor     edx, edx; Val
0x1800071c4  call    memset_0
0x1800071c9  mov     r10d, ebx
0x1800071cc  test    esi, esi
0x1800071ce  jle     loc_1800072AC
0x1800071d4  mov     r12d, 30h ; '0'
0x1800071da  mov     eax, r10d
0x1800071dd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x1800071e5  cmp     edx, 61h ; 'a'
0x1800071e8  ja      short loc_180007257
0x1800071ea  jz      loc_180007277
0x1800071f0  cmp     edx, 38h ; '8'
0x1800071f3  ja      short loc_180007229
0x1800071f5  jz      short loc_180007221
0x1800071f7  mov     ecx, edx
0x1800071f9  sub     ecx, r12d
0x1800071fc  jz      short loc_180007221
0x1800071fe  sub     ecx, 1
0x180007201  jz      short loc_180007221
0x180007203  sub     ecx, 1
0x180007206  jz      short loc_180007221
0x180007208  sub     ecx, 1
0x18000720b  jz      short loc_180007221
0x18000720d  sub     ecx, 1
0x180007210  jz      short loc_180007221
0x180007212  sub     ecx, 1
0x180007215  jz      short loc_180007221
0x180007217  sub     ecx, 1
0x18000721a  jz      short loc_180007221
0x18000721c  cmp     ecx, 1
0x18000721f  jnz     short loc_180007272
0x180007221  mov     r9d, edx
0x180007224  sub     r9d, r12d
0x180007227  jmp     short loc_18000727B
0x180007229  mov     r9d, edx
0x18000722c  mov     ecx, edx
0x18000722e  sub     ecx, 39h ; '9'
0x180007231  jz      short loc_180007221
0x180007233  sub     ecx, r13d
0x180007236  jz      short loc_180007251
0x180007238  sub     ecx, 1
0x18000723b  jz      short loc_180007251
0x18000723d  sub     ecx, 1
0x180007240  jz      short loc_180007251
0x180007242  sub     ecx, 1
0x180007245  jz      short loc_180007251
0x180007247  sub     ecx, 1
0x18000724a  jz      short loc_180007251
0x18000724c  cmp     ecx, 1
0x18000724f  jnz     short loc_180007272
0x180007251  add     r9d, 0FFFFFFC9h
0x180007255  jmp     short loc_18000727B
0x180007257  mov     ecx, edx
0x180007259  sub     ecx, 62h ; 'b'
0x18000725c  jz      short loc_180007277
0x18000725e  sub     ecx, 1
0x180007261  jz      short loc_180007277
0x180007263  sub     ecx, 1
0x180007266  jz      short loc_180007277
0x180007268  sub     ecx, 1
0x18000726b  jz      short loc_180007277
0x18000726d  cmp     ecx, 1
0x180007270  jz      short loc_180007277
0x180007272  mov     r9d, ebx
0x180007275  jmp     short loc_18000727B
0x180007277  lea     r9d, [rdx-57h]
0x18000727b  mov     r8d, r10d
0x18000727e  shr     r8, 1
0x180007281  mov     rdx, [rsp+21E8h+var_2158]
0x180007289  mov     eax, r10d
0x18000728c  and     eax, 1
0x18000728f  shl     eax, 2
0x180007292  mov     ecx, 4
0x180007297  sub     ecx, eax
0x180007299  shl     r9b, cl
0x18000729c  or      [r8+rdx], r9b
0x1800072a0  inc     r10d
  ... truncated ...
```
