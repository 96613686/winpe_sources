# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800176cc`
- end: `0x180017c4c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18001a8b0`

## callees

- `0x180001e80`
- `0x1800028ac`
- `0x180016aa0`
- `0x180016b3c`
- `0x180016bd0`
- `0x180016e6c`
- `0x1800176cc`
- `0x180017c54`
- `0x180017f2c`
- `0x180018364`
- `0x180019970`
- `0x18001b5c8`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001795a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001795a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017889`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800178a5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180017889`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800178a5`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001790e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800179a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017b9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017bf6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18001790e`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800179a1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017b9f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180017bf6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017767`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180017767`

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
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

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
0x1800176cc  push    rbx
0x1800176ce  push    rsi
0x1800176cf  push    rdi
0x1800176d0  push    r12
0x1800176d2  push    r13
0x1800176d4  push    r14
0x1800176d6  push    r15
0x1800176d8  mov     eax, 21B0h
0x1800176dd  call    _alloca_probe
0x1800176e2  sub     rsp, rax
0x1800176e5  mov     rax, cs:__security_cookie
0x1800176ec  xor     rax, rsp
0x1800176ef  mov     [rsp+21E8h+var_48], rax
0x1800176f7  mov     r14, r8
0x1800176fa  mov     [rsp+21E8h+lpValueName], r8
0x1800176ff  mov     r12, rdx
0x180017702  mov     [rsp+21E8h+var_2198], rdx
0x180017707  mov     r15, rcx
0x18001770a  mov     [rsp+21E8h+var_21B0], rcx
0x18001770f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180017714  mov     [rsp+21E8h+var_2190], rcx
0x180017719  mov     [rsp+21E8h+var_2170], rdx
0x18001771e  mov     [rsp+21E8h+var_2188], r8
0x180017723  mov     [rsp+21E8h+var_2168], r9
0x18001772b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180017733  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180017738  xor     ebx, ebx
0x18001773a  test    eax, eax
0x18001773c  js      loc_180017C29
0x180017742  mov     edi, ebx
0x180017744  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001774b  cmp     edi, 4
0x18001774e  jnb     loc_180017C24
0x180017754  movsxd  rsi, edi
0x180017757  add     rsi, rsi
0x18001775a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18001775f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180017767  call    cs:__imp_lstrcmpiW
0x18001776d  test    eax, eax
0x18001776f  jz      short loc_180017775
0x180017771  inc     edi
0x180017773  jmp     short loc_18001774B
0x180017775  movzx   edi, word ptr [r13+rsi*8+8]
0x18001777b  mov     rcx, r15; this
0x18001777e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180017783  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18001778b  mov     rcx, r15; this
0x18001778e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180017793  test    eax, eax
0x180017795  js      loc_180017C29
0x18001779b  mov     r13d, 8
0x1800177a1  cmp     di, r13w
0x1800177a5  jz      loc_180017BB9
0x1800177ab  cmp     di, 11h
0x1800177af  jz      loc_1800179B8
0x1800177b5  cmp     di, 13h
0x1800177b9  jz      loc_18001793F
0x1800177bf  mov     eax, 4008h
0x1800177c4  cmp     di, ax
0x1800177c7  jnz     loc_180017C0B
0x1800177cd  lea     rcx, [rsp+21E8h+String1]
0x1800177d5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800177d9  mov     rax, rsi
0x1800177dc  inc     rax
0x1800177df  cmp     [rcx+rax*2], bx
0x1800177e3  jnz     short loc_1800177DC
0x1800177e5  add     eax, 2
0x1800177e8  mov     [rsp+21E8h+var_2158], rbx
0x1800177f0  movsxd  rcx, eax
0x1800177f3  mov     r15d, 2
0x1800177f9  mov     edx, r15d
0x1800177fc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180017801  cmp     rax, 100h
0x180017807  jbe     short loc_180017823
0x180017809  mov     rdx, rax
0x18001780c  lea     rcx, [rsp+21E8h+var_2158]
0x180017814  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180017819  mov     rdi, [rsp+21E8h+var_2158]
0x180017821  jmp     short loc_180017833
0x180017823  lea     rdi, [rsp+21E8h+var_2150]
0x18001782b  mov     [rsp+21E8h+var_2158], rdi
0x180017833  mov     r13, [rsp+21E8h+var_2198]
0x180017838  jmp     short loc_180017865
0x18001783a  xor     ebx, ebx
0x18001783c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180017840  lea     r15d, [rbx+2]
0x180017844  mov     rdi, [rsp+21E8h+var_2158]
0x18001784c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180017851  mov     rax, [rsp+21E8h+var_2190]
0x180017856  mov     [rsp+21E8h+var_21B0], rax
0x18001785b  mov     rax, [rsp+21E8h+var_2188]
0x180017860  mov     [rsp+21E8h+lpValueName], rax
0x180017865  test    rdi, rdi
0x180017868  jz      loc_180017923
0x18001786e  lea     r14, [rsp+21E8h+String1]
0x180017876  cmp     [rsp+21E8h+String1], bx
0x18001787e  jz      short loc_1800178BF
0x180017880  mov     r12d, 30h ; '0'
0x180017886  mov     rcx, r14; lpsz
0x180017889  call    cs:__imp_CharNextW
0x18001788f  movzx   ecx, word ptr [r14]
0x180017893  cmp     cx, 5Ch ; '\'
0x180017897  jnz     short loc_1800178B0
0x180017899  cmp     [rax], r12w
0x18001789d  jnz     short loc_1800178B0
0x18001789f  mov     [rdi], bx
0x1800178a2  mov     rcx, rax; lpsz
0x1800178a5  call    cs:__imp_CharNextW
0x1800178ab  mov     r14, rax
0x1800178ae  jmp     short loc_1800178B6
0x1800178b0  mov     [rdi], cx
0x1800178b3  add     r14, r15
0x1800178b6  add     rdi, r15
0x1800178b9  cmp     [r14], bx
0x1800178bd  jnz     short loc_180017886
0x1800178bf  mov     dword ptr [rdi], 0
0x1800178c5  mov     r8, [rsp+21E8h+var_2158]
0x1800178cd  test    r8, r8
0x1800178d0  jz      short loc_180017918
0x1800178d2  mov     r10d, ebx
0x1800178d5  mov     r9, r8
0x1800178d8  mov     rcx, rsi
0x1800178db  inc     rcx
0x1800178de  cmp     [r9+rcx*2], bx
0x1800178e3  jnz     short loc_1800178DB
0x1800178e5  inc     ecx
0x1800178e7  lea     r9, [r9+rcx*2]
0x1800178eb  lea     r10d, [r10+rcx*2]
0x1800178ef  cmp     ecx, 1
0x1800178f2  jnz     short loc_1800178D8
0x1800178f4  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800178f9  mov     [rsp+21E8h+lpData], r8; lpData
0x1800178fe  lea     r9d, [rcx+6]; dwType
0x180017902  xor     r8d, r8d; Reserved
0x180017905  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18001790a  mov     rcx, [r13+0]; hKey
0x18001790e  call    cs:__imp_RegSetValueExW
0x180017914  mov     edi, eax
0x180017916  jmp     short loc_180017928
0x180017918  mov     ecx, 80004005h; int
0x18001791d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180017923  mov     edi, 0Eh
0x180017928  lea     rcx, [rsp+21E8h+var_2158]
0x180017930  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180017935  mov     r15, [rsp+21E8h+var_21B0]
0x18001793a  jmp     loc_180017BFE
0x18001793f  mov     [rsp+21E8h+pulOut], ebx
0x180017943  mov     [rsp+21E8h+var_21B0], rbx
0x180017948  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18001794d  xor     r8d, r8d; dwFlags
0x180017950  xor     edx, edx; lcid
0x180017952  lea     rcx, [rsp+21E8h+String1]; strIn
0x18001795a  call    cs:__imp_VarUI4FromStr
0x180017960  mov     edi, eax
0x180017962  test    eax, eax
0x180017964  jns     short loc_180017977
0x180017966  lea     rcx, [rsp+21E8h+var_21B0]
0x18001796b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180017970  mov     eax, edi
0x180017972  jmp     loc_180017C29
0x180017977  mov     eax, [rsp+21E8h+pulOut]
0x18001797b  mov     dword ptr [rsp+21E8h+Data], eax
0x18001797f  mov     [rsp+21E8h+cbData], 4; cbData
0x180017987  lea     rax, [rsp+21E8h+Data]
0x18001798c  mov     [rsp+21E8h+lpData], rax; lpData
0x180017991  mov     r9d, 4; dwType
0x180017997  xor     r8d, r8d; Reserved
0x18001799a  mov     rdx, r14; lpValueName
0x18001799d  mov     rcx, [r12]; hKey
0x1800179a1  call    cs:__imp_RegSetValueExW
0x1800179a7  mov     edi, eax
0x1800179a9  lea     rcx, [rsp+21E8h+var_21B0]
0x1800179ae  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800179b3  jmp     loc_180017BFE
0x1800179b8  lea     rax, [rsp+21E8h+String1]
0x1800179c0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800179c4  inc     rsi
0x1800179c7  cmp     [rax+rsi*2], bx
0x1800179cb  jnz     short loc_1800179C4
0x1800179cd  mov     dword ptr [rsp+21E8h+Data], esi
0x1800179d1  test    sil, 1
0x1800179d5  jz      short loc_1800179E1
0x1800179d7  mov     eax, 80004005h
0x1800179dc  jmp     loc_180017C29
0x1800179e1  mov     eax, esi
0x1800179e3  cdq
0x1800179e4  mov     r15d, 2
0x1800179ea  idiv    r15d
0x1800179ed  movsxd  r14, eax
0x1800179f0  mov     [rsp+21E8h+var_2158], rbx
0x1800179f8  mov     rdi, r14
0x1800179fb  mov     [rsp+21E8h+var_2178], r14
0x180017a00  lea     edx, [r15-1]
0x180017a04  mov     rcx, r14
0x180017a07  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180017a0c  cmp     rax, 100h
0x180017a12  jbe     short loc_180017A2E
0x180017a14  mov     rdx, rax
0x180017a17  lea     rcx, [rsp+21E8h+var_2158]
0x180017a1f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180017a24  mov     rcx, [rsp+21E8h+var_2158]
0x180017a2c  jmp     short loc_180017A3E
0x180017a2e  lea     rcx, [rsp+21E8h+var_2150]
0x180017a36  mov     [rsp+21E8h+var_2158], rcx
0x180017a3e  mov     r15, [rsp+21E8h+var_2198]
0x180017a43  jmp     short loc_180017A78
0x180017a45  xor     ebx, ebx
0x180017a47  lea     r13d, [rbx+8]
0x180017a4b  mov     esi, dword ptr [rsp+21E8h+Data]
0x180017a4f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180017a57  mov     rdi, [rsp+21E8h+var_2178]
0x180017a5c  mov     rax, [rsp+21E8h+var_2190]
0x180017a61  mov     [rsp+21E8h+var_21B0], rax
0x180017a66  mov     r15, [rsp+21E8h+var_2170]
0x180017a6b  mov     rax, [rsp+21E8h+var_2188]
0x180017a70  mov     [rsp+21E8h+lpValueName], rax
0x180017a75  mov     r14d, edi
0x180017a78  test    rcx, rcx
0x180017a7b  jnz     short loc_180017A8F
0x180017a7d  lea     rcx, [rsp+21E8h+var_2158]
0x180017a85  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180017a8a  jmp     loc_1800179D7
0x180017a8f  mov     r8, rdi; Size
0x180017a92  xor     edx, edx; Val
0x180017a94  call    memset_0
0x180017a99  mov     r10d, ebx
0x180017a9c  test    esi, esi
0x180017a9e  jle     loc_180017B7C
0x180017aa4  mov     r12d, 30h ; '0'
0x180017aaa  mov     eax, r10d
0x180017aad  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180017ab5  cmp     edx, 61h ; 'a'
0x180017ab8  ja      short loc_180017B27
0x180017aba  jz      loc_180017B47
0x180017ac0  cmp     edx, 38h ; '8'
0x180017ac3  ja      short loc_180017AF9
0x180017ac5  jz      short loc_180017AF1
0x180017ac7  mov     ecx, edx
0x180017ac9  sub     ecx, r12d
0x180017acc  jz      short loc_180017AF1
0x180017ace  sub     ecx, 1
0x180017ad1  jz      short loc_180017AF1
0x180017ad3  sub     ecx, 1
0x180017ad6  jz      short loc_180017AF1
0x180017ad8  sub     ecx, 1
0x180017adb  jz      short loc_180017AF1
0x180017add  sub     ecx, 1
0x180017ae0  jz      short loc_180017AF1
0x180017ae2  sub     ecx, 1
0x180017ae5  jz      short loc_180017AF1
0x180017ae7  sub     ecx, 1
0x180017aea  jz      short loc_180017AF1
0x180017aec  cmp     ecx, 1
0x180017aef  jnz     short loc_180017B42
0x180017af1  mov     r9d, edx
0x180017af4  sub     r9d, r12d
0x180017af7  jmp     short loc_180017B4B
0x180017af9  mov     r9d, edx
0x180017afc  mov     ecx, edx
0x180017afe  sub     ecx, 39h ; '9'
0x180017b01  jz      short loc_180017AF1
0x180017b03  sub     ecx, r13d
0x180017b06  jz      short loc_180017B21
0x180017b08  sub     ecx, 1
0x180017b0b  jz      short loc_180017B21
0x180017b0d  sub     ecx, 1
0x180017b10  jz      short loc_180017B21
0x180017b12  sub     ecx, 1
0x180017b15  jz      short loc_180017B21
0x180017b17  sub     ecx, 1
0x180017b1a  jz      short loc_180017B21
0x180017b1c  cmp     ecx, 1
0x180017b1f  jnz     short loc_180017B42
0x180017b21  add     r9d, 0FFFFFFC9h
0x180017b25  jmp     short loc_180017B4B
0x180017b27  mov     ecx, edx
0x180017b29  sub     ecx, 62h ; 'b'
0x180017b2c  jz      short loc_180017B47
0x180017b2e  sub     ecx, 1
0x180017b31  jz      short loc_180017B47
0x180017b33  sub     ecx, 1
0x180017b36  jz      short loc_180017B47
0x180017b38  sub     ecx, 1
0x180017b3b  jz      short loc_180017B47
0x180017b3d  cmp     ecx, 1
0x180017b40  jz      short loc_180017B47
0x180017b42  mov     r9d, ebx
0x180017b45  jmp     short loc_180017B4B
0x180017b47  lea     r9d, [rdx-57h]
0x180017b4b  mov     r8d, r10d
0x180017b4e  shr     r8, 1
0x180017b51  mov     rdx, [rsp+21E8h+var_2158]
0x180017b59  mov     eax, r10d
0x180017b5c  and     eax, 1
0x180017b5f  shl     eax, 2
0x180017b62  mov     ecx, 4
0x180017b67  sub     ecx, eax
0x180017b69  shl     r9b, cl
0x180017b6c  or      [r8+rdx], r9b
0x180017b70  inc     r10d
  ... truncated ...
```
