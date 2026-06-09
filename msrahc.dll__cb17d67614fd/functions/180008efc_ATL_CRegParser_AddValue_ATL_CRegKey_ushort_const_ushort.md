# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180008efc`
- end: `0x18000947c`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1408`
- prototype: `__int64 __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config`

## callers

- `0x18000b44c`

## callees

- `0x18000873c`
- `0x18000882c`
- `0x180008948`
- `0x180008efc`
- `0x180009484`
- `0x180009718`
- `0x180009e80`
- `0x18000aaa0`
- `0x18000bc50`
- `0x18001a5a2`
- `0x18001a5e0`
- `0x18001a6a0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000913e`
- `ADVAPI32!RegSetValueExW` at `0x1800091d1`
- `ADVAPI32!RegSetValueExW` at `0x1800093cf`
- `ADVAPI32!RegSetValueExW` at `0x180009426`
- `ADVAPI32!RegSetValueExW` at `0x18000913e`
- `ADVAPI32!RegSetValueExW` at `0x1800091d1`
- `ADVAPI32!RegSetValueExW` at `0x1800093cf`
- `ADVAPI32!RegSetValueExW` at `0x180009426`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000918a`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000918a`
- `USER32!CharNextW` at `0x1800090b9`
- `USER32!CharNextW` at `0x1800090d5`
- `USER32!CharNextW` at `0x1800090b9`
- `USER32!CharNextW` at `0x1800090d5`
- `KERNEL32!lstrcmpiW` at `0x180008f97`
- `KERNEL32!lstrcmpiW` at `0x180008f97`

## pseudocode

```c
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
  ULONG pulOut; // [rsp+30h] [rbp-21B8h] BYREF
  ATL::CRegParser *v35; // [rsp+38h] [rbp-21B0h] BYREF
  BYTE Data[8]; // [rsp+40h] [rbp-21A8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-21A0h]
  HKEY *v38; // [rsp+50h] [rbp-2198h]
  ATL::CRegParser *v39; // [rsp+58h] [rbp-2190h]
  const WCHAR *v40; // [rsp+60h] [rbp-2188h]
  size_t v41; // [rsp+70h] [rbp-2178h]
  HKEY *v42; // [rsp+78h] [rbp-2170h]
  unsigned __int16 *v43; // [rsp+80h] [rbp-2168h]
  BYTE *lpData; // [rsp+90h] [rbp-2158h] BYREF
  _BYTE v45[264]; // [rsp+98h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+1A0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v38 = a2;
  v6 = this;
  v35 = this;
  *(_QWORD *)Data = a2;
  v39 = this;
  v42 = a2;
  v40 = a3;
  v43 = a4;
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
      lpData = 0;
      v25 = (int)v23 / 2;
      v41 = v25;
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
        v25 = v41;
        v35 = v39;
        v28 = v42;
        lpValueName = v40;
        v24 = v41;
        goto LABEL_47;
      }
      v28 = v38;
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
      v35 = 0;
      v22 = VarUI4FromStr(String1, 0, 0, &pulOut);
      if ( v22 >= 0 )
      {
        *(_DWORD *)Data = pulOut;
        v21 = RegSetValueExW(*a2, a3, 0, 4u, Data, 4u);
        ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
        goto LABEL_80;
      }
      ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>((_QWORD **)&v35);
      return (unsigned int)v22;
    case 16392:
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
        v35 = v39;
        lpValueName = v40;
        goto LABEL_18;
      }
      v14 = v38;
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
      v6 = v35;
LABEL_80:
      if ( v21 )
      {
        return ATL::AtlHresultFromWin32(v21);
      }
      else
      {
LABEL_82:
        Token = ATL::CRegParser::NextToken(v6, v43);
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
0x180008efc  push    rbx
0x180008efe  push    rsi
0x180008eff  push    rdi
0x180008f00  push    r12
0x180008f02  push    r13
0x180008f04  push    r14
0x180008f06  push    r15
0x180008f08  mov     eax, 21B0h
0x180008f0d  call    _alloca_probe
0x180008f12  sub     rsp, rax
0x180008f15  mov     rax, cs:__security_cookie
0x180008f1c  xor     rax, rsp
0x180008f1f  mov     [rsp+21E8h+var_48], rax
0x180008f27  mov     r14, r8
0x180008f2a  mov     [rsp+21E8h+lpValueName], r8
0x180008f2f  mov     r12, rdx
0x180008f32  mov     [rsp+21E8h+var_2198], rdx
0x180008f37  mov     r15, rcx
0x180008f3a  mov     [rsp+21E8h+var_21B0], rcx
0x180008f3f  mov     qword ptr [rsp+21E8h+Data], rdx
0x180008f44  mov     [rsp+21E8h+var_2190], rcx
0x180008f49  mov     [rsp+21E8h+var_2170], rdx
0x180008f4e  mov     [rsp+21E8h+var_2188], r8
0x180008f53  mov     [rsp+21E8h+var_2168], r9
0x180008f5b  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180008f63  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008f68  xor     ebx, ebx
0x180008f6a  test    eax, eax
0x180008f6c  js      loc_180009459
0x180008f72  mov     edi, ebx
0x180008f74  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180008f7b  cmp     edi, 4
0x180008f7e  jnb     loc_180009454
0x180008f84  movsxd  rsi, edi
0x180008f87  add     rsi, rsi
0x180008f8a  mov     rdx, [r13+rsi*8+0]; lpString2
0x180008f8f  lea     rcx, [rsp+21E8h+String1]; lpString1
0x180008f97  call    cs:__imp_lstrcmpiW
0x180008f9d  test    eax, eax
0x180008f9f  jz      short loc_180008FA5
0x180008fa1  inc     edi
0x180008fa3  jmp     short loc_180008F7B
0x180008fa5  movzx   edi, word ptr [r13+rsi*8+8]
0x180008fab  mov     rcx, r15; this
0x180008fae  call    ?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ; ATL::CRegParser::SkipWhiteSpace(void)
0x180008fb3  lea     rdx, [rsp+21E8h+String1]; unsigned __int16 *
0x180008fbb  mov     rcx, r15; this
0x180008fbe  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180008fc3  test    eax, eax
0x180008fc5  js      loc_180009459
0x180008fcb  mov     r13d, 8
0x180008fd1  cmp     di, r13w
0x180008fd5  jz      loc_1800093E9
0x180008fdb  cmp     di, 11h
0x180008fdf  jz      loc_1800091E8
0x180008fe5  cmp     di, 13h
0x180008fe9  jz      loc_18000916F
0x180008fef  mov     eax, 4008h
0x180008ff4  cmp     di, ax
0x180008ff7  jnz     loc_18000943B
0x180008ffd  lea     rcx, [rsp+21E8h+String1]
0x180009005  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009009  mov     rax, rsi
0x18000900c  inc     rax
0x18000900f  cmp     [rcx+rax*2], bx
0x180009013  jnz     short loc_18000900C
0x180009015  add     eax, 2
0x180009018  mov     [rsp+21E8h+var_2158], rbx
0x180009020  movsxd  rcx, eax
0x180009023  mov     r15d, 2
0x180009029  mov     edx, r15d
0x18000902c  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180009031  cmp     rax, 100h
0x180009037  jbe     short loc_180009053
0x180009039  mov     rdx, rax
0x18000903c  lea     rcx, [rsp+21E8h+var_2158]
0x180009044  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180009049  mov     rdi, [rsp+21E8h+var_2158]
0x180009051  jmp     short loc_180009063
0x180009053  lea     rdi, [rsp+21E8h+var_2150]
0x18000905b  mov     [rsp+21E8h+var_2158], rdi
0x180009063  mov     r13, [rsp+21E8h+var_2198]
0x180009068  jmp     short loc_180009095
0x18000906a  xor     ebx, ebx
0x18000906c  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180009070  lea     r15d, [rbx+2]
0x180009074  mov     rdi, [rsp+21E8h+var_2158]
0x18000907c  mov     r13, qword ptr [rsp+21E8h+Data]
0x180009081  mov     rax, [rsp+21E8h+var_2190]
0x180009086  mov     [rsp+21E8h+var_21B0], rax
0x18000908b  mov     rax, [rsp+21E8h+var_2188]
0x180009090  mov     [rsp+21E8h+lpValueName], rax
0x180009095  test    rdi, rdi
0x180009098  jz      loc_180009153
0x18000909e  lea     r14, [rsp+21E8h+String1]
0x1800090a6  cmp     [rsp+21E8h+String1], bx
0x1800090ae  jz      short loc_1800090EF
0x1800090b0  mov     r12d, 30h ; '0'
0x1800090b6  mov     rcx, r14; lpsz
0x1800090b9  call    cs:__imp_CharNextW
0x1800090bf  movzx   ecx, word ptr [r14]
0x1800090c3  cmp     cx, 5Ch ; '\'
0x1800090c7  jnz     short loc_1800090E0
0x1800090c9  cmp     [rax], r12w
0x1800090cd  jnz     short loc_1800090E0
0x1800090cf  mov     [rdi], bx
0x1800090d2  mov     rcx, rax; lpsz
0x1800090d5  call    cs:__imp_CharNextW
0x1800090db  mov     r14, rax
0x1800090de  jmp     short loc_1800090E6
0x1800090e0  mov     [rdi], cx
0x1800090e3  add     r14, r15
0x1800090e6  add     rdi, r15
0x1800090e9  cmp     [r14], bx
0x1800090ed  jnz     short loc_1800090B6
0x1800090ef  mov     dword ptr [rdi], 0
0x1800090f5  mov     r8, [rsp+21E8h+var_2158]
0x1800090fd  test    r8, r8
0x180009100  jz      short loc_180009148
0x180009102  mov     r10d, ebx
0x180009105  mov     r9, r8
0x180009108  mov     rcx, rsi
0x18000910b  inc     rcx
0x18000910e  cmp     [r9+rcx*2], bx
0x180009113  jnz     short loc_18000910B
0x180009115  inc     ecx
0x180009117  lea     r9, [r9+rcx*2]
0x18000911b  lea     r10d, [r10+rcx*2]
0x18000911f  cmp     ecx, 1
0x180009122  jnz     short loc_180009108
0x180009124  mov     [rsp+21E8h+cbData], r10d; cbData
0x180009129  mov     [rsp+21E8h+lpData], r8; lpData
0x18000912e  lea     r9d, [rcx+6]; dwType
0x180009132  xor     r8d, r8d; Reserved
0x180009135  mov     rdx, [rsp+21E8h+lpValueName]; lpValueName
0x18000913a  mov     rcx, [r13+0]; hKey
0x18000913e  call    cs:__imp_RegSetValueExW
0x180009144  mov     edi, eax
0x180009146  jmp     short loc_180009158
0x180009148  mov     ecx, 80004005h; int
0x18000914d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180009153  mov     edi, 0Eh
0x180009158  lea     rcx, [rsp+21E8h+var_2158]
0x180009160  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180009165  mov     r15, [rsp+21E8h+var_21B0]
0x18000916a  jmp     loc_18000942E
0x18000916f  mov     [rsp+21E8h+pulOut], ebx
0x180009173  mov     [rsp+21E8h+var_21B0], rbx
0x180009178  lea     r9, [rsp+21E8h+pulOut]; pulOut
0x18000917d  xor     r8d, r8d; dwFlags
0x180009180  xor     edx, edx; lcid
0x180009182  lea     rcx, [rsp+21E8h+String1]; strIn
0x18000918a  call    cs:__imp_VarUI4FromStr
0x180009190  mov     edi, eax
0x180009192  test    eax, eax
0x180009194  jns     short loc_1800091A7
0x180009196  lea     rcx, [rsp+21E8h+var_21B0]
0x18000919b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800091a0  mov     eax, edi
0x1800091a2  jmp     loc_180009459
0x1800091a7  mov     eax, [rsp+21E8h+pulOut]
0x1800091ab  mov     dword ptr [rsp+21E8h+Data], eax
0x1800091af  mov     [rsp+21E8h+cbData], 4; cbData
0x1800091b7  lea     rax, [rsp+21E8h+Data]
0x1800091bc  mov     [rsp+21E8h+lpData], rax; lpData
0x1800091c1  mov     r9d, 4; dwType
0x1800091c7  xor     r8d, r8d; Reserved
0x1800091ca  mov     rdx, r14; lpValueName
0x1800091cd  mov     rcx, [r12]; hKey
0x1800091d1  call    cs:__imp_RegSetValueExW
0x1800091d7  mov     edi, eax
0x1800091d9  lea     rcx, [rsp+21E8h+var_21B0]
0x1800091de  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800091e3  jmp     loc_18000942E
0x1800091e8  lea     rax, [rsp+21E8h+String1]
0x1800091f0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x1800091f4  inc     rsi
0x1800091f7  cmp     [rax+rsi*2], bx
0x1800091fb  jnz     short loc_1800091F4
0x1800091fd  mov     dword ptr [rsp+21E8h+Data], esi
0x180009201  test    sil, 1
0x180009205  jz      short loc_180009211
0x180009207  mov     eax, 80004005h
0x18000920c  jmp     loc_180009459
0x180009211  mov     eax, esi
0x180009213  cdq
0x180009214  mov     r15d, 2
0x18000921a  idiv    r15d
0x18000921d  movsxd  r14, eax
0x180009220  mov     [rsp+21E8h+var_2158], rbx
0x180009228  mov     rdi, r14
0x18000922b  mov     [rsp+21E8h+var_2178], r14
0x180009230  lea     edx, [r15-1]
0x180009234  mov     rcx, r14
0x180009237  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000923c  cmp     rax, 100h
0x180009242  jbe     short loc_18000925E
0x180009244  mov     rdx, rax
0x180009247  lea     rcx, [rsp+21E8h+var_2158]
0x18000924f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180009254  mov     rcx, [rsp+21E8h+var_2158]
0x18000925c  jmp     short loc_18000926E
0x18000925e  lea     rcx, [rsp+21E8h+var_2150]
0x180009266  mov     [rsp+21E8h+var_2158], rcx
0x18000926e  mov     r15, [rsp+21E8h+var_2198]
0x180009273  jmp     short loc_1800092A8
0x180009275  xor     ebx, ebx
0x180009277  lea     r13d, [rbx+8]
0x18000927b  mov     esi, dword ptr [rsp+21E8h+Data]
0x18000927f  mov     rcx, [rsp+21E8h+var_2158]; void *
0x180009287  mov     rdi, [rsp+21E8h+var_2178]
0x18000928c  mov     rax, [rsp+21E8h+var_2190]
0x180009291  mov     [rsp+21E8h+var_21B0], rax
0x180009296  mov     r15, [rsp+21E8h+var_2170]
0x18000929b  mov     rax, [rsp+21E8h+var_2188]
0x1800092a0  mov     [rsp+21E8h+lpValueName], rax
0x1800092a5  mov     r14d, edi
0x1800092a8  test    rcx, rcx
0x1800092ab  jnz     short loc_1800092BF
0x1800092ad  lea     rcx, [rsp+21E8h+var_2158]
0x1800092b5  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800092ba  jmp     loc_180009207
0x1800092bf  mov     r8, rdi; Size
0x1800092c2  xor     edx, edx; Val
0x1800092c4  call    memset_0
0x1800092c9  mov     r10d, ebx
0x1800092cc  test    esi, esi
0x1800092ce  jle     loc_1800093AC
0x1800092d4  mov     r12d, 30h ; '0'
0x1800092da  mov     eax, r10d
0x1800092dd  movzx   edx, [rsp+rax*2+21E8h+String1]
0x1800092e5  cmp     edx, 61h ; 'a'
0x1800092e8  ja      short loc_180009357
0x1800092ea  jz      loc_180009377
0x1800092f0  cmp     edx, 38h ; '8'
0x1800092f3  ja      short loc_180009329
0x1800092f5  jz      short loc_180009321
0x1800092f7  mov     ecx, edx
0x1800092f9  sub     ecx, r12d
0x1800092fc  jz      short loc_180009321
0x1800092fe  sub     ecx, 1
0x180009301  jz      short loc_180009321
0x180009303  sub     ecx, 1
0x180009306  jz      short loc_180009321
0x180009308  sub     ecx, 1
0x18000930b  jz      short loc_180009321
0x18000930d  sub     ecx, 1
0x180009310  jz      short loc_180009321
0x180009312  sub     ecx, 1
0x180009315  jz      short loc_180009321
0x180009317  sub     ecx, 1
0x18000931a  jz      short loc_180009321
0x18000931c  cmp     ecx, 1
0x18000931f  jnz     short loc_180009372
0x180009321  mov     r9d, edx
0x180009324  sub     r9d, r12d
0x180009327  jmp     short loc_18000937B
0x180009329  mov     r9d, edx
0x18000932c  mov     ecx, edx
0x18000932e  sub     ecx, 39h ; '9'
0x180009331  jz      short loc_180009321
0x180009333  sub     ecx, r13d
0x180009336  jz      short loc_180009351
0x180009338  sub     ecx, 1
0x18000933b  jz      short loc_180009351
0x18000933d  sub     ecx, 1
0x180009340  jz      short loc_180009351
0x180009342  sub     ecx, 1
0x180009345  jz      short loc_180009351
0x180009347  sub     ecx, 1
0x18000934a  jz      short loc_180009351
0x18000934c  cmp     ecx, 1
0x18000934f  jnz     short loc_180009372
0x180009351  add     r9d, 0FFFFFFC9h
0x180009355  jmp     short loc_18000937B
0x180009357  mov     ecx, edx
0x180009359  sub     ecx, 62h ; 'b'
0x18000935c  jz      short loc_180009377
0x18000935e  sub     ecx, 1
0x180009361  jz      short loc_180009377
0x180009363  sub     ecx, 1
0x180009366  jz      short loc_180009377
0x180009368  sub     ecx, 1
0x18000936b  jz      short loc_180009377
0x18000936d  cmp     ecx, 1
0x180009370  jz      short loc_180009377
0x180009372  mov     r9d, ebx
0x180009375  jmp     short loc_18000937B
0x180009377  lea     r9d, [rdx-57h]
0x18000937b  mov     r8d, r10d
0x18000937e  shr     r8, 1
0x180009381  mov     rdx, [rsp+21E8h+var_2158]
0x180009389  mov     eax, r10d
0x18000938c  and     eax, 1
0x18000938f  shl     eax, 2
0x180009392  mov     ecx, 4
0x180009397  sub     ecx, eax
0x180009399  shl     r9b, cl
0x18000939c  or      [r8+rdx], r9b
0x1800093a0  inc     r10d
  ... truncated ...
```
