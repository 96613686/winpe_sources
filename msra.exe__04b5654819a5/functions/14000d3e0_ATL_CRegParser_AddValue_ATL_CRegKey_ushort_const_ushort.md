# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x14000d3e0`
- end: `0x14000d9e5`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1541`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140015bdc`

## callees

- `0x140002463`
- `0x1400044f8`
- `0x14000d3e0`
- `0x14000d9fc`
- `0x14000e520`
- `0x1400105d8`
- `0x140011b60`
- `0x14004ad80`
- `0x14004ae40`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x14000d67c`
- `ADVAPI32!RegSetValueExW` at `0x14000d720`
- `ADVAPI32!RegSetValueExW` at `0x14000d927`
- `ADVAPI32!RegSetValueExW` at `0x14000d67c`
- `ADVAPI32!RegSetValueExW` at `0x14000d720`
- `ADVAPI32!RegSetValueExW` at `0x14000d927`
- `KERNEL32!lstrcmpiW` at `0x14000d471`
- `KERNEL32!lstrcmpiW` at `0x14000d471`
- `USER32!CharNextW` at `0x14000d5e7`
- `USER32!CharNextW` at `0x14000d609`
- `USER32!CharNextW` at `0x14000d9af`
- `USER32!CharNextW` at `0x14000d5e7`
- `USER32!CharNextW` at `0x14000d609`
- `USER32!CharNextW` at `0x14000d9af`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000d6e2`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x14000d6e2`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  HKEY *v5; // r12
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 v11; // rax
  int v12; // eax
  BYTE *v13; // rdi
  const WCHAR *v14; // r13
  WCHAR *i; // r14
  const WCHAR *v16; // rax
  DWORD v17; // r10d
  BYTE *v18; // r9
  __int64 v19; // rcx
  __int64 v20; // rcx
  LSTATUS v21; // esi
  const BYTE *v22; // rax
  DWORD v23; // r9d
  __int64 v24; // r14
  DWORD v25; // r12d
  size_t v26; // rdi
  BYTE *v27; // rcx
  HKEY *v28; // rsi
  unsigned int v29; // r10d
  unsigned int v30; // edx
  char v31; // r9
  __int64 v32; // rsi
  int Token; // eax
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v36; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v39; // [rsp+50h] [rbp-22A8h]
  const WCHAR *v40; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v41; // [rsp+70h] [rbp-2288h]
  size_t v42; // [rsp+78h] [rbp-2280h]
  struct ATL::CRegKey *v43; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v44; // [rsp+88h] [rbp-2270h]
  BYTE *v45; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v46[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v48[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v41 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v36 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v39 = (ATL::CRegParser *)this;
  v43 = (struct ATL::CRegKey *)a2;
  v40 = a3;
  v44 = a4;
  result = ATL::CRegParser::NextToken((ATL::CRegParser *)this, String1);
  v8 = 0;
  if ( result >= 0 )
  {
    v9 = 0;
    while ( lstrcmpiW(String1, (&`ATL::CRegParser::VTFromRegType'::`2'::map)[2 * v9]) )
    {
      if ( (unsigned int)++v9 >= 4 )
        return -2147352567;
    }
    v10 = *((_WORD *)&`ATL::CRegParser::VTFromRegType'::`2'::map + 8 * v9 + 4);
    while ( **v6 == 9 || **v6 == 10 || **v6 == 13 || **v6 == 32 )
      *v6 = CharNextW(*v6);
    result = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, String1);
    if ( result >= 0 )
    {
      if ( v10 == 8 )
      {
        v32 = -1;
        do
          ++v32;
        while ( String1[v32] );
        cbData = 2 * v32 + 2;
        v22 = (const BYTE *)String1;
        v23 = 1;
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_93:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v44);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v11 = -1;
          do
            ++v11;
          while ( String1[v11] );
          v12 = v11 + 2;
          lpData = 0;
          try
          {
            if ( !v12 )
              goto LABEL_24;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v12 < 2 )
              ATL::AtlThrowImpl(-2147024809);
            if ( (unsigned __int64)(2LL * v12) > 0x100 )
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, 2LL * v12);
              v13 = lpData;
            }
            else
            {
LABEL_24:
              v13 = v48;
              lpData = v48;
            }
          }
          catch ( ... )
          {
            v8 = 0;
            v13 = lpData;
            v5 = *(HKEY **)Data;
            v36 = v39;
            v14 = v40;
            goto LABEL_26;
          }
          v14 = lpValueName;
LABEL_26:
          if ( v13 )
          {
            for ( i = String1; *i; v13 += 2 )
            {
              v16 = CharNextW(i);
              if ( *i == 92 && *v16 == 48 )
              {
                *(_WORD *)v13 = 0;
                i = CharNextW(v16);
              }
              else
              {
                *(_WORD *)v13 = *i++;
              }
            }
            *(_DWORD *)v13 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v17 = 0;
            v18 = lpData;
            do
            {
              v19 = -1;
              do
                ++v19;
              while ( *(_WORD *)&v18[2 * v19] );
              v20 = (unsigned int)(v19 + 1);
              v18 += 2 * v20;
              v17 += 2 * v20;
            }
            while ( (_DWORD)v20 != 1 );
            v21 = RegSetValueExW(*v5, v14, 0, 7u, lpData, v17);
            v13 = lpData;
          }
          else
          {
            v21 = 14;
          }
          if ( v13 != v48 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_42;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v22 = Data;
        v23 = 4;
LABEL_47:
        v21 = RegSetValueExW(*v5, a3, 0, v23, v22, cbData);
LABEL_43:
        if ( v21 )
          return ATL::AtlHresultFromWin32(v21);
        goto LABEL_93;
      }
      v24 = -1;
      do
        ++v24;
      while ( String1[v24] );
      *(_DWORD *)Data = v24;
      if ( (v24 & 1) != 0 )
        return -2147467259;
      try
      {
        v25 = (int)v24 / 2;
        v45 = 0;
        v26 = (int)v24 / 2;
        v42 = v26;
        if ( !((int)v24 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v26) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v26 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v45, v26);
          v27 = v45;
        }
        else
        {
LABEL_56:
          v27 = v46;
          v45 = v46;
        }
        v28 = (HKEY *)v41;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v24) = *(_DWORD *)Data;
        v27 = v45;
        v26 = v42;
        v36 = v39;
        v28 = (HKEY *)v43;
        lpValueName = v40;
        v25 = v42;
      }
      if ( !v27 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
        return -2147467259;
      }
      memset_0(v27, 0, v26);
      v29 = 0;
      if ( (int)v24 <= 0 )
      {
LABEL_88:
        v21 = RegSetValueExW(*v28, lpValueName, 0, 3u, v45, v25);
        if ( v45 != v46 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v45);
LABEL_42:
        v6 = (LPCWSTR *)v36;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v30 = String1[v29];
        if ( v30 > 0x61 )
        {
          if ( v30 == 98 || v30 == 99 || v30 == 100 || v30 - 101 < 2 )
          {
LABEL_86:
            v31 = v30 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v31 = 0;
          goto LABEL_87;
        }
        if ( v30 == 97 )
          goto LABEL_86;
        if ( v30 <= 0x38 )
          break;
        if ( v30 == 57 )
          goto LABEL_73;
        if ( v30 != 65 && v30 != 66 && v30 != 67 && v30 != 68 && v30 - 69 > 1 )
          goto LABEL_85;
        v31 = v30 - 55;
LABEL_87:
        v45[(unsigned __int64)v29 >> 1] |= v31 << (4 - 4 * (v29 & 1));
        if ( (int)++v29 >= (int)v24 )
          goto LABEL_88;
      }
      if ( v30 != 56 && v30 != 48 && v30 != 49 && v30 != 50 && v30 != 51 && v30 != 52 && v30 != 53 && v30 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v31 = v30 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000d3e0  push    rbx
0x14000d3e2  push    rsi
0x14000d3e3  push    rdi
0x14000d3e4  push    r12
0x14000d3e6  push    r13
0x14000d3e8  push    r14
0x14000d3ea  push    r15
0x14000d3ec  mov     eax, 22C0h
0x14000d3f1  call    _alloca_probe
0x14000d3f6  sub     rsp, rax
0x14000d3f9  mov     rax, cs:__security_cookie
0x14000d400  xor     rax, rsp
0x14000d403  mov     [rsp+22F8h+var_48], rax
0x14000d40b  mov     r14, r8
0x14000d40e  mov     [rsp+22F8h+lpValueName], r8
0x14000d413  mov     r12, rdx
0x14000d416  mov     [rsp+22F8h+var_2288], rdx
0x14000d41b  mov     r15, rcx
0x14000d41e  mov     [rsp+22F8h+var_22C0], rcx
0x14000d423  mov     qword ptr [rsp+22F8h+Data], rdx
0x14000d428  mov     [rsp+22F8h+var_22A8], rcx
0x14000d42d  mov     [rsp+22F8h+var_2278], rdx
0x14000d435  mov     [rsp+22F8h+var_2298], r8
0x14000d43a  mov     [rsp+22F8h+var_2270], r9
0x14000d442  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x14000d44a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000d44f  xor     ebx, ebx
0x14000d451  test    eax, eax
0x14000d453  js      short loc_14000D48D
0x14000d455  mov     edi, ebx
0x14000d457  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x14000d45e  movsxd  rsi, edi
0x14000d461  add     rsi, rsi
0x14000d464  mov     rdx, [r13+rsi*8+0]; lpString2
0x14000d469  lea     rcx, [rsp+22F8h+String1]; lpString1
0x14000d471  call    cs:__imp_lstrcmpiW
0x14000d478  nop     dword ptr [rax+rax+00h]
0x14000d47d  test    eax, eax
0x14000d47f  jz      short loc_14000D4B1
0x14000d481  inc     edi
0x14000d483  cmp     edi, 4
0x14000d486  jb      short loc_14000D45E
0x14000d488  mov     eax, 80020009h
0x14000d48d  mov     rcx, [rsp+22F8h+var_48]
0x14000d495  xor     rcx, rsp; StackCookie
0x14000d498  call    __security_check_cookie
0x14000d49d  add     rsp, 22C0h
0x14000d4a4  pop     r15
0x14000d4a6  pop     r14
0x14000d4a8  pop     r13
0x14000d4aa  pop     r12
0x14000d4ac  pop     rdi
0x14000d4ad  pop     rsi
0x14000d4ae  pop     rbx
0x14000d4af  retn
0x14000d4b1  movzx   edi, word ptr [r13+rsi*8+8]
0x14000d4b7  mov     esi, 13h
0x14000d4bc  mov     rdx, [r15]
0x14000d4bf  movzx   ecx, word ptr [rdx]
0x14000d4c2  sub     ecx, 9
0x14000d4c5  jz      loc_14000D9AC
0x14000d4cb  sub     ecx, 1
0x14000d4ce  jz      loc_14000D9AC
0x14000d4d4  sub     ecx, 3
0x14000d4d7  jz      loc_14000D9AC
0x14000d4dd  cmp     ecx, esi
0x14000d4df  jz      loc_14000D9AC
0x14000d4e5  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x14000d4ed  mov     rcx, r15; this
0x14000d4f0  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x14000d4f5  test    eax, eax
0x14000d4f7  js      short loc_14000D48D
0x14000d4f9  mov     r13d, 8
0x14000d4ff  cmp     di, r13w
0x14000d503  jz      loc_14000D95D
0x14000d509  cmp     di, 11h
0x14000d50d  jz      loc_14000D730
0x14000d513  cmp     di, si
0x14000d516  jz      loc_14000D6CC
0x14000d51c  mov     eax, 4008h
0x14000d521  cmp     di, ax
0x14000d524  jnz     loc_14000D990
0x14000d52a  lea     rcx, [rsp+22F8h+String1]
0x14000d532  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d536  mov     rax, rsi
0x14000d539  inc     rax
0x14000d53c  cmp     [rcx+rax*2], bx
0x14000d540  jnz     short loc_14000D539
0x14000d542  add     eax, 2
0x14000d545  mov     [rsp+22F8h+var_2158], rbx
0x14000d54d  test    eax, eax
0x14000d54f  jz      short loc_14000D58A
0x14000d551  movsxd  rcx, eax
0x14000d554  xor     edx, edx
0x14000d556  mov     rax, rsi
0x14000d559  div     rcx
0x14000d55c  cmp     rax, 2
0x14000d560  jb      loc_14000D9C3
0x14000d566  lea     rdx, [rcx+rcx]
0x14000d56a  cmp     rdx, 100h
0x14000d571  jbe     short loc_14000D58A
0x14000d573  lea     rcx, [rsp+22F8h+var_2158]
0x14000d57b  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000d580  mov     rdi, [rsp+22F8h+var_2158]
0x14000d588  jmp     short loc_14000D59A
0x14000d58a  lea     rdi, [rsp+22F8h+var_2150]
0x14000d592  mov     [rsp+22F8h+var_2158], rdi
0x14000d59a  mov     r13, [rsp+22F8h+lpValueName]
0x14000d59f  jmp     short loc_14000D5C3
0x14000d5a1  xor     ebx, ebx
0x14000d5a3  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d5a7  mov     rdi, [rsp+22F8h+var_2158]
0x14000d5af  mov     r12, qword ptr [rsp+22F8h+Data]
0x14000d5b4  mov     rax, [rsp+22F8h+var_22A8]
0x14000d5b9  mov     [rsp+22F8h+var_22C0], rax
0x14000d5be  mov     r13, [rsp+22F8h+var_2298]
0x14000d5c3  test    rdi, rdi
0x14000d5c6  jz      loc_14000D694
0x14000d5cc  lea     r14, [rsp+22F8h+String1]
0x14000d5d4  cmp     [rsp+22F8h+String1], bx
0x14000d5dc  jz      short loc_14000D62B
0x14000d5de  mov     r15d, 30h ; '0'
0x14000d5e4  mov     rcx, r14; lpsz
0x14000d5e7  call    cs:__imp_CharNextW
0x14000d5ee  nop     dword ptr [rax+rax+00h]
0x14000d5f3  movzx   ecx, word ptr [r14]
0x14000d5f7  cmp     cx, 5Ch ; '\'
0x14000d5fb  jnz     short loc_14000D61A
0x14000d5fd  cmp     [rax], r15w
0x14000d601  jnz     short loc_14000D61A
0x14000d603  mov     [rdi], bx
0x14000d606  mov     rcx, rax; lpsz
0x14000d609  call    cs:__imp_CharNextW
0x14000d610  nop     dword ptr [rax+rax+00h]
0x14000d615  mov     r14, rax
0x14000d618  jmp     short loc_14000D621
0x14000d61a  mov     [rdi], cx
0x14000d61d  add     r14, 2
0x14000d621  add     rdi, 2
0x14000d625  cmp     [r14], bx
0x14000d629  jnz     short loc_14000D5E4
0x14000d62b  mov     dword ptr [rdi], 0
0x14000d631  mov     r8, [rsp+22F8h+var_2158]
0x14000d639  test    r8, r8
0x14000d63c  jz      loc_14000D9CE
0x14000d642  mov     r10d, ebx
0x14000d645  mov     r9, r8
0x14000d648  mov     rcx, rsi
0x14000d64b  inc     rcx
0x14000d64e  cmp     [r9+rcx*2], bx
0x14000d653  jnz     short loc_14000D64B
0x14000d655  inc     ecx
0x14000d657  lea     r9, [r9+rcx*2]
0x14000d65b  lea     r10d, [r10+rcx*2]
0x14000d65f  cmp     ecx, 1
0x14000d662  jnz     short loc_14000D648
0x14000d664  mov     [rsp+22F8h+cbData], r10d; cbData
0x14000d669  mov     [rsp+22F8h+lpData], r8; lpData
0x14000d66e  lea     r9d, [rcx+6]; dwType
0x14000d672  xor     r8d, r8d; Reserved
0x14000d675  mov     rdx, r13; lpValueName
0x14000d678  mov     rcx, [r12]; hKey
0x14000d67c  call    cs:__imp_RegSetValueExW
0x14000d683  nop     dword ptr [rax+rax+00h]
0x14000d688  mov     esi, eax
0x14000d68a  mov     rdi, [rsp+22F8h+var_2158]
0x14000d692  jmp     short loc_14000D699
0x14000d694  mov     esi, 0Eh
0x14000d699  lea     rax, [rsp+22F8h+var_2150]
0x14000d6a1  cmp     rdi, rax
0x14000d6a4  jz      short loc_14000D6B3
0x14000d6a6  lea     rcx, [rsp+22F8h+var_2158]
0x14000d6ae  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000d6b3  mov     r15, [rsp+22F8h+var_22C0]
0x14000d6b8  test    esi, esi
0x14000d6ba  jz      loc_14000D990
0x14000d6c0  mov     ecx, esi; unsigned int
0x14000d6c2  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x14000d6c7  jmp     loc_14000D48D
0x14000d6cc  mov     [rsp+22F8h+pulOut], ebx
0x14000d6d0  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x14000d6d5  xor     r8d, r8d; dwFlags
0x14000d6d8  xor     edx, edx; lcid
0x14000d6da  lea     rcx, [rsp+22F8h+String1]; strIn
0x14000d6e2  call    cs:__imp_VarUI4FromStr
0x14000d6e9  nop     dword ptr [rax+rax+00h]
0x14000d6ee  test    eax, eax
0x14000d6f0  js      loc_14000D48D
0x14000d6f6  mov     eax, [rsp+22F8h+pulOut]
0x14000d6fa  mov     dword ptr [rsp+22F8h+Data], eax
0x14000d6fe  mov     [rsp+22F8h+cbData], 4; cbData
0x14000d706  lea     rax, [rsp+22F8h+Data]
0x14000d70b  mov     r9d, 4; dwType
0x14000d711  mov     [rsp+22F8h+lpData], rax; lpData
0x14000d716  xor     r8d, r8d; Reserved
0x14000d719  mov     rdx, r14; lpValueName
0x14000d71c  mov     rcx, [r12]; hKey
0x14000d720  call    cs:__imp_RegSetValueExW
0x14000d727  nop     dword ptr [rax+rax+00h]
0x14000d72c  mov     esi, eax
0x14000d72e  jmp     short loc_14000D6B8
0x14000d730  lea     rax, [rsp+22F8h+String1]
0x14000d738  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d73c  mov     r14, rsi
0x14000d73f  inc     r14
0x14000d742  cmp     [rax+r14*2], bx
0x14000d747  jnz     short loc_14000D73F
0x14000d749  mov     dword ptr [rsp+22F8h+Data], r14d
0x14000d74e  test    r14b, 1
0x14000d752  jnz     loc_14000D80C
0x14000d758  mov     eax, r14d
0x14000d75b  cdq
0x14000d75c  sub     eax, edx
0x14000d75e  sar     eax, 1
0x14000d760  movsxd  r12, eax
0x14000d763  mov     [rsp+22F8h+var_2268], rbx
0x14000d76b  mov     rdi, r12
0x14000d76e  mov     [rsp+22F8h+var_2280], r12
0x14000d773  test    eax, eax
0x14000d775  jz      short loc_14000D7AC
0x14000d777  xor     edx, edx
0x14000d779  mov     rax, rsi
0x14000d77c  div     rdi
0x14000d77f  cmp     rax, 1
0x14000d783  jb      loc_14000D9D9
0x14000d789  cmp     rdi, 100h
0x14000d790  jbe     short loc_14000D7AC
0x14000d792  mov     rdx, rdi
0x14000d795  lea     rcx, [rsp+22F8h+var_2268]
0x14000d79d  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x14000d7a2  mov     rcx, [rsp+22F8h+var_2268]
0x14000d7aa  jmp     short loc_14000D7BC
0x14000d7ac  lea     rcx, [rsp+22F8h+var_2260]
0x14000d7b4  mov     [rsp+22F8h+var_2268], rcx
0x14000d7bc  mov     rsi, [rsp+22F8h+var_2288]
0x14000d7c1  jmp     short loc_14000D7FA
0x14000d7c3  xor     ebx, ebx
0x14000d7c5  lea     r13d, [rbx+8]
0x14000d7c9  mov     r14d, dword ptr [rsp+22F8h+Data]
0x14000d7ce  mov     rcx, [rsp+22F8h+var_2268]; void *
0x14000d7d6  mov     rdi, [rsp+22F8h+var_2280]
0x14000d7db  mov     rax, [rsp+22F8h+var_22A8]
0x14000d7e0  mov     [rsp+22F8h+var_22C0], rax
0x14000d7e5  mov     rsi, [rsp+22F8h+var_2278]
0x14000d7ed  mov     rax, [rsp+22F8h+var_2298]
0x14000d7f2  mov     [rsp+22F8h+lpValueName], rax
0x14000d7f7  mov     r12d, edi
0x14000d7fa  test    rcx, rcx
0x14000d7fd  jnz     short loc_14000D816
0x14000d7ff  lea     rcx, [rsp+22F8h+var_2268]
0x14000d807  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x14000d80c  mov     eax, 80004005h
0x14000d811  jmp     loc_14000D48D
0x14000d816  mov     r8, rdi; Size
0x14000d819  xor     edx, edx; Val
0x14000d81b  call    memset_0
0x14000d820  mov     r10d, ebx
0x14000d823  test    r14d, r14d
0x14000d826  jle     loc_14000D904
0x14000d82c  mov     r15d, 30h ; '0'
0x14000d832  mov     eax, r10d
0x14000d835  movzx   edx, [rsp+rax*2+22F8h+String1]
0x14000d83d  cmp     edx, 61h ; 'a'
0x14000d840  ja      short loc_14000D8AF
0x14000d842  jz      loc_14000D8CF
0x14000d848  cmp     edx, 38h ; '8'
0x14000d84b  ja      short loc_14000D881
0x14000d84d  jz      short loc_14000D879
0x14000d84f  mov     ecx, edx
0x14000d851  sub     ecx, r15d
0x14000d854  jz      short loc_14000D879
0x14000d856  sub     ecx, 1
0x14000d859  jz      short loc_14000D879
0x14000d85b  sub     ecx, 1
0x14000d85e  jz      short loc_14000D879
0x14000d860  sub     ecx, 1
0x14000d863  jz      short loc_14000D879
0x14000d865  sub     ecx, 1
0x14000d868  jz      short loc_14000D879
0x14000d86a  sub     ecx, 1
0x14000d86d  jz      short loc_14000D879
0x14000d86f  sub     ecx, 1
0x14000d872  jz      short loc_14000D879
0x14000d874  cmp     ecx, 1
0x14000d877  jnz     short loc_14000D8CA
0x14000d879  mov     r9d, edx
0x14000d87c  sub     r9d, r15d
0x14000d87f  jmp     short loc_14000D8D3
0x14000d881  mov     r9d, edx
0x14000d884  mov     ecx, edx
0x14000d886  sub     ecx, 39h ; '9'
0x14000d889  jz      short loc_14000D879
0x14000d88b  sub     ecx, r13d
0x14000d88e  jz      short loc_14000D8A9
0x14000d890  sub     ecx, 1
0x14000d893  jz      short loc_14000D8A9
0x14000d895  sub     ecx, 1
0x14000d898  jz      short loc_14000D8A9
0x14000d89a  sub     ecx, 1
0x14000d89d  jz      short loc_14000D8A9
  ... truncated ...
```
