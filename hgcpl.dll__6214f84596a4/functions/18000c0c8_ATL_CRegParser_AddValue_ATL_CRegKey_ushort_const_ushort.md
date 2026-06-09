# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000c0c8`
- end: `0x18000c574`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000d764`

## callees

- `0x18000bc24`
- `0x18000bc94`
- `0x18000bcec`
- `0x18000c0c8`
- `0x18000c57c`
- `0x18000c7fc`
- `0x18000c814`
- `0x18000cf14`
- `0x18000de50`
- `0x180018a52`
- `0x180018a80`
- `0x180018b10`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000c2ee`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000c2ee`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c221`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c23d`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c221`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000c23d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c2a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c335`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c4d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c521`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c2a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c335`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c4d1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000c521`
- `KERNEL32!lstrcmpiW` at `0x18000c149`
- `KERNEL32!lstrcmpiW` at `0x18000c149`

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
0x18000c0c8  push    rbp
0x18000c0ca  push    rbx
0x18000c0cb  push    rsi
0x18000c0cc  push    rdi
0x18000c0cd  push    r12
0x18000c0cf  push    r13
0x18000c0d1  push    r14
0x18000c0d3  push    r15
0x18000c0d5  lea     rbp, [rsp-2078h]
0x18000c0dd  mov     eax, 2178h
0x18000c0e2  call    _alloca_probe
0x18000c0e7  sub     rsp, rax
0x18000c0ea  mov     rax, cs:__security_cookie
0x18000c0f1  xor     rax, rsp
0x18000c0f4  mov     [rbp+20B0h+var_50], rax
0x18000c0fb  mov     r12, rdx
0x18000c0fe  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x18000c103  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18000c107  mov     [rsp+21B0h+var_2180], r9
0x18000c10c  mov     r15, r9
0x18000c10f  mov     qword ptr [rsp+21B0h+Data], rcx
0x18000c114  mov     r13, r8
0x18000c117  mov     r14, rcx
0x18000c11a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c11f  xor     esi, esi
0x18000c121  test    eax, eax
0x18000c123  js      loc_18000C551
0x18000c129  mov     ebx, esi
0x18000c12b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000c132  cmp     ebx, 4
0x18000c135  jnb     loc_18000C54C
0x18000c13b  movsxd  rdi, ebx
0x18000c13e  lea     rcx, [rbp+20B0h+String1]; lpString1
0x18000c142  add     rdi, rdi
0x18000c145  mov     rdx, [rax+rdi*8]; lpString2
0x18000c149  call    cs:__imp_lstrcmpiW
0x18000c14f  test    eax, eax
0x18000c151  jz      short loc_18000C157
0x18000c153  inc     ebx
0x18000c155  jmp     short loc_18000C12B
0x18000c157  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000c15e  mov     rcx, r14; this
0x18000c161  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18000c166  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000c16b  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18000c16f  mov     rcx, r14; this
0x18000c172  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000c177  test    eax, eax
0x18000c179  js      loc_18000C551
0x18000c17f  mov     eax, 8
0x18000c184  cmp     bx, ax
0x18000c187  jz      loc_18000C4EC
0x18000c18d  cmp     bx, 11h
0x18000c191  jz      loc_18000C34C
0x18000c197  cmp     bx, 13h
0x18000c19b  jz      loc_18000C2D7
0x18000c1a1  mov     eax, 4008h
0x18000c1a6  cmp     bx, ax
0x18000c1a9  jnz     loc_18000C536
0x18000c1af  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c1b3  lea     rcx, [rbp+20B0h+String1]
0x18000c1b7  mov     rax, rdi
0x18000c1ba  inc     rax
0x18000c1bd  cmp     [rcx+rax*2], si
0x18000c1c1  jnz     short loc_18000C1BA
0x18000c1c3  add     eax, 2
0x18000c1c6  mov     [rsp+21B0h+var_2160], rsi
0x18000c1cb  mov     r14d, 2
0x18000c1d1  movsxd  rcx, eax
0x18000c1d4  mov     edx, r14d
0x18000c1d7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000c1dc  cmp     rax, 100h
0x18000c1e2  jbe     short loc_18000C1F8
0x18000c1e4  mov     rdx, rax
0x18000c1e7  lea     rcx, [rsp+21B0h+var_2160]
0x18000c1ec  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000c1f1  mov     rbx, [rsp+21B0h+var_2160]
0x18000c1f6  jmp     short loc_18000C202
0x18000c1f8  lea     rbx, [rsp+21B0h+var_2158]
0x18000c1fd  mov     [rsp+21B0h+var_2160], rbx
0x18000c202  test    rbx, rbx
0x18000c205  jz      loc_18000C2BE
0x18000c20b  xor     eax, eax
0x18000c20d  lea     rsi, [rbp+20B0h+String1]
0x18000c211  cmp     [rbp+20B0h+String1], ax
0x18000c215  jz      short loc_18000C261
0x18000c217  lea     r15d, [rax+30h]
0x18000c21b  xor     r12d, r12d
0x18000c21e  mov     rcx, rsi; lpsz
0x18000c221  call    cs:__imp_CharNextW
0x18000c227  movzx   ecx, word ptr [rsi]
0x18000c22a  cmp     cx, 5Ch ; '\'
0x18000c22e  jnz     short loc_18000C248
0x18000c230  cmp     [rax], r15w
0x18000c234  jnz     short loc_18000C248
0x18000c236  mov     rcx, rax; lpsz
0x18000c239  mov     [rbx], r12w
0x18000c23d  call    cs:__imp_CharNextW
0x18000c243  mov     rsi, rax
0x18000c246  jmp     short loc_18000C24E
0x18000c248  mov     [rbx], cx
0x18000c24b  add     rsi, r14
0x18000c24e  add     rbx, r14
0x18000c251  cmp     [rsi], r12w
0x18000c255  jnz     short loc_18000C21E
0x18000c257  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x18000c25c  mov     r15, [rsp+21B0h+var_2180]
0x18000c261  xor     esi, esi
0x18000c263  mov     [rbx], esi
0x18000c265  mov     r8, [rsp+21B0h+var_2160]
0x18000c26a  test    r8, r8
0x18000c26d  jz      short loc_18000C2B3
0x18000c26f  mov     r10d, esi
0x18000c272  mov     r9, r8
0x18000c275  mov     rcx, rdi
0x18000c278  inc     rcx
0x18000c27b  cmp     [r9+rcx*2], si
0x18000c280  jnz     short loc_18000C278
0x18000c282  inc     ecx
0x18000c284  lea     r9, [r9+rcx*2]
0x18000c288  lea     r10d, [r10+rcx*2]
0x18000c28c  cmp     ecx, 1
0x18000c28f  jnz     short loc_18000C275
0x18000c291  mov     [rsp+21B0h+cbData], r10d; cbData
0x18000c296  lea     r9d, [rcx+6]; dwType
0x18000c29a  mov     rcx, [r12]; hKey
0x18000c29e  mov     rdx, r13; lpValueName
0x18000c2a1  mov     [rsp+21B0h+lpData], r8; lpData
0x18000c2a6  xor     r8d, r8d; Reserved
0x18000c2a9  call    cs:__imp_RegSetValueExW
0x18000c2af  mov     ebx, eax
0x18000c2b1  jmp     short loc_18000C2C3
0x18000c2b3  mov     ecx, 80004005h; int
0x18000c2b8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000c2be  mov     ebx, 0Eh
0x18000c2c3  lea     rcx, [rsp+21B0h+var_2160]
0x18000c2c8  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000c2cd  mov     r14, qword ptr [rsp+21B0h+Data]
0x18000c2d2  jmp     loc_18000C529
0x18000c2d7  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x18000c2dc  mov     [rsp+21B0h+pulOut], esi
0x18000c2e0  xor     r8d, r8d; dwFlags
0x18000c2e3  mov     [rsp+21B0h+var_2180], rsi
0x18000c2e8  xor     edx, edx; lcid
0x18000c2ea  lea     rcx, [rbp+20B0h+String1]; strIn
0x18000c2ee  call    cs:__imp_VarUI4FromStr
0x18000c2f4  mov     ebx, eax
0x18000c2f6  test    eax, eax
0x18000c2f8  jns     short loc_18000C30B
0x18000c2fa  lea     rcx, [rsp+21B0h+var_2180]
0x18000c2ff  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c304  mov     eax, ebx
0x18000c306  jmp     loc_18000C551
0x18000c30b  mov     eax, [rsp+21B0h+pulOut]
0x18000c30f  mov     r9d, 4; dwType
0x18000c315  mov     rcx, [r12]; hKey
0x18000c319  xor     r8d, r8d; Reserved
0x18000c31c  mov     dword ptr [rsp+21B0h+Data], eax
0x18000c320  mov     rdx, r13; lpValueName
0x18000c323  lea     rax, [rsp+21B0h+Data]
0x18000c328  mov     [rsp+21B0h+cbData], 4; cbData
0x18000c330  mov     [rsp+21B0h+lpData], rax; lpData
0x18000c335  call    cs:__imp_RegSetValueExW
0x18000c33b  lea     rcx, [rsp+21B0h+var_2180]
0x18000c340  mov     ebx, eax
0x18000c342  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000c347  jmp     loc_18000C529
0x18000c34c  lea     rax, [rbp+20B0h+String1]
0x18000c350  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c354  inc     rdi
0x18000c357  cmp     [rax+rdi*2], si
0x18000c35b  jnz     short loc_18000C354
0x18000c35d  test    dil, 1
0x18000c361  jz      short loc_18000C36D
0x18000c363  mov     eax, 80004005h
0x18000c368  jmp     loc_18000C551
0x18000c36d  mov     eax, edi
0x18000c36f  mov     r14d, 2
0x18000c375  cdq
0x18000c376  idiv    r14d
0x18000c379  xor     r14d, r14d
0x18000c37c  movsxd  rsi, eax
0x18000c37f  mov     rcx, rsi
0x18000c382  mov     [rsp+21B0h+var_2160], r14
0x18000c387  lea     edx, [r14+1]
0x18000c38b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000c390  cmp     rax, 100h
0x18000c396  jbe     short loc_18000C3AC
0x18000c398  mov     rdx, rax
0x18000c39b  lea     rcx, [rsp+21B0h+var_2160]
0x18000c3a0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000c3a5  mov     rcx, [rsp+21B0h+var_2160]
0x18000c3aa  jmp     short loc_18000C3B6
0x18000c3ac  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18000c3b1  mov     [rsp+21B0h+var_2160], rcx
0x18000c3b6  test    rcx, rcx
0x18000c3b9  jnz     short loc_18000C3C7
0x18000c3bb  lea     rcx, [rsp+21B0h+var_2160]
0x18000c3c0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000c3c5  jmp     short loc_18000C363
0x18000c3c7  mov     r8, rsi; Size
0x18000c3ca  xor     edx, edx; Val
0x18000c3cc  call    memset_0
0x18000c3d1  mov     r10d, r14d
0x18000c3d4  test    edi, edi
0x18000c3d6  jle     loc_18000C4B3
0x18000c3dc  mov     r15d, 30h ; '0'
0x18000c3e2  mov     eax, r10d
0x18000c3e5  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x18000c3eb  cmp     r9d, 61h ; 'a'
0x18000c3ef  ja      short loc_18000C45B
0x18000c3f1  jz      loc_18000C47C
0x18000c3f7  cmp     r9d, 38h ; '8'
0x18000c3fb  ja      short loc_18000C42F
0x18000c3fd  jz      short loc_18000C42A
0x18000c3ff  mov     ecx, r9d
0x18000c402  sub     ecx, r15d
0x18000c405  jz      short loc_18000C42A
0x18000c407  sub     ecx, 1
0x18000c40a  jz      short loc_18000C42A
0x18000c40c  sub     ecx, 1
0x18000c40f  jz      short loc_18000C42A
0x18000c411  sub     ecx, 1
0x18000c414  jz      short loc_18000C42A
0x18000c416  sub     ecx, 1
0x18000c419  jz      short loc_18000C42A
0x18000c41b  sub     ecx, 1
0x18000c41e  jz      short loc_18000C42A
0x18000c420  sub     ecx, 1
0x18000c423  jz      short loc_18000C42A
0x18000c425  cmp     ecx, 1
0x18000c428  jnz     short loc_18000C477
0x18000c42a  sub     r9b, r15b
0x18000c42d  jmp     short loc_18000C480
0x18000c42f  mov     ecx, r9d
0x18000c432  sub     ecx, 39h ; '9'
0x18000c435  jz      short loc_18000C42A
0x18000c437  sub     ecx, 8
0x18000c43a  jz      short loc_18000C455
0x18000c43c  sub     ecx, 1
0x18000c43f  jz      short loc_18000C455
0x18000c441  sub     ecx, 1
0x18000c444  jz      short loc_18000C455
0x18000c446  sub     ecx, 1
0x18000c449  jz      short loc_18000C455
0x18000c44b  sub     ecx, 1
0x18000c44e  jz      short loc_18000C455
0x18000c450  cmp     ecx, 1
0x18000c453  jnz     short loc_18000C477
0x18000c455  sub     r9b, 37h ; '7'
0x18000c459  jmp     short loc_18000C480
0x18000c45b  mov     ecx, r9d
0x18000c45e  sub     ecx, 62h ; 'b'
0x18000c461  jz      short loc_18000C47C
0x18000c463  sub     ecx, 1
0x18000c466  jz      short loc_18000C47C
0x18000c468  sub     ecx, 1
0x18000c46b  jz      short loc_18000C47C
0x18000c46d  sub     ecx, 1
0x18000c470  jz      short loc_18000C47C
0x18000c472  cmp     ecx, 1
0x18000c475  jz      short loc_18000C47C
0x18000c477  mov     r9b, r14b
0x18000c47a  jmp     short loc_18000C480
0x18000c47c  sub     r9b, 57h ; 'W'
0x18000c480  mov     rdx, [rsp+21B0h+var_2160]
0x18000c485  mov     eax, r10d
0x18000c488  and     eax, 1
0x18000c48b  mov     r8d, r10d
0x18000c48e  shl     eax, 2
0x18000c491  mov     ecx, 4
0x18000c496  shr     r8, 1
0x18000c499  sub     ecx, eax
0x18000c49b  shl     r9b, cl
0x18000c49e  inc     r10d
0x18000c4a1  or      [r8+rdx], r9b
0x18000c4a5  cmp     r10d, edi
0x18000c4a8  jl      loc_18000C3E2
0x18000c4ae  mov     r15, [rsp+21B0h+var_2180]
0x18000c4b3  mov     rax, [rsp+21B0h+var_2160]
0x18000c4b8  mov     r9d, 3; dwType
0x18000c4be  mov     rcx, [r12]; hKey
0x18000c4c2  xor     r8d, r8d; Reserved
0x18000c4c5  mov     [rsp+21B0h+cbData], esi; cbData
0x18000c4c9  mov     rdx, r13; lpValueName
0x18000c4cc  mov     [rsp+21B0h+lpData], rax; lpData
0x18000c4d1  call    cs:__imp_RegSetValueExW
0x18000c4d7  lea     rcx, [rsp+21B0h+var_2160]
0x18000c4dc  mov     ebx, eax
0x18000c4de  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000c4e3  mov     r14, qword ptr [rsp+21B0h+Data]
0x18000c4e8  xor     esi, esi
0x18000c4ea  jmp     short loc_18000C529
0x18000c4ec  lea     rax, [rbp+20B0h+String1]
0x18000c4f0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000c4f4  inc     rdi
0x18000c4f7  cmp     [rax+rdi*2], si
0x18000c4fb  jnz     short loc_18000C4F4
0x18000c4fd  mov     rcx, [r12]; hKey
0x18000c501  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
