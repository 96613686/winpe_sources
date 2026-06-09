# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18002edbc`
- end: `0x18002f33c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180032298`

## callees

- `0x18002b530`
- `0x18002c5b0`
- `0x18002d39c`
- `0x18002e130`
- `0x18002e280`
- `0x18002edbc`
- `0x18002f344`
- `0x18002f650`
- `0x18002fdb8`
- `0x180031720`
- `0x180033130`
- `0x180081700`

## import_xrefs

- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002effe`
- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002f091`
- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002f28f`
- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002f2e6`
- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002effe`
- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002f091`
- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002f28f`
- `api-ms-win-core-localregistry-l1-1-0!RegSetValueExW` at `0x18002f2e6`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002f04a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18002f04a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ef79`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ef95`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ef79`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18002ef95`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ee57`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18002ee57`

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
0x18002edbc  push    rbx
0x18002edbe  push    rsi
0x18002edbf  push    rdi
0x18002edc0  push    r12
0x18002edc2  push    r13
0x18002edc4  push    r14
0x18002edc6  push    r15
0x18002edc8  mov     eax, 21B0h
0x18002edcd  call    _alloca_probe
0x18002edd2  sub     rsp, rax
0x18002edd5  mov     rax, cs:__security_cookie
0x18002eddc  xor     rax, rsp
0x18002eddf  mov     [rsp+21E8h+var_48], rax
0x18002ede7  mov     r14, r8
0x18002edea  mov     [rsp+21E8h+lpValueName], r8
0x18002edef  mov     r12, rdx
0x18002edf2  mov     [rsp+21E8h+var_2198], rdx
0x18002edf7  mov     r15, rcx
0x18002edfa  mov     [rsp+21E8h+var_21B0], rcx
0x18002edff  mov     qword ptr [rsp+21E8h+Data], rdx
0x18002ee04  mov     [rsp+21E8h+var_2190], rcx
0x18002ee09  mov     [rsp+21E8h+var_2170], rdx
0x18002ee0e  mov     [rsp+21E8h+var_2188], r8
0x18002ee13  mov     [rsp+21E8h+var_2168], r9
0x18002ee1b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18002ee23  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002ee28  xor     ebx, ebx
0x18002ee2a  test    eax, eax
0x18002ee2c  js      loc_18002F319
0x18002ee32  mov     edi, ebx
0x18002ee34  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18002ee3b  cmp     edi, 4
0x18002ee3e  jnb     loc_18002F314
0x18002ee44  movsxd  rsi, edi
0x18002ee47  add     rsi, rsi
0x18002ee4a  mov     rdx, [r13+rsi*8+0]; lpString2
0x18002ee4f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18002ee57  call    cs:__imp_lstrcmpiW
0x18002ee5d  test    eax, eax
0x18002ee5f  jz      short loc_18002EE65
0x18002ee61  inc     edi
0x18002ee63  jmp     short loc_18002EE3B
0x18002ee65  movzx   edi, word ptr [r13+rsi*8+8]
0x18002ee6b  mov     rcx, r15; this
0x18002ee6e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18002ee73  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18002ee7b  mov     rcx, r15; this
0x18002ee7e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18002ee83  test    eax, eax
0x18002ee85  js      loc_18002F319
0x18002ee8b  mov     r13d, 8
0x18002ee91  cmp     di, r13w
0x18002ee95  jz      loc_18002F2A9
0x18002ee9b  cmp     di, 11h
0x18002ee9f  jz      loc_18002F0A8
0x18002eea5  cmp     di, 13h
0x18002eea9  jz      loc_18002F02F
0x18002eeaf  mov     eax, 4008h
0x18002eeb4  cmp     di, ax
0x18002eeb7  jnz     loc_18002F2FB
0x18002eebd  lea     rcx, [rsp+21E8h+String1]
0x18002eec5  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002eec9  mov     rax, rsi
0x18002eecc  inc     rax
0x18002eecf  cmp     [rcx+rax*2], bx
0x18002eed3  jnz     short loc_18002EECC
0x18002eed5  add     eax, 2
0x18002eed8  mov     [rsp+21E8h+var_2158], rbx
0x18002eee0  movsxd  rcx, eax
0x18002eee3  mov     r15d, 2
0x18002eee9  mov     edx, r15d
0x18002eeec  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002eef1  cmp     rax, 100h
0x18002eef7  jbe     short loc_18002EF13
0x18002eef9  mov     rdx, rax
0x18002eefc  lea     rcx, [rsp+21E8h+var_2158]
0x18002ef04  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002ef09  mov     rdi, [rsp+21E8h+var_2158]
0x18002ef11  jmp     short loc_18002EF23
0x18002ef13  lea     rdi, [rsp+21E8h+var_2150]
0x18002ef1b  mov     [rsp+21E8h+var_2158], rdi
0x18002ef23  mov     r13, [rsp+21E8h+var_2198]
0x18002ef28  jmp     short loc_18002EF55
0x18002ef2a  xor     ebx, ebx
0x18002ef2c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002ef30  lea     r15d, [rbx+2]
0x18002ef34  mov     rdi, [rsp+21E8h+var_2158]
0x18002ef3c  mov     r13, qword ptr [rsp+21E8h+Data]
0x18002ef41  mov     rax, [rsp+21E8h+var_2190]
0x18002ef46  mov     [rsp+21E8h+var_21B0], rax
0x18002ef4b  mov     rax, [rsp+21E8h+var_2188]
0x18002ef50  mov     [rsp+21E8h+lpValueName], rax
0x18002ef55  test    rdi, rdi
0x18002ef58  jz      loc_18002F013
0x18002ef5e  lea     r14, [rsp+21E8h+String1]
0x18002ef66  cmp     [rsp+21E8h+String1], bx
0x18002ef6e  jz      short loc_18002EFAF
0x18002ef70  mov     r12d, 30h ; '0'
0x18002ef76  mov     rcx, r14; lpsz
0x18002ef79  call    cs:__imp_CharNextW
0x18002ef7f  movzx   ecx, word ptr [r14]
0x18002ef83  cmp     cx, 5Ch ; '\'
0x18002ef87  jnz     short loc_18002EFA0
0x18002ef89  cmp     [rax], r12w
0x18002ef8d  jnz     short loc_18002EFA0
0x18002ef8f  mov     [rdi], bx
0x18002ef92  mov     rcx, rax; lpsz
0x18002ef95  call    cs:__imp_CharNextW
0x18002ef9b  mov     r14, rax
0x18002ef9e  jmp     short loc_18002EFA6
0x18002efa0  mov     [rdi], cx
0x18002efa3  add     r14, r15
0x18002efa6  add     rdi, r15
0x18002efa9  cmp     [r14], bx
0x18002efad  jnz     short loc_18002EF76
0x18002efaf  mov     dword ptr [rdi], 0
0x18002efb5  mov     r8, [rsp+21E8h+var_2158]
0x18002efbd  test    r8, r8
0x18002efc0  jz      short loc_18002F008
0x18002efc2  mov     r10d, ebx
0x18002efc5  mov     r9, r8
0x18002efc8  mov     rcx, rsi
0x18002efcb  inc     rcx
0x18002efce  cmp     [r9+rcx*2], bx
0x18002efd3  jnz     short loc_18002EFCB
0x18002efd5  inc     ecx
0x18002efd7  lea     r9, [r9+rcx*2]
0x18002efdb  lea     r10d, [r10+rcx*2]
0x18002efdf  cmp     ecx, 1
0x18002efe2  jnz     short loc_18002EFC8
0x18002efe4  mov     [rsp+21E8h+cbData], r10d; cbData
0x18002efe9  mov     [rsp+21E8h+lpData], r8; lpData
0x18002efee  lea     r9d, [rcx+6]; dwType
0x18002eff2  xor     r8d, r8d; Reserved
0x18002eff5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18002effa  mov     rcx, [r13+0]; hKey
0x18002effe  call    cs:__imp_RegSetValueExW
0x18002f004  mov     edi, eax
0x18002f006  jmp     short loc_18002F018
0x18002f008  mov     ecx, 80004005h; int
0x18002f00d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18002f013  mov     edi, 0Eh
0x18002f018  lea     rcx, [rsp+21E8h+var_2158]
0x18002f020  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002f025  mov     r15, [rsp+21E8h+var_21B0]
0x18002f02a  jmp     loc_18002F2EE
0x18002f02f  mov     [rsp+21E8h+pulOut], ebx
0x18002f033  mov     [rsp+21E8h+var_21B0], rbx
0x18002f038  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18002f03d  xor     r8d, r8d; dwFlags
0x18002f040  xor     edx, edx; lcid
0x18002f042  lea     rcx, [rsp+21E8h+String1]; strIn
0x18002f04a  call    cs:__imp_VarUI4FromStr
0x18002f050  mov     edi, eax
0x18002f052  test    eax, eax
0x18002f054  jns     short loc_18002F067
0x18002f056  lea     rcx, [rsp+21E8h+var_21B0]
0x18002f05b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002f060  mov     eax, edi
0x18002f062  jmp     loc_18002F319
0x18002f067  mov     eax, [rsp+21E8h+pulOut]
0x18002f06b  mov     dword ptr [rsp+21E8h+Data], eax
0x18002f06f  mov     [rsp+21E8h+cbData], 4; cbData
0x18002f077  lea     rax, [rsp+21E8h+Data]
0x18002f07c  mov     [rsp+21E8h+lpData], rax; lpData
0x18002f081  mov     r9d, 4; dwType
0x18002f087  xor     r8d, r8d; Reserved
0x18002f08a  mov     rdx, r14; lpValueName
0x18002f08d  mov     rcx, [r12]; hKey
0x18002f091  call    cs:__imp_RegSetValueExW
0x18002f097  mov     edi, eax
0x18002f099  lea     rcx, [rsp+21E8h+var_21B0]
0x18002f09e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002f0a3  jmp     loc_18002F2EE
0x18002f0a8  lea     rax, [rsp+21E8h+String1]
0x18002f0b0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18002f0b4  inc     rsi
0x18002f0b7  cmp     [rax+rsi*2], bx
0x18002f0bb  jnz     short loc_18002F0B4
0x18002f0bd  mov     dword ptr [rsp+21E8h+Data], esi
0x18002f0c1  test    sil, 1
0x18002f0c5  jz      short loc_18002F0D1
0x18002f0c7  mov     eax, 80004005h
0x18002f0cc  jmp     loc_18002F319
0x18002f0d1  mov     eax, esi
0x18002f0d3  cdq
0x18002f0d4  mov     r15d, 2
0x18002f0da  idiv    r15d
0x18002f0dd  movsxd  r14, eax
0x18002f0e0  mov     [rsp+21E8h+var_2158], rbx
0x18002f0e8  mov     rdi, r14
0x18002f0eb  mov     [rsp+21E8h+var_2178], r14
0x18002f0f0  lea     edx, [r15-1]
0x18002f0f4  mov     rcx, r14
0x18002f0f7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002f0fc  cmp     rax, 100h
0x18002f102  jbe     short loc_18002F11E
0x18002f104  mov     rdx, rax
0x18002f107  lea     rcx, [rsp+21E8h+var_2158]
0x18002f10f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002f114  mov     rcx, [rsp+21E8h+var_2158]
0x18002f11c  jmp     short loc_18002F12E
0x18002f11e  lea     rcx, [rsp+21E8h+var_2150]
0x18002f126  mov     [rsp+21E8h+var_2158], rcx
0x18002f12e  mov     r15, [rsp+21E8h+var_2198]
0x18002f133  jmp     short loc_18002F168
0x18002f135  xor     ebx, ebx
0x18002f137  lea     r13d, [rbx+8]
0x18002f13b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18002f13f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18002f147  mov     rdi, [rsp+21E8h+var_2178]
0x18002f14c  mov     rax, [rsp+21E8h+var_2190]
0x18002f151  mov     [rsp+21E8h+var_21B0], rax
0x18002f156  mov     r15, [rsp+21E8h+var_2170]
0x18002f15b  mov     rax, [rsp+21E8h+var_2188]
0x18002f160  mov     [rsp+21E8h+lpValueName], rax
0x18002f165  mov     r14d, edi
0x18002f168  test    rcx, rcx
0x18002f16b  jnz     short loc_18002F17F
0x18002f16d  lea     rcx, [rsp+21E8h+var_2158]
0x18002f175  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002f17a  jmp     loc_18002F0C7
0x18002f17f  mov     r8, rdi; Size
0x18002f182  xor     edx, edx; Val
0x18002f184  call    memset_0
0x18002f189  mov     r10d, ebx
0x18002f18c  test    esi, esi
0x18002f18e  jle     loc_18002F26C
0x18002f194  mov     r12d, 30h ; '0'
0x18002f19a  mov     eax, r10d
0x18002f19d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18002f1a5  cmp     edx, 61h ; 'a'
0x18002f1a8  ja      short loc_18002F217
0x18002f1aa  jz      loc_18002F237
0x18002f1b0  cmp     edx, 38h ; '8'
0x18002f1b3  ja      short loc_18002F1E9
0x18002f1b5  jz      short loc_18002F1E1
0x18002f1b7  mov     ecx, edx
0x18002f1b9  sub     ecx, r12d
0x18002f1bc  jz      short loc_18002F1E1
0x18002f1be  sub     ecx, 1
0x18002f1c1  jz      short loc_18002F1E1
0x18002f1c3  sub     ecx, 1
0x18002f1c6  jz      short loc_18002F1E1
0x18002f1c8  sub     ecx, 1
0x18002f1cb  jz      short loc_18002F1E1
0x18002f1cd  sub     ecx, 1
0x18002f1d0  jz      short loc_18002F1E1
0x18002f1d2  sub     ecx, 1
0x18002f1d5  jz      short loc_18002F1E1
0x18002f1d7  sub     ecx, 1
0x18002f1da  jz      short loc_18002F1E1
0x18002f1dc  cmp     ecx, 1
0x18002f1df  jnz     short loc_18002F232
0x18002f1e1  mov     r9d, edx
0x18002f1e4  sub     r9d, r12d
0x18002f1e7  jmp     short loc_18002F23B
0x18002f1e9  mov     r9d, edx
0x18002f1ec  mov     ecx, edx
0x18002f1ee  sub     ecx, 39h ; '9'
0x18002f1f1  jz      short loc_18002F1E1
0x18002f1f3  sub     ecx, r13d
0x18002f1f6  jz      short loc_18002F211
0x18002f1f8  sub     ecx, 1
0x18002f1fb  jz      short loc_18002F211
0x18002f1fd  sub     ecx, 1
0x18002f200  jz      short loc_18002F211
0x18002f202  sub     ecx, 1
0x18002f205  jz      short loc_18002F211
0x18002f207  sub     ecx, 1
0x18002f20a  jz      short loc_18002F211
0x18002f20c  cmp     ecx, 1
0x18002f20f  jnz     short loc_18002F232
0x18002f211  add     r9d, 0FFFFFFC9h
0x18002f215  jmp     short loc_18002F23B
0x18002f217  mov     ecx, edx
0x18002f219  sub     ecx, 62h ; 'b'
0x18002f21c  jz      short loc_18002F237
0x18002f21e  sub     ecx, 1
0x18002f221  jz      short loc_18002F237
0x18002f223  sub     ecx, 1
0x18002f226  jz      short loc_18002F237
0x18002f228  sub     ecx, 1
0x18002f22b  jz      short loc_18002F237
0x18002f22d  cmp     ecx, 1
0x18002f230  jz      short loc_18002F237
0x18002f232  mov     r9d, ebx
0x18002f235  jmp     short loc_18002F23B
0x18002f237  lea     r9d, [rdx-57h]
0x18002f23b  mov     r8d, r10d
0x18002f23e  shr     r8, 1
0x18002f241  mov     rdx, [rsp+21E8h+var_2158]
0x18002f249  mov     eax, r10d
0x18002f24c  and     eax, 1
0x18002f24f  shl     eax, 2
0x18002f252  mov     ecx, 4
0x18002f257  sub     ecx, eax
0x18002f259  shl     r9b, cl
0x18002f25c  or      [r8+rdx], r9b
0x18002f260  inc     r10d
  ... truncated ...
```
