# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1400099b0`
- end: `0x140009e5c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x14000bf0c`

## callees

- `0x140004703`
- `0x140009420`
- `0x1400095c0`
- `0x140009614`
- `0x1400099b0`
- `0x140009e64`
- `0x140009fe4`
- `0x14000a670`
- `0x14000add4`
- `0x14000c8bc`
- `0x140111220`
- `0x1401112e0`

## import_xrefs

- `USER32!CharNextW` at `0x140009b09`
- `USER32!CharNextW` at `0x140009b25`
- `USER32!CharNextW` at `0x140009b09`
- `USER32!CharNextW` at `0x140009b25`
- `KERNEL32!lstrcmpiW` at `0x140009a31`
- `KERNEL32!lstrcmpiW` at `0x140009a31`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140009bd6`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x140009bd6`
- `ADVAPI32!RegSetValueExW` at `0x140009b91`
- `ADVAPI32!RegSetValueExW` at `0x140009c1d`
- `ADVAPI32!RegSetValueExW` at `0x140009db9`
- `ADVAPI32!RegSetValueExW` at `0x140009e09`
- `ADVAPI32!RegSetValueExW` at `0x140009b91`
- `ADVAPI32!RegSetValueExW` at `0x140009c1d`
- `ADVAPI32!RegSetValueExW` at `0x140009db9`
- `ADVAPI32!RegSetValueExW` at `0x140009e09`

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
0x1400099b0  push    rbp
0x1400099b2  push    rbx
0x1400099b3  push    rsi
0x1400099b4  push    rdi
0x1400099b5  push    r12
0x1400099b7  push    r13
0x1400099b9  push    r14
0x1400099bb  push    r15
0x1400099bd  lea     rbp, [rsp-2078h]
0x1400099c5  mov     eax, 2178h
0x1400099ca  call    _alloca_probe
0x1400099cf  sub     rsp, rax
0x1400099d2  mov     rax, cs:__security_cookie
0x1400099d9  xor     rax, rsp
0x1400099dc  mov     [rbp+20B0h+var_50], rax
0x1400099e3  mov     r12, rdx
0x1400099e6  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x1400099eb  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x1400099ef  mov     [rsp+21B0h+var_2180], r9
0x1400099f4  mov     r15, r9
0x1400099f7  mov     qword ptr [rsp+21B0h+Data], rcx
0x1400099fc  mov     r13, r8
0x1400099ff  mov     r14, rcx
0x140009a02  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009a07  xor     esi, esi
0x140009a09  test    eax, eax
0x140009a0b  js      loc_140009E39
0x140009a11  mov     ebx, esi
0x140009a13  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140009a1a  cmp     ebx, 4
0x140009a1d  jnb     loc_140009E34
0x140009a23  movsxd  rdi, ebx
0x140009a26  lea     rcx, [rbp+20B0h+String1]; lpString1
0x140009a2a  add     rdi, rdi
0x140009a2d  mov     rdx, [rax+rdi*8]; lpString2
0x140009a31  call    cs:__imp_lstrcmpiW
0x140009a37  test    eax, eax
0x140009a39  jz      short loc_140009A3F
0x140009a3b  inc     ebx
0x140009a3d  jmp     short loc_140009A13
0x140009a3f  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x140009a46  mov     rcx, r14; this
0x140009a49  movzx   ebx, word ptr [rbx+rdi*8+8]
0x140009a4e  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x140009a53  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x140009a57  mov     rcx, r14; this
0x140009a5a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x140009a5f  test    eax, eax
0x140009a61  js      loc_140009E39
0x140009a67  mov     eax, 8
0x140009a6c  cmp     bx, ax
0x140009a6f  jz      loc_140009DD4
0x140009a75  cmp     bx, 11h
0x140009a79  jz      loc_140009C34
0x140009a7f  cmp     bx, 13h
0x140009a83  jz      loc_140009BBF
0x140009a89  mov     eax, 4008h
0x140009a8e  cmp     bx, ax
0x140009a91  jnz     loc_140009E1E
0x140009a97  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009a9b  lea     rcx, [rbp+20B0h+String1]
0x140009a9f  mov     rax, rdi
0x140009aa2  inc     rax
0x140009aa5  cmp     [rcx+rax*2], si
0x140009aa9  jnz     short loc_140009AA2
0x140009aab  add     eax, 2
0x140009aae  mov     [rsp+21B0h+var_2160], rsi
0x140009ab3  mov     r14d, 2
0x140009ab9  movsxd  rcx, eax
0x140009abc  mov     edx, r14d
0x140009abf  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140009ac4  cmp     rax, 100h
0x140009aca  jbe     short loc_140009AE0
0x140009acc  mov     rdx, rax
0x140009acf  lea     rcx, [rsp+21B0h+var_2160]
0x140009ad4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140009ad9  mov     rbx, [rsp+21B0h+var_2160]
0x140009ade  jmp     short loc_140009AEA
0x140009ae0  lea     rbx, [rsp+21B0h+var_2158]
0x140009ae5  mov     [rsp+21B0h+var_2160], rbx
0x140009aea  test    rbx, rbx
0x140009aed  jz      loc_140009BA6
0x140009af3  xor     eax, eax
0x140009af5  lea     rsi, [rbp+20B0h+String1]
0x140009af9  cmp     [rbp+20B0h+String1], ax
0x140009afd  jz      short loc_140009B49
0x140009aff  lea     r15d, [rax+30h]
0x140009b03  xor     r12d, r12d
0x140009b06  mov     rcx, rsi; lpsz
0x140009b09  call    cs:__imp_CharNextW
0x140009b0f  movzx   ecx, word ptr [rsi]
0x140009b12  cmp     cx, 5Ch ; '\'
0x140009b16  jnz     short loc_140009B30
0x140009b18  cmp     [rax], r15w
0x140009b1c  jnz     short loc_140009B30
0x140009b1e  mov     rcx, rax; lpsz
0x140009b21  mov     [rbx], r12w
0x140009b25  call    cs:__imp_CharNextW
0x140009b2b  mov     rsi, rax
0x140009b2e  jmp     short loc_140009B36
0x140009b30  mov     [rbx], cx
0x140009b33  add     rsi, r14
0x140009b36  add     rbx, r14
0x140009b39  cmp     [rsi], r12w
0x140009b3d  jnz     short loc_140009B06
0x140009b3f  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x140009b44  mov     r15, [rsp+21B0h+var_2180]
0x140009b49  xor     esi, esi
0x140009b4b  mov     [rbx], esi
0x140009b4d  mov     r8, [rsp+21B0h+var_2160]
0x140009b52  test    r8, r8
0x140009b55  jz      short loc_140009B9B
0x140009b57  mov     r10d, esi
0x140009b5a  mov     r9, r8
0x140009b5d  mov     rcx, rdi
0x140009b60  inc     rcx
0x140009b63  cmp     [r9+rcx*2], si
0x140009b68  jnz     short loc_140009B60
0x140009b6a  inc     ecx
0x140009b6c  lea     r9, [r9+rcx*2]
0x140009b70  lea     r10d, [r10+rcx*2]
0x140009b74  cmp     ecx, 1
0x140009b77  jnz     short loc_140009B5D
0x140009b79  mov     [rsp+21B0h+cbData], r10d; cbData
0x140009b7e  lea     r9d, [rcx+6]; dwType
0x140009b82  mov     rcx, [r12]; hKey
0x140009b86  mov     rdx, r13; lpValueName
0x140009b89  mov     [rsp+21B0h+lpData], r8; lpData
0x140009b8e  xor     r8d, r8d; Reserved
0x140009b91  call    cs:__imp_RegSetValueExW
0x140009b97  mov     ebx, eax
0x140009b99  jmp     short loc_140009BAB
0x140009b9b  mov     ecx, 80004005h; int
0x140009ba0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x140009ba6  mov     ebx, 0Eh
0x140009bab  lea     rcx, [rsp+21B0h+var_2160]
0x140009bb0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140009bb5  mov     r14, qword ptr [rsp+21B0h+Data]
0x140009bba  jmp     loc_140009E11
0x140009bbf  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x140009bc4  mov     [rsp+21B0h+pulOut], esi
0x140009bc8  xor     r8d, r8d; dwFlags
0x140009bcb  mov     [rsp+21B0h+var_2180], rsi
0x140009bd0  xor     edx, edx; lcid
0x140009bd2  lea     rcx, [rbp+20B0h+String1]; strIn
0x140009bd6  call    cs:__imp_VarUI4FromStr
0x140009bdc  mov     ebx, eax
0x140009bde  test    eax, eax
0x140009be0  jns     short loc_140009BF3
0x140009be2  lea     rcx, [rsp+21B0h+var_2180]
0x140009be7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140009bec  mov     eax, ebx
0x140009bee  jmp     loc_140009E39
0x140009bf3  mov     eax, [rsp+21B0h+pulOut]
0x140009bf7  mov     r9d, 4; dwType
0x140009bfd  mov     rcx, [r12]; hKey
0x140009c01  xor     r8d, r8d; Reserved
0x140009c04  mov     dword ptr [rsp+21B0h+Data], eax
0x140009c08  mov     rdx, r13; lpValueName
0x140009c0b  lea     rax, [rsp+21B0h+Data]
0x140009c10  mov     [rsp+21B0h+cbData], 4; cbData
0x140009c18  mov     [rsp+21B0h+lpData], rax; lpData
0x140009c1d  call    cs:__imp_RegSetValueExW
0x140009c23  lea     rcx, [rsp+21B0h+var_2180]
0x140009c28  mov     ebx, eax
0x140009c2a  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140009c2f  jmp     loc_140009E11
0x140009c34  lea     rax, [rbp+20B0h+String1]
0x140009c38  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009c3c  inc     rdi
0x140009c3f  cmp     [rax+rdi*2], si
0x140009c43  jnz     short loc_140009C3C
0x140009c45  test    dil, 1
0x140009c49  jz      short loc_140009C55
0x140009c4b  mov     eax, 80004005h
0x140009c50  jmp     loc_140009E39
0x140009c55  mov     eax, edi
0x140009c57  mov     r14d, 2
0x140009c5d  cdq
0x140009c5e  idiv    r14d
0x140009c61  xor     r14d, r14d
0x140009c64  movsxd  rsi, eax
0x140009c67  mov     rcx, rsi
0x140009c6a  mov     [rsp+21B0h+var_2160], r14
0x140009c6f  lea     edx, [r14+1]
0x140009c73  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140009c78  cmp     rax, 100h
0x140009c7e  jbe     short loc_140009C94
0x140009c80  mov     rdx, rax
0x140009c83  lea     rcx, [rsp+21B0h+var_2160]
0x140009c88  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140009c8d  mov     rcx, [rsp+21B0h+var_2160]
0x140009c92  jmp     short loc_140009C9E
0x140009c94  lea     rcx, [rsp+21B0h+var_2158]; void *
0x140009c99  mov     [rsp+21B0h+var_2160], rcx
0x140009c9e  test    rcx, rcx
0x140009ca1  jnz     short loc_140009CAF
0x140009ca3  lea     rcx, [rsp+21B0h+var_2160]
0x140009ca8  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140009cad  jmp     short loc_140009C4B
0x140009caf  mov     r8, rsi; Size
0x140009cb2  xor     edx, edx; Val
0x140009cb4  call    memset_0
0x140009cb9  mov     r10d, r14d
0x140009cbc  test    edi, edi
0x140009cbe  jle     loc_140009D9B
0x140009cc4  mov     r15d, 30h ; '0'
0x140009cca  mov     eax, r10d
0x140009ccd  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x140009cd3  cmp     r9d, 61h ; 'a'
0x140009cd7  ja      short loc_140009D43
0x140009cd9  jz      loc_140009D64
0x140009cdf  cmp     r9d, 38h ; '8'
0x140009ce3  ja      short loc_140009D17
0x140009ce5  jz      short loc_140009D12
0x140009ce7  mov     ecx, r9d
0x140009cea  sub     ecx, r15d
0x140009ced  jz      short loc_140009D12
0x140009cef  sub     ecx, 1
0x140009cf2  jz      short loc_140009D12
0x140009cf4  sub     ecx, 1
0x140009cf7  jz      short loc_140009D12
0x140009cf9  sub     ecx, 1
0x140009cfc  jz      short loc_140009D12
0x140009cfe  sub     ecx, 1
0x140009d01  jz      short loc_140009D12
0x140009d03  sub     ecx, 1
0x140009d06  jz      short loc_140009D12
0x140009d08  sub     ecx, 1
0x140009d0b  jz      short loc_140009D12
0x140009d0d  cmp     ecx, 1
0x140009d10  jnz     short loc_140009D5F
0x140009d12  sub     r9b, r15b
0x140009d15  jmp     short loc_140009D68
0x140009d17  mov     ecx, r9d
0x140009d1a  sub     ecx, 39h ; '9'
0x140009d1d  jz      short loc_140009D12
0x140009d1f  sub     ecx, 8
0x140009d22  jz      short loc_140009D3D
0x140009d24  sub     ecx, 1
0x140009d27  jz      short loc_140009D3D
0x140009d29  sub     ecx, 1
0x140009d2c  jz      short loc_140009D3D
0x140009d2e  sub     ecx, 1
0x140009d31  jz      short loc_140009D3D
0x140009d33  sub     ecx, 1
0x140009d36  jz      short loc_140009D3D
0x140009d38  cmp     ecx, 1
0x140009d3b  jnz     short loc_140009D5F
0x140009d3d  sub     r9b, 37h ; '7'
0x140009d41  jmp     short loc_140009D68
0x140009d43  mov     ecx, r9d
0x140009d46  sub     ecx, 62h ; 'b'
0x140009d49  jz      short loc_140009D64
0x140009d4b  sub     ecx, 1
0x140009d4e  jz      short loc_140009D64
0x140009d50  sub     ecx, 1
0x140009d53  jz      short loc_140009D64
0x140009d55  sub     ecx, 1
0x140009d58  jz      short loc_140009D64
0x140009d5a  cmp     ecx, 1
0x140009d5d  jz      short loc_140009D64
0x140009d5f  mov     r9b, r14b
0x140009d62  jmp     short loc_140009D68
0x140009d64  sub     r9b, 57h ; 'W'
0x140009d68  mov     rdx, [rsp+21B0h+var_2160]
0x140009d6d  mov     eax, r10d
0x140009d70  and     eax, 1
0x140009d73  mov     r8d, r10d
0x140009d76  shl     eax, 2
0x140009d79  mov     ecx, 4
0x140009d7e  shr     r8, 1
0x140009d81  sub     ecx, eax
0x140009d83  shl     r9b, cl
0x140009d86  inc     r10d
0x140009d89  or      [r8+rdx], r9b
0x140009d8d  cmp     r10d, edi
0x140009d90  jl      loc_140009CCA
0x140009d96  mov     r15, [rsp+21B0h+var_2180]
0x140009d9b  mov     rax, [rsp+21B0h+var_2160]
0x140009da0  mov     r9d, 3; dwType
0x140009da6  mov     rcx, [r12]; hKey
0x140009daa  xor     r8d, r8d; Reserved
0x140009dad  mov     [rsp+21B0h+cbData], esi; cbData
0x140009db1  mov     rdx, r13; lpValueName
0x140009db4  mov     [rsp+21B0h+lpData], rax; lpData
0x140009db9  call    cs:__imp_RegSetValueExW
0x140009dbf  lea     rcx, [rsp+21B0h+var_2160]
0x140009dc4  mov     ebx, eax
0x140009dc6  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140009dcb  mov     r14, qword ptr [rsp+21B0h+Data]
0x140009dd0  xor     esi, esi
0x140009dd2  jmp     short loc_140009E11
0x140009dd4  lea     rax, [rbp+20B0h+String1]
0x140009dd8  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140009ddc  inc     rdi
0x140009ddf  cmp     [rax+rdi*2], si
0x140009de3  jnz     short loc_140009DDC
0x140009de5  mov     rcx, [r12]; hKey
0x140009de9  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
