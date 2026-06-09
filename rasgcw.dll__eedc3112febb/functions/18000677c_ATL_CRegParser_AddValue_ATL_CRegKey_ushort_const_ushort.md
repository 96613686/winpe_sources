# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000677c`
- end: `0x180006cfc`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000e1a8`

## callees

- `0x180003c80`
- `0x180004078`
- `0x180005060`
- `0x18000677c`
- `0x180006d04`
- `0x180006f84`
- `0x1800076ec`
- `0x18000c5c0`
- `0x18000f0e0`
- `0x18002f382`
- `0x18002f3b0`
- `0x18002f470`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800069be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006c4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006ca6`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800069be`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006a51`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006c4f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180006ca6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006939`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006955`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006939`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180006955`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006817`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180006817`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006a0a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180006a0a`

## pseudocode

```c
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
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
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
0x18000677c  push    rbx
0x18000677e  push    rsi
0x18000677f  push    rdi
0x180006780  push    r12
0x180006782  push    r13
0x180006784  push    r14
0x180006786  push    r15
0x180006788  mov     eax, 21B0h
0x18000678d  call    _alloca_probe
0x180006792  sub     rsp, rax
0x180006795  mov     rax, cs:__security_cookie
0x18000679c  xor     rax, rsp
0x18000679f  mov     [rsp+21E8h+var_48], rax
0x1800067a7  mov     r14, r8
0x1800067aa  mov     [rsp+21E8h+lpValueName], r8
0x1800067af  mov     r12, rdx
0x1800067b2  mov     [rsp+21E8h+var_2198], rdx
0x1800067b7  mov     r15, rcx
0x1800067ba  mov     [rsp+21E8h+var_21B0], rcx
0x1800067bf  mov     qword ptr [rsp+21E8h+Data], rdx
0x1800067c4  mov     [rsp+21E8h+var_2190], rcx
0x1800067c9  mov     [rsp+21E8h+var_2170], rdx
0x1800067ce  mov     [rsp+21E8h+var_2188], r8
0x1800067d3  mov     [rsp+21E8h+var_2168], r9
0x1800067db  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x1800067e3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800067e8  xor     ebx, ebx
0x1800067ea  test    eax, eax
0x1800067ec  js      loc_180006CD9
0x1800067f2  mov     edi, ebx
0x1800067f4  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800067fb  cmp     edi, 4
0x1800067fe  jnb     loc_180006CD4
0x180006804  movsxd  rsi, edi
0x180006807  add     rsi, rsi
0x18000680a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000680f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180006817  call    cs:__imp_lstrcmpiW
0x18000681d  test    eax, eax
0x18000681f  jz      short loc_180006825
0x180006821  inc     edi
0x180006823  jmp     short loc_1800067FB
0x180006825  movzx   edi, word ptr [r13+rsi*8+8]
0x18000682b  mov     rcx, r15; this
0x18000682e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180006833  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18000683b  mov     rcx, r15; this
0x18000683e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180006843  test    eax, eax
0x180006845  js      loc_180006CD9
0x18000684b  mov     r13d, 8
0x180006851  cmp     di, r13w
0x180006855  jz      loc_180006C69
0x18000685b  cmp     di, 11h
0x18000685f  jz      loc_180006A68
0x180006865  cmp     di, 13h
0x180006869  jz      loc_1800069EF
0x18000686f  mov     eax, 4008h
0x180006874  cmp     di, ax
0x180006877  jnz     loc_180006CBB
0x18000687d  lea     rcx, [rsp+21E8h+String1]
0x180006885  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006889  mov     rax, rsi
0x18000688c  inc     rax
0x18000688f  cmp     [rcx+rax*2], bx
0x180006893  jnz     short loc_18000688C
0x180006895  add     eax, 2
0x180006898  mov     [rsp+21E8h+var_2158], rbx
0x1800068a0  movsxd  rcx, eax
0x1800068a3  mov     r15d, 2
0x1800068a9  mov     edx, r15d
0x1800068ac  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800068b1  cmp     rax, 100h
0x1800068b7  jbe     short loc_1800068D3
0x1800068b9  mov     rdx, rax
0x1800068bc  lea     rcx, [rsp+21E8h+var_2158]
0x1800068c4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800068c9  mov     rdi, [rsp+21E8h+var_2158]
0x1800068d1  jmp     short loc_1800068E3
0x1800068d3  lea     rdi, [rsp+21E8h+var_2150]
0x1800068db  mov     [rsp+21E8h+var_2158], rdi
0x1800068e3  mov     r13, [rsp+21E8h+var_2198]
0x1800068e8  jmp     short loc_180006915
0x1800068ea  xor     ebx, ebx
0x1800068ec  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800068f0  lea     r15d, [rbx+2]
0x1800068f4  mov     rdi, [rsp+21E8h+var_2158]
0x1800068fc  mov     r13, qword ptr [rsp+21E8h+Data]
0x180006901  mov     rax, [rsp+21E8h+var_2190]
0x180006906  mov     [rsp+21E8h+var_21B0], rax
0x18000690b  mov     rax, [rsp+21E8h+var_2188]
0x180006910  mov     [rsp+21E8h+lpValueName], rax
0x180006915  test    rdi, rdi
0x180006918  jz      loc_1800069D3
0x18000691e  lea     r14, [rsp+21E8h+String1]
0x180006926  cmp     [rsp+21E8h+String1], bx
0x18000692e  jz      short loc_18000696F
0x180006930  mov     r12d, 30h ; '0'
0x180006936  mov     rcx, r14; lpsz
0x180006939  call    cs:__imp_CharNextW
0x18000693f  movzx   ecx, word ptr [r14]
0x180006943  cmp     cx, 5Ch ; '\'
0x180006947  jnz     short loc_180006960
0x180006949  cmp     [rax], r12w
0x18000694d  jnz     short loc_180006960
0x18000694f  mov     [rdi], bx
0x180006952  mov     rcx, rax; lpsz
0x180006955  call    cs:__imp_CharNextW
0x18000695b  mov     r14, rax
0x18000695e  jmp     short loc_180006966
0x180006960  mov     [rdi], cx
0x180006963  add     r14, r15
0x180006966  add     rdi, r15
0x180006969  cmp     [r14], bx
0x18000696d  jnz     short loc_180006936
0x18000696f  mov     dword ptr [rdi], 0
0x180006975  mov     r8, [rsp+21E8h+var_2158]
0x18000697d  test    r8, r8
0x180006980  jz      short loc_1800069C8
0x180006982  mov     r10d, ebx
0x180006985  mov     r9, r8
0x180006988  mov     rcx, rsi
0x18000698b  inc     rcx
0x18000698e  cmp     [r9+rcx*2], bx
0x180006993  jnz     short loc_18000698B
0x180006995  inc     ecx
0x180006997  lea     r9, [r9+rcx*2]
0x18000699b  lea     r10d, [r10+rcx*2]
0x18000699f  cmp     ecx, 1
0x1800069a2  jnz     short loc_180006988
0x1800069a4  mov     [rsp+21E8h+cbData], r10d; cbData
0x1800069a9  mov     [rsp+21E8h+lpData], r8; lpData
0x1800069ae  lea     r9d, [rcx+6]; dwType
0x1800069b2  xor     r8d, r8d; Reserved
0x1800069b5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x1800069ba  mov     rcx, [r13+0]; hKey
0x1800069be  call    cs:__imp_RegSetValueExW
0x1800069c4  mov     edi, eax
0x1800069c6  jmp     short loc_1800069D8
0x1800069c8  mov     ecx, 80004005h; int
0x1800069cd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800069d3  mov     edi, 0Eh
0x1800069d8  lea     rcx, [rsp+21E8h+var_2158]
0x1800069e0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800069e5  mov     r15, [rsp+21E8h+var_21B0]
0x1800069ea  jmp     loc_180006CAE
0x1800069ef  mov     [rsp+21E8h+pulOut], ebx
0x1800069f3  mov     [rsp+21E8h+var_21B0], rbx
0x1800069f8  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x1800069fd  xor     r8d, r8d; dwFlags
0x180006a00  xor     edx, edx; lcid
0x180006a02  lea     rcx, [rsp+21E8h+String1]; strIn
0x180006a0a  call    cs:__imp_VarUI4FromStr
0x180006a10  mov     edi, eax
0x180006a12  test    eax, eax
0x180006a14  jns     short loc_180006A27
0x180006a16  lea     rcx, [rsp+21E8h+var_21B0]
0x180006a1b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006a20  mov     eax, edi
0x180006a22  jmp     loc_180006CD9
0x180006a27  mov     eax, [rsp+21E8h+pulOut]
0x180006a2b  mov     dword ptr [rsp+21E8h+Data], eax
0x180006a2f  mov     [rsp+21E8h+cbData], 4; cbData
0x180006a37  lea     rax, [rsp+21E8h+Data]
0x180006a3c  mov     [rsp+21E8h+lpData], rax; lpData
0x180006a41  mov     r9d, 4; dwType
0x180006a47  xor     r8d, r8d; Reserved
0x180006a4a  mov     rdx, r14; lpValueName
0x180006a4d  mov     rcx, [r12]; hKey
0x180006a51  call    cs:__imp_RegSetValueExW
0x180006a57  mov     edi, eax
0x180006a59  lea     rcx, [rsp+21E8h+var_21B0]
0x180006a5e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180006a63  jmp     loc_180006CAE
0x180006a68  lea     rax, [rsp+21E8h+String1]
0x180006a70  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180006a74  inc     rsi
0x180006a77  cmp     [rax+rsi*2], bx
0x180006a7b  jnz     short loc_180006A74
0x180006a7d  mov     dword ptr [rsp+21E8h+Data], esi
0x180006a81  test    sil, 1
0x180006a85  jz      short loc_180006A91
0x180006a87  mov     eax, 80004005h
0x180006a8c  jmp     loc_180006CD9
0x180006a91  mov     eax, esi
0x180006a93  cdq
0x180006a94  mov     r15d, 2
0x180006a9a  idiv    r15d
0x180006a9d  movsxd  r14, eax
0x180006aa0  mov     [rsp+21E8h+var_2158], rbx
0x180006aa8  mov     rdi, r14
0x180006aab  mov     [rsp+21E8h+var_2178], r14
0x180006ab0  lea     edx, [r15-1]
0x180006ab4  mov     rcx, r14
0x180006ab7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180006abc  cmp     rax, 100h
0x180006ac2  jbe     short loc_180006ADE
0x180006ac4  mov     rdx, rax
0x180006ac7  lea     rcx, [rsp+21E8h+var_2158]
0x180006acf  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180006ad4  mov     rcx, [rsp+21E8h+var_2158]
0x180006adc  jmp     short loc_180006AEE
0x180006ade  lea     rcx, [rsp+21E8h+var_2150]
0x180006ae6  mov     [rsp+21E8h+var_2158], rcx
0x180006aee  mov     r15, [rsp+21E8h+var_2198]
0x180006af3  jmp     short loc_180006B28
0x180006af5  xor     ebx, ebx
0x180006af7  lea     r13d, [rbx+8]
0x180006afb  mov     esi, dword ptr [rsp+21E8h+Data]
0x180006aff  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180006b07  mov     rdi, [rsp+21E8h+var_2178]
0x180006b0c  mov     rax, [rsp+21E8h+var_2190]
0x180006b11  mov     [rsp+21E8h+var_21B0], rax
0x180006b16  mov     r15, [rsp+21E8h+var_2170]
0x180006b1b  mov     rax, [rsp+21E8h+var_2188]
0x180006b20  mov     [rsp+21E8h+lpValueName], rax
0x180006b25  mov     r14d, edi
0x180006b28  test    rcx, rcx
0x180006b2b  jnz     short loc_180006B3F
0x180006b2d  lea     rcx, [rsp+21E8h+var_2158]
0x180006b35  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180006b3a  jmp     loc_180006A87
0x180006b3f  mov     r8, rdi; Size
0x180006b42  xor     edx, edx; Val
0x180006b44  call    memset_0
0x180006b49  mov     r10d, ebx
0x180006b4c  test    esi, esi
0x180006b4e  jle     loc_180006C2C
0x180006b54  mov     r12d, 30h ; '0'
0x180006b5a  mov     eax, r10d
0x180006b5d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180006b65  cmp     edx, 61h ; 'a'
0x180006b68  ja      short loc_180006BD7
0x180006b6a  jz      loc_180006BF7
0x180006b70  cmp     edx, 38h ; '8'
0x180006b73  ja      short loc_180006BA9
0x180006b75  jz      short loc_180006BA1
0x180006b77  mov     ecx, edx
0x180006b79  sub     ecx, r12d
0x180006b7c  jz      short loc_180006BA1
0x180006b7e  sub     ecx, 1
0x180006b81  jz      short loc_180006BA1
0x180006b83  sub     ecx, 1
0x180006b86  jz      short loc_180006BA1
0x180006b88  sub     ecx, 1
0x180006b8b  jz      short loc_180006BA1
0x180006b8d  sub     ecx, 1
0x180006b90  jz      short loc_180006BA1
0x180006b92  sub     ecx, 1
0x180006b95  jz      short loc_180006BA1
0x180006b97  sub     ecx, 1
0x180006b9a  jz      short loc_180006BA1
0x180006b9c  cmp     ecx, 1
0x180006b9f  jnz     short loc_180006BF2
0x180006ba1  mov     r9d, edx
0x180006ba4  sub     r9d, r12d
0x180006ba7  jmp     short loc_180006BFB
0x180006ba9  mov     r9d, edx
0x180006bac  mov     ecx, edx
0x180006bae  sub     ecx, 39h ; '9'
0x180006bb1  jz      short loc_180006BA1
0x180006bb3  sub     ecx, r13d
0x180006bb6  jz      short loc_180006BD1
0x180006bb8  sub     ecx, 1
0x180006bbb  jz      short loc_180006BD1
0x180006bbd  sub     ecx, 1
0x180006bc0  jz      short loc_180006BD1
0x180006bc2  sub     ecx, 1
0x180006bc5  jz      short loc_180006BD1
0x180006bc7  sub     ecx, 1
0x180006bca  jz      short loc_180006BD1
0x180006bcc  cmp     ecx, 1
0x180006bcf  jnz     short loc_180006BF2
0x180006bd1  add     r9d, 0FFFFFFC9h
0x180006bd5  jmp     short loc_180006BFB
0x180006bd7  mov     ecx, edx
0x180006bd9  sub     ecx, 62h ; 'b'
0x180006bdc  jz      short loc_180006BF7
0x180006bde  sub     ecx, 1
0x180006be1  jz      short loc_180006BF7
0x180006be3  sub     ecx, 1
0x180006be6  jz      short loc_180006BF7
0x180006be8  sub     ecx, 1
0x180006beb  jz      short loc_180006BF7
0x180006bed  cmp     ecx, 1
0x180006bf0  jz      short loc_180006BF7
0x180006bf2  mov     r9d, ebx
0x180006bf5  jmp     short loc_180006BFB
0x180006bf7  lea     r9d, [rdx-57h]
0x180006bfb  mov     r8d, r10d
0x180006bfe  shr     r8, 1
0x180006c01  mov     rdx, [rsp+21E8h+var_2158]
0x180006c09  mov     eax, r10d
0x180006c0c  and     eax, 1
0x180006c0f  shl     eax, 2
0x180006c12  mov     ecx, 4
0x180006c17  sub     ecx, eax
0x180006c19  shl     r9b, cl
0x180006c1c  or      [r8+rdx], r9b
0x180006c20  inc     r10d
  ... truncated ...
```
