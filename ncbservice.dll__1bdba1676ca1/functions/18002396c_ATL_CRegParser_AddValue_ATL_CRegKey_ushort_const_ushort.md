# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18002396c`
- end: `0x180023eec`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180024d50`

## callees

- `0x18001d8e0`
- `0x18001e368`
- `0x180023484`
- `0x1800234bc`
- `0x180023510`
- `0x18002396c`
- `0x180023ef4`
- `0x1800240d8`
- `0x1800240f0`
- `0x1800244d4`
- `0x18002541c`
- `0x180032090`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023bae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023c41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023e3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023e96`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023bae`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023c41`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023e3f`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180023e96`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180023b29`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180023b45`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180023b29`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180023b45`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180023a07`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180023a07`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180023bfa`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180023bfa`

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
  int v12; // eax
  unsigned __int64 v13; // rax
  BYTE *v14; // rdi
  HKEY *v15; // r13
  WCHAR *j; // r14
  const WCHAR *v17; // rax
  DWORD cbData; // r10d
  BYTE *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  LSTATUS v22; // edi
  HRESULT v23; // edi
  __int64 v24; // rsi
  DWORD v25; // r14d
  size_t v26; // rdi
  unsigned __int64 v27; // rax
  BYTE *v28; // rcx
  HKEY *v29; // r15
  unsigned int v30; // r10d
  unsigned int v31; // edx
  char v32; // r9
  __int64 v33; // rsi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-21B0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21A8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-21A0h]
  HKEY *v39; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v40; // [rsp+58h] [rbp-2190h]
  const WCHAR *v41; // [rsp+60h] [rbp-2188h]
  size_t v42; // [rsp+70h] [rbp-2178h]
  HKEY *v43; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v44; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v39 = a2;
  v6 = this;
  v36 = this;
  *(_QWORD *)Data = a2;
  v40 = this;
  v43 = a2;
  v41 = a3;
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
      v33 = -1;
      do
        ++v33;
      while ( String1[v33] );
      v22 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v33 + 2);
      goto LABEL_80;
    case 17:
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      *(_DWORD *)Data = v24;
      if ( (v24 & 1) != 0 )
        return 2147500037LL;
      v25 = (int)v24 / 2;
      lpData = 0;
      v26 = (int)v24 / 2;
      v42 = v26;
      try
      {
        v27 = ((__int64 (*)(void))ATL::AtlMultiplyThrow<unsigned __int64>)();
        if ( v27 <= 0x100 )
        {
          v28 = v46;
          lpData = v46;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v27);
          v28 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v28 = lpData;
        v26 = v42;
        v36 = v40;
        v29 = v43;
        lpValueName = v41;
        v25 = v42;
        goto LABEL_47;
      }
      v29 = v39;
LABEL_47:
      if ( !v28 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v28, 0, v26);
      v30 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_76:
        v22 = RegSetValueExW(*v29, lpValueName, 0, 3u, lpData, v25);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_34;
      }
      while ( 1 )
      {
        v31 = String1[v30];
        if ( v31 > 0x61 )
        {
          if ( v31 == 98 || v31 == 99 || v31 == 100 || v31 - 101 < 2 )
          {
LABEL_74:
            v32 = v31 - 87;
            goto LABEL_75;
          }
LABEL_73:
          v32 = 0;
          goto LABEL_75;
        }
        if ( v31 == 97 )
          goto LABEL_74;
        if ( v31 <= 0x38 )
          break;
        if ( v31 == 57 )
          goto LABEL_61;
        if ( v31 != 65 && v31 != 66 && v31 != 67 && v31 != 68 && v31 - 69 > 1 )
          goto LABEL_73;
        v32 = v31 - 55;
LABEL_75:
        lpData[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
        if ( (int)++v30 >= (int)v24 )
          goto LABEL_76;
      }
      if ( v31 != 56 && v31 != 48 && v31 != 49 && v31 != 50 && v31 != 51 && v31 != 52 && v31 != 53 && v31 - 54 > 1 )
        goto LABEL_73;
LABEL_61:
      v32 = v31 - 48;
      goto LABEL_75;
    case 19:
      pulOut = 0;
      v36 = 0;
      v23 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v23 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v22 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v36);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v36);
      return (unsigned int)v23;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      v12 = v11 + 2;
      lpData = 0;
      try
      {
        v13 = ATL::AtlMultiplyThrow<unsigned __int64>(v12, 2);
        if ( v13 <= 0x100 )
        {
          v14 = v46;
          lpData = v46;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v13);
          v14 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        v14 = lpData;
        v15 = *(HKEY **)Data;
        v36 = v40;
        lpValueName = v41;
        goto LABEL_18;
      }
      v15 = v39;
LABEL_18:
      if ( v14 )
      {
        for ( j = String1; *j; v14 += 2 )
        {
          v17 = CharNextW(j);
          if ( *j == 92 && *v17 == 48 )
          {
            *(_WORD *)v14 = 0;
            j = CharNextW(v17);
          }
          else
          {
            *(_WORD *)v14 = *j++;
          }
        }
        *(_DWORD *)v14 = 0;
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
        v22 = RegSetValueExW(*v15, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v22 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v36;
LABEL_80:
      if ( v22 )
      {
        return ATL::AtlHresultFromWin32(v22);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v44);
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
0x18002396c  push    rbx
0x18002396e  push    rsi
0x18002396f  push    rdi
0x180023970  push    r12
0x180023972  push    r13
0x180023974  push    r14
0x180023976  push    r15
0x180023978  mov     eax, 21B0h
0x18002397d  call    _alloca_probe
0x180023982  sub     rsp, rax
0x180023985  mov     rax, cs:__security_cookie
0x18002398c  xor     rax, rsp
0x18002398f  mov     [rsp+21E8h+var_48], rax
0x180023997  mov     r14, r8
0x18002399a  mov     [rsp+21E8h+lpValueName], r8
0x18002399f  mov     r12, rdx
0x1800239a2  mov     [rsp+21E8h+var_2198], rdx
0x1800239a7  mov     r15, rcx
0x1800239aa  mov     [rsp+21E8h+var_21B0], rcx
0x1800239af  mov     qword ptr [rsp+21E8h+Data], rdx
0x1800239b4  mov     [rsp+21E8h+var_2190], rcx
0x1800239b9  mov     [rsp+21E8h+var_2170], rdx
0x1800239be  mov     [rsp+21E8h+var_2188], r8
0x1800239c3  mov     [rsp+21E8h+var_2168], r9
0x1800239cb  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x1800239d3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800239d8  xor     ebx, ebx
0x1800239da  test    eax, eax
0x1800239dc  js      loc_180023EC9
0x1800239e2  mov     edi, ebx
0x1800239e4  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800239eb  cmp     edi, 4
0x1800239ee  jnb     loc_180023EC4
0x1800239f4  movsxd  rsi, edi
0x1800239f7  add     rsi, rsi
0x1800239fa  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800239ff  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180023a07  call    cs:__imp_lstrcmpiW
0x180023a0d  test    eax, eax
0x180023a0f  jz      short loc_180023A15
0x180023a11  inc     edi
0x180023a13  jmp     short loc_1800239EB
0x180023a15  movzx   edi, word ptr [r13+rsi*8+8]
0x180023a1b  mov     rcx, r15; this
0x180023a1e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180023a23  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180023a2b  mov     rcx, r15; this
0x180023a2e  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180023a33  test    eax, eax
0x180023a35  js      loc_180023EC9
0x180023a3b  mov     r13d, 8
0x180023a41  cmp     di, r13w
0x180023a45  jz      loc_180023E59
0x180023a4b  cmp     di, 11h
0x180023a4f  jz      loc_180023C58
0x180023a55  cmp     di, 13h
0x180023a59  jz      loc_180023BDF
0x180023a5f  mov     eax, 4008h
0x180023a64  cmp     di, ax
0x180023a67  jnz     loc_180023EAB
0x180023a6d  lea     rcx, [rsp+21E8h+String1]
0x180023a75  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023a79  mov     rax, rsi
0x180023a7c  inc     rax
0x180023a7f  cmp     [rcx+rax*2], bx
0x180023a83  jnz     short loc_180023A7C
0x180023a85  add     eax, 2
0x180023a88  mov     [rsp+21E8h+var_2158], rbx
0x180023a90  movsxd  rcx, eax
0x180023a93  mov     r15d, 2
0x180023a99  mov     edx, r15d
0x180023a9c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180023aa1  cmp     rax, 100h
0x180023aa7  jbe     short loc_180023AC3
0x180023aa9  mov     rdx, rax
0x180023aac  lea     rcx, [rsp+21E8h+var_2158]
0x180023ab4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180023ab9  mov     rdi, [rsp+21E8h+var_2158]
0x180023ac1  jmp     short loc_180023AD3
0x180023ac3  lea     rdi, [rsp+21E8h+var_2150]
0x180023acb  mov     [rsp+21E8h+var_2158], rdi
0x180023ad3  mov     r13, [rsp+21E8h+var_2198]
0x180023ad8  jmp     short loc_180023B05
0x180023ada  xor     ebx, ebx
0x180023adc  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023ae0  lea     r15d, [rbx+2]
0x180023ae4  mov     rdi, [rsp+21E8h+var_2158]
0x180023aec  mov     r13, qword ptr [rsp+21E8h+Data]
0x180023af1  mov     rax, [rsp+21E8h+var_2190]
0x180023af6  mov     [rsp+21E8h+var_21B0], rax
0x180023afb  mov     rax, [rsp+21E8h+var_2188]
0x180023b00  mov     [rsp+21E8h+lpValueName], rax
0x180023b05  test    rdi, rdi
0x180023b08  jz      loc_180023BC3
0x180023b0e  lea     r14, [rsp+21E8h+String1]
0x180023b16  cmp     [rsp+21E8h+String1], bx
0x180023b1e  jz      short loc_180023B5F
0x180023b20  mov     r12d, 30h ; '0'
0x180023b26  mov     rcx, r14; lpsz
0x180023b29  call    cs:__imp_CharNextW
0x180023b2f  movzx   ecx, word ptr [r14]
0x180023b33  cmp     cx, 5Ch ; '\'
0x180023b37  jnz     short loc_180023B50
0x180023b39  cmp     [rax], r12w
0x180023b3d  jnz     short loc_180023B50
0x180023b3f  mov     [rdi], bx
0x180023b42  mov     rcx, rax; lpsz
0x180023b45  call    cs:__imp_CharNextW
0x180023b4b  mov     r14, rax
0x180023b4e  jmp     short loc_180023B56
0x180023b50  mov     [rdi], cx
0x180023b53  add     r14, r15
0x180023b56  add     rdi, r15
0x180023b59  cmp     [r14], bx
0x180023b5d  jnz     short loc_180023B26
0x180023b5f  mov     dword ptr [rdi], 0
0x180023b65  mov     r8, [rsp+21E8h+var_2158]
0x180023b6d  test    r8, r8
0x180023b70  jz      short loc_180023BB8
0x180023b72  mov     r10d, ebx
0x180023b75  mov     r9, r8
0x180023b78  mov     rcx, rsi
0x180023b7b  inc     rcx
0x180023b7e  cmp     [r9+rcx*2], bx
0x180023b83  jnz     short loc_180023B7B
0x180023b85  inc     ecx
0x180023b87  lea     r9, [r9+rcx*2]
0x180023b8b  lea     r10d, [r10+rcx*2]
0x180023b8f  cmp     ecx, 1
0x180023b92  jnz     short loc_180023B78
0x180023b94  mov     [rsp+21E8h+cbData], r10d; cbData
0x180023b99  mov     [rsp+21E8h+lpData], r8; lpData
0x180023b9e  lea     r9d, [rcx+6]; dwType
0x180023ba2  xor     r8d, r8d; Reserved
0x180023ba5  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x180023baa  mov     rcx, [r13+0]; hKey
0x180023bae  call    cs:__imp_RegSetValueExW
0x180023bb4  mov     edi, eax
0x180023bb6  jmp     short loc_180023BC8
0x180023bb8  mov     ecx, 80004005h; int
0x180023bbd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180023bc3  mov     edi, 0Eh
0x180023bc8  lea     rcx, [rsp+21E8h+var_2158]
0x180023bd0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180023bd5  mov     r15, [rsp+21E8h+var_21B0]
0x180023bda  jmp     loc_180023E9E
0x180023bdf  mov     [rsp+21E8h+pulOut], ebx
0x180023be3  mov     [rsp+21E8h+var_21B0], rbx
0x180023be8  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x180023bed  xor     r8d, r8d; dwFlags
0x180023bf0  xor     edx, edx; lcid
0x180023bf2  lea     rcx, [rsp+21E8h+String1]; strIn
0x180023bfa  call    cs:__imp_VarUI4FromStr
0x180023c00  mov     edi, eax
0x180023c02  test    eax, eax
0x180023c04  jns     short loc_180023C17
0x180023c06  lea     rcx, [rsp+21E8h+var_21B0]
0x180023c0b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180023c10  mov     eax, edi
0x180023c12  jmp     loc_180023EC9
0x180023c17  mov     eax, [rsp+21E8h+pulOut]
0x180023c1b  mov     dword ptr [rsp+21E8h+Data], eax
0x180023c1f  mov     [rsp+21E8h+cbData], 4; cbData
0x180023c27  lea     rax, [rsp+21E8h+Data]
0x180023c2c  mov     [rsp+21E8h+lpData], rax; lpData
0x180023c31  mov     r9d, 4; dwType
0x180023c37  xor     r8d, r8d; Reserved
0x180023c3a  mov     rdx, r14; lpValueName
0x180023c3d  mov     rcx, [r12]; hKey
0x180023c41  call    cs:__imp_RegSetValueExW
0x180023c47  mov     edi, eax
0x180023c49  lea     rcx, [rsp+21E8h+var_21B0]
0x180023c4e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180023c53  jmp     loc_180023E9E
0x180023c58  lea     rax, [rsp+21E8h+String1]
0x180023c60  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180023c64  inc     rsi
0x180023c67  cmp     [rax+rsi*2], bx
0x180023c6b  jnz     short loc_180023C64
0x180023c6d  mov     dword ptr [rsp+21E8h+Data], esi
0x180023c71  test    sil, 1
0x180023c75  jz      short loc_180023C81
0x180023c77  mov     eax, 80004005h
0x180023c7c  jmp     loc_180023EC9
0x180023c81  mov     eax, esi
0x180023c83  cdq
0x180023c84  mov     r15d, 2
0x180023c8a  idiv    r15d
0x180023c8d  movsxd  r14, eax
0x180023c90  mov     [rsp+21E8h+var_2158], rbx
0x180023c98  mov     rdi, r14
0x180023c9b  mov     [rsp+21E8h+var_2178], r14
0x180023ca0  lea     edx, [r15-1]
0x180023ca4  mov     rcx, r14
0x180023ca7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180023cac  cmp     rax, 100h
0x180023cb2  jbe     short loc_180023CCE
0x180023cb4  mov     rdx, rax
0x180023cb7  lea     rcx, [rsp+21E8h+var_2158]
0x180023cbf  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180023cc4  mov     rcx, [rsp+21E8h+var_2158]
0x180023ccc  jmp     short loc_180023CDE
0x180023cce  lea     rcx, [rsp+21E8h+var_2150]
0x180023cd6  mov     [rsp+21E8h+var_2158], rcx
0x180023cde  mov     r15, [rsp+21E8h+var_2198]
0x180023ce3  jmp     short loc_180023D18
0x180023ce5  xor     ebx, ebx
0x180023ce7  lea     r13d, [rbx+8]
0x180023ceb  mov     esi, dword ptr [rsp+21E8h+Data]
0x180023cef  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180023cf7  mov     rdi, [rsp+21E8h+var_2178]
0x180023cfc  mov     rax, [rsp+21E8h+var_2190]
0x180023d01  mov     [rsp+21E8h+var_21B0], rax
0x180023d06  mov     r15, [rsp+21E8h+var_2170]
0x180023d0b  mov     rax, [rsp+21E8h+var_2188]
0x180023d10  mov     [rsp+21E8h+lpValueName], rax
0x180023d15  mov     r14d, edi
0x180023d18  test    rcx, rcx
0x180023d1b  jnz     short loc_180023D2F
0x180023d1d  lea     rcx, [rsp+21E8h+var_2158]
0x180023d25  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180023d2a  jmp     loc_180023C77
0x180023d2f  mov     r8, rdi; Size
0x180023d32  xor     edx, edx; Val
0x180023d34  call    memset_0
0x180023d39  mov     r10d, ebx
0x180023d3c  test    esi, esi
0x180023d3e  jle     loc_180023E1C
0x180023d44  mov     r12d, 30h ; '0'
0x180023d4a  mov     eax, r10d
0x180023d4d  movzx   edx, [rsp+rax*2+21E8h+String1]
0x180023d55  cmp     edx, 61h ; 'a'
0x180023d58  ja      short loc_180023DC7
0x180023d5a  jz      loc_180023DE7
0x180023d60  cmp     edx, 38h ; '8'
0x180023d63  ja      short loc_180023D99
0x180023d65  jz      short loc_180023D91
0x180023d67  mov     ecx, edx
0x180023d69  sub     ecx, r12d
0x180023d6c  jz      short loc_180023D91
0x180023d6e  sub     ecx, 1
0x180023d71  jz      short loc_180023D91
0x180023d73  sub     ecx, 1
0x180023d76  jz      short loc_180023D91
0x180023d78  sub     ecx, 1
0x180023d7b  jz      short loc_180023D91
0x180023d7d  sub     ecx, 1
0x180023d80  jz      short loc_180023D91
0x180023d82  sub     ecx, 1
0x180023d85  jz      short loc_180023D91
0x180023d87  sub     ecx, 1
0x180023d8a  jz      short loc_180023D91
0x180023d8c  cmp     ecx, 1
0x180023d8f  jnz     short loc_180023DE2
0x180023d91  mov     r9d, edx
0x180023d94  sub     r9d, r12d
0x180023d97  jmp     short loc_180023DEB
0x180023d99  mov     r9d, edx
0x180023d9c  mov     ecx, edx
0x180023d9e  sub     ecx, 39h ; '9'
0x180023da1  jz      short loc_180023D91
0x180023da3  sub     ecx, r13d
0x180023da6  jz      short loc_180023DC1
0x180023da8  sub     ecx, 1
0x180023dab  jz      short loc_180023DC1
0x180023dad  sub     ecx, 1
0x180023db0  jz      short loc_180023DC1
0x180023db2  sub     ecx, 1
0x180023db5  jz      short loc_180023DC1
0x180023db7  sub     ecx, 1
0x180023dba  jz      short loc_180023DC1
0x180023dbc  cmp     ecx, 1
0x180023dbf  jnz     short loc_180023DE2
0x180023dc1  add     r9d, 0FFFFFFC9h
0x180023dc5  jmp     short loc_180023DEB
0x180023dc7  mov     ecx, edx
0x180023dc9  sub     ecx, 62h ; 'b'
0x180023dcc  jz      short loc_180023DE7
0x180023dce  sub     ecx, 1
0x180023dd1  jz      short loc_180023DE7
0x180023dd3  sub     ecx, 1
0x180023dd6  jz      short loc_180023DE7
0x180023dd8  sub     ecx, 1
0x180023ddb  jz      short loc_180023DE7
0x180023ddd  cmp     ecx, 1
0x180023de0  jz      short loc_180023DE7
0x180023de2  mov     r9d, ebx
0x180023de5  jmp     short loc_180023DEB
0x180023de7  lea     r9d, [rdx-57h]
0x180023deb  mov     r8d, r10d
0x180023dee  shr     r8, 1
0x180023df1  mov     rdx, [rsp+21E8h+var_2158]
0x180023df9  mov     eax, r10d
0x180023dfc  and     eax, 1
0x180023dff  shl     eax, 2
0x180023e02  mov     ecx, 4
0x180023e07  sub     ecx, eax
0x180023e09  shl     r9b, cl
0x180023e0c  or      [r8+rdx], r9b
0x180023e10  inc     r10d
  ... truncated ...
```
