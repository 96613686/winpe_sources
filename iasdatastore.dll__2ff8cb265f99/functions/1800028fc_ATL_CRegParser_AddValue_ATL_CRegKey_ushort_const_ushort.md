# ATL::CRegParser::AddValue(ATL::CRegKey &,ushort const *,ushort *)

- ea: `0x1800028fc`
- end: `0x180002ed0`
- name: `?AddValue@CRegParser@ATL@@IEAAJAEAVCRegKey@2@PEBGPEAG@Z`
- size: `1492`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, struct ATL::CRegKey *, const unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x180004efc`

## callees

- `0x1800028fc`
- `0x180002ed8`
- `0x180003138`
- `0x1800039a4`
- `0x180004184`
- `0x1800044c0`
- `0x18000dce6`
- `0x18000dd10`
- `0x18000ddd0`

## import_xrefs

- `ADVAPI32!RegSetValueExW` at `0x180002b85`
- `ADVAPI32!RegSetValueExW` at `0x180002c1d`
- `ADVAPI32!RegSetValueExW` at `0x180002e1e`
- `ADVAPI32!RegSetValueExW` at `0x180002b85`
- `ADVAPI32!RegSetValueExW` at `0x180002c1d`
- `ADVAPI32!RegSetValueExW` at `0x180002e1e`
- `KERNEL32!lstrcmpiW` at `0x18000298d`
- `KERNEL32!lstrcmpiW` at `0x18000298d`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002be5`
- `OLEAUT32!__imp_VarUI4FromStr` at `0x180002be5`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002afc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002b18`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002ea0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002afc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002b18`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180002ea0`

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
0x1800028fc  push    rbx
0x1800028fe  push    rsi
0x1800028ff  push    rdi
0x180002900  push    r12
0x180002902  push    r13
0x180002904  push    r14
0x180002906  push    r15
0x180002908  mov     eax, 22C0h
0x18000290d  call    _alloca_probe
0x180002912  sub     rsp, rax
0x180002915  mov     rax, cs:__security_cookie
0x18000291c  xor     rax, rsp
0x18000291f  mov     [rsp+22F8h+var_48], rax
0x180002927  mov     r14, r8
0x18000292a  mov     [rsp+22F8h+lpValueName], r8
0x18000292f  mov     r12, rdx
0x180002932  mov     [rsp+22F8h+var_2288], rdx
0x180002937  mov     r15, rcx
0x18000293a  mov     [rsp+22F8h+var_22C0], rcx
0x18000293f  mov     qword ptr [rsp+22F8h+Data], rdx
0x180002944  mov     [rsp+22F8h+var_22A8], rcx
0x180002949  mov     [rsp+22F8h+var_2278], rdx
0x180002951  mov     [rsp+22F8h+var_2298], r8
0x180002956  mov     [rsp+22F8h+var_2270], r9
0x18000295e  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180002966  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x18000296b  xor     ebx, ebx
0x18000296d  test    eax, eax
0x18000296f  js      short loc_1800029A3
0x180002971  mov     edi, ebx
0x180002973  lea     r13, ?map@?1??VTFromRegType@CRegParser@ATL@@KAHPEBGAEAG@Z@4QBUtypemap@?1??123@KAH01@Z@B; `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::typemap const near * const `ATL::CRegParser::VTFromRegType(ushort const *,ushort &)'::`2'::map
0x18000297a  movsxd  rsi, edi
0x18000297d  add     rsi, rsi
0x180002980  mov     rdx, [r13+rsi*8+0]; lpString2
0x180002985  lea     rcx, [rsp+22F8h+String1]; lpString1
0x18000298d  call    cs:__imp_lstrcmpiW
0x180002993  test    eax, eax
0x180002995  jz      short loc_1800029C6
0x180002997  inc     edi
0x180002999  cmp     edi, 4
0x18000299c  jb      short loc_18000297A
0x18000299e  mov     eax, 80020009h
0x1800029a3  mov     rcx, [rsp+22F8h+var_48]
0x1800029ab  xor     rcx, rsp; StackCookie
0x1800029ae  call    __security_check_cookie
0x1800029b3  add     rsp, 22C0h
0x1800029ba  pop     r15
0x1800029bc  pop     r14
0x1800029be  pop     r13
0x1800029c0  pop     r12
0x1800029c2  pop     rdi
0x1800029c3  pop     rsi
0x1800029c4  pop     rbx
0x1800029c5  retn
0x1800029c6  movzx   edi, word ptr [r13+rsi*8+8]
0x1800029cc  mov     esi, 13h
0x1800029d1  mov     rdx, [r15]
0x1800029d4  movzx   ecx, word ptr [rdx]
0x1800029d7  sub     ecx, 9
0x1800029da  jz      loc_180002E9D
0x1800029e0  sub     ecx, 1
0x1800029e3  jz      loc_180002E9D
0x1800029e9  sub     ecx, 3
0x1800029ec  jz      loc_180002E9D
0x1800029f2  cmp     ecx, esi
0x1800029f4  jz      loc_180002E9D
0x1800029fa  lea     rdx, [rsp+22F8h+String1]; unsigned __int16 *
0x180002a02  mov     rcx, r15; this
0x180002a05  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180002a0a  test    eax, eax
0x180002a0c  js      short loc_1800029A3
0x180002a0e  mov     r13d, 8
0x180002a14  cmp     di, r13w
0x180002a18  jz      loc_180002E4E
0x180002a1e  cmp     di, 11h
0x180002a22  jz      loc_180002C27
0x180002a28  cmp     di, si
0x180002a2b  jz      loc_180002BCF
0x180002a31  mov     eax, 4008h
0x180002a36  cmp     di, ax
0x180002a39  jnz     loc_180002E81
0x180002a3f  lea     rcx, [rsp+22F8h+String1]
0x180002a47  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002a4b  mov     rax, rsi
0x180002a4e  inc     rax
0x180002a51  cmp     [rcx+rax*2], bx
0x180002a55  jnz     short loc_180002A4E
0x180002a57  add     eax, 2
0x180002a5a  mov     [rsp+22F8h+var_2158], rbx
0x180002a62  test    eax, eax
0x180002a64  jz      short loc_180002A9F
0x180002a66  movsxd  rcx, eax
0x180002a69  xor     edx, edx
0x180002a6b  mov     rax, rsi
0x180002a6e  div     rcx
0x180002a71  cmp     rax, 2
0x180002a75  jb      loc_180002EAE
0x180002a7b  lea     rdx, [rcx+rcx]
0x180002a7f  cmp     rdx, 100h
0x180002a86  jbe     short loc_180002A9F
0x180002a88  lea     rcx, [rsp+22F8h+var_2158]
0x180002a90  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002a95  mov     rdi, [rsp+22F8h+var_2158]
0x180002a9d  jmp     short loc_180002AAF
0x180002a9f  lea     rdi, [rsp+22F8h+var_2150]
0x180002aa7  mov     [rsp+22F8h+var_2158], rdi
0x180002aaf  mov     r13, [rsp+22F8h+lpValueName]
0x180002ab4  jmp     short loc_180002AD8
0x180002ab6  xor     ebx, ebx
0x180002ab8  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002abc  mov     rdi, [rsp+22F8h+var_2158]
0x180002ac4  mov     r12, qword ptr [rsp+22F8h+Data]
0x180002ac9  mov     rax, [rsp+22F8h+var_22A8]
0x180002ace  mov     [rsp+22F8h+var_22C0], rax
0x180002ad3  mov     r13, [rsp+22F8h+var_2298]
0x180002ad8  test    rdi, rdi
0x180002adb  jz      loc_180002B97
0x180002ae1  lea     r14, [rsp+22F8h+String1]
0x180002ae9  cmp     [rsp+22F8h+String1], bx
0x180002af1  jz      short loc_180002B34
0x180002af3  mov     r15d, 30h ; '0'
0x180002af9  mov     rcx, r14; lpsz
0x180002afc  call    cs:__imp_CharNextW
0x180002b02  movzx   ecx, word ptr [r14]
0x180002b06  cmp     cx, 5Ch ; '\'
0x180002b0a  jnz     short loc_180002B23
0x180002b0c  cmp     [rax], r15w
0x180002b10  jnz     short loc_180002B23
0x180002b12  mov     [rdi], bx
0x180002b15  mov     rcx, rax; lpsz
0x180002b18  call    cs:__imp_CharNextW
0x180002b1e  mov     r14, rax
0x180002b21  jmp     short loc_180002B2A
0x180002b23  mov     [rdi], cx
0x180002b26  add     r14, 2
0x180002b2a  add     rdi, 2
0x180002b2e  cmp     [r14], bx
0x180002b32  jnz     short loc_180002AF9
0x180002b34  mov     dword ptr [rdi], 0
0x180002b3a  mov     r8, [rsp+22F8h+var_2158]
0x180002b42  test    r8, r8
0x180002b45  jz      loc_180002EB9
0x180002b4b  mov     r10d, ebx
0x180002b4e  mov     r9, r8
0x180002b51  mov     rcx, rsi
0x180002b54  inc     rcx
0x180002b57  cmp     [r9+rcx*2], bx
0x180002b5c  jnz     short loc_180002B54
0x180002b5e  inc     ecx
0x180002b60  lea     r9, [r9+rcx*2]
0x180002b64  lea     r10d, [r10+rcx*2]
0x180002b68  cmp     ecx, 1
0x180002b6b  jnz     short loc_180002B51
0x180002b6d  mov     [rsp+22F8h+cbData], r10d; cbData
0x180002b72  mov     [rsp+22F8h+lpData], r8; lpData
0x180002b77  lea     r9d, [rcx+6]; dwType
0x180002b7b  xor     r8d, r8d; Reserved
0x180002b7e  mov     rdx, r13; lpValueName
0x180002b81  mov     rcx, [r12]; hKey
0x180002b85  call    cs:__imp_RegSetValueExW
0x180002b8b  mov     esi, eax
0x180002b8d  mov     rdi, [rsp+22F8h+var_2158]
0x180002b95  jmp     short loc_180002B9C
0x180002b97  mov     esi, 0Eh
0x180002b9c  lea     rax, [rsp+22F8h+var_2150]
0x180002ba4  cmp     rdi, rax
0x180002ba7  jz      short loc_180002BB6
0x180002ba9  lea     rcx, [rsp+22F8h+var_2158]
0x180002bb1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002bb6  mov     r15, [rsp+22F8h+var_22C0]
0x180002bbb  test    esi, esi
0x180002bbd  jz      loc_180002E81
0x180002bc3  mov     ecx, esi; unsigned int
0x180002bc5  call    ?AtlHresultFromWin32@ATL@@YAJK@Z; ATL::AtlHresultFromWin32(ulong)
0x180002bca  jmp     loc_1800029A3
0x180002bcf  mov     [rsp+22F8h+pulOut], ebx
0x180002bd3  lea     r9, [rsp+22F8h+pulOut]; pulOut
0x180002bd8  xor     r8d, r8d; dwFlags
0x180002bdb  xor     edx, edx; lcid
0x180002bdd  lea     rcx, [rsp+22F8h+String1]; strIn
0x180002be5  call    cs:__imp_VarUI4FromStr
0x180002beb  test    eax, eax
0x180002bed  js      loc_1800029A3
0x180002bf3  mov     eax, [rsp+22F8h+pulOut]
0x180002bf7  mov     dword ptr [rsp+22F8h+Data], eax
0x180002bfb  mov     [rsp+22F8h+cbData], 4; cbData
0x180002c03  lea     rax, [rsp+22F8h+Data]
0x180002c08  mov     r9d, 4; dwType
0x180002c0e  mov     [rsp+22F8h+lpData], rax; lpData
0x180002c13  xor     r8d, r8d; Reserved
0x180002c16  mov     rdx, r14; lpValueName
0x180002c19  mov     rcx, [r12]; hKey
0x180002c1d  call    cs:__imp_RegSetValueExW
0x180002c23  mov     esi, eax
0x180002c25  jmp     short loc_180002BBB
0x180002c27  lea     rax, [rsp+22F8h+String1]
0x180002c2f  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180002c33  mov     r14, rsi
0x180002c36  inc     r14
0x180002c39  cmp     [rax+r14*2], bx
0x180002c3e  jnz     short loc_180002C36
0x180002c40  mov     dword ptr [rsp+22F8h+Data], r14d
0x180002c45  test    r14b, 1
0x180002c49  jnz     loc_180002D03
0x180002c4f  mov     eax, r14d
0x180002c52  cdq
0x180002c53  sub     eax, edx
0x180002c55  sar     eax, 1
0x180002c57  movsxd  r12, eax
0x180002c5a  mov     [rsp+22F8h+var_2268], rbx
0x180002c62  mov     rdi, r12
0x180002c65  mov     [rsp+22F8h+var_2280], r12
0x180002c6a  test    eax, eax
0x180002c6c  jz      short loc_180002CA3
0x180002c6e  xor     edx, edx
0x180002c70  mov     rax, rsi
0x180002c73  div     rdi
0x180002c76  cmp     rax, 1
0x180002c7a  jb      loc_180002EC4
0x180002c80  cmp     rdi, 100h
0x180002c87  jbe     short loc_180002CA3
0x180002c89  mov     rdx, rdi
0x180002c8c  lea     rcx, [rsp+22F8h+var_2268]
0x180002c94  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180002c99  mov     rcx, [rsp+22F8h+var_2268]
0x180002ca1  jmp     short loc_180002CB3
0x180002ca3  lea     rcx, [rsp+22F8h+var_2260]
0x180002cab  mov     [rsp+22F8h+var_2268], rcx
0x180002cb3  mov     rsi, [rsp+22F8h+var_2288]
0x180002cb8  jmp     short loc_180002CF1
0x180002cba  xor     ebx, ebx
0x180002cbc  lea     r13d, [rbx+8]
0x180002cc0  mov     r14d, dword ptr [rsp+22F8h+Data]
0x180002cc5  mov     rcx, [rsp+22F8h+var_2268]; void *
0x180002ccd  mov     rdi, [rsp+22F8h+var_2280]
0x180002cd2  mov     rax, [rsp+22F8h+var_22A8]
0x180002cd7  mov     [rsp+22F8h+var_22C0], rax
0x180002cdc  mov     rsi, [rsp+22F8h+var_2278]
0x180002ce4  mov     rax, [rsp+22F8h+var_2298]
0x180002ce9  mov     [rsp+22F8h+lpValueName], rax
0x180002cee  mov     r12d, edi
0x180002cf1  test    rcx, rcx
0x180002cf4  jnz     short loc_180002D0D
0x180002cf6  lea     rcx, [rsp+22F8h+var_2268]
0x180002cfe  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180002d03  mov     eax, 80004005h
0x180002d08  jmp     loc_1800029A3
0x180002d0d  mov     r8, rdi; Size
0x180002d10  xor     edx, edx; Val
0x180002d12  call    memset_0
0x180002d17  mov     r10d, ebx
0x180002d1a  test    r14d, r14d
0x180002d1d  jle     loc_180002DFB
0x180002d23  mov     r15d, 30h ; '0'
0x180002d29  mov     eax, r10d
0x180002d2c  movzx   edx, [rsp+rax*2+22F8h+String1]
0x180002d34  cmp     edx, 61h ; 'a'
0x180002d37  ja      short loc_180002DA6
0x180002d39  jz      loc_180002DC6
0x180002d3f  cmp     edx, 38h ; '8'
0x180002d42  ja      short loc_180002D78
0x180002d44  jz      short loc_180002D70
0x180002d46  mov     ecx, edx
0x180002d48  sub     ecx, r15d
0x180002d4b  jz      short loc_180002D70
0x180002d4d  sub     ecx, 1
0x180002d50  jz      short loc_180002D70
0x180002d52  sub     ecx, 1
0x180002d55  jz      short loc_180002D70
0x180002d57  sub     ecx, 1
0x180002d5a  jz      short loc_180002D70
0x180002d5c  sub     ecx, 1
0x180002d5f  jz      short loc_180002D70
0x180002d61  sub     ecx, 1
0x180002d64  jz      short loc_180002D70
0x180002d66  sub     ecx, 1
0x180002d69  jz      short loc_180002D70
0x180002d6b  cmp     ecx, 1
0x180002d6e  jnz     short loc_180002DC1
0x180002d70  mov     r9d, edx
0x180002d73  sub     r9d, r15d
0x180002d76  jmp     short loc_180002DCA
0x180002d78  mov     r9d, edx
0x180002d7b  mov     ecx, edx
0x180002d7d  sub     ecx, 39h ; '9'
0x180002d80  jz      short loc_180002D70
0x180002d82  sub     ecx, r13d
0x180002d85  jz      short loc_180002DA0
0x180002d87  sub     ecx, 1
0x180002d8a  jz      short loc_180002DA0
0x180002d8c  sub     ecx, 1
0x180002d8f  jz      short loc_180002DA0
0x180002d91  sub     ecx, 1
0x180002d94  jz      short loc_180002DA0
0x180002d96  sub     ecx, 1
0x180002d99  jz      short loc_180002DA0
0x180002d9b  cmp     ecx, 1
0x180002d9e  jnz     short loc_180002DC1
0x180002da0  add     r9d, 0FFFFFFC9h
0x180002da4  jmp     short loc_180002DCA
  ... truncated ...
```
