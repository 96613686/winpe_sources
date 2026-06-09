# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000ea4c`
- end: `0x18000ee3f`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x1800110f4`

## callees

- `0x18000adb0`
- `0x18000e150`
- `0x18000e3bc`
- `0x18000ea4c`
- `0x18000ee48`
- `0x18000f19c`
- `0x18000f91c`
- `0x1800106a0`
- `0x180011910`
- `0x180011a24`
- `0x18002e202`
- `0x18002e230`
- `0x18002e2f0`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000eac6`
- `KERNEL32!lstrcmpiW` at `0x18000eac6`
- `ADVAPI32!RegSetValueExW` at `0x18000ec7a`
- `ADVAPI32!RegSetValueExW` at `0x18000eda3`
- `ADVAPI32!RegSetValueExW` at `0x18000edf3`
- `ADVAPI32!RegSetValueExW` at `0x18000ec7a`
- `ADVAPI32!RegSetValueExW` at `0x18000eda3`
- `ADVAPI32!RegSetValueExW` at `0x18000edf3`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000ec34`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000ec34`
- `USER32!CharNextW` at `0x18000ebb5`
- `USER32!CharNextW` at `0x18000ebd0`
- `USER32!CharNextW` at `0x18000ebb5`
- `USER32!CharNextW` at `0x18000ebd0`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r12
  HKEY *v5; // r15
  ATL::CRegParser *v6; // r13
  __int64 result; // rax
  unsigned int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rdi
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  WCHAR *i; // rsi
  const WCHAR *v15; // rax
  LSTATUS v16; // edi
  HRESULT v17; // edi
  __int64 v18; // rdi
  DWORD cbData; // esi
  size_t v20; // r14
  unsigned __int64 v21; // rax
  BYTE *v22; // rcx
  int j; // r10d
  unsigned __int8 v24; // al
  int v25; // r10d
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-2198h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-2190h] BYREF
  ATL::CRegParser *v32; // [rsp+40h] [rbp-2188h] BYREF
  struct ATL::CRegKey *v33; // [rsp+48h] [rbp-2180h]
  const unsigned __int16 *v34; // [rsp+50h] [rbp-2178h]
  size_t v35; // [rsp+60h] [rbp-2168h]
  unsigned __int16 *v36; // [rsp+68h] [rbp-2160h]
  BYTE *lpData; // [rsp+70h] [rbp-2158h] BYREF
  _BYTE v38[264]; // [rsp+78h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+180h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v32 = this;
  v33 = (struct ATL::CRegKey *)a2;
  v34 = a3;
  v36 = a4;
  result = ATL::CRegParser::NextToken(this, String1);
  v8 = 0;
  if ( (int)result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return 2147614729LL;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    ATL::CRegParser::SkipWhiteSpace(v6);
    result = ATL::CRegParser::NextToken(v6, String1);
    if ( (int)result >= 0 )
    {
      if ( v10 == 8 )
      {
        v28 = -1;
        do
          ++v28;
        while ( String1[v28] );
        v16 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)String1, 2 * v28 + 2);
        goto LABEL_46;
      }
      if ( v10 != 17 )
      {
        if ( v10 == 19 )
        {
          pulOut = 0;
          v32 = 0;
          v17 = VarUI4FromStr(String1, 0, 0, &pulOut);
          if ( v17 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
            return (unsigned int)v17;
          }
          *(_DWORD *)Data = pulOut;
          v16 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v32);
        }
        else
        {
          if ( v10 != 16392 )
          {
LABEL_48:
            Token = ATL::CRegParser::NextToken(v6, v36);
            if ( Token < 0 )
              return (unsigned int)Token;
            return v8;
          }
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
              v13 = v38;
              lpData = v38;
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
            v6 = v32;
            v5 = (HKEY *)v33;
            v4 = v34;
          }
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v15 = CharNextW(i);
              if ( *i == 92 && *v15 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v15);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            v16 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, (const unsigned __int16 *)lpData);
          }
          else
          {
            v16 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_46:
        if ( v16 )
          return ATL::AtlHresultFromWin32(v16);
        goto LABEL_48;
      }
      v18 = -1;
      do
        ++v18;
      while ( String1[v18] );
      *(_DWORD *)Data = v18;
      if ( (v18 & 1) == 0 )
      {
        cbData = (int)v18 / 2;
        lpData = 0;
        v20 = (int)v18 / 2;
        v35 = v20;
        try
        {
          v21 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v21 <= 0x100 )
          {
            v22 = v38;
            lpData = v38;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v21);
            v22 = lpData;
          }
        }
        catch ( ... )
        {
          v8 = 0;
          LODWORD(v18) = *(_DWORD *)Data;
          v22 = lpData;
          v20 = v35;
          v6 = v32;
          v5 = (HKEY *)v33;
          v4 = v34;
          cbData = v35;
        }
        if ( v22 )
        {
          memset_0(v22, 0, v20);
          for ( j = 0; j < (int)v18; j = v25 + 1 )
          {
            v24 = ATL::CRegParser::ChToByte(String1[j]);
            *(_BYTE *)(v27 + v26) |= v24 << (4 - 4 * (v25 & 1));
          }
          v16 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_46;
        }
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
      }
      return 2147500037LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000ea4c  push    rbx
0x18000ea4e  push    rsi
0x18000ea4f  push    rdi
0x18000ea50  push    r12
0x18000ea52  push    r13
0x18000ea54  push    r14
0x18000ea56  push    r15
0x18000ea58  mov     eax, 2190h
0x18000ea5d  call    _alloca_probe
0x18000ea62  sub     rsp, rax
0x18000ea65  mov     rax, cs:__security_cookie
0x18000ea6c  xor     rax, rsp
0x18000ea6f  mov     [rsp+21C8h+var_48], rax
0x18000ea77  mov     r12, r8
0x18000ea7a  mov     r15, rdx
0x18000ea7d  mov     r13, rcx
0x18000ea80  mov     [rsp+21C8h+var_2188], rcx
0x18000ea85  mov     [rsp+21C8h+var_2180], rdx
0x18000ea8a  mov     [rsp+21C8h+var_2178], r8
0x18000ea8f  mov     [rsp+21C8h+var_2160], r9
0x18000ea94  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x18000ea9c  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000eaa1  xor     ebx, ebx
0x18000eaa3  test    eax, eax
0x18000eaa5  js      loc_18000EE1C
0x18000eaab  mov     edi, ebx
0x18000eaad  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000eab4  movsxd  rsi, edi
0x18000eab7  add     rsi, rsi
0x18000eaba  mov     rdx, [r14+rsi*8]; lpString2
0x18000eabe  lea     rcx, [rsp+21C8h+String1]; lpString1
0x18000eac6  call    cs:__imp_lstrcmpiW
0x18000eacc  test    eax, eax
0x18000eace  jz      short loc_18000EAE1
0x18000ead0  inc     edi
0x18000ead2  cmp     edi, 4
0x18000ead5  jb      short loc_18000EAB4
0x18000ead7  mov     eax, 80020009h
0x18000eadc  jmp     loc_18000EE1C
0x18000eae1  movzx   edi, word ptr [r14+rsi*8+8]
0x18000eae7  mov     rcx, r13; this
0x18000eaea  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000eaef  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x18000eaf7  mov     rcx, r13; this
0x18000eafa  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000eaff  test    eax, eax
0x18000eb01  js      loc_18000EE1C
0x18000eb07  cmp     di, 8
0x18000eb0b  jz      loc_18000EDB7
0x18000eb11  cmp     di, 11h
0x18000eb15  jz      loc_18000EC91
0x18000eb1b  cmp     di, 13h
0x18000eb1f  jz      loc_18000EC19
0x18000eb25  mov     eax, 4008h
0x18000eb2a  cmp     di, ax
0x18000eb2d  jnz     loc_18000EE08
0x18000eb33  lea     rax, [rsp+21C8h+String1]
0x18000eb3b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000eb3f  inc     rdi
0x18000eb42  cmp     [rax+rdi*2], bx
0x18000eb46  jnz     short loc_18000EB3F
0x18000eb48  add     edi, 2
0x18000eb4b  mov     [rsp+21C8h+var_2158], rbx
0x18000eb50  movsxd  rcx, edi
0x18000eb53  mov     edx, 2
0x18000eb58  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000eb5d  cmp     rax, 100h
0x18000eb63  jbe     short loc_18000EB79
0x18000eb65  mov     rdx, rax
0x18000eb68  lea     rcx, [rsp+21C8h+var_2158]
0x18000eb6d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000eb72  mov     rdi, [rsp+21C8h+var_2158]
0x18000eb77  jmp     short loc_18000EB83
0x18000eb79  lea     rdi, [rsp+21C8h+var_2150]
0x18000eb7e  mov     [rsp+21C8h+var_2158], rdi
0x18000eb83  jmp     short loc_18000EB9B
0x18000eb85  xor     ebx, ebx
0x18000eb87  mov     rdi, [rsp+21C8h+var_2158]
0x18000eb8c  mov     r13, [rsp+21C8h+var_2188]
0x18000eb91  mov     r15, [rsp+21C8h+var_2180]
0x18000eb96  mov     r12, [rsp+21C8h+var_2178]
0x18000eb9b  test    rdi, rdi
0x18000eb9e  jz      short loc_18000EC05
0x18000eba0  lea     rsi, [rsp+21C8h+String1]
0x18000eba8  cmp     [rsp+21C8h+String1], bx
0x18000ebb0  jz      short loc_18000EBEB
0x18000ebb2  mov     rcx, rsi; lpsz
0x18000ebb5  call    cs:__imp_CharNextW
0x18000ebbb  movzx   ecx, word ptr [rsi]
0x18000ebbe  cmp     cx, 5Ch ; '\'
0x18000ebc2  jnz     short loc_18000EBDB
0x18000ebc4  cmp     word ptr [rax], 30h ; '0'
0x18000ebc8  jnz     short loc_18000EBDB
0x18000ebca  mov     [rdi], bx
0x18000ebcd  mov     rcx, rax; lpsz
0x18000ebd0  call    cs:__imp_CharNextW
0x18000ebd6  mov     rsi, rax
0x18000ebd9  jmp     short loc_18000EBE2
0x18000ebdb  mov     [rdi], cx
0x18000ebde  add     rsi, 2
0x18000ebe2  add     rdi, 2
0x18000ebe6  cmp     [rsi], bx
0x18000ebe9  jnz     short loc_18000EBB2
0x18000ebeb  mov     dword ptr [rdi], 0
0x18000ebf1  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x18000ebf6  mov     rdx, r12; unsigned __int16 *
0x18000ebf9  mov     rcx, r15; this
0x18000ebfc  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x18000ec01  mov     edi, eax
0x18000ec03  jmp     short loc_18000EC0A
0x18000ec05  mov     edi, 0Eh
0x18000ec0a  lea     rcx, [rsp+21C8h+var_2158]
0x18000ec0f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000ec14  jmp     loc_18000EDFB
0x18000ec19  mov     [rsp+21C8h+pulOut], ebx
0x18000ec1d  mov     [rsp+21C8h+var_2188], rbx
0x18000ec22  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x18000ec27  xor     r8d, r8d; dwFlags
0x18000ec2a  xor     edx, edx; lcid
0x18000ec2c  lea     rcx, [rsp+21C8h+String1]; strIn
0x18000ec34  call    cs:__imp_VarUI4FromStr
0x18000ec3a  mov     edi, eax
0x18000ec3c  test    eax, eax
0x18000ec3e  jns     short loc_18000EC51
0x18000ec40  lea     rcx, [rsp+21C8h+var_2188]
0x18000ec45  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ec4a  mov     eax, edi
0x18000ec4c  jmp     loc_18000EE1C
0x18000ec51  mov     eax, [rsp+21C8h+pulOut]
0x18000ec55  mov     dword ptr [rsp+21C8h+Data], eax
0x18000ec59  mov     [rsp+21C8h+cbData], 4; cbData
0x18000ec61  lea     rax, [rsp+21C8h+Data]
0x18000ec66  mov     [rsp+21C8h+lpData], rax; lpData
0x18000ec6b  mov     r9d, 4; dwType
0x18000ec71  xor     r8d, r8d; Reserved
0x18000ec74  mov     rdx, r12; lpValueName
0x18000ec77  mov     rcx, [r15]; hKey
0x18000ec7a  call    cs:__imp_RegSetValueExW
0x18000ec80  mov     edi, eax
0x18000ec82  lea     rcx, [rsp+21C8h+var_2188]
0x18000ec87  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000ec8c  jmp     loc_18000EDFB
0x18000ec91  lea     rax, [rsp+21C8h+String1]
0x18000ec99  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000ec9d  inc     rdi
0x18000eca0  cmp     [rax+rdi*2], bx
0x18000eca4  jnz     short loc_18000EC9D
0x18000eca6  mov     dword ptr [rsp+21C8h+Data], edi
0x18000ecaa  test    dil, 1
0x18000ecae  jz      short loc_18000ECBA
0x18000ecb0  mov     eax, 80004005h
0x18000ecb5  jmp     loc_18000EE1C
0x18000ecba  mov     eax, edi
0x18000ecbc  cdq
0x18000ecbd  sub     eax, edx
0x18000ecbf  sar     eax, 1
0x18000ecc1  movsxd  rsi, eax
0x18000ecc4  mov     [rsp+21C8h+var_2158], rbx
0x18000ecc9  mov     r14, rsi
0x18000eccc  mov     [rsp+21C8h+var_2168], rsi
0x18000ecd1  mov     edx, 1
0x18000ecd6  mov     rcx, rsi
0x18000ecd9  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000ecde  cmp     rax, 100h
0x18000ece4  jbe     short loc_18000ECFA
0x18000ece6  mov     rdx, rax
0x18000ece9  lea     rcx, [rsp+21C8h+var_2158]
0x18000ecee  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000ecf3  mov     rcx, [rsp+21C8h+var_2158]
0x18000ecf8  jmp     short loc_18000ED04
0x18000ecfa  lea     rcx, [rsp+21C8h+var_2150]
0x18000ecff  mov     [rsp+21C8h+var_2158], rcx
0x18000ed04  jmp     short loc_18000ED28
0x18000ed06  xor     ebx, ebx
0x18000ed08  mov     edi, dword ptr [rsp+21C8h+Data]
0x18000ed0c  mov     rcx, [rsp+21C8h+var_2158]; void *
0x18000ed11  mov     r14, [rsp+21C8h+var_2168]
0x18000ed16  mov     r13, [rsp+21C8h+var_2188]
0x18000ed1b  mov     r15, [rsp+21C8h+var_2180]
0x18000ed20  mov     r12, [rsp+21C8h+var_2178]
0x18000ed25  mov     esi, r14d
0x18000ed28  test    rcx, rcx
0x18000ed2b  jnz     short loc_18000ED3C
0x18000ed2d  lea     rcx, [rsp+21C8h+var_2158]
0x18000ed32  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000ed37  jmp     loc_18000ECB0
0x18000ed3c  mov     r8, r14; Size
0x18000ed3f  xor     edx, edx; Val
0x18000ed41  call    memset_0
0x18000ed46  mov     r10d, ebx
0x18000ed49  test    edi, edi
0x18000ed4b  jle     short loc_18000ED86
0x18000ed4d  mov     r9d, r10d
0x18000ed50  shr     r9, 1
0x18000ed53  mov     r8, [rsp+21C8h+var_2158]
0x18000ed58  mov     ecx, r10d
0x18000ed5b  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x18000ed63  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x18000ed68  mov     edx, r10d
0x18000ed6b  and     edx, 1
0x18000ed6e  shl     edx, 2
0x18000ed71  mov     ecx, 4
0x18000ed76  sub     ecx, edx
0x18000ed78  shl     al, cl
0x18000ed7a  or      [r9+r8], al
0x18000ed7e  inc     r10d
0x18000ed81  cmp     r10d, edi
0x18000ed84  jl      short loc_18000ED4D
0x18000ed86  mov     rax, [rsp+21C8h+var_2158]
0x18000ed8b  mov     [rsp+21C8h+cbData], esi; cbData
0x18000ed8f  mov     [rsp+21C8h+lpData], rax; lpData
0x18000ed94  mov     r9d, 3; dwType
0x18000ed9a  xor     r8d, r8d; Reserved
0x18000ed9d  mov     rdx, r12; lpValueName
0x18000eda0  mov     rcx, [r15]; hKey
0x18000eda3  call    cs:__imp_RegSetValueExW
0x18000eda9  mov     edi, eax
0x18000edab  lea     rcx, [rsp+21C8h+var_2158]
0x18000edb0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000edb5  jmp     short loc_18000EDFB
0x18000edb7  lea     rax, [rsp+21C8h+String1]
0x18000edbf  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18000edc3  inc     rdi
0x18000edc6  cmp     [rax+rdi*2], bx
0x18000edca  jnz     short loc_18000EDC3
0x18000edcc  lea     eax, ds:2[rdi*2]
0x18000edd3  mov     [rsp+21C8h+cbData], eax; cbData
0x18000edd7  lea     rax, [rsp+21C8h+String1]
0x18000eddf  mov     [rsp+21C8h+lpData], rax; lpData
0x18000ede4  mov     r9d, 1; dwType
0x18000edea  xor     r8d, r8d; Reserved
0x18000eded  mov     rdx, r12; lpValueName
0x18000edf0  mov     rcx, [r15]; hKey
0x18000edf3  call    cs:__imp_RegSetValueExW
0x18000edf9  mov     edi, eax
0x18000edfb  test    edi, edi
0x18000edfd  jz      short loc_18000EE08
0x18000edff  mov     ecx, edi; unsigned int
0x18000ee01  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000ee06  jmp     short loc_18000EE1C
0x18000ee08  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x18000ee0d  mov     rcx, r13; this
0x18000ee10  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ee15  test    eax, eax
0x18000ee17  cmovs   ebx, eax
0x18000ee1a  mov     eax, ebx
0x18000ee1c  mov     rcx, [rsp+21C8h+var_48]
0x18000ee24  xor     rcx, rsp; StackCookie
0x18000ee27  call    __security_check_cookie
0x18000ee2c  add     rsp, 2190h
0x18000ee33  pop     r15
0x18000ee35  pop     r14
0x18000ee37  pop     r13
0x18000ee39  pop     r12
0x18000ee3b  pop     rdi
0x18000ee3c  pop     rsi
0x18000ee3d  pop     rbx
0x18000ee3e  retn
```
