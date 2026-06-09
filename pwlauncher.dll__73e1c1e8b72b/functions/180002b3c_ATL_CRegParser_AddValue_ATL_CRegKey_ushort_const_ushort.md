# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x180002b3c`
- end: `0x180003110`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `HRESULT __fastcall(LPCWSTR *this, HKEY *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000448c`

## callees

- `0x180002b3c`
- `0x180003118`
- `0x18000326c`
- `0x18000374c`
- `0x180003a3c`
- `0x180003b24`
- `0x18000fdd6`
- `0x18000fe10`
- `0x18000fed0`

## import_xrefs

- `USER32!CharNextW` at `0x180002d3c`
- `USER32!CharNextW` at `0x180002d58`
- `USER32!CharNextW` at `0x1800030e0`
- `USER32!CharNextW` at `0x180002d3c`
- `USER32!CharNextW` at `0x180002d58`
- `USER32!CharNextW` at `0x1800030e0`
- `ADVAPI32!RegSetValueExW` at `0x180002dc5`
- `ADVAPI32!RegSetValueExW` at `0x180002e5d`
- `ADVAPI32!RegSetValueExW` at `0x18000305e`
- `ADVAPI32!RegSetValueExW` at `0x180002dc5`
- `ADVAPI32!RegSetValueExW` at `0x180002e5d`
- `ADVAPI32!RegSetValueExW` at `0x18000305e`
- `KERNEL32!lstrcmpiW` at `0x180002bcd`
- `KERNEL32!lstrcmpiW` at `0x180002bcd`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002e25`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002e25`

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
0x180002b3c  push    rbx
0x180002b3e  push    rsi
0x180002b3f  push    rdi
0x180002b40  push    r12
0x180002b42  push    r13
0x180002b44  push    r14
0x180002b46  push    r15
0x180002b48  mov     eax, 22C0h
0x180002b4d  call    _alloca_probe
0x180002b52  sub     rsp, rax
0x180002b55  mov     rax, cs:__security_cookie
0x180002b5c  xor     rax, rsp
0x180002b5f  mov     [rsp+22F8h+var_48], rax
0x180002b67  mov     r14, r8
0x180002b6a  mov     [rsp+22F8h+lpValueName], r8
0x180002b6f  mov     r12, rdx
0x180002b72  mov     [rsp+22F8h+var_2288], rdx
0x180002b77  mov     r15, rcx
0x180002b7a  mov     [rsp+22F8h+var_22C0], rcx
0x180002b7f  mov     qword ptr [rsp+22F8h+Data], rdx
0x180002b84  mov     [rsp+22F8h+var_22A8], rcx
0x180002b89  mov     [rsp+22F8h+var_2278], rdx
0x180002b91  mov     [rsp+22F8h+var_2298], r8
0x180002b96  mov     [rsp+22F8h+var_2270], r9
0x180002b9e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180002ba6  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002bab  xor     ebx, ebx
0x180002bad  test    eax, eax
0x180002baf  js      short loc_180002BE3
0x180002bb1  mov     edi, ebx
0x180002bb3  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x180002bba  movsxd  rsi, edi
0x180002bbd  add     rsi, rsi
0x180002bc0  mov     rdx, [r13+rsi*8+0]; lpString2
0x180002bc5  lea     rcx, [rsp+22F8h+String1]; lpString1
0x180002bcd  call    cs:__imp_lstrcmpiW
0x180002bd3  test    eax, eax
0x180002bd5  jz      short loc_180002C06
0x180002bd7  inc     edi
0x180002bd9  cmp     edi, 4
0x180002bdc  jb      short loc_180002BBA
0x180002bde  mov     eax, 80020009h
0x180002be3  mov     rcx, [rsp+22F8h+var_48]
0x180002beb  xor     rcx, rsp; StackCookie
0x180002bee  call    __security_check_cookie
0x180002bf3  add     rsp, 22C0h
0x180002bfa  pop     r15
0x180002bfc  pop     r14
0x180002bfe  pop     r13
0x180002c00  pop     r12
0x180002c02  pop     rdi
0x180002c03  pop     rsi
0x180002c04  pop     rbx
0x180002c05  retn
0x180002c06  movzx   edi, word ptr [r13+rsi*8+8]
0x180002c0c  mov     esi, 13h
0x180002c11  mov     rdx, [r15]
0x180002c14  movzx   ecx, word ptr [rdx]
0x180002c17  sub     ecx, 9
0x180002c1a  jz      loc_1800030DD
0x180002c20  sub     ecx, 1
0x180002c23  jz      loc_1800030DD
0x180002c29  sub     ecx, 3
0x180002c2c  jz      loc_1800030DD
0x180002c32  cmp     ecx, esi
0x180002c34  jz      loc_1800030DD
0x180002c3a  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180002c42  mov     rcx, r15; this
0x180002c45  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002c4a  test    eax, eax
0x180002c4c  js      short loc_180002BE3
0x180002c4e  mov     r13d, 8
0x180002c54  cmp     di, r13w
0x180002c58  jz      loc_18000308E
0x180002c5e  cmp     di, 11h
0x180002c62  jz      loc_180002E67
0x180002c68  cmp     di, si
0x180002c6b  jz      loc_180002E0F
0x180002c71  mov     eax, 4008h
0x180002c76  cmp     di, ax
0x180002c79  jnz     loc_1800030C1
0x180002c7f  lea     rcx, [rsp+22F8h+String1]
0x180002c87  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002c8b  mov     rax, rsi
0x180002c8e  inc     rax
0x180002c91  cmp     [rcx+rax*2], bx
0x180002c95  jnz     short loc_180002C8E
0x180002c97  add     eax, 2
0x180002c9a  mov     [rsp+22F8h+var_2158], rbx
0x180002ca2  test    eax, eax
0x180002ca4  jz      short loc_180002CDF
0x180002ca6  movsxd  rcx, eax
0x180002ca9  xor     edx, edx
0x180002cab  mov     rax, rsi
0x180002cae  div     rcx
0x180002cb1  cmp     rax, 2
0x180002cb5  jb      loc_1800030EE
0x180002cbb  lea     rdx, [rcx+rcx]
0x180002cbf  cmp     rdx, 100h
0x180002cc6  jbe     short loc_180002CDF
0x180002cc8  lea     rcx, [rsp+22F8h+var_2158]
0x180002cd0  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002cd5  mov     rdi, [rsp+22F8h+var_2158]
0x180002cdd  jmp     short loc_180002CEF
0x180002cdf  lea     rdi, [rsp+22F8h+var_2150]
0x180002ce7  mov     [rsp+22F8h+var_2158], rdi
0x180002cef  mov     r13, [rsp+22F8h+lpValueName]
0x180002cf4  jmp     short loc_180002D18
0x180002cf6  xor     ebx, ebx
0x180002cf8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002cfc  mov     rdi, [rsp+22F8h+var_2158]
0x180002d04  mov     r12, qword ptr [rsp+22F8h+Data]
0x180002d09  mov     rax, [rsp+22F8h+var_22A8]
0x180002d0e  mov     [rsp+22F8h+var_22C0], rax
0x180002d13  mov     r13, [rsp+22F8h+var_2298]
0x180002d18  test    rdi, rdi
0x180002d1b  jz      loc_180002DD7
0x180002d21  lea     r14, [rsp+22F8h+String1]
0x180002d29  cmp     [rsp+22F8h+String1], bx
0x180002d31  jz      short loc_180002D74
0x180002d33  mov     r15d, 30h ; '0'
0x180002d39  mov     rcx, r14; lpsz
0x180002d3c  call    cs:__imp_CharNextW
0x180002d42  movzx   ecx, word ptr [r14]
0x180002d46  cmp     cx, 5Ch ; '\'
0x180002d4a  jnz     short loc_180002D63
0x180002d4c  cmp     [rax], r15w
0x180002d50  jnz     short loc_180002D63
0x180002d52  mov     [rdi], bx
0x180002d55  mov     rcx, rax; lpsz
0x180002d58  call    cs:__imp_CharNextW
0x180002d5e  mov     r14, rax
0x180002d61  jmp     short loc_180002D6A
0x180002d63  mov     [rdi], cx
0x180002d66  add     r14, 2
0x180002d6a  add     rdi, 2
0x180002d6e  cmp     [r14], bx
0x180002d72  jnz     short loc_180002D39
0x180002d74  mov     dword ptr [rdi], 0
0x180002d7a  mov     r8, [rsp+22F8h+var_2158]
0x180002d82  test    r8, r8
0x180002d85  jz      loc_1800030F9
0x180002d8b  mov     r10d, ebx
0x180002d8e  mov     r9, r8
0x180002d91  mov     rcx, rsi
0x180002d94  inc     rcx
0x180002d97  cmp     [r9+rcx*2], bx
0x180002d9c  jnz     short loc_180002D94
0x180002d9e  inc     ecx
0x180002da0  lea     r9, [r9+rcx*2]
0x180002da4  lea     r10d, [r10+rcx*2]
0x180002da8  cmp     ecx, 1
0x180002dab  jnz     short loc_180002D91
0x180002dad  mov     [rsp+22F8h+cbData], r10d; cbData
0x180002db2  mov     [rsp+22F8h+lpData], r8; lpData
0x180002db7  lea     r9d, [rcx+6]; dwType
0x180002dbb  xor     r8d, r8d; Reserved
0x180002dbe  mov     rdx, r13; lpValueName
0x180002dc1  mov     rcx, [r12]; hKey
0x180002dc5  call    cs:__imp_RegSetValueExW
0x180002dcb  mov     esi, eax
0x180002dcd  mov     rdi, [rsp+22F8h+var_2158]
0x180002dd5  jmp     short loc_180002DDC
0x180002dd7  mov     esi, 0Eh
0x180002ddc  lea     rax, [rsp+22F8h+var_2150]
0x180002de4  cmp     rdi, rax
0x180002de7  jz      short loc_180002DF6
0x180002de9  lea     rcx, [rsp+22F8h+var_2158]
0x180002df1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002df6  mov     r15, [rsp+22F8h+var_22C0]
0x180002dfb  test    esi, esi
0x180002dfd  jz      loc_1800030C1
0x180002e03  mov     ecx, esi; unsigned int
0x180002e05  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180002e0a  jmp     loc_180002BE3
0x180002e0f  mov     [rsp+22F8h+pulOut], ebx
0x180002e13  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180002e18  xor     r8d, r8d; dwFlags
0x180002e1b  xor     edx, edx; lcid
0x180002e1d  lea     rcx, [rsp+22F8h+String1]; strIn
0x180002e25  call    cs:__imp_VarUI4FromStr
0x180002e2b  test    eax, eax
0x180002e2d  js      loc_180002BE3
0x180002e33  mov     eax, [rsp+22F8h+pulOut]
0x180002e37  mov     dword ptr [rsp+22F8h+Data], eax
0x180002e3b  mov     [rsp+22F8h+cbData], 4; cbData
0x180002e43  lea     rax, [rsp+22F8h+Data]
0x180002e48  mov     r9d, 4; dwType
0x180002e4e  mov     [rsp+22F8h+lpData], rax; lpData
0x180002e53  xor     r8d, r8d; Reserved
0x180002e56  mov     rdx, r14; lpValueName
0x180002e59  mov     rcx, [r12]; hKey
0x180002e5d  call    cs:__imp_RegSetValueExW
0x180002e63  mov     esi, eax
0x180002e65  jmp     short loc_180002DFB
0x180002e67  lea     rax, [rsp+22F8h+String1]
0x180002e6f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002e73  mov     r14, rsi
0x180002e76  inc     r14
0x180002e79  cmp     [rax+r14*2], bx
0x180002e7e  jnz     short loc_180002E76
0x180002e80  mov     dword ptr [rsp+22F8h+Data], r14d
0x180002e85  test    r14b, 1
0x180002e89  jnz     loc_180002F43
0x180002e8f  mov     eax, r14d
0x180002e92  cdq
0x180002e93  sub     eax, edx
0x180002e95  sar     eax, 1
0x180002e97  movsxd  r12, eax
0x180002e9a  mov     [rsp+22F8h+var_2268], rbx
0x180002ea2  mov     rdi, r12
0x180002ea5  mov     [rsp+22F8h+var_2280], r12
0x180002eaa  test    eax, eax
0x180002eac  jz      short loc_180002EE3
0x180002eae  xor     edx, edx
0x180002eb0  mov     rax, rsi
0x180002eb3  div     rdi
0x180002eb6  cmp     rax, 1
0x180002eba  jb      loc_180003104
0x180002ec0  cmp     rdi, 100h
0x180002ec7  jbe     short loc_180002EE3
0x180002ec9  mov     rdx, rdi
0x180002ecc  lea     rcx, [rsp+22F8h+var_2268]
0x180002ed4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002ed9  mov     rcx, [rsp+22F8h+var_2268]
0x180002ee1  jmp     short loc_180002EF3
0x180002ee3  lea     rcx, [rsp+22F8h+var_2260]
0x180002eeb  mov     [rsp+22F8h+var_2268], rcx
0x180002ef3  mov     rsi, [rsp+22F8h+var_2288]
0x180002ef8  jmp     short loc_180002F31
0x180002efa  xor     ebx, ebx
0x180002efc  lea     r13d, [rbx+8]
0x180002f00  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180002f05  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180002f0d  mov     rdi, [rsp+22F8h+var_2280]
0x180002f12  mov     rax, [rsp+22F8h+var_22A8]
0x180002f17  mov     [rsp+22F8h+var_22C0], rax
0x180002f1c  mov     rsi, [rsp+22F8h+var_2278]
0x180002f24  mov     rax, [rsp+22F8h+var_2298]
0x180002f29  mov     [rsp+22F8h+lpValueName], rax
0x180002f2e  mov     r12d, edi
0x180002f31  test    rcx, rcx
0x180002f34  jnz     short loc_180002F4D
0x180002f36  lea     rcx, [rsp+22F8h+var_2268]
0x180002f3e  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002f43  mov     eax, 80004005h
0x180002f48  jmp     loc_180002BE3
0x180002f4d  mov     r8, rdi; Size
0x180002f50  xor     edx, edx; Val
0x180002f52  call    memset_0
0x180002f57  mov     r10d, ebx
0x180002f5a  test    r14d, r14d
0x180002f5d  jle     loc_18000303B
0x180002f63  mov     r15d, 30h ; '0'
0x180002f69  mov     eax, r10d
0x180002f6c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180002f74  cmp     edx, 61h ; 'a'
0x180002f77  ja      short loc_180002FE6
0x180002f79  jz      loc_180003006
0x180002f7f  cmp     edx, 38h ; '8'
0x180002f82  ja      short loc_180002FB8
0x180002f84  jz      short loc_180002FB0
0x180002f86  mov     ecx, edx
0x180002f88  sub     ecx, r15d
0x180002f8b  jz      short loc_180002FB0
0x180002f8d  sub     ecx, 1
0x180002f90  jz      short loc_180002FB0
0x180002f92  sub     ecx, 1
0x180002f95  jz      short loc_180002FB0
0x180002f97  sub     ecx, 1
0x180002f9a  jz      short loc_180002FB0
0x180002f9c  sub     ecx, 1
0x180002f9f  jz      short loc_180002FB0
0x180002fa1  sub     ecx, 1
0x180002fa4  jz      short loc_180002FB0
0x180002fa6  sub     ecx, 1
0x180002fa9  jz      short loc_180002FB0
0x180002fab  cmp     ecx, 1
0x180002fae  jnz     short loc_180003001
0x180002fb0  mov     r9d, edx
0x180002fb3  sub     r9d, r15d
0x180002fb6  jmp     short loc_18000300A
0x180002fb8  mov     r9d, edx
0x180002fbb  mov     ecx, edx
0x180002fbd  sub     ecx, 39h ; '9'
0x180002fc0  jz      short loc_180002FB0
0x180002fc2  sub     ecx, r13d
0x180002fc5  jz      short loc_180002FE0
0x180002fc7  sub     ecx, 1
0x180002fca  jz      short loc_180002FE0
0x180002fcc  sub     ecx, 1
0x180002fcf  jz      short loc_180002FE0
0x180002fd1  sub     ecx, 1
0x180002fd4  jz      short loc_180002FE0
0x180002fd6  sub     ecx, 1
0x180002fd9  jz      short loc_180002FE0
0x180002fdb  cmp     ecx, 1
0x180002fde  jnz     short loc_180003001
0x180002fe0  add     r9d, 0FFFFFFC9h
0x180002fe4  jmp     short loc_18000300A
  ... truncated ...
```
