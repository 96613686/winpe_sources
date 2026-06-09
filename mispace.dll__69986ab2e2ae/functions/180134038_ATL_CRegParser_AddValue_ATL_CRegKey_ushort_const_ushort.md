# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180134038`
- end: `0x180134410`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `984`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config`

## callers

- `0x18013674c`

## callees

- `0x180006350`
- `0x180006dd4`
- `0x1801338b0`
- `0x180133988`
- `0x180133a34`
- `0x180134038`
- `0x180134418`
- `0x1801345ac`
- `0x1801346d4`
- `0x180135db4`
- `0x180136fb4`
- `0x18013783c`
- `0x1801fa390`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801341ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180134273`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18013436d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801343bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801341ec`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180134273`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18013436d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1801343bd`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180134227`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180134227`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134161`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134183`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134161`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180134183`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  ATL::CRegParser *v7; // r14
  __int64 result; // rax
  __int64 v9; // rax
  unsigned __int64 v10; // rax
  BYTE *v11; // rdi
  WCHAR *v12; // rsi
  const WCHAR *v13; // rax
  DWORD cbData; // r9d
  BYTE *v15; // r8
  __int64 v16; // rcx
  __int64 v17; // rcx
  LSTATUS v18; // ebx
  HRESULT v19; // ebx
  HKEY v20; // rcx
  __int64 v21; // rbx
  size_t v22; // rsi
  unsigned __int64 v23; // rax
  BYTE *v24; // rcx
  int i; // r10d
  unsigned __int8 v26; // al
  int v27; // r10d
  char v28; // dl
  __int64 v29; // r8
  __int64 v30; // r9
  __int64 v31; // rbx
  int Token; // eax
  unsigned int v33; // ecx
  ULONG pulOut; // [rsp+30h] [rbp-D0h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-C8h] BYREF
  BYTE Data[16]; // [rsp+40h] [rbp-C0h] BYREF
  BYTE *lpData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v38[264]; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[4096]; // [rsp+160h] [rbp+60h] BYREF

  v35 = this;
  LOWORD(pulOut) = 0;
  v7 = this;
  result = ATL::CRegParser::NextToken(this, sz);
  if ( (int)result >= 0 )
  {
    if ( !(unsigned int)ATL::CRegParser::VTFromRegType(sz, (unsigned __int16 *)&pulOut) )
      return 2147614729LL;
    ATL::CRegParser::SkipWhiteSpace(v7);
    result = ATL::CRegParser::NextToken(v7, sz);
    if ( (int)result >= 0 )
    {
      if ( (unsigned __int16)pulOut == 8 )
      {
        v31 = -1;
        do
          ++v31;
        while ( sz[v31] );
        v18 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)sz, 2 * v31 + 2);
        goto LABEL_47;
      }
      if ( (unsigned __int16)pulOut != 17 )
      {
        if ( (unsigned __int16)pulOut == 19 )
        {
          pulOut = 0;
          v35 = 0;
          v19 = VarUI4FromStr(sz, 0, 0, &pulOut);
          if ( v19 < 0 )
          {
            ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
            return (unsigned int)v19;
          }
          v20 = *a2;
          *(_DWORD *)Data = pulOut;
          v18 = RegSetValueExW(v20, a3, 0, 4u, Data, 4u);
          ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v35);
        }
        else
        {
          if ( (unsigned __int16)pulOut != 16392 )
          {
LABEL_49:
            Token = ATL::CRegParser::NextToken(v7, a4);
            v33 = 0;
            if ( Token < 0 )
              return (unsigned int)Token;
            return v33;
          }
          lpData = 0;
          v9 = -1;
          do
            ++v9;
          while ( sz[v9] );
          v10 = ATL::AtlMultiplyThrow<unsigned __int64>((int)v9 + 2, 2);
          if ( v10 <= 0x100 )
          {
            v11 = v38;
            lpData = v38;
          }
          else
          {
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v10);
            v11 = lpData;
          }
          if ( v11 )
          {
            v12 = sz;
            if ( sz[0] )
            {
              do
              {
                v13 = CharNextW(v12);
                if ( *v12 == 92 && *v13 == 48 )
                {
                  *(_WORD *)v11 = 0;
                  v12 = CharNextW(v13);
                }
                else
                {
                  *(_WORD *)v11 = *v12++;
                }
                v11 += 2;
              }
              while ( *v12 );
              v7 = v35;
            }
            *(_DWORD *)v11 = 0;
            cbData = 0;
            v15 = lpData;
            do
            {
              v16 = -1;
              do
                ++v16;
              while ( *(_WORD *)&v15[2 * v16] );
              v17 = (unsigned int)(v16 + 1);
              v15 += 2 * v17;
              cbData += 2 * v17;
            }
            while ( (_DWORD)v17 != 1 );
            v18 = RegSetValueExW(*a2, a3, 0, 7u, lpData, cbData);
          }
          else
          {
            v18 = 14;
          }
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        }
LABEL_47:
        if ( v18 )
          return ATL::AtlHresultFromWin32(v18);
        goto LABEL_49;
      }
      v21 = -1;
      do
        ++v21;
      while ( sz[v21] );
      if ( (v21 & 1) == 0 )
      {
        lpData = 0;
        v22 = (int)v21 / 2;
        v23 = ATL::AtlMultiplyThrow<unsigned __int64>(v22, 1);
        if ( v23 <= 0x100 )
        {
          v24 = v38;
          lpData = v38;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v23);
          v24 = lpData;
        }
        if ( v24 )
        {
          memset_0(v24, 0, v22);
          for ( i = 0; i < (int)v21; *(_BYTE *)(v30 + v29) |= v26 << (4 - 4 * v28) )
          {
            v26 = ATL::CRegParser::ChToByte(sz[i]);
            v28 = v27 & 1;
            i = v27 + 1;
          }
          v18 = RegSetValueExW(*a2, a3, 0, 3u, lpData, v22);
          ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
          goto LABEL_47;
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
0x180134038  push    rbp
0x18013403a  push    rbx
0x18013403b  push    rsi
0x18013403c  push    rdi
0x18013403d  push    r12
0x18013403f  push    r13
0x180134041  push    r14
0x180134043  push    r15
0x180134045  lea     rbp, [rsp-2078h]
0x18013404d  mov     eax, 2178h
0x180134052  call    _alloca_probe
0x180134057  sub     rsp, rax
0x18013405a  mov     rax, cs:__security_cookie
0x180134061  xor     rax, rsp
0x180134064  mov     [rbp+20B0h+var_50], rax
0x18013406b  mov     r15, rdx
0x18013406e  mov     [rsp+21B0h+var_2178], rcx
0x180134073  xor     esi, esi
0x180134075  lea     rdx, [rbp+20B0h+sz]; unsigned __int16 *
0x180134079  mov     word ptr [rsp+21B0h+pulOut], si
0x18013407e  mov     r13, r9
0x180134081  mov     r12, r8
0x180134084  mov     r14, rcx
0x180134087  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18013408c  test    eax, eax
0x18013408e  js      loc_1801343EC
0x180134094  lea     rdx, [rsp+21B0h+pulOut]; unsigned __int16 *
0x180134099  lea     rcx, [rbp+20B0h+sz]; lpString1
0x18013409d  call    ?VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z; ATL::CRegParser::VTFromRegType(ushort const *,ushort &)
0x1801340a2  test    eax, eax
0x1801340a4  jnz     short loc_1801340B0
0x1801340a6  mov     eax, 80020009h
0x1801340ab  jmp     loc_1801343EC
0x1801340b0  mov     rcx, r14; this
0x1801340b3  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x1801340b8  lea     rdx, [rbp+20B0h+sz]; unsigned __int16 *
0x1801340bc  mov     rcx, r14; this
0x1801340bf  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801340c4  test    eax, eax
0x1801340c6  js      loc_1801343EC
0x1801340cc  movzx   eax, word ptr [rsp+21B0h+pulOut]
0x1801340d1  cmp     eax, 8
0x1801340d4  jz      loc_180134389
0x1801340da  cmp     eax, 11h
0x1801340dd  jz      loc_180134290
0x1801340e3  cmp     eax, 13h
0x1801340e6  jz      loc_180134210
0x1801340ec  cmp     eax, 4008h
0x1801340f1  jnz     loc_1801343D8
0x1801340f7  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1801340fb  mov     [rsp+21B0h+var_2160], rsi
0x180134100  mov     rax, rbx
0x180134103  lea     rcx, [rbp+20B0h+sz]
0x180134107  inc     rax
0x18013410a  cmp     [rcx+rax*2], si
0x18013410e  jnz     short loc_180134107
0x180134110  add     eax, 2
0x180134113  mov     edx, 2
0x180134118  movsxd  rcx, eax
0x18013411b  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180134120  cmp     rax, 100h
0x180134126  jbe     short loc_18013413C
0x180134128  mov     rdx, rax
0x18013412b  lea     rcx, [rsp+21B0h+var_2160]
0x180134130  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180134135  mov     rdi, [rsp+21B0h+var_2160]
0x18013413a  jmp     short loc_180134146
0x18013413c  lea     rdi, [rsp+21B0h+var_2158]
0x180134141  mov     [rsp+21B0h+var_2160], rdi
0x180134146  test    rdi, rdi
0x180134149  jz      loc_1801341FC
0x18013414f  xor     eax, eax
0x180134151  lea     rsi, [rbp+20B0h+sz]
0x180134155  cmp     [rbp+20B0h+sz], ax
0x180134159  jz      short loc_1801341AA
0x18013415b  xor     r14d, r14d
0x18013415e  mov     rcx, rsi; lpsz
0x180134161  call    cs:__imp_CharNextW
0x180134168  nop     dword ptr [rax+rax+00h]
0x18013416d  movzx   ecx, word ptr [rsi]
0x180134170  cmp     cx, 5Ch ; '\'
0x180134174  jnz     short loc_180134194
0x180134176  cmp     word ptr [rax], 30h ; '0'
0x18013417a  jnz     short loc_180134194
0x18013417c  mov     rcx, rax; lpsz
0x18013417f  mov     [rdi], r14w
0x180134183  call    cs:__imp_CharNextW
0x18013418a  nop     dword ptr [rax+rax+00h]
0x18013418f  mov     rsi, rax
0x180134192  jmp     short loc_18013419B
0x180134194  mov     [rdi], cx
0x180134197  add     rsi, 2
0x18013419b  add     rdi, 2
0x18013419f  cmp     [rsi], r14w
0x1801341a3  jnz     short loc_18013415E
0x1801341a5  mov     r14, [rsp+21B0h+var_2178]
0x1801341aa  xor     esi, esi
0x1801341ac  mov     [rdi], esi
0x1801341ae  mov     r9d, esi
0x1801341b1  mov     r10, [rsp+21B0h+var_2160]
0x1801341b6  mov     r8, r10
0x1801341b9  mov     rcx, rbx
0x1801341bc  inc     rcx
0x1801341bf  cmp     [r8+rcx*2], si
0x1801341c4  jnz     short loc_1801341BC
0x1801341c6  inc     ecx
0x1801341c8  lea     r8, [r8+rcx*2]
0x1801341cc  lea     r9d, [r9+rcx*2]
0x1801341d0  cmp     ecx, 1
0x1801341d3  jnz     short loc_1801341B9
0x1801341d5  mov     [rsp+21B0h+cbData], r9d; cbData
0x1801341da  xor     r8d, r8d; Reserved
0x1801341dd  lea     r9d, [rcx+6]; dwType
0x1801341e1  mov     [rsp+21B0h+lpData], r10; lpData
0x1801341e6  mov     rcx, [r15]; hKey
0x1801341e9  mov     rdx, r12; lpValueName
0x1801341ec  call    cs:__imp_RegSetValueExW
0x1801341f3  nop     dword ptr [rax+rax+00h]
0x1801341f8  mov     ebx, eax
0x1801341fa  jmp     short loc_180134201
0x1801341fc  mov     ebx, 0Eh
0x180134201  lea     rcx, [rsp+21B0h+var_2160]
0x180134206  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18013420b  jmp     loc_1801343CB
0x180134210  lea     r9, [rsp+21B0h+pulOut]; pulOut
0x180134215  mov     [rsp+21B0h+pulOut], esi
0x180134219  xor     r8d, r8d; dwFlags
0x18013421c  mov     [rsp+21B0h+var_2178], rsi
0x180134221  xor     edx, edx; lcid
0x180134223  lea     rcx, [rbp+20B0h+sz]; strIn
0x180134227  call    cs:__imp_VarUI4FromStr
0x18013422e  nop     dword ptr [rax+rax+00h]
0x180134233  mov     ebx, eax
0x180134235  test    eax, eax
0x180134237  jns     short loc_18013424A
0x180134239  lea     rcx, [rsp+21B0h+var_2178]
0x18013423e  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180134243  mov     eax, ebx
0x180134245  jmp     loc_1801343EC
0x18013424a  mov     eax, [rsp+21B0h+pulOut]
0x18013424e  mov     r9d, 4; dwType
0x180134254  mov     rcx, [r15]; hKey
0x180134257  xor     r8d, r8d; Reserved
0x18013425a  mov     dword ptr [rsp+21B0h+Data], eax
0x18013425e  mov     rdx, r12; lpValueName
0x180134261  lea     rax, [rsp+21B0h+Data]
0x180134266  mov     [rsp+21B0h+cbData], 4; cbData
0x18013426e  mov     [rsp+21B0h+lpData], rax; lpData
0x180134273  call    cs:__imp_RegSetValueExW
0x18013427a  nop     dword ptr [rax+rax+00h]
0x18013427f  lea     rcx, [rsp+21B0h+var_2178]
0x180134284  mov     ebx, eax
0x180134286  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18013428b  jmp     loc_1801343CB
0x180134290  lea     rax, [rbp+20B0h+sz]
0x180134294  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180134298  inc     rbx
0x18013429b  cmp     [rax+rbx*2], si
0x18013429f  jnz     short loc_180134298
0x1801342a1  test    bl, 1
0x1801342a4  jz      short loc_1801342B0
0x1801342a6  mov     eax, 80004005h
0x1801342ab  jmp     loc_1801343EC
0x1801342b0  mov     eax, ebx
0x1801342b2  mov     [rsp+21B0h+var_2160], 0
0x1801342bb  cdq
0x1801342bc  sub     eax, edx
0x1801342be  mov     edx, 1
0x1801342c3  sar     eax, 1
0x1801342c5  movsxd  rsi, eax
0x1801342c8  mov     rcx, rsi
0x1801342cb  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1801342d0  cmp     rax, 100h
0x1801342d6  jbe     short loc_1801342EC
0x1801342d8  mov     rdx, rax
0x1801342db  lea     rcx, [rsp+21B0h+var_2160]
0x1801342e0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1801342e5  mov     rcx, [rsp+21B0h+var_2160]
0x1801342ea  jmp     short loc_1801342F6
0x1801342ec  lea     rcx, [rsp+21B0h+var_2158]; void *
0x1801342f1  mov     [rsp+21B0h+var_2160], rcx
0x1801342f6  test    rcx, rcx
0x1801342f9  jnz     short loc_180134307
0x1801342fb  lea     rcx, [rsp+21B0h+var_2160]
0x180134300  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180134305  jmp     short loc_1801342A6
0x180134307  mov     r8, rsi; Size
0x18013430a  xor     edx, edx; Val
0x18013430c  call    memset_0
0x180134311  xor     eax, eax
0x180134313  mov     r10d, eax
0x180134316  test    ebx, ebx
0x180134318  jle     short loc_180134350
0x18013431a  mov     r8, [rsp+21B0h+var_2160]
0x18013431f  mov     ecx, r10d
0x180134322  mov     r9d, r10d
0x180134325  shr     r9, 1
0x180134328  movzx   ecx, [rbp+rcx*2+20B0h+sz]; unsigned __int16
0x18013432d  call    ?ChToByte@CRegParser@ATL@@KAEG@Z; ATL::CRegParser::ChToByte(ushort)
0x180134332  mov     edx, r10d
0x180134335  mov     ecx, 4
0x18013433a  and     edx, 1
0x18013433d  inc     r10d
0x180134340  shl     edx, 2
0x180134343  sub     ecx, edx
0x180134345  shl     al, cl
0x180134347  or      [r9+r8], al
0x18013434b  cmp     r10d, ebx
0x18013434e  jl      short loc_18013431A
0x180134350  mov     rax, [rsp+21B0h+var_2160]
0x180134355  mov     r9d, 3; dwType
0x18013435b  mov     rcx, [r15]; hKey
0x18013435e  xor     r8d, r8d; Reserved
0x180134361  mov     [rsp+21B0h+cbData], esi; cbData
0x180134365  mov     rdx, r12; lpValueName
0x180134368  mov     [rsp+21B0h+lpData], rax; lpData
0x18013436d  call    cs:__imp_RegSetValueExW
0x180134374  nop     dword ptr [rax+rax+00h]
0x180134379  lea     rcx, [rsp+21B0h+var_2160]
0x18013437e  mov     ebx, eax
0x180134380  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180134385  xor     esi, esi
0x180134387  jmp     short loc_1801343CB
0x180134389  lea     rax, [rbp+20B0h+sz]
0x18013438d  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180134391  inc     rbx
0x180134394  cmp     [rax+rbx*2], si
0x180134398  jnz     short loc_180134391
0x18013439a  mov     rcx, [r15]; hKey
0x18013439d  lea     eax, ds:2[rbx*2]
0x1801343a4  mov     [rsp+21B0h+cbData], eax; cbData
0x1801343a8  mov     r9d, 1; dwType
0x1801343ae  lea     rax, [rbp+20B0h+sz]
0x1801343b2  xor     r8d, r8d; Reserved
0x1801343b5  mov     rdx, r12; lpValueName
0x1801343b8  mov     [rsp+21B0h+lpData], rax; lpData
0x1801343bd  call    cs:__imp_RegSetValueExW
0x1801343c4  nop     dword ptr [rax+rax+00h]
0x1801343c9  mov     ebx, eax
0x1801343cb  test    ebx, ebx
0x1801343cd  jz      short loc_1801343D8
0x1801343cf  mov     ecx, ebx; unsigned int
0x1801343d1  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x1801343d6  jmp     short loc_1801343EC
0x1801343d8  mov     rdx, r13; unsigned __int16 *
0x1801343db  mov     rcx, r14; this
0x1801343de  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1801343e3  test    eax, eax
0x1801343e5  mov     ecx, esi
0x1801343e7  cmovs   ecx, eax
0x1801343ea  mov     eax, ecx
0x1801343ec  mov     rcx, [rbp+20B0h+var_50]
0x1801343f3  xor     rcx, rsp; StackCookie
0x1801343f6  call    __security_check_cookie
0x1801343fb  add     rsp, 2178h
0x180134402  pop     r15
0x180134404  pop     r14
0x180134406  pop     r13
0x180134408  pop     r12
0x18013440a  pop     rdi
0x18013440b  pop     rsi
0x18013440c  pop     rbx
0x18013440d  pop     rbp
0x18013440e  retn
```
