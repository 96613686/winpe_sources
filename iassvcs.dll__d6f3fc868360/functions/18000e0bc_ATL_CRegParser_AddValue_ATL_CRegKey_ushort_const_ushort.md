# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000e0bc`
- end: `0x18000e690`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180011384`

## callees

- `0x18000e0bc`
- `0x18000e698`
- `0x18000e8f8`
- `0x18000f208`
- `0x18000fe34`
- `0x1800107e0`
- `0x1800181a2`
- `0x1800181e0`
- `0x1800182a0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x18000e345`
- `ADVAPI32!RegSetValueExW` at `0x18000e3dd`
- `ADVAPI32!RegSetValueExW` at `0x18000e5de`
- `ADVAPI32!RegSetValueExW` at `0x18000e345`
- `ADVAPI32!RegSetValueExW` at `0x18000e3dd`
- `ADVAPI32!RegSetValueExW` at `0x18000e5de`
- `KERNEL32!lstrcmpiW` at `0x18000e14d`
- `KERNEL32!lstrcmpiW` at `0x18000e14d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000e3a5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000e3a5`
- `USER32!CharNextW` at `0x18000e2bc`
- `USER32!CharNextW` at `0x18000e2d8`
- `USER32!CharNextW` at `0x18000e660`
- `USER32!CharNextW` at `0x18000e2bc`
- `USER32!CharNextW` at `0x18000e2d8`
- `USER32!CharNextW` at `0x18000e660`

## pseudocode

```c
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
0x18000e0bc  push    rbx
0x18000e0be  push    rsi
0x18000e0bf  push    rdi
0x18000e0c0  push    r12
0x18000e0c2  push    r13
0x18000e0c4  push    r14
0x18000e0c6  push    r15
0x18000e0c8  mov     eax, 22C0h
0x18000e0cd  call    _alloca_probe
0x18000e0d2  sub     rsp, rax
0x18000e0d5  mov     rax, cs:__security_cookie
0x18000e0dc  xor     rax, rsp
0x18000e0df  mov     [rsp+22F8h+var_48], rax
0x18000e0e7  mov     r14, r8
0x18000e0ea  mov     [rsp+22F8h+lpValueName], r8
0x18000e0ef  mov     r12, rdx
0x18000e0f2  mov     [rsp+22F8h+var_2288], rdx
0x18000e0f7  mov     r15, rcx
0x18000e0fa  mov     [rsp+22F8h+var_22C0], rcx
0x18000e0ff  mov     qword ptr [rsp+22F8h+Data], rdx
0x18000e104  mov     [rsp+22F8h+var_22A8], rcx
0x18000e109  mov     [rsp+22F8h+var_2278], rdx
0x18000e111  mov     [rsp+22F8h+var_2298], r8
0x18000e116  mov     [rsp+22F8h+var_2270], r9
0x18000e11e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000e126  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e12b  xor     ebx, ebx
0x18000e12d  test    eax, eax
0x18000e12f  js      short loc_18000E163
0x18000e131  mov     edi, ebx
0x18000e133  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000e13a  movsxd  rsi, edi
0x18000e13d  add     rsi, rsi
0x18000e140  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000e145  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000e14d  call    cs:__imp_lstrcmpiW
0x18000e153  test    eax, eax
0x18000e155  jz      short loc_18000E186
0x18000e157  inc     edi
0x18000e159  cmp     edi, 4
0x18000e15c  jb      short loc_18000E13A
0x18000e15e  mov     eax, 80020009h
0x18000e163  mov     rcx, [rsp+22F8h+var_48]
0x18000e16b  xor     rcx, rsp; StackCookie
0x18000e16e  call    __security_check_cookie
0x18000e173  add     rsp, 22C0h
0x18000e17a  pop     r15
0x18000e17c  pop     r14
0x18000e17e  pop     r13
0x18000e180  pop     r12
0x18000e182  pop     rdi
0x18000e183  pop     rsi
0x18000e184  pop     rbx
0x18000e185  retn
0x18000e186  movzx   edi, word ptr [r13+rsi*8+8]
0x18000e18c  mov     esi, 13h
0x18000e191  mov     rdx, [r15]
0x18000e194  movzx   ecx, word ptr [rdx]
0x18000e197  sub     ecx, 9
0x18000e19a  jz      loc_18000E65D
0x18000e1a0  sub     ecx, 1
0x18000e1a3  jz      loc_18000E65D
0x18000e1a9  sub     ecx, 3
0x18000e1ac  jz      loc_18000E65D
0x18000e1b2  cmp     ecx, esi
0x18000e1b4  jz      loc_18000E65D
0x18000e1ba  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000e1c2  mov     rcx, r15; this
0x18000e1c5  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000e1ca  test    eax, eax
0x18000e1cc  js      short loc_18000E163
0x18000e1ce  mov     r13d, 8
0x18000e1d4  cmp     di, r13w
0x18000e1d8  jz      loc_18000E60E
0x18000e1de  cmp     di, 11h
0x18000e1e2  jz      loc_18000E3E7
0x18000e1e8  cmp     di, si
0x18000e1eb  jz      loc_18000E38F
0x18000e1f1  mov     eax, 4008h
0x18000e1f6  cmp     di, ax
0x18000e1f9  jnz     loc_18000E641
0x18000e1ff  lea     rcx, [rsp+22F8h+String1]
0x18000e207  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e20b  mov     rax, rsi
0x18000e20e  inc     rax
0x18000e211  cmp     [rcx+rax*2], bx
0x18000e215  jnz     short loc_18000E20E
0x18000e217  add     eax, 2
0x18000e21a  mov     [rsp+22F8h+var_2158], rbx
0x18000e222  test    eax, eax
0x18000e224  jz      short loc_18000E25F
0x18000e226  movsxd  rcx, eax
0x18000e229  xor     edx, edx
0x18000e22b  mov     rax, rsi
0x18000e22e  div     rcx
0x18000e231  cmp     rax, 2
0x18000e235  jb      loc_18000E66E
0x18000e23b  lea     rdx, [rcx+rcx]
0x18000e23f  cmp     rdx, 100h
0x18000e246  jbe     short loc_18000E25F
0x18000e248  lea     rcx, [rsp+22F8h+var_2158]
0x18000e250  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000e255  mov     rdi, [rsp+22F8h+var_2158]
0x18000e25d  jmp     short loc_18000E26F
0x18000e25f  lea     rdi, [rsp+22F8h+var_2150]
0x18000e267  mov     [rsp+22F8h+var_2158], rdi
0x18000e26f  mov     r13, [rsp+22F8h+lpValueName]
0x18000e274  jmp     short loc_18000E298
0x18000e276  xor     ebx, ebx
0x18000e278  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e27c  mov     rdi, [rsp+22F8h+var_2158]
0x18000e284  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000e289  mov     rax, [rsp+22F8h+var_22A8]
0x18000e28e  mov     [rsp+22F8h+var_22C0], rax
0x18000e293  mov     r13, [rsp+22F8h+var_2298]
0x18000e298  test    rdi, rdi
0x18000e29b  jz      loc_18000E357
0x18000e2a1  lea     r14, [rsp+22F8h+String1]
0x18000e2a9  cmp     [rsp+22F8h+String1], bx
0x18000e2b1  jz      short loc_18000E2F4
0x18000e2b3  mov     r15d, 30h ; '0'
0x18000e2b9  mov     rcx, r14; lpsz
0x18000e2bc  call    cs:__imp_CharNextW
0x18000e2c2  movzx   ecx, word ptr [r14]
0x18000e2c6  cmp     cx, 5Ch ; '\'
0x18000e2ca  jnz     short loc_18000E2E3
0x18000e2cc  cmp     [rax], r15w
0x18000e2d0  jnz     short loc_18000E2E3
0x18000e2d2  mov     [rdi], bx
0x18000e2d5  mov     rcx, rax; lpsz
0x18000e2d8  call    cs:__imp_CharNextW
0x18000e2de  mov     r14, rax
0x18000e2e1  jmp     short loc_18000E2EA
0x18000e2e3  mov     [rdi], cx
0x18000e2e6  add     r14, 2
0x18000e2ea  add     rdi, 2
0x18000e2ee  cmp     [r14], bx
0x18000e2f2  jnz     short loc_18000E2B9
0x18000e2f4  mov     dword ptr [rdi], 0
0x18000e2fa  mov     r8, [rsp+22F8h+var_2158]
0x18000e302  test    r8, r8
0x18000e305  jz      loc_18000E679
0x18000e30b  mov     r10d, ebx
0x18000e30e  mov     r9, r8
0x18000e311  mov     rcx, rsi
0x18000e314  inc     rcx
0x18000e317  cmp     [r9+rcx*2], bx
0x18000e31c  jnz     short loc_18000E314
0x18000e31e  inc     ecx
0x18000e320  lea     r9, [r9+rcx*2]
0x18000e324  lea     r10d, [r10+rcx*2]
0x18000e328  cmp     ecx, 1
0x18000e32b  jnz     short loc_18000E311
0x18000e32d  mov     [rsp+22F8h+cbData], r10d; cbData
0x18000e332  mov     [rsp+22F8h+lpData], r8; lpData
0x18000e337  lea     r9d, [rcx+6]; dwType
0x18000e33b  xor     r8d, r8d; Reserved
0x18000e33e  mov     rdx, r13; lpValueName
0x18000e341  mov     rcx, [r12]; hKey
0x18000e345  call    cs:__imp_RegSetValueExW
0x18000e34b  mov     esi, eax
0x18000e34d  mov     rdi, [rsp+22F8h+var_2158]
0x18000e355  jmp     short loc_18000E35C
0x18000e357  mov     esi, 0Eh
0x18000e35c  lea     rax, [rsp+22F8h+var_2150]
0x18000e364  cmp     rdi, rax
0x18000e367  jz      short loc_18000E376
0x18000e369  lea     rcx, [rsp+22F8h+var_2158]
0x18000e371  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000e376  mov     r15, [rsp+22F8h+var_22C0]
0x18000e37b  test    esi, esi
0x18000e37d  jz      loc_18000E641
0x18000e383  mov     ecx, esi; unsigned int
0x18000e385  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x18000e38a  jmp     loc_18000E163
0x18000e38f  mov     [rsp+22F8h+pulOut], ebx
0x18000e393  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000e398  xor     r8d, r8d; dwFlags
0x18000e39b  xor     edx, edx; lcid
0x18000e39d  lea     rcx, [rsp+22F8h+String1]; strIn
0x18000e3a5  call    cs:__imp_VarUI4FromStr
0x18000e3ab  test    eax, eax
0x18000e3ad  js      loc_18000E163
0x18000e3b3  mov     eax, [rsp+22F8h+pulOut]
0x18000e3b7  mov     dword ptr [rsp+22F8h+Data], eax
0x18000e3bb  mov     [rsp+22F8h+cbData], 4; cbData
0x18000e3c3  lea     rax, [rsp+22F8h+Data]
0x18000e3c8  mov     r9d, 4; dwType
0x18000e3ce  mov     [rsp+22F8h+lpData], rax; lpData
0x18000e3d3  xor     r8d, r8d; Reserved
0x18000e3d6  mov     rdx, r14; lpValueName
0x18000e3d9  mov     rcx, [r12]; hKey
0x18000e3dd  call    cs:__imp_RegSetValueExW
0x18000e3e3  mov     esi, eax
0x18000e3e5  jmp     short loc_18000E37B
0x18000e3e7  lea     rax, [rsp+22F8h+String1]
0x18000e3ef  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e3f3  mov     r14, rsi
0x18000e3f6  inc     r14
0x18000e3f9  cmp     [rax+r14*2], bx
0x18000e3fe  jnz     short loc_18000E3F6
0x18000e400  mov     dword ptr [rsp+22F8h+Data], r14d
0x18000e405  test    r14b, 1
0x18000e409  jnz     loc_18000E4C3
0x18000e40f  mov     eax, r14d
0x18000e412  cdq
0x18000e413  sub     eax, edx
0x18000e415  sar     eax, 1
0x18000e417  movsxd  r12, eax
0x18000e41a  mov     [rsp+22F8h+var_2268], rbx
0x18000e422  mov     rdi, r12
0x18000e425  mov     [rsp+22F8h+var_2280], r12
0x18000e42a  test    eax, eax
0x18000e42c  jz      short loc_18000E463
0x18000e42e  xor     edx, edx
0x18000e430  mov     rax, rsi
0x18000e433  div     rdi
0x18000e436  cmp     rax, 1
0x18000e43a  jb      loc_18000E684
0x18000e440  cmp     rdi, 100h
0x18000e447  jbe     short loc_18000E463
0x18000e449  mov     rdx, rdi
0x18000e44c  lea     rcx, [rsp+22F8h+var_2268]
0x18000e454  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000e459  mov     rcx, [rsp+22F8h+var_2268]
0x18000e461  jmp     short loc_18000E473
0x18000e463  lea     rcx, [rsp+22F8h+var_2260]
0x18000e46b  mov     [rsp+22F8h+var_2268], rcx
0x18000e473  mov     rsi, [rsp+22F8h+var_2288]
0x18000e478  jmp     short loc_18000E4B1
0x18000e47a  xor     ebx, ebx
0x18000e47c  lea     r13d, [rbx+8]
0x18000e480  mov     r14d, dword ptr [rsp+22F8h+Data]
0x18000e485  mov     rcx, [rsp+22F8h+var_2268]; void *
0x18000e48d  mov     rdi, [rsp+22F8h+var_2280]
0x18000e492  mov     rax, [rsp+22F8h+var_22A8]
0x18000e497  mov     [rsp+22F8h+var_22C0], rax
0x18000e49c  mov     rsi, [rsp+22F8h+var_2278]
0x18000e4a4  mov     rax, [rsp+22F8h+var_2298]
0x18000e4a9  mov     [rsp+22F8h+lpValueName], rax
0x18000e4ae  mov     r12d, edi
0x18000e4b1  test    rcx, rcx
0x18000e4b4  jnz     short loc_18000E4CD
0x18000e4b6  lea     rcx, [rsp+22F8h+var_2268]
0x18000e4be  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000e4c3  mov     eax, 80004005h
0x18000e4c8  jmp     loc_18000E163
0x18000e4cd  mov     r8, rdi; Size
0x18000e4d0  xor     edx, edx; Val
0x18000e4d2  call    memset_0
0x18000e4d7  mov     r10d, ebx
0x18000e4da  test    r14d, r14d
0x18000e4dd  jle     loc_18000E5BB
0x18000e4e3  mov     r15d, 30h ; '0'
0x18000e4e9  mov     eax, r10d
0x18000e4ec  movzx   edx, [rsp+rax*2+22F8h+String1]
0x18000e4f4  cmp     edx, 61h ; 'a'
0x18000e4f7  ja      short loc_18000E566
0x18000e4f9  jz      loc_18000E586
0x18000e4ff  cmp     edx, 38h ; '8'
0x18000e502  ja      short loc_18000E538
0x18000e504  jz      short loc_18000E530
0x18000e506  mov     ecx, edx
0x18000e508  sub     ecx, r15d
0x18000e50b  jz      short loc_18000E530
0x18000e50d  sub     ecx, 1
0x18000e510  jz      short loc_18000E530
0x18000e512  sub     ecx, 1
0x18000e515  jz      short loc_18000E530
0x18000e517  sub     ecx, 1
0x18000e51a  jz      short loc_18000E530
0x18000e51c  sub     ecx, 1
0x18000e51f  jz      short loc_18000E530
0x18000e521  sub     ecx, 1
0x18000e524  jz      short loc_18000E530
0x18000e526  sub     ecx, 1
0x18000e529  jz      short loc_18000E530
0x18000e52b  cmp     ecx, 1
0x18000e52e  jnz     short loc_18000E581
0x18000e530  mov     r9d, edx
0x18000e533  sub     r9d, r15d
0x18000e536  jmp     short loc_18000E58A
0x18000e538  mov     r9d, edx
0x18000e53b  mov     ecx, edx
0x18000e53d  sub     ecx, 39h ; '9'
0x18000e540  jz      short loc_18000E530
0x18000e542  sub     ecx, r13d
0x18000e545  jz      short loc_18000E560
0x18000e547  sub     ecx, 1
0x18000e54a  jz      short loc_18000E560
0x18000e54c  sub     ecx, 1
0x18000e54f  jz      short loc_18000E560
0x18000e551  sub     ecx, 1
0x18000e554  jz      short loc_18000E560
0x18000e556  sub     ecx, 1
0x18000e559  jz      short loc_18000E560
0x18000e55b  cmp     ecx, 1
0x18000e55e  jnz     short loc_18000E581
0x18000e560  add     r9d, 0FFFFFFC9h
0x18000e564  jmp     short loc_18000E58A
  ... truncated ...
```
