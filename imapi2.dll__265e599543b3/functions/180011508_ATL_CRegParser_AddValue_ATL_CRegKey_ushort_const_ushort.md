# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180011508`
- end: `0x1800119b4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1196`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180013134`

## callees

- `0x180010f5c`
- `0x180011024`
- `0x1800110e8`
- `0x180011508`
- `0x1800119bc`
- `0x180011b34`
- `0x180011b4c`
- `0x180012760`
- `0x180013980`
- `0x18004984a`
- `0x180049880`
- `0x180049940`

## import_xrefs

- `USER32!CharNextW` at `0x180011661`
- `USER32!CharNextW` at `0x18001167d`
- `USER32!CharNextW` at `0x180011661`
- `USER32!CharNextW` at `0x18001167d`
- `ADVAPI32!RegSetValueExW` at `0x1800116e9`
- `ADVAPI32!RegSetValueExW` at `0x180011775`
- `ADVAPI32!RegSetValueExW` at `0x180011911`
- `ADVAPI32!RegSetValueExW` at `0x180011961`
- `ADVAPI32!RegSetValueExW` at `0x1800116e9`
- `ADVAPI32!RegSetValueExW` at `0x180011775`
- `ADVAPI32!RegSetValueExW` at `0x180011911`
- `ADVAPI32!RegSetValueExW` at `0x180011961`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001172e`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18001172e`
- `KERNEL32!lstrcmpiW` at `0x180011589`
- `KERNEL32!lstrcmpiW` at `0x180011589`

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
0x180011508  push    rbp
0x18001150a  push    rbx
0x18001150b  push    rsi
0x18001150c  push    rdi
0x18001150d  push    r12
0x18001150f  push    r13
0x180011511  push    r14
0x180011513  push    r15
0x180011515  lea     rbp, [rsp-2078h]
0x18001151d  mov     eax, 2178h
0x180011522  call    _alloca_probe
0x180011527  sub     rsp, rax
0x18001152a  mov     rax, cs:__security_cookie
0x180011531  xor     rax, rsp
0x180011534  mov     [rbp+20B0h+var_50], rax
0x18001153b  mov     r12, rdx
0x18001153e  mov     qword ptr [rsp+21B0h+pulOut], rdx
0x180011543  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x180011547  mov     [rsp+21B0h+var_2180], r9
0x18001154c  mov     r15, r9
0x18001154f  mov     qword ptr [rsp+21B0h+Data], rcx
0x180011554  mov     r13, r8
0x180011557  mov     r14, rcx
0x18001155a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18001155f  xor     esi, esi
0x180011561  test    eax, eax
0x180011563  js      loc_180011991
0x180011569  mov     ebx, esi
0x18001156b  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180011572  cmp     ebx, 4
0x180011575  jnb     loc_18001198C
0x18001157b  movsxd  rdi, ebx
0x18001157e  lea     rcx, [rbp+20B0h+String1]; lpString1
0x180011582  add     rdi, rdi
0x180011585  mov     rdx, [rax+rdi*8]; lpString2
0x180011589  call    cs:__imp_lstrcmpiW
0x18001158f  test    eax, eax
0x180011591  jz      short loc_180011597
0x180011593  inc     ebx
0x180011595  jmp     short loc_18001156B
0x180011597  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18001159e  mov     rcx, r14; this
0x1800115a1  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800115a6  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1800115ab  lea     rdx, [rbp+20B0h+String1]; unsigned __int16 *
0x1800115af  mov     rcx, r14; this
0x1800115b2  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800115b7  test    eax, eax
0x1800115b9  js      loc_180011991
0x1800115bf  mov     eax, 8
0x1800115c4  cmp     bx, ax
0x1800115c7  jz      loc_18001192C
0x1800115cd  cmp     bx, 11h
0x1800115d1  jz      loc_18001178C
0x1800115d7  cmp     bx, 13h
0x1800115db  jz      loc_180011717
0x1800115e1  mov     eax, 4008h
0x1800115e6  cmp     bx, ax
0x1800115e9  jnz     loc_180011976
0x1800115ef  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800115f3  lea     rcx, [rbp+20B0h+String1]
0x1800115f7  mov     rax, rdi
0x1800115fa  inc     rax
0x1800115fd  cmp     [rcx+rax*2], si
0x180011601  jnz     short loc_1800115FA
0x180011603  add     eax, 2
0x180011606  mov     [rsp+21B0h+var_2160], rsi
0x18001160b  mov     r14d, 2
0x180011611  movsxd  rcx, eax
0x180011614  mov     edx, r14d
0x180011617  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001161c  cmp     rax, 100h
0x180011622  jbe     short loc_180011638
0x180011624  mov     rdx, rax
0x180011627  lea     rcx, [rsp+21B0h+var_2160]
0x18001162c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180011631  mov     rbx, [rsp+21B0h+var_2160]
0x180011636  jmp     short loc_180011642
0x180011638  lea     rbx, [rsp+21B0h+var_2158]
0x18001163d  mov     [rsp+21B0h+var_2160], rbx
0x180011642  test    rbx, rbx
0x180011645  jz      loc_1800116FE
0x18001164b  xor     eax, eax
0x18001164d  lea     rsi, [rbp+20B0h+String1]
0x180011651  cmp     [rbp+20B0h+String1], ax
0x180011655  jz      short loc_1800116A1
0x180011657  lea     r15d, [rax+30h]
0x18001165b  xor     r12d, r12d
0x18001165e  mov     rcx, rsi; lpsz
0x180011661  call    cs:__imp_CharNextW
0x180011667  movzx   ecx, word ptr [rsi]
0x18001166a  cmp     cx, 5Ch ; '\'
0x18001166e  jnz     short loc_180011688
0x180011670  cmp     [rax], r15w
0x180011674  jnz     short loc_180011688
0x180011676  mov     rcx, rax; lpsz
0x180011679  mov     [rbx], r12w
0x18001167d  call    cs:__imp_CharNextW
0x180011683  mov     rsi, rax
0x180011686  jmp     short loc_18001168E
0x180011688  mov     [rbx], cx
0x18001168b  add     rsi, r14
0x18001168e  add     rbx, r14
0x180011691  cmp     [rsi], r12w
0x180011695  jnz     short loc_18001165E
0x180011697  mov     r12, qword ptr [rsp+21B0h+pulOut]
0x18001169c  mov     r15, [rsp+21B0h+var_2180]
0x1800116a1  xor     esi, esi
0x1800116a3  mov     [rbx], esi
0x1800116a5  mov     r8, [rsp+21B0h+var_2160]
0x1800116aa  test    r8, r8
0x1800116ad  jz      short loc_1800116F3
0x1800116af  mov     r10d, esi
0x1800116b2  mov     r9, r8
0x1800116b5  mov     rcx, rdi
0x1800116b8  inc     rcx
0x1800116bb  cmp     [r9+rcx*2], si
0x1800116c0  jnz     short loc_1800116B8
0x1800116c2  inc     ecx
0x1800116c4  lea     r9, [r9+rcx*2]
0x1800116c8  lea     r10d, [r10+rcx*2]
0x1800116cc  cmp     ecx, 1
0x1800116cf  jnz     short loc_1800116B5
0x1800116d1  mov     [rsp+21B0h+cbData], r10d; cbData
0x1800116d6  lea     r9d, [rcx+6]; dwType
0x1800116da  mov     rcx, [r12]; hKey
0x1800116de  mov     rdx, r13; lpValueName
0x1800116e1  mov     [rsp+21B0h+lpData], r8; lpData
0x1800116e6  xor     r8d, r8d; Reserved
0x1800116e9  call    cs:__imp_RegSetValueExW
0x1800116ef  mov     ebx, eax
0x1800116f1  jmp     short loc_180011703
0x1800116f3  mov     ecx, 80004005h; int
0x1800116f8  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1800116fe  mov     ebx, 0Eh
0x180011703  lea     rcx, [rsp+21B0h+var_2160]
0x180011708  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001170d  mov     r14, qword ptr [rsp+21B0h+Data]
0x180011712  jmp     loc_180011969
0x180011717  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x18001171c  mov     [rsp+21B0h+pulOut], esi
0x180011720  xor     r8d, r8d; dwFlags
0x180011723  mov     [rsp+21B0h+var_2180], rsi
0x180011728  xor     edx, edx; lcid
0x18001172a  lea     rcx, [rbp+20B0h+String1]; strIn
0x18001172e  call    cs:__imp_VarUI4FromStr
0x180011734  mov     ebx, eax
0x180011736  test    eax, eax
0x180011738  jns     short loc_18001174B
0x18001173a  lea     rcx, [rsp+21B0h+var_2180]
0x18001173f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011744  mov     eax, ebx
0x180011746  jmp     loc_180011991
0x18001174b  mov     eax, [rsp+21B0h+pulOut]
0x18001174f  mov     r9d, 4; dwType
0x180011755  mov     rcx, [r12]; hKey
0x180011759  xor     r8d, r8d; Reserved
0x18001175c  mov     dword ptr [rsp+21B0h+Data], eax
0x180011760  mov     rdx, r13; lpValueName
0x180011763  lea     rax, [rsp+21B0h+Data]
0x180011768  mov     [rsp+21B0h+cbData], 4; cbData
0x180011770  mov     [rsp+21B0h+lpData], rax; lpData
0x180011775  call    cs:__imp_RegSetValueExW
0x18001177b  lea     rcx, [rsp+21B0h+var_2180]
0x180011780  mov     ebx, eax
0x180011782  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180011787  jmp     loc_180011969
0x18001178c  lea     rax, [rbp+20B0h+String1]
0x180011790  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011794  inc     rdi
0x180011797  cmp     [rax+rdi*2], si
0x18001179b  jnz     short loc_180011794
0x18001179d  test    dil, 1
0x1800117a1  jz      short loc_1800117AD
0x1800117a3  mov     eax, 80004005h
0x1800117a8  jmp     loc_180011991
0x1800117ad  mov     eax, edi
0x1800117af  mov     r14d, 2
0x1800117b5  cdq
0x1800117b6  idiv    r14d
0x1800117b9  xor     r14d, r14d
0x1800117bc  movsxd  rsi, eax
0x1800117bf  mov     rcx, rsi
0x1800117c2  mov     [rsp+21B0h+var_2160], r14
0x1800117c7  lea     edx, [r14+1]
0x1800117cb  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800117d0  cmp     rax, 100h
0x1800117d6  jbe     short loc_1800117EC
0x1800117d8  mov     rdx, rax
0x1800117db  lea     rcx, [rsp+21B0h+var_2160]
0x1800117e0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800117e5  mov     rcx, [rsp+21B0h+var_2160]
0x1800117ea  jmp     short loc_1800117F6
0x1800117ec  lea     rcx, [rsp+21B0h+var_2158]; void *
0x1800117f1  mov     [rsp+21B0h+var_2160], rcx
0x1800117f6  test    rcx, rcx
0x1800117f9  jnz     short loc_180011807
0x1800117fb  lea     rcx, [rsp+21B0h+var_2160]
0x180011800  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180011805  jmp     short loc_1800117A3
0x180011807  mov     r8, rsi; Size
0x18001180a  xor     edx, edx; Val
0x18001180c  call    memset_0
0x180011811  mov     r10d, r14d
0x180011814  test    edi, edi
0x180011816  jle     loc_1800118F3
0x18001181c  mov     r15d, 30h ; '0'
0x180011822  mov     eax, r10d
0x180011825  movzx   r9d, [rbp+rax*2+20B0h+String1]
0x18001182b  cmp     r9d, 61h ; 'a'
0x18001182f  ja      short loc_18001189B
0x180011831  jz      loc_1800118BC
0x180011837  cmp     r9d, 38h ; '8'
0x18001183b  ja      short loc_18001186F
0x18001183d  jz      short loc_18001186A
0x18001183f  mov     ecx, r9d
0x180011842  sub     ecx, r15d
0x180011845  jz      short loc_18001186A
0x180011847  sub     ecx, 1
0x18001184a  jz      short loc_18001186A
0x18001184c  sub     ecx, 1
0x18001184f  jz      short loc_18001186A
0x180011851  sub     ecx, 1
0x180011854  jz      short loc_18001186A
0x180011856  sub     ecx, 1
0x180011859  jz      short loc_18001186A
0x18001185b  sub     ecx, 1
0x18001185e  jz      short loc_18001186A
0x180011860  sub     ecx, 1
0x180011863  jz      short loc_18001186A
0x180011865  cmp     ecx, 1
0x180011868  jnz     short loc_1800118B7
0x18001186a  sub     r9b, r15b
0x18001186d  jmp     short loc_1800118C0
0x18001186f  mov     ecx, r9d
0x180011872  sub     ecx, 39h ; '9'
0x180011875  jz      short loc_18001186A
0x180011877  sub     ecx, 8
0x18001187a  jz      short loc_180011895
0x18001187c  sub     ecx, 1
0x18001187f  jz      short loc_180011895
0x180011881  sub     ecx, 1
0x180011884  jz      short loc_180011895
0x180011886  sub     ecx, 1
0x180011889  jz      short loc_180011895
0x18001188b  sub     ecx, 1
0x18001188e  jz      short loc_180011895
0x180011890  cmp     ecx, 1
0x180011893  jnz     short loc_1800118B7
0x180011895  sub     r9b, 37h ; '7'
0x180011899  jmp     short loc_1800118C0
0x18001189b  mov     ecx, r9d
0x18001189e  sub     ecx, 62h ; 'b'
0x1800118a1  jz      short loc_1800118BC
0x1800118a3  sub     ecx, 1
0x1800118a6  jz      short loc_1800118BC
0x1800118a8  sub     ecx, 1
0x1800118ab  jz      short loc_1800118BC
0x1800118ad  sub     ecx, 1
0x1800118b0  jz      short loc_1800118BC
0x1800118b2  cmp     ecx, 1
0x1800118b5  jz      short loc_1800118BC
0x1800118b7  mov     r9b, r14b
0x1800118ba  jmp     short loc_1800118C0
0x1800118bc  sub     r9b, 57h ; 'W'
0x1800118c0  mov     rdx, [rsp+21B0h+var_2160]
0x1800118c5  mov     eax, r10d
0x1800118c8  and     eax, 1
0x1800118cb  mov     r8d, r10d
0x1800118ce  shl     eax, 2
0x1800118d1  mov     ecx, 4
0x1800118d6  shr     r8, 1
0x1800118d9  sub     ecx, eax
0x1800118db  shl     r9b, cl
0x1800118de  inc     r10d
0x1800118e1  or      [r8+rdx], r9b
0x1800118e5  cmp     r10d, edi
0x1800118e8  jl      loc_180011822
0x1800118ee  mov     r15, [rsp+21B0h+var_2180]
0x1800118f3  mov     rax, [rsp+21B0h+var_2160]
0x1800118f8  mov     r9d, 3; dwType
0x1800118fe  mov     rcx, [r12]; hKey
0x180011902  xor     r8d, r8d; Reserved
0x180011905  mov     [rsp+21B0h+cbData], esi; cbData
0x180011909  mov     rdx, r13; lpValueName
0x18001190c  mov     [rsp+21B0h+lpData], rax; lpData
0x180011911  call    cs:__imp_RegSetValueExW
0x180011917  lea     rcx, [rsp+21B0h+var_2160]
0x18001191c  mov     ebx, eax
0x18001191e  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180011923  mov     r14, qword ptr [rsp+21B0h+Data]
0x180011928  xor     esi, esi
0x18001192a  jmp     short loc_180011969
0x18001192c  lea     rax, [rbp+20B0h+String1]
0x180011930  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180011934  inc     rdi
0x180011937  cmp     [rax+rdi*2], si
0x18001193b  jnz     short loc_180011934
0x18001193d  mov     rcx, [r12]; hKey
0x180011941  lea     eax, ds:2[rdi*2]
  ... truncated ...
```
