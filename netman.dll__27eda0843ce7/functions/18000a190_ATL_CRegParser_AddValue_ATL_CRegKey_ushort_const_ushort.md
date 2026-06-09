# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000a190`
- end: `0x18000a746`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1462`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x180014d38`

## callees

- `0x180001710`
- `0x180002320`
- `0x1800057dc`
- `0x1800071a0`
- `0x1800081b0`
- `0x18000a190`
- `0x18000a7cc`
- `0x18000a9a8`
- `0x18000aa9c`
- `0x180012408`
- `0x1800174d4`
- `0x180034d90`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000a3ea`
- `ADVAPI32!RegSetValueExW` at `0x18000a483`
- `ADVAPI32!RegSetValueExW` at `0x18000a69c`
- `ADVAPI32!RegSetValueExW` at `0x18000a6f3`
- `ADVAPI32!RegSetValueExW` at `0x18000a3ea`
- `ADVAPI32!RegSetValueExW` at `0x18000a483`
- `ADVAPI32!RegSetValueExW` at `0x18000a69c`
- `ADVAPI32!RegSetValueExW` at `0x18000a6f3`
- `KERNEL32!lstrcmpiW` at `0x18000a22b`
- `KERNEL32!lstrcmpiW` at `0x18000a22b`
- `USER32!CharNextW` at `0x18000a365`
- `USER32!CharNextW` at `0x18000a381`
- `USER32!CharNextW` at `0x18000a365`
- `USER32!CharNextW` at `0x18000a381`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000a436`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000a436`

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
  unsigned __int64 v12; // rax
  BYTE *v13; // rdi
  HKEY *v14; // r13
  WCHAR *j; // r14
  const WCHAR *v16; // rax
  DWORD cbData; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // edi
  HRESULT v22; // edi
  __int64 v23; // rsi
  DWORD v24; // r14d
  size_t v25; // rdi
  unsigned __int64 v26; // rax
  BYTE *v27; // rcx
  HKEY *v28; // r15
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  ATL::CRegParser *v34; // [rsp+30h] [rbp-21B8h] BYREF
  LPCWSTR lpValueName; // [rsp+38h] [rbp-21B0h]
  HKEY *v36; // [rsp+40h] [rbp-21A8h]
  ATL::CRegParser *v37; // [rsp+48h] [rbp-21A0h]
  const WCHAR *v38; // [rsp+50h] [rbp-2198h]
  size_t v39; // [rsp+60h] [rbp-2188h]
  HKEY *v40; // [rsp+68h] [rbp-2180h]
  unsigned __int16 *v41; // [rsp+70h] [rbp-2178h]
  ULONG pulOut; // [rsp+78h] [rbp-2170h] BYREF
  BYTE Data[16]; // [rsp+80h] [rbp-2168h] BYREF
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v36 = a2;
  v6 = this;
  v34 = this;
  *(_QWORD *)Data = a2;
  v37 = this;
  v40 = a2;
  v38 = a3;
  v41 = a4;
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
      v32 = -1;
      do
        ++v32;
      while ( String1[v32] );
      v21 = RegSetValueExW(*a2, a3, 0, 1u, (const BYTE *)String1, 2 * v32 + 2);
      goto LABEL_80;
    case 17:
      v23 = -1;
      do
        ++v23;
      while ( String1[v23] );
      *(_DWORD *)Data = v23;
      if ( (v23 & 1) != 0 )
        return 2147500037LL;
      v24 = (int)v23 / 2;
      memset_0(&lpData, 0, 0x108u);
      lpData = 0;
      v25 = (int)v23 / 2;
      v39 = v25;
      try
      {
        v26 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v26 <= 0x100 )
        {
          v27 = v45;
          lpData = v45;
        }
        else
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v26);
          v27 = lpData;
        }
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v23) = *(_DWORD *)Data;
        v27 = lpData;
        v25 = v39;
        v34 = v37;
        v28 = v40;
        lpValueName = v38;
        v24 = v39;
        goto LABEL_47;
      }
      v28 = v36;
LABEL_47:
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        return 2147500037LL;
      }
      memset_0(v27, 0, v25);
      v29 = 0;
      if ( (int)v23 <= 0 )
      {
LABEL_76:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, lpData, v24);
        ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
        goto LABEL_34;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_74:
            v31 = v30 - 87;
            goto LABEL_75;
          }
LABEL_73:
          v31 = 0;
          goto LABEL_75;
        }
        if ( v30 == 97 )
          goto LABEL_74;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_61;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_73;
        v31 = v30 - 55;
LABEL_75:
        lpData[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v23 )
          goto LABEL_76;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_73;
LABEL_61:
      v31 = v30 - 48;
      goto LABEL_75;
    case 19:
      pulOut = 0;
      v34 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v34);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v34);
      return (unsigned int)v22;
    case 16392:
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      memset_0(&lpData, 0, 0x108u);
      lpData = 0;
      try
      {
        v12 = ATL::AtlMultiplyThrow<unsigned __int64>();
        if ( v12 <= 0x100 )
        {
          v13 = v45;
          lpData = v45;
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
        v14 = *(HKEY **)Data;
        v34 = v37;
        lpValueName = v38;
        goto LABEL_18;
      }
      v14 = v36;
LABEL_18:
      if ( v13 )
      {
        for ( j = String1; *j; v13 += 2 )
        {
          v16 = CharNextW(j);
          if ( *j == 92 && *v16 == 48 )
          {
            *(_WORD *)v13 = 0;
            j = CharNextW(v16);
          }
          else
          {
            *(_WORD *)v13 = *j++;
          }
        }
        *(_DWORD *)v13 = 0;
        if ( !lpData )
          ATL::AtlThrowImpl(-2147467259);
        cbData = 0;
        v18 = lpData;
        do
        {
          v19 = -1;
          do
            ++v19;
          while ( *(_WORD *)&v18[2 * v19] );
          v20 = (unsigned int)(v19 + 1);
          v18 += 2 * v20;
          cbData += 2 * v20;
        }
        while ( (_DWORD)v20 != 1 );
        v21 = RegSetValueExW(*v14, lpValueName, 0, 7u, lpData, cbData);
      }
      else
      {
        v21 = 14;
      }
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpData);
LABEL_34:
      v6 = v34;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v41);
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
0x18000a190  push    rbx
0x18000a192  push    rsi
0x18000a193  push    rdi
0x18000a194  push    r12
0x18000a196  push    r13
0x18000a198  push    r14
0x18000a19a  push    r15
0x18000a19c  mov     eax, 21B0h
0x18000a1a1  call    _alloca_probe
0x18000a1a6  sub     rsp, rax
0x18000a1a9  mov     rax, cs:__security_cookie
0x18000a1b0  xor     rax, rsp
0x18000a1b3  mov     [rsp+21E8h+var_48], rax
0x18000a1bb  mov     r14, r8
0x18000a1be  mov     [rsp+21E8h+lpValueName], r8
0x18000a1c3  mov     r12, rdx
0x18000a1c6  mov     [rsp+21E8h+var_21A8], rdx
0x18000a1cb  mov     r15, rcx
0x18000a1ce  mov     [rsp+21E8h+var_21B8], rcx
0x18000a1d3  mov     qword ptr [rsp+21E8h+Data], rdx
0x18000a1db  mov     [rsp+21E8h+var_21A0], rcx
0x18000a1e0  mov     [rsp+21E8h+var_2180], rdx
0x18000a1e5  mov     [rsp+21E8h+var_2198], r8
0x18000a1ea  mov     [rsp+21E8h+var_2178], r9
0x18000a1ef  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18000a1f7  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a1fc  xor     ebx, ebx
0x18000a1fe  test    eax, eax
0x18000a200  js      loc_18000A723
0x18000a206  mov     edi, ebx
0x18000a208  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000a20f  cmp     edi, 4
0x18000a212  jnb     loc_18000A71E
0x18000a218  movsxd  rsi, edi
0x18000a21b  add     rsi, rsi
0x18000a21e  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000a223  lea     rcx, [rsp+21E8h+String1]; lpString1
0x18000a22b  call    cs:__imp_lstrcmpiW
0x18000a231  test    eax, eax
0x18000a233  jz      short loc_18000A239
0x18000a235  inc     edi
0x18000a237  jmp     short loc_18000A20F
0x18000a239  movzx   edi, word ptr [r13+rsi*8+8]
0x18000a23f  mov     rcx, r15; this
0x18000a242  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x18000a247  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x18000a24f  mov     rcx, r15; this
0x18000a252  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000a257  test    eax, eax
0x18000a259  js      loc_18000A723
0x18000a25f  mov     r13d, 8
0x18000a265  cmp     di, r13w
0x18000a269  jz      loc_18000A6B6
0x18000a26f  cmp     di, 11h
0x18000a273  jz      loc_18000A49A
0x18000a279  cmp     di, 13h
0x18000a27d  jz      loc_18000A41B
0x18000a283  mov     eax, 4008h
0x18000a288  cmp     di, ax
0x18000a28b  jnz     loc_18000A708
0x18000a291  lea     rcx, [rsp+21E8h+String1]
0x18000a299  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a29d  mov     rax, rsi
0x18000a2a0  inc     rax
0x18000a2a3  cmp     [rcx+rax*2], bx
0x18000a2a7  jnz     short loc_18000A2A0
0x18000a2a9  lea     edi, [rax+2]
0x18000a2ac  xor     edx, edx; Val
0x18000a2ae  mov     r8d, 108h; Size
0x18000a2b4  lea     rcx, [rsp+21E8h+var_2158]; void *
0x18000a2bc  call    memset_0
0x18000a2c1  mov     [rsp+21E8h+var_2158], rbx
0x18000a2c9  movsxd  rcx, edi
0x18000a2cc  mov     r15d, 2
0x18000a2d2  mov     edx, r15d
0x18000a2d5  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000a2da  cmp     rax, 100h
0x18000a2e0  jbe     short loc_18000A2FC
0x18000a2e2  mov     rdx, rax
0x18000a2e5  lea     rcx, [rsp+21E8h+var_2158]
0x18000a2ed  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000a2f2  mov     rdi, [rsp+21E8h+var_2158]
0x18000a2fa  jmp     short loc_18000A30C
0x18000a2fc  lea     rdi, [rsp+21E8h+var_2150]
0x18000a304  mov     [rsp+21E8h+var_2158], rdi
0x18000a30c  mov     r13, [rsp+21E8h+var_21A8]
0x18000a311  jmp     short loc_18000A341
0x18000a313  xor     ebx, ebx
0x18000a315  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a319  lea     r15d, [rbx+2]
0x18000a31d  mov     rdi, [rsp+21E8h+var_2158]
0x18000a325  mov     r13, qword ptr [rsp+21E8h+Data]
0x18000a32d  mov     rax, [rsp+21E8h+var_21A0]
0x18000a332  mov     [rsp+21E8h+var_21B8], rax
0x18000a337  mov     rax, [rsp+21E8h+var_2198]
0x18000a33c  mov     [rsp+21E8h+lpValueName], rax
0x18000a341  test    rdi, rdi
0x18000a344  jz      loc_18000A3FF
0x18000a34a  lea     r14, [rsp+21E8h+String1]
0x18000a352  cmp     [rsp+21E8h+String1], bx
0x18000a35a  jz      short loc_18000A39B
0x18000a35c  mov     r12d, 30h ; '0'
0x18000a362  mov     rcx, r14; lpsz
0x18000a365  call    cs:__imp_CharNextW
0x18000a36b  movzx   ecx, word ptr [r14]
0x18000a36f  cmp     cx, 5Ch ; '\'
0x18000a373  jnz     short loc_18000A38C
0x18000a375  cmp     [rax], r12w
0x18000a379  jnz     short loc_18000A38C
0x18000a37b  mov     [rdi], bx
0x18000a37e  mov     rcx, rax; lpsz
0x18000a381  call    cs:__imp_CharNextW
0x18000a387  mov     r14, rax
0x18000a38a  jmp     short loc_18000A392
0x18000a38c  mov     [rdi], cx
0x18000a38f  add     r14, r15
0x18000a392  add     rdi, r15
0x18000a395  cmp     [r14], bx
0x18000a399  jnz     short loc_18000A362
0x18000a39b  mov     dword ptr [rdi], 0
0x18000a3a1  mov     r8, [rsp+21E8h+var_2158]
0x18000a3a9  test    r8, r8
0x18000a3ac  jz      short loc_18000A3F4
0x18000a3ae  mov     r10d, ebx
0x18000a3b1  mov     r9, r8
0x18000a3b4  mov     rcx, rsi
0x18000a3b7  inc     rcx
0x18000a3ba  cmp     [r9+rcx*2], bx
0x18000a3bf  jnz     short loc_18000A3B7
0x18000a3c1  inc     ecx
0x18000a3c3  lea     r9, [r9+rcx*2]
0x18000a3c7  lea     r10d, [r10+rcx*2]
0x18000a3cb  cmp     ecx, 1
0x18000a3ce  jnz     short loc_18000A3B4
0x18000a3d0  mov     [rsp+21E8h+cbData], r10d; cbData
0x18000a3d5  mov     [rsp+21E8h+lpData], r8; lpData
0x18000a3da  lea     r9d, [rcx+6]; dwType
0x18000a3de  xor     r8d, r8d; Reserved
0x18000a3e1  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18000a3e6  mov     rcx, [r13+0]; hKey
0x18000a3ea  call    cs:__imp_RegSetValueExW
0x18000a3f0  mov     edi, eax
0x18000a3f2  jmp     short loc_18000A404
0x18000a3f4  mov     ecx, 80004005h; int
0x18000a3f9  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x18000a3ff  mov     edi, 0Eh
0x18000a404  lea     rcx, [rsp+21E8h+var_2158]
0x18000a40c  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000a411  mov     r15, [rsp+21E8h+var_21B8]
0x18000a416  jmp     loc_18000A6FB
0x18000a41b  mov     [rsp+21E8h+pulOut], ebx
0x18000a41f  mov     [rsp+21E8h+var_21B8], rbx
0x18000a424  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000a429  xor     r8d, r8d; dwFlags
0x18000a42c  xor     edx, edx; lcid
0x18000a42e  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000a436  call    cs:__imp_VarUI4FromStr
0x18000a43c  mov     edi, eax
0x18000a43e  test    eax, eax
0x18000a440  jns     short loc_18000A453
0x18000a442  lea     rcx, [rsp+21E8h+var_21B8]
0x18000a447  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000a44c  mov     eax, edi
0x18000a44e  jmp     loc_18000A723
0x18000a453  mov     eax, [rsp+21E8h+pulOut]
0x18000a457  mov     dword ptr [rsp+21E8h+Data], eax
0x18000a45e  mov     [rsp+21E8h+cbData], 4; cbData
0x18000a466  lea     rax, [rsp+21E8h+Data]
0x18000a46e  mov     [rsp+21E8h+lpData], rax; lpData
0x18000a473  mov     r9d, 4; dwType
0x18000a479  xor     r8d, r8d; Reserved
0x18000a47c  mov     rdx, r14; lpValueName
0x18000a47f  mov     rcx, [r12]; hKey
0x18000a483  call    cs:__imp_RegSetValueExW
0x18000a489  mov     edi, eax
0x18000a48b  lea     rcx, [rsp+21E8h+var_21B8]
0x18000a490  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000a495  jmp     loc_18000A6FB
0x18000a49a  lea     rax, [rsp+21E8h+String1]
0x18000a4a2  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000a4a6  inc     rsi
0x18000a4a9  cmp     [rax+rsi*2], bx
0x18000a4ad  jnz     short loc_18000A4A6
0x18000a4af  mov     dword ptr [rsp+21E8h+Data], esi
0x18000a4b6  test    sil, 1
0x18000a4ba  jz      short loc_18000A4C6
0x18000a4bc  mov     eax, 80004005h
0x18000a4c1  jmp     loc_18000A723
0x18000a4c6  mov     eax, esi
0x18000a4c8  cdq
0x18000a4c9  mov     r15d, 2
0x18000a4cf  idiv    r15d
0x18000a4d2  movsxd  r14, eax
0x18000a4d5  xor     edx, edx; Val
0x18000a4d7  mov     r8d, 108h; Size
0x18000a4dd  lea     rcx, [rsp+21E8h+var_2158]; void *
0x18000a4e5  call    memset_0
0x18000a4ea  mov     [rsp+21E8h+var_2158], rbx
0x18000a4f2  mov     rdi, r14
0x18000a4f5  mov     [rsp+21E8h+var_2188], r14
0x18000a4fa  lea     edx, [r15-1]
0x18000a4fe  mov     rcx, r14
0x18000a501  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000a506  cmp     rax, 100h
0x18000a50c  jbe     short loc_18000A528
0x18000a50e  mov     rdx, rax
0x18000a511  lea     rcx, [rsp+21E8h+var_2158]
0x18000a519  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000a51e  mov     rcx, [rsp+21E8h+var_2158]
0x18000a526  jmp     short loc_18000A538
0x18000a528  lea     rcx, [rsp+21E8h+var_2150]
0x18000a530  mov     [rsp+21E8h+var_2158], rcx
0x18000a538  mov     r15, [rsp+21E8h+var_21A8]
0x18000a53d  jmp     short loc_18000A575
0x18000a53f  xor     ebx, ebx
0x18000a541  lea     r13d, [rbx+8]
0x18000a545  mov     esi, dword ptr [rsp+21E8h+Data]
0x18000a54c  mov     rcx, [rsp+21E8h+var_2158]; void *
0x18000a554  mov     rdi, [rsp+21E8h+var_2188]
0x18000a559  mov     rax, [rsp+21E8h+var_21A0]
0x18000a55e  mov     [rsp+21E8h+var_21B8], rax
0x18000a563  mov     r15, [rsp+21E8h+var_2180]
0x18000a568  mov     rax, [rsp+21E8h+var_2198]
0x18000a56d  mov     [rsp+21E8h+lpValueName], rax
0x18000a572  mov     r14d, edi
0x18000a575  test    rcx, rcx
0x18000a578  jnz     short loc_18000A58C
0x18000a57a  lea     rcx, [rsp+21E8h+var_2158]
0x18000a582  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000a587  jmp     loc_18000A4BC
0x18000a58c  mov     r8, rdi; Size
0x18000a58f  xor     edx, edx; Val
0x18000a591  call    memset_0
0x18000a596  mov     r10d, ebx
0x18000a599  test    esi, esi
0x18000a59b  jle     loc_18000A679
0x18000a5a1  mov     r12d, 30h ; '0'
0x18000a5a7  mov     eax, r10d
0x18000a5aa  movzx   edx, [rsp+rax*2+21E8h+String1]
0x18000a5b2  cmp     edx, 61h ; 'a'
0x18000a5b5  ja      short loc_18000A624
0x18000a5b7  jz      loc_18000A644
0x18000a5bd  cmp     edx, 38h ; '8'
0x18000a5c0  ja      short loc_18000A5F6
0x18000a5c2  jz      short loc_18000A5EE
0x18000a5c4  mov     ecx, edx
0x18000a5c6  sub     ecx, r12d
0x18000a5c9  jz      short loc_18000A5EE
0x18000a5cb  sub     ecx, 1
0x18000a5ce  jz      short loc_18000A5EE
0x18000a5d0  sub     ecx, 1
0x18000a5d3  jz      short loc_18000A5EE
0x18000a5d5  sub     ecx, 1
0x18000a5d8  jz      short loc_18000A5EE
0x18000a5da  sub     ecx, 1
0x18000a5dd  jz      short loc_18000A5EE
0x18000a5df  sub     ecx, 1
0x18000a5e2  jz      short loc_18000A5EE
0x18000a5e4  sub     ecx, 1
0x18000a5e7  jz      short loc_18000A5EE
0x18000a5e9  cmp     ecx, 1
0x18000a5ec  jnz     short loc_18000A63F
0x18000a5ee  mov     r9d, edx
0x18000a5f1  sub     r9d, r12d
0x18000a5f4  jmp     short loc_18000A648
0x18000a5f6  mov     r9d, edx
0x18000a5f9  mov     ecx, edx
0x18000a5fb  sub     ecx, 39h ; '9'
0x18000a5fe  jz      short loc_18000A5EE
0x18000a600  sub     ecx, r13d
0x18000a603  jz      short loc_18000A61E
0x18000a605  sub     ecx, 1
0x18000a608  jz      short loc_18000A61E
0x18000a60a  sub     ecx, 1
0x18000a60d  jz      short loc_18000A61E
0x18000a60f  sub     ecx, 1
0x18000a612  jz      short loc_18000A61E
0x18000a614  sub     ecx, 1
0x18000a617  jz      short loc_18000A61E
0x18000a619  cmp     ecx, 1
0x18000a61c  jnz     short loc_18000A63F
0x18000a61e  add     r9d, 0FFFFFFC9h
0x18000a622  jmp     short loc_18000A648
0x18000a624  mov     ecx, edx
0x18000a626  sub     ecx, 62h ; 'b'
0x18000a629  jz      short loc_18000A644
0x18000a62b  sub     ecx, 1
0x18000a62e  jz      short loc_18000A644
0x18000a630  sub     ecx, 1
0x18000a633  jz      short loc_18000A644
0x18000a635  sub     ecx, 1
0x18000a638  jz      short loc_18000A644
0x18000a63a  cmp     ecx, 1
0x18000a63d  jz      short loc_18000A644
0x18000a63f  mov     r9d, ebx
0x18000a642  jmp     short loc_18000A648
0x18000a644  lea     r9d, [rdx-57h]
0x18000a648  mov     r8d, r10d
0x18000a64b  shr     r8, 1
0x18000a64e  mov     rdx, [rsp+21E8h+var_2158]
  ... truncated ...
```
