# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800119c8`
- end: `0x180011e74`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x1800155fc`

## callees

- `0x18000f970`
- `0x1800103e8`
- `0x18001086c`
- `0x180010f88`
- `0x180010fd8`
- `0x1800119c8`
- `0x180011e7c`
- `0x180011fe8`
- `0x180012000`
- `0x180014370`
- `0x180016514`
- `0x180022540`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180011ba9`
- `ADVAPI32!RegSetValueExW` at `0x180011c35`
- `ADVAPI32!RegSetValueExW` at `0x180011dd1`
- `ADVAPI32!RegSetValueExW` at `0x180011e21`
- `ADVAPI32!RegSetValueExW` at `0x180011ba9`
- `ADVAPI32!RegSetValueExW` at `0x180011c35`
- `ADVAPI32!RegSetValueExW` at `0x180011dd1`
- `ADVAPI32!RegSetValueExW` at `0x180011e21`
- `KERNEL32!lstrcmpiW` at `0x180011a49`
- `KERNEL32!lstrcmpiW` at `0x180011a49`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180011bee`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180011bee`
- `USER32!CharNextW` at `0x180011b21`
- `USER32!CharNextW` at `0x180011b3d`
- `USER32!CharNextW` at `0x180011b21`
- `USER32!CharNextW` at `0x180011b3d`

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
0x1800119c8  push    rbp
0x1800119ca  push    rbx
0x1800119cb  push    rsi
0x1800119cc  push    rdi
0x1800119cd  push    r12
0x1800119cf  push    r13
0x1800119d1  push    r14
0x1800119d3  push    r15
0x1800119d5  lea     rbp, [rsp-2078h]
0x1800119dd  mov     eax, 2178h
0x1800119e2  call    _alloca_probe
0x1800119e7  sub     rsp, rax
0x1800119ea  mov     rax, cs:__security_cookie
0x1800119f1  xor     rax, rsp
0x1800119f4  mov     [rbp+20B0h+var_50], rax
0x1800119fb  mov     r12, rdx
0x1800119fe  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x180011a03  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180011a07  mov     [rsp+21B0h+var_2180], r9
0x180011a0c  mov     r15, r9
0x180011a0f  mov     qword ptr [rsp+21B0h+Data], rcx
0x180011a14  mov     r13, r8
0x180011a17  mov     r14, rcx
0x180011a1a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011a1f  xor     esi, esi
0x180011a21  test    eax, eax
0x180011a23  js      loc_180011E51
0x180011a29  mov     ebx, esi
0x180011a2b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180011a32  cmp     ebx, 4
0x180011a35  jnb     loc_180011E4C
0x180011a3b  movsxd  rdi, ebx
0x180011a3e  lea     rcx, [rbp+20B0h+String1]; lpString1
0x180011a42  add     rdi, rdi
0x180011a45  mov     rdx, [rax+rdi*8]; lpString2
0x180011a49  call    cs:__imp_lstrcmpiW
0x180011a4f  test    eax, eax
0x180011a51  jz      short loc_180011A57
0x180011a53  inc     ebx
0x180011a55  jmp     short loc_180011A2B
0x180011a57  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180011a5e  mov     rcx, r14; this
0x180011a61  movzx   ebx, word ptr [rbx+rdi*8+8]
0x180011a66  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180011a6b  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180011a6f  mov     rcx, r14; this
0x180011a72  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180011a77  test    eax, eax
0x180011a79  js      loc_180011E51
0x180011a7f  mov     eax, 8
0x180011a84  cmp     bx, ax
0x180011a87  jz      loc_180011DEC
0x180011a8d  cmp     bx, 11h
0x180011a91  jz      loc_180011C4C
0x180011a97  cmp     bx, 13h
0x180011a9b  jz      loc_180011BD7
0x180011aa1  mov     eax, 4008h
0x180011aa6  cmp     bx, ax
0x180011aa9  jnz     loc_180011E36
0x180011aaf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011ab3  lea     rcx, [rbp+20B0h+String1]
0x180011ab7  mov     rax, rdi
0x180011aba  inc     rax
0x180011abd  cmp     [rcx+rax*2], si
0x180011ac1  jnz     short loc_180011ABA
0x180011ac3  add     eax, 2
0x180011ac6  mov     [rsp+21B0h+var_2160], rsi
0x180011acb  mov     r14d, 2
0x180011ad1  movsxd  rcx, eax
0x180011ad4  mov     edx, r14d
0x180011ad7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180011adc  cmp     rax, 100h
0x180011ae2  jbe     short loc_180011AF8
0x180011ae4  mov     rdx, rax
0x180011ae7  lea     rcx, [rsp+21B0h+var_2160]
0x180011aec  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180011af1  mov     rbx, [rsp+21B0h+var_2160]
0x180011af6  jmp     short loc_180011B02
0x180011af8  lea     rbx, [rsp+21B0h+var_2158]
0x180011afd  mov     [rsp+21B0h+var_2160], rbx
0x180011b02  test    rbx, rbx
0x180011b05  jz      loc_180011BBE
0x180011b0b  xor     eax, eax
0x180011b0d  lea     rsi, [rbp+20B0h+String1]
0x180011b11  cmp     [rbp+20B0h+String1], ax
0x180011b15  jz      short loc_180011B61
0x180011b17  lea     r15d, [rax+30h]
0x180011b1b  xor     r12d, r12d
0x180011b1e  mov     rcx, rsi; lpsz
0x180011b21  call    cs:__imp_CharNextW
0x180011b27  movzx   ecx, word ptr [rsi]
0x180011b2a  cmp     cx, 5Ch ; '\'
0x180011b2e  jnz     short loc_180011B48
0x180011b30  cmp     [rax], r15w
0x180011b34  jnz     short loc_180011B48
0x180011b36  mov     rcx, rax; lpsz
0x180011b39  mov     [rbx], r12w
0x180011b3d  call    cs:__imp_CharNextW
0x180011b43  mov     rsi, rax
0x180011b46  jmp     short loc_180011B4E
0x180011b48  mov     [rbx], cx
0x180011b4b  add     rsi, r14
0x180011b4e  add     rbx, r14
0x180011b51  cmp     [rsi], r12w
0x180011b55  jnz     short loc_180011B1E
0x180011b57  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x180011b5c  mov     r15, [rsp+21B0h+var_2180]
0x180011b61  xor     esi, esi
0x180011b63  mov     [rbx], esi
0x180011b65  mov     r8, [rsp+21B0h+var_2160]
0x180011b6a  test    r8, r8
0x180011b6d  jz      short loc_180011BB3
0x180011b6f  mov     r10d, esi
0x180011b72  mov     r9, r8
0x180011b75  mov     rcx, rdi
0x180011b78  inc     rcx
0x180011b7b  cmp     [r9+rcx*2], si
0x180011b80  jnz     short loc_180011B78
0x180011b82  inc     ecx
0x180011b84  lea     r9, [r9+rcx*2]
0x180011b88  lea     r10d, [r10+rcx*2]
0x180011b8c  cmp     ecx, 1
0x180011b8f  jnz     short loc_180011B75
0x180011b91  mov     [rsp+21B0h+cbData], r10d; cbData
0x180011b96  lea     r9d, [rcx+6]; dwType
0x180011b9a  mov     rcx, [r12]; hKey
0x180011b9e  mov     rdx, r13; lpValueName
0x180011ba1  mov     [rsp+21B0h+lpData], r8; lpData
0x180011ba6  xor     r8d, r8d; Reserved
0x180011ba9  call    cs:__imp_RegSetValueExW
0x180011baf  mov     ebx, eax
0x180011bb1  jmp     short loc_180011BC3
0x180011bb3  mov     ecx, 80004005h; int
0x180011bb8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011bbe  mov     ebx, 0Eh
0x180011bc3  lea     rcx, [rsp+21B0h+var_2160]
0x180011bc8  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180011bcd  mov     r14, qword ptr [rsp+21B0h+Data]
0x180011bd2  jmp     loc_180011E29
0x180011bd7  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x180011bdc  mov     [rsp+21B0h+pulOut], esi
0x180011be0  xor     r8d, r8d; dwFlags
0x180011be3  mov     [rsp+21B0h+var_2180], rsi
0x180011be8  xor     edx, edx; lcid
0x180011bea  lea     rcx, [rbp+20B0h+String1]; strIn
0x180011bee  call    cs:__imp_VarUI4FromStr
0x180011bf4  mov     ebx, eax
0x180011bf6  test    eax, eax
0x180011bf8  jns     short loc_180011C0B
0x180011bfa  lea     rcx, [rsp+21B0h+var_2180]
0x180011bff  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011c04  mov     eax, ebx
0x180011c06  jmp     loc_180011E51
0x180011c0b  mov     eax, [rsp+21B0h+pulOut]
0x180011c0f  mov     r9d, 4; dwType
0x180011c15  mov     rcx, [r12]; hKey
0x180011c19  xor     r8d, r8d; Reserved
0x180011c1c  mov     dword ptr [rsp+21B0h+Data], eax
0x180011c20  mov     rdx, r13; lpValueName
0x180011c23  lea     rax, [rsp+21B0h+Data]
0x180011c28  mov     [rsp+21B0h+cbData], 4; cbData
0x180011c30  mov     [rsp+21B0h+lpData], rax; lpData
0x180011c35  call    cs:__imp_RegSetValueExW
0x180011c3b  lea     rcx, [rsp+21B0h+var_2180]
0x180011c40  mov     ebx, eax
0x180011c42  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011c47  jmp     loc_180011E29
0x180011c4c  lea     rax, [rbp+20B0h+String1]
0x180011c50  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011c54  inc     rdi
0x180011c57  cmp     [rax+rdi*2], si
0x180011c5b  jnz     short loc_180011C54
0x180011c5d  test    dil, 1
0x180011c61  jz      short loc_180011C6D
0x180011c63  mov     eax, 80004005h
0x180011c68  jmp     loc_180011E51
0x180011c6d  mov     eax, edi
0x180011c6f  mov     r14d, 2
0x180011c75  cdq
0x180011c76  idiv    r14d
0x180011c79  xor     r14d, r14d
0x180011c7c  movsxd  rsi, eax
0x180011c7f  mov     rcx, rsi
0x180011c82  mov     [rsp+21B0h+var_2160], r14
0x180011c87  lea     edx, [r14+1]
0x180011c8b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180011c90  cmp     rax, 100h
0x180011c96  jbe     short loc_180011CAC
0x180011c98  mov     rdx, rax
0x180011c9b  lea     rcx, [rsp+21B0h+var_2160]
0x180011ca0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180011ca5  mov     rcx, [rsp+21B0h+var_2160]
0x180011caa  jmp     short loc_180011CB6
0x180011cac  lea     rcx, [rsp+21B0h+var_2158]; void *
0x180011cb1  mov     [rsp+21B0h+var_2160], rcx
0x180011cb6  test    rcx, rcx
0x180011cb9  jnz     short loc_180011CC7
0x180011cbb  lea     rcx, [rsp+21B0h+var_2160]
0x180011cc0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180011cc5  jmp     short loc_180011C63
0x180011cc7  mov     r8, rsi; Size
0x180011cca  xor     edx, edx; Val
0x180011ccc  call    memset_0
0x180011cd1  mov     r10d, r14d
0x180011cd4  test    edi, edi
0x180011cd6  jle     loc_180011DB3
0x180011cdc  mov     r15d, 30h ; '0'
0x180011ce2  mov     eax, r10d
0x180011ce5  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x180011ceb  cmp     r9d, 61h ; 'a'
0x180011cef  ja      short loc_180011D5B
0x180011cf1  jz      loc_180011D7C
0x180011cf7  cmp     r9d, 38h ; '8'
0x180011cfb  ja      short loc_180011D2F
0x180011cfd  jz      short loc_180011D2A
0x180011cff  mov     ecx, r9d
0x180011d02  sub     ecx, r15d
0x180011d05  jz      short loc_180011D2A
0x180011d07  sub     ecx, 1
0x180011d0a  jz      short loc_180011D2A
0x180011d0c  sub     ecx, 1
0x180011d0f  jz      short loc_180011D2A
0x180011d11  sub     ecx, 1
0x180011d14  jz      short loc_180011D2A
0x180011d16  sub     ecx, 1
0x180011d19  jz      short loc_180011D2A
0x180011d1b  sub     ecx, 1
0x180011d1e  jz      short loc_180011D2A
0x180011d20  sub     ecx, 1
0x180011d23  jz      short loc_180011D2A
0x180011d25  cmp     ecx, 1
0x180011d28  jnz     short loc_180011D77
0x180011d2a  sub     r9b, r15b
0x180011d2d  jmp     short loc_180011D80
0x180011d2f  mov     ecx, r9d
0x180011d32  sub     ecx, 39h ; '9'
0x180011d35  jz      short loc_180011D2A
0x180011d37  sub     ecx, 8
0x180011d3a  jz      short loc_180011D55
0x180011d3c  sub     ecx, 1
0x180011d3f  jz      short loc_180011D55
0x180011d41  sub     ecx, 1
0x180011d44  jz      short loc_180011D55
0x180011d46  sub     ecx, 1
0x180011d49  jz      short loc_180011D55
0x180011d4b  sub     ecx, 1
0x180011d4e  jz      short loc_180011D55
0x180011d50  cmp     ecx, 1
0x180011d53  jnz     short loc_180011D77
0x180011d55  sub     r9b, 37h ; '7'
0x180011d59  jmp     short loc_180011D80
0x180011d5b  mov     ecx, r9d
0x180011d5e  sub     ecx, 62h ; 'b'
0x180011d61  jz      short loc_180011D7C
0x180011d63  sub     ecx, 1
0x180011d66  jz      short loc_180011D7C
0x180011d68  sub     ecx, 1
0x180011d6b  jz      short loc_180011D7C
0x180011d6d  sub     ecx, 1
0x180011d70  jz      short loc_180011D7C
0x180011d72  cmp     ecx, 1
0x180011d75  jz      short loc_180011D7C
0x180011d77  mov     r9b, r14b
0x180011d7a  jmp     short loc_180011D80
0x180011d7c  sub     r9b, 57h ; 'W'
0x180011d80  mov     rdx, [rsp+21B0h+var_2160]
0x180011d85  mov     eax, r10d
0x180011d88  and     eax, 1
0x180011d8b  mov     r8d, r10d
0x180011d8e  shl     eax, 2
0x180011d91  mov     ecx, 4
0x180011d96  shr     r8, 1
0x180011d99  sub     ecx, eax
0x180011d9b  shl     r9b, cl
0x180011d9e  inc     r10d
0x180011da1  or      [r8+rdx], r9b
0x180011da5  cmp     r10d, edi
0x180011da8  jl      loc_180011CE2
0x180011dae  mov     r15, [rsp+21B0h+var_2180]
0x180011db3  mov     rax, [rsp+21B0h+var_2160]
0x180011db8  mov     r9d, 3; dwType
0x180011dbe  mov     rcx, [r12]; hKey
0x180011dc2  xor     r8d, r8d; Reserved
0x180011dc5  mov     [rsp+21B0h+cbData], esi; cbData
0x180011dc9  mov     rdx, r13; lpValueName
0x180011dcc  mov     [rsp+21B0h+lpData], rax; lpData
0x180011dd1  call    cs:__imp_RegSetValueExW
0x180011dd7  lea     rcx, [rsp+21B0h+var_2160]
0x180011ddc  mov     ebx, eax
0x180011dde  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180011de3  mov     r14, qword ptr [rsp+21B0h+Data]
0x180011de8  xor     esi, esi
0x180011dea  jmp     short loc_180011E29
0x180011dec  lea     rax, [rbp+20B0h+String1]
0x180011df0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011df4  inc     rdi
0x180011df7  cmp     [rax+rdi*2], si
0x180011dfb  jnz     short loc_180011DF4
0x180011dfd  mov     rcx, [r12]; hKey
0x180011e01  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
