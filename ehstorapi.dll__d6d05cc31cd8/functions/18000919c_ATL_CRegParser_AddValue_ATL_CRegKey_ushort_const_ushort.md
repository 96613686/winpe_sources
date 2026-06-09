# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000919c`
- end: `0x18000971c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000ae30`

## callees

- `0x180002338`
- `0x180008bb8`
- `0x180008bf4`
- `0x180008cd0`
- `0x18000919c`
- `0x180009724`
- `0x18000996c`
- `0x18000a570`
- `0x18000b5b8`
- `0x18000c4c2`
- `0x18000c4f0`
- `0x18000c5b0`

## import_xrefs

- `USER32!CharNextW` at `0x180009359`
- `USER32!CharNextW` at `0x180009375`
- `USER32!CharNextW` at `0x180009359`
- `USER32!CharNextW` at `0x180009375`
- `ADVAPI32!RegSetValueExW` at `0x1800093de`
- `ADVAPI32!RegSetValueExW` at `0x180009471`
- `ADVAPI32!RegSetValueExW` at `0x18000966f`
- `ADVAPI32!RegSetValueExW` at `0x1800096c6`
- `ADVAPI32!RegSetValueExW` at `0x1800093de`
- `ADVAPI32!RegSetValueExW` at `0x180009471`
- `ADVAPI32!RegSetValueExW` at `0x18000966f`
- `ADVAPI32!RegSetValueExW` at `0x1800096c6`
- `KERNEL32!lstrcmpiW` at `0x180009237`
- `KERNEL32!lstrcmpiW` at `0x180009237`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000942a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000942a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v6; // r15
  __int64 result; // rax
  unsigned int v8; // ebx
  unsigned int i; // edi
  __int16 v10; // di
  __int64 v11; // rax
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  HKEY *v14; // r13
  WCHAR *j; // r14
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // edi
  HRESULT v22; // edi
  __int64 v23; // rsi
  DWORD v24; // r14d
  size_t v25; // rdi
  unsigned __int64 v26; // rax
  BYTE *v27; // rcx
  HKEY *v28; // r15
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21B0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21A8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-21A0h]
  HKEY *v38; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v39; // [rsp+58h] [rbp-2190h]
  const WCHAR *v40; // [rsp+60h] [rbp-2188h]
  size_t v41; // [rsp+70h] [rbp-2178h]
  HKEY *v42; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v43; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  WCHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v38 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v39 = this;
  v42 = a2;
  v40 = a3;
  v43 = a4;
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
      v21 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      goto LABEL_80;
    case 17:
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      *(_DWORD *)Data = v23;
      if ( (v23 & 1) != 0 )
        return 2147500037LL;
      v24 = (int)v23 / 2;
      lpData = 0;
      v25 = (int)v23 / 2;
      v41 = v25;
      try
      {
        v26 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v26 <= 0x100 )
        {
          v27 = v45;
          lpData = v45;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
          v27 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v23) = *(_DWORD *)Data;
        v27 = lpData;
        v25 = v41;
        v35 = v39;
        v28 = v42;
        lpValueName = v40;
        v24 = v41;
        goto LABEL_47;
      }
      v28 = v38;
LABEL_47:
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_34;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_74:
            v31 = v30 - 87;
            goto LABEL_75;
          }
LABEL_73:
          v31 = 0;
          goto LABEL_75;
        }
        if ( v30 == 97 )
          goto LABEL_74;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_61;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_73;
        v31 = v30 - 55;
LABEL_75:
        lpData[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v23 )
          goto LABEL_76;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_73;
LABEL_61:
      v31 = v30 - 48;
      goto LABEL_75;
    case 19:
      pulOut = 0;
      v35 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
      return (unsigned int)v22;
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
          v13 = v45;
          lpData = v45;
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
        v14 = *(HKEY **)Data;
        v35 = v39;
        lpValueName = v40;
        goto LABEL_18;
      }
      v14 = v38;
LABEL_18:
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v16 = CharNextW(j);
          if ( *j == 92 && *v16 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v16);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v18 = lpData;
        do
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)&v18[2 * v19] );
          v20 = (unsigned int)(v19 + 1);
          v18 += 2 * v20;
          cbData += 2 * v20;
        }
        while ( (_DWORD)v20 != 1 );
        v21 = RegSetValueExW(*v14, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v35;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v43);
        if ( Token < 0 )
          return (unsigned int)Token;
        return v8;
      }
    default:
      goto LABEL_82;
  }
}

```

## disassembly

```asm
0x18000919c  push    rbx
0x18000919e  push    rsi
0x18000919f  push    rdi
0x1800091a0  push    r12
0x1800091a2  push    r13
0x1800091a4  push    r14
0x1800091a6  push    r15
0x1800091a8  mov     eax, 21B0h
0x1800091ad  call    _alloca_probe
0x1800091b2  sub     rsp, rax
0x1800091b5  mov     rax, cs:__security_cookie
0x1800091bc  xor     rax, rsp
0x1800091bf  mov     [rsp+21E8h+var_48], rax
0x1800091c7  mov     r14, r8
0x1800091ca  mov     [rsp+21E8h+lpValueName], r8
0x1800091cf  mov     r12, rdx
0x1800091d2  mov     [rsp+21E8h+var_2198], rdx
0x1800091d7  mov     r15, rcx
0x1800091da  mov     [rsp+21E8h+var_21B0], rcx
0x1800091df  mov     qword ptr [rsp+21E8h+Data], rdx
0x1800091e4  mov     [rsp+21E8h+var_2190], rcx
0x1800091e9  mov     [rsp+21E8h+var_2170], rdx
0x1800091ee  mov     [rsp+21E8h+var_2188], r8
0x1800091f3  mov     [rsp+21E8h+var_2168], r9
0x1800091fb  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180009203  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009208  xor     ebx, ebx
0x18000920a  test    eax, eax
0x18000920c  js      loc_1800096F9
0x180009212  mov     edi, ebx
0x180009214  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000921b  cmp     edi, 4
0x18000921e  jnb     loc_1800096F4
0x180009224  movsxd  rsi, edi
0x180009227  add     rsi, rsi
0x18000922a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000922f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180009237  call    cs:__imp_lstrcmpiW
0x18000923d  test    eax, eax
0x18000923f  jz      short loc_180009245
0x180009241  inc     edi
0x180009243  jmp     short loc_18000921B
0x180009245  movzx   edi, word ptr [r13+rsi*8+8]
0x18000924b  mov     rcx, r15; this
0x18000924e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180009253  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18000925b  mov     rcx, r15; this
0x18000925e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180009263  test    eax, eax
0x180009265  js      loc_1800096F9
0x18000926b  mov     r13d, 8
0x180009271  cmp     di, r13w
0x180009275  jz      loc_180009689
0x18000927b  cmp     di, 11h
0x18000927f  jz      loc_180009488
0x180009285  cmp     di, 13h
0x180009289  jz      loc_18000940F
0x18000928f  mov     eax, 4008h
0x180009294  cmp     di, ax
0x180009297  jnz     loc_1800096DB
0x18000929d  lea     rcx, [rsp+21E8h+String1]
0x1800092a5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800092a9  mov     rax, rsi
0x1800092ac  inc     rax
0x1800092af  cmp     [rcx+rax*2], bx
0x1800092b3  jnz     short loc_1800092AC
0x1800092b5  add     eax, 2
0x1800092b8  mov     [rsp+21E8h+var_2158], rbx
0x1800092c0  movsxd  rcx, eax
0x1800092c3  mov     r15d, 2
0x1800092c9  mov     edx, r15d
0x1800092cc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800092d1  cmp     rax, 100h
0x1800092d7  jbe     short loc_1800092F3
0x1800092d9  mov     rdx, rax
0x1800092dc  lea     rcx, [rsp+21E8h+var_2158]
0x1800092e4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800092e9  mov     rdi, [rsp+21E8h+var_2158]
0x1800092f1  jmp     short loc_180009303
0x1800092f3  lea     rdi, [rsp+21E8h+var_2150]
0x1800092fb  mov     [rsp+21E8h+var_2158], rdi
0x180009303  mov     r13, [rsp+21E8h+var_2198]
0x180009308  jmp     short loc_180009335
0x18000930a  xor     ebx, ebx
0x18000930c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009310  lea     r15d, [rbx+2]
0x180009314  mov     rdi, [rsp+21E8h+var_2158]
0x18000931c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180009321  mov     rax, [rsp+21E8h+var_2190]
0x180009326  mov     [rsp+21E8h+var_21B0], rax
0x18000932b  mov     rax, [rsp+21E8h+var_2188]
0x180009330  mov     [rsp+21E8h+lpValueName], rax
0x180009335  test    rdi, rdi
0x180009338  jz      loc_1800093F3
0x18000933e  lea     r14, [rsp+21E8h+String1]
0x180009346  cmp     [rsp+21E8h+String1], bx
0x18000934e  jz      short loc_18000938F
0x180009350  mov     r12d, 30h ; '0'
0x180009356  mov     rcx, r14; lpsz
0x180009359  call    cs:__imp_CharNextW
0x18000935f  movzx   ecx, word ptr [r14]
0x180009363  cmp     cx, 5Ch ; '\'
0x180009367  jnz     short loc_180009380
0x180009369  cmp     [rax], r12w
0x18000936d  jnz     short loc_180009380
0x18000936f  mov     [rdi], bx
0x180009372  mov     rcx, rax; lpsz
0x180009375  call    cs:__imp_CharNextW
0x18000937b  mov     r14, rax
0x18000937e  jmp     short loc_180009386
0x180009380  mov     [rdi], cx
0x180009383  add     r14, r15
0x180009386  add     rdi, r15
0x180009389  cmp     [r14], bx
0x18000938d  jnz     short loc_180009356
0x18000938f  mov     dword ptr [rdi], 0
0x180009395  mov     r8, [rsp+21E8h+var_2158]
0x18000939d  test    r8, r8
0x1800093a0  jz      short loc_1800093E8
0x1800093a2  mov     r10d, ebx
0x1800093a5  mov     r9, r8
0x1800093a8  mov     rcx, rsi
0x1800093ab  inc     rcx
0x1800093ae  cmp     [r9+rcx*2], bx
0x1800093b3  jnz     short loc_1800093AB
0x1800093b5  inc     ecx
0x1800093b7  lea     r9, [r9+rcx*2]
0x1800093bb  lea     r10d, [r10+rcx*2]
0x1800093bf  cmp     ecx, 1
0x1800093c2  jnz     short loc_1800093A8
0x1800093c4  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800093c9  mov     [rsp+21E8h+lpData], r8; lpData
0x1800093ce  lea     r9d, [rcx+6]; dwType
0x1800093d2  xor     r8d, r8d; Reserved
0x1800093d5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x1800093da  mov     rcx, [r13+0]; hKey
0x1800093de  call    cs:__imp_RegSetValueExW
0x1800093e4  mov     edi, eax
0x1800093e6  jmp     short loc_1800093F8
0x1800093e8  mov     ecx, 80004005h; int
0x1800093ed  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800093f3  mov     edi, 0Eh
0x1800093f8  lea     rcx, [rsp+21E8h+var_2158]
0x180009400  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180009405  mov     r15, [rsp+21E8h+var_21B0]
0x18000940a  jmp     loc_1800096CE
0x18000940f  mov     [rsp+21E8h+pulOut], ebx
0x180009413  mov     [rsp+21E8h+var_21B0], rbx
0x180009418  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000941d  xor     r8d, r8d; dwFlags
0x180009420  xor     edx, edx; lcid
0x180009422  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000942a  call    cs:__imp_VarUI4FromStr
0x180009430  mov     edi, eax
0x180009432  test    eax, eax
0x180009434  jns     short loc_180009447
0x180009436  lea     rcx, [rsp+21E8h+var_21B0]
0x18000943b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009440  mov     eax, edi
0x180009442  jmp     loc_1800096F9
0x180009447  mov     eax, [rsp+21E8h+pulOut]
0x18000944b  mov     dword ptr [rsp+21E8h+Data], eax
0x18000944f  mov     [rsp+21E8h+cbData], 4; cbData
0x180009457  lea     rax, [rsp+21E8h+Data]
0x18000945c  mov     [rsp+21E8h+lpData], rax; lpData
0x180009461  mov     r9d, 4; dwType
0x180009467  xor     r8d, r8d; Reserved
0x18000946a  mov     rdx, r14; lpValueName
0x18000946d  mov     rcx, [r12]; hKey
0x180009471  call    cs:__imp_RegSetValueExW
0x180009477  mov     edi, eax
0x180009479  lea     rcx, [rsp+21E8h+var_21B0]
0x18000947e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180009483  jmp     loc_1800096CE
0x180009488  lea     rax, [rsp+21E8h+String1]
0x180009490  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009494  inc     rsi
0x180009497  cmp     [rax+rsi*2], bx
0x18000949b  jnz     short loc_180009494
0x18000949d  mov     dword ptr [rsp+21E8h+Data], esi
0x1800094a1  test    sil, 1
0x1800094a5  jz      short loc_1800094B1
0x1800094a7  mov     eax, 80004005h
0x1800094ac  jmp     loc_1800096F9
0x1800094b1  mov     eax, esi
0x1800094b3  cdq
0x1800094b4  mov     r15d, 2
0x1800094ba  idiv    r15d
0x1800094bd  movsxd  r14, eax
0x1800094c0  mov     [rsp+21E8h+var_2158], rbx
0x1800094c8  mov     rdi, r14
0x1800094cb  mov     [rsp+21E8h+var_2178], r14
0x1800094d0  lea     edx, [r15-1]
0x1800094d4  mov     rcx, r14
0x1800094d7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800094dc  cmp     rax, 100h
0x1800094e2  jbe     short loc_1800094FE
0x1800094e4  mov     rdx, rax
0x1800094e7  lea     rcx, [rsp+21E8h+var_2158]
0x1800094ef  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800094f4  mov     rcx, [rsp+21E8h+var_2158]
0x1800094fc  jmp     short loc_18000950E
0x1800094fe  lea     rcx, [rsp+21E8h+var_2150]
0x180009506  mov     [rsp+21E8h+var_2158], rcx
0x18000950e  mov     r15, [rsp+21E8h+var_2198]
0x180009513  jmp     short loc_180009548
0x180009515  xor     ebx, ebx
0x180009517  lea     r13d, [rbx+8]
0x18000951b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18000951f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180009527  mov     rdi, [rsp+21E8h+var_2178]
0x18000952c  mov     rax, [rsp+21E8h+var_2190]
0x180009531  mov     [rsp+21E8h+var_21B0], rax
0x180009536  mov     r15, [rsp+21E8h+var_2170]
0x18000953b  mov     rax, [rsp+21E8h+var_2188]
0x180009540  mov     [rsp+21E8h+lpValueName], rax
0x180009545  mov     r14d, edi
0x180009548  test    rcx, rcx
0x18000954b  jnz     short loc_18000955F
0x18000954d  lea     rcx, [rsp+21E8h+var_2158]
0x180009555  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000955a  jmp     loc_1800094A7
0x18000955f  mov     r8, rdi; Size
0x180009562  xor     edx, edx; Val
0x180009564  call    memset_0
0x180009569  mov     r10d, ebx
0x18000956c  test    esi, esi
0x18000956e  jle     loc_18000964C
0x180009574  mov     r12d, 30h ; '0'
0x18000957a  mov     eax, r10d
0x18000957d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180009585  cmp     edx, 61h ; 'a'
0x180009588  ja      short loc_1800095F7
0x18000958a  jz      loc_180009617
0x180009590  cmp     edx, 38h ; '8'
0x180009593  ja      short loc_1800095C9
0x180009595  jz      short loc_1800095C1
0x180009597  mov     ecx, edx
0x180009599  sub     ecx, r12d
0x18000959c  jz      short loc_1800095C1
0x18000959e  sub     ecx, 1
0x1800095a1  jz      short loc_1800095C1
0x1800095a3  sub     ecx, 1
0x1800095a6  jz      short loc_1800095C1
0x1800095a8  sub     ecx, 1
0x1800095ab  jz      short loc_1800095C1
0x1800095ad  sub     ecx, 1
0x1800095b0  jz      short loc_1800095C1
0x1800095b2  sub     ecx, 1
0x1800095b5  jz      short loc_1800095C1
0x1800095b7  sub     ecx, 1
0x1800095ba  jz      short loc_1800095C1
0x1800095bc  cmp     ecx, 1
0x1800095bf  jnz     short loc_180009612
0x1800095c1  mov     r9d, edx
0x1800095c4  sub     r9d, r12d
0x1800095c7  jmp     short loc_18000961B
0x1800095c9  mov     r9d, edx
0x1800095cc  mov     ecx, edx
0x1800095ce  sub     ecx, 39h ; '9'
0x1800095d1  jz      short loc_1800095C1
0x1800095d3  sub     ecx, r13d
0x1800095d6  jz      short loc_1800095F1
0x1800095d8  sub     ecx, 1
0x1800095db  jz      short loc_1800095F1
0x1800095dd  sub     ecx, 1
0x1800095e0  jz      short loc_1800095F1
0x1800095e2  sub     ecx, 1
0x1800095e5  jz      short loc_1800095F1
0x1800095e7  sub     ecx, 1
0x1800095ea  jz      short loc_1800095F1
0x1800095ec  cmp     ecx, 1
0x1800095ef  jnz     short loc_180009612
0x1800095f1  add     r9d, 0FFFFFFC9h
0x1800095f5  jmp     short loc_18000961B
0x1800095f7  mov     ecx, edx
0x1800095f9  sub     ecx, 62h ; 'b'
0x1800095fc  jz      short loc_180009617
0x1800095fe  sub     ecx, 1
0x180009601  jz      short loc_180009617
0x180009603  sub     ecx, 1
0x180009606  jz      short loc_180009617
0x180009608  sub     ecx, 1
0x18000960b  jz      short loc_180009617
0x18000960d  cmp     ecx, 1
0x180009610  jz      short loc_180009617
0x180009612  mov     r9d, ebx
0x180009615  jmp     short loc_18000961B
0x180009617  lea     r9d, [rdx-57h]
0x18000961b  mov     r8d, r10d
0x18000961e  shr     r8, 1
0x180009621  mov     rdx, [rsp+21E8h+var_2158]
0x180009629  mov     eax, r10d
0x18000962c  and     eax, 1
0x18000962f  shl     eax, 2
0x180009632  mov     ecx, 4
0x180009637  sub     ecx, eax
0x180009639  shl     r9b, cl
0x18000963c  or      [r8+rdx], r9b
0x180009640  inc     r10d
  ... truncated ...
```
