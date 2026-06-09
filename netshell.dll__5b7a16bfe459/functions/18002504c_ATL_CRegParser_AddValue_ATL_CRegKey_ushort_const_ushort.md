# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18002504c`
- end: `0x1800254f4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1192`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800290b0`

## callees

- `0x18001e1e0`
- `0x18001eb7c`
- `0x18002325c`
- `0x1800238f8`
- `0x180024108`
- `0x18002504c`
- `0x1800254fc`
- `0x18002580c`
- `0x180025824`
- `0x180025894`
- `0x180027fc8`
- `0x180029ed0`
- `0x1800620a0`

## import_xrefs

- `USER32!CharNextW` at `0x1800251e5`
- `USER32!CharNextW` at `0x180025201`
- `USER32!CharNextW` at `0x1800251e5`
- `USER32!CharNextW` at `0x180025201`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800250d9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x1800250d9`
- `ADVAPI32!RegSetValueExW` at `0x180025268`
- `ADVAPI32!RegSetValueExW` at `0x1800252fb`
- `ADVAPI32!RegSetValueExW` at `0x18002544a`
- `ADVAPI32!RegSetValueExW` at `0x1800254a1`
- `ADVAPI32!RegSetValueExW` at `0x180025268`
- `ADVAPI32!RegSetValueExW` at `0x1800252fb`
- `ADVAPI32!RegSetValueExW` at `0x18002544a`
- `ADVAPI32!RegSetValueExW` at `0x1800254a1`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800252b4`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800252b4`

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
0x18002504c  push    rbx
0x18002504e  push    rsi
0x18002504f  push    rdi
0x180025050  push    r12
0x180025052  push    r13
0x180025054  push    r14
0x180025056  push    r15
0x180025058  mov     eax, 21A0h
0x18002505d  call    _alloca_probe
0x180025062  sub     rsp, rax
0x180025065  mov     rax, cs:__security_cookie
0x18002506c  xor     rax, rsp
0x18002506f  mov     [rsp+21D8h+var_48], rax
0x180025077  mov     r13, r8
0x18002507a  mov     r12, rdx
0x18002507d  mov     r14, rcx
0x180025080  mov     [rsp+21D8h+var_21A0], rcx
0x180025085  mov     qword ptr [rsp+21D8h+Data], rdx
0x18002508a  mov     [rsp+21D8h+var_2190], rcx
0x18002508f  mov     [rsp+21D8h+var_2170], rdx
0x180025094  mov     [rsp+21D8h+var_2188], r8
0x180025099  mov     [rsp+21D8h+var_2168], r9
0x18002509e  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x1800250a6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800250ab  xor     ebx, ebx
0x1800250ad  test    eax, eax
0x1800250af  js      loc_1800254D1
0x1800250b5  mov     edi, ebx
0x1800250b7  lea     r15, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800250be  cmp     edi, 4
0x1800250c1  jnb     loc_1800254CC
0x1800250c7  movsxd  rsi, edi
0x1800250ca  add     rsi, rsi
0x1800250cd  mov     rdx, [r15+rsi*8]; lpString2
0x1800250d1  lea     rcx, [rsp+21D8h+String1]; lpString1
0x1800250d9  call    cs:__imp_lstrcmpiW
0x1800250df  test    eax, eax
0x1800250e1  jz      short loc_1800250E7
0x1800250e3  inc     edi
0x1800250e5  jmp     short loc_1800250BE
0x1800250e7  movzx   edi, word ptr [r15+rsi*8+8]
0x1800250ed  mov     rcx, r14; this
0x1800250f0  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800250f5  lea     rdx, [rsp+21D8h+String1]; unsigned __int16 *
0x1800250fd  mov     rcx, r14; this
0x180025100  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180025105  test    eax, eax
0x180025107  js      loc_1800254D1
0x18002510d  cmp     di, 8
0x180025111  jz      loc_180025464
0x180025117  cmp     di, 11h
0x18002511b  jz      loc_180025312
0x180025121  cmp     di, 13h
0x180025125  jz      loc_180025299
0x18002512b  mov     eax, 4008h
0x180025130  cmp     di, ax
0x180025133  jnz     loc_1800254B6
0x180025139  lea     rcx, [rsp+21D8h+String1]
0x180025141  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025145  mov     rax, rdi
0x180025148  inc     rax
0x18002514b  cmp     [rcx+rax*2], bx
0x18002514f  jnz     short loc_180025148
0x180025151  add     eax, 2
0x180025154  mov     [rsp+21D8h+var_2158], rbx
0x18002515c  movsxd  rcx, eax
0x18002515f  mov     r15d, 2
0x180025165  mov     edx, r15d
0x180025168  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002516d  cmp     rax, 100h
0x180025173  jbe     short loc_18002518F
0x180025175  mov     rdx, rax
0x180025178  lea     rcx, [rsp+21D8h+var_2158]
0x180025180  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180025185  mov     rsi, [rsp+21D8h+var_2158]
0x18002518d  jmp     short loc_18002519F
0x18002518f  lea     rsi, [rsp+21D8h+var_2150]
0x180025197  mov     [rsp+21D8h+var_2158], rsi
0x18002519f  jmp     short loc_1800251C7
0x1800251a1  xor     ebx, ebx
0x1800251a3  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800251a7  lea     r15d, [rbx+2]
0x1800251ab  mov     rsi, [rsp+21D8h+var_2158]
0x1800251b3  mov     r12, qword ptr [rsp+21D8h+Data]
0x1800251b8  mov     rax, [rsp+21D8h+var_2190]
0x1800251bd  mov     [rsp+21D8h+var_21A0], rax
0x1800251c2  mov     r13, [rsp+21D8h+var_2188]
0x1800251c7  test    rsi, rsi
0x1800251ca  jz      loc_18002527D
0x1800251d0  lea     r14, [rsp+21D8h+String1]
0x1800251d8  cmp     [rsp+21D8h+String1], bx
0x1800251e0  jz      short loc_18002521B
0x1800251e2  mov     rcx, r14; lpsz
0x1800251e5  call    cs:__imp_CharNextW
0x1800251eb  movzx   ecx, word ptr [r14]
0x1800251ef  cmp     cx, 5Ch ; '\'
0x1800251f3  jnz     short loc_18002520C
0x1800251f5  cmp     word ptr [rax], 30h ; '0'
0x1800251f9  jnz     short loc_18002520C
0x1800251fb  mov     [rsi], bx
0x1800251fe  mov     rcx, rax; lpsz
0x180025201  call    cs:__imp_CharNextW
0x180025207  mov     r14, rax
0x18002520a  jmp     short loc_180025212
0x18002520c  mov     [rsi], cx
0x18002520f  add     r14, r15
0x180025212  add     rsi, r15
0x180025215  cmp     [r14], bx
0x180025219  jnz     short loc_1800251E2
0x18002521b  mov     dword ptr [rsi], 0
0x180025221  mov     r8, [rsp+21D8h+var_2158]
0x180025229  test    r8, r8
0x18002522c  jz      short loc_180025272
0x18002522e  mov     r10d, ebx
0x180025231  mov     r9, r8
0x180025234  mov     rcx, rdi
0x180025237  inc     rcx
0x18002523a  cmp     [r9+rcx*2], bx
0x18002523f  jnz     short loc_180025237
0x180025241  inc     ecx
0x180025243  lea     r9, [r9+rcx*2]
0x180025247  lea     r10d, [r10+rcx*2]
0x18002524b  cmp     ecx, 1
0x18002524e  jnz     short loc_180025234
0x180025250  mov     [rsp+21D8h+cbData], r10d; cbData
0x180025255  mov     [rsp+21D8h+lpData], r8; lpData
0x18002525a  lea     r9d, [rcx+6]; dwType
0x18002525e  xor     r8d, r8d; Reserved
0x180025261  mov     rdx, r13; lpValueName
0x180025264  mov     rcx, [r12]; hKey
0x180025268  call    cs:__imp_RegSetValueExW
0x18002526e  mov     edi, eax
0x180025270  jmp     short loc_180025282
0x180025272  mov     ecx, 80004005h; int
0x180025277  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002527d  mov     edi, 0Eh
0x180025282  lea     rcx, [rsp+21D8h+var_2158]
0x18002528a  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002528f  mov     r14, [rsp+21D8h+var_21A0]
0x180025294  jmp     loc_1800254A9
0x180025299  mov     [rsp+21D8h+pulOut], ebx
0x18002529d  mov     [rsp+21D8h+var_21A0], rbx
0x1800252a2  lea     r9, [rsp+21D8h+pulOut]; pulOut
0x1800252a7  xor     r8d, r8d; dwFlags
0x1800252aa  xor     edx, edx; lcid
0x1800252ac  lea     rcx, [rsp+21D8h+String1]; strIn
0x1800252b4  call    cs:__imp_VarUI4FromStr
0x1800252ba  mov     edi, eax
0x1800252bc  test    eax, eax
0x1800252be  jns     short loc_1800252D1
0x1800252c0  lea     rcx, [rsp+21D8h+var_21A0]
0x1800252c5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800252ca  mov     eax, edi
0x1800252cc  jmp     loc_1800254D1
0x1800252d1  mov     eax, [rsp+21D8h+pulOut]
0x1800252d5  mov     dword ptr [rsp+21D8h+Data], eax
0x1800252d9  mov     [rsp+21D8h+cbData], 4; cbData
0x1800252e1  lea     rax, [rsp+21D8h+Data]
0x1800252e6  mov     [rsp+21D8h+lpData], rax; lpData
0x1800252eb  mov     r9d, 4; dwType
0x1800252f1  xor     r8d, r8d; Reserved
0x1800252f4  mov     rdx, r13; lpValueName
0x1800252f7  mov     rcx, [r12]; hKey
0x1800252fb  call    cs:__imp_RegSetValueExW
0x180025301  mov     edi, eax
0x180025303  lea     rcx, [rsp+21D8h+var_21A0]
0x180025308  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002530d  jmp     loc_1800254A9
0x180025312  lea     rax, [rsp+21D8h+String1]
0x18002531a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002531e  inc     rdi
0x180025321  cmp     [rax+rdi*2], bx
0x180025325  jnz     short loc_18002531E
0x180025327  mov     dword ptr [rsp+21D8h+Data], edi
0x18002532b  test    dil, 1
0x18002532f  jz      short loc_18002533B
0x180025331  mov     eax, 80004005h
0x180025336  jmp     loc_1800254D1
0x18002533b  mov     eax, edi
0x18002533d  cdq
0x18002533e  mov     r15d, 2
0x180025344  idiv    r15d
0x180025347  movsxd  r14, eax
0x18002534a  mov     [rsp+21D8h+var_2158], rbx
0x180025352  mov     rsi, r14
0x180025355  mov     [rsp+21D8h+var_2178], r14
0x18002535a  lea     edx, [r15-1]
0x18002535e  mov     rcx, r14
0x180025361  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180025366  cmp     rax, 100h
0x18002536c  jbe     short loc_180025388
0x18002536e  mov     rdx, rax
0x180025371  lea     rcx, [rsp+21D8h+var_2158]
0x180025379  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002537e  mov     rcx, [rsp+21D8h+var_2158]
0x180025386  jmp     short loc_180025398
0x180025388  lea     rcx, [rsp+21D8h+var_2150]
0x180025390  mov     [rsp+21D8h+var_2158], rcx
0x180025398  jmp     short loc_1800253C4
0x18002539a  xor     ebx, ebx
0x18002539c  mov     edi, dword ptr [rsp+21D8h+Data]
0x1800253a0  mov     rcx, [rsp+21D8h+var_2158]; void *
0x1800253a8  mov     rsi, [rsp+21D8h+var_2178]
0x1800253ad  mov     rax, [rsp+21D8h+var_2190]
0x1800253b2  mov     [rsp+21D8h+var_21A0], rax
0x1800253b7  mov     r12, [rsp+21D8h+var_2170]
0x1800253bc  mov     r13, [rsp+21D8h+var_2188]
0x1800253c1  mov     r14d, esi
0x1800253c4  test    rcx, rcx
0x1800253c7  jnz     short loc_1800253DB
0x1800253c9  lea     rcx, [rsp+21D8h+var_2158]
0x1800253d1  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800253d6  jmp     loc_180025331
0x1800253db  mov     r8, rsi; Size
0x1800253de  xor     edx, edx; Val
0x1800253e0  call    memset_0
0x1800253e5  mov     r10d, ebx
0x1800253e8  test    edi, edi
0x1800253ea  jle     short loc_180025428
0x1800253ec  mov     r9d, r10d
0x1800253ef  shr     r9, 1
0x1800253f2  mov     r8, [rsp+21D8h+var_2158]
0x1800253fa  mov     ecx, r10d
0x1800253fd  movzx   ecx, [rsp+rcx*2+21D8h+String1]; unsigned __int16
0x180025405  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18002540a  mov     edx, r10d
0x18002540d  and     edx, 1
0x180025410  shl     edx, 2
0x180025413  mov     ecx, 4
0x180025418  sub     ecx, edx
0x18002541a  shl     al, cl
0x18002541c  or      [r9+r8], al
0x180025420  inc     r10d
0x180025423  cmp     r10d, edi
0x180025426  jl      short loc_1800253EC
0x180025428  mov     rax, [rsp+21D8h+var_2158]
0x180025430  mov     [rsp+21D8h+cbData], r14d; cbData
0x180025435  mov     [rsp+21D8h+lpData], rax; lpData
0x18002543a  mov     r9d, 3; dwType
0x180025440  xor     r8d, r8d; Reserved
0x180025443  mov     rdx, r13; lpValueName
0x180025446  mov     rcx, [r12]; hKey
0x18002544a  call    cs:__imp_RegSetValueExW
0x180025450  mov     edi, eax
0x180025452  lea     rcx, [rsp+21D8h+var_2158]
0x18002545a  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002545f  jmp     loc_18002528F
0x180025464  lea     rax, [rsp+21D8h+String1]
0x18002546c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025470  inc     rdi
0x180025473  cmp     [rax+rdi*2], bx
0x180025477  jnz     short loc_180025470
0x180025479  lea     eax, ds:2[rdi*2]
0x180025480  mov     [rsp+21D8h+cbData], eax; cbData
0x180025484  lea     rax, [rsp+21D8h+String1]
0x18002548c  mov     [rsp+21D8h+lpData], rax; lpData
0x180025491  mov     r9d, 1; dwType
0x180025497  xor     r8d, r8d; Reserved
0x18002549a  mov     rdx, r13; lpValueName
0x18002549d  mov     rcx, [r12]; hKey
0x1800254a1  call    cs:__imp_RegSetValueExW
0x1800254a7  mov     edi, eax
0x1800254a9  test    edi, edi
0x1800254ab  jz      short loc_1800254B6
0x1800254ad  mov     ecx, edi; unsigned int
0x1800254af  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1800254b4  jmp     short loc_1800254D1
0x1800254b6  mov     rdx, [rsp+21D8h+var_2168]; unsigned __int16 *
0x1800254bb  mov     rcx, r14; this
0x1800254be  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800254c3  test    eax, eax
0x1800254c5  cmovs   ebx, eax
0x1800254c8  mov     eax, ebx
0x1800254ca  jmp     short loc_1800254D1
0x1800254cc  mov     eax, 80020009h
0x1800254d1  mov     rcx, [rsp+21D8h+var_48]
0x1800254d9  xor     rcx, rsp; StackCookie
0x1800254dc  call    __security_check_cookie
0x1800254e1  add     rsp, 21A0h
0x1800254e8  pop     r15
0x1800254ea  pop     r14
0x1800254ec  pop     r13
0x1800254ee  pop     r12
0x1800254f0  pop     rdi
0x1800254f1  pop     rsi
0x1800254f2  pop     rbx
0x1800254f3  retn
```
