# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180025d40`
- end: `0x1800261ec`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180027800`

## callees

- `0x180018db4`
- `0x18001901c`
- `0x1800258f8`
- `0x180025934`
- `0x1800259b0`
- `0x180025d40`
- `0x1800261f4`
- `0x180026f14`
- `0x180027ed4`
- `0x18008170e`
- `0x180081750`
- `0x180081810`

## import_xrefs

- `USER32!CharNextW` at `0x180025e99`
- `USER32!CharNextW` at `0x180025eb5`
- `USER32!CharNextW` at `0x180025e99`
- `USER32!CharNextW` at `0x180025eb5`
- `ADVAPI32!RegSetValueExW` at `0x180025f21`
- `ADVAPI32!RegSetValueExW` at `0x180025fad`
- `ADVAPI32!RegSetValueExW` at `0x180026149`
- `ADVAPI32!RegSetValueExW` at `0x180026199`
- `ADVAPI32!RegSetValueExW` at `0x180025f21`
- `ADVAPI32!RegSetValueExW` at `0x180025fad`
- `ADVAPI32!RegSetValueExW` at `0x180026149`
- `ADVAPI32!RegSetValueExW` at `0x180026199`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180025f66`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180025f66`
- `KERNEL32!lstrcmpiW` at `0x180025dc1`
- `KERNEL32!lstrcmpiW` at `0x180025dc1`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v4; // r15
  HKEY *v6; // r12
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
  __int64 v22; // rdi
  size_t v23; // rsi
  unsigned __int64 v24; // rax
  BYTE *v25; // rcx
  unsigned int v26; // r10d
  unsigned int v27; // edx
  char v28; // r9
  __int64 v29; // rdi
  int Token; // eax
  unsigned int v31; // ecx
  unsigned __int16 *v32; // [rsp+30h] [rbp-D0h] BYREF
  ULONG pulOut[2]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v36[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR String1[4096]; // [rsp+160h] [rbp+60h] BYREF

  v4 = a4;
  v32 = a4;
  v6 = a2;
  *(_QWORD *)pulOut = a2;
  v7 = this;
  *(_QWORD *)Data = this;
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
    v29 = -1;
    do
      ++v29;
    while ( String1[v29] );
    v20 = RegSetValueExW(*v6, a3, 0, 1u, (const BYTE *)String1, 2 * v29 + 2);
    goto LABEL_77;
  }
  if ( v10 == 17 )
  {
    v22 = -1;
    do
      ++v22;
    while ( String1[v22] );
    if ( (v22 & 1) != 0 )
      return 2147500037LL;
    v23 = (int)v22 / 2;
    lpData = 0;
    v24 = ATL::AtlMultiplyThrow<unsigned __int64>(v23, 1);
    if ( v24 <= 0x100 )
    {
      v25 = v36;
      lpData = v36;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v24);
      v25 = lpData;
    }
    if ( !v25 )
    {
      ATL::CTempBuffer<unsigned short,10,ATL::CCRTAllocator>::~CTempBuffer<unsigned short,10,ATL::CCRTAllocator>(&lpData);
      return 2147500037LL;
    }
    memset_0(v25, 0, v23);
    v26 = 0;
    if ( (int)v22 <= 0 )
      goto LABEL_73;
    while ( 1 )
    {
      v27 = String1[v26];
      if ( v27 > 0x61 )
      {
        if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
        {
LABEL_70:
          v28 = v27 - 87;
          goto LABEL_71;
        }
LABEL_69:
        v28 = 0;
        goto LABEL_71;
      }
      if ( v27 == 97 )
        goto LABEL_70;
      if ( v27 <= 0x38 )
        break;
      if ( v27 == 57 )
        goto LABEL_57;
      if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
        goto LABEL_69;
      v28 = v27 - 55;
LABEL_71:
      lpData[(unsigned __int64)v26 >> 1] |= v28 << (4 - 4 * (v26 & 1));
      if ( (int)++v26 >= (int)v22 )
      {
        v4 = v32;
LABEL_73:
        v20 = RegSetValueExW(*v6, a3, 0, 3u, lpData, v23);
        ATL::CTempBuffer<unsigned short,10,ATL::CCRTAllocator>::~CTempBuffer<unsigned short,10,ATL::CCRTAllocator>(&lpData);
        v7 = *(ATL::CRegParser **)Data;
LABEL_77:
        if ( v20 )
          return ATL::AtlHresultFromWin32(v20);
LABEL_79:
        Token = ATL::CRegParser::NextToken(v7, v4);
        v31 = 0;
        if ( Token < 0 )
          return (unsigned int)Token;
        return v31;
      }
    }
    if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
      goto LABEL_69;
LABEL_57:
    v28 = v27 - 48;
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
        v13 = v36;
        lpData = v36;
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
          v6 = *(HKEY **)pulOut;
          v4 = v32;
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
        v20 = RegSetValueExW(*v6, a3, 0, 7u, lpData, cbData);
      }
      else
      {
        v20 = 14;
      }
      ATL::CTempBuffer<unsigned short,10,ATL::CCRTAllocator>::~CTempBuffer<unsigned short,10,ATL::CCRTAllocator>(&lpData);
      v7 = *(ATL::CRegParser **)Data;
      goto LABEL_77;
    }
    goto LABEL_79;
  }
  pulOut[0] = 0;
  v32 = 0;
  v21 = VarUI4FromStr(String1, 0, 0, pulOut);
  if ( v21 >= 0 )
  {
    *(_DWORD *)Data = pulOut[0];
    v20 = RegSetValueExW(*v6, a3, 0, 4u, Data, 4u);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
    goto LABEL_77;
  }
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x180025d40  push    rbp
0x180025d42  push    rbx
0x180025d43  push    rsi
0x180025d44  push    rdi
0x180025d45  push    r12
0x180025d47  push    r13
0x180025d49  push    r14
0x180025d4b  push    r15
0x180025d4d  lea     rbp, [rsp-2078h]
0x180025d55  mov     eax, 2178h
0x180025d5a  call    _alloca_probe
0x180025d5f  sub     rsp, rax
0x180025d62  mov     rax, cs:__security_cookie
0x180025d69  xor     rax, rsp
0x180025d6c  mov     [rbp+20B0h+var_50], rax
0x180025d73  mov     r15, r9
0x180025d76  mov     [rsp+21B0h+var_2180], r9
0x180025d7b  mov     r13, r8
0x180025d7e  mov     r12, rdx
0x180025d81  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x180025d86  mov     r14, rcx
0x180025d89  mov     qword ptr [rsp+21B0h+Data], rcx
0x180025d8e  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180025d92  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180025d97  xor     esi, esi
0x180025d99  test    eax, eax
0x180025d9b  js      loc_1800261C9
0x180025da1  mov     ebx, esi
0x180025da3  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180025daa  cmp     ebx, 4
0x180025dad  jnb     loc_1800261C4
0x180025db3  movsxd  rdi, ebx
0x180025db6  add     rdi, rdi
0x180025db9  mov     rdx, [rax+rdi*8]; lpString2
0x180025dbd  lea     rcx, [rbp+20B0h+String1]; lpString1
0x180025dc1  call    cs:__imp_lstrcmpiW
0x180025dc7  test    eax, eax
0x180025dc9  jz      short loc_180025DCF
0x180025dcb  inc     ebx
0x180025dcd  jmp     short loc_180025DA3
0x180025dcf  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180025dd6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180025ddb  mov     rcx, r14; this
0x180025dde  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180025de3  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180025de7  mov     rcx, r14; this
0x180025dea  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180025def  test    eax, eax
0x180025df1  js      loc_1800261C9
0x180025df7  mov     eax, 8
0x180025dfc  cmp     bx, ax
0x180025dff  jz      loc_180026164
0x180025e05  cmp     bx, 11h
0x180025e09  jz      loc_180025FC4
0x180025e0f  cmp     bx, 13h
0x180025e13  jz      loc_180025F4F
0x180025e19  mov     eax, 4008h
0x180025e1e  cmp     bx, ax
0x180025e21  jnz     loc_1800261AE
0x180025e27  lea     rcx, [rbp+20B0h+String1]
0x180025e2b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025e2f  mov     rax, rdi
0x180025e32  inc     rax
0x180025e35  cmp     [rcx+rax*2], si
0x180025e39  jnz     short loc_180025E32
0x180025e3b  add     eax, 2
0x180025e3e  mov     [rsp+21B0h+var_2160], rsi
0x180025e43  movsxd  rcx, eax
0x180025e46  mov     r14d, 2
0x180025e4c  mov     edx, r14d
0x180025e4f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180025e54  cmp     rax, 100h
0x180025e5a  jbe     short loc_180025E70
0x180025e5c  mov     rdx, rax
0x180025e5f  lea     rcx, [rsp+21B0h+var_2160]
0x180025e64  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180025e69  mov     rbx, [rsp+21B0h+var_2160]
0x180025e6e  jmp     short loc_180025E7A
0x180025e70  lea     rbx, [rsp+21B0h+var_2158]
0x180025e75  mov     [rsp+21B0h+var_2160], rbx
0x180025e7a  test    rbx, rbx
0x180025e7d  jz      loc_180025F36
0x180025e83  lea     rsi, [rbp+20B0h+String1]
0x180025e87  xor     eax, eax
0x180025e89  cmp     [rbp+20B0h+String1], ax
0x180025e8d  jz      short loc_180025ED9
0x180025e8f  lea     r15d, [rax+30h]
0x180025e93  xor     r12d, r12d
0x180025e96  mov     rcx, rsi; lpsz
0x180025e99  call    cs:__imp_CharNextW
0x180025e9f  movzx   ecx, word ptr [rsi]
0x180025ea2  cmp     cx, 5Ch ; '\'
0x180025ea6  jnz     short loc_180025EC0
0x180025ea8  cmp     [rax], r15w
0x180025eac  jnz     short loc_180025EC0
0x180025eae  mov     [rbx], r12w
0x180025eb2  mov     rcx, rax; lpsz
0x180025eb5  call    cs:__imp_CharNextW
0x180025ebb  mov     rsi, rax
0x180025ebe  jmp     short loc_180025EC6
0x180025ec0  mov     [rbx], cx
0x180025ec3  add     rsi, r14
0x180025ec6  add     rbx, r14
0x180025ec9  cmp     [rsi], r12w
0x180025ecd  jnz     short loc_180025E96
0x180025ecf  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x180025ed4  mov     r15, [rsp+21B0h+var_2180]
0x180025ed9  xor     esi, esi
0x180025edb  mov     [rbx], esi
0x180025edd  mov     r8, [rsp+21B0h+var_2160]
0x180025ee2  test    r8, r8
0x180025ee5  jz      short loc_180025F2B
0x180025ee7  mov     r10d, esi
0x180025eea  mov     r9, r8
0x180025eed  mov     rcx, rdi
0x180025ef0  inc     rcx
0x180025ef3  cmp     [r9+rcx*2], si
0x180025ef8  jnz     short loc_180025EF0
0x180025efa  inc     ecx
0x180025efc  lea     r9, [r9+rcx*2]
0x180025f00  lea     r10d, [r10+rcx*2]
0x180025f04  cmp     ecx, 1
0x180025f07  jnz     short loc_180025EED
0x180025f09  mov     [rsp+21B0h+cbData], r10d; cbData
0x180025f0e  mov     [rsp+21B0h+lpData], r8; lpData
0x180025f13  lea     r9d, [rcx+6]; dwType
0x180025f17  xor     r8d, r8d; Reserved
0x180025f1a  mov     rdx, r13; lpValueName
0x180025f1d  mov     rcx, [r12]; hKey
0x180025f21  call    cs:__imp_RegSetValueExW
0x180025f27  mov     ebx, eax
0x180025f29  jmp     short loc_180025F3B
0x180025f2b  mov     ecx, 80004005h; int
0x180025f30  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180025f36  mov     ebx, 0Eh
0x180025f3b  lea     rcx, [rsp+21B0h+var_2160]
0x180025f40  call    ??1?$CTempBuffer@G$09VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,10,ATL::CCRTAllocator>::~CTempBuffer<ushort,10,ATL::CCRTAllocator>(void)
0x180025f45  mov     r14, qword ptr [rsp+21B0h+Data]
0x180025f4a  jmp     loc_1800261A1
0x180025f4f  mov     [rsp+21B0h+pulOut], esi
0x180025f53  mov     [rsp+21B0h+var_2180], rsi
0x180025f58  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x180025f5d  xor     r8d, r8d; dwFlags
0x180025f60  xor     edx, edx; lcid
0x180025f62  lea     rcx, [rbp+20B0h+String1]; strIn
0x180025f66  call    cs:__imp_VarUI4FromStr
0x180025f6c  mov     ebx, eax
0x180025f6e  test    eax, eax
0x180025f70  jns     short loc_180025F83
0x180025f72  lea     rcx, [rsp+21B0h+var_2180]
0x180025f77  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180025f7c  mov     eax, ebx
0x180025f7e  jmp     loc_1800261C9
0x180025f83  mov     eax, [rsp+21B0h+pulOut]
0x180025f87  mov     dword ptr [rsp+21B0h+Data], eax
0x180025f8b  mov     [rsp+21B0h+cbData], 4; cbData
0x180025f93  lea     rax, [rsp+21B0h+Data]
0x180025f98  mov     [rsp+21B0h+lpData], rax; lpData
0x180025f9d  mov     r9d, 4; dwType
0x180025fa3  xor     r8d, r8d; Reserved
0x180025fa6  mov     rdx, r13; lpValueName
0x180025fa9  mov     rcx, [r12]; hKey
0x180025fad  call    cs:__imp_RegSetValueExW
0x180025fb3  mov     ebx, eax
0x180025fb5  lea     rcx, [rsp+21B0h+var_2180]
0x180025fba  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180025fbf  jmp     loc_1800261A1
0x180025fc4  lea     rax, [rbp+20B0h+String1]
0x180025fc8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180025fcc  inc     rdi
0x180025fcf  cmp     [rax+rdi*2], si
0x180025fd3  jnz     short loc_180025FCC
0x180025fd5  test    dil, 1
0x180025fd9  jz      short loc_180025FE5
0x180025fdb  mov     eax, 80004005h
0x180025fe0  jmp     loc_1800261C9
0x180025fe5  mov     eax, edi
0x180025fe7  cdq
0x180025fe8  mov     r14d, 2
0x180025fee  idiv    r14d
0x180025ff1  movsxd  rsi, eax
0x180025ff4  xor     r14d, r14d
0x180025ff7  mov     [rsp+21B0h+var_2160], r14
0x180025ffc  lea     edx, [r14+1]
0x180026000  mov     rcx, rsi
0x180026003  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180026008  cmp     rax, 100h
0x18002600e  jbe     short loc_180026024
0x180026010  mov     rdx, rax
0x180026013  lea     rcx, [rsp+21B0h+var_2160]
0x180026018  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002601d  mov     rcx, [rsp+21B0h+var_2160]
0x180026022  jmp     short loc_18002602E
0x180026024  lea     rcx, [rsp+21B0h+var_2158]; void *
0x180026029  mov     [rsp+21B0h+var_2160], rcx
0x18002602e  test    rcx, rcx
0x180026031  jnz     short loc_18002603F
0x180026033  lea     rcx, [rsp+21B0h+var_2160]
0x180026038  call    ??1?$CTempBuffer@G$09VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,10,ATL::CCRTAllocator>::~CTempBuffer<ushort,10,ATL::CCRTAllocator>(void)
0x18002603d  jmp     short loc_180025FDB
0x18002603f  mov     r8, rsi; Size
0x180026042  xor     edx, edx; Val
0x180026044  call    memset_0
0x180026049  mov     r10d, r14d
0x18002604c  test    edi, edi
0x18002604e  jle     loc_18002612B
0x180026054  mov     r15d, 30h ; '0'
0x18002605a  mov     eax, r10d
0x18002605d  movzx   edx, [rbp+rax*2+20B0h+String1]
0x180026062  cmp     edx, 61h ; 'a'
0x180026065  ja      short loc_1800260D4
0x180026067  jz      loc_1800260F4
0x18002606d  cmp     edx, 38h ; '8'
0x180026070  ja      short loc_1800260A6
0x180026072  jz      short loc_18002609E
0x180026074  mov     ecx, edx
0x180026076  sub     ecx, r15d
0x180026079  jz      short loc_18002609E
0x18002607b  sub     ecx, 1
0x18002607e  jz      short loc_18002609E
0x180026080  sub     ecx, 1
0x180026083  jz      short loc_18002609E
0x180026085  sub     ecx, 1
0x180026088  jz      short loc_18002609E
0x18002608a  sub     ecx, 1
0x18002608d  jz      short loc_18002609E
0x18002608f  sub     ecx, 1
0x180026092  jz      short loc_18002609E
0x180026094  sub     ecx, 1
0x180026097  jz      short loc_18002609E
0x180026099  cmp     ecx, 1
0x18002609c  jnz     short loc_1800260EF
0x18002609e  mov     r9d, edx
0x1800260a1  sub     r9d, r15d
0x1800260a4  jmp     short loc_1800260F8
0x1800260a6  mov     r9d, edx
0x1800260a9  mov     ecx, edx
0x1800260ab  sub     ecx, 39h ; '9'
0x1800260ae  jz      short loc_18002609E
0x1800260b0  sub     ecx, 8
0x1800260b3  jz      short loc_1800260CE
0x1800260b5  sub     ecx, 1
0x1800260b8  jz      short loc_1800260CE
0x1800260ba  sub     ecx, 1
0x1800260bd  jz      short loc_1800260CE
0x1800260bf  sub     ecx, 1
0x1800260c2  jz      short loc_1800260CE
0x1800260c4  sub     ecx, 1
0x1800260c7  jz      short loc_1800260CE
0x1800260c9  cmp     ecx, 1
0x1800260cc  jnz     short loc_1800260EF
0x1800260ce  add     r9d, 0FFFFFFC9h
0x1800260d2  jmp     short loc_1800260F8
0x1800260d4  mov     ecx, edx
0x1800260d6  sub     ecx, 62h ; 'b'
0x1800260d9  jz      short loc_1800260F4
0x1800260db  sub     ecx, 1
0x1800260de  jz      short loc_1800260F4
0x1800260e0  sub     ecx, 1
0x1800260e3  jz      short loc_1800260F4
0x1800260e5  sub     ecx, 1
0x1800260e8  jz      short loc_1800260F4
0x1800260ea  cmp     ecx, 1
0x1800260ed  jz      short loc_1800260F4
0x1800260ef  mov     r9d, r14d
0x1800260f2  jmp     short loc_1800260F8
0x1800260f4  lea     r9d, [rdx-57h]
0x1800260f8  mov     r8d, r10d
0x1800260fb  shr     r8, 1
0x1800260fe  mov     rdx, [rsp+21B0h+var_2160]
0x180026103  mov     eax, r10d
0x180026106  and     eax, 1
0x180026109  shl     eax, 2
0x18002610c  mov     ecx, 4
0x180026111  sub     ecx, eax
0x180026113  shl     r9b, cl
0x180026116  or      [r8+rdx], r9b
0x18002611a  inc     r10d
0x18002611d  cmp     r10d, edi
0x180026120  jl      loc_18002605A
0x180026126  mov     r15, [rsp+21B0h+var_2180]
0x18002612b  mov     rax, [rsp+21B0h+var_2160]
0x180026130  mov     [rsp+21B0h+cbData], esi; cbData
0x180026134  mov     [rsp+21B0h+lpData], rax; lpData
0x180026139  mov     r9d, 3; dwType
0x18002613f  xor     r8d, r8d; Reserved
0x180026142  mov     rdx, r13; lpValueName
0x180026145  mov     rcx, [r12]; hKey
0x180026149  call    cs:__imp_RegSetValueExW
0x18002614f  mov     ebx, eax
0x180026151  lea     rcx, [rsp+21B0h+var_2160]
0x180026156  call    ??1?$CTempBuffer@G$09VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<ushort,10,ATL::CCRTAllocator>::~CTempBuffer<ushort,10,ATL::CCRTAllocator>(void)
0x18002615b  mov     r14, qword ptr [rsp+21B0h+Data]
0x180026160  xor     esi, esi
0x180026162  jmp     short loc_1800261A1
0x180026164  lea     rax, [rbp+20B0h+String1]
0x180026168  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002616c  inc     rdi
0x18002616f  cmp     [rax+rdi*2], si
0x180026173  jnz     short loc_18002616C
  ... truncated ...
```
