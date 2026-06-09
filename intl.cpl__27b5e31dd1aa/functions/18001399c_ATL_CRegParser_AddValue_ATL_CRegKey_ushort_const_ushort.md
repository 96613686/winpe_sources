# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18001399c`
- end: `0x180013d8f`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18001646c`

## callees

- `0x180013124`
- `0x180013378`
- `0x180013450`
- `0x18001399c`
- `0x180013d98`
- `0x180014080`
- `0x180014284`
- `0x180015890`
- `0x180016c04`
- `0x180016d04`
- `0x18002a112`
- `0x18002a150`
- `0x18002a210`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013cf3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013d43`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013bca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013cf3`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180013d43`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180013b84`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180013b84`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013b05`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013b20`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013b05`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180013b20`
- `KERNEL32!lstrcmpiW` at `0x180013a16`
- `KERNEL32!lstrcmpiW` at `0x180013a16`

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
0x18001399c  push    rbx
0x18001399e  push    rsi
0x18001399f  push    rdi
0x1800139a0  push    r12
0x1800139a2  push    r13
0x1800139a4  push    r14
0x1800139a6  push    r15
0x1800139a8  mov     eax, 2190h
0x1800139ad  call    _alloca_probe
0x1800139b2  sub     rsp, rax
0x1800139b5  mov     rax, cs:__security_cookie
0x1800139bc  xor     rax, rsp
0x1800139bf  mov     [rsp+21C8h+var_48], rax
0x1800139c7  mov     r12, r8
0x1800139ca  mov     r15, rdx
0x1800139cd  mov     r13, rcx
0x1800139d0  mov     [rsp+21C8h+var_2188], rcx
0x1800139d5  mov     [rsp+21C8h+var_2180], rdx
0x1800139da  mov     [rsp+21C8h+var_2178], r8
0x1800139df  mov     [rsp+21C8h+var_2160], r9
0x1800139e4  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x1800139ec  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800139f1  xor     ebx, ebx
0x1800139f3  test    eax, eax
0x1800139f5  js      loc_180013D6C
0x1800139fb  mov     edi, ebx
0x1800139fd  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180013a04  movsxd  rsi, edi
0x180013a07  add     rsi, rsi
0x180013a0a  mov     rdx, [r14+rsi*8]; lpString2
0x180013a0e  lea     rcx, [rsp+21C8h+String1]; lpString1
0x180013a16  call    cs:__imp_lstrcmpiW
0x180013a1c  test    eax, eax
0x180013a1e  jz      short loc_180013A31
0x180013a20  inc     edi
0x180013a22  cmp     edi, 4
0x180013a25  jb      short loc_180013A04
0x180013a27  mov     eax, 80020009h
0x180013a2c  jmp     loc_180013D6C
0x180013a31  movzx   edi, word ptr [r14+rsi*8+8]
0x180013a37  mov     rcx, r13; this
0x180013a3a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180013a3f  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x180013a47  mov     rcx, r13; this
0x180013a4a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180013a4f  test    eax, eax
0x180013a51  js      loc_180013D6C
0x180013a57  cmp     di, 8
0x180013a5b  jz      loc_180013D07
0x180013a61  cmp     di, 11h
0x180013a65  jz      loc_180013BE1
0x180013a6b  cmp     di, 13h
0x180013a6f  jz      loc_180013B69
0x180013a75  mov     eax, 4008h
0x180013a7a  cmp     di, ax
0x180013a7d  jnz     loc_180013D58
0x180013a83  lea     rax, [rsp+21C8h+String1]
0x180013a8b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013a8f  inc     rdi
0x180013a92  cmp     [rax+rdi*2], bx
0x180013a96  jnz     short loc_180013A8F
0x180013a98  add     edi, 2
0x180013a9b  mov     [rsp+21C8h+var_2158], rbx
0x180013aa0  movsxd  rcx, edi
0x180013aa3  mov     edx, 2
0x180013aa8  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180013aad  cmp     rax, 100h
0x180013ab3  jbe     short loc_180013AC9
0x180013ab5  mov     rdx, rax
0x180013ab8  lea     rcx, [rsp+21C8h+var_2158]
0x180013abd  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180013ac2  mov     rdi, [rsp+21C8h+var_2158]
0x180013ac7  jmp     short loc_180013AD3
0x180013ac9  lea     rdi, [rsp+21C8h+var_2150]
0x180013ace  mov     [rsp+21C8h+var_2158], rdi
0x180013ad3  jmp     short loc_180013AEB
0x180013ad5  xor     ebx, ebx
0x180013ad7  mov     rdi, [rsp+21C8h+var_2158]
0x180013adc  mov     r13, [rsp+21C8h+var_2188]
0x180013ae1  mov     r15, [rsp+21C8h+var_2180]
0x180013ae6  mov     r12, [rsp+21C8h+var_2178]
0x180013aeb  test    rdi, rdi
0x180013aee  jz      short loc_180013B55
0x180013af0  lea     rsi, [rsp+21C8h+String1]
0x180013af8  cmp     [rsp+21C8h+String1], bx
0x180013b00  jz      short loc_180013B3B
0x180013b02  mov     rcx, rsi; lpsz
0x180013b05  call    cs:__imp_CharNextW
0x180013b0b  movzx   ecx, word ptr [rsi]
0x180013b0e  cmp     cx, 5Ch ; '\'
0x180013b12  jnz     short loc_180013B2B
0x180013b14  cmp     word ptr [rax], 30h ; '0'
0x180013b18  jnz     short loc_180013B2B
0x180013b1a  mov     [rdi], bx
0x180013b1d  mov     rcx, rax; lpsz
0x180013b20  call    cs:__imp_CharNextW
0x180013b26  mov     rsi, rax
0x180013b29  jmp     short loc_180013B32
0x180013b2b  mov     [rdi], cx
0x180013b2e  add     rsi, 2
0x180013b32  add     rdi, 2
0x180013b36  cmp     [rsi], bx
0x180013b39  jnz     short loc_180013B02
0x180013b3b  mov     dword ptr [rdi], 0
0x180013b41  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x180013b46  mov     rdx, r12; unsigned __int16 *
0x180013b49  mov     rcx, r15; this
0x180013b4c  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x180013b51  mov     edi, eax
0x180013b53  jmp     short loc_180013B5A
0x180013b55  mov     edi, 0Eh
0x180013b5a  lea     rcx, [rsp+21C8h+var_2158]
0x180013b5f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180013b64  jmp     loc_180013D4B
0x180013b69  mov     [rsp+21C8h+pulOut], ebx
0x180013b6d  mov     [rsp+21C8h+var_2188], rbx
0x180013b72  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x180013b77  xor     r8d, r8d; dwFlags
0x180013b7a  xor     edx, edx; lcid
0x180013b7c  lea     rcx, [rsp+21C8h+String1]; strIn
0x180013b84  call    cs:__imp_VarUI4FromStr
0x180013b8a  mov     edi, eax
0x180013b8c  test    eax, eax
0x180013b8e  jns     short loc_180013BA1
0x180013b90  lea     rcx, [rsp+21C8h+var_2188]
0x180013b95  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013b9a  mov     eax, edi
0x180013b9c  jmp     loc_180013D6C
0x180013ba1  mov     eax, [rsp+21C8h+pulOut]
0x180013ba5  mov     dword ptr [rsp+21C8h+Data], eax
0x180013ba9  mov     [rsp+21C8h+cbData], 4; cbData
0x180013bb1  lea     rax, [rsp+21C8h+Data]
0x180013bb6  mov     [rsp+21C8h+lpData], rax; lpData
0x180013bbb  mov     r9d, 4; dwType
0x180013bc1  xor     r8d, r8d; Reserved
0x180013bc4  mov     rdx, r12; lpValueName
0x180013bc7  mov     rcx, [r15]; hKey
0x180013bca  call    cs:__imp_RegSetValueExW
0x180013bd0  mov     edi, eax
0x180013bd2  lea     rcx, [rsp+21C8h+var_2188]
0x180013bd7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180013bdc  jmp     loc_180013D4B
0x180013be1  lea     rax, [rsp+21C8h+String1]
0x180013be9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013bed  inc     rdi
0x180013bf0  cmp     [rax+rdi*2], bx
0x180013bf4  jnz     short loc_180013BED
0x180013bf6  mov     dword ptr [rsp+21C8h+Data], edi
0x180013bfa  test    dil, 1
0x180013bfe  jz      short loc_180013C0A
0x180013c00  mov     eax, 80004005h
0x180013c05  jmp     loc_180013D6C
0x180013c0a  mov     eax, edi
0x180013c0c  cdq
0x180013c0d  sub     eax, edx
0x180013c0f  sar     eax, 1
0x180013c11  movsxd  rsi, eax
0x180013c14  mov     [rsp+21C8h+var_2158], rbx
0x180013c19  mov     r14, rsi
0x180013c1c  mov     [rsp+21C8h+var_2168], rsi
0x180013c21  mov     edx, 1
0x180013c26  mov     rcx, rsi
0x180013c29  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180013c2e  cmp     rax, 100h
0x180013c34  jbe     short loc_180013C4A
0x180013c36  mov     rdx, rax
0x180013c39  lea     rcx, [rsp+21C8h+var_2158]
0x180013c3e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180013c43  mov     rcx, [rsp+21C8h+var_2158]
0x180013c48  jmp     short loc_180013C54
0x180013c4a  lea     rcx, [rsp+21C8h+var_2150]
0x180013c4f  mov     [rsp+21C8h+var_2158], rcx
0x180013c54  jmp     short loc_180013C78
0x180013c56  xor     ebx, ebx
0x180013c58  mov     edi, dword ptr [rsp+21C8h+Data]
0x180013c5c  mov     rcx, [rsp+21C8h+var_2158]; void *
0x180013c61  mov     r14, [rsp+21C8h+var_2168]
0x180013c66  mov     r13, [rsp+21C8h+var_2188]
0x180013c6b  mov     r15, [rsp+21C8h+var_2180]
0x180013c70  mov     r12, [rsp+21C8h+var_2178]
0x180013c75  mov     esi, r14d
0x180013c78  test    rcx, rcx
0x180013c7b  jnz     short loc_180013C8C
0x180013c7d  lea     rcx, [rsp+21C8h+var_2158]
0x180013c82  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180013c87  jmp     loc_180013C00
0x180013c8c  mov     r8, r14; Size
0x180013c8f  xor     edx, edx; Val
0x180013c91  call    memset_0
0x180013c96  mov     r10d, ebx
0x180013c99  test    edi, edi
0x180013c9b  jle     short loc_180013CD6
0x180013c9d  mov     r9d, r10d
0x180013ca0  shr     r9, 1
0x180013ca3  mov     r8, [rsp+21C8h+var_2158]
0x180013ca8  mov     ecx, r10d
0x180013cab  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x180013cb3  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180013cb8  mov     edx, r10d
0x180013cbb  and     edx, 1
0x180013cbe  shl     edx, 2
0x180013cc1  mov     ecx, 4
0x180013cc6  sub     ecx, edx
0x180013cc8  shl     al, cl
0x180013cca  or      [r9+r8], al
0x180013cce  inc     r10d
0x180013cd1  cmp     r10d, edi
0x180013cd4  jl      short loc_180013C9D
0x180013cd6  mov     rax, [rsp+21C8h+var_2158]
0x180013cdb  mov     [rsp+21C8h+cbData], esi; cbData
0x180013cdf  mov     [rsp+21C8h+lpData], rax; lpData
0x180013ce4  mov     r9d, 3; dwType
0x180013cea  xor     r8d, r8d; Reserved
0x180013ced  mov     rdx, r12; lpValueName
0x180013cf0  mov     rcx, [r15]; hKey
0x180013cf3  call    cs:__imp_RegSetValueExW
0x180013cf9  mov     edi, eax
0x180013cfb  lea     rcx, [rsp+21C8h+var_2158]
0x180013d00  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180013d05  jmp     short loc_180013D4B
0x180013d07  lea     rax, [rsp+21C8h+String1]
0x180013d0f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180013d13  inc     rdi
0x180013d16  cmp     [rax+rdi*2], bx
0x180013d1a  jnz     short loc_180013D13
0x180013d1c  lea     eax, ds:2[rdi*2]
0x180013d23  mov     [rsp+21C8h+cbData], eax; cbData
0x180013d27  lea     rax, [rsp+21C8h+String1]
0x180013d2f  mov     [rsp+21C8h+lpData], rax; lpData
0x180013d34  mov     r9d, 1; dwType
0x180013d3a  xor     r8d, r8d; Reserved
0x180013d3d  mov     rdx, r12; lpValueName
0x180013d40  mov     rcx, [r15]; hKey
0x180013d43  call    cs:__imp_RegSetValueExW
0x180013d49  mov     edi, eax
0x180013d4b  test    edi, edi
0x180013d4d  jz      short loc_180013D58
0x180013d4f  mov     ecx, edi; unsigned int
0x180013d51  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180013d56  jmp     short loc_180013D6C
0x180013d58  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x180013d5d  mov     rcx, r13; this
0x180013d60  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180013d65  test    eax, eax
0x180013d67  cmovs   ebx, eax
0x180013d6a  mov     eax, ebx
0x180013d6c  mov     rcx, [rsp+21C8h+var_48]
0x180013d74  xor     rcx, rsp; StackCookie
0x180013d77  call    __security_check_cookie
0x180013d7c  add     rsp, 2190h
0x180013d83  pop     r15
0x180013d85  pop     r14
0x180013d87  pop     r13
0x180013d89  pop     r12
0x180013d8b  pop     rdi
0x180013d8c  pop     rsi
0x180013d8d  pop     rbx
0x180013d8e  retn
```
