# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18010cc38`
- end: `0x18010d0e4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180110bf8`

## callees

- `0x1801099f0`
- `0x18010a450`
- `0x18010ac08`
- `0x18010b218`
- `0x18010baa0`
- `0x18010cc38`
- `0x18010d0ec`
- `0x18010d3e4`
- `0x18010d3fc`
- `0x18010fd0c`
- `0x180111e08`
- `0x180172350`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010ce19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010cea5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010d041`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010d091`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010ce19`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010cea5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010d041`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18010d091`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18010cd91`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18010cdad`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18010cd91`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18010cdad`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18010ccb9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18010ccb9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18010ce5e`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18010ce5e`

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
  WCHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

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
0x18010cc38  push    rbp
0x18010cc3a  push    rbx
0x18010cc3b  push    rsi
0x18010cc3c  push    rdi
0x18010cc3d  push    r12
0x18010cc3f  push    r13
0x18010cc41  push    r14
0x18010cc43  push    r15
0x18010cc45  lea     rbp, [rsp-2078h]
0x18010cc4d  mov     eax, 2178h
0x18010cc52  call    _alloca_probe
0x18010cc57  sub     rsp, rax
0x18010cc5a  mov     rax, cs:__security_cookie
0x18010cc61  xor     rax, rsp
0x18010cc64  mov     [rbp+20B0h+var_50], rax
0x18010cc6b  mov     r12, rdx
0x18010cc6e  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x18010cc73  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18010cc77  mov     [rsp+21B0h+var_2180], r9
0x18010cc7c  mov     r15, r9
0x18010cc7f  mov     qword ptr [rsp+21B0h+Data], rcx
0x18010cc84  mov     r13, r8
0x18010cc87  mov     r14, rcx
0x18010cc8a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18010cc8f  xor     esi, esi
0x18010cc91  test    eax, eax
0x18010cc93  js      loc_18010D0C1
0x18010cc99  mov     ebx, esi
0x18010cc9b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18010cca2  cmp     ebx, 4
0x18010cca5  jnb     loc_18010D0BC
0x18010ccab  movsxd  rdi, ebx
0x18010ccae  lea     rcx, [rbp+20B0h+String1]; lpString1
0x18010ccb2  add     rdi, rdi
0x18010ccb5  mov     rdx, [rax+rdi*8]; lpString2
0x18010ccb9  call    cs:__imp_lstrcmpiW
0x18010ccbf  test    eax, eax
0x18010ccc1  jz      short loc_18010CCC7
0x18010ccc3  inc     ebx
0x18010ccc5  jmp     short loc_18010CC9B
0x18010ccc7  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18010ccce  mov     rcx, r14; this
0x18010ccd1  movzx   ebx, word ptr [rbx+rdi*8+8]
0x18010ccd6  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18010ccdb  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x18010ccdf  mov     rcx, r14; this
0x18010cce2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18010cce7  test    eax, eax
0x18010cce9  js      loc_18010D0C1
0x18010ccef  mov     eax, 8
0x18010ccf4  cmp     bx, ax
0x18010ccf7  jz      loc_18010D05C
0x18010ccfd  cmp     bx, 11h
0x18010cd01  jz      loc_18010CEBC
0x18010cd07  cmp     bx, 13h
0x18010cd0b  jz      loc_18010CE47
0x18010cd11  mov     eax, 4008h
0x18010cd16  cmp     bx, ax
0x18010cd19  jnz     loc_18010D0A6
0x18010cd1f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010cd23  lea     rcx, [rbp+20B0h+String1]
0x18010cd27  mov     rax, rdi
0x18010cd2a  inc     rax
0x18010cd2d  cmp     [rcx+rax*2], si
0x18010cd31  jnz     short loc_18010CD2A
0x18010cd33  add     eax, 2
0x18010cd36  mov     [rsp+21B0h+var_2160], rsi
0x18010cd3b  mov     r14d, 2
0x18010cd41  movsxd  rcx, eax
0x18010cd44  mov     edx, r14d
0x18010cd47  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18010cd4c  cmp     rax, 100h
0x18010cd52  jbe     short loc_18010CD68
0x18010cd54  mov     rdx, rax
0x18010cd57  lea     rcx, [rsp+21B0h+var_2160]
0x18010cd5c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18010cd61  mov     rbx, [rsp+21B0h+var_2160]
0x18010cd66  jmp     short loc_18010CD72
0x18010cd68  lea     rbx, [rsp+21B0h+var_2158]
0x18010cd6d  mov     [rsp+21B0h+var_2160], rbx
0x18010cd72  test    rbx, rbx
0x18010cd75  jz      loc_18010CE2E
0x18010cd7b  xor     eax, eax
0x18010cd7d  lea     rsi, [rbp+20B0h+String1]
0x18010cd81  cmp     [rbp+20B0h+String1], ax
0x18010cd85  jz      short loc_18010CDD1
0x18010cd87  lea     r15d, [rax+30h]
0x18010cd8b  xor     r12d, r12d
0x18010cd8e  mov     rcx, rsi; lpsz
0x18010cd91  call    cs:__imp_CharNextW
0x18010cd97  movzx   ecx, word ptr [rsi]
0x18010cd9a  cmp     cx, 5Ch ; '\'
0x18010cd9e  jnz     short loc_18010CDB8
0x18010cda0  cmp     [rax], r15w
0x18010cda4  jnz     short loc_18010CDB8
0x18010cda6  mov     rcx, rax; lpsz
0x18010cda9  mov     [rbx], r12w
0x18010cdad  call    cs:__imp_CharNextW
0x18010cdb3  mov     rsi, rax
0x18010cdb6  jmp     short loc_18010CDBE
0x18010cdb8  mov     [rbx], cx
0x18010cdbb  add     rsi, r14
0x18010cdbe  add     rbx, r14
0x18010cdc1  cmp     [rsi], r12w
0x18010cdc5  jnz     short loc_18010CD8E
0x18010cdc7  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x18010cdcc  mov     r15, [rsp+21B0h+var_2180]
0x18010cdd1  xor     esi, esi
0x18010cdd3  mov     [rbx], esi
0x18010cdd5  mov     r8, [rsp+21B0h+var_2160]
0x18010cdda  test    r8, r8
0x18010cddd  jz      short loc_18010CE23
0x18010cddf  mov     r10d, esi
0x18010cde2  mov     r9, r8
0x18010cde5  mov     rcx, rdi
0x18010cde8  inc     rcx
0x18010cdeb  cmp     [r9+rcx*2], si
0x18010cdf0  jnz     short loc_18010CDE8
0x18010cdf2  inc     ecx
0x18010cdf4  lea     r9, [r9+rcx*2]
0x18010cdf8  lea     r10d, [r10+rcx*2]
0x18010cdfc  cmp     ecx, 1
0x18010cdff  jnz     short loc_18010CDE5
0x18010ce01  mov     [rsp+21B0h+cbData], r10d; cbData
0x18010ce06  lea     r9d, [rcx+6]; dwType
0x18010ce0a  mov     rcx, [r12]; hKey
0x18010ce0e  mov     rdx, r13; lpValueName
0x18010ce11  mov     [rsp+21B0h+lpData], r8; lpData
0x18010ce16  xor     r8d, r8d; Reserved
0x18010ce19  call    cs:__imp_RegSetValueExW
0x18010ce1f  mov     ebx, eax
0x18010ce21  jmp     short loc_18010CE33
0x18010ce23  mov     ecx, 80004005h; int
0x18010ce28  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18010ce2e  mov     ebx, 0Eh
0x18010ce33  lea     rcx, [rsp+21B0h+var_2160]
0x18010ce38  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18010ce3d  mov     r14, qword ptr [rsp+21B0h+Data]
0x18010ce42  jmp     loc_18010D099
0x18010ce47  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x18010ce4c  mov     [rsp+21B0h+pulOut], esi
0x18010ce50  xor     r8d, r8d; dwFlags
0x18010ce53  mov     [rsp+21B0h+var_2180], rsi
0x18010ce58  xor     edx, edx; lcid
0x18010ce5a  lea     rcx, [rbp+20B0h+String1]; strIn
0x18010ce5e  call    cs:__imp_VarUI4FromStr
0x18010ce64  mov     ebx, eax
0x18010ce66  test    eax, eax
0x18010ce68  jns     short loc_18010CE7B
0x18010ce6a  lea     rcx, [rsp+21B0h+var_2180]
0x18010ce6f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18010ce74  mov     eax, ebx
0x18010ce76  jmp     loc_18010D0C1
0x18010ce7b  mov     eax, [rsp+21B0h+pulOut]
0x18010ce7f  mov     r9d, 4; dwType
0x18010ce85  mov     rcx, [r12]; hKey
0x18010ce89  xor     r8d, r8d; Reserved
0x18010ce8c  mov     dword ptr [rsp+21B0h+Data], eax
0x18010ce90  mov     rdx, r13; lpValueName
0x18010ce93  lea     rax, [rsp+21B0h+Data]
0x18010ce98  mov     [rsp+21B0h+cbData], 4; cbData
0x18010cea0  mov     [rsp+21B0h+lpData], rax; lpData
0x18010cea5  call    cs:__imp_RegSetValueExW
0x18010ceab  lea     rcx, [rsp+21B0h+var_2180]
0x18010ceb0  mov     ebx, eax
0x18010ceb2  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18010ceb7  jmp     loc_18010D099
0x18010cebc  lea     rax, [rbp+20B0h+String1]
0x18010cec0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010cec4  inc     rdi
0x18010cec7  cmp     [rax+rdi*2], si
0x18010cecb  jnz     short loc_18010CEC4
0x18010cecd  test    dil, 1
0x18010ced1  jz      short loc_18010CEDD
0x18010ced3  mov     eax, 80004005h
0x18010ced8  jmp     loc_18010D0C1
0x18010cedd  mov     eax, edi
0x18010cedf  mov     r14d, 2
0x18010cee5  cdq
0x18010cee6  idiv    r14d
0x18010cee9  xor     r14d, r14d
0x18010ceec  movsxd  rsi, eax
0x18010ceef  mov     rcx, rsi
0x18010cef2  mov     [rsp+21B0h+var_2160], r14
0x18010cef7  lea     edx, [r14+1]
0x18010cefb  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18010cf00  cmp     rax, 100h
0x18010cf06  jbe     short loc_18010CF1C
0x18010cf08  mov     rdx, rax
0x18010cf0b  lea     rcx, [rsp+21B0h+var_2160]
0x18010cf10  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18010cf15  mov     rcx, [rsp+21B0h+var_2160]
0x18010cf1a  jmp     short loc_18010CF26
0x18010cf1c  lea     rcx, [rsp+21B0h+var_2158]; void *
0x18010cf21  mov     [rsp+21B0h+var_2160], rcx
0x18010cf26  test    rcx, rcx
0x18010cf29  jnz     short loc_18010CF37
0x18010cf2b  lea     rcx, [rsp+21B0h+var_2160]
0x18010cf30  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18010cf35  jmp     short loc_18010CED3
0x18010cf37  mov     r8, rsi; Size
0x18010cf3a  xor     edx, edx; Val
0x18010cf3c  call    memset_0
0x18010cf41  mov     r10d, r14d
0x18010cf44  test    edi, edi
0x18010cf46  jle     loc_18010D023
0x18010cf4c  mov     r15d, 30h ; '0'
0x18010cf52  mov     eax, r10d
0x18010cf55  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x18010cf5b  cmp     r9d, 61h ; 'a'
0x18010cf5f  ja      short loc_18010CFCB
0x18010cf61  jz      loc_18010CFEC
0x18010cf67  cmp     r9d, 38h ; '8'
0x18010cf6b  ja      short loc_18010CF9F
0x18010cf6d  jz      short loc_18010CF9A
0x18010cf6f  mov     ecx, r9d
0x18010cf72  sub     ecx, r15d
0x18010cf75  jz      short loc_18010CF9A
0x18010cf77  sub     ecx, 1
0x18010cf7a  jz      short loc_18010CF9A
0x18010cf7c  sub     ecx, 1
0x18010cf7f  jz      short loc_18010CF9A
0x18010cf81  sub     ecx, 1
0x18010cf84  jz      short loc_18010CF9A
0x18010cf86  sub     ecx, 1
0x18010cf89  jz      short loc_18010CF9A
0x18010cf8b  sub     ecx, 1
0x18010cf8e  jz      short loc_18010CF9A
0x18010cf90  sub     ecx, 1
0x18010cf93  jz      short loc_18010CF9A
0x18010cf95  cmp     ecx, 1
0x18010cf98  jnz     short loc_18010CFE7
0x18010cf9a  sub     r9b, r15b
0x18010cf9d  jmp     short loc_18010CFF0
0x18010cf9f  mov     ecx, r9d
0x18010cfa2  sub     ecx, 39h ; '9'
0x18010cfa5  jz      short loc_18010CF9A
0x18010cfa7  sub     ecx, 8
0x18010cfaa  jz      short loc_18010CFC5
0x18010cfac  sub     ecx, 1
0x18010cfaf  jz      short loc_18010CFC5
0x18010cfb1  sub     ecx, 1
0x18010cfb4  jz      short loc_18010CFC5
0x18010cfb6  sub     ecx, 1
0x18010cfb9  jz      short loc_18010CFC5
0x18010cfbb  sub     ecx, 1
0x18010cfbe  jz      short loc_18010CFC5
0x18010cfc0  cmp     ecx, 1
0x18010cfc3  jnz     short loc_18010CFE7
0x18010cfc5  sub     r9b, 37h ; '7'
0x18010cfc9  jmp     short loc_18010CFF0
0x18010cfcb  mov     ecx, r9d
0x18010cfce  sub     ecx, 62h ; 'b'
0x18010cfd1  jz      short loc_18010CFEC
0x18010cfd3  sub     ecx, 1
0x18010cfd6  jz      short loc_18010CFEC
0x18010cfd8  sub     ecx, 1
0x18010cfdb  jz      short loc_18010CFEC
0x18010cfdd  sub     ecx, 1
0x18010cfe0  jz      short loc_18010CFEC
0x18010cfe2  cmp     ecx, 1
0x18010cfe5  jz      short loc_18010CFEC
0x18010cfe7  mov     r9b, r14b
0x18010cfea  jmp     short loc_18010CFF0
0x18010cfec  sub     r9b, 57h ; 'W'
0x18010cff0  mov     rdx, [rsp+21B0h+var_2160]
0x18010cff5  mov     eax, r10d
0x18010cff8  and     eax, 1
0x18010cffb  mov     r8d, r10d
0x18010cffe  shl     eax, 2
0x18010d001  mov     ecx, 4
0x18010d006  shr     r8, 1
0x18010d009  sub     ecx, eax
0x18010d00b  shl     r9b, cl
0x18010d00e  inc     r10d
0x18010d011  or      [r8+rdx], r9b
0x18010d015  cmp     r10d, edi
0x18010d018  jl      loc_18010CF52
0x18010d01e  mov     r15, [rsp+21B0h+var_2180]
0x18010d023  mov     rax, [rsp+21B0h+var_2160]
0x18010d028  mov     r9d, 3; dwType
0x18010d02e  mov     rcx, [r12]; hKey
0x18010d032  xor     r8d, r8d; Reserved
0x18010d035  mov     [rsp+21B0h+cbData], esi; cbData
0x18010d039  mov     rdx, r13; lpValueName
0x18010d03c  mov     [rsp+21B0h+lpData], rax; lpData
0x18010d041  call    cs:__imp_RegSetValueExW
0x18010d047  lea     rcx, [rsp+21B0h+var_2160]
0x18010d04c  mov     ebx, eax
0x18010d04e  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18010d053  mov     r14, qword ptr [rsp+21B0h+Data]
0x18010d058  xor     esi, esi
0x18010d05a  jmp     short loc_18010D099
0x18010d05c  lea     rax, [rbp+20B0h+String1]
0x18010d060  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18010d064  inc     rdi
0x18010d067  cmp     [rax+rdi*2], si
0x18010d06b  jnz     short loc_18010D064
0x18010d06d  mov     rcx, [r12]; hKey
0x18010d071  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
