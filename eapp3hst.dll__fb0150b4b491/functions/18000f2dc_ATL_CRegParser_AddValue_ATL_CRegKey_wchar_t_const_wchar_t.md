# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18000f2dc`
- end: `0x18000f85c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001075c`

## callees

- `0x1800017a0`
- `0x18000213c`
- `0x18000d1dc`
- `0x18000ee0c`
- `0x18000ee68`
- `0x18000eec0`
- `0x18000f2dc`
- `0x18000f864`
- `0x18000fae4`
- `0x18000fee4`
- `0x180010e24`
- `0x18002f450`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000f56a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000f56a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f51e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f5b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f7af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f806`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f51e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f5b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f7af`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f806`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f499`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f4b5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f499`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f4b5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f377`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000f377`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000f2dc  push    rbx
0x18000f2de  push    rsi
0x18000f2df  push    rdi
0x18000f2e0  push    r12
0x18000f2e2  push    r13
0x18000f2e4  push    r14
0x18000f2e6  push    r15
0x18000f2e8  mov     eax, 21B0h
0x18000f2ed  call    _alloca_probe
0x18000f2f2  sub     rsp, rax
0x18000f2f5  mov     rax, cs:__security_cookie
0x18000f2fc  xor     rax, rsp
0x18000f2ff  mov     [rsp+21E8h+var_48], rax
0x18000f307  mov     r14, r8
0x18000f30a  mov     [rsp+21E8h+lpValueName], r8
0x18000f30f  mov     r12, rdx
0x18000f312  mov     [rsp+21E8h+var_2198], rdx
0x18000f317  mov     r15, rcx
0x18000f31a  mov     [rsp+21E8h+var_21B0], rcx
0x18000f31f  mov     qword ptr [rsp+21E8h+Data], rdx
0x18000f324  mov     [rsp+21E8h+var_2190], rcx
0x18000f329  mov     [rsp+21E8h+var_2170], rdx
0x18000f32e  mov     [rsp+21E8h+var_2188], r8
0x18000f333  mov     [rsp+21E8h+var_2168], r9
0x18000f33b  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x18000f343  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f348  xor     ebx, ebx
0x18000f34a  test    eax, eax
0x18000f34c  js      loc_18000F839
0x18000f352  mov     edi, ebx
0x18000f354  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000f35b  cmp     edi, 4
0x18000f35e  jnb     loc_18000F834
0x18000f364  movsxd  rsi, edi
0x18000f367  add     rsi, rsi
0x18000f36a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000f36f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18000f377  call    cs:__imp_lstrcmpiW
0x18000f37d  test    eax, eax
0x18000f37f  jz      short loc_18000F385
0x18000f381  inc     edi
0x18000f383  jmp     short loc_18000F35B
0x18000f385  movzx   edi, word ptr [r13+rsi*8+8]
0x18000f38b  mov     rcx, r15; this
0x18000f38e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000f393  lea     rdx, [rsp+21E8h+String1]; wchar_t *
0x18000f39b  mov     rcx, r15; this
0x18000f39e  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f3a3  test    eax, eax
0x18000f3a5  js      loc_18000F839
0x18000f3ab  mov     r13d, 8
0x18000f3b1  cmp     di, r13w
0x18000f3b5  jz      loc_18000F7C9
0x18000f3bb  cmp     di, 11h
0x18000f3bf  jz      loc_18000F5C8
0x18000f3c5  cmp     di, 13h
0x18000f3c9  jz      loc_18000F54F
0x18000f3cf  mov     eax, 4008h
0x18000f3d4  cmp     di, ax
0x18000f3d7  jnz     loc_18000F81B
0x18000f3dd  lea     rcx, [rsp+21E8h+String1]
0x18000f3e5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f3e9  mov     rax, rsi
0x18000f3ec  inc     rax
0x18000f3ef  cmp     [rcx+rax*2], bx
0x18000f3f3  jnz     short loc_18000F3EC
0x18000f3f5  add     eax, 2
0x18000f3f8  mov     [rsp+21E8h+var_2158], rbx
0x18000f400  movsxd  rcx, eax
0x18000f403  mov     r15d, 2
0x18000f409  mov     edx, r15d
0x18000f40c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000f411  cmp     rax, 100h
0x18000f417  jbe     short loc_18000F433
0x18000f419  mov     rdx, rax
0x18000f41c  lea     rcx, [rsp+21E8h+var_2158]
0x18000f424  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000f429  mov     rdi, [rsp+21E8h+var_2158]
0x18000f431  jmp     short loc_18000F443
0x18000f433  lea     rdi, [rsp+21E8h+var_2150]
0x18000f43b  mov     [rsp+21E8h+var_2158], rdi
0x18000f443  mov     r13, [rsp+21E8h+var_2198]
0x18000f448  jmp     short loc_18000F475
0x18000f44a  xor     ebx, ebx
0x18000f44c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f450  lea     r15d, [rbx+2]
0x18000f454  mov     rdi, [rsp+21E8h+var_2158]
0x18000f45c  mov     r13, qword ptr [rsp+21E8h+Data]
0x18000f461  mov     rax, [rsp+21E8h+var_2190]
0x18000f466  mov     [rsp+21E8h+var_21B0], rax
0x18000f46b  mov     rax, [rsp+21E8h+var_2188]
0x18000f470  mov     [rsp+21E8h+lpValueName], rax
0x18000f475  test    rdi, rdi
0x18000f478  jz      loc_18000F533
0x18000f47e  lea     r14, [rsp+21E8h+String1]
0x18000f486  cmp     [rsp+21E8h+String1], bx
0x18000f48e  jz      short loc_18000F4CF
0x18000f490  mov     r12d, 30h ; '0'
0x18000f496  mov     rcx, r14; lpsz
0x18000f499  call    cs:__imp_CharNextW
0x18000f49f  movzx   ecx, word ptr [r14]
0x18000f4a3  cmp     cx, 5Ch ; '\'
0x18000f4a7  jnz     short loc_18000F4C0
0x18000f4a9  cmp     [rax], r12w
0x18000f4ad  jnz     short loc_18000F4C0
0x18000f4af  mov     [rdi], bx
0x18000f4b2  mov     rcx, rax; lpsz
0x18000f4b5  call    cs:__imp_CharNextW
0x18000f4bb  mov     r14, rax
0x18000f4be  jmp     short loc_18000F4C6
0x18000f4c0  mov     [rdi], cx
0x18000f4c3  add     r14, r15
0x18000f4c6  add     rdi, r15
0x18000f4c9  cmp     [r14], bx
0x18000f4cd  jnz     short loc_18000F496
0x18000f4cf  mov     dword ptr [rdi], 0
0x18000f4d5  mov     r8, [rsp+21E8h+var_2158]
0x18000f4dd  test    r8, r8
0x18000f4e0  jz      short loc_18000F528
0x18000f4e2  mov     r10d, ebx
0x18000f4e5  mov     r9, r8
0x18000f4e8  mov     rcx, rsi
0x18000f4eb  inc     rcx
0x18000f4ee  cmp     [r9+rcx*2], bx
0x18000f4f3  jnz     short loc_18000F4EB
0x18000f4f5  inc     ecx
0x18000f4f7  lea     r9, [r9+rcx*2]
0x18000f4fb  lea     r10d, [r10+rcx*2]
0x18000f4ff  cmp     ecx, 1
0x18000f502  jnz     short loc_18000F4E8
0x18000f504  mov     [rsp+21E8h+cbData], r10d; cbData
0x18000f509  mov     [rsp+21E8h+lpData], r8; lpData
0x18000f50e  lea     r9d, [rcx+6]; dwType
0x18000f512  xor     r8d, r8d; Reserved
0x18000f515  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18000f51a  mov     rcx, [r13+0]; hKey
0x18000f51e  call    cs:__imp_RegSetValueExW
0x18000f524  mov     edi, eax
0x18000f526  jmp     short loc_18000F538
0x18000f528  mov     ecx, 80004005h; int
0x18000f52d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f533  mov     edi, 0Eh
0x18000f538  lea     rcx, [rsp+21E8h+var_2158]
0x18000f540  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000f545  mov     r15, [rsp+21E8h+var_21B0]
0x18000f54a  jmp     loc_18000F80E
0x18000f54f  mov     [rsp+21E8h+pulOut], ebx
0x18000f553  mov     [rsp+21E8h+var_21B0], rbx
0x18000f558  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000f55d  xor     r8d, r8d; dwFlags
0x18000f560  xor     edx, edx; lcid
0x18000f562  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000f56a  call    cs:__imp_VarUI4FromStr
0x18000f570  mov     edi, eax
0x18000f572  test    eax, eax
0x18000f574  jns     short loc_18000F587
0x18000f576  lea     rcx, [rsp+21E8h+var_21B0]
0x18000f57b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f580  mov     eax, edi
0x18000f582  jmp     loc_18000F839
0x18000f587  mov     eax, [rsp+21E8h+pulOut]
0x18000f58b  mov     dword ptr [rsp+21E8h+Data], eax
0x18000f58f  mov     [rsp+21E8h+cbData], 4; cbData
0x18000f597  lea     rax, [rsp+21E8h+Data]
0x18000f59c  mov     [rsp+21E8h+lpData], rax; lpData
0x18000f5a1  mov     r9d, 4; dwType
0x18000f5a7  xor     r8d, r8d; Reserved
0x18000f5aa  mov     rdx, r14; lpValueName
0x18000f5ad  mov     rcx, [r12]; hKey
0x18000f5b1  call    cs:__imp_RegSetValueExW
0x18000f5b7  mov     edi, eax
0x18000f5b9  lea     rcx, [rsp+21E8h+var_21B0]
0x18000f5be  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f5c3  jmp     loc_18000F80E
0x18000f5c8  lea     rax, [rsp+21E8h+String1]
0x18000f5d0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000f5d4  inc     rsi
0x18000f5d7  cmp     [rax+rsi*2], bx
0x18000f5db  jnz     short loc_18000F5D4
0x18000f5dd  mov     dword ptr [rsp+21E8h+Data], esi
0x18000f5e1  test    sil, 1
0x18000f5e5  jz      short loc_18000F5F1
0x18000f5e7  mov     eax, 80004005h
0x18000f5ec  jmp     loc_18000F839
0x18000f5f1  mov     eax, esi
0x18000f5f3  cdq
0x18000f5f4  mov     r15d, 2
0x18000f5fa  idiv    r15d
0x18000f5fd  movsxd  r14, eax
0x18000f600  mov     [rsp+21E8h+var_2158], rbx
0x18000f608  mov     rdi, r14
0x18000f60b  mov     [rsp+21E8h+var_2178], r14
0x18000f610  lea     edx, [r15-1]
0x18000f614  mov     rcx, r14
0x18000f617  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000f61c  cmp     rax, 100h
0x18000f622  jbe     short loc_18000F63E
0x18000f624  mov     rdx, rax
0x18000f627  lea     rcx, [rsp+21E8h+var_2158]
0x18000f62f  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000f634  mov     rcx, [rsp+21E8h+var_2158]
0x18000f63c  jmp     short loc_18000F64E
0x18000f63e  lea     rcx, [rsp+21E8h+var_2150]
0x18000f646  mov     [rsp+21E8h+var_2158], rcx
0x18000f64e  mov     r15, [rsp+21E8h+var_2198]
0x18000f653  jmp     short loc_18000F688
0x18000f655  xor     ebx, ebx
0x18000f657  lea     r13d, [rbx+8]
0x18000f65b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18000f65f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18000f667  mov     rdi, [rsp+21E8h+var_2178]
0x18000f66c  mov     rax, [rsp+21E8h+var_2190]
0x18000f671  mov     [rsp+21E8h+var_21B0], rax
0x18000f676  mov     r15, [rsp+21E8h+var_2170]
0x18000f67b  mov     rax, [rsp+21E8h+var_2188]
0x18000f680  mov     [rsp+21E8h+lpValueName], rax
0x18000f685  mov     r14d, edi
0x18000f688  test    rcx, rcx
0x18000f68b  jnz     short loc_18000F69F
0x18000f68d  lea     rcx, [rsp+21E8h+var_2158]
0x18000f695  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000f69a  jmp     loc_18000F5E7
0x18000f69f  mov     r8, rdi; Size
0x18000f6a2  xor     edx, edx; Val
0x18000f6a4  call    memset_0
0x18000f6a9  mov     r10d, ebx
0x18000f6ac  test    esi, esi
0x18000f6ae  jle     loc_18000F78C
0x18000f6b4  mov     r12d, 30h ; '0'
0x18000f6ba  mov     eax, r10d
0x18000f6bd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18000f6c5  cmp     edx, 61h ; 'a'
0x18000f6c8  ja      short loc_18000F737
0x18000f6ca  jz      loc_18000F757
0x18000f6d0  cmp     edx, 38h ; '8'
0x18000f6d3  ja      short loc_18000F709
0x18000f6d5  jz      short loc_18000F701
0x18000f6d7  mov     ecx, edx
0x18000f6d9  sub     ecx, r12d
0x18000f6dc  jz      short loc_18000F701
0x18000f6de  sub     ecx, 1
0x18000f6e1  jz      short loc_18000F701
0x18000f6e3  sub     ecx, 1
0x18000f6e6  jz      short loc_18000F701
0x18000f6e8  sub     ecx, 1
0x18000f6eb  jz      short loc_18000F701
0x18000f6ed  sub     ecx, 1
0x18000f6f0  jz      short loc_18000F701
0x18000f6f2  sub     ecx, 1
0x18000f6f5  jz      short loc_18000F701
0x18000f6f7  sub     ecx, 1
0x18000f6fa  jz      short loc_18000F701
0x18000f6fc  cmp     ecx, 1
0x18000f6ff  jnz     short loc_18000F752
0x18000f701  mov     r9d, edx
0x18000f704  sub     r9d, r12d
0x18000f707  jmp     short loc_18000F75B
0x18000f709  mov     r9d, edx
0x18000f70c  mov     ecx, edx
0x18000f70e  sub     ecx, 39h ; '9'
0x18000f711  jz      short loc_18000F701
0x18000f713  sub     ecx, r13d
0x18000f716  jz      short loc_18000F731
0x18000f718  sub     ecx, 1
0x18000f71b  jz      short loc_18000F731
0x18000f71d  sub     ecx, 1
0x18000f720  jz      short loc_18000F731
0x18000f722  sub     ecx, 1
0x18000f725  jz      short loc_18000F731
0x18000f727  sub     ecx, 1
0x18000f72a  jz      short loc_18000F731
0x18000f72c  cmp     ecx, 1
0x18000f72f  jnz     short loc_18000F752
0x18000f731  add     r9d, 0FFFFFFC9h
0x18000f735  jmp     short loc_18000F75B
0x18000f737  mov     ecx, edx
0x18000f739  sub     ecx, 62h ; 'b'
0x18000f73c  jz      short loc_18000F757
0x18000f73e  sub     ecx, 1
0x18000f741  jz      short loc_18000F757
0x18000f743  sub     ecx, 1
0x18000f746  jz      short loc_18000F757
0x18000f748  sub     ecx, 1
0x18000f74b  jz      short loc_18000F757
0x18000f74d  cmp     ecx, 1
0x18000f750  jz      short loc_18000F757
0x18000f752  mov     r9d, ebx
0x18000f755  jmp     short loc_18000F75B
0x18000f757  lea     r9d, [rdx-57h]
0x18000f75b  mov     r8d, r10d
0x18000f75e  shr     r8, 1
0x18000f761  mov     rdx, [rsp+21E8h+var_2158]
0x18000f769  mov     eax, r10d
0x18000f76c  and     eax, 1
0x18000f76f  shl     eax, 2
0x18000f772  mov     ecx, 4
0x18000f777  sub     ecx, eax
0x18000f779  shl     r9b, cl
0x18000f77c  or      [r8+rdx], r9b
0x18000f780  inc     r10d
  ... truncated ...
```
