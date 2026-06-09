# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000586c`
- end: `0x180005da3`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1335`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18000893c`

## callees

- `0x180004a8c`
- `0x180004e8c`
- `0x180005160`
- `0x18000586c`
- `0x180005dac`
- `0x18000602c`
- `0x1800061ec`
- `0x180007c40`
- `0x1800092fc`
- `0x1800093e4`
- `0x1800396f2`
- `0x180039740`
- `0x180039800`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005a9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005b2f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005d26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005a9c`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005b2f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180005d26`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005a19`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005a34`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005a19`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005a34`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005904`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180005904`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005ae8`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180005ae8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        struct ATL::CRegKey *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegKey *v5; // r13
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  unsigned int v11; // r9d
  __int64 v12; // rax
  int v13; // eax
  unsigned __int64 v14; // rax
  BYTE *v15; // rdi
  WCHAR *j; // rsi
  const WCHAR *v17; // rax
  DWORD cbData; // r10d
  BYTE *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  LSTATUS v22; // edi
  HRESULT v23; // edi
  __int64 v24; // r14
  int v25; // eax
  DWORD v26; // esi
  size_t v27; // rdi
  unsigned __int64 v28; // rax
  const WCHAR *v29; // r15
  unsigned int v30; // r10d
  unsigned int v31; // edx
  char v32; // r9
  int Token; // eax
  BYTE Data[4]; // [rsp+30h] [rbp-22C8h] BYREF
  ULONG pulOut; // [rsp+38h] [rbp-22C0h] BYREF
  ATL::CRegParser *v36; // [rsp+40h] [rbp-22B8h]
  int v37; // [rsp+48h] [rbp-22B0h]
  struct ATL::CRegKey *v38; // [rsp+50h] [rbp-22A8h]
  LPCWSTR lpValueName; // [rsp+58h] [rbp-22A0h]
  __int64 v40; // [rsp+60h] [rbp-2298h] BYREF
  ATL::CRegParser *v41; // [rsp+68h] [rbp-2290h]
  const WCHAR *v42; // [rsp+70h] [rbp-2288h]
  struct ATL::CRegKey *v43; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-2270h]
  BYTE *v45; // [rsp+90h] [rbp-2268h] BYREF
  char v46; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  char v48; // [rsp+1A8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v6 = this;
  v36 = this;
  v38 = a2;
  v41 = this;
  v43 = a2;
  v42 = a3;
  v44 = a4;
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
      v22 = ATL::CRegKey::SetStringValue(v5, a3, String1, v11);
      goto LABEL_77;
    case 17:
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      v37 = v24;
      if ( (v24 & 1) != 0 )
        return 2147500037LL;
      v25 = (int)v24 / 2;
      v26 = (int)v24 / 2;
      *(_DWORD *)Data = (int)v24 / 2;
      LODWORD(v38) = (int)v24 / 2;
      v45 = 0;
      try
      {
        v27 = v25;
        v28 = ATL::AtlMultiplyThrow<unsigned __int64>(v25, 1);
        if ( v28 <= 0x100 )
          v45 = (BYTE *)&v46;
        else
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v45, v28);
      }
      catch ( ... )
      {
        v27 = *(int *)Data;
        v8 = 0;
        LODWORD(v24) = v37;
        v26 = (unsigned int)v38;
        v36 = v41;
        v5 = v43;
        v29 = v42;
        goto LABEL_46;
      }
      v29 = lpValueName;
LABEL_46:
      if ( !v45 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v45);
        return 2147500037LL;
      }
      memset_0(v45, 0, v27);
      v30 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_75:
        v22 = RegSetValueExW(*(HKEY *)v5, v29, 0, 3u, v45, v26);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v45);
        goto LABEL_33;
      }
      while ( 1 )
      {
        v31 = String1[v30];
        if ( v31 > 0x61 )
        {
          if ( v31 == 98 || v31 == 99 || v31 == 100 || v31 - 101 < 2 )
          {
LABEL_73:
            v32 = v31 - 87;
            goto LABEL_74;
          }
LABEL_72:
          v32 = 0;
          goto LABEL_74;
        }
        if ( v31 == 97 )
          goto LABEL_73;
        if ( v31 <= 0x38 )
          break;
        if ( v31 == 57 )
          goto LABEL_60;
        if ( v31 != 65 && v31 != 66 && v31 != 67 && v31 != 68 && v31 - 69 > 1 )
          goto LABEL_72;
        v32 = v31 - 55;
LABEL_74:
        v45[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
        if ( (int)++v30 >= (int)v24 )
          goto LABEL_75;
      }
      if ( v31 != 56 && v31 != 48 && v31 != 49 && v31 != 50 && v31 != 51 && v31 != 52 && v31 != 53 && v31 - 54 > 1 )
        goto LABEL_72;
LABEL_60:
      v32 = v31 - 48;
      goto LABEL_74;
    case 19:
      pulOut = 0;
      v40 = 0;
      v23 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v23 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v22 = RegSetValueExW(*(HKEY *)v5, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v40);
        goto LABEL_77;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v40);
      return (unsigned int)v23;
    case 16392:
      v12 = -1;
      do
        ++v12;
      while ( String1[v12] );
      v13 = v12 + 2;
      lpData = 0;
      try
      {
        v14 = ATL::AtlMultiplyThrow<unsigned __int64>(v13, 2);
        if ( v14 <= 0x100 )
          lpData = (BYTE *)&v48;
        else
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v14);
      }
      catch ( ... )
      {
        v8 = 0;
        v5 = v38;
        v36 = v41;
        lpValueName = v42;
      }
      v15 = lpData;
      if ( lpData )
      {
        for ( j = String1; *j; v15 += 2 )
        {
          v17 = CharNextW(j);
          if ( *j == 92 && *v17 == 48 )
          {
            *(_WORD *)v15 = 0;
            j = CharNextW(v17);
          }
          else
          {
            *(_WORD *)v15 = *j++;
          }
        }
        *(_DWORD *)v15 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v19 = lpData;
        do
        {
          v20 = -1;
          do
            ++v20;
          while ( *(_WORD *)&v19[2 * v20] );
          v21 = (unsigned int)(v20 + 1);
          v19 += 2 * v21;
          cbData += 2 * v21;
        }
        while ( (_DWORD)v21 != 1 );
        v22 = RegSetValueExW(*(HKEY *)v5, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v22 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_33:
      v6 = v36;
LABEL_77:
      if ( v22 )
      {
        return ATL::AtlHresultFromWin32(v22);
      }
      else
      {
LABEL_79:
        Token = ATL::CRegParser::NextToken(v6, v44);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_79;
  }
}

```

## disassembly

```asm
0x18000586c  push    rbx
0x18000586e  push    rsi
0x18000586f  push    rdi
0x180005870  push    r12
0x180005872  push    r13
0x180005874  push    r14
0x180005876  push    r15
0x180005878  mov     eax, 22C0h
0x18000587d  call    _alloca_probe
0x180005882  sub     rsp, rax
0x180005885  mov     rax, cs:__security_cookie
0x18000588c  xor     rax, rsp
0x18000588f  mov     [rsp+22F8h+var_48], rax
0x180005897  mov     r14, r8
0x18000589a  mov     [rsp+22F8h+lpValueName], r8
0x18000589f  mov     r13, rdx
0x1800058a2  mov     r15, rcx
0x1800058a5  mov     [rsp+22F8h+var_22B8], rcx
0x1800058aa  mov     [rsp+22F8h+var_22A8], rdx
0x1800058af  mov     [rsp+22F8h+var_2290], rcx
0x1800058b4  mov     [rsp+22F8h+var_2278], rdx
0x1800058bc  mov     [rsp+22F8h+var_2288], r8
0x1800058c1  mov     [rsp+22F8h+var_2270], r9
0x1800058c9  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800058d1  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800058d6  xor     ebx, ebx
0x1800058d8  test    eax, eax
0x1800058da  js      loc_180005D80
0x1800058e0  mov     edi, ebx
0x1800058e2  lea     r12, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800058e9  cmp     edi, 4
0x1800058ec  jnb     loc_180005D7B
0x1800058f2  movsxd  rsi, edi
0x1800058f5  add     rsi, rsi
0x1800058f8  mov     rdx, [r12+rsi*8]; lpString2
0x1800058fc  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180005904  call    cs:__imp_lstrcmpiW
0x18000590a  test    eax, eax
0x18000590c  jz      short loc_180005912
0x18000590e  inc     edi
0x180005910  jmp     short loc_1800058E9
0x180005912  movzx   edi, word ptr [r12+rsi*8+8]
0x180005918  mov     rcx, r15; this
0x18000591b  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180005920  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180005928  mov     rcx, r15; this
0x18000592b  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180005930  test    eax, eax
0x180005932  js      loc_180005D80
0x180005938  mov     r12d, 8
0x18000593e  cmp     di, r12w
0x180005942  jz      loc_180005D40
0x180005948  cmp     di, 11h
0x18000594c  jz      loc_180005B46
0x180005952  cmp     di, 13h
0x180005956  jz      loc_180005ACD
0x18000595c  mov     eax, 4008h
0x180005961  cmp     di, ax
0x180005964  jnz     loc_180005D62
0x18000596a  lea     rcx, [rsp+22F8h+String1]
0x180005972  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005976  mov     rax, r14
0x180005979  inc     rax
0x18000597c  cmp     [rcx+rax*2], bx
0x180005980  jnz     short loc_180005979
0x180005982  add     eax, 2
0x180005985  mov     [rsp+22F8h+var_2158], rbx
0x18000598d  movsxd  rcx, eax
0x180005990  mov     r15d, 2
0x180005996  mov     edx, r15d
0x180005999  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000599e  cmp     rax, 100h
0x1800059a4  jbe     short loc_1800059B8
0x1800059a6  mov     rdx, rax
0x1800059a9  lea     rcx, [rsp+22F8h+var_2158]
0x1800059b1  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800059b6  jmp     short loc_1800059C8
0x1800059b8  lea     rax, [rsp+22F8h+var_2150]
0x1800059c0  mov     [rsp+22F8h+var_2158], rax
0x1800059c8  jmp     short loc_1800059ED
0x1800059ca  xor     ebx, ebx
0x1800059cc  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800059d0  lea     r15d, [rbx+2]
0x1800059d4  mov     r13, [rsp+22F8h+var_22A8]
0x1800059d9  mov     rax, [rsp+22F8h+var_2290]
0x1800059de  mov     [rsp+22F8h+var_22B8], rax
0x1800059e3  mov     rax, [rsp+22F8h+var_2288]
0x1800059e8  mov     [rsp+22F8h+lpValueName], rax
0x1800059ed  mov     rdi, [rsp+22F8h+var_2158]
0x1800059f5  test    rdi, rdi
0x1800059f8  jz      loc_180005AB1
0x1800059fe  lea     rsi, [rsp+22F8h+String1]
0x180005a06  cmp     [rsp+22F8h+String1], bx
0x180005a0e  jz      short loc_180005A4D
0x180005a10  mov     r12d, 30h ; '0'
0x180005a16  mov     rcx, rsi; lpsz
0x180005a19  call    cs:__imp_CharNextW
0x180005a1f  movzx   ecx, word ptr [rsi]
0x180005a22  cmp     cx, 5Ch ; '\'
0x180005a26  jnz     short loc_180005A3F
0x180005a28  cmp     [rax], r12w
0x180005a2c  jnz     short loc_180005A3F
0x180005a2e  mov     [rdi], bx
0x180005a31  mov     rcx, rax; lpsz
0x180005a34  call    cs:__imp_CharNextW
0x180005a3a  mov     rsi, rax
0x180005a3d  jmp     short loc_180005A45
0x180005a3f  mov     [rdi], cx
0x180005a42  add     rsi, r15
0x180005a45  add     rdi, r15
0x180005a48  cmp     [rsi], bx
0x180005a4b  jnz     short loc_180005A16
0x180005a4d  mov     dword ptr [rdi], 0
0x180005a53  mov     r8, [rsp+22F8h+var_2158]
0x180005a5b  test    r8, r8
0x180005a5e  jz      short loc_180005AA6
0x180005a60  mov     r10d, ebx
0x180005a63  mov     r9, r8
0x180005a66  mov     rcx, r14
0x180005a69  inc     rcx
0x180005a6c  cmp     [r9+rcx*2], bx
0x180005a71  jnz     short loc_180005A69
0x180005a73  inc     ecx
0x180005a75  lea     r9, [r9+rcx*2]
0x180005a79  lea     r10d, [r10+rcx*2]
0x180005a7d  cmp     ecx, 1
0x180005a80  jnz     short loc_180005A66
0x180005a82  mov     [rsp+22F8h+cbData], r10d; cbData
0x180005a87  mov     [rsp+22F8h+lpData], r8; lpData
0x180005a8c  lea     r9d, [rcx+6]; dwType
0x180005a90  xor     r8d, r8d; Reserved
0x180005a93  mov     rdx, [rsp+22F8h+lpValueName]; lpValueName
0x180005a98  mov     rcx, [r13+0]; hKey
0x180005a9c  call    cs:__imp_RegSetValueExW
0x180005aa2  mov     edi, eax
0x180005aa4  jmp     short loc_180005AB6
0x180005aa6  mov     ecx, 80004005h; int
0x180005aab  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180005ab1  mov     edi, 0Eh
0x180005ab6  lea     rcx, [rsp+22F8h+var_2158]
0x180005abe  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180005ac3  mov     r15, [rsp+22F8h+var_22B8]
0x180005ac8  jmp     loc_180005D55
0x180005acd  mov     [rsp+22F8h+pulOut], ebx
0x180005ad1  mov     [rsp+22F8h+var_2298], rbx
0x180005ad6  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180005adb  xor     r8d, r8d; dwFlags
0x180005ade  xor     edx, edx; lcid
0x180005ae0  lea     rcx, [rsp+22F8h+String1]; strIn
0x180005ae8  call    cs:__imp_VarUI4FromStr
0x180005aee  mov     edi, eax
0x180005af0  test    eax, eax
0x180005af2  jns     short loc_180005B05
0x180005af4  lea     rcx, [rsp+22F8h+var_2298]
0x180005af9  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005afe  mov     eax, edi
0x180005b00  jmp     loc_180005D80
0x180005b05  mov     eax, [rsp+22F8h+pulOut]
0x180005b09  mov     dword ptr [rsp+22F8h+Data], eax
0x180005b0d  mov     [rsp+22F8h+cbData], 4; cbData
0x180005b15  lea     rax, [rsp+22F8h+Data]
0x180005b1a  mov     [rsp+22F8h+lpData], rax; lpData
0x180005b1f  mov     r9d, 4; dwType
0x180005b25  xor     r8d, r8d; Reserved
0x180005b28  mov     rdx, r14; lpValueName
0x180005b2b  mov     rcx, [r13+0]; hKey
0x180005b2f  call    cs:__imp_RegSetValueExW
0x180005b35  mov     edi, eax
0x180005b37  lea     rcx, [rsp+22F8h+var_2298]
0x180005b3c  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005b41  jmp     loc_180005D55
0x180005b46  lea     rax, [rsp+22F8h+String1]
0x180005b4e  or      r14, 0FFFFFFFFFFFFFFFFh
0x180005b52  inc     r14
0x180005b55  cmp     [rax+r14*2], bx
0x180005b5a  jnz     short loc_180005B52
0x180005b5c  mov     [rsp+22F8h+var_22B0], r14d
0x180005b61  test    r14b, 1
0x180005b65  jz      short loc_180005B71
0x180005b67  mov     eax, 80004005h
0x180005b6c  jmp     loc_180005D80
0x180005b71  mov     eax, r14d
0x180005b74  cdq
0x180005b75  mov     r15d, 2
0x180005b7b  idiv    r15d
0x180005b7e  movsxd  rsi, eax
0x180005b81  mov     dword ptr [rsp+22F8h+Data], esi
0x180005b85  mov     dword ptr [rsp+22F8h+var_22A8], esi
0x180005b89  mov     [rsp+22F8h+var_2268], rbx
0x180005b91  mov     rdi, rsi
0x180005b94  lea     edx, [r15-1]
0x180005b98  mov     rcx, rsi
0x180005b9b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180005ba0  cmp     rax, 100h
0x180005ba6  jbe     short loc_180005BBA
0x180005ba8  mov     rdx, rax
0x180005bab  lea     rcx, [rsp+22F8h+var_2268]
0x180005bb3  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180005bb8  jmp     short loc_180005BCA
0x180005bba  lea     rax, [rsp+22F8h+var_2260]
0x180005bc2  mov     [rsp+22F8h+var_2268], rax
0x180005bca  mov     r15, [rsp+22F8h+lpValueName]
0x180005bcf  jmp     short loc_180005BF8
0x180005bd1  movsxd  rdi, dword ptr [rsp+22F8h+Data]
0x180005bd6  xor     ebx, ebx
0x180005bd8  mov     r14d, [rsp+22F8h+var_22B0]
0x180005bdd  mov     esi, dword ptr [rsp+22F8h+var_22A8]
0x180005be1  mov     rax, [rsp+22F8h+var_2290]
0x180005be6  mov     [rsp+22F8h+var_22B8], rax
0x180005beb  mov     r13, [rsp+22F8h+var_2278]
0x180005bf3  mov     r15, [rsp+22F8h+var_2288]
0x180005bf8  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180005c00  test    rcx, rcx
0x180005c03  jnz     short loc_180005C17
0x180005c05  lea     rcx, [rsp+22F8h+var_2268]
0x180005c0d  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180005c12  jmp     loc_180005B67
0x180005c17  mov     r8, rdi; Size
0x180005c1a  xor     edx, edx; Val
0x180005c1c  call    memset_0
0x180005c21  mov     r10d, ebx
0x180005c24  test    r14d, r14d
0x180005c27  jle     loc_180005D05
0x180005c2d  mov     r12d, 30h ; '0'
0x180005c33  mov     eax, r10d
0x180005c36  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180005c3e  cmp     edx, 61h ; 'a'
0x180005c41  ja      short loc_180005CB0
0x180005c43  jz      loc_180005CD0
0x180005c49  cmp     edx, 38h ; '8'
0x180005c4c  ja      short loc_180005C82
0x180005c4e  jz      short loc_180005C7A
0x180005c50  mov     ecx, edx
0x180005c52  sub     ecx, r12d
0x180005c55  jz      short loc_180005C7A
0x180005c57  sub     ecx, 1
0x180005c5a  jz      short loc_180005C7A
0x180005c5c  sub     ecx, 1
0x180005c5f  jz      short loc_180005C7A
0x180005c61  sub     ecx, 1
0x180005c64  jz      short loc_180005C7A
0x180005c66  sub     ecx, 1
0x180005c69  jz      short loc_180005C7A
0x180005c6b  sub     ecx, 1
0x180005c6e  jz      short loc_180005C7A
0x180005c70  sub     ecx, 1
0x180005c73  jz      short loc_180005C7A
0x180005c75  cmp     ecx, 1
0x180005c78  jnz     short loc_180005CCB
0x180005c7a  mov     r9d, edx
0x180005c7d  sub     r9d, r12d
0x180005c80  jmp     short loc_180005CD4
0x180005c82  mov     r9d, edx
0x180005c85  mov     ecx, edx
0x180005c87  sub     ecx, 39h ; '9'
0x180005c8a  jz      short loc_180005C7A
0x180005c8c  sub     ecx, 8
0x180005c8f  jz      short loc_180005CAA
0x180005c91  sub     ecx, 1
0x180005c94  jz      short loc_180005CAA
0x180005c96  sub     ecx, 1
0x180005c99  jz      short loc_180005CAA
0x180005c9b  sub     ecx, 1
0x180005c9e  jz      short loc_180005CAA
0x180005ca0  sub     ecx, 1
0x180005ca3  jz      short loc_180005CAA
0x180005ca5  cmp     ecx, 1
0x180005ca8  jnz     short loc_180005CCB
0x180005caa  add     r9d, 0FFFFFFC9h
0x180005cae  jmp     short loc_180005CD4
0x180005cb0  mov     ecx, edx
0x180005cb2  sub     ecx, 62h ; 'b'
0x180005cb5  jz      short loc_180005CD0
0x180005cb7  sub     ecx, 1
0x180005cba  jz      short loc_180005CD0
0x180005cbc  sub     ecx, 1
0x180005cbf  jz      short loc_180005CD0
0x180005cc1  sub     ecx, 1
0x180005cc4  jz      short loc_180005CD0
0x180005cc6  cmp     ecx, 1
0x180005cc9  jz      short loc_180005CD0
0x180005ccb  mov     r9d, ebx
0x180005cce  jmp     short loc_180005CD4
0x180005cd0  lea     r9d, [rdx-57h]
0x180005cd4  mov     r8d, r10d
0x180005cd7  shr     r8, 1
0x180005cda  mov     rdx, [rsp+22F8h+var_2268]
0x180005ce2  mov     eax, r10d
0x180005ce5  and     eax, 1
0x180005ce8  shl     eax, 2
0x180005ceb  mov     ecx, 4
0x180005cf0  sub     ecx, eax
0x180005cf2  shl     r9b, cl
0x180005cf5  or      [r8+rdx], r9b
0x180005cf9  inc     r10d
0x180005cfc  cmp     r10d, r14d
0x180005cff  jl      loc_180005C33
0x180005d05  mov     rax, [rsp+22F8h+var_2268]
0x180005d0d  mov     [rsp+22F8h+cbData], esi; cbData
0x180005d11  mov     [rsp+22F8h+lpData], rax; lpData
  ... truncated ...
```
