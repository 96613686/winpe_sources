# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800103a8`
- end: `0x180010881`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1241`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180014770`

## callees

- `0x180008de0`
- `0x180009cc4`
- `0x18000e6e0`
- `0x18000e784`
- `0x18000f0a8`
- `0x1800103a8`
- `0x180010888`
- `0x180010b14`
- `0x180010c0c`
- `0x180010c80`
- `0x180013480`
- `0x1800150f0`
- `0x180100500`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x180010628`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180010628`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010547`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010569`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010547`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180010569`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800105d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010675`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800107ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010827`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800105d6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010675`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800107ca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180010827`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010435`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180010435`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
0x1800103a8  push    rbx
0x1800103aa  push    rsi
0x1800103ab  push    rdi
0x1800103ac  push    r12
0x1800103ae  push    r13
0x1800103b0  push    r14
0x1800103b2  push    r15
0x1800103b4  mov     eax, 21A0h
0x1800103b9  call    _alloca_probe
0x1800103be  sub     rsp, rax
0x1800103c1  mov     rax, cs:__security_cookie
0x1800103c8  xor     rax, rsp
0x1800103cb  mov     [rsp+21D8h+var_48], rax
0x1800103d3  mov     r13, r8
0x1800103d6  mov     r12, rdx
0x1800103d9  mov     r14, rcx
0x1800103dc  mov     [rsp+21D8h+var_21A0], rcx
0x1800103e1  mov     qword ptr [rsp+21D8h+Data], rdx
0x1800103e6  mov     [rsp+21D8h+var_2190], rcx
0x1800103eb  mov     [rsp+21D8h+var_2170], rdx
0x1800103f0  mov     [rsp+21D8h+var_2188], r8
0x1800103f5  mov     [rsp+21D8h+var_2168], r9
0x1800103fa  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x180010402  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010407  xor     ebx, ebx
0x180010409  test    eax, eax
0x18001040b  js      loc_18001085D
0x180010411  mov     edi, ebx
0x180010413  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001041a  cmp     edi, 4
0x18001041d  jnb     loc_180010858
0x180010423  movsxd  rsi, edi
0x180010426  add     rsi, rsi
0x180010429  mov     rdx, [r15+rsi*8]; lpString2
0x18001042d  lea     rcx, [rsp+21D8h+String1]; lpString1
0x180010435  call    cs:__imp_lstrcmpiW
0x18001043c  nop     dword ptr [rax+rax+00h]
0x180010441  test    eax, eax
0x180010443  jz      short loc_180010449
0x180010445  inc     edi
0x180010447  jmp     short loc_18001041A
0x180010449  movzx   edi, word ptr [r15+rsi*8+8]
0x18001044f  mov     rcx, r14; this
0x180010452  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180010457  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x18001045f  mov     rcx, r14; this
0x180010462  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180010467  test    eax, eax
0x180010469  js      loc_18001085D
0x18001046f  cmp     di, 8
0x180010473  jz      loc_1800107EA
0x180010479  cmp     di, 11h
0x18001047d  jz      loc_180010692
0x180010483  cmp     di, 13h
0x180010487  jz      loc_18001060D
0x18001048d  mov     eax, 4008h
0x180010492  cmp     di, ax
0x180010495  jnz     loc_180010842
0x18001049b  lea     rcx, [rsp+21D8h+String1]
0x1800104a3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800104a7  mov     rax, rdi
0x1800104aa  inc     rax
0x1800104ad  cmp     [rcx+rax*2], bx
0x1800104b1  jnz     short loc_1800104AA
0x1800104b3  add     eax, 2
0x1800104b6  mov     [rsp+21D8h+var_2158], rbx
0x1800104be  movsxd  rcx, eax
0x1800104c1  mov     r15d, 2
0x1800104c7  mov     edx, r15d
0x1800104ca  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800104cf  cmp     rax, 100h
0x1800104d5  jbe     short loc_1800104F1
0x1800104d7  mov     rdx, rax
0x1800104da  lea     rcx, [rsp+21D8h+var_2158]
0x1800104e2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800104e7  mov     rsi, [rsp+21D8h+var_2158]
0x1800104ef  jmp     short loc_180010501
0x1800104f1  lea     rsi, [rsp+21D8h+var_2150]
0x1800104f9  mov     [rsp+21D8h+var_2158], rsi
0x180010501  jmp     short loc_180010529
0x180010503  xor     ebx, ebx
0x180010505  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180010509  lea     r15d, [rbx+2]
0x18001050d  mov     rsi, [rsp+21D8h+var_2158]
0x180010515  mov     r12, qword ptr [rsp+21D8h+Data]
0x18001051a  mov     rax, [rsp+21D8h+var_2190]
0x18001051f  mov     [rsp+21D8h+var_21A0], rax
0x180010524  mov     r13, [rsp+21D8h+var_2188]
0x180010529  test    rsi, rsi
0x18001052c  jz      loc_1800105F1
0x180010532  lea     r14, [rsp+21D8h+String1]
0x18001053a  cmp     [rsp+21D8h+String1], bx
0x180010542  jz      short loc_180010589
0x180010544  mov     rcx, r14; lpsz
0x180010547  call    cs:__imp_CharNextW
0x18001054e  nop     dword ptr [rax+rax+00h]
0x180010553  movzx   ecx, word ptr [r14]
0x180010557  cmp     cx, 5Ch ; '\'
0x18001055b  jnz     short loc_18001057A
0x18001055d  cmp     word ptr [rax], 30h ; '0'
0x180010561  jnz     short loc_18001057A
0x180010563  mov     [rsi], bx
0x180010566  mov     rcx, rax; lpsz
0x180010569  call    cs:__imp_CharNextW
0x180010570  nop     dword ptr [rax+rax+00h]
0x180010575  mov     r14, rax
0x180010578  jmp     short loc_180010580
0x18001057a  mov     [rsi], cx
0x18001057d  add     r14, r15
0x180010580  add     rsi, r15
0x180010583  cmp     [r14], bx
0x180010587  jnz     short loc_180010544
0x180010589  mov     dword ptr [rsi], 0
0x18001058f  mov     r8, [rsp+21D8h+var_2158]
0x180010597  test    r8, r8
0x18001059a  jz      short loc_1800105E6
0x18001059c  mov     r10d, ebx
0x18001059f  mov     r9, r8
0x1800105a2  mov     rcx, rdi
0x1800105a5  inc     rcx
0x1800105a8  cmp     [r9+rcx*2], bx
0x1800105ad  jnz     short loc_1800105A5
0x1800105af  inc     ecx
0x1800105b1  lea     r9, [r9+rcx*2]
0x1800105b5  lea     r10d, [r10+rcx*2]
0x1800105b9  cmp     ecx, 1
0x1800105bc  jnz     short loc_1800105A2
0x1800105be  mov     [rsp+21D8h+cbData], r10d; cbData
0x1800105c3  mov     [rsp+21D8h+lpData], r8; lpData
0x1800105c8  lea     r9d, [rcx+6]; dwType
0x1800105cc  xor     r8d, r8d; Reserved
0x1800105cf  mov     rdx, r13; lpValueName
0x1800105d2  mov     rcx, [r12]; hKey
0x1800105d6  call    cs:__imp_RegSetValueExW
0x1800105dd  nop     dword ptr [rax+rax+00h]
0x1800105e2  mov     edi, eax
0x1800105e4  jmp     short loc_1800105F6
0x1800105e6  mov     ecx, 80004005h; int
0x1800105eb  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800105f1  mov     edi, 0Eh
0x1800105f6  lea     rcx, [rsp+21D8h+var_2158]
0x1800105fe  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180010603  mov     r14, [rsp+21D8h+var_21A0]
0x180010608  jmp     loc_180010835
0x18001060d  mov     [rsp+21D8h+pulOut], ebx
0x180010611  mov     [rsp+21D8h+var_21A0], rbx
0x180010616  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x18001061b  xor     r8d, r8d; dwFlags
0x18001061e  xor     edx, edx; lcid
0x180010620  lea     rcx, [rsp+21D8h+String1]; strIn
0x180010628  call    cs:__imp_VarUI4FromStr
0x18001062f  nop     dword ptr [rax+rax+00h]
0x180010634  mov     edi, eax
0x180010636  test    eax, eax
0x180010638  jns     short loc_18001064B
0x18001063a  lea     rcx, [rsp+21D8h+var_21A0]
0x18001063f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180010644  mov     eax, edi
0x180010646  jmp     loc_18001085D
0x18001064b  mov     eax, [rsp+21D8h+pulOut]
0x18001064f  mov     dword ptr [rsp+21D8h+Data], eax
0x180010653  mov     [rsp+21D8h+cbData], 4; cbData
0x18001065b  lea     rax, [rsp+21D8h+Data]
0x180010660  mov     [rsp+21D8h+lpData], rax; lpData
0x180010665  mov     r9d, 4; dwType
0x18001066b  xor     r8d, r8d; Reserved
0x18001066e  mov     rdx, r13; lpValueName
0x180010671  mov     rcx, [r12]; hKey
0x180010675  call    cs:__imp_RegSetValueExW
0x18001067c  nop     dword ptr [rax+rax+00h]
0x180010681  mov     edi, eax
0x180010683  lea     rcx, [rsp+21D8h+var_21A0]
0x180010688  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001068d  jmp     loc_180010835
0x180010692  lea     rax, [rsp+21D8h+String1]
0x18001069a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001069e  inc     rdi
0x1800106a1  cmp     [rax+rdi*2], bx
0x1800106a5  jnz     short loc_18001069E
0x1800106a7  mov     dword ptr [rsp+21D8h+Data], edi
0x1800106ab  test    dil, 1
0x1800106af  jz      short loc_1800106BB
0x1800106b1  mov     eax, 80004005h
0x1800106b6  jmp     loc_18001085D
0x1800106bb  mov     eax, edi
0x1800106bd  cdq
0x1800106be  mov     r15d, 2
0x1800106c4  idiv    r15d
0x1800106c7  movsxd  r14, eax
0x1800106ca  mov     [rsp+21D8h+var_2158], rbx
0x1800106d2  mov     rsi, r14
0x1800106d5  mov     [rsp+21D8h+var_2178], r14
0x1800106da  lea     edx, [r15-1]
0x1800106de  mov     rcx, r14
0x1800106e1  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800106e6  cmp     rax, 100h
0x1800106ec  jbe     short loc_180010708
0x1800106ee  mov     rdx, rax
0x1800106f1  lea     rcx, [rsp+21D8h+var_2158]
0x1800106f9  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800106fe  mov     rcx, [rsp+21D8h+var_2158]
0x180010706  jmp     short loc_180010718
0x180010708  lea     rcx, [rsp+21D8h+var_2150]
0x180010710  mov     [rsp+21D8h+var_2158], rcx
0x180010718  jmp     short loc_180010744
0x18001071a  xor     ebx, ebx
0x18001071c  mov     edi, dword ptr [rsp+21D8h+Data]
0x180010720  mov     rcx, [rsp+21D8h+var_2158]; void *
0x180010728  mov     rsi, [rsp+21D8h+var_2178]
0x18001072d  mov     rax, [rsp+21D8h+var_2190]
0x180010732  mov     [rsp+21D8h+var_21A0], rax
0x180010737  mov     r12, [rsp+21D8h+var_2170]
0x18001073c  mov     r13, [rsp+21D8h+var_2188]
0x180010741  mov     r14d, esi
0x180010744  test    rcx, rcx
0x180010747  jnz     short loc_18001075B
0x180010749  lea     rcx, [rsp+21D8h+var_2158]
0x180010751  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180010756  jmp     loc_1800106B1
0x18001075b  mov     r8, rsi; Size
0x18001075e  xor     edx, edx; Val
0x180010760  call    memset_0
0x180010765  mov     r10d, ebx
0x180010768  test    edi, edi
0x18001076a  jle     short loc_1800107A8
0x18001076c  mov     r9d, r10d
0x18001076f  shr     r9, 1
0x180010772  mov     r8, [rsp+21D8h+var_2158]
0x18001077a  mov     ecx, r10d
0x18001077d  movzx   ecx, [rsp+rcx*2+21D8h+String1]; unsigned __int16
0x180010785  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18001078a  mov     edx, r10d
0x18001078d  and     edx, 1
0x180010790  shl     edx, 2
0x180010793  mov     ecx, 4
0x180010798  sub     ecx, edx
0x18001079a  shl     al, cl
0x18001079c  or      [r9+r8], al
0x1800107a0  inc     r10d
0x1800107a3  cmp     r10d, edi
0x1800107a6  jl      short loc_18001076C
0x1800107a8  mov     rax, [rsp+21D8h+var_2158]
0x1800107b0  mov     [rsp+21D8h+cbData], r14d; cbData
0x1800107b5  mov     [rsp+21D8h+lpData], rax; lpData
0x1800107ba  mov     r9d, 3; dwType
0x1800107c0  xor     r8d, r8d; Reserved
0x1800107c3  mov     rdx, r13; lpValueName
0x1800107c6  mov     rcx, [r12]; hKey
0x1800107ca  call    cs:__imp_RegSetValueExW
0x1800107d1  nop     dword ptr [rax+rax+00h]
0x1800107d6  mov     edi, eax
0x1800107d8  lea     rcx, [rsp+21D8h+var_2158]
0x1800107e0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800107e5  jmp     loc_180010603
0x1800107ea  lea     rax, [rsp+21D8h+String1]
0x1800107f2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800107f6  inc     rdi
0x1800107f9  cmp     [rax+rdi*2], bx
0x1800107fd  jnz     short loc_1800107F6
0x1800107ff  lea     eax, ds:2[rdi*2]
0x180010806  mov     [rsp+21D8h+cbData], eax; cbData
0x18001080a  lea     rax, [rsp+21D8h+String1]
0x180010812  mov     [rsp+21D8h+lpData], rax; lpData
0x180010817  mov     r9d, 1; dwType
0x18001081d  xor     r8d, r8d; Reserved
0x180010820  mov     rdx, r13; lpValueName
0x180010823  mov     rcx, [r12]; hKey
0x180010827  call    cs:__imp_RegSetValueExW
0x18001082e  nop     dword ptr [rax+rax+00h]
0x180010833  mov     edi, eax
0x180010835  test    edi, edi
0x180010837  jz      short loc_180010842
0x180010839  mov     ecx, edi; unsigned int
0x18001083b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180010840  jmp     short loc_18001085D
0x180010842  mov     rdx, [rsp+21D8h+var_2168]; unsigned __int16 *
0x180010847  mov     rcx, r14; this
0x18001084a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001084f  test    eax, eax
0x180010851  cmovs   ebx, eax
0x180010854  mov     eax, ebx
0x180010856  jmp     short loc_18001085D
0x180010858  mov     eax, 80020009h
0x18001085d  mov     rcx, [rsp+21D8h+var_48]
0x180010865  xor     rcx, rsp; StackCookie
0x180010868  call    __security_check_cookie
0x18001086d  add     rsp, 21A0h
0x180010874  pop     r15
0x180010876  pop     r14
0x180010878  pop     r13
0x18001087a  pop     r12
0x18001087c  pop     rdi
0x18001087d  pop     rsi
0x18001087e  pop     rbx
0x18001087f  retn
```
