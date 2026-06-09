# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180004314`
- end: `0x180004810`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `HRESULT __fastcall(ATL::CRegParser *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180008dd0`

## callees

- `0x180004314`
- `0x180004818`
- `0x180004a78`
- `0x180004a90`
- `0x1800059c8`
- `0x180007038`
- `0x1800184ce`
- `0x180018500`
- `0x180018590`

## import_xrefs

- `KERNEL32!lstrcmpiW` at `0x18000438d`
- `KERNEL32!lstrcmpiW` at `0x18000438d`
- `USER32!CharNextW` at `0x1800043dd`
- `USER32!CharNextW` at `0x1800044ad`
- `USER32!CharNextW` at `0x1800044c9`
- `USER32!CharNextW` at `0x1800043dd`
- `USER32!CharNextW` at `0x1800044ad`
- `USER32!CharNextW` at `0x1800044c9`
- `ADVAPI32!RegSetValueExW` at `0x18000453a`
- `ADVAPI32!RegSetValueExW` at `0x1800045b3`
- `ADVAPI32!RegSetValueExW` at `0x180004755`
- `ADVAPI32!RegSetValueExW` at `0x18000453a`
- `ADVAPI32!RegSetValueExW` at `0x1800045b3`
- `ADVAPI32!RegSetValueExW` at `0x180004755`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000457d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000457d`

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
0x180004314  push    rbp
0x180004316  push    rbx
0x180004317  push    rsi
0x180004318  push    rdi
0x180004319  push    r12
0x18000431b  push    r13
0x18000431d  push    r14
0x18000431f  push    r15
0x180004321  lea     rbp, [rsp-2178h]
0x180004329  mov     eax, 2278h
0x18000432e  call    _alloca_probe
0x180004333  sub     rsp, rax
0x180004336  mov     rax, cs:__security_cookie
0x18000433d  xor     rax, rsp
0x180004340  mov     [rbp+21B0h+var_50], rax
0x180004347  mov     r13, rdx
0x18000434a  mov     qword ptr [rsp+22B0h+Data], r9
0x18000434f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x180004356  mov     qword ptr [rsp+22B0h+pulOut], r8
0x18000435b  mov     r15, r9
0x18000435e  mov     r14, r8
0x180004361  mov     r12, rcx
0x180004364  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004369  xor     esi, esi
0x18000436b  test    eax, eax
0x18000436d  js      loc_1800047CC
0x180004373  mov     ebx, esi
0x180004375  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000437c  movsxd  rdi, ebx
0x18000437f  lea     rcx, [rbp+21B0h+String1]; lpString1
0x180004386  add     rdi, rdi
0x180004389  mov     rdx, [rax+rdi*8]; lpString2
0x18000438d  call    cs:__imp_lstrcmpiW
0x180004393  test    eax, eax
0x180004395  jz      short loc_1800043AF
0x180004397  inc     ebx
0x180004399  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800043a0  cmp     ebx, 4
0x1800043a3  jb      short loc_18000437C
0x1800043a5  mov     eax, 80020009h
0x1800043aa  jmp     loc_1800047CC
0x1800043af  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800043b6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x1800043bb  mov     edi, 13h
0x1800043c0  mov     rdx, [r12]
0x1800043c4  movzx   ecx, word ptr [rdx]
0x1800043c7  sub     ecx, 9
0x1800043ca  jz      short loc_1800043DA
0x1800043cc  sub     ecx, 1
0x1800043cf  jz      short loc_1800043DA
0x1800043d1  sub     ecx, 3
0x1800043d4  jz      short loc_1800043DA
0x1800043d6  cmp     ecx, edi
0x1800043d8  jnz     short loc_1800043E9
0x1800043da  mov     rcx, rdx; lpsz
0x1800043dd  call    cs:__imp_CharNextW
0x1800043e3  mov     [r12], rax
0x1800043e7  jmp     short loc_1800043C0
0x1800043e9  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x1800043f0  mov     rcx, r12; this
0x1800043f3  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800043f8  test    eax, eax
0x1800043fa  js      loc_1800047CC
0x180004400  mov     eax, 8
0x180004405  cmp     bx, ax
0x180004408  jz      loc_180004787
0x18000440e  cmp     bx, 11h
0x180004412  jz      loc_1800045C0
0x180004418  cmp     bx, di
0x18000441b  jz      loc_180004568
0x180004421  mov     eax, 4008h
0x180004426  cmp     bx, ax
0x180004429  jnz     loc_1800047B8
0x18000442f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180004433  mov     [rbp+21B0h+var_2160], rsi
0x180004437  mov     rax, rdi
0x18000443a  lea     rcx, [rbp+21B0h+String1]
0x180004441  inc     rax
0x180004444  cmp     [rcx+rax*2], si
0x180004448  jnz     short loc_180004441
0x18000444a  add     eax, 2
0x18000444d  movsxd  rcx, eax
0x180004450  jz      short loc_180004480
0x180004452  xor     edx, edx
0x180004454  mov     rax, rdi
0x180004457  div     rcx
0x18000445a  cmp     rax, 2
0x18000445e  jb      loc_1800047FA
0x180004464  lea     rdx, [rcx+rcx]
0x180004468  cmp     rdx, 100h
0x18000446f  jbe     short loc_180004480
0x180004471  lea     rcx, [rbp+21B0h+var_2160]
0x180004475  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000447a  mov     rbx, [rbp+21B0h+var_2160]
0x18000447e  jmp     short loc_180004488
0x180004480  lea     rbx, [rbp+21B0h+var_2158]
0x180004484  mov     [rbp+21B0h+var_2160], rbx
0x180004488  test    rbx, rbx
0x18000448b  jz      loc_180004548
0x180004491  xor     eax, eax
0x180004493  lea     rsi, [rbp+21B0h+String1]
0x18000449a  cmp     [rbp+21B0h+String1], ax
0x1800044a1  jz      short loc_1800044EF
0x1800044a3  lea     r14d, [rax+30h]
0x1800044a7  xor     r15d, r15d
0x1800044aa  mov     rcx, rsi; lpsz
0x1800044ad  call    cs:__imp_CharNextW
0x1800044b3  movzx   ecx, word ptr [rsi]
0x1800044b6  cmp     cx, 5Ch ; '\'
0x1800044ba  jnz     short loc_1800044D4
0x1800044bc  cmp     [rax], r14w
0x1800044c0  jnz     short loc_1800044D4
0x1800044c2  mov     rcx, rax; lpsz
0x1800044c5  mov     [rbx], r15w
0x1800044c9  call    cs:__imp_CharNextW
0x1800044cf  mov     rsi, rax
0x1800044d2  jmp     short loc_1800044DB
0x1800044d4  mov     [rbx], cx
0x1800044d7  add     rsi, 2
0x1800044db  add     rbx, 2
0x1800044df  cmp     [rsi], r15w
0x1800044e3  jnz     short loc_1800044AA
0x1800044e5  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x1800044ea  mov     r15, qword ptr [rsp+22B0h+Data]
0x1800044ef  xor     esi, esi
0x1800044f1  mov     [rbx], esi
0x1800044f3  mov     r8, [rbp+21B0h+var_2160]
0x1800044f7  test    r8, r8
0x1800044fa  jz      loc_180004805
0x180004500  mov     r10d, esi
0x180004503  mov     r9, r8
0x180004506  mov     rcx, rdi
0x180004509  inc     rcx
0x18000450c  cmp     [r9+rcx*2], si
0x180004511  jnz     short loc_180004509
0x180004513  inc     ecx
0x180004515  lea     r9, [r9+rcx*2]
0x180004519  lea     r10d, [r10+rcx*2]
0x18000451d  cmp     ecx, 1
0x180004520  jnz     short loc_180004506
0x180004522  mov     [rsp+22B0h+cbData], r10d; cbData
0x180004527  lea     r9d, [rcx+6]; dwType
0x18000452b  mov     rcx, [r13+0]; hKey
0x18000452f  mov     rdx, r14; lpValueName
0x180004532  mov     [rsp+22B0h+lpData], r8; lpData
0x180004537  xor     r8d, r8d; Reserved
0x18000453a  call    cs:__imp_RegSetValueExW
0x180004540  mov     rbx, [rbp+21B0h+var_2160]
0x180004544  mov     edi, eax
0x180004546  jmp     short loc_18000454D
0x180004548  mov     edi, 0Eh
0x18000454d  lea     rax, [rbp+21B0h+var_2158]
0x180004551  cmp     rbx, rax
0x180004554  jz      loc_18000477A
0x18000455a  lea     rcx, [rbp+21B0h+var_2160]
0x18000455e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004563  jmp     loc_18000477A
0x180004568  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x18000456d  mov     [rsp+22B0h+pulOut], esi
0x180004571  xor     r8d, r8d; dwFlags
0x180004574  lea     rcx, [rbp+21B0h+String1]; strIn
0x18000457b  xor     edx, edx; lcid
0x18000457d  call    cs:__imp_VarUI4FromStr
0x180004583  test    eax, eax
0x180004585  js      loc_1800047CC
0x18000458b  mov     eax, [rsp+22B0h+pulOut]
0x18000458f  mov     ecx, 4
0x180004594  mov     dword ptr [rsp+22B0h+Data], eax
0x180004598  mov     r9d, ecx; dwType
0x18000459b  mov     [rsp+22B0h+cbData], ecx; cbData
0x18000459f  lea     rax, [rsp+22B0h+Data]
0x1800045a4  mov     rcx, [r13+0]; hKey
0x1800045a8  xor     r8d, r8d; Reserved
0x1800045ab  mov     rdx, r14; lpValueName
0x1800045ae  mov     [rsp+22B0h+lpData], rax; lpData
0x1800045b3  call    cs:__imp_RegSetValueExW
0x1800045b9  mov     edi, eax
0x1800045bb  jmp     loc_18000477A
0x1800045c0  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800045c4  lea     rax, [rbp+21B0h+String1]
0x1800045cb  mov     rsi, rdi
0x1800045ce  xor     ecx, ecx
0x1800045d0  inc     rsi
0x1800045d3  cmp     [rax+rsi*2], cx
0x1800045d7  jnz     short loc_1800045D0
0x1800045d9  test    sil, 1
0x1800045dd  jnz     short loc_18000463D
0x1800045df  mov     eax, esi
0x1800045e1  mov     [rsp+22B0h+var_2270], rcx
0x1800045e6  cdq
0x1800045e7  sub     eax, edx
0x1800045e9  sar     eax, 1
0x1800045eb  movsxd  r15, eax
0x1800045ee  mov     rbx, r15
0x1800045f1  jz      short loc_180004622
0x1800045f3  xor     edx, edx
0x1800045f5  mov     rax, rdi
0x1800045f8  div     rbx
0x1800045fb  cmp     rax, 1
0x1800045ff  jb      loc_1800047EF
0x180004605  cmp     rbx, 100h
0x18000460c  jbe     short loc_180004622
0x18000460e  mov     rdx, rbx
0x180004611  lea     rcx, [rsp+22B0h+var_2270]
0x180004616  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000461b  mov     rcx, [rsp+22B0h+var_2270]
0x180004620  jmp     short loc_18000462C
0x180004622  lea     rcx, [rsp+22B0h+var_2268]; void *
0x180004627  mov     [rsp+22B0h+var_2270], rcx
0x18000462c  xor     edi, edi
0x18000462e  test    rcx, rcx
0x180004631  jnz     short loc_180004647
0x180004633  lea     rcx, [rsp+22B0h+var_2270]
0x180004638  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000463d  mov     eax, 80004005h
0x180004642  jmp     loc_1800047CC
0x180004647  mov     r8, rbx; Size
0x18000464a  xor     edx, edx; Val
0x18000464c  call    memset_0
0x180004651  mov     r10d, edi
0x180004654  test    esi, esi
0x180004656  jle     loc_180004736
0x18000465c  mov     r14d, 30h ; '0'
0x180004662  mov     eax, r10d
0x180004665  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x18000466e  cmp     r9d, 61h ; 'a'
0x180004672  ja      short loc_1800046DE
0x180004674  jz      loc_1800046FF
0x18000467a  cmp     r9d, 38h ; '8'
0x18000467e  ja      short loc_1800046B2
0x180004680  jz      short loc_1800046AD
0x180004682  mov     ecx, r9d
0x180004685  sub     ecx, r14d
0x180004688  jz      short loc_1800046AD
0x18000468a  sub     ecx, 1
0x18000468d  jz      short loc_1800046AD
0x18000468f  sub     ecx, 1
0x180004692  jz      short loc_1800046AD
0x180004694  sub     ecx, 1
0x180004697  jz      short loc_1800046AD
0x180004699  sub     ecx, 1
0x18000469c  jz      short loc_1800046AD
0x18000469e  sub     ecx, 1
0x1800046a1  jz      short loc_1800046AD
0x1800046a3  sub     ecx, 1
0x1800046a6  jz      short loc_1800046AD
0x1800046a8  cmp     ecx, 1
0x1800046ab  jnz     short loc_1800046FA
0x1800046ad  sub     r9b, r14b
0x1800046b0  jmp     short loc_180004703
0x1800046b2  mov     ecx, r9d
0x1800046b5  sub     ecx, 39h ; '9'
0x1800046b8  jz      short loc_1800046AD
0x1800046ba  sub     ecx, 8
0x1800046bd  jz      short loc_1800046D8
0x1800046bf  sub     ecx, 1
0x1800046c2  jz      short loc_1800046D8
0x1800046c4  sub     ecx, 1
0x1800046c7  jz      short loc_1800046D8
0x1800046c9  sub     ecx, 1
0x1800046cc  jz      short loc_1800046D8
0x1800046ce  sub     ecx, 1
0x1800046d1  jz      short loc_1800046D8
0x1800046d3  cmp     ecx, 1
0x1800046d6  jnz     short loc_1800046FA
0x1800046d8  sub     r9b, 37h ; '7'
0x1800046dc  jmp     short loc_180004703
0x1800046de  mov     ecx, r9d
0x1800046e1  sub     ecx, 62h ; 'b'
0x1800046e4  jz      short loc_1800046FF
0x1800046e6  sub     ecx, 1
0x1800046e9  jz      short loc_1800046FF
0x1800046eb  sub     ecx, 1
0x1800046ee  jz      short loc_1800046FF
0x1800046f0  sub     ecx, 1
0x1800046f3  jz      short loc_1800046FF
0x1800046f5  cmp     ecx, 1
0x1800046f8  jz      short loc_1800046FF
0x1800046fa  mov     r9b, dil
0x1800046fd  jmp     short loc_180004703
0x1800046ff  sub     r9b, 57h ; 'W'
0x180004703  mov     rdx, [rsp+22B0h+var_2270]
0x180004708  mov     eax, r10d
0x18000470b  and     eax, 1
0x18000470e  mov     r8d, r10d
0x180004711  shl     eax, 2
0x180004714  mov     ecx, 4
0x180004719  shr     r8, 1
0x18000471c  sub     ecx, eax
0x18000471e  shl     r9b, cl
0x180004721  inc     r10d
0x180004724  or      [r8+rdx], r9b
0x180004728  cmp     r10d, esi
0x18000472b  jl      loc_180004662
0x180004731  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x180004736  mov     rax, [rsp+22B0h+var_2270]
0x18000473b  mov     r9d, 3; dwType
0x180004741  mov     rcx, [r13+0]; hKey
0x180004745  xor     r8d, r8d; Reserved
0x180004748  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
