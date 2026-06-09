# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180077ac0`
- end: `0x180077f99`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1241`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180078f90`

## callees

- `0x18004b630`
- `0x18004c1c8`
- `0x1800774fc`
- `0x180077534`
- `0x1800775e0`
- `0x180077ac0`
- `0x180077fa0`
- `0x180078188`
- `0x1800781a0`
- `0x180078214`
- `0x180078658`
- `0x1800796a4`
- `0x180082000`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077d8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077ee2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077f3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077cee`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077d8d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077ee2`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180077f3f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077c5f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077c81`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077c5f`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180077c81`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180077b4d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180077b4d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180077d40`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180077d40`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180077ac0  push    rbx
0x180077ac2  push    rsi
0x180077ac3  push    rdi
0x180077ac4  push    r12
0x180077ac6  push    r13
0x180077ac8  push    r14
0x180077aca  push    r15
0x180077acc  mov     eax, 21A0h
0x180077ad1  call    _alloca_probe
0x180077ad6  sub     rsp, rax
0x180077ad9  mov     rax, cs:__security_cookie
0x180077ae0  xor     rax, rsp
0x180077ae3  mov     [rsp+21D8h+var_48], rax
0x180077aeb  mov     r13, r8
0x180077aee  mov     r12, rdx
0x180077af1  mov     r14, rcx
0x180077af4  mov     [rsp+21D8h+var_21A0], rcx
0x180077af9  mov     qword ptr [rsp+21D8h+Data], rdx
0x180077afe  mov     [rsp+21D8h+var_2190], rcx
0x180077b03  mov     [rsp+21D8h+var_2170], rdx
0x180077b08  mov     [rsp+21D8h+var_2188], r8
0x180077b0d  mov     [rsp+21D8h+var_2168], r9
0x180077b12  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180077b1a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180077b1f  xor     ebx, ebx
0x180077b21  test    eax, eax
0x180077b23  js      loc_180077F75
0x180077b29  mov     edi, ebx
0x180077b2b  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180077b32  cmp     edi, 4
0x180077b35  jnb     loc_180077F70
0x180077b3b  movsxd  rsi, edi
0x180077b3e  add     rsi, rsi
0x180077b41  mov     rdx, [r15+rsi*8]; lpString2
0x180077b45  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180077b4d  call    cs:__imp_lstrcmpiW
0x180077b54  nop     dword ptr [rax+rax+00h]
0x180077b59  test    eax, eax
0x180077b5b  jz      short loc_180077B61
0x180077b5d  inc     edi
0x180077b5f  jmp     short loc_180077B32
0x180077b61  movzx   edi, word ptr [r15+rsi*8+8]
0x180077b67  mov     rcx, r14; this
0x180077b6a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180077b6f  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180077b77  mov     rcx, r14; this
0x180077b7a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180077b7f  test    eax, eax
0x180077b81  js      loc_180077F75
0x180077b87  cmp     di, 8
0x180077b8b  jz      loc_180077F02
0x180077b91  cmp     di, 11h
0x180077b95  jz      loc_180077DAA
0x180077b9b  cmp     di, 13h
0x180077b9f  jz      loc_180077D25
0x180077ba5  mov     eax, 4008h
0x180077baa  cmp     di, ax
0x180077bad  jnz     loc_180077F5A
0x180077bb3  lea     rcx, [rsp+21D8h+String1]
0x180077bbb  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077bbf  mov     rax, rdi
0x180077bc2  inc     rax
0x180077bc5  cmp     [rcx+rax*2], bx
0x180077bc9  jnz     short loc_180077BC2
0x180077bcb  add     eax, 2
0x180077bce  mov     [rsp+21D8h+var_2158], rbx
0x180077bd6  movsxd  rcx, eax
0x180077bd9  mov     r15d, 2
0x180077bdf  mov     edx, r15d
0x180077be2  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180077be7  cmp     rax, 100h
0x180077bed  jbe     short loc_180077C09
0x180077bef  mov     rdx, rax
0x180077bf2  lea     rcx, [rsp+21D8h+var_2158]
0x180077bfa  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180077bff  mov     rsi, [rsp+21D8h+var_2158]
0x180077c07  jmp     short loc_180077C19
0x180077c09  lea     rsi, [rsp+21D8h+var_2150]
0x180077c11  mov     [rsp+21D8h+var_2158], rsi
0x180077c19  jmp     short loc_180077C41
0x180077c1b  xor     ebx, ebx
0x180077c1d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077c21  lea     r15d, [rbx+2]
0x180077c25  mov     rsi, [rsp+21D8h+var_2158]
0x180077c2d  mov     r12, qword ptr [rsp+21D8h+Data]
0x180077c32  mov     rax, [rsp+21D8h+var_2190]
0x180077c37  mov     [rsp+21D8h+var_21A0], rax
0x180077c3c  mov     r13, [rsp+21D8h+var_2188]
0x180077c41  test    rsi, rsi
0x180077c44  jz      loc_180077D09
0x180077c4a  lea     r14, [rsp+21D8h+String1]
0x180077c52  cmp     [rsp+21D8h+String1], bx
0x180077c5a  jz      short loc_180077CA1
0x180077c5c  mov     rcx, r14; lpsz
0x180077c5f  call    cs:__imp_CharNextW
0x180077c66  nop     dword ptr [rax+rax+00h]
0x180077c6b  movzx   ecx, word ptr [r14]
0x180077c6f  cmp     cx, 5Ch ; '\'
0x180077c73  jnz     short loc_180077C92
0x180077c75  cmp     word ptr [rax], 30h ; '0'
0x180077c79  jnz     short loc_180077C92
0x180077c7b  mov     [rsi], bx
0x180077c7e  mov     rcx, rax; lpsz
0x180077c81  call    cs:__imp_CharNextW
0x180077c88  nop     dword ptr [rax+rax+00h]
0x180077c8d  mov     r14, rax
0x180077c90  jmp     short loc_180077C98
0x180077c92  mov     [rsi], cx
0x180077c95  add     r14, r15
0x180077c98  add     rsi, r15
0x180077c9b  cmp     [r14], bx
0x180077c9f  jnz     short loc_180077C5C
0x180077ca1  mov     dword ptr [rsi], 0
0x180077ca7  mov     r8, [rsp+21D8h+var_2158]
0x180077caf  test    r8, r8
0x180077cb2  jz      short loc_180077CFE
0x180077cb4  mov     r10d, ebx
0x180077cb7  mov     r9, r8
0x180077cba  mov     rcx, rdi
0x180077cbd  inc     rcx
0x180077cc0  cmp     [r9+rcx*2], bx
0x180077cc5  jnz     short loc_180077CBD
0x180077cc7  inc     ecx
0x180077cc9  lea     r9, [r9+rcx*2]
0x180077ccd  lea     r10d, [r10+rcx*2]
0x180077cd1  cmp     ecx, 1
0x180077cd4  jnz     short loc_180077CBA
0x180077cd6  mov     [rsp+21D8h+cbData], r10d; cbData
0x180077cdb  mov     [rsp+21D8h+lpData], r8; lpData
0x180077ce0  lea     r9d, [rcx+6]; dwType
0x180077ce4  xor     r8d, r8d; Reserved
0x180077ce7  mov     rdx, r13; lpValueName
0x180077cea  mov     rcx, [r12]; hKey
0x180077cee  call    cs:__imp_RegSetValueExW
0x180077cf5  nop     dword ptr [rax+rax+00h]
0x180077cfa  mov     edi, eax
0x180077cfc  jmp     short loc_180077D0E
0x180077cfe  mov     ecx, 80004005h; int
0x180077d03  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180077d09  mov     edi, 0Eh
0x180077d0e  lea     rcx, [rsp+21D8h+var_2158]
0x180077d16  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180077d1b  mov     r14, [rsp+21D8h+var_21A0]
0x180077d20  jmp     loc_180077F4D
0x180077d25  mov     [rsp+21D8h+pulOut], ebx
0x180077d29  mov     [rsp+21D8h+var_21A0], rbx
0x180077d2e  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x180077d33  xor     r8d, r8d; dwFlags
0x180077d36  xor     edx, edx; lcid
0x180077d38  lea     rcx, [rsp+21D8h+String1]; strIn
0x180077d40  call    cs:__imp_VarUI4FromStr
0x180077d47  nop     dword ptr [rax+rax+00h]
0x180077d4c  mov     edi, eax
0x180077d4e  test    eax, eax
0x180077d50  jns     short loc_180077D63
0x180077d52  lea     rcx, [rsp+21D8h+var_21A0]
0x180077d57  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180077d5c  mov     eax, edi
0x180077d5e  jmp     loc_180077F75
0x180077d63  mov     eax, [rsp+21D8h+pulOut]
0x180077d67  mov     dword ptr [rsp+21D8h+Data], eax
0x180077d6b  mov     [rsp+21D8h+cbData], 4; cbData
0x180077d73  lea     rax, [rsp+21D8h+Data]
0x180077d78  mov     [rsp+21D8h+lpData], rax; lpData
0x180077d7d  mov     r9d, 4; dwType
0x180077d83  xor     r8d, r8d; Reserved
0x180077d86  mov     rdx, r13; lpValueName
0x180077d89  mov     rcx, [r12]; hKey
0x180077d8d  call    cs:__imp_RegSetValueExW
0x180077d94  nop     dword ptr [rax+rax+00h]
0x180077d99  mov     edi, eax
0x180077d9b  lea     rcx, [rsp+21D8h+var_21A0]
0x180077da0  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180077da5  jmp     loc_180077F4D
0x180077daa  lea     rax, [rsp+21D8h+String1]
0x180077db2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077db6  inc     rdi
0x180077db9  cmp     [rax+rdi*2], bx
0x180077dbd  jnz     short loc_180077DB6
0x180077dbf  mov     dword ptr [rsp+21D8h+Data], edi
0x180077dc3  test    dil, 1
0x180077dc7  jz      short loc_180077DD3
0x180077dc9  mov     eax, 80004005h
0x180077dce  jmp     loc_180077F75
0x180077dd3  mov     eax, edi
0x180077dd5  cdq
0x180077dd6  mov     r15d, 2
0x180077ddc  idiv    r15d
0x180077ddf  movsxd  r14, eax
0x180077de2  mov     [rsp+21D8h+var_2158], rbx
0x180077dea  mov     rsi, r14
0x180077ded  mov     [rsp+21D8h+var_2178], r14
0x180077df2  lea     edx, [r15-1]
0x180077df6  mov     rcx, r14
0x180077df9  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180077dfe  cmp     rax, 100h
0x180077e04  jbe     short loc_180077E20
0x180077e06  mov     rdx, rax
0x180077e09  lea     rcx, [rsp+21D8h+var_2158]
0x180077e11  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180077e16  mov     rcx, [rsp+21D8h+var_2158]
0x180077e1e  jmp     short loc_180077E30
0x180077e20  lea     rcx, [rsp+21D8h+var_2150]
0x180077e28  mov     [rsp+21D8h+var_2158], rcx
0x180077e30  jmp     short loc_180077E5C
0x180077e32  xor     ebx, ebx
0x180077e34  mov     edi, dword ptr [rsp+21D8h+Data]
0x180077e38  mov     rcx, [rsp+21D8h+var_2158]; void *
0x180077e40  mov     rsi, [rsp+21D8h+var_2178]
0x180077e45  mov     rax, [rsp+21D8h+var_2190]
0x180077e4a  mov     [rsp+21D8h+var_21A0], rax
0x180077e4f  mov     r12, [rsp+21D8h+var_2170]
0x180077e54  mov     r13, [rsp+21D8h+var_2188]
0x180077e59  mov     r14d, esi
0x180077e5c  test    rcx, rcx
0x180077e5f  jnz     short loc_180077E73
0x180077e61  lea     rcx, [rsp+21D8h+var_2158]
0x180077e69  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180077e6e  jmp     loc_180077DC9
0x180077e73  mov     r8, rsi; Size
0x180077e76  xor     edx, edx; Val
0x180077e78  call    memset_0
0x180077e7d  mov     r10d, ebx
0x180077e80  test    edi, edi
0x180077e82  jle     short loc_180077EC0
0x180077e84  mov     r9d, r10d
0x180077e87  shr     r9, 1
0x180077e8a  mov     r8, [rsp+21D8h+var_2158]
0x180077e92  mov     ecx, r10d
0x180077e95  movzx   ecx, [rsp+rcx*2+21D8h+String1]; unsigned __int16
0x180077e9d  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180077ea2  mov     edx, r10d
0x180077ea5  and     edx, 1
0x180077ea8  shl     edx, 2
0x180077eab  mov     ecx, 4
0x180077eb0  sub     ecx, edx
0x180077eb2  shl     al, cl
0x180077eb4  or      [r9+r8], al
0x180077eb8  inc     r10d
0x180077ebb  cmp     r10d, edi
0x180077ebe  jl      short loc_180077E84
0x180077ec0  mov     rax, [rsp+21D8h+var_2158]
0x180077ec8  mov     [rsp+21D8h+cbData], r14d; cbData
0x180077ecd  mov     [rsp+21D8h+lpData], rax; lpData
0x180077ed2  mov     r9d, 3; dwType
0x180077ed8  xor     r8d, r8d; Reserved
0x180077edb  mov     rdx, r13; lpValueName
0x180077ede  mov     rcx, [r12]; hKey
0x180077ee2  call    cs:__imp_RegSetValueExW
0x180077ee9  nop     dword ptr [rax+rax+00h]
0x180077eee  mov     edi, eax
0x180077ef0  lea     rcx, [rsp+21D8h+var_2158]
0x180077ef8  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180077efd  jmp     loc_180077D1B
0x180077f02  lea     rax, [rsp+21D8h+String1]
0x180077f0a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077f0e  inc     rdi
0x180077f11  cmp     [rax+rdi*2], bx
0x180077f15  jnz     short loc_180077F0E
0x180077f17  lea     eax, ds:2[rdi*2]
0x180077f1e  mov     [rsp+21D8h+cbData], eax; cbData
0x180077f22  lea     rax, [rsp+21D8h+String1]
0x180077f2a  mov     [rsp+21D8h+lpData], rax; lpData
0x180077f2f  mov     r9d, 1; dwType
0x180077f35  xor     r8d, r8d; Reserved
0x180077f38  mov     rdx, r13; lpValueName
0x180077f3b  mov     rcx, [r12]; hKey
0x180077f3f  call    cs:__imp_RegSetValueExW
0x180077f46  nop     dword ptr [rax+rax+00h]
0x180077f4b  mov     edi, eax
0x180077f4d  test    edi, edi
0x180077f4f  jz      short loc_180077F5A
0x180077f51  mov     ecx, edi; unsigned int
0x180077f53  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180077f58  jmp     short loc_180077F75
0x180077f5a  mov     rdx, [rsp+21D8h+var_2168]; unsigned __int16 *
0x180077f5f  mov     rcx, r14; this
0x180077f62  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180077f67  test    eax, eax
0x180077f69  cmovs   ebx, eax
0x180077f6c  mov     eax, ebx
0x180077f6e  jmp     short loc_180077F75
0x180077f70  mov     eax, 80020009h
0x180077f75  mov     rcx, [rsp+21D8h+var_48]
0x180077f7d  xor     rcx, rsp; StackCookie
0x180077f80  call    __security_check_cookie
0x180077f85  add     rsp, 21A0h
0x180077f8c  pop     r15
0x180077f8e  pop     r14
0x180077f90  pop     r13
0x180077f92  pop     r12
0x180077f94  pop     rdi
0x180077f95  pop     rsi
0x180077f96  pop     rbx
0x180077f97  retn
```
