# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800508ac`
- end: `0x180050c9f`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1011`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x180053e48`

## callees

- `0x18004e0c0`
- `0x18004ed64`
- `0x18004fbcc`
- `0x18005021c`
- `0x1800502bc`
- `0x1800508ac`
- `0x180050ca8`
- `0x180050e80`
- `0x180050f08`
- `0x180052048`
- `0x18005497c`
- `0x180054a7c`
- `0x18008e890`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180050a15`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180050a30`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180050a15`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180050a30`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050ada`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050c03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050c53`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050ada`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050c03`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180050c53`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180050926`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180050926`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180050a94`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180050a94`

## pseudocode

```c
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
0x1800508ac  push    rbx
0x1800508ae  push    rsi
0x1800508af  push    rdi
0x1800508b0  push    r12
0x1800508b2  push    r13
0x1800508b4  push    r14
0x1800508b6  push    r15
0x1800508b8  mov     eax, 2190h
0x1800508bd  call    _alloca_probe
0x1800508c2  sub     rsp, rax
0x1800508c5  mov     rax, cs:__security_cookie
0x1800508cc  xor     rax, rsp
0x1800508cf  mov     [rsp+21C8h+var_48], rax
0x1800508d7  mov     r12, r8
0x1800508da  mov     r15, rdx
0x1800508dd  mov     r13, rcx
0x1800508e0  mov     [rsp+21C8h+var_2188], rcx
0x1800508e5  mov     [rsp+21C8h+var_2180], rdx
0x1800508ea  mov     [rsp+21C8h+var_2178], r8
0x1800508ef  mov     [rsp+21C8h+var_2160], r9
0x1800508f4  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x1800508fc  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180050901  xor     ebx, ebx
0x180050903  test    eax, eax
0x180050905  js      loc_180050C7C
0x18005090b  mov     edi, ebx
0x18005090d  lea     r14, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180050914  movsxd  rsi, edi
0x180050917  add     rsi, rsi
0x18005091a  mov     rdx, [r14+rsi*8]; lpString2
0x18005091e  lea     rcx, [rsp+21C8h+String1]; lpString1
0x180050926  call    cs:__imp_lstrcmpiW
0x18005092c  test    eax, eax
0x18005092e  jz      short loc_180050941
0x180050930  inc     edi
0x180050932  cmp     edi, 4
0x180050935  jb      short loc_180050914
0x180050937  mov     eax, 80020009h
0x18005093c  jmp     loc_180050C7C
0x180050941  movzx   edi, word ptr [r14+rsi*8+8]
0x180050947  mov     rcx, r13; this
0x18005094a  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18005094f  lea     rdx, [rsp+21C8h+String1]; unsigned __int16 *
0x180050957  mov     rcx, r13; this
0x18005095a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18005095f  test    eax, eax
0x180050961  js      loc_180050C7C
0x180050967  cmp     di, 8
0x18005096b  jz      loc_180050C17
0x180050971  cmp     di, 11h
0x180050975  jz      loc_180050AF1
0x18005097b  cmp     di, 13h
0x18005097f  jz      loc_180050A79
0x180050985  mov     eax, 4008h
0x18005098a  cmp     di, ax
0x18005098d  jnz     loc_180050C68
0x180050993  lea     rax, [rsp+21C8h+String1]
0x18005099b  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18005099f  inc     rdi
0x1800509a2  cmp     [rax+rdi*2], bx
0x1800509a6  jnz     short loc_18005099F
0x1800509a8  add     edi, 2
0x1800509ab  mov     [rsp+21C8h+var_2158], rbx
0x1800509b0  movsxd  rcx, edi
0x1800509b3  mov     edx, 2
0x1800509b8  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800509bd  cmp     rax, 100h
0x1800509c3  jbe     short loc_1800509D9
0x1800509c5  mov     rdx, rax
0x1800509c8  lea     rcx, [rsp+21C8h+var_2158]
0x1800509cd  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800509d2  mov     rdi, [rsp+21C8h+var_2158]
0x1800509d7  jmp     short loc_1800509E3
0x1800509d9  lea     rdi, [rsp+21C8h+var_2150]
0x1800509de  mov     [rsp+21C8h+var_2158], rdi
0x1800509e3  jmp     short loc_1800509FB
0x1800509e5  xor     ebx, ebx
0x1800509e7  mov     rdi, [rsp+21C8h+var_2158]
0x1800509ec  mov     r13, [rsp+21C8h+var_2188]
0x1800509f1  mov     r15, [rsp+21C8h+var_2180]
0x1800509f6  mov     r12, [rsp+21C8h+var_2178]
0x1800509fb  test    rdi, rdi
0x1800509fe  jz      short loc_180050A65
0x180050a00  lea     rsi, [rsp+21C8h+String1]
0x180050a08  cmp     [rsp+21C8h+String1], bx
0x180050a10  jz      short loc_180050A4B
0x180050a12  mov     rcx, rsi; lpsz
0x180050a15  call    cs:__imp_CharNextW
0x180050a1b  movzx   ecx, word ptr [rsi]
0x180050a1e  cmp     cx, 5Ch ; '\'
0x180050a22  jnz     short loc_180050A3B
0x180050a24  cmp     word ptr [rax], 30h ; '0'
0x180050a28  jnz     short loc_180050A3B
0x180050a2a  mov     [rdi], bx
0x180050a2d  mov     rcx, rax; lpsz
0x180050a30  call    cs:__imp_CharNextW
0x180050a36  mov     rsi, rax
0x180050a39  jmp     short loc_180050A42
0x180050a3b  mov     [rdi], cx
0x180050a3e  add     rsi, 2
0x180050a42  add     rdi, 2
0x180050a46  cmp     [rsi], bx
0x180050a49  jnz     short loc_180050A12
0x180050a4b  mov     dword ptr [rdi], 0
0x180050a51  mov     r8, [rsp+21C8h+var_2158]; unsigned __int16 *
0x180050a56  mov     rdx, r12; unsigned __int16 *
0x180050a59  mov     rcx, r15; this
0x180050a5c  call    ?SetMultiStringValue@CRegKey@ATL@@QEAAJPEBG0@Z; ATL::CRegKey::SetMultiStringValue(ushort const *,ushort const *)
0x180050a61  mov     edi, eax
0x180050a63  jmp     short loc_180050A6A
0x180050a65  mov     edi, 0Eh
0x180050a6a  lea     rcx, [rsp+21C8h+var_2158]
0x180050a6f  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180050a74  jmp     loc_180050C5B
0x180050a79  mov     [rsp+21C8h+pulOut], ebx
0x180050a7d  mov     [rsp+21C8h+var_2188], rbx
0x180050a82  lea     r9, [rsp+21C8h+pulOut]; pulOut
0x180050a87  xor     r8d, r8d; dwFlags
0x180050a8a  xor     edx, edx; lcid
0x180050a8c  lea     rcx, [rsp+21C8h+String1]; strIn
0x180050a94  call    cs:__imp_VarUI4FromStr
0x180050a9a  mov     edi, eax
0x180050a9c  test    eax, eax
0x180050a9e  jns     short loc_180050AB1
0x180050aa0  lea     rcx, [rsp+21C8h+var_2188]
0x180050aa5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180050aaa  mov     eax, edi
0x180050aac  jmp     loc_180050C7C
0x180050ab1  mov     eax, [rsp+21C8h+pulOut]
0x180050ab5  mov     dword ptr [rsp+21C8h+Data], eax
0x180050ab9  mov     [rsp+21C8h+cbData], 4; cbData
0x180050ac1  lea     rax, [rsp+21C8h+Data]
0x180050ac6  mov     [rsp+21C8h+lpData], rax; lpData
0x180050acb  mov     r9d, 4; dwType
0x180050ad1  xor     r8d, r8d; Reserved
0x180050ad4  mov     rdx, r12; lpValueName
0x180050ad7  mov     rcx, [r15]; hKey
0x180050ada  call    cs:__imp_RegSetValueExW
0x180050ae0  mov     edi, eax
0x180050ae2  lea     rcx, [rsp+21C8h+var_2188]
0x180050ae7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180050aec  jmp     loc_180050C5B
0x180050af1  lea     rax, [rsp+21C8h+String1]
0x180050af9  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180050afd  inc     rdi
0x180050b00  cmp     [rax+rdi*2], bx
0x180050b04  jnz     short loc_180050AFD
0x180050b06  mov     dword ptr [rsp+21C8h+Data], edi
0x180050b0a  test    dil, 1
0x180050b0e  jz      short loc_180050B1A
0x180050b10  mov     eax, 80004005h
0x180050b15  jmp     loc_180050C7C
0x180050b1a  mov     eax, edi
0x180050b1c  cdq
0x180050b1d  sub     eax, edx
0x180050b1f  sar     eax, 1
0x180050b21  movsxd  rsi, eax
0x180050b24  mov     [rsp+21C8h+var_2158], rbx
0x180050b29  mov     r14, rsi
0x180050b2c  mov     [rsp+21C8h+var_2168], rsi
0x180050b31  mov     edx, 1
0x180050b36  mov     rcx, rsi
0x180050b39  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180050b3e  cmp     rax, 100h
0x180050b44  jbe     short loc_180050B5A
0x180050b46  mov     rdx, rax
0x180050b49  lea     rcx, [rsp+21C8h+var_2158]
0x180050b4e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180050b53  mov     rcx, [rsp+21C8h+var_2158]
0x180050b58  jmp     short loc_180050B64
0x180050b5a  lea     rcx, [rsp+21C8h+var_2150]
0x180050b5f  mov     [rsp+21C8h+var_2158], rcx
0x180050b64  jmp     short loc_180050B88
0x180050b66  xor     ebx, ebx
0x180050b68  mov     edi, dword ptr [rsp+21C8h+Data]
0x180050b6c  mov     rcx, [rsp+21C8h+var_2158]; void *
0x180050b71  mov     r14, [rsp+21C8h+var_2168]
0x180050b76  mov     r13, [rsp+21C8h+var_2188]
0x180050b7b  mov     r15, [rsp+21C8h+var_2180]
0x180050b80  mov     r12, [rsp+21C8h+var_2178]
0x180050b85  mov     esi, r14d
0x180050b88  test    rcx, rcx
0x180050b8b  jnz     short loc_180050B9C
0x180050b8d  lea     rcx, [rsp+21C8h+var_2158]
0x180050b92  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180050b97  jmp     loc_180050B10
0x180050b9c  mov     r8, r14; Size
0x180050b9f  xor     edx, edx; Val
0x180050ba1  call    memset_0
0x180050ba6  mov     r10d, ebx
0x180050ba9  test    edi, edi
0x180050bab  jle     short loc_180050BE6
0x180050bad  mov     r9d, r10d
0x180050bb0  shr     r9, 1
0x180050bb3  mov     r8, [rsp+21C8h+var_2158]
0x180050bb8  mov     ecx, r10d
0x180050bbb  movzx   ecx, [rsp+rcx*2+21C8h+String1]; unsigned __int16
0x180050bc3  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180050bc8  mov     edx, r10d
0x180050bcb  and     edx, 1
0x180050bce  shl     edx, 2
0x180050bd1  mov     ecx, 4
0x180050bd6  sub     ecx, edx
0x180050bd8  shl     al, cl
0x180050bda  or      [r9+r8], al
0x180050bde  inc     r10d
0x180050be1  cmp     r10d, edi
0x180050be4  jl      short loc_180050BAD
0x180050be6  mov     rax, [rsp+21C8h+var_2158]
0x180050beb  mov     [rsp+21C8h+cbData], esi; cbData
0x180050bef  mov     [rsp+21C8h+lpData], rax; lpData
0x180050bf4  mov     r9d, 3; dwType
0x180050bfa  xor     r8d, r8d; Reserved
0x180050bfd  mov     rdx, r12; lpValueName
0x180050c00  mov     rcx, [r15]; hKey
0x180050c03  call    cs:__imp_RegSetValueExW
0x180050c09  mov     edi, eax
0x180050c0b  lea     rcx, [rsp+21C8h+var_2158]
0x180050c10  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180050c15  jmp     short loc_180050C5B
0x180050c17  lea     rax, [rsp+21C8h+String1]
0x180050c1f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180050c23  inc     rdi
0x180050c26  cmp     [rax+rdi*2], bx
0x180050c2a  jnz     short loc_180050C23
0x180050c2c  lea     eax, ds:2[rdi*2]
0x180050c33  mov     [rsp+21C8h+cbData], eax; cbData
0x180050c37  lea     rax, [rsp+21C8h+String1]
0x180050c3f  mov     [rsp+21C8h+lpData], rax; lpData
0x180050c44  mov     r9d, 1; dwType
0x180050c4a  xor     r8d, r8d; Reserved
0x180050c4d  mov     rdx, r12; lpValueName
0x180050c50  mov     rcx, [r15]; hKey
0x180050c53  call    cs:__imp_RegSetValueExW
0x180050c59  mov     edi, eax
0x180050c5b  test    edi, edi
0x180050c5d  jz      short loc_180050C68
0x180050c5f  mov     ecx, edi; unsigned int
0x180050c61  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180050c66  jmp     short loc_180050C7C
0x180050c68  mov     rdx, [rsp+21C8h+var_2160]; unsigned __int16 *
0x180050c6d  mov     rcx, r13; this
0x180050c70  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180050c75  test    eax, eax
0x180050c77  cmovs   ebx, eax
0x180050c7a  mov     eax, ebx
0x180050c7c  mov     rcx, [rsp+21C8h+var_48]
0x180050c84  xor     rcx, rsp; StackCookie
0x180050c87  call    __security_check_cookie
0x180050c8c  add     rsp, 2190h
0x180050c93  pop     r15
0x180050c95  pop     r14
0x180050c97  pop     r13
0x180050c99  pop     r12
0x180050c9b  pop     rdi
0x180050c9c  pop     rsi
0x180050c9d  pop     rbx
0x180050c9e  retn
```
