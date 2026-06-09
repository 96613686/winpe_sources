# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800547c8`
- end: `0x180054bd0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1032`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config`

## callers

- `0x180057fd0`

## callees

- `0x180051f30`
- `0x180052bf4`
- `0x180053aa0`
- `0x180054104`
- `0x1800541b0`
- `0x1800547c8`
- `0x180054bd8`
- `0x180054dc4`
- `0x180054e54`
- `0x180056028`
- `0x180058b4c`
- `0x180058c50`
- `0x18005946c`
- `0x180095ab0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180054919`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005493a`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180054919`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18005493a`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800549f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180054b26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180054b7d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800549f1`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180054b26`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180054b7d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800549a4`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800549a4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  const WCHAR *v4; // r13
  HKEY *v5; // r12
  ATL::CRegParser *v6; // r15
  unsigned int v7; // ebx
  __int64 result; // rax
  __int64 v9; // rdi
  unsigned __int64 v10; // rax
  BYTE *v11; // rdi
  WCHAR *i; // rsi
  const WCHAR *v13; // rax
  LSTATUS v14; // edi
  HRESULT v15; // edi
  __int64 v16; // rdi
  DWORD cbData; // r14d
  size_t v18; // rsi
  unsigned __int64 v19; // rax
  BYTE *v20; // rcx
  int j; // r11d
  unsigned __int8 v22; // al
  int v23; // r11d
  __int64 v24; // r9
  __int64 v25; // r10
  __int64 v26; // rdi
  int Token; // eax
  ULONG pulOut; // [rsp+30h] [rbp-2198h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-2190h] BYREF
  ATL::CRegParser *v30; // [rsp+40h] [rbp-2188h] BYREF
  struct ATL::CRegKey *v31; // [rsp+48h] [rbp-2180h]
  const unsigned __int16 *v32; // [rsp+50h] [rbp-2178h]
  size_t v33; // [rsp+60h] [rbp-2168h]
  unsigned __int16 *v34; // [rsp+68h] [rbp-2160h]
  BYTE *lpData; // [rsp+70h] [rbp-2158h] BYREF
  _BYTE v36[264]; // [rsp+78h] [rbp-2150h] BYREF
  OLECHAR sz[4096]; // [rsp+180h] [rbp-2048h] BYREF

  v4 = a3;
  v5 = a2;
  v6 = this;
  v30 = this;
  v31 = (struct ATL::CRegKey *)a2;
  v32 = a3;
  v34 = a4;
  v7 = 0;
  LOWORD(pulOut) = 0;
  result = ATL::CRegParser::NextToken(this, sz);
  if ( (int)result >= 0 )
  {
    if ( !(unsigned int)ATL::CRegParser::VTFromRegType(sz, (unsigned __int16 *)&pulOut) )
      return 2147614729LL;
    ATL::CRegParser::SkipWhiteSpace(v6);
    result = ATL::CRegParser::NextToken(v6, sz);
    if ( (int)result >= 0 )
    {
      if ( (unsigned __int16)pulOut == 8 )
      {
        v26 = -1;
        do
          ++v26;
        while ( sz[v26] );
        v14 = RegSetValueExW(*v5, v4, 0, 1u, (const BYTE *)sz, 2 * v26 + 2);
        goto LABEL_44;
      }
      if ( (unsigned __int16)pulOut != 17 )
      {
        if ( (unsigned __int16)pulOut == 19 )
        {
          pulOut = 0;
          v30 = 0;
          v15 = VarUI4FromStr(sz, 0, 0, &pulOut);
          if ( v15 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v30);
            return (unsigned int)v15;
          }
          *(_DWORD *)Data = pulOut;
          v14 = RegSetValueExW(*v5, v4, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v30);
        }
        else
        {
          if ( (unsigned __int16)pulOut != 16392 )
          {
LABEL_46:
            Token = ATL::CRegParser::NextToken(v6, v34);
            if ( Token < 0 )
              return (unsigned int)Token;
            return v7;
          }
          v9 = -1;
          do
            ++v9;
          while ( sz[v9] );
          lpData = 0;
          try
          {
            v10 = ATL::AtlMultiplyThrow<unsigned __int64>();
            if ( v10 <= 0x100 )
            {
              v11 = v36;
              lpData = v36;
            }
            else
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v10);
              v11 = lpData;
            }
          }
          catch ( ... )
          {
            v7 = 0;
            v11 = lpData;
            v6 = v30;
            v5 = (HKEY *)v31;
            v4 = v32;
          }
          if ( v11 )
          {
            for ( i = sz; *i; v11 += 2 )
            {
              v13 = CharNextW(i);
              if ( *i == 92 && *v13 == 48 )
              {
                *(_WORD *)v11 = 0;
                i = CharNextW(v13);
              }
              else
              {
                *(_WORD *)v11 = *i++;
              }
            }
            *(_DWORD *)v11 = 0;
            v14 = ATL::CRegKey::SetMultiStringValue((ATL::CRegKey *)v5, v4, (const unsigned __int16 *)lpData);
          }
          else
          {
            v14 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_44:
        if ( v14 )
          return ATL::AtlHresultFromWin32(v14);
        goto LABEL_46;
      }
      v16 = -1;
      do
        ++v16;
      while ( sz[v16] );
      *(_DWORD *)Data = v16;
      if ( (v16 & 1) == 0 )
      {
        cbData = (int)v16 / 2;
        lpData = 0;
        v18 = (int)v16 / 2;
        v33 = v18;
        try
        {
          v19 = ATL::AtlMultiplyThrow<unsigned __int64>();
          if ( v19 <= 0x100 )
          {
            v20 = v36;
            lpData = v36;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v19);
            v20 = lpData;
          }
        }
        catch ( ... )
        {
          v7 = 0;
          LODWORD(v16) = *(_DWORD *)Data;
          v20 = lpData;
          v18 = v33;
          v6 = v30;
          v5 = (HKEY *)v31;
          v4 = v32;
          cbData = v33;
        }
        if ( v20 )
        {
          memset_0(v20, 0, v18);
          for ( j = 0; j < (int)v16; j = v23 + 1 )
          {
            v22 = ATL::CRegParser::ChToByte(sz[j]);
            *(_BYTE *)(v25 + v24) |= v22 << (4 - 4 * (v23 & 1));
          }
          v14 = RegSetValueExW(*v5, v4, 0, 3u, lpData, cbData);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_44;
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
0x1800547c8  push    rbx
0x1800547ca  push    rsi
0x1800547cb  push    rdi
0x1800547cc  push    r12
0x1800547ce  push    r13
0x1800547d0  push    r14
0x1800547d2  push    r15
0x1800547d4  mov     eax, 2190h
0x1800547d9  call    _alloca_probe
0x1800547de  sub     rsp, rax
0x1800547e1  mov     rax, cs:__security_cookie
0x1800547e8  xor     rax, rsp
0x1800547eb  mov     [rsp+21C8h+var_48], rax
0x1800547f3  mov     r13, r8
0x1800547f6  mov     r12, rdx
0x1800547f9  mov     r15, rcx
0x1800547fc  mov     [rsp+21C8h+var_2188], rcx
0x180054801  mov     [rsp+21C8h+var_2180], rdx
0x180054806  mov     [rsp+21C8h+var_2178], r8
0x18005480b  mov     [rsp+21C8h+var_2160], r9
0x180054810  xor     ebx, ebx
0x180054812  mov     word ptr [rsp+21C8h+pulOut], bx
0x180054817  lea     rdx, [rsp+21C8h+sz]; unsigned __int16 *
0x18005481f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180054824  test    eax, eax
0x180054826  js      loc_180054BAC
0x18005482c  lea     rdx, [rsp+21C8h+pulOut]; unsigned __int16 *
0x180054831  lea     rcx, [rsp+21C8h+sz]; lpString1
0x180054839  call    ?VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z; ATL::CRegParser::VTFromRegType(ushort const *,ushort &)
0x18005483e  test    eax, eax
0x180054840  jnz     short loc_18005484C
0x180054842  mov     eax, 80020009h
0x180054847  jmp     loc_180054BAC
0x18005484c  mov     rcx, r15; this
0x18005484f  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180054854  lea     rdx, [rsp+21C8h+sz]; unsigned __int16 *
0x18005485c  mov     rcx, r15; this
0x18005485f  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180054864  test    eax, eax
0x180054866  js      loc_180054BAC
0x18005486c  movzx   eax, word ptr [rsp+21C8h+pulOut]
0x180054871  cmp     eax, 8
0x180054874  jz      loc_180054B40
0x18005487a  cmp     eax, 11h
0x18005487d  jz      loc_180054A0E
0x180054883  cmp     eax, 13h
0x180054886  jz      loc_180054989
0x18005488c  cmp     eax, 4008h
0x180054891  jnz     loc_180054B98
0x180054897  lea     rax, [rsp+21C8h+sz]
0x18005489f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800548a3  inc     rdi
0x1800548a6  cmp     [rax+rdi*2], bx
0x1800548aa  jnz     short loc_1800548A3
0x1800548ac  add     edi, 2
0x1800548af  mov     [rsp+21C8h+var_2158], rbx
0x1800548b4  movsxd  rcx, edi
0x1800548b7  mov     edx, 2
0x1800548bc  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800548c1  cmp     rax, 100h
0x1800548c7  jbe     short loc_1800548DD
0x1800548c9  mov     rdx, rax
0x1800548cc  lea     rcx, [rsp+21C8h+var_2158]
0x1800548d1  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800548d6  mov     rdi, [rsp+21C8h+var_2158]
0x1800548db  jmp     short loc_1800548E7
0x1800548dd  lea     rdi, [rsp+21C8h+var_2150]
0x1800548e2  mov     [rsp+21C8h+var_2158], rdi
0x1800548e7  jmp     short loc_1800548FF
0x1800548e9  xor     ebx, ebx
0x1800548eb  mov     rdi, [rsp+21C8h+var_2158]
0x1800548f0  mov     r15, [rsp+21C8h+var_2188]
0x1800548f5  mov     r12, [rsp+21C8h+var_2180]
0x1800548fa  mov     r13, [rsp+21C8h+var_2178]
0x1800548ff  test    rdi, rdi
0x180054902  jz      short loc_180054975
0x180054904  lea     rsi, [rsp+21C8h+sz]
0x18005490c  cmp     [rsp+21C8h+sz], bx
0x180054914  jz      short loc_18005495B
0x180054916  mov     rcx, rsi; lpsz
0x180054919  call    cs:__imp_CharNextW
0x180054920  nop     dword ptr [rax+rax+00h]
0x180054925  movzx   ecx, word ptr [rsi]
0x180054928  cmp     cx, 5Ch ; '\'
0x18005492c  jnz     short loc_18005494B
0x18005492e  cmp     word ptr [rax], 30h ; '0'
0x180054932  jnz     short loc_18005494B
0x180054934  mov     [rdi], bx
0x180054937  mov     rcx, rax; lpsz
0x18005493a  call    cs:__imp_CharNextW
0x180054941  nop     dword ptr [rax+rax+00h]
0x180054946  mov     rsi, rax
0x180054949  jmp     short loc_180054952
0x18005494b  mov     [rdi], cx
0x18005494e  add     rsi, 2
0x180054952  add     rdi, 2
0x180054956  cmp     [rsi], bx
0x180054959  jnz     short loc_180054916
0x18005495b  mov     dword ptr [rdi], 0
0x180054961  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x180054966  mov     rdx, r13; unsigned __int16 *
0x180054969  mov     rcx, r12; this
0x18005496c  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x180054971  mov     edi, eax
0x180054973  jmp     short loc_18005497A
0x180054975  mov     edi, 0Eh
0x18005497a  lea     rcx, [rsp+21C8h+var_2158]
0x18005497f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180054984  jmp     loc_180054B8B
0x180054989  mov     [rsp+21C8h+pulOut], ebx
0x18005498d  mov     [rsp+21C8h+var_2188], rbx
0x180054992  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x180054997  xor     r8d, r8d; dwFlags
0x18005499a  xor     edx, edx; lcid
0x18005499c  lea     rcx, [rsp+21C8h+sz]; strIn
0x1800549a4  call    cs:__imp_VarUI4FromStr
0x1800549ab  nop     dword ptr [rax+rax+00h]
0x1800549b0  mov     edi, eax
0x1800549b2  test    eax, eax
0x1800549b4  jns     short loc_1800549C7
0x1800549b6  lea     rcx, [rsp+21C8h+var_2188]
0x1800549bb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800549c0  mov     eax, edi
0x1800549c2  jmp     loc_180054BAC
0x1800549c7  mov     eax, [rsp+21C8h+pulOut]
0x1800549cb  mov     dword ptr [rsp+21C8h+Data], eax
0x1800549cf  mov     [rsp+21C8h+cbData], 4; cbData
0x1800549d7  lea     rax, [rsp+21C8h+Data]
0x1800549dc  mov     [rsp+21C8h+lpData], rax; lpData
0x1800549e1  mov     r9d, 4; dwType
0x1800549e7  xor     r8d, r8d; Reserved
0x1800549ea  mov     rdx, r13; lpValueName
0x1800549ed  mov     rcx, [r12]; hKey
0x1800549f1  call    cs:__imp_RegSetValueExW
0x1800549f8  nop     dword ptr [rax+rax+00h]
0x1800549fd  mov     edi, eax
0x1800549ff  lea     rcx, [rsp+21C8h+var_2188]
0x180054a04  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180054a09  jmp     loc_180054B8B
0x180054a0e  lea     rax, [rsp+21C8h+sz]
0x180054a16  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180054a1a  inc     rdi
0x180054a1d  cmp     [rax+rdi*2], bx
0x180054a21  jnz     short loc_180054A1A
0x180054a23  mov     dword ptr [rsp+21C8h+Data], edi
0x180054a27  test    dil, 1
0x180054a2b  jz      short loc_180054A37
0x180054a2d  mov     eax, 80004005h
0x180054a32  jmp     loc_180054BAC
0x180054a37  mov     eax, edi
0x180054a39  cdq
0x180054a3a  sub     eax, edx
0x180054a3c  sar     eax, 1
0x180054a3e  movsxd  r14, eax
0x180054a41  mov     [rsp+21C8h+var_2158], rbx
0x180054a46  mov     rsi, r14
0x180054a49  mov     [rsp+21C8h+var_2168], r14
0x180054a4e  mov     edx, 1
0x180054a53  mov     rcx, r14
0x180054a56  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180054a5b  cmp     rax, 100h
0x180054a61  jbe     short loc_180054A77
0x180054a63  mov     rdx, rax
0x180054a66  lea     rcx, [rsp+21C8h+var_2158]
0x180054a6b  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180054a70  mov     rcx, [rsp+21C8h+var_2158]
0x180054a75  jmp     short loc_180054A81
0x180054a77  lea     rcx, [rsp+21C8h+var_2150]
0x180054a7c  mov     [rsp+21C8h+var_2158], rcx
0x180054a81  jmp     short loc_180054AA5
0x180054a83  xor     ebx, ebx
0x180054a85  mov     edi, dword ptr [rsp+21C8h+Data]
0x180054a89  mov     rcx, [rsp+21C8h+var_2158]; void *
0x180054a8e  mov     rsi, [rsp+21C8h+var_2168]
0x180054a93  mov     r15, [rsp+21C8h+var_2188]
0x180054a98  mov     r12, [rsp+21C8h+var_2180]
0x180054a9d  mov     r13, [rsp+21C8h+var_2178]
0x180054aa2  mov     r14d, esi
0x180054aa5  test    rcx, rcx
0x180054aa8  jnz     short loc_180054AB9
0x180054aaa  lea     rcx, [rsp+21C8h+var_2158]
0x180054aaf  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180054ab4  jmp     loc_180054A2D
0x180054ab9  mov     r8, rsi; Size
0x180054abc  xor     edx, edx; Val
0x180054abe  call    memset_0
0x180054ac3  mov     r11d, ebx
0x180054ac6  test    edi, edi
0x180054ac8  jle     short loc_180054B07
0x180054aca  mov     r10d, r11d
0x180054acd  shr     r10, 1
0x180054ad0  mov     r9, [rsp+21C8h+var_2158]
0x180054ad5  mov     ecx, r11d
0x180054ad8  movzx   ecx, [rsp+rcx*2+21C8h+sz]; unsigned __int16
0x180054ae0  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180054ae5  mov     r8b, al
0x180054ae8  mov     eax, r11d
0x180054aeb  and     eax, 1
0x180054aee  shl     eax, 2
0x180054af1  mov     ecx, 4
0x180054af6  sub     ecx, eax
0x180054af8  shl     r8b, cl
0x180054afb  or      [r10+r9], r8b
0x180054aff  inc     r11d
0x180054b02  cmp     r11d, edi
0x180054b05  jl      short loc_180054ACA
0x180054b07  mov     rax, [rsp+21C8h+var_2158]
0x180054b0c  mov     [rsp+21C8h+cbData], r14d; cbData
0x180054b11  mov     [rsp+21C8h+lpData], rax; lpData
0x180054b16  mov     r9d, 3; dwType
0x180054b1c  xor     r8d, r8d; Reserved
0x180054b1f  mov     rdx, r13; lpValueName
0x180054b22  mov     rcx, [r12]; hKey
0x180054b26  call    cs:__imp_RegSetValueExW
0x180054b2d  nop     dword ptr [rax+rax+00h]
0x180054b32  mov     edi, eax
0x180054b34  lea     rcx, [rsp+21C8h+var_2158]
0x180054b39  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180054b3e  jmp     short loc_180054B8B
0x180054b40  lea     rax, [rsp+21C8h+sz]
0x180054b48  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180054b4c  inc     rdi
0x180054b4f  cmp     [rax+rdi*2], bx
0x180054b53  jnz     short loc_180054B4C
0x180054b55  lea     eax, ds:2[rdi*2]
0x180054b5c  mov     [rsp+21C8h+cbData], eax; cbData
0x180054b60  lea     rax, [rsp+21C8h+sz]
0x180054b68  mov     [rsp+21C8h+lpData], rax; lpData
0x180054b6d  mov     r9d, 1; dwType
0x180054b73  xor     r8d, r8d; Reserved
0x180054b76  mov     rdx, r13; lpValueName
0x180054b79  mov     rcx, [r12]; hKey
0x180054b7d  call    cs:__imp_RegSetValueExW
0x180054b84  nop     dword ptr [rax+rax+00h]
0x180054b89  mov     edi, eax
0x180054b8b  test    edi, edi
0x180054b8d  jz      short loc_180054B98
0x180054b8f  mov     ecx, edi; unsigned int
0x180054b91  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180054b96  jmp     short loc_180054BAC
0x180054b98  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x180054b9d  mov     rcx, r15; this
0x180054ba0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180054ba5  test    eax, eax
0x180054ba7  cmovs   ebx, eax
0x180054baa  mov     eax, ebx
0x180054bac  mov     rcx, [rsp+21C8h+var_48]
0x180054bb4  xor     rcx, rsp; StackCookie
0x180054bb7  call    __security_check_cookie
0x180054bbc  add     rsp, 2190h
0x180054bc3  pop     r15
0x180054bc5  pop     r14
0x180054bc7  pop     r13
0x180054bc9  pop     r12
0x180054bcb  pop     rdi
0x180054bcc  pop     rsi
0x180054bcd  pop     rbx
0x180054bce  retn
```
