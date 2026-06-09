# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180020c50`
- end: `0x1800211b0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1376`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180022ad0`

## callees

- `0x18001e4c0`
- `0x18001efc4`
- `0x180020670`
- `0x1800206d0`
- `0x18002078c`
- `0x180020c50`
- `0x1800211b8`
- `0x18002139c`
- `0x180021470`
- `0x180022200`
- `0x180023154`
- `0x18002321c`
- `0x180047f80`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020e0d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020e29`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020e0d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180020e29`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020e92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002115a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180020e92`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180021103`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002115a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020ceb`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180020ceb`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180020ede`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180020ede`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  LPCWSTR lpValueName; // [rsp+40h] [rbp-21A8h]
  HKEY *v37; // [rsp+48h] [rbp-21A0h]
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
  v37 = a2;
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
      pulOut = v23;
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
        LODWORD(v23) = pulOut;
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
        v21 = ATL::CRegKey::SetDWORDValue((ATL::CRegKey *)a2, a3, pulOut);
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
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
          v13 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v13 = lpData;
        v14 = v37;
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
0x180020c50  push    rbx
0x180020c52  push    rsi
0x180020c53  push    rdi
0x180020c54  push    r12
0x180020c56  push    r13
0x180020c58  push    r14
0x180020c5a  push    r15
0x180020c5c  mov     eax, 21B0h
0x180020c61  call    _alloca_probe
0x180020c66  sub     rsp, rax
0x180020c69  mov     rax, cs:__security_cookie
0x180020c70  xor     rax, rsp
0x180020c73  mov     [rsp+21E8h+var_48], rax
0x180020c7b  mov     r14, r8
0x180020c7e  mov     [rsp+21E8h+lpValueName], r8
0x180020c83  mov     r12, rdx
0x180020c86  mov     [rsp+21E8h+var_2198], rdx
0x180020c8b  mov     r15, rcx
0x180020c8e  mov     [rsp+21E8h+var_21B0], rcx
0x180020c93  mov     [rsp+21E8h+var_21A0], rdx
0x180020c98  mov     [rsp+21E8h+var_2190], rcx
0x180020c9d  mov     [rsp+21E8h+var_2170], rdx
0x180020ca2  mov     [rsp+21E8h+var_2188], r8
0x180020ca7  mov     [rsp+21E8h+var_2168], r9
0x180020caf  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180020cb7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180020cbc  xor     ebx, ebx
0x180020cbe  test    eax, eax
0x180020cc0  js      loc_18002118D
0x180020cc6  mov     edi, ebx
0x180020cc8  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180020ccf  cmp     edi, 4
0x180020cd2  jnb     loc_180021188
0x180020cd8  movsxd  rsi, edi
0x180020cdb  add     rsi, rsi
0x180020cde  mov     rdx, [r13+rsi*8+0]; lpString2
0x180020ce3  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180020ceb  call    cs:__imp_lstrcmpiW
0x180020cf1  test    eax, eax
0x180020cf3  jz      short loc_180020CF9
0x180020cf5  inc     edi
0x180020cf7  jmp     short loc_180020CCF
0x180020cf9  movzx   edi, word ptr [r13+rsi*8+8]
0x180020cff  mov     rcx, r15; this
0x180020d02  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180020d07  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180020d0f  mov     rcx, r15; this
0x180020d12  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180020d17  test    eax, eax
0x180020d19  js      loc_18002118D
0x180020d1f  mov     r13d, 8
0x180020d25  cmp     di, r13w
0x180020d29  jz      loc_18002111D
0x180020d2f  cmp     di, 11h
0x180020d33  jz      loc_180020F1C
0x180020d39  cmp     di, 13h
0x180020d3d  jz      loc_180020EC3
0x180020d43  mov     eax, 4008h
0x180020d48  cmp     di, ax
0x180020d4b  jnz     loc_18002116F
0x180020d51  lea     rcx, [rsp+21E8h+String1]
0x180020d59  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180020d5d  mov     rax, rsi
0x180020d60  inc     rax
0x180020d63  cmp     [rcx+rax*2], bx
0x180020d67  jnz     short loc_180020D60
0x180020d69  add     eax, 2
0x180020d6c  mov     [rsp+21E8h+var_2158], rbx
0x180020d74  movsxd  rcx, eax
0x180020d77  mov     r15d, 2
0x180020d7d  mov     edx, r15d
0x180020d80  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180020d85  cmp     rax, 100h
0x180020d8b  jbe     short loc_180020DA7
0x180020d8d  mov     rdx, rax
0x180020d90  lea     rcx, [rsp+21E8h+var_2158]
0x180020d98  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180020d9d  mov     rdi, [rsp+21E8h+var_2158]
0x180020da5  jmp     short loc_180020DB7
0x180020da7  lea     rdi, [rsp+21E8h+var_2150]
0x180020daf  mov     [rsp+21E8h+var_2158], rdi
0x180020db7  mov     r13, [rsp+21E8h+var_2198]
0x180020dbc  jmp     short loc_180020DE9
0x180020dbe  xor     ebx, ebx
0x180020dc0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180020dc4  lea     r15d, [rbx+2]
0x180020dc8  mov     rdi, [rsp+21E8h+var_2158]
0x180020dd0  mov     r13, [rsp+21E8h+var_21A0]
0x180020dd5  mov     rax, [rsp+21E8h+var_2190]
0x180020dda  mov     [rsp+21E8h+var_21B0], rax
0x180020ddf  mov     rax, [rsp+21E8h+var_2188]
0x180020de4  mov     [rsp+21E8h+lpValueName], rax
0x180020de9  test    rdi, rdi
0x180020dec  jz      loc_180020EA7
0x180020df2  lea     r14, [rsp+21E8h+String1]
0x180020dfa  cmp     [rsp+21E8h+String1], bx
0x180020e02  jz      short loc_180020E43
0x180020e04  mov     r12d, 30h ; '0'
0x180020e0a  mov     rcx, r14; lpsz
0x180020e0d  call    cs:__imp_CharNextW
0x180020e13  movzx   ecx, word ptr [r14]
0x180020e17  cmp     cx, 5Ch ; '\'
0x180020e1b  jnz     short loc_180020E34
0x180020e1d  cmp     [rax], r12w
0x180020e21  jnz     short loc_180020E34
0x180020e23  mov     [rdi], bx
0x180020e26  mov     rcx, rax; lpsz
0x180020e29  call    cs:__imp_CharNextW
0x180020e2f  mov     r14, rax
0x180020e32  jmp     short loc_180020E3A
0x180020e34  mov     [rdi], cx
0x180020e37  add     r14, r15
0x180020e3a  add     rdi, r15
0x180020e3d  cmp     [r14], bx
0x180020e41  jnz     short loc_180020E0A
0x180020e43  mov     dword ptr [rdi], 0
0x180020e49  mov     r8, [rsp+21E8h+var_2158]
0x180020e51  test    r8, r8
0x180020e54  jz      short loc_180020E9C
0x180020e56  mov     r10d, ebx
0x180020e59  mov     r9, r8
0x180020e5c  mov     rcx, rsi
0x180020e5f  inc     rcx
0x180020e62  cmp     [r9+rcx*2], bx
0x180020e67  jnz     short loc_180020E5F
0x180020e69  inc     ecx
0x180020e6b  lea     r9, [r9+rcx*2]
0x180020e6f  lea     r10d, [r10+rcx*2]
0x180020e73  cmp     ecx, 1
0x180020e76  jnz     short loc_180020E5C
0x180020e78  mov     [rsp+21E8h+cbData], r10d; cbData
0x180020e7d  mov     [rsp+21E8h+lpData], r8; lpData
0x180020e82  lea     r9d, [rcx+6]; dwType
0x180020e86  xor     r8d, r8d; Reserved
0x180020e89  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180020e8e  mov     rcx, [r13+0]; hKey
0x180020e92  call    cs:__imp_RegSetValueExW
0x180020e98  mov     edi, eax
0x180020e9a  jmp     short loc_180020EAC
0x180020e9c  mov     ecx, 80004005h; int
0x180020ea1  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180020ea7  mov     edi, 0Eh
0x180020eac  lea     rcx, [rsp+21E8h+var_2158]
0x180020eb4  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180020eb9  mov     r15, [rsp+21E8h+var_21B0]
0x180020ebe  jmp     loc_180021162
0x180020ec3  mov     [rsp+21E8h+pulOut], ebx
0x180020ec7  mov     [rsp+21E8h+var_21B0], rbx
0x180020ecc  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180020ed1  xor     r8d, r8d; dwFlags
0x180020ed4  xor     edx, edx; lcid
0x180020ed6  lea     rcx, [rsp+21E8h+String1]; strIn
0x180020ede  call    cs:__imp_VarUI4FromStr
0x180020ee4  mov     edi, eax
0x180020ee6  test    eax, eax
0x180020ee8  jns     short loc_180020EFB
0x180020eea  lea     rcx, [rsp+21E8h+var_21B0]
0x180020eef  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180020ef4  mov     eax, edi
0x180020ef6  jmp     loc_18002118D
0x180020efb  mov     r8d, [rsp+21E8h+pulOut]; unsigned int
0x180020f00  mov     rdx, r14; unsigned __int16 *
0x180020f03  mov     rcx, r12; this
0x180020f06  call    ?SetDWORDValue@CRegKey@ATL@@QEAAJPEBGK@Z; ATL::CRegKey::SetDWORDValue(ushort const *,ulong)
0x180020f0b  mov     edi, eax
0x180020f0d  lea     rcx, [rsp+21E8h+var_21B0]
0x180020f12  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180020f17  jmp     loc_180021162
0x180020f1c  lea     rax, [rsp+21E8h+String1]
0x180020f24  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180020f28  inc     rsi
0x180020f2b  cmp     [rax+rsi*2], bx
0x180020f2f  jnz     short loc_180020F28
0x180020f31  mov     [rsp+21E8h+pulOut], esi
0x180020f35  test    sil, 1
0x180020f39  jz      short loc_180020F45
0x180020f3b  mov     eax, 80004005h
0x180020f40  jmp     loc_18002118D
0x180020f45  mov     eax, esi
0x180020f47  cdq
0x180020f48  mov     r15d, 2
0x180020f4e  idiv    r15d
0x180020f51  movsxd  r14, eax
0x180020f54  mov     [rsp+21E8h+var_2158], rbx
0x180020f5c  mov     rdi, r14
0x180020f5f  mov     [rsp+21E8h+var_2178], r14
0x180020f64  lea     edx, [r15-1]
0x180020f68  mov     rcx, r14
0x180020f6b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180020f70  cmp     rax, 100h
0x180020f76  jbe     short loc_180020F92
0x180020f78  mov     rdx, rax
0x180020f7b  lea     rcx, [rsp+21E8h+var_2158]
0x180020f83  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180020f88  mov     rcx, [rsp+21E8h+var_2158]
0x180020f90  jmp     short loc_180020FA2
0x180020f92  lea     rcx, [rsp+21E8h+var_2150]
0x180020f9a  mov     [rsp+21E8h+var_2158], rcx
0x180020fa2  mov     r15, [rsp+21E8h+var_2198]
0x180020fa7  jmp     short loc_180020FDC
0x180020fa9  xor     ebx, ebx
0x180020fab  lea     r13d, [rbx+8]
0x180020faf  mov     esi, [rsp+21E8h+pulOut]
0x180020fb3  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180020fbb  mov     rdi, [rsp+21E8h+var_2178]
0x180020fc0  mov     rax, [rsp+21E8h+var_2190]
0x180020fc5  mov     [rsp+21E8h+var_21B0], rax
0x180020fca  mov     r15, [rsp+21E8h+var_2170]
0x180020fcf  mov     rax, [rsp+21E8h+var_2188]
0x180020fd4  mov     [rsp+21E8h+lpValueName], rax
0x180020fd9  mov     r14d, edi
0x180020fdc  test    rcx, rcx
0x180020fdf  jnz     short loc_180020FF3
0x180020fe1  lea     rcx, [rsp+21E8h+var_2158]
0x180020fe9  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180020fee  jmp     loc_180020F3B
0x180020ff3  mov     r8, rdi; Size
0x180020ff6  xor     edx, edx; Val
0x180020ff8  call    memset_0
0x180020ffd  mov     r10d, ebx
0x180021000  test    esi, esi
0x180021002  jle     loc_1800210E0
0x180021008  mov     r12d, 30h ; '0'
0x18002100e  mov     eax, r10d
0x180021011  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180021019  cmp     edx, 61h ; 'a'
0x18002101c  ja      short loc_18002108B
0x18002101e  jz      loc_1800210AB
0x180021024  cmp     edx, 38h ; '8'
0x180021027  ja      short loc_18002105D
0x180021029  jz      short loc_180021055
0x18002102b  mov     ecx, edx
0x18002102d  sub     ecx, r12d
0x180021030  jz      short loc_180021055
0x180021032  sub     ecx, 1
0x180021035  jz      short loc_180021055
0x180021037  sub     ecx, 1
0x18002103a  jz      short loc_180021055
0x18002103c  sub     ecx, 1
0x18002103f  jz      short loc_180021055
0x180021041  sub     ecx, 1
0x180021044  jz      short loc_180021055
0x180021046  sub     ecx, 1
0x180021049  jz      short loc_180021055
0x18002104b  sub     ecx, 1
0x18002104e  jz      short loc_180021055
0x180021050  cmp     ecx, 1
0x180021053  jnz     short loc_1800210A6
0x180021055  mov     r9d, edx
0x180021058  sub     r9d, r12d
0x18002105b  jmp     short loc_1800210AF
0x18002105d  mov     r9d, edx
0x180021060  mov     ecx, edx
0x180021062  sub     ecx, 39h ; '9'
0x180021065  jz      short loc_180021055
0x180021067  sub     ecx, r13d
0x18002106a  jz      short loc_180021085
0x18002106c  sub     ecx, 1
0x18002106f  jz      short loc_180021085
0x180021071  sub     ecx, 1
0x180021074  jz      short loc_180021085
0x180021076  sub     ecx, 1
0x180021079  jz      short loc_180021085
0x18002107b  sub     ecx, 1
0x18002107e  jz      short loc_180021085
0x180021080  cmp     ecx, 1
0x180021083  jnz     short loc_1800210A6
0x180021085  add     r9d, 0FFFFFFC9h
0x180021089  jmp     short loc_1800210AF
0x18002108b  mov     ecx, edx
0x18002108d  sub     ecx, 62h ; 'b'
0x180021090  jz      short loc_1800210AB
0x180021092  sub     ecx, 1
0x180021095  jz      short loc_1800210AB
0x180021097  sub     ecx, 1
0x18002109a  jz      short loc_1800210AB
0x18002109c  sub     ecx, 1
0x18002109f  jz      short loc_1800210AB
0x1800210a1  cmp     ecx, 1
0x1800210a4  jz      short loc_1800210AB
0x1800210a6  mov     r9d, ebx
0x1800210a9  jmp     short loc_1800210AF
0x1800210ab  lea     r9d, [rdx-57h]
0x1800210af  mov     r8d, r10d
0x1800210b2  shr     r8, 1
0x1800210b5  mov     rdx, [rsp+21E8h+var_2158]
0x1800210bd  mov     eax, r10d
0x1800210c0  and     eax, 1
0x1800210c3  shl     eax, 2
0x1800210c6  mov     ecx, 4
0x1800210cb  sub     ecx, eax
0x1800210cd  shl     r9b, cl
0x1800210d0  or      [r8+rdx], r9b
0x1800210d4  inc     r10d
0x1800210d7  cmp     r10d, esi
0x1800210da  jl      loc_18002100E
0x1800210e0  mov     rax, [rsp+21E8h+var_2158]
0x1800210e8  mov     [rsp+21E8h+cbData], r14d; cbData
0x1800210ed  mov     [rsp+21E8h+lpData], rax; lpData
0x1800210f2  mov     r9d, 3; dwType
  ... truncated ...
```
