# UiccFromKey(HKEY__ *)

- ea: `0x1800123b0`
- end: `0x18001289b`
- name: `?UiccFromKey@@YA?AUUicc@@PEAUHKEY__@@@Z`
- size: `1259`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x1800114a0`

## callees

- `0x180002c08`
- `0x18000e308`
- `0x18000f7c4`
- `0x18000faec`
- `0x18000fd24`
- `0x180010cb4`
- `0x180012124`
- `0x180012390`
- `0x1800123b0`
- `0x180012c70`
- `0x180012d04`
- `0x180012d80`
- `0x18003b9a0`

## import_xrefs

- `msvcrt!wcstok_s` at `0x1800125bb`
- `msvcrt!wcstok_s` at `0x1800125bb`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012554`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001256d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800127d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800127ea`
- `msvcrt!??3@YAXPEAX@Z` at `0x180012554`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001256d`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800127d1`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800127ea`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800127bb`
- `msvcrt!??_V@YAXPEAX@Z` at `0x1800127bb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001276e`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001276e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001245a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800124a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800124f8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001245a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800124a9`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800124f8`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001265b`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x18001265b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800126d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800126d2`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800127a7`
- `api-ms-win-core-registry-l1-1-0!RegEnumKeyExW` at `0x1800127a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall UiccFromKey(__int64 a1, HKEY a2)
{
  unsigned int ValueW; // eax
  unsigned int v5; // eax
  void *v6; // rdx
  wchar_t *v7; // rbx
  wchar_t *v8; // rbx
  wchar_t *v9; // rcx
  char *v10; // rdi
  _QWORD *v11; // rcx
  unsigned __int64 v12; // r8
  unsigned int v13; // eax
  DWORD v14; // eax
  wchar_t *v15; // rdi
  DWORD i; // edx
  unsigned int v17; // eax
  _QWORD *v18; // r15
  _QWORD *v19; // rsi
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  unsigned int v23; // eax
  unsigned int pdwType; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-E0h]
  int pdwTypeb; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypec; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTyped; // [rsp+20h] [rbp-E0h]
  unsigned int pdwTypee; // [rsp+20h] [rbp-E0h]
  int pvData; // [rsp+60h] [rbp-A0h] BYREF
  DWORD pcbData; // [rsp+64h] [rbp-9Ch] BYREF
  DWORD cbMaxSubKeyLen; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *Context; // [rsp+70h] [rbp-90h] BYREF
  DWORD cchName; // [rsp+78h] [rbp-88h] BYREF
  DWORD v36; // [rsp+7Ch] [rbp-84h]
  int v37; // [rsp+80h] [rbp-80h]
  wchar_t *String[5]; // [rsp+88h] [rbp-78h] BYREF
  _BYTE v39[96]; // [rsp+B0h] [rbp-50h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  String[1] = (wchar_t *)a1;
  *(_QWORD *)(a1 + 24) = 7;
  *(_QWORD *)(a1 + 16) = 0;
  *(_WORD *)a1 = 0;
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 40) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_QWORD *)(a1 + 64) = 0;
  *(_QWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 80) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  v37 = 1;
  pvData = 0;
  pcbData = 4;
  ValueW = RegGetValueW(a2, 0, L"Locked", 0x10u, 0, &pvData, &pcbData);
  if ( ValueW )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)ValueW,
      pdwType);
  *(_DWORD *)(a1 + 100) = (pvData != 0) + 1;
  pcbData = 4;
  v5 = RegGetValueW(a2, 0, L"roaming", 0x10u, 0, &pvData, &pcbData);
  if ( v5 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1C5,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)v5,
      pdwTypea);
  *(_BYTE *)(a1 + 104) = pvData != 0;
  pvData = 0;
  pcbData = 4;
  RegGetValueW(a2, 0, L"ESIM", 0x10u, 0, &pvData, &pcbData);
  *(_BYTE *)(a1 + 105) = pvData != 0;
  v6 = *(void **)StringFromKey(&Context, a2, L"Iccid", 0);
  if ( !v6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x24,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\inc\\nullable.h",
      (const char *)0x8007139FLL,
      pdwTypeb);
  std::wstring::operator=((void *)a1, v6);
  v7 = Context;
  if ( Context )
  {
    if ( *((_QWORD *)Context + 3) >= 8u )
      operator delete(*(void **)Context);
    *((_QWORD *)v7 + 3) = 7;
    *((_QWORD *)v7 + 2) = 0;
    *v7 = 0;
    operator delete(v7);
  }
  StringFromKey(String, a2, L"PreferredLanguages", 0);
  v8 = String[0];
  if ( String[0] )
  {
    Context = 0;
    if ( *((_QWORD *)String[0] + 3) < 8u )
      v9 = String[0];
    else
      v9 = *(wchar_t **)String[0];
    while ( 1 )
    {
      v10 = (char *)wcstok_s(v9, L";", &Context);
      if ( !v10 )
        break;
      if ( *(_QWORD *)(a1 + 40) == *(_QWORD *)(a1 + 48) )
        std::vector<std::wstring>::_Reserve(a1 + 32);
      v11 = *(_QWORD **)(a1 + 40);
      v11[3] = 7;
      v11[2] = 0;
      *(_WORD *)v11 = 0;
      if ( *(_WORD *)v10 )
      {
        v12 = -1;
        do
          ++v12;
        while ( *(_WORD *)&v10[2 * v12] );
      }
      else
      {
        v12 = 0;
      }
      std::wstring::assign(v11, v10, v12);
      *(_QWORD *)(a1 + 40) += 32LL;
      v9 = 0;
    }
  }
  cbMaxSubKeyLen = 0;
  v13 = RegQueryInfoKeyW(a2, 0, 0, 0, 0, &cbMaxSubKeyLen, 0, 0, 0, 0, 0, 0);
  if ( v13 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x1E4,
      (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
      (const char *)v13,
      pdwTypec);
  v14 = cbMaxSubKeyLen;
  if ( cbMaxSubKeyLen )
  {
    ++cbMaxSubKeyLen;
    v15 = (wchar_t *)operator new[](saturated_mul(v14 + 1, 2u));
    String[3] = v15;
    v36 = 0;
    for ( i = 0; ; i = v36 )
    {
      cchName = cbMaxSubKeyLen;
      v23 = RegEnumKeyExW(a2, i, v15, &cchName, 0, 0, 0, 0);
      if ( v23 == 259 )
        break;
      if ( v23 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1F7,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
          (const char *)v23,
          pdwTypee);
      Context = 0;
      v17 = RegOpenKeyExW(a2, v15, 0, 0x20019u, (PHKEY)&Context);
      if ( v17 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x1FB,
          (unsigned int)"onecoreuap\\admin\\prov\\multivariant\\handlers\\emulator\\mvcellularemulator.cpp",
          (const char *)v17,
          pdwTyped);
      v18 = (_QWORD *)LineFromKey(v39, Context);
      if ( *(_QWORD *)(a1 + 64) == *(_QWORD *)(a1 + 72) )
        std::vector<Line>::_Reserve(a1 + 56);
      v19 = *(_QWORD **)(a1 + 64);
      std::wstring::wstring(v19, v18);
      std::wstring::wstring(v19 + 4, v18 + 4);
      v20 = v18[8];
      v18[8] = 0;
      v19[8] = v20;
      v21 = v18[9];
      v18[9] = 0;
      v19[9] = v21;
      v22 = v18[10];
      v18[10] = 0;
      v19[10] = v22;
      v19[11] = v18[11];
      *(_QWORD *)(a1 + 64) += 96LL;
      Line::~Line((Line *)v39);
      if ( Context )
        RegCloseKey((HKEY)Context);
      ++v36;
    }
    operator delete[](v15);
  }
  if ( v8 )
  {
    if ( *((_QWORD *)v8 + 3) >= 8u )
      operator delete(*(void **)v8);
    *((_QWORD *)v8 + 3) = 7;
    *((_QWORD *)v8 + 2) = 0;
    *v8 = 0;
    operator delete(v8);
  }
  return a1;
}

```

## disassembly

```asm
0x1800123b0  mov     [rsp-8+arg_10], rbx
0x1800123b5  push    rbp
0x1800123b6  push    rsi
0x1800123b7  push    rdi
0x1800123b8  push    r12
0x1800123ba  push    r13
0x1800123bc  push    r14
0x1800123be  push    r15
0x1800123c0  lea     rbp, [rsp-20h]
0x1800123c5  sub     rsp, 120h
0x1800123cc  mov     rax, cs:__security_cookie
0x1800123d3  xor     rax, rsp
0x1800123d6  mov     [rbp+50h+var_40], rax
0x1800123da  mov     r12, rdx
0x1800123dd  mov     r14, rcx
0x1800123e0  mov     [rbp+50h+var_C0], rcx
0x1800123e4  xor     r15d, r15d
0x1800123e7  mov     [rbp+50h+var_D0], r15d
0x1800123eb  mov     qword ptr [rcx+18h], 7
0x1800123f3  mov     [rcx+10h], r15
0x1800123f7  mov     [rcx], r15w
0x1800123fb  mov     [rcx+20h], r15
0x1800123ff  mov     [rcx+28h], r15
0x180012403  mov     [rcx+30h], r15
0x180012407  mov     [rcx+38h], r15
0x18001240b  mov     [rcx+40h], r15
0x18001240f  mov     [rcx+48h], r15
0x180012413  mov     [rcx+50h], r15
0x180012417  mov     [rcx+58h], r15
0x18001241b  mov     [rbp+50h+var_D0], 1
0x180012422  mov     [rsp+150h+var_F0], r15d
0x180012427  lea     ebx, [r15+4]
0x18001242b  mov     [rsp+150h+var_EC], ebx
0x18001242f  lea     rax, [rsp+150h+var_EC]
0x180012434  mov     [rsp+150h+pcbData], rax; pcbData
0x180012439  lea     rax, [rsp+150h+var_F0]
0x18001243e  mov     [rsp+150h+pvData], rax; pvData
0x180012443  mov     [rsp+150h+pdwType], r15; unsigned int
0x180012448  lea     edi, [rbx+0Ch]
0x18001244b  mov     r9d, edi; dwFlags
0x18001244e  lea     r8, ?gc_wszLocked@@3QBGB; "Locked"
0x180012455  xor     edx, edx; lpSubKey
0x180012457  mov     rcx, r12; hkey
0x18001245a  call    cs:__imp_RegGetValueW
0x180012460  mov     rcx, [rbp+58h]; this
0x180012464  test    eax, eax
0x180012466  jnz     loc_180012844
0x18001246c  mov     eax, r15d
0x18001246f  cmp     [rsp+150h+var_F0], r15d
0x180012474  setnz   al
0x180012477  inc     eax
0x180012479  mov     [r14+64h], eax
0x18001247d  mov     [rsp+150h+var_EC], ebx
0x180012481  lea     rax, [rsp+150h+var_EC]
0x180012486  mov     [rsp+150h+pcbData], rax; pcbData
0x18001248b  lea     rax, [rsp+150h+var_F0]
0x180012490  mov     [rsp+150h+pvData], rax; pvData
0x180012495  mov     [rsp+150h+pdwType], r15; unsigned int
0x18001249a  mov     r9d, edi; dwFlags
0x18001249d  lea     r8, ?gc_wszRoaming@@3QBGB; "roaming"
0x1800124a4  xor     edx, edx; lpSubKey
0x1800124a6  mov     rcx, r12; hkey
0x1800124a9  call    cs:__imp_RegGetValueW
0x1800124af  mov     rcx, [rbp+58h]; this
0x1800124b3  test    eax, eax
0x1800124b5  jnz     loc_180012859
0x1800124bb  cmp     [rsp+150h+var_F0], r15d
0x1800124c0  setnz   al
0x1800124c3  mov     [r14+68h], al
0x1800124c7  mov     [rsp+150h+var_F0], r15d
0x1800124cc  mov     [rsp+150h+var_EC], ebx
0x1800124d0  lea     rax, [rsp+150h+var_EC]
0x1800124d5  mov     [rsp+150h+pcbData], rax; pcbData
0x1800124da  lea     rax, [rsp+150h+var_F0]
0x1800124df  mov     [rsp+150h+pvData], rax; pvData
0x1800124e4  mov     [rsp+150h+pdwType], r15; int
0x1800124e9  mov     r9d, edi; dwFlags
0x1800124ec  lea     r8, ?c_esim@@3QBGB; "ESIM"
0x1800124f3  xor     edx, edx; lpSubKey
0x1800124f5  mov     rcx, r12; hkey
0x1800124f8  call    cs:__imp_RegGetValueW
0x1800124fe  cmp     [rsp+150h+var_F0], r15d
0x180012503  setnz   al
0x180012506  mov     [r14+69h], al
0x18001250a  xor     r9d, r9d
0x18001250d  lea     r8, ?gc_wszIccid@@3QBGB; "Iccid"
0x180012514  mov     rdx, r12
0x180012517  lea     rcx, [rsp+150h+Context]
0x18001251c  call    ?StringFromKey@@YA?AV?$nullable_any@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@PEAUHKEY__@@PEBGW4PresenceRequired@@@Z; StringFromKey(HKEY__ *,ushort const *,PresenceRequired)
0x180012521  nop
0x180012522  mov     rdx, [rax]; Src
0x180012525  test    rdx, rdx
0x180012528  setnz   al
0x18001252b  mov     rcx, [rbp+58h]; this
0x18001252f  test    al, al
0x180012531  jz      loc_18001286E
0x180012537  mov     rcx, r14; void *
0x18001253a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001253f  nop
0x180012540  mov     rbx, [rsp+150h+Context]
0x180012545  test    rbx, rbx
0x180012548  jz      short loc_180012573
0x18001254a  cmp     qword ptr [rbx+18h], 8
0x18001254f  jb      short loc_18001255A
0x180012551  mov     rcx, [rbx]
0x180012554  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18001255a  mov     qword ptr [rbx+18h], 7
0x180012562  mov     [rbx+10h], r15
0x180012566  mov     [rbx], r15w
0x18001256a  mov     rcx, rbx
0x18001256d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180012573  xor     r9d, r9d
0x180012576  lea     r8, ?gc_wszPreferredLanguages@@3QBGB; "PreferredLanguages"
0x18001257d  mov     rdx, r12
0x180012580  lea     rcx, [rbp+50h+String]
0x180012584  call    ?StringFromKey@@YA?AV?$nullable_any@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@@PEAUHKEY__@@PEBGW4PresenceRequired@@@Z; StringFromKey(HKEY__ *,ushort const *,PresenceRequired)
0x180012589  nop
0x18001258a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001258e  mov     rbx, [rbp+50h+String]
0x180012592  test    rbx, rbx
0x180012595  jz      loc_18001261E
0x18001259b  mov     [rsp+150h+Context], r15
0x1800125a0  cmp     qword ptr [rbx+18h], 8
0x1800125a5  jb      short loc_1800125AC
0x1800125a7  mov     rcx, [rbx]
0x1800125aa  jmp     short loc_1800125AF
0x1800125ac  mov     rcx, rbx; String
0x1800125af  lea     r8, [rsp+150h+Context]; Context
0x1800125b4  lea     rdx, Delimiter; ";"
0x1800125bb  call    cs:__imp_wcstok_s
0x1800125c1  test    rax, rax
0x1800125c4  mov     rdi, rax
0x1800125c7  jz      short loc_18001261A
0x1800125c9  mov     rax, [r14+30h]
0x1800125cd  cmp     [r14+28h], rax
0x1800125d1  jnz     short loc_1800125DC
0x1800125d3  lea     rcx, [r14+20h]
0x1800125d7  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x1800125dc  mov     rcx, [r14+28h]; void *
0x1800125e0  mov     qword ptr [rcx+18h], 7
0x1800125e8  mov     [rcx+10h], r15
0x1800125ec  mov     [rcx], r15w
0x1800125f0  cmp     [rdi], r15w
0x1800125f4  jnz     short loc_1800125FB
0x1800125f6  mov     r8, r15
0x1800125f9  jmp     short loc_180012609
0x1800125fb  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800125ff  inc     r8
0x180012602  cmp     [rdi+r8*2], r15w
0x180012607  jnz     short loc_1800125FF
0x180012609  mov     rdx, rdi; Src
0x18001260c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180012611  add     qword ptr [r14+28h], 20h ; ' '
0x180012616  xor     ecx, ecx
0x180012618  jmp     short loc_1800125AF
0x18001261a  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18001261e  mov     [rsp+150h+cbMaxSubKeyLen], r15d
0x180012623  mov     [rsp+150h+lpftLastWriteTime], r15; lpftLastWriteTime
0x180012628  mov     [rsp+150h+lpcbSecurityDescriptor], r15; lpcbSecurityDescriptor
0x18001262d  mov     [rsp+150h+lpcbMaxValueLen], r15; lpcbMaxValueLen
0x180012632  mov     [rsp+150h+lpcbMaxValueNameLen], r15; lpcbMaxValueNameLen
0x180012637  mov     [rsp+150h+lpcValues], r15; lpcValues
0x18001263c  mov     [rsp+150h+pcbData], r15; lpcbMaxClassLen
0x180012641  lea     rax, [rsp+150h+cbMaxSubKeyLen]
0x180012646  mov     [rsp+150h+pvData], rax; lpcbMaxSubKeyLen
0x18001264b  mov     [rsp+150h+pdwType], r15; unsigned int
0x180012650  xor     r9d, r9d; lpReserved
0x180012653  xor     r8d, r8d; lpcchClass
0x180012656  xor     edx, edx; lpClass
0x180012658  mov     rcx, r12; hKey
0x18001265b  call    cs:__imp_RegQueryInfoKeyW
0x180012661  mov     rcx, [rbp+58h]; this
0x180012665  test    eax, eax
0x180012667  jnz     loc_180012886
0x18001266d  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x180012671  test    eax, eax
0x180012673  jz      loc_1800127C2
0x180012679  inc     eax
0x18001267b  mov     [rsp+150h+cbMaxSubKeyLen], eax
0x18001267f  mov     ecx, eax
0x180012681  mov     eax, 2
0x180012686  mul     rcx
0x180012689  cmovb   rax, rdi
0x18001268d  mov     rcx, rax; unsigned __int64
0x180012690  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180012695  mov     rdi, rax
0x180012698  mov     [rbp+50h+var_B0], rax
0x18001269c  mov     [rsp+150h+var_D4], r15d
0x1800126a1  xor     edx, edx
0x1800126a3  jmp     loc_180012780
0x1800126a8  mov     rcx, [rbp+58h]; this
0x1800126ac  test    eax, eax
0x1800126ae  jnz     loc_18001282F
0x1800126b4  mov     [rsp+150h+Context], r15
0x1800126b9  lea     rax, [rsp+150h+Context]
0x1800126be  mov     [rsp+150h+pdwType], rax; unsigned int
0x1800126c3  mov     r9d, 20019h; samDesired
0x1800126c9  xor     r8d, r8d; ulOptions
0x1800126cc  mov     rdx, rdi; lpSubKey
0x1800126cf  mov     rcx, r12; hKey
0x1800126d2  call    cs:__imp_RegOpenKeyExW
0x1800126d8  mov     rcx, [rbp+58h]; this
0x1800126dc  test    eax, eax
0x1800126de  jnz     loc_18001281A
0x1800126e4  mov     rdx, [rsp+150h+Context]
0x1800126e9  lea     rcx, [rbp+50h+var_A0]
0x1800126ed  call    ?LineFromKey@@YA?AULine@@PEAUHKEY__@@@Z; LineFromKey(HKEY__ *)
0x1800126f2  mov     r15, rax
0x1800126f5  mov     rax, [r14+48h]
0x1800126f9  cmp     [r14+40h], rax
0x1800126fd  jnz     short loc_180012708
0x1800126ff  lea     rcx, [r14+38h]
0x180012703  call    ?_Reserve@?$vector@ULine@@V?$allocator@ULine@@@std@@@std@@IEAAX_K@Z; std::vector<Line>::_Reserve(unsigned __int64)
0x180012708  mov     rsi, [r14+40h]
0x18001270c  mov     rdx, r15
0x18001270f  mov     rcx, rsi
0x180012712  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180012717  lea     rdx, [r15+20h]
0x18001271b  lea     rcx, [rsi+20h]
0x18001271f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x180012724  mov     rax, [r15+40h]
0x180012728  xor     ecx, ecx
0x18001272a  mov     [r15+40h], rcx
0x18001272e  mov     [rsi+40h], rax
0x180012732  mov     rax, [r15+48h]
0x180012736  mov     [r15+48h], rcx
0x18001273a  mov     [rsi+48h], rax
0x18001273e  mov     rax, [r15+50h]
0x180012742  mov     [r15+50h], rcx
0x180012746  mov     [rsi+50h], rax
0x18001274a  mov     rax, [r15+58h]
0x18001274e  mov     [rsi+58h], rax
0x180012752  add     qword ptr [r14+40h], 60h ; '`'
0x180012757  lea     rcx, [rbp+50h+var_A0]; this
0x18001275b  call    ??1Line@@QEAA@XZ; Line::~Line(void)
0x180012760  nop
0x180012761  mov     rcx, [rsp+150h+Context]; hKey
0x180012766  xor     r15d, r15d
0x180012769  test    rcx, rcx
0x18001276c  jz      short loc_180012774
0x18001276e  call    cs:__imp_RegCloseKey
0x180012774  mov     esi, [rsp+150h+var_D4]
0x180012778  inc     esi
0x18001277a  mov     [rsp+150h+var_D4], esi
0x18001277e  mov     edx, esi; dwIndex
0x180012780  mov     [rsp+150h+lpcValues], r15; lpftLastWriteTime
0x180012785  mov     [rsp+150h+pcbData], r15; lpcchClass
0x18001278a  mov     [rsp+150h+pvData], r15; lpClass
0x18001278f  mov     eax, [rsp+150h+cbMaxSubKeyLen]
0x180012793  mov     [rsp+150h+pdwType], r15; unsigned int
0x180012798  mov     [rsp+150h+cchName], eax
0x18001279c  lea     r9, [rsp+150h+cchName]; lpcchName
0x1800127a1  mov     r8, rdi; lpName
0x1800127a4  mov     rcx, r12; hKey
0x1800127a7  call    cs:__imp_RegEnumKeyExW
0x1800127ad  cmp     eax, 103h
0x1800127b2  jnz     loc_1800126A8
0x1800127b8  mov     rcx, rdi
0x1800127bb  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x1800127c1  nop
0x1800127c2  test    rbx, rbx
0x1800127c5  jz      short loc_1800127F0
0x1800127c7  cmp     qword ptr [rbx+18h], 8
0x1800127cc  jb      short loc_1800127D7
0x1800127ce  mov     rcx, [rbx]
0x1800127d1  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800127d7  mov     qword ptr [rbx+18h], 7
0x1800127df  mov     [rbx+10h], r15
0x1800127e3  mov     [rbx], r15w
0x1800127e7  mov     rcx, rbx
0x1800127ea  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x1800127f0  mov     rax, r14
0x1800127f3  mov     rcx, [rbp+50h+var_40]
0x1800127f7  xor     rcx, rsp; StackCookie
0x1800127fa  call    __security_check_cookie
0x1800127ff  mov     rbx, [rsp+150h+arg_10]
0x180012807  add     rsp, 120h
0x18001280e  pop     r15
0x180012810  pop     r14
0x180012812  pop     r13
0x180012814  pop     r12
0x180012816  pop     rdi
0x180012817  pop     rsi
0x180012818  pop     rbp
0x180012819  retn
0x18001281a  mov     r9d, eax; char *
0x18001281d  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180012824  mov     edx, 1FBh; void *
0x180012829  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18001282f  mov     r9d, eax; char *
0x180012832  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180012839  mov     edx, 1F7h; void *
0x18001283e  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012844  mov     r9d, eax; char *
0x180012847  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x18001284e  mov     edx, 1BFh; void *
0x180012853  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180012859  mov     r9d, eax; char *
0x18001285c  lea     r8, aOnecoreuapAdmi_8; "onecoreuap\\admin\\prov\\multivariant\\"...
0x180012863  mov     edx, 1C5h; void *
  ... truncated ...
```
