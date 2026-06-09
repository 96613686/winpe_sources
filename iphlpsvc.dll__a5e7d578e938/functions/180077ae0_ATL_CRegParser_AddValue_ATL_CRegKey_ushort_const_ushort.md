# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180077ae0`
- end: `0x180077fb9`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1241`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180078fb0`

## callees

- `0x18004b5f0`
- `0x18004c188`
- `0x18007751c`
- `0x180077554`
- `0x180077600`
- `0x180077ae0`
- `0x180077fc0`
- `0x1800781a8`
- `0x1800781c0`
- `0x180078234`
- `0x180078678`
- `0x1800796c4`
- `0x1800821f0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077d0e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077dad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077f02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077f5f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077d0e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077dad`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077f02`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077f5f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077c7f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077ca1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077c7f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077ca1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180077b6d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180077b6d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180077d60`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180077d60`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  ATL::CRegParser *v6; // r14
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rsi
  WCHAR *k; // r14
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // edi
  HRESULT v21; // edi
  __int64 v22; // rdi
  DWORD v23; // r14d
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int j; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21A0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-2198h] BYREF
  ATL::CRegParser *v37; // [rsp+48h] [rbp-2190h]
  const unsigned __int16 *v38; // [rsp+50h] [rbp-2188h]
  size_t v39; // [rsp+60h] [rbp-2178h]
  struct ATL::CRegKey *v40; // [rsp+68h] [rbp-2170h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-2168h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v43[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v37 = this;
  v40 = (struct ATL::CRegKey *)a2;
  v38 = a3;
  v41 = a4;
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
      v20 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      break;
    case 17:
      v22 = -1;
      do
        ++v22;
      while ( String1[v22] );
      *(_DWORD *)Data = v22;
      if ( (v22 & 1) == 0 )
      {
        v23 = (int)v22 / 2;
        lpData = 0;
        v24 = (int)v22 / 2;
        v39 = v24;
        try
        {
          v25 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v25 <= 0x100 )
          {
            v26 = v43;
            lpData = v43;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
            v26 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v22) = *(_DWORD *)Data;
          v26 = lpData;
          v24 = v39;
          v35 = v37;
          v5 = (HKEY *)v40;
          v4 = v38;
          v23 = v39;
        }
        if ( v26 )
        {
          memset_0(v26, 0, v24);
          for ( j = 0; j < (int)v22; j = v29 + 1 )
          {
            v28 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v31 + v30) |= v28 << (4 - 4 * (v29 & 1));
          }
          v20 = RegSetValueExW(*v5, v4, 0, 3u, lpData, v23);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_33:
          v6 = v35;
          break;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    case 19:
      pulOut = 0;
      v35 = 0;
      v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v21 < 0 )
      {
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        return (unsigned int)v21;
      }
      *(_DWORD *)Data = pulOut;
      v20 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
      break;
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
          v13 = v43;
          lpData = v43;
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
        v5 = *(HKEY **)Data;
        v35 = v37;
        v4 = v38;
      }
      if ( v13 )
      {
        for ( k = String1; *k; v13 += 2 )
        {
          v15 = CharNextW(k);
          if ( *k == 92 && *v15 == 48 )
          {
            *(_WORD *)v13 = 0;
            k = CharNextW(v15);
          }
          else
          {
            *(_WORD *)v13 = *k++;
          }
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v17 = lpData;
        do
        {
          v18 = -1;
          do
            ++v18;
          while ( *(_WORD *)&v17[2 * v18] );
          v19 = (unsigned int)(v18 + 1);
          v17 += 2 * v19;
          cbData += 2 * v19;
        }
        while ( (_DWORD)v19 != 1 );
        v20 = RegSetValueExW(*v5, v4, 0, 7u, lpData, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      goto LABEL_33;
    default:
LABEL_55:
      Token = ATL::CRegParser::NextToken(v6, v41);
      if ( Token < 0 )
        return (unsigned int)Token;
      return v8;
  }
  if ( !v20 )
    goto LABEL_55;
  return ATL::AtlHresultFromWin32(v20);
}

```

## disassembly

```asm
0x180077ae0  push    rbx
0x180077ae2  push    rsi
0x180077ae3  push    rdi
0x180077ae4  push    r12
0x180077ae6  push    r13
0x180077ae8  push    r14
0x180077aea  push    r15
0x180077aec  mov     eax, 21A0h
0x180077af1  call    _alloca_probe
0x180077af6  sub     rsp, rax
0x180077af9  mov     rax, cs:__security_cookie
0x180077b00  xor     rax, rsp
0x180077b03  mov     [rsp+21D8h+var_48], rax
0x180077b0b  mov     r13, r8
0x180077b0e  mov     r12, rdx
0x180077b11  mov     r14, rcx
0x180077b14  mov     [rsp+21D8h+var_21A0], rcx
0x180077b19  mov     qword ptr [rsp+21D8h+Data], rdx
0x180077b1e  mov     [rsp+21D8h+var_2190], rcx
0x180077b23  mov     [rsp+21D8h+var_2170], rdx
0x180077b28  mov     [rsp+21D8h+var_2188], r8
0x180077b2d  mov     [rsp+21D8h+var_2168], r9
0x180077b32  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180077b3a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180077b3f  xor     ebx, ebx
0x180077b41  test    eax, eax
0x180077b43  js      loc_180077F95
0x180077b49  mov     edi, ebx
0x180077b4b  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180077b52  cmp     edi, 4
0x180077b55  jnb     loc_180077F90
0x180077b5b  movsxd  rsi, edi
0x180077b5e  add     rsi, rsi
0x180077b61  mov     rdx, [r15+rsi*8]; lpString2
0x180077b65  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180077b6d  call    cs:__imp_lstrcmpiW
0x180077b74  nop     dword ptr [rax+rax+00h]
0x180077b79  test    eax, eax
0x180077b7b  jz      short loc_180077B81
0x180077b7d  inc     edi
0x180077b7f  jmp     short loc_180077B52
0x180077b81  movzx   edi, word ptr [r15+rsi*8+8]
0x180077b87  mov     rcx, r14; this
0x180077b8a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180077b8f  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180077b97  mov     rcx, r14; this
0x180077b9a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180077b9f  test    eax, eax
0x180077ba1  js      loc_180077F95
0x180077ba7  cmp     di, 8
0x180077bab  jz      loc_180077F22
0x180077bb1  cmp     di, 11h
0x180077bb5  jz      loc_180077DCA
0x180077bbb  cmp     di, 13h
0x180077bbf  jz      loc_180077D45
0x180077bc5  mov     eax, 4008h
0x180077bca  cmp     di, ax
0x180077bcd  jnz     loc_180077F7A
0x180077bd3  lea     rcx, [rsp+21D8h+String1]
0x180077bdb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077bdf  mov     rax, rdi
0x180077be2  inc     rax
0x180077be5  cmp     [rcx+rax*2], bx
0x180077be9  jnz     short loc_180077BE2
0x180077beb  add     eax, 2
0x180077bee  mov     [rsp+21D8h+var_2158], rbx
0x180077bf6  movsxd  rcx, eax
0x180077bf9  mov     r15d, 2
0x180077bff  mov     edx, r15d
0x180077c02  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180077c07  cmp     rax, 100h
0x180077c0d  jbe     short loc_180077C29
0x180077c0f  mov     rdx, rax
0x180077c12  lea     rcx, [rsp+21D8h+var_2158]
0x180077c1a  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180077c1f  mov     rsi, [rsp+21D8h+var_2158]
0x180077c27  jmp     short loc_180077C39
0x180077c29  lea     rsi, [rsp+21D8h+var_2150]
0x180077c31  mov     [rsp+21D8h+var_2158], rsi
0x180077c39  jmp     short loc_180077C61
0x180077c3b  xor     ebx, ebx
0x180077c3d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077c41  lea     r15d, [rbx+2]
0x180077c45  mov     rsi, [rsp+21D8h+var_2158]
0x180077c4d  mov     r12, qword ptr [rsp+21D8h+Data]
0x180077c52  mov     rax, [rsp+21D8h+var_2190]
0x180077c57  mov     [rsp+21D8h+var_21A0], rax
0x180077c5c  mov     r13, [rsp+21D8h+var_2188]
0x180077c61  test    rsi, rsi
0x180077c64  jz      loc_180077D29
0x180077c6a  lea     r14, [rsp+21D8h+String1]
0x180077c72  cmp     [rsp+21D8h+String1], bx
0x180077c7a  jz      short loc_180077CC1
0x180077c7c  mov     rcx, r14; lpsz
0x180077c7f  call    cs:__imp_CharNextW
0x180077c86  nop     dword ptr [rax+rax+00h]
0x180077c8b  movzx   ecx, word ptr [r14]
0x180077c8f  cmp     cx, 5Ch ; '\'
0x180077c93  jnz     short loc_180077CB2
0x180077c95  cmp     word ptr [rax], 30h ; '0'
0x180077c99  jnz     short loc_180077CB2
0x180077c9b  mov     [rsi], bx
0x180077c9e  mov     rcx, rax; lpsz
0x180077ca1  call    cs:__imp_CharNextW
0x180077ca8  nop     dword ptr [rax+rax+00h]
0x180077cad  mov     r14, rax
0x180077cb0  jmp     short loc_180077CB8
0x180077cb2  mov     [rsi], cx
0x180077cb5  add     r14, r15
0x180077cb8  add     rsi, r15
0x180077cbb  cmp     [r14], bx
0x180077cbf  jnz     short loc_180077C7C
0x180077cc1  mov     dword ptr [rsi], 0
0x180077cc7  mov     r8, [rsp+21D8h+var_2158]
0x180077ccf  test    r8, r8
0x180077cd2  jz      short loc_180077D1E
0x180077cd4  mov     r10d, ebx
0x180077cd7  mov     r9, r8
0x180077cda  mov     rcx, rdi
0x180077cdd  inc     rcx
0x180077ce0  cmp     [r9+rcx*2], bx
0x180077ce5  jnz     short loc_180077CDD
0x180077ce7  inc     ecx
0x180077ce9  lea     r9, [r9+rcx*2]
0x180077ced  lea     r10d, [r10+rcx*2]
0x180077cf1  cmp     ecx, 1
0x180077cf4  jnz     short loc_180077CDA
0x180077cf6  mov     [rsp+21D8h+cbData], r10d; cbData
0x180077cfb  mov     [rsp+21D8h+lpData], r8; lpData
0x180077d00  lea     r9d, [rcx+6]; dwType
0x180077d04  xor     r8d, r8d; Reserved
0x180077d07  mov     rdx, r13; lpValueName
0x180077d0a  mov     rcx, [r12]; hKey
0x180077d0e  call    cs:__imp_RegSetValueExW
0x180077d15  nop     dword ptr [rax+rax+00h]
0x180077d1a  mov     edi, eax
0x180077d1c  jmp     short loc_180077D2E
0x180077d1e  mov     ecx, 80004005h; int
0x180077d23  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180077d29  mov     edi, 0Eh
0x180077d2e  lea     rcx, [rsp+21D8h+var_2158]
0x180077d36  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180077d3b  mov     r14, [rsp+21D8h+var_21A0]
0x180077d40  jmp     loc_180077F6D
0x180077d45  mov     [rsp+21D8h+pulOut], ebx
0x180077d49  mov     [rsp+21D8h+var_21A0], rbx
0x180077d4e  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x180077d53  xor     r8d, r8d; dwFlags
0x180077d56  xor     edx, edx; lcid
0x180077d58  lea     rcx, [rsp+21D8h+String1]; strIn
0x180077d60  call    cs:__imp_VarUI4FromStr
0x180077d67  nop     dword ptr [rax+rax+00h]
0x180077d6c  mov     edi, eax
0x180077d6e  test    eax, eax
0x180077d70  jns     short loc_180077D83
0x180077d72  lea     rcx, [rsp+21D8h+var_21A0]
0x180077d77  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180077d7c  mov     eax, edi
0x180077d7e  jmp     loc_180077F95
0x180077d83  mov     eax, [rsp+21D8h+pulOut]
0x180077d87  mov     dword ptr [rsp+21D8h+Data], eax
0x180077d8b  mov     [rsp+21D8h+cbData], 4; cbData
0x180077d93  lea     rax, [rsp+21D8h+Data]
0x180077d98  mov     [rsp+21D8h+lpData], rax; lpData
0x180077d9d  mov     r9d, 4; dwType
0x180077da3  xor     r8d, r8d; Reserved
0x180077da6  mov     rdx, r13; lpValueName
0x180077da9  mov     rcx, [r12]; hKey
0x180077dad  call    cs:__imp_RegSetValueExW
0x180077db4  nop     dword ptr [rax+rax+00h]
0x180077db9  mov     edi, eax
0x180077dbb  lea     rcx, [rsp+21D8h+var_21A0]
0x180077dc0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180077dc5  jmp     loc_180077F6D
0x180077dca  lea     rax, [rsp+21D8h+String1]
0x180077dd2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077dd6  inc     rdi
0x180077dd9  cmp     [rax+rdi*2], bx
0x180077ddd  jnz     short loc_180077DD6
0x180077ddf  mov     dword ptr [rsp+21D8h+Data], edi
0x180077de3  test    dil, 1
0x180077de7  jz      short loc_180077DF3
0x180077de9  mov     eax, 80004005h
0x180077dee  jmp     loc_180077F95
0x180077df3  mov     eax, edi
0x180077df5  cdq
0x180077df6  mov     r15d, 2
0x180077dfc  idiv    r15d
0x180077dff  movsxd  r14, eax
0x180077e02  mov     [rsp+21D8h+var_2158], rbx
0x180077e0a  mov     rsi, r14
0x180077e0d  mov     [rsp+21D8h+var_2178], r14
0x180077e12  lea     edx, [r15-1]
0x180077e16  mov     rcx, r14
0x180077e19  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180077e1e  cmp     rax, 100h
0x180077e24  jbe     short loc_180077E40
0x180077e26  mov     rdx, rax
0x180077e29  lea     rcx, [rsp+21D8h+var_2158]
0x180077e31  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180077e36  mov     rcx, [rsp+21D8h+var_2158]
0x180077e3e  jmp     short loc_180077E50
0x180077e40  lea     rcx, [rsp+21D8h+var_2150]
0x180077e48  mov     [rsp+21D8h+var_2158], rcx
0x180077e50  jmp     short loc_180077E7C
0x180077e52  xor     ebx, ebx
0x180077e54  mov     edi, dword ptr [rsp+21D8h+Data]
0x180077e58  mov     rcx, [rsp+21D8h+var_2158]; void *
0x180077e60  mov     rsi, [rsp+21D8h+var_2178]
0x180077e65  mov     rax, [rsp+21D8h+var_2190]
0x180077e6a  mov     [rsp+21D8h+var_21A0], rax
0x180077e6f  mov     r12, [rsp+21D8h+var_2170]
0x180077e74  mov     r13, [rsp+21D8h+var_2188]
0x180077e79  mov     r14d, esi
0x180077e7c  test    rcx, rcx
0x180077e7f  jnz     short loc_180077E93
0x180077e81  lea     rcx, [rsp+21D8h+var_2158]
0x180077e89  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180077e8e  jmp     loc_180077DE9
0x180077e93  mov     r8, rsi; Size
0x180077e96  xor     edx, edx; Val
0x180077e98  call    memset_0
0x180077e9d  mov     r10d, ebx
0x180077ea0  test    edi, edi
0x180077ea2  jle     short loc_180077EE0
0x180077ea4  mov     r9d, r10d
0x180077ea7  shr     r9, 1
0x180077eaa  mov     r8, [rsp+21D8h+var_2158]
0x180077eb2  mov     ecx, r10d
0x180077eb5  movzx   ecx, [rsp+rcx*2+21D8h+String1]; unsigned __int16
0x180077ebd  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180077ec2  mov     edx, r10d
0x180077ec5  and     edx, 1
0x180077ec8  shl     edx, 2
0x180077ecb  mov     ecx, 4
0x180077ed0  sub     ecx, edx
0x180077ed2  shl     al, cl
0x180077ed4  or      [r9+r8], al
0x180077ed8  inc     r10d
0x180077edb  cmp     r10d, edi
0x180077ede  jl      short loc_180077EA4
0x180077ee0  mov     rax, [rsp+21D8h+var_2158]
0x180077ee8  mov     [rsp+21D8h+cbData], r14d; cbData
0x180077eed  mov     [rsp+21D8h+lpData], rax; lpData
0x180077ef2  mov     r9d, 3; dwType
0x180077ef8  xor     r8d, r8d; Reserved
0x180077efb  mov     rdx, r13; lpValueName
0x180077efe  mov     rcx, [r12]; hKey
0x180077f02  call    cs:__imp_RegSetValueExW
0x180077f09  nop     dword ptr [rax+rax+00h]
0x180077f0e  mov     edi, eax
0x180077f10  lea     rcx, [rsp+21D8h+var_2158]
0x180077f18  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180077f1d  jmp     loc_180077D3B
0x180077f22  lea     rax, [rsp+21D8h+String1]
0x180077f2a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077f2e  inc     rdi
0x180077f31  cmp     [rax+rdi*2], bx
0x180077f35  jnz     short loc_180077F2E
0x180077f37  lea     eax, ds:2[rdi*2]
0x180077f3e  mov     [rsp+21D8h+cbData], eax; cbData
0x180077f42  lea     rax, [rsp+21D8h+String1]
0x180077f4a  mov     [rsp+21D8h+lpData], rax; lpData
0x180077f4f  mov     r9d, 1; dwType
0x180077f55  xor     r8d, r8d; Reserved
0x180077f58  mov     rdx, r13; lpValueName
0x180077f5b  mov     rcx, [r12]; hKey
0x180077f5f  call    cs:__imp_RegSetValueExW
0x180077f66  nop     dword ptr [rax+rax+00h]
0x180077f6b  mov     edi, eax
0x180077f6d  test    edi, edi
0x180077f6f  jz      short loc_180077F7A
0x180077f71  mov     ecx, edi; unsigned int
0x180077f73  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180077f78  jmp     short loc_180077F95
0x180077f7a  mov     rdx, [rsp+21D8h+var_2168]; unsigned __int16 *
0x180077f7f  mov     rcx, r14; this
0x180077f82  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180077f87  test    eax, eax
0x180077f89  cmovs   ebx, eax
0x180077f8c  mov     eax, ebx
0x180077f8e  jmp     short loc_180077F95
0x180077f90  mov     eax, 80020009h
0x180077f95  mov     rcx, [rsp+21D8h+var_48]
0x180077f9d  xor     rcx, rsp; StackCookie
0x180077fa0  call    __security_check_cookie
0x180077fa5  add     rsp, 21A0h
0x180077fac  pop     r15
0x180077fae  pop     r14
0x180077fb0  pop     r13
0x180077fb2  pop     r12
0x180077fb4  pop     rdi
0x180077fb5  pop     rsi
0x180077fb6  pop     rbx
0x180077fb7  retn
```
