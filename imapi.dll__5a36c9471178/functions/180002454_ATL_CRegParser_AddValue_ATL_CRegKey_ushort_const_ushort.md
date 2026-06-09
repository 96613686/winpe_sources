# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180002454`
- end: `0x180002950`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180003a3c`

## callees

- `0x180002454`
- `0x180002958`
- `0x180002aac`
- `0x180002ac4`
- `0x180002f34`
- `0x1800030c0`
- `0x1800184ce`
- `0x180018500`
- `0x1800185c0`

## import_xrefs

- `USER32!CharNextW` at `0x18000251d`
- `USER32!CharNextW` at `0x1800025ed`
- `USER32!CharNextW` at `0x180002609`
- `USER32!CharNextW` at `0x18000251d`
- `USER32!CharNextW` at `0x1800025ed`
- `USER32!CharNextW` at `0x180002609`
- `ADVAPI32!RegSetValueExW` at `0x18000267a`
- `ADVAPI32!RegSetValueExW` at `0x1800026f3`
- `ADVAPI32!RegSetValueExW` at `0x180002895`
- `ADVAPI32!RegSetValueExW` at `0x18000267a`
- `ADVAPI32!RegSetValueExW` at `0x1800026f3`
- `ADVAPI32!RegSetValueExW` at `0x180002895`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800026bd`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x1800026bd`
- `KERNEL32!lstrcmpiW` at `0x1800024cd`
- `KERNEL32!lstrcmpiW` at `0x1800024cd`

## pseudocode

```c
HRESULT __fastcall ATL::CRegParser::AddValue(
        ATL::CRegParser *this,
        HKEY *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4)
{
  unsigned __int16 *v5; // r15
  const WCHAR *v6; // r14
  HRESULT result; // eax
  int v9; // ebx
  __int16 v10; // bx
  __int64 v11; // rax
  unsigned __int64 v12; // rcx
  BYTE *v13; // rbx
  WCHAR *v14; // rsi
  const WCHAR *v15; // rax
  DWORD cbData; // r10d
  BYTE *v17; // r9
  __int64 v18; // rcx
  __int64 v19; // rcx
  LSTATUS v20; // eax
  LSTATUS v21; // edi
  LSTATUS v22; // eax
  __int64 v23; // rsi
  size_t v24; // rbx
  BYTE *v25; // rcx
  int v26; // r10d
  unsigned int v27; // r9d
  char v28; // r9
  unsigned __int64 v29; // r8
  char v30; // r9
  __int64 v31; // rdi
  int Token; // eax
  int v33; // ecx
  ULONG pulOut[2]; // [rsp+30h] [rbp-D0h] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  BYTE *v36; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v37[264]; // [rsp+48h] [rbp-B8h] BYREF
  BYTE *lpData; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v39[264]; // [rsp+158h] [rbp+58h] BYREF
  OLECHAR String1[4096]; // [rsp+260h] [rbp+160h] BYREF

  *(_QWORD *)Data = a4;
  *(_QWORD *)pulOut = a3;
  v5 = a4;
  v6 = a3;
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  v9 = 0;
  while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
  {
    if ( (unsigned int)++v9 >= 4 )
      return -2147352567;
  }
  v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
  while ( **(_WORD **)this == 9 || **(_WORD **)this == 10 || **(_WORD **)this == 13 || **(_WORD **)this == 32 )
    *(_QWORD *)this = CharNextW(*(LPCWSTR *)this);
  result = ATL::CRegParser::NextToken(this, String1);
  if ( result < 0 )
    return result;
  if ( v10 == 8 )
  {
    v31 = -1;
    do
      ++v31;
    while ( String1[v31] );
    v22 = RegSetValueExW(*a2, v6, 0, 1u, (const BYTE *)String1, 2 * v31 + 2);
    goto LABEL_43;
  }
  if ( v10 == 17 )
  {
    v23 = -1;
    do
      ++v23;
    while ( String1[v23] );
    if ( (v23 & 1) != 0 )
      return -2147467259;
    v36 = 0;
    v24 = (int)v23 / 2;
    if ( !((int)v23 / 2) )
      goto LABEL_51;
    if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
      ATL::AtlThrowImpl(-2147024809);
    if ( v24 > 0x100 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v36, v24);
      v25 = v36;
    }
    else
    {
LABEL_51:
      v25 = v37;
      v36 = v37;
    }
    if ( !v25 )
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
      return -2147467259;
    }
    memset_0(v25, 0, v24);
    v26 = 0;
    if ( (int)v23 <= 0 )
      goto LABEL_83;
    while ( 1 )
    {
      v27 = String1[v26];
      if ( v27 > 0x61 )
      {
        if ( v27 == 98 || v27 == 99 || v27 == 100 || v27 - 101 < 2 )
        {
LABEL_80:
          v28 = v27 - 87;
          goto LABEL_81;
        }
LABEL_79:
        v28 = 0;
        goto LABEL_81;
      }
      if ( v27 == 97 )
        goto LABEL_80;
      if ( v27 <= 0x38 )
        break;
      if ( v27 == 57 )
        goto LABEL_67;
      if ( v27 != 65 && v27 != 66 && v27 != 67 && v27 != 68 && v27 - 69 > 1 )
        goto LABEL_79;
      v28 = v27 - 55;
LABEL_81:
      v29 = (unsigned __int64)(unsigned int)v26 >> 1;
      v30 = v28 << (4 - 4 * (v26++ & 1));
      v36[v29] |= v30;
      if ( v26 >= (int)v23 )
      {
        v6 = *(const WCHAR **)pulOut;
LABEL_83:
        v21 = RegSetValueExW(*a2, v6, 0, 3u, v36, (int)v23 / 2);
        if ( v36 != v37 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v36);
        v5 = *(unsigned __int16 **)Data;
LABEL_86:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
LABEL_91:
        Token = ATL::CRegParser::NextToken(this, v5);
        v33 = 0;
        if ( Token < 0 )
          return Token;
        return v33;
      }
    }
    if ( v27 != 56 && v27 != 48 && v27 != 49 && v27 != 50 && v27 != 51 && v27 != 52 && v27 != 53 && v27 - 54 > 1 )
      goto LABEL_79;
LABEL_67:
    v28 = v27 - 48;
    goto LABEL_81;
  }
  if ( v10 != 19 )
  {
    if ( v10 == 16392 )
    {
      lpData = 0;
      v11 = -1;
      do
        ++v11;
      while ( String1[v11] );
      v12 = (int)v11 + 2;
      if ( (_DWORD)v11 == -2 )
        goto LABEL_23;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * v12 <= 0x100 )
      {
LABEL_23:
        v13 = v39;
        lpData = v39;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2 * v12);
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
          v6 = *(const WCHAR **)pulOut;
          v5 = *(unsigned __int16 **)Data;
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
        v20 = RegSetValueExW(*a2, v6, 0, 7u, lpData, cbData);
        v13 = lpData;
        v21 = v20;
      }
      else
      {
        v21 = 14;
      }
      if ( v13 != v39 )
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
      goto LABEL_86;
    }
    goto LABEL_91;
  }
  pulOut[0] = 0;
  result = VarUI4FromStr(String1, 0, 0, pulOut);
  if ( result >= 0 )
  {
    *(_DWORD *)Data = pulOut[0];
    v22 = RegSetValueExW(*a2, v6, 0, 4u, Data, 4u);
LABEL_43:
    v21 = v22;
    goto LABEL_86;
  }
  return result;
}

```

## disassembly

```asm
0x180002454  push    rbp
0x180002456  push    rbx
0x180002457  push    rsi
0x180002458  push    rdi
0x180002459  push    r12
0x18000245b  push    r13
0x18000245d  push    r14
0x18000245f  push    r15
0x180002461  lea     rbp, [rsp-2178h]
0x180002469  mov     eax, 2278h
0x18000246e  call    _alloca_probe
0x180002473  sub     rsp, rax
0x180002476  mov     rax, cs:__security_cookie
0x18000247d  xor     rax, rsp
0x180002480  mov     [rbp+21B0h+var_50], rax
0x180002487  mov     r13, rdx
0x18000248a  mov     qword ptr [rsp+22B0h+Data], r9
0x18000248f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180002496  mov     qword ptr [rsp+22B0h+pulOut], r8
0x18000249b  mov     r15, r9
0x18000249e  mov     r14, r8
0x1800024a1  mov     r12, rcx
0x1800024a4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800024a9  xor     esi, esi
0x1800024ab  test    eax, eax
0x1800024ad  js      loc_18000290C
0x1800024b3  mov     ebx, esi
0x1800024b5  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800024bc  movsxd  rdi, ebx
0x1800024bf  lea     rcx, [rbp+21B0h+String1]; lpString1
0x1800024c6  add     rdi, rdi
0x1800024c9  mov     rdx, [rax+rdi*8]; lpString2
0x1800024cd  call    cs:__imp_lstrcmpiW
0x1800024d3  test    eax, eax
0x1800024d5  jz      short loc_1800024EF
0x1800024d7  inc     ebx
0x1800024d9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800024e0  cmp     ebx, 4
0x1800024e3  jb      short loc_1800024BC
0x1800024e5  mov     eax, 80020009h
0x1800024ea  jmp     loc_18000290C
0x1800024ef  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800024f6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800024fb  mov     edi, 13h
0x180002500  mov     rdx, [r12]
0x180002504  movzx   ecx, word ptr [rdx]
0x180002507  sub     ecx, 9
0x18000250a  jz      short loc_18000251A
0x18000250c  sub     ecx, 1
0x18000250f  jz      short loc_18000251A
0x180002511  sub     ecx, 3
0x180002514  jz      short loc_18000251A
0x180002516  cmp     ecx, edi
0x180002518  jnz     short loc_180002529
0x18000251a  mov     rcx, rdx; lpsz
0x18000251d  call    cs:__imp_CharNextW
0x180002523  mov     [r12], rax
0x180002527  jmp     short loc_180002500
0x180002529  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180002530  mov     rcx, r12; this
0x180002533  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002538  test    eax, eax
0x18000253a  js      loc_18000290C
0x180002540  mov     eax, 8
0x180002545  cmp     bx, ax
0x180002548  jz      loc_1800028C7
0x18000254e  cmp     bx, 11h
0x180002552  jz      loc_180002700
0x180002558  cmp     bx, di
0x18000255b  jz      loc_1800026A8
0x180002561  mov     eax, 4008h
0x180002566  cmp     bx, ax
0x180002569  jnz     loc_1800028F8
0x18000256f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002573  mov     [rbp+21B0h+var_2160], rsi
0x180002577  mov     rax, rdi
0x18000257a  lea     rcx, [rbp+21B0h+String1]
0x180002581  inc     rax
0x180002584  cmp     [rcx+rax*2], si
0x180002588  jnz     short loc_180002581
0x18000258a  add     eax, 2
0x18000258d  movsxd  rcx, eax
0x180002590  jz      short loc_1800025C0
0x180002592  xor     edx, edx
0x180002594  mov     rax, rdi
0x180002597  div     rcx
0x18000259a  cmp     rax, 2
0x18000259e  jb      loc_18000293A
0x1800025a4  lea     rdx, [rcx+rcx]
0x1800025a8  cmp     rdx, 100h
0x1800025af  jbe     short loc_1800025C0
0x1800025b1  lea     rcx, [rbp+21B0h+var_2160]
0x1800025b5  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800025ba  mov     rbx, [rbp+21B0h+var_2160]
0x1800025be  jmp     short loc_1800025C8
0x1800025c0  lea     rbx, [rbp+21B0h+var_2158]
0x1800025c4  mov     [rbp+21B0h+var_2160], rbx
0x1800025c8  test    rbx, rbx
0x1800025cb  jz      loc_180002688
0x1800025d1  xor     eax, eax
0x1800025d3  lea     rsi, [rbp+21B0h+String1]
0x1800025da  cmp     [rbp+21B0h+String1], ax
0x1800025e1  jz      short loc_18000262F
0x1800025e3  lea     r14d, [rax+30h]
0x1800025e7  xor     r15d, r15d
0x1800025ea  mov     rcx, rsi; lpsz
0x1800025ed  call    cs:__imp_CharNextW
0x1800025f3  movzx   ecx, word ptr [rsi]
0x1800025f6  cmp     cx, 5Ch ; '\'
0x1800025fa  jnz     short loc_180002614
0x1800025fc  cmp     [rax], r14w
0x180002600  jnz     short loc_180002614
0x180002602  mov     rcx, rax; lpsz
0x180002605  mov     [rbx], r15w
0x180002609  call    cs:__imp_CharNextW
0x18000260f  mov     rsi, rax
0x180002612  jmp     short loc_18000261B
0x180002614  mov     [rbx], cx
0x180002617  add     rsi, 2
0x18000261b  add     rbx, 2
0x18000261f  cmp     [rsi], r15w
0x180002623  jnz     short loc_1800025EA
0x180002625  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x18000262a  mov     r15, qword ptr [rsp+22B0h+Data]
0x18000262f  xor     esi, esi
0x180002631  mov     [rbx], esi
0x180002633  mov     r8, [rbp+21B0h+var_2160]
0x180002637  test    r8, r8
0x18000263a  jz      loc_180002945
0x180002640  mov     r10d, esi
0x180002643  mov     r9, r8
0x180002646  mov     rcx, rdi
0x180002649  inc     rcx
0x18000264c  cmp     [r9+rcx*2], si
0x180002651  jnz     short loc_180002649
0x180002653  inc     ecx
0x180002655  lea     r9, [r9+rcx*2]
0x180002659  lea     r10d, [r10+rcx*2]
0x18000265d  cmp     ecx, 1
0x180002660  jnz     short loc_180002646
0x180002662  mov     [rsp+22B0h+cbData], r10d; cbData
0x180002667  lea     r9d, [rcx+6]; dwType
0x18000266b  mov     rcx, [r13+0]; hKey
0x18000266f  mov     rdx, r14; lpValueName
0x180002672  mov     [rsp+22B0h+lpData], r8; lpData
0x180002677  xor     r8d, r8d; Reserved
0x18000267a  call    cs:__imp_RegSetValueExW
0x180002680  mov     rbx, [rbp+21B0h+var_2160]
0x180002684  mov     edi, eax
0x180002686  jmp     short loc_18000268D
0x180002688  mov     edi, 0Eh
0x18000268d  lea     rax, [rbp+21B0h+var_2158]
0x180002691  cmp     rbx, rax
0x180002694  jz      loc_1800028BA
0x18000269a  lea     rcx, [rbp+21B0h+var_2160]
0x18000269e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800026a3  jmp     loc_1800028BA
0x1800026a8  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x1800026ad  mov     [rsp+22B0h+pulOut], esi
0x1800026b1  xor     r8d, r8d; dwFlags
0x1800026b4  lea     rcx, [rbp+21B0h+String1]; strIn
0x1800026bb  xor     edx, edx; lcid
0x1800026bd  call    cs:__imp_VarUI4FromStr
0x1800026c3  test    eax, eax
0x1800026c5  js      loc_18000290C
0x1800026cb  mov     eax, [rsp+22B0h+pulOut]
0x1800026cf  mov     ecx, 4
0x1800026d4  mov     dword ptr [rsp+22B0h+Data], eax
0x1800026d8  mov     r9d, ecx; dwType
0x1800026db  mov     [rsp+22B0h+cbData], ecx; cbData
0x1800026df  lea     rax, [rsp+22B0h+Data]
0x1800026e4  mov     rcx, [r13+0]; hKey
0x1800026e8  xor     r8d, r8d; Reserved
0x1800026eb  mov     rdx, r14; lpValueName
0x1800026ee  mov     [rsp+22B0h+lpData], rax; lpData
0x1800026f3  call    cs:__imp_RegSetValueExW
0x1800026f9  mov     edi, eax
0x1800026fb  jmp     loc_1800028BA
0x180002700  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180002704  lea     rax, [rbp+21B0h+String1]
0x18000270b  mov     rsi, rdi
0x18000270e  xor     ecx, ecx
0x180002710  inc     rsi
0x180002713  cmp     [rax+rsi*2], cx
0x180002717  jnz     short loc_180002710
0x180002719  test    sil, 1
0x18000271d  jnz     short loc_18000277D
0x18000271f  mov     eax, esi
0x180002721  mov     [rsp+22B0h+var_2270], rcx
0x180002726  cdq
0x180002727  sub     eax, edx
0x180002729  sar     eax, 1
0x18000272b  movsxd  r15, eax
0x18000272e  mov     rbx, r15
0x180002731  jz      short loc_180002762
0x180002733  xor     edx, edx
0x180002735  mov     rax, rdi
0x180002738  div     rbx
0x18000273b  cmp     rax, 1
0x18000273f  jb      loc_18000292F
0x180002745  cmp     rbx, 100h
0x18000274c  jbe     short loc_180002762
0x18000274e  mov     rdx, rbx
0x180002751  lea     rcx, [rsp+22B0h+var_2270]
0x180002756  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000275b  mov     rcx, [rsp+22B0h+var_2270]
0x180002760  jmp     short loc_18000276C
0x180002762  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180002767  mov     [rsp+22B0h+var_2270], rcx
0x18000276c  xor     edi, edi
0x18000276e  test    rcx, rcx
0x180002771  jnz     short loc_180002787
0x180002773  lea     rcx, [rsp+22B0h+var_2270]
0x180002778  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000277d  mov     eax, 80004005h
0x180002782  jmp     loc_18000290C
0x180002787  mov     r8, rbx; Size
0x18000278a  xor     edx, edx; Val
0x18000278c  call    memset_0
0x180002791  mov     r10d, edi
0x180002794  test    esi, esi
0x180002796  jle     loc_180002876
0x18000279c  mov     r14d, 30h ; '0'
0x1800027a2  mov     eax, r10d
0x1800027a5  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x1800027ae  cmp     r9d, 61h ; 'a'
0x1800027b2  ja      short loc_18000281E
0x1800027b4  jz      loc_18000283F
0x1800027ba  cmp     r9d, 38h ; '8'
0x1800027be  ja      short loc_1800027F2
0x1800027c0  jz      short loc_1800027ED
0x1800027c2  mov     ecx, r9d
0x1800027c5  sub     ecx, r14d
0x1800027c8  jz      short loc_1800027ED
0x1800027ca  sub     ecx, 1
0x1800027cd  jz      short loc_1800027ED
0x1800027cf  sub     ecx, 1
0x1800027d2  jz      short loc_1800027ED
0x1800027d4  sub     ecx, 1
0x1800027d7  jz      short loc_1800027ED
0x1800027d9  sub     ecx, 1
0x1800027dc  jz      short loc_1800027ED
0x1800027de  sub     ecx, 1
0x1800027e1  jz      short loc_1800027ED
0x1800027e3  sub     ecx, 1
0x1800027e6  jz      short loc_1800027ED
0x1800027e8  cmp     ecx, 1
0x1800027eb  jnz     short loc_18000283A
0x1800027ed  sub     r9b, r14b
0x1800027f0  jmp     short loc_180002843
0x1800027f2  mov     ecx, r9d
0x1800027f5  sub     ecx, 39h ; '9'
0x1800027f8  jz      short loc_1800027ED
0x1800027fa  sub     ecx, 8
0x1800027fd  jz      short loc_180002818
0x1800027ff  sub     ecx, 1
0x180002802  jz      short loc_180002818
0x180002804  sub     ecx, 1
0x180002807  jz      short loc_180002818
0x180002809  sub     ecx, 1
0x18000280c  jz      short loc_180002818
0x18000280e  sub     ecx, 1
0x180002811  jz      short loc_180002818
0x180002813  cmp     ecx, 1
0x180002816  jnz     short loc_18000283A
0x180002818  sub     r9b, 37h ; '7'
0x18000281c  jmp     short loc_180002843
0x18000281e  mov     ecx, r9d
0x180002821  sub     ecx, 62h ; 'b'
0x180002824  jz      short loc_18000283F
0x180002826  sub     ecx, 1
0x180002829  jz      short loc_18000283F
0x18000282b  sub     ecx, 1
0x18000282e  jz      short loc_18000283F
0x180002830  sub     ecx, 1
0x180002833  jz      short loc_18000283F
0x180002835  cmp     ecx, 1
0x180002838  jz      short loc_18000283F
0x18000283a  mov     r9b, dil
0x18000283d  jmp     short loc_180002843
0x18000283f  sub     r9b, 57h ; 'W'
0x180002843  mov     rdx, [rsp+22B0h+var_2270]
0x180002848  mov     eax, r10d
0x18000284b  and     eax, 1
0x18000284e  mov     r8d, r10d
0x180002851  shl     eax, 2
0x180002854  mov     ecx, 4
0x180002859  shr     r8, 1
0x18000285c  sub     ecx, eax
0x18000285e  shl     r9b, cl
0x180002861  inc     r10d
0x180002864  or      [r8+rdx], r9b
0x180002868  cmp     r10d, esi
0x18000286b  jl      loc_1800027A2
0x180002871  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180002876  mov     rax, [rsp+22B0h+var_2270]
0x18000287b  mov     r9d, 3; dwType
0x180002881  mov     rcx, [r13+0]; hKey
0x180002885  xor     r8d, r8d; Reserved
0x180002888  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
