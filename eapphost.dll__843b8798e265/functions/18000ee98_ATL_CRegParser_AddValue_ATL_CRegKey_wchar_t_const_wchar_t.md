# ATL::CRegParser::AddValue(ATL::CRegKey &,wchar_t const *,wchar_t *)

- ea: `0x18000ee98`
- end: `0x18000f371`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEB_WPEA_W@Z`
- size: `1241`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const wchar_t *, wchar_t *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800105a0`

## callees

- `0x180002af0`
- `0x1800034cc`
- `0x18000e958`
- `0x18000ea04`
- `0x18000ea3c`
- `0x18000ee98`
- `0x18000f378`
- `0x18000f5cc`
- `0x18000f5e4`
- `0x18000f658`
- `0x18000fc34`
- `0x180010ca0`
- `0x1800350c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f0c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f165`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f2ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f317`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f0c6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f165`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f2ba`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000f317`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f037`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f059`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f037`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000f059`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ef25`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000ef25`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000f118`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000f118`

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
  const wchar_t *v38; // [rsp+50h] [rbp-2188h]
  size_t v39; // [rsp+60h] [rbp-2178h]
  struct ATL::CRegKey *v40; // [rsp+68h] [rbp-2170h]
  wchar_t *v41; // [rsp+70h] [rbp-2168h]
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
            ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
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
          ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
LABEL_33:
          v6 = v35;
          break;
        }
        ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
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
          ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
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
      ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(&lpData);
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
0x18000ee98  push    rbx
0x18000ee9a  push    rsi
0x18000ee9b  push    rdi
0x18000ee9c  push    r12
0x18000ee9e  push    r13
0x18000eea0  push    r14
0x18000eea2  push    r15
0x18000eea4  mov     eax, 21A0h
0x18000eea9  call    _alloca_probe
0x18000eeae  sub     rsp, rax
0x18000eeb1  mov     rax, cs:__security_cookie
0x18000eeb8  xor     rax, rsp
0x18000eebb  mov     [rsp+21D8h+var_48], rax
0x18000eec3  mov     r13, r8
0x18000eec6  mov     r12, rdx
0x18000eec9  mov     r14, rcx
0x18000eecc  mov     [rsp+21D8h+var_21A0], rcx
0x18000eed1  mov     qword ptr [rsp+21D8h+Data], rdx
0x18000eed6  mov     [rsp+21D8h+var_2190], rcx
0x18000eedb  mov     [rsp+21D8h+var_2170], rdx
0x18000eee0  mov     [rsp+21D8h+var_2188], r8
0x18000eee5  mov     [rsp+21D8h+var_2168], r9
0x18000eeea  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x18000eef2  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000eef7  xor     ebx, ebx
0x18000eef9  test    eax, eax
0x18000eefb  js      loc_18000F34D
0x18000ef01  mov     edi, ebx
0x18000ef03  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEB_WAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(wchar_t const *,ushort &)'::`2'::map
0x18000ef0a  cmp     edi, 4
0x18000ef0d  jnb     loc_18000F348
0x18000ef13  movsxd  rsi, edi
0x18000ef16  add     rsi, rsi
0x18000ef19  mov     rdx, [r15+rsi*8]; lpString2
0x18000ef1d  lea     rcx, [rsp+21D8h+String1]; lpString1
0x18000ef25  call    cs:__imp_lstrcmpiW
0x18000ef2c  nop     dword ptr [rax+rax+00h]
0x18000ef31  test    eax, eax
0x18000ef33  jz      short loc_18000EF39
0x18000ef35  inc     edi
0x18000ef37  jmp     short loc_18000EF0A
0x18000ef39  movzx   edi, word ptr [r15+rsi*8+8]
0x18000ef3f  mov     rcx, r14; this
0x18000ef42  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000ef47  lea     rdx, [rsp+21D8h+String1]; wchar_t *
0x18000ef4f  mov     rcx, r14; this
0x18000ef52  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000ef57  test    eax, eax
0x18000ef59  js      loc_18000F34D
0x18000ef5f  cmp     di, 8
0x18000ef63  jz      loc_18000F2DA
0x18000ef69  cmp     di, 11h
0x18000ef6d  jz      loc_18000F182
0x18000ef73  cmp     di, 13h
0x18000ef77  jz      loc_18000F0FD
0x18000ef7d  mov     eax, 4008h
0x18000ef82  cmp     di, ax
0x18000ef85  jnz     loc_18000F332
0x18000ef8b  lea     rcx, [rsp+21D8h+String1]
0x18000ef93  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ef97  mov     rax, rdi
0x18000ef9a  inc     rax
0x18000ef9d  cmp     [rcx+rax*2], bx
0x18000efa1  jnz     short loc_18000EF9A
0x18000efa3  add     eax, 2
0x18000efa6  mov     [rsp+21D8h+var_2158], rbx
0x18000efae  movsxd  rcx, eax
0x18000efb1  mov     r15d, 2
0x18000efb7  mov     edx, r15d
0x18000efba  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000efbf  cmp     rax, 100h
0x18000efc5  jbe     short loc_18000EFE1
0x18000efc7  mov     rdx, rax
0x18000efca  lea     rcx, [rsp+21D8h+var_2158]
0x18000efd2  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000efd7  mov     rsi, [rsp+21D8h+var_2158]
0x18000efdf  jmp     short loc_18000EFF1
0x18000efe1  lea     rsi, [rsp+21D8h+var_2150]
0x18000efe9  mov     [rsp+21D8h+var_2158], rsi
0x18000eff1  jmp     short loc_18000F019
0x18000eff3  xor     ebx, ebx
0x18000eff5  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000eff9  lea     r15d, [rbx+2]
0x18000effd  mov     rsi, [rsp+21D8h+var_2158]
0x18000f005  mov     r12, qword ptr [rsp+21D8h+Data]
0x18000f00a  mov     rax, [rsp+21D8h+var_2190]
0x18000f00f  mov     [rsp+21D8h+var_21A0], rax
0x18000f014  mov     r13, [rsp+21D8h+var_2188]
0x18000f019  test    rsi, rsi
0x18000f01c  jz      loc_18000F0E1
0x18000f022  lea     r14, [rsp+21D8h+String1]
0x18000f02a  cmp     [rsp+21D8h+String1], bx
0x18000f032  jz      short loc_18000F079
0x18000f034  mov     rcx, r14; lpsz
0x18000f037  call    cs:__imp_CharNextW
0x18000f03e  nop     dword ptr [rax+rax+00h]
0x18000f043  movzx   ecx, word ptr [r14]
0x18000f047  cmp     cx, 5Ch ; '\'
0x18000f04b  jnz     short loc_18000F06A
0x18000f04d  cmp     word ptr [rax], 30h ; '0'
0x18000f051  jnz     short loc_18000F06A
0x18000f053  mov     [rsi], bx
0x18000f056  mov     rcx, rax; lpsz
0x18000f059  call    cs:__imp_CharNextW
0x18000f060  nop     dword ptr [rax+rax+00h]
0x18000f065  mov     r14, rax
0x18000f068  jmp     short loc_18000F070
0x18000f06a  mov     [rsi], cx
0x18000f06d  add     r14, r15
0x18000f070  add     rsi, r15
0x18000f073  cmp     [r14], bx
0x18000f077  jnz     short loc_18000F034
0x18000f079  mov     dword ptr [rsi], 0
0x18000f07f  mov     r8, [rsp+21D8h+var_2158]
0x18000f087  test    r8, r8
0x18000f08a  jz      short loc_18000F0D6
0x18000f08c  mov     r10d, ebx
0x18000f08f  mov     r9, r8
0x18000f092  mov     rcx, rdi
0x18000f095  inc     rcx
0x18000f098  cmp     [r9+rcx*2], bx
0x18000f09d  jnz     short loc_18000F095
0x18000f09f  inc     ecx
0x18000f0a1  lea     r9, [r9+rcx*2]
0x18000f0a5  lea     r10d, [r10+rcx*2]
0x18000f0a9  cmp     ecx, 1
0x18000f0ac  jnz     short loc_18000F092
0x18000f0ae  mov     [rsp+21D8h+cbData], r10d; cbData
0x18000f0b3  mov     [rsp+21D8h+lpData], r8; lpData
0x18000f0b8  lea     r9d, [rcx+6]; dwType
0x18000f0bc  xor     r8d, r8d; Reserved
0x18000f0bf  mov     rdx, r13; lpValueName
0x18000f0c2  mov     rcx, [r12]; hKey
0x18000f0c6  call    cs:__imp_RegSetValueExW
0x18000f0cd  nop     dword ptr [rax+rax+00h]
0x18000f0d2  mov     edi, eax
0x18000f0d4  jmp     short loc_18000F0E6
0x18000f0d6  mov     ecx, 80004005h; int
0x18000f0db  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000f0e1  mov     edi, 0Eh
0x18000f0e6  lea     rcx, [rsp+21D8h+var_2158]
0x18000f0ee  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000f0f3  mov     r14, [rsp+21D8h+var_21A0]
0x18000f0f8  jmp     loc_18000F325
0x18000f0fd  mov     [rsp+21D8h+pulOut], ebx
0x18000f101  mov     [rsp+21D8h+var_21A0], rbx
0x18000f106  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x18000f10b  xor     r8d, r8d; dwFlags
0x18000f10e  xor     edx, edx; lcid
0x18000f110  lea     rcx, [rsp+21D8h+String1]; strIn
0x18000f118  call    cs:__imp_VarUI4FromStr
0x18000f11f  nop     dword ptr [rax+rax+00h]
0x18000f124  mov     edi, eax
0x18000f126  test    eax, eax
0x18000f128  jns     short loc_18000F13B
0x18000f12a  lea     rcx, [rsp+21D8h+var_21A0]
0x18000f12f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f134  mov     eax, edi
0x18000f136  jmp     loc_18000F34D
0x18000f13b  mov     eax, [rsp+21D8h+pulOut]
0x18000f13f  mov     dword ptr [rsp+21D8h+Data], eax
0x18000f143  mov     [rsp+21D8h+cbData], 4; cbData
0x18000f14b  lea     rax, [rsp+21D8h+Data]
0x18000f150  mov     [rsp+21D8h+lpData], rax; lpData
0x18000f155  mov     r9d, 4; dwType
0x18000f15b  xor     r8d, r8d; Reserved
0x18000f15e  mov     rdx, r13; lpValueName
0x18000f161  mov     rcx, [r12]; hKey
0x18000f165  call    cs:__imp_RegSetValueExW
0x18000f16c  nop     dword ptr [rax+rax+00h]
0x18000f171  mov     edi, eax
0x18000f173  lea     rcx, [rsp+21D8h+var_21A0]
0x18000f178  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000f17d  jmp     loc_18000F325
0x18000f182  lea     rax, [rsp+21D8h+String1]
0x18000f18a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f18e  inc     rdi
0x18000f191  cmp     [rax+rdi*2], bx
0x18000f195  jnz     short loc_18000F18E
0x18000f197  mov     dword ptr [rsp+21D8h+Data], edi
0x18000f19b  test    dil, 1
0x18000f19f  jz      short loc_18000F1AB
0x18000f1a1  mov     eax, 80004005h
0x18000f1a6  jmp     loc_18000F34D
0x18000f1ab  mov     eax, edi
0x18000f1ad  cdq
0x18000f1ae  mov     r15d, 2
0x18000f1b4  idiv    r15d
0x18000f1b7  movsxd  r14, eax
0x18000f1ba  mov     [rsp+21D8h+var_2158], rbx
0x18000f1c2  mov     rsi, r14
0x18000f1c5  mov     [rsp+21D8h+var_2178], r14
0x18000f1ca  lea     edx, [r15-1]
0x18000f1ce  mov     rcx, r14
0x18000f1d1  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000f1d6  cmp     rax, 100h
0x18000f1dc  jbe     short loc_18000F1F8
0x18000f1de  mov     rdx, rax
0x18000f1e1  lea     rcx, [rsp+21D8h+var_2158]
0x18000f1e9  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000f1ee  mov     rcx, [rsp+21D8h+var_2158]
0x18000f1f6  jmp     short loc_18000F208
0x18000f1f8  lea     rcx, [rsp+21D8h+var_2150]
0x18000f200  mov     [rsp+21D8h+var_2158], rcx
0x18000f208  jmp     short loc_18000F234
0x18000f20a  xor     ebx, ebx
0x18000f20c  mov     edi, dword ptr [rsp+21D8h+Data]
0x18000f210  mov     rcx, [rsp+21D8h+var_2158]; void *
0x18000f218  mov     rsi, [rsp+21D8h+var_2178]
0x18000f21d  mov     rax, [rsp+21D8h+var_2190]
0x18000f222  mov     [rsp+21D8h+var_21A0], rax
0x18000f227  mov     r12, [rsp+21D8h+var_2170]
0x18000f22c  mov     r13, [rsp+21D8h+var_2188]
0x18000f231  mov     r14d, esi
0x18000f234  test    rcx, rcx
0x18000f237  jnz     short loc_18000F24B
0x18000f239  lea     rcx, [rsp+21D8h+var_2158]
0x18000f241  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000f246  jmp     loc_18000F1A1
0x18000f24b  mov     r8, rsi; Size
0x18000f24e  xor     edx, edx; Val
0x18000f250  call    memset_0
0x18000f255  mov     r10d, ebx
0x18000f258  test    edi, edi
0x18000f25a  jle     short loc_18000F298
0x18000f25c  mov     r9d, r10d
0x18000f25f  shr     r9, 1
0x18000f262  mov     r8, [rsp+21D8h+var_2158]
0x18000f26a  mov     ecx, r10d
0x18000f26d  movzx   ecx, [rsp+rcx*2+21D8h+String1]; wchar_t
0x18000f275  call    ?ChToByte@CRegParser@ATL@@KAE_W@Z; ATL::CRegParser::ChToByte(wchar_t)
0x18000f27a  mov     edx, r10d
0x18000f27d  and     edx, 1
0x18000f280  shl     edx, 2
0x18000f283  mov     ecx, 4
0x18000f288  sub     ecx, edx
0x18000f28a  shl     al, cl
0x18000f28c  or      [r9+r8], al
0x18000f290  inc     r10d
0x18000f293  cmp     r10d, edi
0x18000f296  jl      short loc_18000F25C
0x18000f298  mov     rax, [rsp+21D8h+var_2158]
0x18000f2a0  mov     [rsp+21D8h+cbData], r14d; cbData
0x18000f2a5  mov     [rsp+21D8h+lpData], rax; lpData
0x18000f2aa  mov     r9d, 3; dwType
0x18000f2b0  xor     r8d, r8d; Reserved
0x18000f2b3  mov     rdx, r13; lpValueName
0x18000f2b6  mov     rcx, [r12]; hKey
0x18000f2ba  call    cs:__imp_RegSetValueExW
0x18000f2c1  nop     dword ptr [rax+rax+00h]
0x18000f2c6  mov     edi, eax
0x18000f2c8  lea     rcx, [rsp+21D8h+var_2158]
0x18000f2d0  call    ??1?$CTempBuffer@_W$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<wchar_t,256,ATL::CCRTAllocator>::~CTempBuffer<wchar_t,256,ATL::CCRTAllocator>(void)
0x18000f2d5  jmp     loc_18000F0F3
0x18000f2da  lea     rax, [rsp+21D8h+String1]
0x18000f2e2  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000f2e6  inc     rdi
0x18000f2e9  cmp     [rax+rdi*2], bx
0x18000f2ed  jnz     short loc_18000F2E6
0x18000f2ef  lea     eax, ds:2[rdi*2]
0x18000f2f6  mov     [rsp+21D8h+cbData], eax; cbData
0x18000f2fa  lea     rax, [rsp+21D8h+String1]
0x18000f302  mov     [rsp+21D8h+lpData], rax; lpData
0x18000f307  mov     r9d, 1; dwType
0x18000f30d  xor     r8d, r8d; Reserved
0x18000f310  mov     rdx, r13; lpValueName
0x18000f313  mov     rcx, [r12]; hKey
0x18000f317  call    cs:__imp_RegSetValueExW
0x18000f31e  nop     dword ptr [rax+rax+00h]
0x18000f323  mov     edi, eax
0x18000f325  test    edi, edi
0x18000f327  jz      short loc_18000F332
0x18000f329  mov     ecx, edi; unsigned int
0x18000f32b  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000f330  jmp     short loc_18000F34D
0x18000f332  mov     rdx, [rsp+21D8h+var_2168]; wchar_t *
0x18000f337  mov     rcx, r14; this
0x18000f33a  call    ?NextToken@CRegParser@ATL@@IEAAJPEA_W@Z; ATL::CRegParser::NextToken(wchar_t *)
0x18000f33f  test    eax, eax
0x18000f341  cmovs   ebx, eax
0x18000f344  mov     eax, ebx
0x18000f346  jmp     short loc_18000F34D
0x18000f348  mov     eax, 80020009h
0x18000f34d  mov     rcx, [rsp+21D8h+var_48]
0x18000f355  xor     rcx, rsp; StackCookie
0x18000f358  call    __security_check_cookie
0x18000f35d  add     rsp, 21A0h
0x18000f364  pop     r15
0x18000f366  pop     r14
0x18000f368  pop     r13
0x18000f36a  pop     r12
0x18000f36c  pop     rdi
0x18000f36d  pop     rsi
0x18000f36e  pop     rbx
0x18000f36f  retn
```
