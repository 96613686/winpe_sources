# CFilterMapper2::RegisterPin(_GUID,ushort const *,int,int,int,int,_GUID,ushort const *)

- ea: `0x180067980`
- end: `0x180067dc3`
- name: `?RegisterPin@CFilterMapper2@@EEAAJU_GUID@@PEBGHHHH01@Z`
- size: `1091`
- prototype: `int(CFilterMapper2 *__hidden this, struct _GUID *__struct_ptr, const unsigned __int16 *, int, int, int, int, struct _GUID *__struct_ptr, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180004924`
- `0x1800388a0`
- `0x180065b20`
- `0x1800662f4`
- `0x18006666c`
- `0x180066aa8`
- `0x180067980`
- `0x180068154`
- `0x1800681e4`
- `0x18015bb8c`
- `0x18015e010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x180067b63`
- `KERNEL32!LeaveCriticalSection` at `0x180067d4d`
- `KERNEL32!LeaveCriticalSection` at `0x180067d90`
- `KERNEL32!LeaveCriticalSection` at `0x180067b63`
- `KERNEL32!LeaveCriticalSection` at `0x180067d4d`
- `KERNEL32!LeaveCriticalSection` at `0x180067d90`
- `KERNEL32!EnterCriticalSection` at `0x180067a32`
- `KERNEL32!EnterCriticalSection` at `0x180067a32`
- `ADVAPI32!RegCreateKeyExW` at `0x180067b3f`
- `ADVAPI32!RegCreateKeyExW` at `0x180067be1`
- `ADVAPI32!RegCreateKeyExW` at `0x180067b3f`
- `ADVAPI32!RegCreateKeyExW` at `0x180067be1`
- `ADVAPI32!RegCloseKey` at `0x180067b54`
- `ADVAPI32!RegCloseKey` at `0x180067b7c`
- `ADVAPI32!RegCloseKey` at `0x180067c02`
- `ADVAPI32!RegCloseKey` at `0x180067d3e`
- `ADVAPI32!RegCloseKey` at `0x180067b54`
- `ADVAPI32!RegCloseKey` at `0x180067b7c`
- `ADVAPI32!RegCloseKey` at `0x180067c02`
- `ADVAPI32!RegCloseKey` at `0x180067d3e`
- `ole32!StringFromGUID2` at `0x180067a67`
- `ole32!StringFromGUID2` at `0x180067ce7`
- `ole32!StringFromGUID2` at `0x180067a67`
- `ole32!StringFromGUID2` at `0x180067ce7`

## string_xrefs

- `0x180067a83`: `CLSID`
- `0x180067ab9`: `CLSID`

## pseudocode

```c
__int64 __fastcall CFilterMapper2::RegisterPin(
        CFilterMapper2 *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        int a4,
        int a5,
        int a6,
        int a7,
        struct _GUID *Buf2,
        unsigned __int16 *a9)
{
  char *v13; // rbx
  struct _RTL_CRITICAL_SECTION *v14; // rdi
  CFilterMapper2 *v15; // rcx
  HKEY RegKey; // r14
  LSTATUS v17; // ebx
  HKEY v18; // rcx
  LSTATUS v19; // eax
  LSTATUS v20; // eax
  LSTATUS v21; // eax
  HKEY v22; // rbx
  LSTATUS v23; // eax
  bool v24; // zf
  LSTATUS v25; // eax
  bool v26; // zf
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwDisposition; // [rsp+58h] [rbp-A8h] BYREF
  HKEY phkResult; // [rsp+60h] [rbp-A0h] BYREF
  GUID rguid; // [rsp+70h] [rbp-90h] BYREF
  OLECHAR sz[40]; // [rsp+80h] [rbp-80h] BYREF
  OLECHAR v32[40]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR SubKey[264]; // [rsp+120h] [rbp+20h] BYREF

  *(_QWORD *)&rguid.Data1 = a3;
  if ( !a3 )
    return 2147500035LL;
  hKey = 0;
  dwDisposition = 0;
  if ( a4 && a5 || (!a9 || !*a9) && memcmp_0(&GUID_NULL, Buf2, 0x10u) )
    return 2147942487LL;
  v13 = (char *)this - 8;
  v14 = (struct _RTL_CRITICAL_SECTION *)(((unsigned __int64)this + 40) & -(__int64)(this != (CFilterMapper2 *)8));
  EnterCriticalSection(v14);
  CFilterMapper2::BreakCacheIfNotBuildingCache(v15);
  (*(void (__fastcall **)(char *, _QWORD, _QWORD, struct _GUID *))(*(_QWORD *)v13 + 32LL))(v13, 0, 0, a2);
  StringFromGUID2(a2, sz, 39);
  StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls", L"CLSID", sz);
  if ( (unsigned int)CheckRegKey(SubKey)
    && (StringCchPrintfW(SubKey, 0x104u, L"%ls\\%ls\\%ls", L"CLSID", sz, L"Pins"), (RegKey = GetRegKey(SubKey)) != 0) )
  {
    StringCchPrintfW(SubKey, 0x104u, L"%ls", *(_QWORD *)&rguid.Data1);
    v17 = RegCreateKeyExW(RegKey, SubKey, 0, 0, 0, 0x20006u, 0, &hKey, &dwDisposition);
    v18 = RegKey;
    if ( v17 )
    {
LABEL_12:
      RegCloseKey(v18);
      LeaveCriticalSection(v14);
      return v17 | 0x80070000;
    }
    RegCloseKey(RegKey);
    StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Types");
    phkResult = 0;
    v17 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x20006u, 0, &phkResult, &dwDisposition);
    if ( v17 )
      goto LABEL_14;
    RegCloseKey(phkResult);
    v19 = SetRegDword(hKey, L"Direction", a5 != 0);
    v18 = hKey;
    v17 = v19;
    if ( v19 )
      goto LABEL_12;
    v20 = SetRegDword(hKey, L"IsRendered", a4 != 0);
    v18 = hKey;
    v17 = v20;
    if ( v20 )
      goto LABEL_12;
    v21 = SetRegDword(hKey, L"AllowedZero", a6 != 0);
    v18 = hKey;
    v17 = v21;
    if ( v21 )
      goto LABEL_12;
    v17 = SetRegDword(hKey, L"AllowedMany", a7 != 0);
    if ( v17 )
      goto LABEL_14;
    if ( !memcmp_0(&GUID_NULL, Buf2, 0x10u) )
    {
      v23 = DeleteRegValue(hKey, L"ConnectsToFilter");
      v24 = (v23 & 0xFFFFFFFD) == 0;
    }
    else
    {
      v22 = hKey;
      rguid = *Buf2;
      StringFromGUID2(&rguid, v32, 39);
      v23 = SetRegString(v22, L"ConnectsToFilter", v32);
      v24 = v23 == 0;
    }
    v17 = v23;
    if ( !v24 )
      goto LABEL_14;
    if ( a9 && *a9 )
    {
      v25 = SetRegString(hKey, L"ConnectsToPin", a9);
      v26 = v25 == 0;
    }
    else
    {
      v25 = DeleteRegValue(hKey, L"ConnectsToPin");
      v26 = (v25 & 0xFFFFFFFD) == 0;
    }
    v17 = v25;
    if ( !v26 )
    {
LABEL_14:
      v18 = hKey;
      goto LABEL_12;
    }
    RegCloseKey(hKey);
    LeaveCriticalSection(v14);
    return 0;
  }
  else
  {
    LeaveCriticalSection(v14);
    return 2147746802LL;
  }
}

```

## disassembly

```asm
0x180067980  push    rbp
0x180067982  push    rbx
0x180067983  push    rsi
0x180067984  push    rdi
0x180067985  push    r13
0x180067987  push    r14
0x180067989  push    r15
0x18006798b  lea     rbp, [rsp-240h]
0x180067993  sub     rsp, 340h
0x18006799a  mov     rax, cs:__security_cookie
0x1800679a1  xor     rax, rsp
0x1800679a4  mov     [rbp+270h+var_40], rax
0x1800679ab  mov     r15, [rbp+270h+Buf2]
0x1800679b2  xor     ebx, ebx
0x1800679b4  mov     rsi, [rbp+270h+arg_40]
0x1800679bb  mov     r13d, r9d
0x1800679be  mov     qword ptr [rsp+370h+rguid.Data1], r8
0x1800679c3  mov     r14, rdx
0x1800679c6  mov     rdi, rcx
0x1800679c9  test    r8, r8
0x1800679cc  jnz     short loc_1800679D8
0x1800679ce  mov     eax, 80004003h
0x1800679d3  jmp     loc_180067DA1
0x1800679d8  mov     [rsp+370h+hKey], rbx
0x1800679dd  mov     [rsp+370h+dwDisposition], ebx
0x1800679e1  test    r13d, r13d
0x1800679e4  jz      short loc_1800679EE
0x1800679e6  cmp     [rbp+270h+arg_20], ebx
0x1800679ec  jnz     short loc_180067A11
0x1800679ee  test    rsi, rsi
0x1800679f1  jz      short loc_1800679F8
0x1800679f3  cmp     [rsi], bx
0x1800679f6  jnz     short loc_180067A1B
0x1800679f8  mov     r8d, 10h; Size
0x1800679fe  lea     rcx, GUID_NULL; Buf1
0x180067a05  mov     rdx, r15; Buf2
0x180067a08  call    memcmp_0
0x180067a0d  test    eax, eax
0x180067a0f  jz      short loc_180067A1B
0x180067a11  mov     eax, 80070057h
0x180067a16  jmp     loc_180067DA1
0x180067a1b  lea     rbx, [rdi-8]
0x180067a1f  lea     rdx, [rdi+28h]
0x180067a23  mov     rax, rbx
0x180067a26  neg     rax
0x180067a29  sbb     rdi, rdi
0x180067a2c  and     rdi, rdx
0x180067a2f  mov     rcx, rdi; lpCriticalSection
0x180067a32  call    cs:__imp_EnterCriticalSection
0x180067a39  nop     dword ptr [rax+rax+00h]
0x180067a3e  call    ?BreakCacheIfNotBuildingCache@CFilterMapper2@@AEAAXXZ; CFilterMapper2::BreakCacheIfNotBuildingCache(void)
0x180067a43  mov     rax, [rbx]
0x180067a46  mov     r9, r14
0x180067a49  xor     r8d, r8d
0x180067a4c  xor     edx, edx
0x180067a4e  mov     rcx, rbx
0x180067a51  mov     rax, [rax+20h]
0x180067a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067a5a  mov     r8d, 27h ; '''; cchMax
0x180067a60  lea     rdx, [rbp+270h+sz]; lpsz
0x180067a64  mov     rcx, r14; rguid
0x180067a67  call    cs:__imp_StringFromGUID2
0x180067a6e  nop     dword ptr [rax+rax+00h]
0x180067a73  lea     rax, [rbp+270h+sz]
0x180067a77  mov     ebx, 104h
0x180067a7c  mov     edx, ebx; unsigned __int64
0x180067a7e  mov     qword ptr [rsp+370h+dwOptions], rax
0x180067a83  lea     r9, aClsid_0; "CLSID"
0x180067a8a  lea     r8, aLsLs_0; "%ls\\%ls"
0x180067a91  lea     rcx, [rbp+270h+SubKey]; Buffer
0x180067a95  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067a9a  lea     rcx, [rbp+270h+SubKey]; lpSubKey
0x180067a9e  call    ?CheckRegKey@@YAHPEBG@Z; CheckRegKey(ushort const *)
0x180067aa3  test    eax, eax
0x180067aa5  jz      loc_180067D8D
0x180067aab  lea     rax, aPins_0; "Pins"
0x180067ab2  mov     edx, ebx; unsigned __int64
0x180067ab4  mov     qword ptr [rsp+370h+samDesired], rax
0x180067ab9  lea     r9, aClsid_0; "CLSID"
0x180067ac0  lea     rax, [rbp+270h+sz]
0x180067ac4  lea     r8, aLsLsLs; "%ls\\%ls\\%ls"
0x180067acb  mov     qword ptr [rsp+370h+dwOptions], rax
0x180067ad0  lea     rcx, [rbp+270h+SubKey]; Buffer
0x180067ad4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067ad9  lea     rcx, [rbp+270h+SubKey]; lpSubKey
0x180067add  call    ?GetRegKey@@YAPEAUHKEY__@@PEBG@Z; GetRegKey(ushort const *)
0x180067ae2  mov     r14, rax
0x180067ae5  test    rax, rax
0x180067ae8  jz      loc_180067D8D
0x180067aee  mov     r9, qword ptr [rsp+370h+rguid.Data1]
0x180067af3  lea     r8, aLs; "%ls"
0x180067afa  mov     edx, ebx; unsigned __int64
0x180067afc  lea     rcx, [rbp+270h+SubKey]; Buffer
0x180067b00  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067b05  lea     rax, [rsp+370h+dwDisposition]
0x180067b0a  xor     r9d, r9d; lpClass
0x180067b0d  mov     [rsp+370h+lpdwDisposition], rax; lpdwDisposition
0x180067b12  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x180067b16  lea     rax, [rsp+370h+hKey]
0x180067b1b  xor     r8d, r8d; Reserved
0x180067b1e  mov     [rsp+370h+phkResult], rax; phkResult
0x180067b23  mov     rcx, r14; hKey
0x180067b26  mov     [rsp+370h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180067b2f  mov     [rsp+370h+samDesired], 20006h; samDesired
0x180067b37  mov     [rsp+370h+dwOptions], 0; dwOptions
0x180067b3f  call    cs:__imp_RegCreateKeyExW
0x180067b46  nop     dword ptr [rax+rax+00h]
0x180067b4b  mov     ebx, eax
0x180067b4d  mov     rcx, r14; hKey
0x180067b50  test    eax, eax
0x180067b52  jz      short loc_180067B7C
0x180067b54  call    cs:__imp_RegCloseKey
0x180067b5b  nop     dword ptr [rax+rax+00h]
0x180067b60  mov     rcx, rdi; lpCriticalSection
0x180067b63  call    cs:__imp_LeaveCriticalSection
0x180067b6a  nop     dword ptr [rax+rax+00h]
0x180067b6f  or      ebx, 80070000h
0x180067b75  mov     eax, ebx
0x180067b77  jmp     loc_180067DA1
0x180067b7c  call    cs:__imp_RegCloseKey
0x180067b83  nop     dword ptr [rax+rax+00h]
0x180067b88  lea     r9, aTypes; "Types"
0x180067b8f  mov     edx, 104h; unsigned __int64
0x180067b94  lea     r8, aLs; "%ls"
0x180067b9b  lea     rcx, [rbp+270h+SubKey]; Buffer
0x180067b9f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067ba4  mov     rcx, [rsp+370h+hKey]; hKey
0x180067ba9  lea     rax, [rsp+370h+dwDisposition]
0x180067bae  mov     [rsp+370h+lpdwDisposition], rax; lpdwDisposition
0x180067bb3  lea     rdx, [rbp+270h+SubKey]; lpSubKey
0x180067bb7  xor     r14d, r14d
0x180067bba  lea     rax, [rsp+370h+var_310]
0x180067bbf  mov     [rsp+370h+phkResult], rax; phkResult
0x180067bc4  xor     r9d, r9d; lpClass
0x180067bc7  mov     [rsp+370h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180067bcc  xor     r8d, r8d; Reserved
0x180067bcf  mov     [rsp+370h+samDesired], 20006h; samDesired
0x180067bd7  mov     [rsp+370h+dwOptions], r14d; dwOptions
0x180067bdc  mov     [rsp+370h+var_310], r14
0x180067be1  call    cs:__imp_RegCreateKeyExW
0x180067be8  nop     dword ptr [rax+rax+00h]
0x180067bed  mov     ebx, eax
0x180067bef  test    eax, eax
0x180067bf1  jz      short loc_180067BFD
0x180067bf3  mov     rcx, [rsp+370h+hKey]
0x180067bf8  jmp     loc_180067B54
0x180067bfd  mov     rcx, [rsp+370h+var_310]; hKey
0x180067c02  call    cs:__imp_RegCloseKey
0x180067c09  nop     dword ptr [rax+rax+00h]
0x180067c0e  cmp     [rbp+270h+arg_20], r14d
0x180067c15  lea     rdx, aDirection; "Direction"
0x180067c1c  mov     rcx, [rsp+370h+hKey]; hKey
0x180067c21  mov     r8d, r14d
0x180067c24  setnz   r8b; unsigned int
0x180067c28  call    ?SetRegDword@@YAJPEAUHKEY__@@PEBGK@Z; SetRegDword(HKEY__ *,ushort const *,ulong)
0x180067c2d  mov     rcx, [rsp+370h+hKey]; hKey
0x180067c32  mov     ebx, eax
0x180067c34  test    eax, eax
0x180067c36  jnz     loc_180067B54
0x180067c3c  mov     r8d, r14d
0x180067c3f  lea     rdx, aIsrendered; "IsRendered"
0x180067c46  test    r13d, r13d
0x180067c49  setnz   r8b; unsigned int
0x180067c4d  call    ?SetRegDword@@YAJPEAUHKEY__@@PEBGK@Z; SetRegDword(HKEY__ *,ushort const *,ulong)
0x180067c52  mov     rcx, [rsp+370h+hKey]; hKey
0x180067c57  mov     ebx, eax
0x180067c59  test    eax, eax
0x180067c5b  jnz     loc_180067B54
0x180067c61  cmp     [rbp+270h+arg_28], r14d
0x180067c68  lea     rdx, aAllowedzero; "AllowedZero"
0x180067c6f  mov     r8d, r14d
0x180067c72  setnz   r8b; unsigned int
0x180067c76  call    ?SetRegDword@@YAJPEAUHKEY__@@PEBGK@Z; SetRegDword(HKEY__ *,ushort const *,ulong)
0x180067c7b  mov     rcx, [rsp+370h+hKey]; hKey
0x180067c80  mov     ebx, eax
0x180067c82  test    eax, eax
0x180067c84  jnz     loc_180067B54
0x180067c8a  cmp     [rbp+270h+arg_30], r14d
0x180067c91  lea     rdx, aAllowedmany; "AllowedMany"
0x180067c98  mov     r8d, r14d
0x180067c9b  setnz   r8b; unsigned int
0x180067c9f  call    ?SetRegDword@@YAJPEAUHKEY__@@PEBGK@Z; SetRegDword(HKEY__ *,ushort const *,ulong)
0x180067ca4  mov     ebx, eax
0x180067ca6  test    eax, eax
0x180067ca8  jnz     loc_180067BF3
0x180067cae  lea     r8d, [rax+10h]; Size
0x180067cb2  mov     rdx, r15; Buf2
0x180067cb5  lea     rcx, GUID_NULL; Buf1
0x180067cbc  call    memcmp_0
0x180067cc1  test    eax, eax
0x180067cc3  jz      loc_180067D5D
0x180067cc9  movups  xmm0, xmmword ptr [r15]
0x180067ccd  mov     rbx, [rsp+370h+hKey]
0x180067cd2  lea     rdx, [rbp+270h+var_2A0]; lpsz
0x180067cd6  mov     r8d, 27h ; '''; cchMax
0x180067cdc  lea     rcx, [rsp+370h+rguid]; rguid
0x180067ce1  movdqu  xmmword ptr [rsp+370h+rguid.Data1], xmm0
0x180067ce7  call    cs:__imp_StringFromGUID2
0x180067cee  nop     dword ptr [rax+rax+00h]
0x180067cf3  lea     r8, [rbp+270h+var_2A0]; unsigned __int16 *
0x180067cf7  mov     rcx, rbx; hKey
0x180067cfa  lea     rdx, aConnectstofilt; "ConnectsToFilter"
0x180067d01  call    ?SetRegString@@YAJPEAUHKEY__@@PEBG1@Z; SetRegString(HKEY__ *,ushort const *,ushort const *)
0x180067d06  test    eax, eax
0x180067d08  mov     ebx, eax
0x180067d0a  jnz     loc_180067BF3
0x180067d10  test    rsi, rsi
0x180067d13  jz      short loc_180067D75
0x180067d15  cmp     [rsi], r14w
0x180067d19  jz      short loc_180067D75
0x180067d1b  mov     rcx, [rsp+370h+hKey]; hKey
0x180067d20  lea     rdx, aConnectstopin; "ConnectsToPin"
0x180067d27  mov     r8, rsi; unsigned __int16 *
0x180067d2a  call    ?SetRegString@@YAJPEAUHKEY__@@PEBG1@Z; SetRegString(HKEY__ *,ushort const *,ushort const *)
0x180067d2f  test    eax, eax
0x180067d31  mov     ebx, eax
0x180067d33  jnz     loc_180067BF3
0x180067d39  mov     rcx, [rsp+370h+hKey]; hKey
0x180067d3e  call    cs:__imp_RegCloseKey
0x180067d45  nop     dword ptr [rax+rax+00h]
0x180067d4a  mov     rcx, rdi; lpCriticalSection
0x180067d4d  call    cs:__imp_LeaveCriticalSection
0x180067d54  nop     dword ptr [rax+rax+00h]
0x180067d59  xor     eax, eax
0x180067d5b  jmp     short loc_180067DA1
0x180067d5d  mov     rcx, [rsp+370h+hKey]; hKey
0x180067d62  lea     rdx, aConnectstofilt; "ConnectsToFilter"
0x180067d69  call    ?DeleteRegValue@@YAJPEAUHKEY__@@PEBG@Z; DeleteRegValue(HKEY__ *,ushort const *)
0x180067d6e  test    eax, 0FFFFFFFDh
0x180067d73  jmp     short loc_180067D08
0x180067d75  mov     rcx, [rsp+370h+hKey]; hKey
0x180067d7a  lea     rdx, aConnectstopin; "ConnectsToPin"
0x180067d81  call    ?DeleteRegValue@@YAJPEAUHKEY__@@PEBG@Z; DeleteRegValue(HKEY__ *,ushort const *)
0x180067d86  test    eax, 0FFFFFFFDh
0x180067d8b  jmp     short loc_180067D31
0x180067d8d  mov     rcx, rdi; lpCriticalSection
0x180067d90  call    cs:__imp_LeaveCriticalSection
0x180067d97  nop     dword ptr [rax+rax+00h]
0x180067d9c  mov     eax, 800403F2h
0x180067da1  mov     rcx, [rbp+270h+var_40]
0x180067da8  xor     rcx, rsp; StackCookie
0x180067dab  call    __security_check_cookie
0x180067db0  add     rsp, 340h
0x180067db7  pop     r15
0x180067db9  pop     r14
0x180067dbb  pop     r13
0x180067dbd  pop     rdi
0x180067dbe  pop     rsi
0x180067dbf  pop     rbx
0x180067dc0  pop     rbp
0x180067dc1  retn
```
