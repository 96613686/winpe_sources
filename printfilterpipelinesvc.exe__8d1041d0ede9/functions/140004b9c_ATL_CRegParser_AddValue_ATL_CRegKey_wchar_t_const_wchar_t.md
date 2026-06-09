# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x140004b9c`
- end: `0x14000509a`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1278`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x140006af0`

## callees

- `0x140002070`
- `0x140002c68`
- `0x1400042a8`
- `0x140004528`
- `0x1400045f4`
- `0x140004b9c`
- `0x1400050a0`
- `0x14000537c`
- `0x140005eb0`
- `0x140007328`
- `0x140007548`
- `0x14005d370`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x140004e00`
- `ADVAPI32!RegSetValueExW` at `0x140004ff0`
- `ADVAPI32!RegSetValueExW` at `0x140005047`
- `ADVAPI32!RegSetValueExW` at `0x140004e00`
- `ADVAPI32!RegSetValueExW` at `0x140004ff0`
- `ADVAPI32!RegSetValueExW` at `0x140005047`
- `KERNEL32!lstrcmpiW` at `0x140004c24`
- `KERNEL32!lstrcmpiW` at `0x140004c24`
- `USER32!CharNextW` at `0x140004d31`
- `USER32!CharNextW` at `0x140004d4c`
- `USER32!CharNextW` at `0x140004d31`
- `USER32!CharNextW` at `0x140004d4c`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140004db9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140004db9`

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
  unsigned int v16; // edi
  int v17; // edx
  HRESULT v18; // edi
  __int64 v19; // rdi
  DWORD cbData; // r14d
  size_t v21; // rsi
  unsigned __int64 v22; // rax
  BYTE *v23; // rcx
  unsigned int v24; // r10d
  unsigned int v25; // edx
  char v26; // r9
  __int64 v27; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21A8h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-21A0h] BYREF
  ATL::CRegParser *v31; // [rsp+40h] [rbp-2198h] BYREF
  ATL::CRegParser *v32; // [rsp+48h] [rbp-2190h]
  struct ATL::CRegKey *v33; // [rsp+50h] [rbp-2188h]
  const wchar_t *v34; // [rsp+60h] [rbp-2178h]
  size_t v35; // [rsp+70h] [rbp-2168h]
  wchar_t *v36; // [rsp+78h] [rbp-2160h]
  BYTE *lpData; // [rsp+80h] [rbp-2158h] BYREF
  _BYTE v38[264]; // [rsp+88h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+190h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v31 = this;
  v32 = this;
  v33 = (struct ATL::CRegKey *)a2;
  v34 = a3;
  v36 = a4;
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
      v27 = -1;
      do
        ++v27;
      while ( String1[v27] );
      v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v27 + 2);
      goto LABEL_72;
    case 17:
      v19 = -1;
      do
        ++v19;
      while ( String1[v19] );
      *(_DWORD *)Data = v19;
      if ( (v19 & 1) != 0 )
        return 2147500037LL;
      cbData = (int)v19 / 2;
      lpData = 0;
      v21 = (int)v19 / 2;
      v35 = v21;
      try
      {
        v22 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v22 <= 0x100 )
        {
          v23 = v38;
          lpData = v38;
        }
        else
        {
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v22);
          v23 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v19) = *(_DWORD *)Data;
        v23 = lpData;
        v21 = v35;
        v31 = v32;
        v5 = (HKEY *)v33;
        v4 = v34;
        cbData = v35;
      }
      if ( !v23 )
      {
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v23, 0, v21);
      v24 = 0;
      if ( (int)v19 <= 0 )
      {
LABEL_68:
        v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_27;
      }
      while ( 1 )
      {
        v25 = String1[v24];
        if ( v25 > 0x61 )
        {
          if ( v25 == 98 || v25 == 99 || v25 == 100 || v25 - 101 < 2 )
          {
LABEL_66:
            v26 = v25 - 87;
            goto LABEL_67;
          }
LABEL_65:
          v26 = 0;
          goto LABEL_67;
        }
        if ( v25 == 97 )
          goto LABEL_66;
        if ( v25 <= 0x38 )
          break;
        if ( v25 == 57 )
          goto LABEL_53;
        if ( v25 != 65 && v25 != 66 && v25 != 67 && v25 != 68 && v25 - 69 > 1 )
          goto LABEL_65;
        v26 = v25 - 55;
LABEL_67:
        lpData[(unsigned __int64)v24 >> 1] |= v26 << (4 - 4 * (v24 & 1));
        if ( (int)++v24 >= (int)v19 )
          goto LABEL_68;
      }
      if ( v25 != 56 && v25 != 48 && v25 != 49 && v25 != 50 && v25 != 51 && v25 != 52 && v25 != 53 && v25 - 54 > 1 )
        goto LABEL_65;
LABEL_53:
      v26 = v25 - 48;
      goto LABEL_67;
    case 19:
      pulOut = 0;
      v31 = 0;
      v18 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v18 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v16 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v31);
        goto LABEL_72;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v31);
      return (unsigned int)v18;
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
          v13 = v38;
          lpData = v38;
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
        v31 = v32;
        v5 = (HKEY *)v33;
        v4 = v34;
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
      v6 = v31;
LABEL_72:
      if ( v16 )
      {
        return NCoreLibrary::HResultFromWin32((NCoreLibrary *)v16, v17);
      }
      else
      {
LABEL_74:
        Token = ATL::CRegParser::NextToken(v6, v36);
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
0x140004b9c  push    rbx
0x140004b9e  push    rsi
0x140004b9f  push    rdi
0x140004ba0  push    r12
0x140004ba2  push    r13
0x140004ba4  push    r14
0x140004ba6  push    r15
0x140004ba8  mov     eax, 21A0h
0x140004bad  call    _alloca_probe
0x140004bb2  sub     rsp, rax
0x140004bb5  mov     rax, cs:__security_cookie
0x140004bbc  xor     rax, rsp
0x140004bbf  mov     [rsp+21D8h+var_48], rax
0x140004bc7  mov     r13, r8
0x140004bca  mov     r12, rdx
0x140004bcd  mov     r14, rcx
0x140004bd0  mov     [rsp+21D8h+var_2198], rcx
0x140004bd5  mov     [rsp+21D8h+var_2190], rcx
0x140004bda  mov     [rsp+21D8h+var_2188], rdx
0x140004bdf  mov     [rsp+21D8h+var_2178], r8
0x140004be4  mov     [rsp+21D8h+var_2160], r9
0x140004be9  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x140004bf1  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140004bf6  xor     ebx, ebx
0x140004bf8  test    eax, eax
0x140004bfa  js      loc_140005077
0x140004c00  mov     edi, ebx
0x140004c02  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x140004c09  cmp     edi, 4
0x140004c0c  jnb     loc_140005072
0x140004c12  movsxd  rsi, edi
0x140004c15  add     rsi, rsi
0x140004c18  mov     rdx, [r15+rsi*8]; lpString2
0x140004c1c  lea     rcx, [rsp+21D8h+String1]; lpString1
0x140004c24  call    cs:__imp_lstrcmpiW
0x140004c2a  test    eax, eax
0x140004c2c  jz      short loc_140004C32
0x140004c2e  inc     edi
0x140004c30  jmp     short loc_140004C09
0x140004c32  movzx   edi, word ptr [r15+rsi*8+8]
0x140004c38  mov     rcx, r14; this
0x140004c3b  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140004c40  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x140004c48  mov     rcx, r14; this
0x140004c4b  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x140004c50  test    eax, eax
0x140004c52  js      loc_140005077
0x140004c58  mov     r15d, 8
0x140004c5e  cmp     di, r15w
0x140004c62  jz      loc_14000500A
0x140004c68  cmp     di, 11h
0x140004c6c  jz      loc_140004E17
0x140004c72  cmp     di, 13h
0x140004c76  jz      loc_140004D9E
0x140004c7c  mov     eax, 4008h
0x140004c81  cmp     di, ax
0x140004c84  jnz     loc_14000505C
0x140004c8a  lea     rax, [rsp+21D8h+String1]
0x140004c92  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140004c96  inc     rdi
0x140004c99  cmp     [rax+rdi*2], bx
0x140004c9d  jnz     short loc_140004C96
0x140004c9f  add     edi, 2
0x140004ca2  mov     [rsp+21D8h+var_2158], rbx
0x140004caa  movsxd  rcx, edi
0x140004cad  mov     r14d, 2
0x140004cb3  mov     edx, r14d
0x140004cb6  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140004cbb  cmp     rax, 100h
0x140004cc1  jbe     short loc_140004CDD
0x140004cc3  mov     rdx, rax
0x140004cc6  lea     rcx, [rsp+21D8h+var_2158]
0x140004cce  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140004cd3  mov     rdi, [rsp+21D8h+var_2158]
0x140004cdb  jmp     short loc_140004CED
0x140004cdd  lea     rdi, [rsp+21D8h+var_2150]
0x140004ce5  mov     [rsp+21D8h+var_2158], rdi
0x140004ced  jmp     short loc_140004D11
0x140004cef  xor     ebx, ebx
0x140004cf1  lea     r14d, [rbx+2]
0x140004cf5  mov     rdi, [rsp+21D8h+var_2158]
0x140004cfd  mov     rax, [rsp+21D8h+var_2190]
0x140004d02  mov     [rsp+21D8h+var_2198], rax
0x140004d07  mov     r12, [rsp+21D8h+var_2188]
0x140004d0c  mov     r13, [rsp+21D8h+var_2178]
0x140004d11  test    rdi, rdi
0x140004d14  jz      short loc_140004D82
0x140004d16  lea     rsi, [rsp+21D8h+String1]
0x140004d1e  cmp     [rsp+21D8h+String1], bx
0x140004d26  jz      short loc_140004D65
0x140004d28  mov     r15d, 30h ; '0'
0x140004d2e  mov     rcx, rsi; lpsz
0x140004d31  call    cs:__imp_CharNextW
0x140004d37  movzx   ecx, word ptr [rsi]
0x140004d3a  cmp     cx, 5Ch ; '\'
0x140004d3e  jnz     short loc_140004D57
0x140004d40  cmp     [rax], r15w
0x140004d44  jnz     short loc_140004D57
0x140004d46  mov     [rdi], bx
0x140004d49  mov     rcx, rax; lpsz
0x140004d4c  call    cs:__imp_CharNextW
0x140004d52  mov     rsi, rax
0x140004d55  jmp     short loc_140004D5D
0x140004d57  mov     [rdi], cx
0x140004d5a  add     rsi, r14
0x140004d5d  add     rdi, r14
0x140004d60  cmp     [rsi], bx
0x140004d63  jnz     short loc_140004D2E
0x140004d65  mov     dword ptr [rdi], 0
0x140004d6b  mov     r8, [rsp+21D8h+var_2158]; wchar_t *
0x140004d73  mov     rdx, r13; wchar_t *
0x140004d76  mov     rcx, r12; this
0x140004d79  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEB_W0@Z; ATL::CRegKey::SetMultiStringValue(wchar_t const *,wchar_t const *)
0x140004d7e  mov     edi, eax
0x140004d80  jmp     short loc_140004D87
0x140004d82  mov     edi, 0Eh
0x140004d87  lea     rcx, [rsp+21D8h+var_2158]
0x140004d8f  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x140004d94  mov     r14, [rsp+21D8h+var_2198]
0x140004d99  jmp     loc_14000504F
0x140004d9e  mov     [rsp+21D8h+pulOut], ebx
0x140004da2  mov     [rsp+21D8h+var_2198], rbx
0x140004da7  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x140004dac  xor     r8d, r8d; dwFlags
0x140004daf  xor     edx, edx; lcid
0x140004db1  lea     rcx, [rsp+21D8h+String1]; strIn
0x140004db9  call    cs:__imp_VarUI4FromStr
0x140004dbf  mov     edi, eax
0x140004dc1  test    eax, eax
0x140004dc3  jns     short loc_140004DD6
0x140004dc5  lea     rcx, [rsp+21D8h+var_2198]
0x140004dca  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140004dcf  mov     eax, edi
0x140004dd1  jmp     loc_140005077
0x140004dd6  mov     eax, [rsp+21D8h+pulOut]
0x140004dda  mov     dword ptr [rsp+21D8h+Data], eax
0x140004dde  mov     [rsp+21D8h+cbData], 4; cbData
0x140004de6  lea     rax, [rsp+21D8h+Data]
0x140004deb  mov     [rsp+21D8h+lpData], rax; lpData
0x140004df0  mov     r9d, 4; dwType
0x140004df6  xor     r8d, r8d; Reserved
0x140004df9  mov     rdx, r13; lpValueName
0x140004dfc  mov     rcx, [r12]; hKey
0x140004e00  call    cs:__imp_RegSetValueExW
0x140004e06  mov     edi, eax
0x140004e08  lea     rcx, [rsp+21D8h+var_2198]
0x140004e0d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140004e12  jmp     loc_14000504F
0x140004e17  lea     rax, [rsp+21D8h+String1]
0x140004e1f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140004e23  inc     rdi
0x140004e26  cmp     [rax+rdi*2], bx
0x140004e2a  jnz     short loc_140004E23
0x140004e2c  mov     dword ptr [rsp+21D8h+Data], edi
0x140004e30  test    dil, 1
0x140004e34  jz      short loc_140004E40
0x140004e36  mov     eax, 80004005h
0x140004e3b  jmp     loc_140005077
0x140004e40  mov     eax, edi
0x140004e42  cdq
0x140004e43  mov     r14d, 2
0x140004e49  idiv    r14d
0x140004e4c  movsxd  r14, eax
0x140004e4f  mov     [rsp+21D8h+var_2158], rbx
0x140004e57  mov     rsi, r14
0x140004e5a  mov     [rsp+21D8h+var_2168], r14
0x140004e5f  mov     edx, 1
0x140004e64  mov     rcx, r14
0x140004e67  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140004e6c  cmp     rax, 100h
0x140004e72  jbe     short loc_140004E8E
0x140004e74  mov     rdx, rax
0x140004e77  lea     rcx, [rsp+21D8h+var_2158]
0x140004e7f  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140004e84  mov     rcx, [rsp+21D8h+var_2158]
0x140004e8c  jmp     short loc_140004E9E
0x140004e8e  lea     rcx, [rsp+21D8h+var_2150]
0x140004e96  mov     [rsp+21D8h+var_2158], rcx
0x140004e9e  jmp     short loc_140004ECA
0x140004ea0  xor     ebx, ebx
0x140004ea2  mov     edi, dword ptr [rsp+21D8h+Data]
0x140004ea6  mov     rcx, [rsp+21D8h+var_2158]; void *
0x140004eae  mov     rsi, [rsp+21D8h+var_2168]
0x140004eb3  mov     rax, [rsp+21D8h+var_2190]
0x140004eb8  mov     [rsp+21D8h+var_2198], rax
0x140004ebd  mov     r12, [rsp+21D8h+var_2188]
0x140004ec2  mov     r13, [rsp+21D8h+var_2178]
0x140004ec7  mov     r14d, esi
0x140004eca  test    rcx, rcx
0x140004ecd  jnz     short loc_140004EE1
0x140004ecf  lea     rcx, [rsp+21D8h+var_2158]
0x140004ed7  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x140004edc  jmp     loc_140004E36
0x140004ee1  mov     r8, rsi; Size
0x140004ee4  xor     edx, edx; Val
0x140004ee6  call    memset_0
0x140004eeb  mov     r10d, ebx
0x140004eee  test    edi, edi
0x140004ef0  jle     loc_140004FCE
0x140004ef6  mov     r15d, 30h ; '0'
0x140004efc  mov     eax, r10d
0x140004eff  movzx   edx, [rsp+rax*2+21D8h+String1]
0x140004f07  cmp     edx, 61h ; 'a'
0x140004f0a  ja      short loc_140004F79
0x140004f0c  jz      loc_140004F99
0x140004f12  cmp     edx, 38h ; '8'
0x140004f15  ja      short loc_140004F4B
0x140004f17  jz      short loc_140004F43
0x140004f19  mov     ecx, edx
0x140004f1b  sub     ecx, r15d
0x140004f1e  jz      short loc_140004F43
0x140004f20  sub     ecx, 1
0x140004f23  jz      short loc_140004F43
0x140004f25  sub     ecx, 1
0x140004f28  jz      short loc_140004F43
0x140004f2a  sub     ecx, 1
0x140004f2d  jz      short loc_140004F43
0x140004f2f  sub     ecx, 1
0x140004f32  jz      short loc_140004F43
0x140004f34  sub     ecx, 1
0x140004f37  jz      short loc_140004F43
0x140004f39  sub     ecx, 1
0x140004f3c  jz      short loc_140004F43
0x140004f3e  cmp     ecx, 1
0x140004f41  jnz     short loc_140004F94
0x140004f43  mov     r9d, edx
0x140004f46  sub     r9d, r15d
0x140004f49  jmp     short loc_140004F9D
0x140004f4b  mov     r9d, edx
0x140004f4e  mov     ecx, edx
0x140004f50  sub     ecx, 39h ; '9'
0x140004f53  jz      short loc_140004F43
0x140004f55  sub     ecx, 8
0x140004f58  jz      short loc_140004F73
0x140004f5a  sub     ecx, 1
0x140004f5d  jz      short loc_140004F73
0x140004f5f  sub     ecx, 1
0x140004f62  jz      short loc_140004F73
0x140004f64  sub     ecx, 1
0x140004f67  jz      short loc_140004F73
0x140004f69  sub     ecx, 1
0x140004f6c  jz      short loc_140004F73
0x140004f6e  cmp     ecx, 1
0x140004f71  jnz     short loc_140004F94
0x140004f73  add     r9d, 0FFFFFFC9h
0x140004f77  jmp     short loc_140004F9D
0x140004f79  mov     ecx, edx
0x140004f7b  sub     ecx, 62h ; 'b'
0x140004f7e  jz      short loc_140004F99
0x140004f80  sub     ecx, 1
0x140004f83  jz      short loc_140004F99
0x140004f85  sub     ecx, 1
0x140004f88  jz      short loc_140004F99
0x140004f8a  sub     ecx, 1
0x140004f8d  jz      short loc_140004F99
0x140004f8f  cmp     ecx, 1
0x140004f92  jz      short loc_140004F99
0x140004f94  mov     r9d, ebx
0x140004f97  jmp     short loc_140004F9D
0x140004f99  lea     r9d, [rdx-57h]
0x140004f9d  mov     r8d, r10d
0x140004fa0  shr     r8, 1
0x140004fa3  mov     rdx, [rsp+21D8h+var_2158]
0x140004fab  mov     eax, r10d
0x140004fae  and     eax, 1
0x140004fb1  shl     eax, 2
0x140004fb4  mov     ecx, 4
0x140004fb9  sub     ecx, eax
0x140004fbb  shl     r9b, cl
0x140004fbe  or      [r8+rdx], r9b
0x140004fc2  inc     r10d
0x140004fc5  cmp     r10d, edi
0x140004fc8  jl      loc_140004EFC
0x140004fce  mov     rax, [rsp+21D8h+var_2158]
0x140004fd6  mov     [rsp+21D8h+cbData], r14d; cbData
0x140004fdb  mov     [rsp+21D8h+lpData], rax; lpData
0x140004fe0  mov     r9d, 3; dwType
0x140004fe6  xor     r8d, r8d; Reserved
0x140004fe9  mov     rdx, r13; lpValueName
0x140004fec  mov     rcx, [r12]; hKey
0x140004ff0  call    cs:__imp_RegSetValueExW
0x140004ff6  mov     edi, eax
0x140004ff8  lea     rcx, [rsp+21D8h+var_2158]
0x140005000  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x140005005  jmp     loc_140004D94
0x14000500a  lea     rax, [rsp+21D8h+String1]
0x140005012  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140005016  inc     rdi
0x140005019  cmp     [rax+rdi*2], bx
0x14000501d  jnz     short loc_140005016
0x14000501f  lea     eax, ds:2[rdi*2]
0x140005026  mov     [rsp+21D8h+cbData], eax; cbData
0x14000502a  lea     rax, [rsp+21D8h+String1]
0x140005032  mov     [rsp+21D8h+lpData], rax; lpData
0x140005037  mov     r9d, 1; dwType
0x14000503d  xor     r8d, r8d; Reserved
0x140005040  mov     rdx, r13; lpValueName
0x140005043  mov     rcx, [r12]; hKey
0x140005047  call    cs:__imp_RegSetValueExW
0x14000504d  mov     edi, eax
  ... truncated ...
```
