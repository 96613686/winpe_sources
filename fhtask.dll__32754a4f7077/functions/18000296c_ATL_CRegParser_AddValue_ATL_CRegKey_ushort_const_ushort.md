# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x18000296c`
- end: `0x180002f40`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000460c`

## callees

- `0x18000296c`
- `0x180002f48`
- `0x18000309c`
- `0x1800030b4`
- `0x1800039a4`
- `0x180003b30`
- `0x1800099ce`
- `0x180009a00`
- `0x180009ac0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180002bf5`
- `ADVAPI32!RegSetValueExW` at `0x180002c8d`
- `ADVAPI32!RegSetValueExW` at `0x180002e8e`
- `ADVAPI32!RegSetValueExW` at `0x180002bf5`
- `ADVAPI32!RegSetValueExW` at `0x180002c8d`
- `ADVAPI32!RegSetValueExW` at `0x180002e8e`
- `KERNEL32!lstrcmpiW` at `0x1800029fd`
- `KERNEL32!lstrcmpiW` at `0x1800029fd`
- `USER32!CharNextW` at `0x180002b6c`
- `USER32!CharNextW` at `0x180002b88`
- `USER32!CharNextW` at `0x180002f10`
- `USER32!CharNextW` at `0x180002b6c`
- `USER32!CharNextW` at `0x180002b88`
- `USER32!CharNextW` at `0x180002f10`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002c55`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002c55`

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
0x18000296c  push    rbx
0x18000296e  push    rsi
0x18000296f  push    rdi
0x180002970  push    r12
0x180002972  push    r13
0x180002974  push    r14
0x180002976  push    r15
0x180002978  mov     eax, 22C0h
0x18000297d  call    _alloca_probe
0x180002982  sub     rsp, rax
0x180002985  mov     rax, cs:__security_cookie
0x18000298c  xor     rax, rsp
0x18000298f  mov     [rsp+22F8h+var_48], rax
0x180002997  mov     r14, r8
0x18000299a  mov     [rsp+22F8h+lpValueName], r8
0x18000299f  mov     r12, rdx
0x1800029a2  mov     [rsp+22F8h+var_2288], rdx
0x1800029a7  mov     r15, rcx
0x1800029aa  mov     [rsp+22F8h+var_22C0], rcx
0x1800029af  mov     qword ptr [rsp+22F8h+Data], rdx
0x1800029b4  mov     [rsp+22F8h+var_22A8], rcx
0x1800029b9  mov     [rsp+22F8h+var_2278], rdx
0x1800029c1  mov     [rsp+22F8h+var_2298], r8
0x1800029c6  mov     [rsp+22F8h+var_2270], r9
0x1800029ce  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x1800029d6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800029db  xor     ebx, ebx
0x1800029dd  test    eax, eax
0x1800029df  js      short loc_180002A13
0x1800029e1  mov     edi, ebx
0x1800029e3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x1800029ea  movsxd  rsi, edi
0x1800029ed  add     rsi, rsi
0x1800029f0  mov     rdx, [r13+rsi*8+0]; lpString2
0x1800029f5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x1800029fd  call    cs:__imp_lstrcmpiW
0x180002a03  test    eax, eax
0x180002a05  jz      short loc_180002A36
0x180002a07  inc     edi
0x180002a09  cmp     edi, 4
0x180002a0c  jb      short loc_1800029EA
0x180002a0e  mov     eax, 80020009h
0x180002a13  mov     rcx, [rsp+22F8h+var_48]
0x180002a1b  xor     rcx, rsp; StackCookie
0x180002a1e  call    __security_check_cookie
0x180002a23  add     rsp, 22C0h
0x180002a2a  pop     r15
0x180002a2c  pop     r14
0x180002a2e  pop     r13
0x180002a30  pop     r12
0x180002a32  pop     rdi
0x180002a33  pop     rsi
0x180002a34  pop     rbx
0x180002a35  retn
0x180002a36  movzx   edi, word ptr [r13+rsi*8+8]
0x180002a3c  mov     esi, 13h
0x180002a41  mov     rdx, [r15]
0x180002a44  movzx   ecx, word ptr [rdx]
0x180002a47  sub     ecx, 9
0x180002a4a  jz      loc_180002F0D
0x180002a50  sub     ecx, 1
0x180002a53  jz      loc_180002F0D
0x180002a59  sub     ecx, 3
0x180002a5c  jz      loc_180002F0D
0x180002a62  cmp     ecx, esi
0x180002a64  jz      loc_180002F0D
0x180002a6a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180002a72  mov     rcx, r15; this
0x180002a75  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002a7a  test    eax, eax
0x180002a7c  js      short loc_180002A13
0x180002a7e  mov     r13d, 8
0x180002a84  cmp     di, r13w
0x180002a88  jz      loc_180002EBE
0x180002a8e  cmp     di, 11h
0x180002a92  jz      loc_180002C97
0x180002a98  cmp     di, si
0x180002a9b  jz      loc_180002C3F
0x180002aa1  mov     eax, 4008h
0x180002aa6  cmp     di, ax
0x180002aa9  jnz     loc_180002EF1
0x180002aaf  lea     rcx, [rsp+22F8h+String1]
0x180002ab7  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002abb  mov     rax, rsi
0x180002abe  inc     rax
0x180002ac1  cmp     [rcx+rax*2], bx
0x180002ac5  jnz     short loc_180002ABE
0x180002ac7  add     eax, 2
0x180002aca  mov     [rsp+22F8h+var_2158], rbx
0x180002ad2  test    eax, eax
0x180002ad4  jz      short loc_180002B0F
0x180002ad6  movsxd  rcx, eax
0x180002ad9  xor     edx, edx
0x180002adb  mov     rax, rsi
0x180002ade  div     rcx
0x180002ae1  cmp     rax, 2
0x180002ae5  jb      loc_180002F1E
0x180002aeb  lea     rdx, [rcx+rcx]
0x180002aef  cmp     rdx, 100h
0x180002af6  jbe     short loc_180002B0F
0x180002af8  lea     rcx, [rsp+22F8h+var_2158]
0x180002b00  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002b05  mov     rdi, [rsp+22F8h+var_2158]
0x180002b0d  jmp     short loc_180002B1F
0x180002b0f  lea     rdi, [rsp+22F8h+var_2150]
0x180002b17  mov     [rsp+22F8h+var_2158], rdi
0x180002b1f  mov     r13, [rsp+22F8h+lpValueName]
0x180002b24  jmp     short loc_180002B48
0x180002b26  xor     ebx, ebx
0x180002b28  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002b2c  mov     rdi, [rsp+22F8h+var_2158]
0x180002b34  mov     r12, qword ptr [rsp+22F8h+Data]
0x180002b39  mov     rax, [rsp+22F8h+var_22A8]
0x180002b3e  mov     [rsp+22F8h+var_22C0], rax
0x180002b43  mov     r13, [rsp+22F8h+var_2298]
0x180002b48  test    rdi, rdi
0x180002b4b  jz      loc_180002C07
0x180002b51  lea     r14, [rsp+22F8h+String1]
0x180002b59  cmp     [rsp+22F8h+String1], bx
0x180002b61  jz      short loc_180002BA4
0x180002b63  mov     r15d, 30h ; '0'
0x180002b69  mov     rcx, r14; lpsz
0x180002b6c  call    cs:__imp_CharNextW
0x180002b72  movzx   ecx, word ptr [r14]
0x180002b76  cmp     cx, 5Ch ; '\'
0x180002b7a  jnz     short loc_180002B93
0x180002b7c  cmp     [rax], r15w
0x180002b80  jnz     short loc_180002B93
0x180002b82  mov     [rdi], bx
0x180002b85  mov     rcx, rax; lpsz
0x180002b88  call    cs:__imp_CharNextW
0x180002b8e  mov     r14, rax
0x180002b91  jmp     short loc_180002B9A
0x180002b93  mov     [rdi], cx
0x180002b96  add     r14, 2
0x180002b9a  add     rdi, 2
0x180002b9e  cmp     [r14], bx
0x180002ba2  jnz     short loc_180002B69
0x180002ba4  mov     dword ptr [rdi], 0
0x180002baa  mov     r8, [rsp+22F8h+var_2158]
0x180002bb2  test    r8, r8
0x180002bb5  jz      loc_180002F29
0x180002bbb  mov     r10d, ebx
0x180002bbe  mov     r9, r8
0x180002bc1  mov     rcx, rsi
0x180002bc4  inc     rcx
0x180002bc7  cmp     [r9+rcx*2], bx
0x180002bcc  jnz     short loc_180002BC4
0x180002bce  inc     ecx
0x180002bd0  lea     r9, [r9+rcx*2]
0x180002bd4  lea     r10d, [r10+rcx*2]
0x180002bd8  cmp     ecx, 1
0x180002bdb  jnz     short loc_180002BC1
0x180002bdd  mov     [rsp+22F8h+cbData], r10d; cbData
0x180002be2  mov     [rsp+22F8h+lpData], r8; lpData
0x180002be7  lea     r9d, [rcx+6]; dwType
0x180002beb  xor     r8d, r8d; Reserved
0x180002bee  mov     rdx, r13; lpValueName
0x180002bf1  mov     rcx, [r12]; hKey
0x180002bf5  call    cs:__imp_RegSetValueExW
0x180002bfb  mov     esi, eax
0x180002bfd  mov     rdi, [rsp+22F8h+var_2158]
0x180002c05  jmp     short loc_180002C0C
0x180002c07  mov     esi, 0Eh
0x180002c0c  lea     rax, [rsp+22F8h+var_2150]
0x180002c14  cmp     rdi, rax
0x180002c17  jz      short loc_180002C26
0x180002c19  lea     rcx, [rsp+22F8h+var_2158]
0x180002c21  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002c26  mov     r15, [rsp+22F8h+var_22C0]
0x180002c2b  test    esi, esi
0x180002c2d  jz      loc_180002EF1
0x180002c33  mov     ecx, esi; unsigned int
0x180002c35  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180002c3a  jmp     loc_180002A13
0x180002c3f  mov     [rsp+22F8h+pulOut], ebx
0x180002c43  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180002c48  xor     r8d, r8d; dwFlags
0x180002c4b  xor     edx, edx; lcid
0x180002c4d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180002c55  call    cs:__imp_VarUI4FromStr
0x180002c5b  test    eax, eax
0x180002c5d  js      loc_180002A13
0x180002c63  mov     eax, [rsp+22F8h+pulOut]
0x180002c67  mov     dword ptr [rsp+22F8h+Data], eax
0x180002c6b  mov     [rsp+22F8h+cbData], 4; cbData
0x180002c73  lea     rax, [rsp+22F8h+Data]
0x180002c78  mov     r9d, 4; dwType
0x180002c7e  mov     [rsp+22F8h+lpData], rax; lpData
0x180002c83  xor     r8d, r8d; Reserved
0x180002c86  mov     rdx, r14; lpValueName
0x180002c89  mov     rcx, [r12]; hKey
0x180002c8d  call    cs:__imp_RegSetValueExW
0x180002c93  mov     esi, eax
0x180002c95  jmp     short loc_180002C2B
0x180002c97  lea     rax, [rsp+22F8h+String1]
0x180002c9f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002ca3  mov     r14, rsi
0x180002ca6  inc     r14
0x180002ca9  cmp     [rax+r14*2], bx
0x180002cae  jnz     short loc_180002CA6
0x180002cb0  mov     dword ptr [rsp+22F8h+Data], r14d
0x180002cb5  test    r14b, 1
0x180002cb9  jnz     loc_180002D73
0x180002cbf  mov     eax, r14d
0x180002cc2  cdq
0x180002cc3  sub     eax, edx
0x180002cc5  sar     eax, 1
0x180002cc7  movsxd  r12, eax
0x180002cca  mov     [rsp+22F8h+var_2268], rbx
0x180002cd2  mov     rdi, r12
0x180002cd5  mov     [rsp+22F8h+var_2280], r12
0x180002cda  test    eax, eax
0x180002cdc  jz      short loc_180002D13
0x180002cde  xor     edx, edx
0x180002ce0  mov     rax, rsi
0x180002ce3  div     rdi
0x180002ce6  cmp     rax, 1
0x180002cea  jb      loc_180002F34
0x180002cf0  cmp     rdi, 100h
0x180002cf7  jbe     short loc_180002D13
0x180002cf9  mov     rdx, rdi
0x180002cfc  lea     rcx, [rsp+22F8h+var_2268]
0x180002d04  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002d09  mov     rcx, [rsp+22F8h+var_2268]
0x180002d11  jmp     short loc_180002D23
0x180002d13  lea     rcx, [rsp+22F8h+var_2260]
0x180002d1b  mov     [rsp+22F8h+var_2268], rcx
0x180002d23  mov     rsi, [rsp+22F8h+var_2288]
0x180002d28  jmp     short loc_180002D61
0x180002d2a  xor     ebx, ebx
0x180002d2c  lea     r13d, [rbx+8]
0x180002d30  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180002d35  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180002d3d  mov     rdi, [rsp+22F8h+var_2280]
0x180002d42  mov     rax, [rsp+22F8h+var_22A8]
0x180002d47  mov     [rsp+22F8h+var_22C0], rax
0x180002d4c  mov     rsi, [rsp+22F8h+var_2278]
0x180002d54  mov     rax, [rsp+22F8h+var_2298]
0x180002d59  mov     [rsp+22F8h+lpValueName], rax
0x180002d5e  mov     r12d, edi
0x180002d61  test    rcx, rcx
0x180002d64  jnz     short loc_180002D7D
0x180002d66  lea     rcx, [rsp+22F8h+var_2268]
0x180002d6e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002d73  mov     eax, 80004005h
0x180002d78  jmp     loc_180002A13
0x180002d7d  mov     r8, rdi; Size
0x180002d80  xor     edx, edx; Val
0x180002d82  call    memset_0
0x180002d87  mov     r10d, ebx
0x180002d8a  test    r14d, r14d
0x180002d8d  jle     loc_180002E6B
0x180002d93  mov     r15d, 30h ; '0'
0x180002d99  mov     eax, r10d
0x180002d9c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180002da4  cmp     edx, 61h ; 'a'
0x180002da7  ja      short loc_180002E16
0x180002da9  jz      loc_180002E36
0x180002daf  cmp     edx, 38h ; '8'
0x180002db2  ja      short loc_180002DE8
0x180002db4  jz      short loc_180002DE0
0x180002db6  mov     ecx, edx
0x180002db8  sub     ecx, r15d
0x180002dbb  jz      short loc_180002DE0
0x180002dbd  sub     ecx, 1
0x180002dc0  jz      short loc_180002DE0
0x180002dc2  sub     ecx, 1
0x180002dc5  jz      short loc_180002DE0
0x180002dc7  sub     ecx, 1
0x180002dca  jz      short loc_180002DE0
0x180002dcc  sub     ecx, 1
0x180002dcf  jz      short loc_180002DE0
0x180002dd1  sub     ecx, 1
0x180002dd4  jz      short loc_180002DE0
0x180002dd6  sub     ecx, 1
0x180002dd9  jz      short loc_180002DE0
0x180002ddb  cmp     ecx, 1
0x180002dde  jnz     short loc_180002E31
0x180002de0  mov     r9d, edx
0x180002de3  sub     r9d, r15d
0x180002de6  jmp     short loc_180002E3A
0x180002de8  mov     r9d, edx
0x180002deb  mov     ecx, edx
0x180002ded  sub     ecx, 39h ; '9'
0x180002df0  jz      short loc_180002DE0
0x180002df2  sub     ecx, r13d
0x180002df5  jz      short loc_180002E10
0x180002df7  sub     ecx, 1
0x180002dfa  jz      short loc_180002E10
0x180002dfc  sub     ecx, 1
0x180002dff  jz      short loc_180002E10
0x180002e01  sub     ecx, 1
0x180002e04  jz      short loc_180002E10
0x180002e06  sub     ecx, 1
0x180002e09  jz      short loc_180002E10
0x180002e0b  cmp     ecx, 1
0x180002e0e  jnz     short loc_180002E31
0x180002e10  add     r9d, 0FFFFFFC9h
0x180002e14  jmp     short loc_180002E3A
  ... truncated ...
```
