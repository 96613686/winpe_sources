# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18000e89c`
- end: `0x18000ee1c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000fea0`

## callees

- `0x180002a90`
- `0x18000343c`
- `0x18000e390`
- `0x18000e43c`
- `0x18000e46c`
- `0x18000e89c`
- `0x18000ee24`
- `0x18000f064`
- `0x18000f07c`
- `0x18000f5e4`
- `0x180010568`
- `0x180033d00`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000eade`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000eb71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ed6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000edc6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000eade`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000eb71`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000ed6f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000edc6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ea59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ea75`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ea59`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000ea75`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e937`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000e937`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000eb2a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000eb2a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
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
0x18000e89c  push    rbx
0x18000e89e  push    rsi
0x18000e89f  push    rdi
0x18000e8a0  push    r12
0x18000e8a2  push    r13
0x18000e8a4  push    r14
0x18000e8a6  push    r15
0x18000e8a8  mov     eax, 21B0h
0x18000e8ad  call    _alloca_probe
0x18000e8b2  sub     rsp, rax
0x18000e8b5  mov     rax, cs:__security_cookie
0x18000e8bc  xor     rax, rsp
0x18000e8bf  mov     [rsp+21E8h+var_48], rax
0x18000e8c7  mov     r14, r8
0x18000e8ca  mov     [rsp+21E8h+lpValueName], r8
0x18000e8cf  mov     r12, rdx
0x18000e8d2  mov     [rsp+21E8h+var_2198], rdx
0x18000e8d7  mov     r15, rcx
0x18000e8da  mov     [rsp+21E8h+var_21B0], rcx
0x18000e8df  mov     qword ptr [rsp+21E8h+Data], rdx
0x18000e8e4  mov     [rsp+21E8h+var_2190], rcx
0x18000e8e9  mov     [rsp+21E8h+var_2170], rdx
0x18000e8ee  mov     [rsp+21E8h+var_2188], r8
0x18000e8f3  mov     [rsp+21E8h+var_2168], r9
0x18000e8fb  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x18000e903  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000e908  xor     ebx, ebx
0x18000e90a  test    eax, eax
0x18000e90c  js      loc_18000EDF9
0x18000e912  mov     edi, ebx
0x18000e914  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000e91b  cmp     edi, 4
0x18000e91e  jnb     loc_18000EDF4
0x18000e924  movsxd  rsi, edi
0x18000e927  add     rsi, rsi
0x18000e92a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000e92f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18000e937  call    cs:__imp_lstrcmpiW
0x18000e93d  test    eax, eax
0x18000e93f  jz      short loc_18000E945
0x18000e941  inc     edi
0x18000e943  jmp     short loc_18000E91B
0x18000e945  movzx   edi, word ptr [r13+rsi*8+8]
0x18000e94b  mov     rcx, r15; this
0x18000e94e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000e953  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x18000e95b  mov     rcx, r15; this
0x18000e95e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000e963  test    eax, eax
0x18000e965  js      loc_18000EDF9
0x18000e96b  mov     r13d, 8
0x18000e971  cmp     di, r13w
0x18000e975  jz      loc_18000ED89
0x18000e97b  cmp     di, 11h
0x18000e97f  jz      loc_18000EB88
0x18000e985  cmp     di, 13h
0x18000e989  jz      loc_18000EB0F
0x18000e98f  mov     eax, 4008h
0x18000e994  cmp     di, ax
0x18000e997  jnz     loc_18000EDDB
0x18000e99d  lea     rcx, [rsp+21E8h+String1]
0x18000e9a5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e9a9  mov     rax, rsi
0x18000e9ac  inc     rax
0x18000e9af  cmp     [rcx+rax*2], bx
0x18000e9b3  jnz     short loc_18000E9AC
0x18000e9b5  add     eax, 2
0x18000e9b8  mov     [rsp+21E8h+var_2158], rbx
0x18000e9c0  movsxd  rcx, eax
0x18000e9c3  mov     r15d, 2
0x18000e9c9  mov     edx, r15d
0x18000e9cc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000e9d1  cmp     rax, 100h
0x18000e9d7  jbe     short loc_18000E9F3
0x18000e9d9  mov     rdx, rax
0x18000e9dc  lea     rcx, [rsp+21E8h+var_2158]
0x18000e9e4  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000e9e9  mov     rdi, [rsp+21E8h+var_2158]
0x18000e9f1  jmp     short loc_18000EA03
0x18000e9f3  lea     rdi, [rsp+21E8h+var_2150]
0x18000e9fb  mov     [rsp+21E8h+var_2158], rdi
0x18000ea03  mov     r13, [rsp+21E8h+var_2198]
0x18000ea08  jmp     short loc_18000EA35
0x18000ea0a  xor     ebx, ebx
0x18000ea0c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000ea10  lea     r15d, [rbx+2]
0x18000ea14  mov     rdi, [rsp+21E8h+var_2158]
0x18000ea1c  mov     r13, qword ptr [rsp+21E8h+Data]
0x18000ea21  mov     rax, [rsp+21E8h+var_2190]
0x18000ea26  mov     [rsp+21E8h+var_21B0], rax
0x18000ea2b  mov     rax, [rsp+21E8h+var_2188]
0x18000ea30  mov     [rsp+21E8h+lpValueName], rax
0x18000ea35  test    rdi, rdi
0x18000ea38  jz      loc_18000EAF3
0x18000ea3e  lea     r14, [rsp+21E8h+String1]
0x18000ea46  cmp     [rsp+21E8h+String1], bx
0x18000ea4e  jz      short loc_18000EA8F
0x18000ea50  mov     r12d, 30h ; '0'
0x18000ea56  mov     rcx, r14; lpsz
0x18000ea59  call    cs:__imp_CharNextW
0x18000ea5f  movzx   ecx, word ptr [r14]
0x18000ea63  cmp     cx, 5Ch ; '\'
0x18000ea67  jnz     short loc_18000EA80
0x18000ea69  cmp     [rax], r12w
0x18000ea6d  jnz     short loc_18000EA80
0x18000ea6f  mov     [rdi], bx
0x18000ea72  mov     rcx, rax; lpsz
0x18000ea75  call    cs:__imp_CharNextW
0x18000ea7b  mov     r14, rax
0x18000ea7e  jmp     short loc_18000EA86
0x18000ea80  mov     [rdi], cx
0x18000ea83  add     r14, r15
0x18000ea86  add     rdi, r15
0x18000ea89  cmp     [r14], bx
0x18000ea8d  jnz     short loc_18000EA56
0x18000ea8f  mov     dword ptr [rdi], 0
0x18000ea95  mov     r8, [rsp+21E8h+var_2158]
0x18000ea9d  test    r8, r8
0x18000eaa0  jz      short loc_18000EAE8
0x18000eaa2  mov     r10d, ebx
0x18000eaa5  mov     r9, r8
0x18000eaa8  mov     rcx, rsi
0x18000eaab  inc     rcx
0x18000eaae  cmp     [r9+rcx*2], bx
0x18000eab3  jnz     short loc_18000EAAB
0x18000eab5  inc     ecx
0x18000eab7  lea     r9, [r9+rcx*2]
0x18000eabb  lea     r10d, [r10+rcx*2]
0x18000eabf  cmp     ecx, 1
0x18000eac2  jnz     short loc_18000EAA8
0x18000eac4  mov     [rsp+21E8h+cbData], r10d; cbData
0x18000eac9  mov     [rsp+21E8h+lpData], r8; lpData
0x18000eace  lea     r9d, [rcx+6]; dwType
0x18000ead2  xor     r8d, r8d; Reserved
0x18000ead5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18000eada  mov     rcx, [r13+0]; hKey
0x18000eade  call    cs:__imp_RegSetValueExW
0x18000eae4  mov     edi, eax
0x18000eae6  jmp     short loc_18000EAF8
0x18000eae8  mov     ecx, 80004005h; int
0x18000eaed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000eaf3  mov     edi, 0Eh
0x18000eaf8  lea     rcx, [rsp+21E8h+var_2158]
0x18000eb00  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000eb05  mov     r15, [rsp+21E8h+var_21B0]
0x18000eb0a  jmp     loc_18000EDCE
0x18000eb0f  mov     [rsp+21E8h+pulOut], ebx
0x18000eb13  mov     [rsp+21E8h+var_21B0], rbx
0x18000eb18  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000eb1d  xor     r8d, r8d; dwFlags
0x18000eb20  xor     edx, edx; lcid
0x18000eb22  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000eb2a  call    cs:__imp_VarUI4FromStr
0x18000eb30  mov     edi, eax
0x18000eb32  test    eax, eax
0x18000eb34  jns     short loc_18000EB47
0x18000eb36  lea     rcx, [rsp+21E8h+var_21B0]
0x18000eb3b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000eb40  mov     eax, edi
0x18000eb42  jmp     loc_18000EDF9
0x18000eb47  mov     eax, [rsp+21E8h+pulOut]
0x18000eb4b  mov     dword ptr [rsp+21E8h+Data], eax
0x18000eb4f  mov     [rsp+21E8h+cbData], 4; cbData
0x18000eb57  lea     rax, [rsp+21E8h+Data]
0x18000eb5c  mov     [rsp+21E8h+lpData], rax; lpData
0x18000eb61  mov     r9d, 4; dwType
0x18000eb67  xor     r8d, r8d; Reserved
0x18000eb6a  mov     rdx, r14; lpValueName
0x18000eb6d  mov     rcx, [r12]; hKey
0x18000eb71  call    cs:__imp_RegSetValueExW
0x18000eb77  mov     edi, eax
0x18000eb79  lea     rcx, [rsp+21E8h+var_21B0]
0x18000eb7e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000eb83  jmp     loc_18000EDCE
0x18000eb88  lea     rax, [rsp+21E8h+String1]
0x18000eb90  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000eb94  inc     rsi
0x18000eb97  cmp     [rax+rsi*2], bx
0x18000eb9b  jnz     short loc_18000EB94
0x18000eb9d  mov     dword ptr [rsp+21E8h+Data], esi
0x18000eba1  test    sil, 1
0x18000eba5  jz      short loc_18000EBB1
0x18000eba7  mov     eax, 80004005h
0x18000ebac  jmp     loc_18000EDF9
0x18000ebb1  mov     eax, esi
0x18000ebb3  cdq
0x18000ebb4  mov     r15d, 2
0x18000ebba  idiv    r15d
0x18000ebbd  movsxd  r14, eax
0x18000ebc0  mov     [rsp+21E8h+var_2158], rbx
0x18000ebc8  mov     rdi, r14
0x18000ebcb  mov     [rsp+21E8h+var_2178], r14
0x18000ebd0  lea     edx, [r15-1]
0x18000ebd4  mov     rcx, r14
0x18000ebd7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000ebdc  cmp     rax, 100h
0x18000ebe2  jbe     short loc_18000EBFE
0x18000ebe4  mov     rdx, rax
0x18000ebe7  lea     rcx, [rsp+21E8h+var_2158]
0x18000ebef  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000ebf4  mov     rcx, [rsp+21E8h+var_2158]
0x18000ebfc  jmp     short loc_18000EC0E
0x18000ebfe  lea     rcx, [rsp+21E8h+var_2150]
0x18000ec06  mov     [rsp+21E8h+var_2158], rcx
0x18000ec0e  mov     r15, [rsp+21E8h+var_2198]
0x18000ec13  jmp     short loc_18000EC48
0x18000ec15  xor     ebx, ebx
0x18000ec17  lea     r13d, [rbx+8]
0x18000ec1b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18000ec1f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18000ec27  mov     rdi, [rsp+21E8h+var_2178]
0x18000ec2c  mov     rax, [rsp+21E8h+var_2190]
0x18000ec31  mov     [rsp+21E8h+var_21B0], rax
0x18000ec36  mov     r15, [rsp+21E8h+var_2170]
0x18000ec3b  mov     rax, [rsp+21E8h+var_2188]
0x18000ec40  mov     [rsp+21E8h+lpValueName], rax
0x18000ec45  mov     r14d, edi
0x18000ec48  test    rcx, rcx
0x18000ec4b  jnz     short loc_18000EC5F
0x18000ec4d  lea     rcx, [rsp+21E8h+var_2158]
0x18000ec55  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000ec5a  jmp     loc_18000EBA7
0x18000ec5f  mov     r8, rdi; Size
0x18000ec62  xor     edx, edx; Val
0x18000ec64  call    memset_0
0x18000ec69  mov     r10d, ebx
0x18000ec6c  test    esi, esi
0x18000ec6e  jle     loc_18000ED4C
0x18000ec74  mov     r12d, 30h ; '0'
0x18000ec7a  mov     eax, r10d
0x18000ec7d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18000ec85  cmp     edx, 61h ; 'a'
0x18000ec88  ja      short loc_18000ECF7
0x18000ec8a  jz      loc_18000ED17
0x18000ec90  cmp     edx, 38h ; '8'
0x18000ec93  ja      short loc_18000ECC9
0x18000ec95  jz      short loc_18000ECC1
0x18000ec97  mov     ecx, edx
0x18000ec99  sub     ecx, r12d
0x18000ec9c  jz      short loc_18000ECC1
0x18000ec9e  sub     ecx, 1
0x18000eca1  jz      short loc_18000ECC1
0x18000eca3  sub     ecx, 1
0x18000eca6  jz      short loc_18000ECC1
0x18000eca8  sub     ecx, 1
0x18000ecab  jz      short loc_18000ECC1
0x18000ecad  sub     ecx, 1
0x18000ecb0  jz      short loc_18000ECC1
0x18000ecb2  sub     ecx, 1
0x18000ecb5  jz      short loc_18000ECC1
0x18000ecb7  sub     ecx, 1
0x18000ecba  jz      short loc_18000ECC1
0x18000ecbc  cmp     ecx, 1
0x18000ecbf  jnz     short loc_18000ED12
0x18000ecc1  mov     r9d, edx
0x18000ecc4  sub     r9d, r12d
0x18000ecc7  jmp     short loc_18000ED1B
0x18000ecc9  mov     r9d, edx
0x18000eccc  mov     ecx, edx
0x18000ecce  sub     ecx, 39h ; '9'
0x18000ecd1  jz      short loc_18000ECC1
0x18000ecd3  sub     ecx, r13d
0x18000ecd6  jz      short loc_18000ECF1
0x18000ecd8  sub     ecx, 1
0x18000ecdb  jz      short loc_18000ECF1
0x18000ecdd  sub     ecx, 1
0x18000ece0  jz      short loc_18000ECF1
0x18000ece2  sub     ecx, 1
0x18000ece5  jz      short loc_18000ECF1
0x18000ece7  sub     ecx, 1
0x18000ecea  jz      short loc_18000ECF1
0x18000ecec  cmp     ecx, 1
0x18000ecef  jnz     short loc_18000ED12
0x18000ecf1  add     r9d, 0FFFFFFC9h
0x18000ecf5  jmp     short loc_18000ED1B
0x18000ecf7  mov     ecx, edx
0x18000ecf9  sub     ecx, 62h ; 'b'
0x18000ecfc  jz      short loc_18000ED17
0x18000ecfe  sub     ecx, 1
0x18000ed01  jz      short loc_18000ED17
0x18000ed03  sub     ecx, 1
0x18000ed06  jz      short loc_18000ED17
0x18000ed08  sub     ecx, 1
0x18000ed0b  jz      short loc_18000ED17
0x18000ed0d  cmp     ecx, 1
0x18000ed10  jz      short loc_18000ED17
0x18000ed12  mov     r9d, ebx
0x18000ed15  jmp     short loc_18000ED1B
0x18000ed17  lea     r9d, [rdx-57h]
0x18000ed1b  mov     r8d, r10d
0x18000ed1e  shr     r8, 1
0x18000ed21  mov     rdx, [rsp+21E8h+var_2158]
0x18000ed29  mov     eax, r10d
0x18000ed2c  and     eax, 1
0x18000ed2f  shl     eax, 2
0x18000ed32  mov     ecx, 4
0x18000ed37  sub     ecx, eax
0x18000ed39  shl     r9b, cl
0x18000ed3c  or      [r8+rdx], r9b
0x18000ed40  inc     r10d
  ... truncated ...
```
