# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1801141a8`
- end: `0x1801145ca`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1058`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180118418`

## callees

- `0x180110ed0`
- `0x180111960`
- `0x180112124`
- `0x180112754`
- `0x180112ff0`
- `0x1801141a8`
- `0x1801145d0`
- `0x1801148cc`
- `0x1801148e4`
- `0x180114960`
- `0x180117414`
- `0x1801196e8`
- `0x18017b6b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180114388`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011441f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011451b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180114570`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180114388`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011441f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18011451b`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180114570`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801142fa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18011431c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1801142fa`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18011431c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180114224`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180114224`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1801143d3`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1801143d3`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v5; // r14
  ATL::CRegParser *v7; // r13
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
  int j; // r10d
  unsigned __int8 v28; // al
  int v29; // r10d
  char v30; // dl
  __int64 v31; // r8
  __int64 v32; // r9
  __int64 v33; // rdi
  int Token; // eax
  unsigned int v35; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int16 *v37; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v40[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v37 = a4;
  *(_QWORD *)Data = this;
  v5 = a4;
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
    v33 = -1;
    do
      ++v33;
    while ( String1[v33] );
    v20 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
    goto LABEL_51;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    if ( (v23 & 1) == 0 )
    {
      v24 = (int)v23 / 2;
      lpData = 0;
      v25 = ATL::AtlMultiplyThrow<unsigned __int64>(v24, 1);
      if ( v25 <= 0x100 )
      {
        v26 = v40;
        lpData = v40;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v25);
        v26 = lpData;
      }
      if ( v26 )
      {
        memset_0(v26, 0, v24);
        for ( j = 0; j < (int)v23; *(_BYTE *)(v32 + v31) |= v28 << (4 - 4 * v30) )
        {
          v28 = ATL::CRegParser::ChToByte(String1[j]);
          v30 = v29 & 1;
          j = v29 + 1;
        }
        v20 = RegSetValueExW(*a2, a3, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        v5 = v37;
        goto LABEL_51;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
    }
    return 2147500037LL;
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
        v13 = v40;
        lpData = v40;
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
          v7 = *(ATL::CRegParser **)Data;
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
        v20 = RegSetValueExW(*a2, a3, 0, 7u, lpData, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      v5 = v37;
      goto LABEL_51;
    }
LABEL_53:
    Token = ATL::CRegParser::NextToken(v7, v5);
    v35 = 0;
    if ( Token < 0 )
      return (unsigned int)Token;
    return v35;
  }
  pulOut = 0;
  v37 = 0;
  v21 = VarUI4FromStr(String1, 0, 0, &pulOut);
  if ( v21 < 0 )
  {
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
    return (unsigned int)v21;
  }
  v22 = *a2;
  *(_DWORD *)Data = pulOut;
  v20 = RegSetValueExW(v22, a3, 0, 4u, Data, 4u);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v37);
LABEL_51:
  if ( !v20 )
    goto LABEL_53;
  return ATL::AtlHresultFromWin32(v20);
}

```

## disassembly

```asm
0x1801141a8  push    rbp
0x1801141aa  push    rbx
0x1801141ab  push    rsi
0x1801141ac  push    rdi
0x1801141ad  push    r12
0x1801141af  push    r13
0x1801141b1  push    r14
0x1801141b3  push    r15
0x1801141b5  lea     rbp, [rsp-2078h]
0x1801141bd  mov     eax, 2178h
0x1801141c2  call    _alloca_probe
0x1801141c7  sub     rsp, rax
0x1801141ca  mov     rax, cs:__security_cookie
0x1801141d1  xor     rax, rsp
0x1801141d4  mov     [rbp+20B0h+var_50], rax
0x1801141db  mov     r15, rdx
0x1801141de  mov     [rsp+21B0h+var_2178], r9
0x1801141e3  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x1801141e7  mov     qword ptr [rsp+21B0h+Data], rcx
0x1801141ec  mov     r14, r9
0x1801141ef  mov     r12, r8
0x1801141f2  mov     r13, rcx
0x1801141f5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801141fa  xor     esi, esi
0x1801141fc  test    eax, eax
0x1801141fe  js      loc_1801145A6
0x180114204  mov     ebx, esi
0x180114206  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18011420d  cmp     ebx, 4
0x180114210  jnb     loc_1801145A1
0x180114216  movsxd  rdi, ebx
0x180114219  lea     rcx, [rbp+20B0h+String1]; lpString1
0x18011421d  add     rdi, rdi
0x180114220  mov     rdx, [rax+rdi*8]; lpString2
0x180114224  call    cs:__imp_lstrcmpiW
0x18011422b  nop     dword ptr [rax+rax+00h]
0x180114230  test    eax, eax
0x180114232  jz      short loc_180114238
0x180114234  inc     ebx
0x180114236  jmp     short loc_180114206
0x180114238  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18011423f  mov     rcx, r13; this
0x180114242  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180114247  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18011424c  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180114250  mov     rcx, r13; this
0x180114253  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180114258  test    eax, eax
0x18011425a  js      loc_1801145A6
0x180114260  cmp     bx, 8
0x180114264  jz      loc_18011453C
0x18011426a  cmp     bx, 11h
0x18011426e  jz      loc_18011443C
0x180114274  cmp     bx, 13h
0x180114278  jz      loc_1801143BC
0x18011427e  mov     eax, 4008h
0x180114283  cmp     bx, ax
0x180114286  jnz     loc_18011458B
0x18011428c  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180114290  lea     rcx, [rbp+20B0h+String1]
0x180114294  mov     rax, rdi
0x180114297  inc     rax
0x18011429a  cmp     [rcx+rax*2], si
0x18011429e  jnz     short loc_180114297
0x1801142a0  add     eax, 2
0x1801142a3  mov     [rsp+21B0h+var_2160], rsi
0x1801142a8  mov     r14d, 2
0x1801142ae  movsxd  rcx, eax
0x1801142b1  mov     edx, r14d
0x1801142b4  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1801142b9  cmp     rax, 100h
0x1801142bf  jbe     short loc_1801142D5
0x1801142c1  mov     rdx, rax
0x1801142c4  lea     rcx, [rsp+21B0h+var_2160]
0x1801142c9  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1801142ce  mov     rbx, [rsp+21B0h+var_2160]
0x1801142d3  jmp     short loc_1801142DF
0x1801142d5  lea     rbx, [rsp+21B0h+var_2158]
0x1801142da  mov     [rsp+21B0h+var_2160], rbx
0x1801142df  test    rbx, rbx
0x1801142e2  jz      loc_1801143A3
0x1801142e8  xor     eax, eax
0x1801142ea  lea     rsi, [rbp+20B0h+String1]
0x1801142ee  cmp     [rbp+20B0h+String1], ax
0x1801142f2  jz      short loc_180114341
0x1801142f4  xor     r13d, r13d
0x1801142f7  mov     rcx, rsi; lpsz
0x1801142fa  call    cs:__imp_CharNextW
0x180114301  nop     dword ptr [rax+rax+00h]
0x180114306  movzx   ecx, word ptr [rsi]
0x180114309  cmp     cx, 5Ch ; '\'
0x18011430d  jnz     short loc_18011432D
0x18011430f  cmp     word ptr [rax], 30h ; '0'
0x180114313  jnz     short loc_18011432D
0x180114315  mov     rcx, rax; lpsz
0x180114318  mov     [rbx], r13w
0x18011431c  call    cs:__imp_CharNextW
0x180114323  nop     dword ptr [rax+rax+00h]
0x180114328  mov     rsi, rax
0x18011432b  jmp     short loc_180114333
0x18011432d  mov     [rbx], cx
0x180114330  add     rsi, r14
0x180114333  add     rbx, r14
0x180114336  cmp     [rsi], r13w
0x18011433a  jnz     short loc_1801142F7
0x18011433c  mov     r13, qword ptr [rsp+21B0h+Data]
0x180114341  xor     esi, esi
0x180114343  mov     [rbx], esi
0x180114345  mov     r8, [rsp+21B0h+var_2160]
0x18011434a  test    r8, r8
0x18011434d  jz      short loc_180114398
0x18011434f  mov     r10d, esi
0x180114352  mov     r9, r8
0x180114355  mov     rcx, rdi
0x180114358  inc     rcx
0x18011435b  cmp     [r9+rcx*2], si
0x180114360  jnz     short loc_180114358
0x180114362  inc     ecx
0x180114364  lea     r9, [r9+rcx*2]
0x180114368  lea     r10d, [r10+rcx*2]
0x18011436c  cmp     ecx, 1
0x18011436f  jnz     short loc_180114355
0x180114371  mov     [rsp+21B0h+cbData], r10d; cbData
0x180114376  lea     r9d, [rcx+6]; dwType
0x18011437a  mov     rcx, [r15]; hKey
0x18011437d  mov     rdx, r12; lpValueName
0x180114380  mov     [rsp+21B0h+lpData], r8; lpData
0x180114385  xor     r8d, r8d; Reserved
0x180114388  call    cs:__imp_RegSetValueExW
0x18011438f  nop     dword ptr [rax+rax+00h]
0x180114394  mov     ebx, eax
0x180114396  jmp     short loc_1801143A8
0x180114398  mov     ecx, 80004005h; int
0x18011439d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1801143a3  mov     ebx, 0Eh
0x1801143a8  lea     rcx, [rsp+21B0h+var_2160]
0x1801143ad  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1801143b2  mov     r14, [rsp+21B0h+var_2178]
0x1801143b7  jmp     loc_18011457E
0x1801143bc  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x1801143c1  mov     [rsp+21B0h+pulOut], esi
0x1801143c5  xor     r8d, r8d; dwFlags
0x1801143c8  mov     [rsp+21B0h+var_2178], rsi
0x1801143cd  xor     edx, edx; lcid
0x1801143cf  lea     rcx, [rbp+20B0h+String1]; strIn
0x1801143d3  call    cs:__imp_VarUI4FromStr
0x1801143da  nop     dword ptr [rax+rax+00h]
0x1801143df  mov     ebx, eax
0x1801143e1  test    eax, eax
0x1801143e3  jns     short loc_1801143F6
0x1801143e5  lea     rcx, [rsp+21B0h+var_2178]
0x1801143ea  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1801143ef  mov     eax, ebx
0x1801143f1  jmp     loc_1801145A6
0x1801143f6  mov     eax, [rsp+21B0h+pulOut]
0x1801143fa  mov     r9d, 4; dwType
0x180114400  mov     rcx, [r15]; hKey
0x180114403  xor     r8d, r8d; Reserved
0x180114406  mov     dword ptr [rsp+21B0h+Data], eax
0x18011440a  mov     rdx, r12; lpValueName
0x18011440d  lea     rax, [rsp+21B0h+Data]
0x180114412  mov     [rsp+21B0h+cbData], 4; cbData
0x18011441a  mov     [rsp+21B0h+lpData], rax; lpData
0x18011441f  call    cs:__imp_RegSetValueExW
0x180114426  nop     dword ptr [rax+rax+00h]
0x18011442b  lea     rcx, [rsp+21B0h+var_2178]
0x180114430  mov     ebx, eax
0x180114432  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180114437  jmp     loc_18011457E
0x18011443c  lea     rax, [rbp+20B0h+String1]
0x180114440  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180114444  inc     rdi
0x180114447  cmp     [rax+rdi*2], si
0x18011444b  jnz     short loc_180114444
0x18011444d  test    dil, 1
0x180114451  jz      short loc_18011445D
0x180114453  mov     eax, 80004005h
0x180114458  jmp     loc_1801145A6
0x18011445d  mov     eax, edi
0x18011445f  mov     r14d, 2
0x180114465  cdq
0x180114466  idiv    r14d
0x180114469  xor     r14d, r14d
0x18011446c  movsxd  rsi, eax
0x18011446f  mov     rcx, rsi
0x180114472  mov     [rsp+21B0h+var_2160], r14
0x180114477  lea     edx, [r14+1]
0x18011447b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180114480  cmp     rax, 100h
0x180114486  jbe     short loc_18011449C
0x180114488  mov     rdx, rax
0x18011448b  lea     rcx, [rsp+21B0h+var_2160]
0x180114490  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180114495  mov     rcx, [rsp+21B0h+var_2160]
0x18011449a  jmp     short loc_1801144A6
0x18011449c  lea     rcx, [rsp+21B0h+var_2158]; void *
0x1801144a1  mov     [rsp+21B0h+var_2160], rcx
0x1801144a6  test    rcx, rcx
0x1801144a9  jnz     short loc_1801144B7
0x1801144ab  lea     rcx, [rsp+21B0h+var_2160]
0x1801144b0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1801144b5  jmp     short loc_180114453
0x1801144b7  mov     r8, rsi; Size
0x1801144ba  xor     edx, edx; Val
0x1801144bc  call    memset_0
0x1801144c1  mov     r10d, r14d
0x1801144c4  test    edi, edi
0x1801144c6  jle     short loc_1801144FE
0x1801144c8  mov     r8, [rsp+21B0h+var_2160]
0x1801144cd  mov     ecx, r10d
0x1801144d0  mov     r9d, r10d
0x1801144d3  shr     r9, 1
0x1801144d6  movzx   ecx, [rbp+rcx*2+20B0h+String1]; unsigned __int16
0x1801144db  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x1801144e0  mov     edx, r10d
0x1801144e3  mov     ecx, 4
0x1801144e8  and     edx, 1
0x1801144eb  inc     r10d
0x1801144ee  shl     edx, 2
0x1801144f1  sub     ecx, edx
0x1801144f3  shl     al, cl
0x1801144f5  or      [r9+r8], al
0x1801144f9  cmp     r10d, edi
0x1801144fc  jl      short loc_1801144C8
0x1801144fe  mov     rax, [rsp+21B0h+var_2160]
0x180114503  mov     r9d, 3; dwType
0x180114509  mov     rcx, [r15]; hKey
0x18011450c  xor     r8d, r8d; Reserved
0x18011450f  mov     [rsp+21B0h+cbData], esi; cbData
0x180114513  mov     rdx, r12; lpValueName
0x180114516  mov     [rsp+21B0h+lpData], rax; lpData
0x18011451b  call    cs:__imp_RegSetValueExW
0x180114522  nop     dword ptr [rax+rax+00h]
0x180114527  lea     rcx, [rsp+21B0h+var_2160]
0x18011452c  mov     ebx, eax
0x18011452e  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180114533  mov     r14, [rsp+21B0h+var_2178]
0x180114538  xor     esi, esi
0x18011453a  jmp     short loc_18011457E
0x18011453c  lea     rax, [rbp+20B0h+String1]
0x180114540  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180114544  inc     rdi
0x180114547  cmp     [rax+rdi*2], si
0x18011454b  jnz     short loc_180114544
0x18011454d  mov     rcx, [r15]; hKey
0x180114550  lea     eax, ds:2[rdi*2]
0x180114557  mov     [rsp+21B0h+cbData], eax; cbData
0x18011455b  mov     r9d, 1; dwType
0x180114561  lea     rax, [rbp+20B0h+String1]
0x180114565  xor     r8d, r8d; Reserved
0x180114568  mov     rdx, r12; lpValueName
0x18011456b  mov     [rsp+21B0h+lpData], rax; lpData
0x180114570  call    cs:__imp_RegSetValueExW
0x180114577  nop     dword ptr [rax+rax+00h]
0x18011457c  mov     ebx, eax
0x18011457e  test    ebx, ebx
0x180114580  jz      short loc_18011458B
0x180114582  mov     ecx, ebx; unsigned int
0x180114584  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180114589  jmp     short loc_1801145A6
0x18011458b  mov     rdx, r14; unsigned __int16 *
0x18011458e  mov     rcx, r13; this
0x180114591  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180114596  test    eax, eax
0x180114598  mov     ecx, esi
0x18011459a  cmovs   ecx, eax
0x18011459d  mov     eax, ecx
0x18011459f  jmp     short loc_1801145A6
0x1801145a1  mov     eax, 80020009h
0x1801145a6  mov     rcx, [rbp+20B0h+var_50]
0x1801145ad  xor     rcx, rsp; StackCookie
0x1801145b0  call    __security_check_cookie
0x1801145b5  add     rsp, 2178h
0x1801145bc  pop     r15
0x1801145be  pop     r14
0x1801145c0  pop     r13
0x1801145c2  pop     r12
0x1801145c4  pop     rdi
0x1801145c5  pop     rsi
0x1801145c6  pop     rbx
0x1801145c7  pop     rbp
0x1801145c8  retn
```
