# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18000b6ac`
- end: `0x18000bb8a`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1246`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180010624`

## callees

- `0x180006270`
- `0x180006dcc`
- `0x180009198`
- `0x180009eb8`
- `0x18000a364`
- `0x18000b6ac`
- `0x18000bb90`
- `0x18000bed0`
- `0x18000e960`
- `0x1800115c4`
- `0x1800116d0`
- `0x1800118b4`
- `0x180038ab0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000b8c9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000b8c9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bae0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bb37`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bae0`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000bb37`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b841`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b85c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b841`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000b85c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b734`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000b734`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(ATL::CRegParser *this, HKEY *a2, const wchar_t *a3, wchar_t *a4)
{
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  ATL::CRegParser *v6; // r14
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *j; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // edi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // r14d
  size_t v20; // rsi
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  unsigned int v23; // r10d
  unsigned int v24; // edx
  char v25; // r9
  __int64 v26; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  _QWORD v29[2]; // [rsp+38h] [rbp-21A0h] BYREF
  ATL::CRegParser *v30; // [rsp+48h] [rbp-2190h]
  struct ATL::CRegKey *v31; // [rsp+50h] [rbp-2188h]
  const wchar_t *v32; // [rsp+60h] [rbp-2178h]
  size_t v33; // [rsp+70h] [rbp-2168h]
  wchar_t *v34; // [rsp+78h] [rbp-2160h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v36[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v29[0] = this;
  v30 = this;
  v31 = (struct ATL::CRegKey *)a2;
  v32 = a3;
  v34 = a4;
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
      v26 = -1;
      do
        ++v26;
      while ( String1[v26] );
      v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v26 + 2);
      goto LABEL_72;
    case 17:
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      pulOut = v18;
      if ( (v18 & 1) != 0 )
        return 2147500037LL;
      cbData = (int)v18 / 2;
      lpData = 0;
      v20 = (int)v18 / 2;
      v33 = v20;
      try
      {
        v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v21 <= 0x100 )
        {
          v22 = v36;
          lpData = v36;
        }
        else
        {
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
          v22 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v18) = pulOut;
        v22 = lpData;
        v20 = v33;
        v29[0] = v30;
        v5 = (HKEY *)v31;
        v4 = v32;
        cbData = v33;
      }
      if ( !v22 )
      {
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v22, 0, v20);
      v23 = 0;
      if ( (int)v18 <= 0 )
      {
LABEL_68:
        v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_27;
      }
      while ( 1 )
      {
        v24 = String1[v23];
        if ( v24 > 0x61 )
        {
          if ( v24 == 98 || v24 == 99 || v24 == 100 || v24 - 101 < 2 )
          {
LABEL_66:
            v25 = v24 - 87;
            goto LABEL_67;
          }
LABEL_65:
          v25 = 0;
          goto LABEL_67;
        }
        if ( v24 == 97 )
          goto LABEL_66;
        if ( v24 <= 0x38 )
          break;
        if ( v24 == 57 )
          goto LABEL_53;
        if ( v24 != 65 && v24 != 66 && v24 != 67 && v24 != 68 && v24 - 69 > 1 )
          goto LABEL_65;
        v25 = v24 - 55;
LABEL_67:
        lpData[(unsigned __int64)v23 >> 1] |= v25 << (4 - 4 * (v23 & 1));
        if ( (int)++v23 >= (int)v18 )
          goto LABEL_68;
      }
      if ( v24 != 56 && v24 != 48 && v24 != 49 && v24 != 50 && v24 != 51 && v24 != 52 && v24 != 53 && v24 - 54 > 1 )
        goto LABEL_65;
LABEL_53:
      v25 = v24 - 48;
      goto LABEL_67;
    case 19:
      pulOut = 0;
      v29[0] = 0;
      v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v17 >= 0 )
      {
        v16 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)v5, v4, pulOut);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v29);
        goto LABEL_72;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v29);
      return (unsigned int)v17;
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
          v13 = v36;
          lpData = v36;
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
        v29[0] = v30;
        v5 = (HKEY *)v31;
        v4 = v32;
      }
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v15 = CharNextW(j);
          if ( *j == 92 && *v15 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v15);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
        v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, (const wchar_t *)lpData);
      }
      else
      {
        v16 = 14;
      }
      ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
LABEL_27:
      v6 = (ATL::CRegParser *)v29[0];
LABEL_72:
      if ( v16 )
      {
        return ATL::AtlHresultFromWin32(v16);
      }
      else
      {
LABEL_74:
        Token = ATL::CRegParser::NextToken(v6, v34);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_74;
  }
}

```

## disassembly

```asm
0x18000b6ac  push    rbx
0x18000b6ae  push    rsi
0x18000b6af  push    rdi
0x18000b6b0  push    r12
0x18000b6b2  push    r13
0x18000b6b4  push    r14
0x18000b6b6  push    r15
0x18000b6b8  mov     eax, 21A0h
0x18000b6bd  call    _alloca_probe
0x18000b6c2  sub     rsp, rax
0x18000b6c5  mov     rax, cs:__security_cookie
0x18000b6cc  xor     rax, rsp
0x18000b6cf  mov     [rsp+21D8h+var_48], rax
0x18000b6d7  mov     r13, r8
0x18000b6da  mov     r12, rdx
0x18000b6dd  mov     r14, rcx
0x18000b6e0  mov     [rsp+21D8h+var_21A0], rcx
0x18000b6e5  mov     [rsp+21D8h+var_2190], rcx
0x18000b6ea  mov     [rsp+21D8h+var_2188], rdx
0x18000b6ef  mov     [rsp+21D8h+var_2178], r8
0x18000b6f4  mov     [rsp+21D8h+var_2160], r9
0x18000b6f9  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x18000b701  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000b706  xor     ebx, ebx
0x18000b708  test    eax, eax
0x18000b70a  js      loc_18000BB67
0x18000b710  mov     edi, ebx
0x18000b712  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000b719  cmp     edi, 4
0x18000b71c  jnb     loc_18000BB62
0x18000b722  movsxd  rsi, edi
0x18000b725  add     rsi, rsi
0x18000b728  mov     rdx, [r15+rsi*8]; lpString2
0x18000b72c  lea     rcx, [rsp+21D8h+String1]; lpString1
0x18000b734  call    cs:__imp_lstrcmpiW
0x18000b73a  test    eax, eax
0x18000b73c  jz      short loc_18000B742
0x18000b73e  inc     edi
0x18000b740  jmp     short loc_18000B719
0x18000b742  movzx   edi, word ptr [r15+rsi*8+8]
0x18000b748  mov     rcx, r14; this
0x18000b74b  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000b750  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x18000b758  mov     rcx, r14; this
0x18000b75b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000b760  test    eax, eax
0x18000b762  js      loc_18000BB67
0x18000b768  mov     r15d, 8
0x18000b76e  cmp     di, r15w
0x18000b772  jz      loc_18000BAFA
0x18000b778  cmp     di, 11h
0x18000b77c  jz      loc_18000B907
0x18000b782  cmp     di, 13h
0x18000b786  jz      loc_18000B8AE
0x18000b78c  mov     eax, 4008h
0x18000b791  cmp     di, ax
0x18000b794  jnz     loc_18000BB4C
0x18000b79a  lea     rax, [rsp+21D8h+String1]
0x18000b7a2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b7a6  inc     rdi
0x18000b7a9  cmp     [rax+rdi*2], bx
0x18000b7ad  jnz     short loc_18000B7A6
0x18000b7af  add     edi, 2
0x18000b7b2  mov     [rsp+21D8h+var_2158], rbx
0x18000b7ba  movsxd  rcx, edi
0x18000b7bd  mov     r14d, 2
0x18000b7c3  mov     edx, r14d
0x18000b7c6  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000b7cb  cmp     rax, 100h
0x18000b7d1  jbe     short loc_18000B7ED
0x18000b7d3  mov     rdx, rax
0x18000b7d6  lea     rcx, [rsp+21D8h+var_2158]
0x18000b7de  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000b7e3  mov     rdi, [rsp+21D8h+var_2158]
0x18000b7eb  jmp     short loc_18000B7FD
0x18000b7ed  lea     rdi, [rsp+21D8h+var_2150]
0x18000b7f5  mov     [rsp+21D8h+var_2158], rdi
0x18000b7fd  jmp     short loc_18000B821
0x18000b7ff  xor     ebx, ebx
0x18000b801  lea     r14d, [rbx+2]
0x18000b805  mov     rdi, [rsp+21D8h+var_2158]
0x18000b80d  mov     rax, [rsp+21D8h+var_2190]
0x18000b812  mov     [rsp+21D8h+var_21A0], rax
0x18000b817  mov     r12, [rsp+21D8h+var_2188]
0x18000b81c  mov     r13, [rsp+21D8h+var_2178]
0x18000b821  test    rdi, rdi
0x18000b824  jz      short loc_18000B892
0x18000b826  lea     rsi, [rsp+21D8h+String1]
0x18000b82e  cmp     [rsp+21D8h+String1], bx
0x18000b836  jz      short loc_18000B875
0x18000b838  mov     r15d, 30h ; '0'
0x18000b83e  mov     rcx, rsi; lpsz
0x18000b841  call    cs:__imp_CharNextW
0x18000b847  movzx   ecx, word ptr [rsi]
0x18000b84a  cmp     cx, 5Ch ; '\'
0x18000b84e  jnz     short loc_18000B867
0x18000b850  cmp     [rax], r15w
0x18000b854  jnz     short loc_18000B867
0x18000b856  mov     [rdi], bx
0x18000b859  mov     rcx, rax; lpsz
0x18000b85c  call    cs:__imp_CharNextW
0x18000b862  mov     rsi, rax
0x18000b865  jmp     short loc_18000B86D
0x18000b867  mov     [rdi], cx
0x18000b86a  add     rsi, r14
0x18000b86d  add     rdi, r14
0x18000b870  cmp     [rsi], bx
0x18000b873  jnz     short loc_18000B83E
0x18000b875  mov     dword ptr [rdi], 0
0x18000b87b  mov     r8, [rsp+21D8h+var_2158]; wchar_t *
0x18000b883  mov     rdx, r13; wchar_t *
0x18000b886  mov     rcx, r12; this
0x18000b889  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEB_W0@Z; ATL::CRegKey::SetMultiStringValue(wchar_t const *,wchar_t const *)
0x18000b88e  mov     edi, eax
0x18000b890  jmp     short loc_18000B897
0x18000b892  mov     edi, 0Eh
0x18000b897  lea     rcx, [rsp+21D8h+var_2158]
0x18000b89f  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000b8a4  mov     r14, [rsp+21D8h+var_21A0]
0x18000b8a9  jmp     loc_18000BB3F
0x18000b8ae  mov     [rsp+21D8h+pulOut], ebx
0x18000b8b2  mov     [rsp+21D8h+var_21A0], rbx
0x18000b8b7  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x18000b8bc  xor     r8d, r8d; dwFlags
0x18000b8bf  xor     edx, edx; lcid
0x18000b8c1  lea     rcx, [rsp+21D8h+String1]; strIn
0x18000b8c9  call    cs:__imp_VarUI4FromStr
0x18000b8cf  mov     edi, eax
0x18000b8d1  test    eax, eax
0x18000b8d3  jns     short loc_18000B8E6
0x18000b8d5  lea     rcx, [rsp+21D8h+var_21A0]
0x18000b8da  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b8df  mov     eax, edi
0x18000b8e1  jmp     loc_18000BB67
0x18000b8e6  mov     r8d, [rsp+21D8h+pulOut]; unsigned int
0x18000b8eb  mov     rdx, r13; wchar_t *
0x18000b8ee  mov     rcx, r12; this
0x18000b8f1  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEB_WK@Z; ATL::CRegKey::SetDWORDValue(wchar_t const *,ulong)
0x18000b8f6  mov     edi, eax
0x18000b8f8  lea     rcx, [rsp+21D8h+var_21A0]
0x18000b8fd  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b902  jmp     loc_18000BB3F
0x18000b907  lea     rax, [rsp+21D8h+String1]
0x18000b90f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000b913  inc     rdi
0x18000b916  cmp     [rax+rdi*2], bx
0x18000b91a  jnz     short loc_18000B913
0x18000b91c  mov     [rsp+21D8h+pulOut], edi
0x18000b920  test    dil, 1
0x18000b924  jz      short loc_18000B930
0x18000b926  mov     eax, 80004005h
0x18000b92b  jmp     loc_18000BB67
0x18000b930  mov     eax, edi
0x18000b932  cdq
0x18000b933  mov     r14d, 2
0x18000b939  idiv    r14d
0x18000b93c  movsxd  r14, eax
0x18000b93f  mov     [rsp+21D8h+var_2158], rbx
0x18000b947  mov     rsi, r14
0x18000b94a  mov     [rsp+21D8h+var_2168], r14
0x18000b94f  mov     edx, 1
0x18000b954  mov     rcx, r14
0x18000b957  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000b95c  cmp     rax, 100h
0x18000b962  jbe     short loc_18000B97E
0x18000b964  mov     rdx, rax
0x18000b967  lea     rcx, [rsp+21D8h+var_2158]
0x18000b96f  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000b974  mov     rcx, [rsp+21D8h+var_2158]
0x18000b97c  jmp     short loc_18000B98E
0x18000b97e  lea     rcx, [rsp+21D8h+var_2150]
0x18000b986  mov     [rsp+21D8h+var_2158], rcx
0x18000b98e  jmp     short loc_18000B9BA
0x18000b990  xor     ebx, ebx
0x18000b992  mov     edi, [rsp+21D8h+pulOut]
0x18000b996  mov     rcx, [rsp+21D8h+var_2158]; void *
0x18000b99e  mov     rsi, [rsp+21D8h+var_2168]
0x18000b9a3  mov     rax, [rsp+21D8h+var_2190]
0x18000b9a8  mov     [rsp+21D8h+var_21A0], rax
0x18000b9ad  mov     r12, [rsp+21D8h+var_2188]
0x18000b9b2  mov     r13, [rsp+21D8h+var_2178]
0x18000b9b7  mov     r14d, esi
0x18000b9ba  test    rcx, rcx
0x18000b9bd  jnz     short loc_18000B9D1
0x18000b9bf  lea     rcx, [rsp+21D8h+var_2158]
0x18000b9c7  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000b9cc  jmp     loc_18000B926
0x18000b9d1  mov     r8, rsi; Size
0x18000b9d4  xor     edx, edx; Val
0x18000b9d6  call    memset_0
0x18000b9db  mov     r10d, ebx
0x18000b9de  test    edi, edi
0x18000b9e0  jle     loc_18000BABE
0x18000b9e6  mov     r15d, 30h ; '0'
0x18000b9ec  mov     eax, r10d
0x18000b9ef  movzx   edx, [rsp+rax*2+21D8h+String1]
0x18000b9f7  cmp     edx, 61h ; 'a'
0x18000b9fa  ja      short loc_18000BA69
0x18000b9fc  jz      loc_18000BA89
0x18000ba02  cmp     edx, 38h ; '8'
0x18000ba05  ja      short loc_18000BA3B
0x18000ba07  jz      short loc_18000BA33
0x18000ba09  mov     ecx, edx
0x18000ba0b  sub     ecx, r15d
0x18000ba0e  jz      short loc_18000BA33
0x18000ba10  sub     ecx, 1
0x18000ba13  jz      short loc_18000BA33
0x18000ba15  sub     ecx, 1
0x18000ba18  jz      short loc_18000BA33
0x18000ba1a  sub     ecx, 1
0x18000ba1d  jz      short loc_18000BA33
0x18000ba1f  sub     ecx, 1
0x18000ba22  jz      short loc_18000BA33
0x18000ba24  sub     ecx, 1
0x18000ba27  jz      short loc_18000BA33
0x18000ba29  sub     ecx, 1
0x18000ba2c  jz      short loc_18000BA33
0x18000ba2e  cmp     ecx, 1
0x18000ba31  jnz     short loc_18000BA84
0x18000ba33  mov     r9d, edx
0x18000ba36  sub     r9d, r15d
0x18000ba39  jmp     short loc_18000BA8D
0x18000ba3b  mov     r9d, edx
0x18000ba3e  mov     ecx, edx
0x18000ba40  sub     ecx, 39h ; '9'
0x18000ba43  jz      short loc_18000BA33
0x18000ba45  sub     ecx, 8
0x18000ba48  jz      short loc_18000BA63
0x18000ba4a  sub     ecx, 1
0x18000ba4d  jz      short loc_18000BA63
0x18000ba4f  sub     ecx, 1
0x18000ba52  jz      short loc_18000BA63
0x18000ba54  sub     ecx, 1
0x18000ba57  jz      short loc_18000BA63
0x18000ba59  sub     ecx, 1
0x18000ba5c  jz      short loc_18000BA63
0x18000ba5e  cmp     ecx, 1
0x18000ba61  jnz     short loc_18000BA84
0x18000ba63  add     r9d, 0FFFFFFC9h
0x18000ba67  jmp     short loc_18000BA8D
0x18000ba69  mov     ecx, edx
0x18000ba6b  sub     ecx, 62h ; 'b'
0x18000ba6e  jz      short loc_18000BA89
0x18000ba70  sub     ecx, 1
0x18000ba73  jz      short loc_18000BA89
0x18000ba75  sub     ecx, 1
0x18000ba78  jz      short loc_18000BA89
0x18000ba7a  sub     ecx, 1
0x18000ba7d  jz      short loc_18000BA89
0x18000ba7f  cmp     ecx, 1
0x18000ba82  jz      short loc_18000BA89
0x18000ba84  mov     r9d, ebx
0x18000ba87  jmp     short loc_18000BA8D
0x18000ba89  lea     r9d, [rdx-57h]
0x18000ba8d  mov     r8d, r10d
0x18000ba90  shr     r8, 1
0x18000ba93  mov     rdx, [rsp+21D8h+var_2158]
0x18000ba9b  mov     eax, r10d
0x18000ba9e  and     eax, 1
0x18000baa1  shl     eax, 2
0x18000baa4  mov     ecx, 4
0x18000baa9  sub     ecx, eax
0x18000baab  shl     r9b, cl
0x18000baae  or      [r8+rdx], r9b
0x18000bab2  inc     r10d
0x18000bab5  cmp     r10d, edi
0x18000bab8  jl      loc_18000B9EC
0x18000babe  mov     rax, [rsp+21D8h+var_2158]
0x18000bac6  mov     [rsp+21D8h+cbData], r14d; cbData
0x18000bacb  mov     [rsp+21D8h+lpData], rax; lpData
0x18000bad0  mov     r9d, 3; dwType
0x18000bad6  xor     r8d, r8d; Reserved
0x18000bad9  mov     rdx, r13; lpValueName
0x18000badc  mov     rcx, [r12]; hKey
0x18000bae0  call    cs:__imp_RegSetValueExW
0x18000bae6  mov     edi, eax
0x18000bae8  lea     rcx, [rsp+21D8h+var_2158]
0x18000baf0  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000baf5  jmp     loc_18000B8A4
0x18000bafa  lea     rax, [rsp+21D8h+String1]
0x18000bb02  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000bb06  inc     rdi
0x18000bb09  cmp     [rax+rdi*2], bx
0x18000bb0d  jnz     short loc_18000BB06
0x18000bb0f  lea     eax, ds:2[rdi*2]
0x18000bb16  mov     [rsp+21D8h+cbData], eax; cbData
0x18000bb1a  lea     rax, [rsp+21D8h+String1]
0x18000bb22  mov     [rsp+21D8h+lpData], rax; lpData
0x18000bb27  mov     r9d, 1; dwType
0x18000bb2d  xor     r8d, r8d; Reserved
0x18000bb30  mov     rdx, r13; lpValueName
0x18000bb33  mov     rcx, [r12]; hKey
0x18000bb37  call    cs:__imp_RegSetValueExW
0x18000bb3d  mov     edi, eax
0x18000bb3f  test    edi, edi
0x18000bb41  jz      short loc_18000BB4C
0x18000bb43  mov     ecx, edi; unsigned int
0x18000bb45  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000bb4a  jmp     short loc_18000BB67
0x18000bb4c  mov     rdx, [rsp+21D8h+var_2160]; wchar_t *
  ... truncated ...
```
