# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800674a8`
- end: `0x180067954`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180069900`

## callees

- `0x180033da0`
- `0x180034970`
- `0x180066cec`
- `0x180066e38`
- `0x180066f58`
- `0x1800674a8`
- `0x18006795c`
- `0x180067c54`
- `0x1800682e0`
- `0x180068b70`
- `0x18006a118`
- `0x18014c2b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067689`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067715`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800678b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067901`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067689`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067715`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800678b1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180067901`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180067601`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18006761d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180067601`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18006761d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180067529`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180067529`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800676ce`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800676ce`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  HKEY *v4; // r12
  unsigned __int16 *v5; // r15
  ATL::CRegParser *v7; // r14
  __int64 result; // rax
  unsigned int i; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // ebx
  HRESULT v21; // ebx
  HKEY v22; // rcx
  __int64 v23; // rdi
  size_t v24; // rsi
  unsigned __int64 v25; // rax
  BYTE *v26; // rcx
  int v27; // r10d
  unsigned int v28; // r9d
  char v29; // r9
  unsigned __int64 v30; // r8
  char v31; // r9
  __int64 v32; // rdi
  int Token; // eax
  unsigned int v34; // ecx
  unsigned __int16 *v35; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pulOut[2]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v39[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v4 = a2;
  *(_QWORD *)pulOut = a2;
  v35 = a4;
  v5 = a4;
  *(_QWORD *)Data = this;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, String1);
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
  ATL::CRegParser::SkipWhiteSpace(v7);
  result = ATL::CRegParser::NextToken(v7, String1);
  if ( (int)result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v32 = -1;
    do
      ++v32;
    while ( String1[v32] );
    v20 = RegSetValueExW(*v4, a3, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
    goto LABEL_77;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    if ( (v23 & 1) != 0 )
      return 2147500037LL;
    v24 = (int)v23 / 2;
    lpData = 0;
    v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
    if ( v25 <= 0x100 )
    {
      v26 = v39;
      lpData = v39;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
      v26 = lpData;
    }
    if ( !v26 )
    {
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      return 2147500037LL;
    }
    memset_0(v26, 0, v24);
    v27 = 0;
    if ( (int)v23 <= 0 )
      goto LABEL_73;
    while ( 1 )
    {
      v28 = String1[v27];
      if ( v28 > 0x61 )
      {
        if ( v28 == 98 || v28 == 99 || v28 == 100 || v28 - 101 < 2 )
        {
LABEL_70:
          v29 = v28 - 87;
          goto LABEL_71;
        }
LABEL_69:
        v29 = 0;
        goto LABEL_71;
      }
      if ( v28 == 97 )
        goto LABEL_70;
      if ( v28 <= 0x38 )
        break;
      if ( v28 == 57 )
        goto LABEL_57;
      if ( v28 != 65 && v28 != 66 && v28 != 67 && v28 != 68 && v28 - 69 > 1 )
        goto LABEL_69;
      v29 = v28 - 55;
LABEL_71:
      v30 = (unsigned __int64)(unsigned int)v27 >> 1;
      v31 = v29 << (4 - 4 * (v27++ & 1));
      lpData[v30] |= v31;
      if ( v27 >= (int)v23 )
      {
        v5 = v35;
LABEL_73:
        v20 = RegSetValueExW(*v4, a3, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        v7 = *(ATL::CRegParser **)Data;
LABEL_77:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
LABEL_79:
        Token = ATL::CRegParser::NextToken(v7, v5);
        v34 = 0;
        if ( Token < 0 )
          return (unsigned int)Token;
        return v34;
      }
    }
    if ( v28 != 56 && v28 != 48 && v28 != 49 && v28 != 50 && v28 != 51 && v28 != 52 && v28 != 53 && v28 - 54 > 1 )
      goto LABEL_69;
LABEL_57:
    v29 = v28 - 48;
    goto LABEL_71;
  }
  if ( v10 != 19 )
  {
    if ( v10 == 16392 )
    {
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      lpData = 0;
      v12 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v11 + 2, 2);
      if ( v12 <= 0x100 )
      {
        v13 = v39;
        lpData = v39;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v12);
        v13 = lpData;
      }
      if ( v13 )
      {
        v14 = String1;
        if ( String1[0] )
        {
          do
          {
            v15 = CharNextW(v14);
            if ( *v14 == 92 && *v15 == 48 )
            {
              *(_WORD *)v13 = 0;
              v14 = CharNextW(v15);
            }
            else
            {
              *(_WORD *)v13 = *v14++;
            }
            v13 += 2;
          }
          while ( *v14 );
          v4 = *(HKEY **)pulOut;
          v5 = v35;
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
        v20 = RegSetValueExW(*v4, a3, 0, 7u, lpData, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      v7 = *(ATL::CRegParser **)Data;
      goto LABEL_77;
    }
    goto LABEL_79;
  }
  pulOut[0] = 0;
  v35 = 0;
  v21 = VarUI4FromStr(String1, 0, 0, pulOut);
  if ( v21 >= 0 )
  {
    v22 = *v4;
    *(_DWORD *)Data = pulOut[0];
    v20 = RegSetValueExW(v22, a3, 0, 4u, Data, 4u);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
    goto LABEL_77;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x1800674a8  push    rbp
0x1800674aa  push    rbx
0x1800674ab  push    rsi
0x1800674ac  push    rdi
0x1800674ad  push    r12
0x1800674af  push    r13
0x1800674b1  push    r14
0x1800674b3  push    r15
0x1800674b5  lea     rbp, [rsp-2078h]
0x1800674bd  mov     eax, 2178h
0x1800674c2  call    _alloca_probe
0x1800674c7  sub     rsp, rax
0x1800674ca  mov     rax, cs:__security_cookie
0x1800674d1  xor     rax, rsp
0x1800674d4  mov     [rbp+20B0h+var_50], rax
0x1800674db  mov     r12, rdx
0x1800674de  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x1800674e3  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x1800674e7  mov     [rsp+21B0h+var_2180], r9
0x1800674ec  mov     r15, r9
0x1800674ef  mov     qword ptr [rsp+21B0h+Data], rcx
0x1800674f4  mov     r13, r8
0x1800674f7  mov     r14, rcx
0x1800674fa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800674ff  xor     esi, esi
0x180067501  test    eax, eax
0x180067503  js      loc_180067931
0x180067509  mov     ebx, esi
0x18006750b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180067512  cmp     ebx, 4
0x180067515  jnb     loc_18006792C
0x18006751b  movsxd  rdi, ebx
0x18006751e  lea     rcx, [rbp+20B0h+String1]; lpString1
0x180067522  add     rdi, rdi
0x180067525  mov     rdx, [rax+rdi*8]; lpString2
0x180067529  call    cs:__imp_lstrcmpiW
0x18006752f  test    eax, eax
0x180067531  jz      short loc_180067537
0x180067533  inc     ebx
0x180067535  jmp     short loc_18006750B
0x180067537  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18006753e  mov     rcx, r14; this
0x180067541  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180067546  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18006754b  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18006754f  mov     rcx, r14; this
0x180067552  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180067557  test    eax, eax
0x180067559  js      loc_180067931
0x18006755f  mov     eax, 8
0x180067564  cmp     bx, ax
0x180067567  jz      loc_1800678CC
0x18006756d  cmp     bx, 11h
0x180067571  jz      loc_18006772C
0x180067577  cmp     bx, 13h
0x18006757b  jz      loc_1800676B7
0x180067581  mov     eax, 4008h
0x180067586  cmp     bx, ax
0x180067589  jnz     loc_180067916
0x18006758f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180067593  lea     rcx, [rbp+20B0h+String1]
0x180067597  mov     rax, rdi
0x18006759a  inc     rax
0x18006759d  cmp     [rcx+rax*2], si
0x1800675a1  jnz     short loc_18006759A
0x1800675a3  add     eax, 2
0x1800675a6  mov     [rsp+21B0h+var_2160], rsi
0x1800675ab  mov     r14d, 2
0x1800675b1  movsxd  rcx, eax
0x1800675b4  mov     edx, r14d
0x1800675b7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800675bc  cmp     rax, 100h
0x1800675c2  jbe     short loc_1800675D8
0x1800675c4  mov     rdx, rax
0x1800675c7  lea     rcx, [rsp+21B0h+var_2160]
0x1800675cc  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800675d1  mov     rbx, [rsp+21B0h+var_2160]
0x1800675d6  jmp     short loc_1800675E2
0x1800675d8  lea     rbx, [rsp+21B0h+var_2158]
0x1800675dd  mov     [rsp+21B0h+var_2160], rbx
0x1800675e2  test    rbx, rbx
0x1800675e5  jz      loc_18006769E
0x1800675eb  xor     eax, eax
0x1800675ed  lea     rsi, [rbp+20B0h+String1]
0x1800675f1  cmp     [rbp+20B0h+String1], ax
0x1800675f5  jz      short loc_180067641
0x1800675f7  lea     r15d, [rax+30h]
0x1800675fb  xor     r12d, r12d
0x1800675fe  mov     rcx, rsi; lpsz
0x180067601  call    cs:__imp_CharNextW
0x180067607  movzx   ecx, word ptr [rsi]
0x18006760a  cmp     cx, 5Ch ; '\'
0x18006760e  jnz     short loc_180067628
0x180067610  cmp     [rax], r15w
0x180067614  jnz     short loc_180067628
0x180067616  mov     rcx, rax; lpsz
0x180067619  mov     [rbx], r12w
0x18006761d  call    cs:__imp_CharNextW
0x180067623  mov     rsi, rax
0x180067626  jmp     short loc_18006762E
0x180067628  mov     [rbx], cx
0x18006762b  add     rsi, r14
0x18006762e  add     rbx, r14
0x180067631  cmp     [rsi], r12w
0x180067635  jnz     short loc_1800675FE
0x180067637  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x18006763c  mov     r15, [rsp+21B0h+var_2180]
0x180067641  xor     esi, esi
0x180067643  mov     [rbx], esi
0x180067645  mov     r8, [rsp+21B0h+var_2160]
0x18006764a  test    r8, r8
0x18006764d  jz      short loc_180067693
0x18006764f  mov     r10d, esi
0x180067652  mov     r9, r8
0x180067655  mov     rcx, rdi
0x180067658  inc     rcx
0x18006765b  cmp     [r9+rcx*2], si
0x180067660  jnz     short loc_180067658
0x180067662  inc     ecx
0x180067664  lea     r9, [r9+rcx*2]
0x180067668  lea     r10d, [r10+rcx*2]
0x18006766c  cmp     ecx, 1
0x18006766f  jnz     short loc_180067655
0x180067671  mov     [rsp+21B0h+cbData], r10d; cbData
0x180067676  lea     r9d, [rcx+6]; dwType
0x18006767a  mov     rcx, [r12]; hKey
0x18006767e  mov     rdx, r13; lpValueName
0x180067681  mov     [rsp+21B0h+lpData], r8; lpData
0x180067686  xor     r8d, r8d; Reserved
0x180067689  call    cs:__imp_RegSetValueExW
0x18006768f  mov     ebx, eax
0x180067691  jmp     short loc_1800676A3
0x180067693  mov     ecx, 80004005h; int
0x180067698  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18006769e  mov     ebx, 0Eh
0x1800676a3  lea     rcx, [rsp+21B0h+var_2160]
0x1800676a8  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800676ad  mov     r14, qword ptr [rsp+21B0h+Data]
0x1800676b2  jmp     loc_180067909
0x1800676b7  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x1800676bc  mov     [rsp+21B0h+pulOut], esi
0x1800676c0  xor     r8d, r8d; dwFlags
0x1800676c3  mov     [rsp+21B0h+var_2180], rsi
0x1800676c8  xor     edx, edx; lcid
0x1800676ca  lea     rcx, [rbp+20B0h+String1]; strIn
0x1800676ce  call    cs:__imp_VarUI4FromStr
0x1800676d4  mov     ebx, eax
0x1800676d6  test    eax, eax
0x1800676d8  jns     short loc_1800676EB
0x1800676da  lea     rcx, [rsp+21B0h+var_2180]
0x1800676df  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800676e4  mov     eax, ebx
0x1800676e6  jmp     loc_180067931
0x1800676eb  mov     eax, [rsp+21B0h+pulOut]
0x1800676ef  mov     r9d, 4; dwType
0x1800676f5  mov     rcx, [r12]; hKey
0x1800676f9  xor     r8d, r8d; Reserved
0x1800676fc  mov     dword ptr [rsp+21B0h+Data], eax
0x180067700  mov     rdx, r13; lpValueName
0x180067703  lea     rax, [rsp+21B0h+Data]
0x180067708  mov     [rsp+21B0h+cbData], 4; cbData
0x180067710  mov     [rsp+21B0h+lpData], rax; lpData
0x180067715  call    cs:__imp_RegSetValueExW
0x18006771b  lea     rcx, [rsp+21B0h+var_2180]
0x180067720  mov     ebx, eax
0x180067722  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180067727  jmp     loc_180067909
0x18006772c  lea     rax, [rbp+20B0h+String1]
0x180067730  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180067734  inc     rdi
0x180067737  cmp     [rax+rdi*2], si
0x18006773b  jnz     short loc_180067734
0x18006773d  test    dil, 1
0x180067741  jz      short loc_18006774D
0x180067743  mov     eax, 80004005h
0x180067748  jmp     loc_180067931
0x18006774d  mov     eax, edi
0x18006774f  mov     r14d, 2
0x180067755  cdq
0x180067756  idiv    r14d
0x180067759  xor     r14d, r14d
0x18006775c  movsxd  rsi, eax
0x18006775f  mov     rcx, rsi
0x180067762  mov     [rsp+21B0h+var_2160], r14
0x180067767  lea     edx, [r14+1]
0x18006776b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180067770  cmp     rax, 100h
0x180067776  jbe     short loc_18006778C
0x180067778  mov     rdx, rax
0x18006777b  lea     rcx, [rsp+21B0h+var_2160]
0x180067780  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180067785  mov     rcx, [rsp+21B0h+var_2160]
0x18006778a  jmp     short loc_180067796
0x18006778c  lea     rcx, [rsp+21B0h+var_2158]; void *
0x180067791  mov     [rsp+21B0h+var_2160], rcx
0x180067796  test    rcx, rcx
0x180067799  jnz     short loc_1800677A7
0x18006779b  lea     rcx, [rsp+21B0h+var_2160]
0x1800677a0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800677a5  jmp     short loc_180067743
0x1800677a7  mov     r8, rsi; Size
0x1800677aa  xor     edx, edx; Val
0x1800677ac  call    memset_0
0x1800677b1  mov     r10d, r14d
0x1800677b4  test    edi, edi
0x1800677b6  jle     loc_180067893
0x1800677bc  mov     r15d, 30h ; '0'
0x1800677c2  mov     eax, r10d
0x1800677c5  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x1800677cb  cmp     r9d, 61h ; 'a'
0x1800677cf  ja      short loc_18006783B
0x1800677d1  jz      loc_18006785C
0x1800677d7  cmp     r9d, 38h ; '8'
0x1800677db  ja      short loc_18006780F
0x1800677dd  jz      short loc_18006780A
0x1800677df  mov     ecx, r9d
0x1800677e2  sub     ecx, r15d
0x1800677e5  jz      short loc_18006780A
0x1800677e7  sub     ecx, 1
0x1800677ea  jz      short loc_18006780A
0x1800677ec  sub     ecx, 1
0x1800677ef  jz      short loc_18006780A
0x1800677f1  sub     ecx, 1
0x1800677f4  jz      short loc_18006780A
0x1800677f6  sub     ecx, 1
0x1800677f9  jz      short loc_18006780A
0x1800677fb  sub     ecx, 1
0x1800677fe  jz      short loc_18006780A
0x180067800  sub     ecx, 1
0x180067803  jz      short loc_18006780A
0x180067805  cmp     ecx, 1
0x180067808  jnz     short loc_180067857
0x18006780a  sub     r9b, r15b
0x18006780d  jmp     short loc_180067860
0x18006780f  mov     ecx, r9d
0x180067812  sub     ecx, 39h ; '9'
0x180067815  jz      short loc_18006780A
0x180067817  sub     ecx, 8
0x18006781a  jz      short loc_180067835
0x18006781c  sub     ecx, 1
0x18006781f  jz      short loc_180067835
0x180067821  sub     ecx, 1
0x180067824  jz      short loc_180067835
0x180067826  sub     ecx, 1
0x180067829  jz      short loc_180067835
0x18006782b  sub     ecx, 1
0x18006782e  jz      short loc_180067835
0x180067830  cmp     ecx, 1
0x180067833  jnz     short loc_180067857
0x180067835  sub     r9b, 37h ; '7'
0x180067839  jmp     short loc_180067860
0x18006783b  mov     ecx, r9d
0x18006783e  sub     ecx, 62h ; 'b'
0x180067841  jz      short loc_18006785C
0x180067843  sub     ecx, 1
0x180067846  jz      short loc_18006785C
0x180067848  sub     ecx, 1
0x18006784b  jz      short loc_18006785C
0x18006784d  sub     ecx, 1
0x180067850  jz      short loc_18006785C
0x180067852  cmp     ecx, 1
0x180067855  jz      short loc_18006785C
0x180067857  mov     r9b, r14b
0x18006785a  jmp     short loc_180067860
0x18006785c  sub     r9b, 57h ; 'W'
0x180067860  mov     rdx, [rsp+21B0h+var_2160]
0x180067865  mov     eax, r10d
0x180067868  and     eax, 1
0x18006786b  mov     r8d, r10d
0x18006786e  shl     eax, 2
0x180067871  mov     ecx, 4
0x180067876  shr     r8, 1
0x180067879  sub     ecx, eax
0x18006787b  shl     r9b, cl
0x18006787e  inc     r10d
0x180067881  or      [r8+rdx], r9b
0x180067885  cmp     r10d, edi
0x180067888  jl      loc_1800677C2
0x18006788e  mov     r15, [rsp+21B0h+var_2180]
0x180067893  mov     rax, [rsp+21B0h+var_2160]
0x180067898  mov     r9d, 3; dwType
0x18006789e  mov     rcx, [r12]; hKey
0x1800678a2  xor     r8d, r8d; Reserved
0x1800678a5  mov     [rsp+21B0h+cbData], esi; cbData
0x1800678a9  mov     rdx, r13; lpValueName
0x1800678ac  mov     [rsp+21B0h+lpData], rax; lpData
0x1800678b1  call    cs:__imp_RegSetValueExW
0x1800678b7  lea     rcx, [rsp+21B0h+var_2160]
0x1800678bc  mov     ebx, eax
0x1800678be  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800678c3  mov     r14, qword ptr [rsp+21B0h+Data]
0x1800678c8  xor     esi, esi
0x1800678ca  jmp     short loc_180067909
0x1800678cc  lea     rax, [rbp+20B0h+String1]
0x1800678d0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800678d4  inc     rdi
0x1800678d7  cmp     [rax+rdi*2], si
0x1800678db  jnz     short loc_1800678D4
0x1800678dd  mov     rcx, [r12]; hKey
0x1800678e1  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
