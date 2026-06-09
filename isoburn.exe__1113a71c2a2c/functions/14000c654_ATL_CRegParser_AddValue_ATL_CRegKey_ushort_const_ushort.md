# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x14000c654`
- end: `0x14000cb50`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1276`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x14000d8cc`

## callees

- `0x140001fa0`
- `0x140002bc6`
- `0x1400045e4`
- `0x14000c654`
- `0x14000cb58`
- `0x14000cc6c`
- `0x14000ce40`
- `0x14000cf98`
- `0x14000f6e0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000c87a`
- `ADVAPI32!RegSetValueExW` at `0x14000c8f3`
- `ADVAPI32!RegSetValueExW` at `0x14000ca95`
- `ADVAPI32!RegSetValueExW` at `0x14000c87a`
- `ADVAPI32!RegSetValueExW` at `0x14000c8f3`
- `ADVAPI32!RegSetValueExW` at `0x14000ca95`
- `KERNEL32!lstrcmpiW` at `0x14000c6cd`
- `KERNEL32!lstrcmpiW` at `0x14000c6cd`
- `USER32!CharNextW` at `0x14000c71d`
- `USER32!CharNextW` at `0x14000c7ed`
- `USER32!CharNextW` at `0x14000c809`
- `USER32!CharNextW` at `0x14000c71d`
- `USER32!CharNextW` at `0x14000c7ed`
- `USER32!CharNextW` at `0x14000c809`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000c8bd`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000c8bd`

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
0x14000c654  push    rbp
0x14000c656  push    rbx
0x14000c657  push    rsi
0x14000c658  push    rdi
0x14000c659  push    r12
0x14000c65b  push    r13
0x14000c65d  push    r14
0x14000c65f  push    r15
0x14000c661  lea     rbp, [rsp-2178h]
0x14000c669  mov     eax, 2278h
0x14000c66e  call    _alloca_probe
0x14000c673  sub     rsp, rax
0x14000c676  mov     rax, cs:__security_cookie
0x14000c67d  xor     rax, rsp
0x14000c680  mov     [rbp+21B0h+var_50], rax
0x14000c687  mov     r13, rdx
0x14000c68a  mov     qword ptr [rsp+22B0h+Data], r9
0x14000c68f  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x14000c696  mov     qword ptr [rsp+22B0h+pulOut], r8
0x14000c69b  mov     r15, r9
0x14000c69e  mov     r14, r8
0x14000c6a1  mov     r12, rcx
0x14000c6a4  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c6a9  xor     esi, esi
0x14000c6ab  test    eax, eax
0x14000c6ad  js      loc_14000CB0C
0x14000c6b3  mov     ebx, esi
0x14000c6b5  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000c6bc  movsxd  rdi, ebx
0x14000c6bf  lea     rcx, [rbp+21B0h+String1]; lpString1
0x14000c6c6  add     rdi, rdi
0x14000c6c9  mov     rdx, [rax+rdi*8]; lpString2
0x14000c6cd  call    cs:__imp_lstrcmpiW
0x14000c6d3  test    eax, eax
0x14000c6d5  jz      short loc_14000C6EF
0x14000c6d7  inc     ebx
0x14000c6d9  lea     rax, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000c6e0  cmp     ebx, 4
0x14000c6e3  jb      short loc_14000C6BC
0x14000c6e5  mov     eax, 80020009h
0x14000c6ea  jmp     loc_14000CB0C
0x14000c6ef  lea     rbx, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000c6f6  movzx   ebx, word ptr [rbx+rdi*8+8]
0x14000c6fb  mov     edi, 13h
0x14000c700  mov     rdx, [r12]
0x14000c704  movzx   ecx, word ptr [rdx]
0x14000c707  sub     ecx, 9
0x14000c70a  jz      short loc_14000C71A
0x14000c70c  sub     ecx, 1
0x14000c70f  jz      short loc_14000C71A
0x14000c711  sub     ecx, 3
0x14000c714  jz      short loc_14000C71A
0x14000c716  cmp     ecx, edi
0x14000c718  jnz     short loc_14000C729
0x14000c71a  mov     rcx, rdx; lpsz
0x14000c71d  call    cs:__imp_CharNextW
0x14000c723  mov     [r12], rax
0x14000c727  jmp     short loc_14000C700
0x14000c729  lea     rdx, [rbp+21B0h+String1]; unsigned __int16 *
0x14000c730  mov     rcx, r12; this
0x14000c733  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000c738  test    eax, eax
0x14000c73a  js      loc_14000CB0C
0x14000c740  mov     eax, 8
0x14000c745  cmp     bx, ax
0x14000c748  jz      loc_14000CAC7
0x14000c74e  cmp     bx, 11h
0x14000c752  jz      loc_14000C900
0x14000c758  cmp     bx, di
0x14000c75b  jz      loc_14000C8A8
0x14000c761  mov     eax, 4008h
0x14000c766  cmp     bx, ax
0x14000c769  jnz     loc_14000CAF8
0x14000c76f  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000c773  mov     [rbp+21B0h+var_2160], rsi
0x14000c777  mov     rax, rdi
0x14000c77a  lea     rcx, [rbp+21B0h+String1]
0x14000c781  inc     rax
0x14000c784  cmp     [rcx+rax*2], si
0x14000c788  jnz     short loc_14000C781
0x14000c78a  add     eax, 2
0x14000c78d  movsxd  rcx, eax
0x14000c790  jz      short loc_14000C7C0
0x14000c792  xor     edx, edx
0x14000c794  mov     rax, rdi
0x14000c797  div     rcx
0x14000c79a  cmp     rax, 2
0x14000c79e  jb      loc_14000CB3A
0x14000c7a4  lea     rdx, [rcx+rcx]
0x14000c7a8  cmp     rdx, 100h
0x14000c7af  jbe     short loc_14000C7C0
0x14000c7b1  lea     rcx, [rbp+21B0h+var_2160]
0x14000c7b5  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000c7ba  mov     rbx, [rbp+21B0h+var_2160]
0x14000c7be  jmp     short loc_14000C7C8
0x14000c7c0  lea     rbx, [rbp+21B0h+var_2158]
0x14000c7c4  mov     [rbp+21B0h+var_2160], rbx
0x14000c7c8  test    rbx, rbx
0x14000c7cb  jz      loc_14000C888
0x14000c7d1  xor     eax, eax
0x14000c7d3  lea     rsi, [rbp+21B0h+String1]
0x14000c7da  cmp     [rbp+21B0h+String1], ax
0x14000c7e1  jz      short loc_14000C82F
0x14000c7e3  lea     r14d, [rax+30h]
0x14000c7e7  xor     r15d, r15d
0x14000c7ea  mov     rcx, rsi; lpsz
0x14000c7ed  call    cs:__imp_CharNextW
0x14000c7f3  movzx   ecx, word ptr [rsi]
0x14000c7f6  cmp     cx, 5Ch ; '\'
0x14000c7fa  jnz     short loc_14000C814
0x14000c7fc  cmp     [rax], r14w
0x14000c800  jnz     short loc_14000C814
0x14000c802  mov     rcx, rax; lpsz
0x14000c805  mov     [rbx], r15w
0x14000c809  call    cs:__imp_CharNextW
0x14000c80f  mov     rsi, rax
0x14000c812  jmp     short loc_14000C81B
0x14000c814  mov     [rbx], cx
0x14000c817  add     rsi, 2
0x14000c81b  add     rbx, 2
0x14000c81f  cmp     [rsi], r15w
0x14000c823  jnz     short loc_14000C7EA
0x14000c825  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x14000c82a  mov     r15, qword ptr [rsp+22B0h+Data]
0x14000c82f  xor     esi, esi
0x14000c831  mov     [rbx], esi
0x14000c833  mov     r8, [rbp+21B0h+var_2160]
0x14000c837  test    r8, r8
0x14000c83a  jz      loc_14000CB45
0x14000c840  mov     r10d, esi
0x14000c843  mov     r9, r8
0x14000c846  mov     rcx, rdi
0x14000c849  inc     rcx
0x14000c84c  cmp     [r9+rcx*2], si
0x14000c851  jnz     short loc_14000C849
0x14000c853  inc     ecx
0x14000c855  lea     r9, [r9+rcx*2]
0x14000c859  lea     r10d, [r10+rcx*2]
0x14000c85d  cmp     ecx, 1
0x14000c860  jnz     short loc_14000C846
0x14000c862  mov     [rsp+22B0h+cbData], r10d; cbData
0x14000c867  lea     r9d, [rcx+6]; dwType
0x14000c86b  mov     rcx, [r13+0]; hKey
0x14000c86f  mov     rdx, r14; lpValueName
0x14000c872  mov     [rsp+22B0h+lpData], r8; lpData
0x14000c877  xor     r8d, r8d; Reserved
0x14000c87a  call    cs:__imp_RegSetValueExW
0x14000c880  mov     rbx, [rbp+21B0h+var_2160]
0x14000c884  mov     edi, eax
0x14000c886  jmp     short loc_14000C88D
0x14000c888  mov     edi, 0Eh
0x14000c88d  lea     rax, [rbp+21B0h+var_2158]
0x14000c891  cmp     rbx, rax
0x14000c894  jz      loc_14000CABA
0x14000c89a  lea     rcx, [rbp+21B0h+var_2160]
0x14000c89e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000c8a3  jmp     loc_14000CABA
0x14000c8a8  lea     r9, [rsp+22B0h+pulOut]; pulOut
0x14000c8ad  mov     [rsp+22B0h+pulOut], esi
0x14000c8b1  xor     r8d, r8d; dwFlags
0x14000c8b4  lea     rcx, [rbp+21B0h+String1]; strIn
0x14000c8bb  xor     edx, edx; lcid
0x14000c8bd  call    cs:__imp_VarUI4FromStr
0x14000c8c3  test    eax, eax
0x14000c8c5  js      loc_14000CB0C
0x14000c8cb  mov     eax, [rsp+22B0h+pulOut]
0x14000c8cf  mov     ecx, 4
0x14000c8d4  mov     dword ptr [rsp+22B0h+Data], eax
0x14000c8d8  mov     r9d, ecx; dwType
0x14000c8db  mov     [rsp+22B0h+cbData], ecx; cbData
0x14000c8df  lea     rax, [rsp+22B0h+Data]
0x14000c8e4  mov     rcx, [r13+0]; hKey
0x14000c8e8  xor     r8d, r8d; Reserved
0x14000c8eb  mov     rdx, r14; lpValueName
0x14000c8ee  mov     [rsp+22B0h+lpData], rax; lpData
0x14000c8f3  call    cs:__imp_RegSetValueExW
0x14000c8f9  mov     edi, eax
0x14000c8fb  jmp     loc_14000CABA
0x14000c900  or      rdi, 0FFFFFFFFFFFFFFFFh
0x14000c904  lea     rax, [rbp+21B0h+String1]
0x14000c90b  mov     rsi, rdi
0x14000c90e  xor     ecx, ecx
0x14000c910  inc     rsi
0x14000c913  cmp     [rax+rsi*2], cx
0x14000c917  jnz     short loc_14000C910
0x14000c919  test    sil, 1
0x14000c91d  jnz     short loc_14000C97D
0x14000c91f  mov     eax, esi
0x14000c921  mov     [rsp+22B0h+var_2270], rcx
0x14000c926  cdq
0x14000c927  sub     eax, edx
0x14000c929  sar     eax, 1
0x14000c92b  movsxd  r15, eax
0x14000c92e  mov     rbx, r15
0x14000c931  jz      short loc_14000C962
0x14000c933  xor     edx, edx
0x14000c935  mov     rax, rdi
0x14000c938  div     rbx
0x14000c93b  cmp     rax, 1
0x14000c93f  jb      loc_14000CB2F
0x14000c945  cmp     rbx, 100h
0x14000c94c  jbe     short loc_14000C962
0x14000c94e  mov     rdx, rbx
0x14000c951  lea     rcx, [rsp+22B0h+var_2270]
0x14000c956  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000c95b  mov     rcx, [rsp+22B0h+var_2270]
0x14000c960  jmp     short loc_14000C96C
0x14000c962  lea     rcx, [rsp+22B0h+var_2268]; void *
0x14000c967  mov     [rsp+22B0h+var_2270], rcx
0x14000c96c  xor     edi, edi
0x14000c96e  test    rcx, rcx
0x14000c971  jnz     short loc_14000C987
0x14000c973  lea     rcx, [rsp+22B0h+var_2270]
0x14000c978  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000c97d  mov     eax, 80004005h
0x14000c982  jmp     loc_14000CB0C
0x14000c987  mov     r8, rbx; Size
0x14000c98a  xor     edx, edx; Val
0x14000c98c  call    memset_0
0x14000c991  mov     r10d, edi
0x14000c994  test    esi, esi
0x14000c996  jle     loc_14000CA76
0x14000c99c  mov     r14d, 30h ; '0'
0x14000c9a2  mov     eax, r10d
0x14000c9a5  movzx   r9d, [rbp+rax*2+21B0h+String1]
0x14000c9ae  cmp     r9d, 61h ; 'a'
0x14000c9b2  ja      short loc_14000CA1E
0x14000c9b4  jz      loc_14000CA3F
0x14000c9ba  cmp     r9d, 38h ; '8'
0x14000c9be  ja      short loc_14000C9F2
0x14000c9c0  jz      short loc_14000C9ED
0x14000c9c2  mov     ecx, r9d
0x14000c9c5  sub     ecx, r14d
0x14000c9c8  jz      short loc_14000C9ED
0x14000c9ca  sub     ecx, 1
0x14000c9cd  jz      short loc_14000C9ED
0x14000c9cf  sub     ecx, 1
0x14000c9d2  jz      short loc_14000C9ED
0x14000c9d4  sub     ecx, 1
0x14000c9d7  jz      short loc_14000C9ED
0x14000c9d9  sub     ecx, 1
0x14000c9dc  jz      short loc_14000C9ED
0x14000c9de  sub     ecx, 1
0x14000c9e1  jz      short loc_14000C9ED
0x14000c9e3  sub     ecx, 1
0x14000c9e6  jz      short loc_14000C9ED
0x14000c9e8  cmp     ecx, 1
0x14000c9eb  jnz     short loc_14000CA3A
0x14000c9ed  sub     r9b, r14b
0x14000c9f0  jmp     short loc_14000CA43
0x14000c9f2  mov     ecx, r9d
0x14000c9f5  sub     ecx, 39h ; '9'
0x14000c9f8  jz      short loc_14000C9ED
0x14000c9fa  sub     ecx, 8
0x14000c9fd  jz      short loc_14000CA18
0x14000c9ff  sub     ecx, 1
0x14000ca02  jz      short loc_14000CA18
0x14000ca04  sub     ecx, 1
0x14000ca07  jz      short loc_14000CA18
0x14000ca09  sub     ecx, 1
0x14000ca0c  jz      short loc_14000CA18
0x14000ca0e  sub     ecx, 1
0x14000ca11  jz      short loc_14000CA18
0x14000ca13  cmp     ecx, 1
0x14000ca16  jnz     short loc_14000CA3A
0x14000ca18  sub     r9b, 37h ; '7'
0x14000ca1c  jmp     short loc_14000CA43
0x14000ca1e  mov     ecx, r9d
0x14000ca21  sub     ecx, 62h ; 'b'
0x14000ca24  jz      short loc_14000CA3F
0x14000ca26  sub     ecx, 1
0x14000ca29  jz      short loc_14000CA3F
0x14000ca2b  sub     ecx, 1
0x14000ca2e  jz      short loc_14000CA3F
0x14000ca30  sub     ecx, 1
0x14000ca33  jz      short loc_14000CA3F
0x14000ca35  cmp     ecx, 1
0x14000ca38  jz      short loc_14000CA3F
0x14000ca3a  mov     r9b, dil
0x14000ca3d  jmp     short loc_14000CA43
0x14000ca3f  sub     r9b, 57h ; 'W'
0x14000ca43  mov     rdx, [rsp+22B0h+var_2270]
0x14000ca48  mov     eax, r10d
0x14000ca4b  and     eax, 1
0x14000ca4e  mov     r8d, r10d
0x14000ca51  shl     eax, 2
0x14000ca54  mov     ecx, 4
0x14000ca59  shr     r8, 1
0x14000ca5c  sub     ecx, eax
0x14000ca5e  shl     r9b, cl
0x14000ca61  inc     r10d
0x14000ca64  or      [r8+rdx], r9b
0x14000ca68  cmp     r10d, esi
0x14000ca6b  jl      loc_14000C9A2
0x14000ca71  mov     r14, qword ptr [rsp+22B0h+pulOut]
0x14000ca76  mov     rax, [rsp+22B0h+var_2270]
0x14000ca7b  mov     r9d, 3; dwType
0x14000ca81  mov     rcx, [r13+0]; hKey
0x14000ca85  xor     r8d, r8d; Reserved
0x14000ca88  mov     [rsp+22B0h+cbData], r15d; cbData
  ... truncated ...
```
