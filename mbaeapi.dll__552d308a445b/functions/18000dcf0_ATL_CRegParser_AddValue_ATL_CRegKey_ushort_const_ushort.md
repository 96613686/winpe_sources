# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000dcf0`
- end: `0x18000e2c4`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180011ac8`

## callees

- `0x1800024e0`
- `0x180002efc`
- `0x18000dcf0`
- `0x18000e2cc`
- `0x18000e3e0`
- `0x18000ec4c`
- `0x18000fcc0`
- `0x180010b7c`
- `0x1800588d0`

## import_xrefs

- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000dfd9`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x18000dfd9`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000def0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000df0c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e294`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000def0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000df0c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000e294`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000df79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e011`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e212`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000df79`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e011`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18000e212`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000dd81`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000dd81`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall ATL::CRegParser::AddValue(LPCWSTR *this, HKEY *a2, const unsigned __int16 *a3, unsigned __int16 *a4)
{
  HKEY *v5; // r12
  LPCWSTR *v6; // r15
  HRESULT result; // eax
  int v8; // ebx
  int v9; // edi
  __int16 v10; // di
  __int64 *v11; // rdx
  __int64 v12; // rax
  int v13; // eax
  BYTE *v14; // rdi
  const WCHAR *v15; // r13
  WCHAR *i; // r14
  const WCHAR *v17; // rax
  DWORD v18; // r10d
  BYTE *v19; // r9
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned int v22; // esi
  const BYTE *v23; // rax
  DWORD v24; // r9d
  __int64 v25; // r14
  DWORD v26; // r12d
  size_t v27; // rdi
  BYTE *v28; // rcx
  HKEY *v29; // rsi
  unsigned int v30; // r10d
  unsigned int v31; // edx
  char v32; // r9
  __int64 v33; // rsi
  int Token; // eax
  __int64 v35; // [rsp+0h] [rbp-22F8h] BYREF
  DWORD cbData; // [rsp+28h] [rbp-22D0h]
  ULONG pulOut; // [rsp+30h] [rbp-22C8h] BYREF
  ATL::CRegParser *v38; // [rsp+38h] [rbp-22C0h]
  BYTE Data[8]; // [rsp+40h] [rbp-22B8h] BYREF
  LPCWSTR lpValueName; // [rsp+48h] [rbp-22B0h]
  ATL::CRegParser *v41; // [rsp+50h] [rbp-22A8h]
  const WCHAR *v42; // [rsp+60h] [rbp-2298h]
  struct ATL::CRegKey *v43; // [rsp+70h] [rbp-2288h]
  size_t v44; // [rsp+78h] [rbp-2280h]
  struct ATL::CRegKey *v45; // [rsp+80h] [rbp-2278h]
  unsigned __int16 *v46; // [rsp+88h] [rbp-2270h]
  BYTE *v47; // [rsp+90h] [rbp-2268h] BYREF
  _BYTE v48[264]; // [rsp+98h] [rbp-2260h] BYREF
  BYTE *lpData; // [rsp+1A0h] [rbp-2158h] BYREF
  _BYTE v50[264]; // [rsp+1A8h] [rbp-2150h] BYREF
  OLECHAR String1[4096]; // [rsp+2B0h] [rbp-2048h] BYREF

  lpValueName = a3;
  v5 = a2;
  v43 = (struct ATL::CRegKey *)a2;
  v6 = this;
  v38 = (ATL::CRegParser *)this;
  *(_QWORD *)Data = a2;
  v41 = (ATL::CRegParser *)this;
  v45 = (struct ATL::CRegKey *)a2;
  v42 = a3;
  v46 = a4;
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
        v33 = -1;
        do
          ++v33;
        while ( String1[v33] );
        cbData = 2 * v33 + 2;
        v23 = (const BYTE *)String1;
        v24 = 1;
        goto LABEL_47;
      }
      if ( v10 != 17 )
      {
        if ( v10 != 19 )
        {
          if ( v10 != 16392 )
          {
LABEL_93:
            Token = ATL::CRegParser::NextToken((ATL::CRegParser *)v6, v46);
            if ( Token < 0 )
              return Token;
            return v8;
          }
          v12 = -1;
          do
            ++v12;
          while ( String1[v12] );
          v13 = v12 + 2;
          lpData = 0;
          try
          {
            if ( !v13 )
              goto LABEL_24;
            if ( 0xFFFFFFFFFFFFFFFFuLL / v13 < 2 )
              ATL::AtlThrowImpl(-2147024809);
            v11 = (__int64 *)(2LL * v13);
            if ( (unsigned __int64)v11 > 0x100 )
            {
              ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpData, v11);
              v14 = lpData;
            }
            else
            {
LABEL_24:
              v14 = v50;
              lpData = v50;
            }
          }
          catch ( ... )
          {
            v11 = &v35;
            v8 = 0;
            v14 = lpData;
            v5 = *(HKEY **)Data;
            v38 = v41;
            v15 = v42;
            goto LABEL_26;
          }
          v15 = lpValueName;
LABEL_26:
          if ( v14 )
          {
            for ( i = String1; *i; v14 += 2 )
            {
              v17 = CharNextW(i);
              if ( *i == 92 && *v17 == 48 )
              {
                *(_WORD *)v14 = 0;
                i = CharNextW(v17);
              }
              else
              {
                *(_WORD *)v14 = *i++;
              }
            }
            *(_DWORD *)v14 = 0;
            if ( !lpData )
              ATL::AtlThrowImpl(-2147467259);
            v18 = 0;
            v19 = lpData;
            do
            {
              v20 = -1;
              do
                ++v20;
              while ( *(_WORD *)&v19[2 * v20] );
              v21 = (unsigned int)(v20 + 1);
              v19 += 2 * v21;
              v18 += 2 * v21;
            }
            while ( (_DWORD)v21 != 1 );
            v22 = RegSetValueExW(*v5, v15, 0, 7u, lpData, v18);
            v14 = lpData;
          }
          else
          {
            v22 = 14;
          }
          if ( v14 != v50 )
            ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&lpData);
          goto LABEL_42;
        }
        pulOut = 0;
        result = VarUI4FromStr(String1, 0, 0, &pulOut);
        if ( result < 0 )
          return result;
        *(_DWORD *)Data = pulOut;
        cbData = 4;
        v23 = Data;
        v24 = 4;
LABEL_47:
        v22 = RegSetValueExW(*v5, a3, 0, v24, v23, cbData);
LABEL_43:
        if ( v22 )
          return winrt::impl::hresult_from_win32((winrt::impl *)v22, (unsigned int)v11);
        goto LABEL_93;
      }
      v25 = -1;
      do
        ++v25;
      while ( String1[v25] );
      *(_DWORD *)Data = v25;
      if ( (v25 & 1) != 0 )
        return -2147467259;
      try
      {
        v26 = (int)v25 / 2;
        v47 = 0;
        v27 = (int)v25 / 2;
        v44 = v27;
        if ( !((int)v25 / 2) )
          goto LABEL_56;
        if ( !(0xFFFFFFFFFFFFFFFFuLL / v27) )
          ATL::AtlThrowImpl(-2147024809);
        if ( v27 > 0x100 )
        {
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v47, v27);
          v28 = v47;
        }
        else
        {
LABEL_56:
          v28 = v48;
          v47 = v48;
        }
        v29 = (HKEY *)v43;
      }
      catch ( ... )
      {
        v8 = 0;
        LODWORD(v25) = *(_DWORD *)Data;
        v28 = v47;
        v27 = v44;
        v38 = v41;
        v29 = (HKEY *)v45;
        lpValueName = v42;
        v26 = v44;
      }
      if ( !v28 )
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v47);
        return -2147467259;
      }
      memset_0(v28, 0, v27);
      v30 = 0;
      if ( (int)v25 <= 0 )
      {
LABEL_88:
        v22 = RegSetValueExW(*v29, lpValueName, 0, 3u, v47, v26);
        if ( v47 != v48 )
          ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v47);
LABEL_42:
        v6 = (LPCWSTR *)v38;
        goto LABEL_43;
      }
      while ( 1 )
      {
        v31 = String1[v30];
        if ( v31 > 0x61 )
        {
          if ( v31 == 98 || v31 == 99 || v31 == 100 || v31 - 101 < 2 )
          {
LABEL_86:
            v32 = v31 - 87;
            goto LABEL_87;
          }
LABEL_85:
          v32 = 0;
          goto LABEL_87;
        }
        if ( v31 == 97 )
          goto LABEL_86;
        if ( v31 <= 0x38 )
          break;
        if ( v31 == 57 )
          goto LABEL_73;
        if ( v31 != 65 && v31 != 66 && v31 != 67 && v31 != 68 && v31 - 69 > 1 )
          goto LABEL_85;
        v32 = v31 - 55;
LABEL_87:
        v47[(unsigned __int64)v30 >> 1] |= v32 << (4 - 4 * (v30 & 1));
        if ( (int)++v30 >= (int)v25 )
          goto LABEL_88;
      }
      if ( v31 != 56 && v31 != 48 && v31 != 49 && v31 != 50 && v31 != 51 && v31 != 52 && v31 != 53 && v31 - 54 > 1 )
        goto LABEL_85;
LABEL_73:
      v32 = v31 - 48;
      goto LABEL_87;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000dcf0  push    rbx
0x18000dcf2  push    rsi
0x18000dcf3  push    rdi
0x18000dcf4  push    r12
0x18000dcf6  push    r13
0x18000dcf8  push    r14
0x18000dcfa  push    r15
0x18000dcfc  mov     eax, 22C0h
0x18000dd01  call    _alloca_probe
0x18000dd06  sub     rsp, rax
0x18000dd09  mov     rax, cs:__security_cookie
0x18000dd10  xor     rax, rsp
0x18000dd13  mov     [rsp+22F8h+var_48], rax
0x18000dd1b  mov     r14, r8
0x18000dd1e  mov     [rsp+22F8h+lpValueName], r8
0x18000dd23  mov     r12, rdx
0x18000dd26  mov     [rsp+22F8h+var_2288], rdx
0x18000dd2b  mov     r15, rcx
0x18000dd2e  mov     [rsp+22F8h+var_22C0], rcx
0x18000dd33  mov     qword ptr [rsp+22F8h+Data], rdx
0x18000dd38  mov     [rsp+22F8h+var_22A8], rcx
0x18000dd3d  mov     [rsp+22F8h+var_2278], rdx
0x18000dd45  mov     [rsp+22F8h+var_2298], r8
0x18000dd4a  mov     [rsp+22F8h+var_2270], r9
0x18000dd52  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000dd5a  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000dd5f  xor     ebx, ebx
0x18000dd61  test    eax, eax
0x18000dd63  js      short loc_18000DD97
0x18000dd65  mov     edi, ebx
0x18000dd67  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000dd6e  movsxd  rsi, edi
0x18000dd71  add     rsi, rsi
0x18000dd74  mov     rdx, [r13+rsi*8+0]; lpString2
0x18000dd79  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000dd81  call    cs:__imp_lstrcmpiW
0x18000dd87  test    eax, eax
0x18000dd89  jz      short loc_18000DDBA
0x18000dd8b  inc     edi
0x18000dd8d  cmp     edi, 4
0x18000dd90  jb      short loc_18000DD6E
0x18000dd92  mov     eax, 80020009h
0x18000dd97  mov     rcx, [rsp+22F8h+var_48]
0x18000dd9f  xor     rcx, rsp; StackCookie
0x18000dda2  call    __security_check_cookie
0x18000dda7  add     rsp, 22C0h
0x18000ddae  pop     r15
0x18000ddb0  pop     r14
0x18000ddb2  pop     r13
0x18000ddb4  pop     r12
0x18000ddb6  pop     rdi
0x18000ddb7  pop     rsi
0x18000ddb8  pop     rbx
0x18000ddb9  retn
0x18000ddba  movzx   edi, word ptr [r13+rsi*8+8]
0x18000ddc0  mov     esi, 13h
0x18000ddc5  mov     rdx, [r15]
0x18000ddc8  movzx   ecx, word ptr [rdx]
0x18000ddcb  sub     ecx, 9
0x18000ddce  jz      loc_18000E291
0x18000ddd4  sub     ecx, 1
0x18000ddd7  jz      loc_18000E291
0x18000dddd  sub     ecx, 3
0x18000dde0  jz      loc_18000E291
0x18000dde6  cmp     ecx, esi
0x18000dde8  jz      loc_18000E291
0x18000ddee  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x18000ddf6  mov     rcx, r15; this
0x18000ddf9  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000ddfe  test    eax, eax
0x18000de00  js      short loc_18000DD97
0x18000de02  mov     r13d, 8
0x18000de08  cmp     di, r13w
0x18000de0c  jz      loc_18000E242
0x18000de12  cmp     di, 11h
0x18000de16  jz      loc_18000E01B
0x18000de1c  cmp     di, si
0x18000de1f  jz      loc_18000DFC3
0x18000de25  mov     eax, 4008h
0x18000de2a  cmp     di, ax
0x18000de2d  jnz     loc_18000E275
0x18000de33  lea     rcx, [rsp+22F8h+String1]
0x18000de3b  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000de3f  mov     rax, rsi
0x18000de42  inc     rax
0x18000de45  cmp     [rcx+rax*2], bx
0x18000de49  jnz     short loc_18000DE42
0x18000de4b  add     eax, 2
0x18000de4e  mov     [rsp+22F8h+var_2158], rbx
0x18000de56  test    eax, eax
0x18000de58  jz      short loc_18000DE93
0x18000de5a  movsxd  rcx, eax
0x18000de5d  xor     edx, edx
0x18000de5f  mov     rax, rsi
0x18000de62  div     rcx
0x18000de65  cmp     rax, 2
0x18000de69  jb      loc_18000E2A2
0x18000de6f  lea     rdx, [rcx+rcx]
0x18000de73  cmp     rdx, 100h
0x18000de7a  jbe     short loc_18000DE93
0x18000de7c  lea     rcx, [rsp+22F8h+var_2158]
0x18000de84  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000de89  mov     rdi, [rsp+22F8h+var_2158]
0x18000de91  jmp     short loc_18000DEA3
0x18000de93  lea     rdi, [rsp+22F8h+var_2150]
0x18000de9b  mov     [rsp+22F8h+var_2158], rdi
0x18000dea3  mov     r13, [rsp+22F8h+lpValueName]
0x18000dea8  jmp     short loc_18000DECC
0x18000deaa  xor     ebx, ebx
0x18000deac  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000deb0  mov     rdi, [rsp+22F8h+var_2158]
0x18000deb8  mov     r12, qword ptr [rsp+22F8h+Data]
0x18000debd  mov     rax, [rsp+22F8h+var_22A8]
0x18000dec2  mov     [rsp+22F8h+var_22C0], rax
0x18000dec7  mov     r13, [rsp+22F8h+var_2298]
0x18000decc  test    rdi, rdi
0x18000decf  jz      loc_18000DF8B
0x18000ded5  lea     r14, [rsp+22F8h+String1]
0x18000dedd  cmp     [rsp+22F8h+String1], bx
0x18000dee5  jz      short loc_18000DF28
0x18000dee7  mov     r15d, 30h ; '0'
0x18000deed  mov     rcx, r14; lpsz
0x18000def0  call    cs:__imp_CharNextW
0x18000def6  movzx   ecx, word ptr [r14]
0x18000defa  cmp     cx, 5Ch ; '\'
0x18000defe  jnz     short loc_18000DF17
0x18000df00  cmp     [rax], r15w
0x18000df04  jnz     short loc_18000DF17
0x18000df06  mov     [rdi], bx
0x18000df09  mov     rcx, rax; lpsz
0x18000df0c  call    cs:__imp_CharNextW
0x18000df12  mov     r14, rax
0x18000df15  jmp     short loc_18000DF1E
0x18000df17  mov     [rdi], cx
0x18000df1a  add     r14, 2
0x18000df1e  add     rdi, 2
0x18000df22  cmp     [r14], bx
0x18000df26  jnz     short loc_18000DEED
0x18000df28  mov     dword ptr [rdi], 0
0x18000df2e  mov     r8, [rsp+22F8h+var_2158]
0x18000df36  test    r8, r8
0x18000df39  jz      loc_18000E2AD
0x18000df3f  mov     r10d, ebx
0x18000df42  mov     r9, r8
0x18000df45  mov     rcx, rsi
0x18000df48  inc     rcx
0x18000df4b  cmp     [r9+rcx*2], bx
0x18000df50  jnz     short loc_18000DF48
0x18000df52  inc     ecx
0x18000df54  lea     r9, [r9+rcx*2]
0x18000df58  lea     r10d, [r10+rcx*2]
0x18000df5c  cmp     ecx, 1
0x18000df5f  jnz     short loc_18000DF45
0x18000df61  mov     [rsp+22F8h+cbData], r10d; cbData
0x18000df66  mov     [rsp+22F8h+lpData], r8; lpData
0x18000df6b  lea     r9d, [rcx+6]; dwType
0x18000df6f  xor     r8d, r8d; Reserved
0x18000df72  mov     rdx, r13; lpValueName
0x18000df75  mov     rcx, [r12]; hKey
0x18000df79  call    cs:__imp_RegSetValueExW
0x18000df7f  mov     esi, eax
0x18000df81  mov     rdi, [rsp+22F8h+var_2158]
0x18000df89  jmp     short loc_18000DF90
0x18000df8b  mov     esi, 0Eh
0x18000df90  lea     rax, [rsp+22F8h+var_2150]
0x18000df98  cmp     rdi, rax
0x18000df9b  jz      short loc_18000DFAA
0x18000df9d  lea     rcx, [rsp+22F8h+var_2158]
0x18000dfa5  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000dfaa  mov     r15, [rsp+22F8h+var_22C0]
0x18000dfaf  test    esi, esi
0x18000dfb1  jz      loc_18000E275
0x18000dfb7  mov     ecx, esi; this
0x18000dfb9  call    ?hresult_from_win32@impl@winrt@@YAHI@Z; winrt::impl::hresult_from_win32(uint)
0x18000dfbe  jmp     loc_18000DD97
0x18000dfc3  mov     [rsp+22F8h+pulOut], ebx
0x18000dfc7  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x18000dfcc  xor     r8d, r8d; dwFlags
0x18000dfcf  xor     edx, edx; lcid
0x18000dfd1  lea     rcx, [rsp+22F8h+String1]; strIn
0x18000dfd9  call    cs:__imp_VarUI4FromStr
0x18000dfdf  test    eax, eax
0x18000dfe1  js      loc_18000DD97
0x18000dfe7  mov     eax, [rsp+22F8h+pulOut]
0x18000dfeb  mov     dword ptr [rsp+22F8h+Data], eax
0x18000dfef  mov     [rsp+22F8h+cbData], 4; cbData
0x18000dff7  lea     rax, [rsp+22F8h+Data]
0x18000dffc  mov     r9d, 4; dwType
0x18000e002  mov     [rsp+22F8h+lpData], rax; lpData
0x18000e007  xor     r8d, r8d; Reserved
0x18000e00a  mov     rdx, r14; lpValueName
0x18000e00d  mov     rcx, [r12]; hKey
0x18000e011  call    cs:__imp_RegSetValueExW
0x18000e017  mov     esi, eax
0x18000e019  jmp     short loc_18000DFAF
0x18000e01b  lea     rax, [rsp+22F8h+String1]
0x18000e023  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000e027  mov     r14, rsi
0x18000e02a  inc     r14
0x18000e02d  cmp     [rax+r14*2], bx
0x18000e032  jnz     short loc_18000E02A
0x18000e034  mov     dword ptr [rsp+22F8h+Data], r14d
0x18000e039  test    r14b, 1
0x18000e03d  jnz     loc_18000E0F7
0x18000e043  mov     eax, r14d
0x18000e046  cdq
0x18000e047  sub     eax, edx
0x18000e049  sar     eax, 1
0x18000e04b  movsxd  r12, eax
0x18000e04e  mov     [rsp+22F8h+var_2268], rbx
0x18000e056  mov     rdi, r12
0x18000e059  mov     [rsp+22F8h+var_2280], r12
0x18000e05e  test    eax, eax
0x18000e060  jz      short loc_18000E097
0x18000e062  xor     edx, edx
0x18000e064  mov     rax, rsi
0x18000e067  div     rdi
0x18000e06a  cmp     rax, 1
0x18000e06e  jb      loc_18000E2B8
0x18000e074  cmp     rdi, 100h
0x18000e07b  jbe     short loc_18000E097
0x18000e07d  mov     rdx, rdi
0x18000e080  lea     rcx, [rsp+22F8h+var_2268]
0x18000e088  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000e08d  mov     rcx, [rsp+22F8h+var_2268]
0x18000e095  jmp     short loc_18000E0A7
0x18000e097  lea     rcx, [rsp+22F8h+var_2260]
0x18000e09f  mov     [rsp+22F8h+var_2268], rcx
0x18000e0a7  mov     rsi, [rsp+22F8h+var_2288]
0x18000e0ac  jmp     short loc_18000E0E5
0x18000e0ae  xor     ebx, ebx
0x18000e0b0  lea     r13d, [rbx+8]
0x18000e0b4  mov     r14d, dword ptr [rsp+22F8h+Data]
0x18000e0b9  mov     rcx, [rsp+22F8h+var_2268]; void *
0x18000e0c1  mov     rdi, [rsp+22F8h+var_2280]
0x18000e0c6  mov     rax, [rsp+22F8h+var_22A8]
0x18000e0cb  mov     [rsp+22F8h+var_22C0], rax
0x18000e0d0  mov     rsi, [rsp+22F8h+var_2278]
0x18000e0d8  mov     rax, [rsp+22F8h+var_2298]
0x18000e0dd  mov     [rsp+22F8h+lpValueName], rax
0x18000e0e2  mov     r12d, edi
0x18000e0e5  test    rcx, rcx
0x18000e0e8  jnz     short loc_18000E101
0x18000e0ea  lea     rcx, [rsp+22F8h+var_2268]
0x18000e0f2  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000e0f7  mov     eax, 80004005h
0x18000e0fc  jmp     loc_18000DD97
0x18000e101  mov     r8, rdi; Size
0x18000e104  xor     edx, edx; Val
0x18000e106  call    memset_0
0x18000e10b  mov     r10d, ebx
0x18000e10e  test    r14d, r14d
0x18000e111  jle     loc_18000E1EF
0x18000e117  mov     r15d, 30h ; '0'
0x18000e11d  mov     eax, r10d
0x18000e120  movzx   edx, [rsp+rax*2+22F8h+String1]
0x18000e128  cmp     edx, 61h ; 'a'
0x18000e12b  ja      short loc_18000E19A
0x18000e12d  jz      loc_18000E1BA
0x18000e133  cmp     edx, 38h ; '8'
0x18000e136  ja      short loc_18000E16C
0x18000e138  jz      short loc_18000E164
0x18000e13a  mov     ecx, edx
0x18000e13c  sub     ecx, r15d
0x18000e13f  jz      short loc_18000E164
0x18000e141  sub     ecx, 1
0x18000e144  jz      short loc_18000E164
0x18000e146  sub     ecx, 1
0x18000e149  jz      short loc_18000E164
0x18000e14b  sub     ecx, 1
0x18000e14e  jz      short loc_18000E164
0x18000e150  sub     ecx, 1
0x18000e153  jz      short loc_18000E164
0x18000e155  sub     ecx, 1
0x18000e158  jz      short loc_18000E164
0x18000e15a  sub     ecx, 1
0x18000e15d  jz      short loc_18000E164
0x18000e15f  cmp     ecx, 1
0x18000e162  jnz     short loc_18000E1B5
0x18000e164  mov     r9d, edx
0x18000e167  sub     r9d, r15d
0x18000e16a  jmp     short loc_18000E1BE
0x18000e16c  mov     r9d, edx
0x18000e16f  mov     ecx, edx
0x18000e171  sub     ecx, 39h ; '9'
0x18000e174  jz      short loc_18000E164
0x18000e176  sub     ecx, r13d
0x18000e179  jz      short loc_18000E194
0x18000e17b  sub     ecx, 1
0x18000e17e  jz      short loc_18000E194
0x18000e180  sub     ecx, 1
0x18000e183  jz      short loc_18000E194
0x18000e185  sub     ecx, 1
0x18000e188  jz      short loc_18000E194
0x18000e18a  sub     ecx, 1
0x18000e18d  jz      short loc_18000E194
0x18000e18f  cmp     ecx, 1
0x18000e192  jnz     short loc_18000E1B5
0x18000e194  add     r9d, 0FFFFFFC9h
0x18000e198  jmp     short loc_18000E1BE
  ... truncated ...
```
