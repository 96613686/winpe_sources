# CRegistry::GetAllRegistryVals(ushort (*)[384],_GUID *,ulong *)

- ea: `0x180044d5c`
- end: `0x180044fc9`
- name: `?GetAllRegistryVals@CRegistry@@QEAAJPEAY0BIA@GPEAU_GUID@@PEAK@Z`
- size: `621`
- prototype: `__int64 __fastcall(CRegistry *__hidden this, unsigned __int16 (*)[384], struct _GUID *, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180044960`
- `0x180045cac`

## callees

- `0x180029414`
- `0x180029560`
- `0x180044d5c`
- `0x18004535c`
- `0x18007e700`

## import_xrefs

- `msvcrt!_wcslwr` at `0x180044ec5`
- `msvcrt!_wcslwr` at `0x180044ec5`
- `ADVAPI32!RegEnumValueW` at `0x180044e70`
- `ADVAPI32!RegEnumValueW` at `0x180044f32`
- `ADVAPI32!RegEnumValueW` at `0x180044e70`
- `ADVAPI32!RegEnumValueW` at `0x180044f32`
- `ADVAPI32!RegEnumKeyExW` at `0x180044dfa`
- `ADVAPI32!RegEnumKeyExW` at `0x180044dfa`
- `ADVAPI32!RegCloseKey` at `0x180044f51`
- `ADVAPI32!RegCloseKey` at `0x180044f51`
- `ole32!CLSIDFromString` at `0x180044ed9`
- `ole32!CLSIDFromString` at `0x180044ed9`

## string_xrefs

- `0x180044f92`: `<CRegistry::GetAllRegistryVals|Trace|HR> `

## pseudocode

```c
__int64 __fastcall CRegistry::GetAllRegistryVals(
        CRegistry *this,
        unsigned __int16 (*a2)[384],
        struct _GUID *a3,
        unsigned int *a4)
{
  HKEY *v4; // r13
  HKEY v5; // rcx
  DWORD v6; // r12d
  unsigned int v7; // esi
  DWORD v8; // edx
  unsigned int v10; // ebx
  LSTATUS v11; // eax
  DWORD v12; // r15d
  unsigned __int16 *v13; // r13
  struct _GUID *v14; // r12
  __int64 result; // rax
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchValueName; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD Type; // [rsp+4Ch] [rbp-B4h] BYREF
  DWORD v20; // [rsp+50h] [rbp-B0h]
  HKEY hKey; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME ftLastWriteTime; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v23; // [rsp+68h] [rbp-98h]
  struct _GUID *v24; // [rsp+70h] [rbp-90h]
  CRegistry *v25; // [rsp+78h] [rbp-88h]
  OLECHAR Data[40]; // [rsp+80h] [rbp-80h] BYREF
  __int16 v27; // [rsp+D0h] [rbp-30h]
  WCHAR Name[272]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR ValueName[272]; // [rsp+300h] [rbp+200h] BYREF

  v23 = (unsigned __int16 *)a2;
  v25 = this;
  v4 = (HKEY *)this;
  hKey = 0;
  v5 = *(HKEY *)this;
  v6 = 0;
  v20 = 0;
  v7 = 0;
  ftLastWriteTime = 0;
  v8 = 0;
  cchValueName = 270;
  v24 = a3;
  Type = 1;
  cbData = 82;
  while ( 1 )
  {
    cchName = 270;
    v10 = RegEnumKeyExW(v5, v8, Name, &cchName, 0, 0, 0, &ftLastWriteTime);
    if ( v10 )
      break;
    if ( v7 >= *a4 )
      break;
    v10 = CRegistry::OpenSchemeKey(v4, Name, &hKey);
    if ( v10 )
      break;
    cchValueName = 270;
    cbData = 82;
    v11 = RegEnumValueW(hKey, 0, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
    v12 = 0;
    v27 = 0;
    v10 = v11;
    if ( !v11 )
    {
      v13 = v23;
      v14 = v24;
      do
      {
        StringCchPrintfW(&v13[384 * v7], 0x180u, L"%ls:%ls", Name, ValueName);
        _wcslwr(&v13[384 * v7]);
        ++v12;
        if ( CLSIDFromString(Data, &v14[v7]) )
          --*a4;
        else
          ++v7;
        cchValueName = 270;
        cbData = 82;
        v10 = RegEnumValueW(hKey, v12, ValueName, &cchValueName, 0, &Type, (LPBYTE)Data, &cbData);
      }
      while ( !v10 );
      v6 = v20;
      v4 = (HKEY *)v25;
    }
    RegCloseKey(hKey);
    if ( v10 != 259 )
      break;
    v5 = *v4;
    v20 = ++v6;
    v8 = v6;
  }
  result = 0;
  if ( v10 != 259 )
    result = v10;
  if ( (bidGblFlags & 2) != 0 )
    return bidTraceHR(off_1800C83A8[0], 586761, L"<CRegistry::GetAllRegistryVals|Trace|HR> ", (unsigned int)result);
  return result;
}

```

## disassembly

```asm
0x180044d5c  push    rbp
0x180044d5e  push    rbx
0x180044d5f  push    rsi
0x180044d60  push    rdi
0x180044d61  push    r12
0x180044d63  push    r13
0x180044d65  push    r14
0x180044d67  push    r15
0x180044d69  lea     rbp, [rsp-438h]
0x180044d71  sub     rsp, 538h
0x180044d78  mov     rax, cs:__security_cookie
0x180044d7f  xor     rax, rsp
0x180044d82  mov     [rbp+470h+var_50], rax
0x180044d89  xor     edi, edi
0x180044d8b  mov     [rsp+570h+var_508], rdx
0x180044d90  mov     r15d, 10Eh
0x180044d96  mov     [rsp+570h+var_4F8], rcx
0x180044d9b  mov     r13, rcx
0x180044d9e  mov     [rsp+570h+hKey], rdi
0x180044da3  mov     rcx, [rcx]; hKey
0x180044da6  mov     r12d, edi
0x180044da9  mov     [rsp+570h+var_520], edi
0x180044dad  mov     esi, edi
0x180044daf  mov     qword ptr [rsp+570h+ftLastWriteTime.dwLowDateTime], rdi
0x180044db4  xor     edx, edx; dwIndex
0x180044db6  mov     [rsp+570h+cchValueName], r15d
0x180044dbb  mov     r14, r9
0x180044dbe  mov     [rsp+570h+var_500], r8
0x180044dc3  mov     [rsp+570h+Type], 1
0x180044dcb  mov     [rsp+570h+cbData], 52h ; 'R'
0x180044dd3  lea     rax, [rsp+570h+ftLastWriteTime]
0x180044dd8  mov     [rsp+570h+cchName], r15d
0x180044ddd  mov     [rsp+570h+lpftLastWriteTime], rax; lpftLastWriteTime
0x180044de2  lea     r9, [rsp+570h+cchName]; lpcchName
0x180044de7  mov     [rsp+570h+lpcchClass], rdi; lpcchClass
0x180044dec  lea     r8, [rbp+470h+Name]; lpName
0x180044df0  mov     [rsp+570h+lpClass], rdi; lpClass
0x180044df5  mov     [rsp+570h+lpReserved], rdi; lpReserved
0x180044dfa  call    cs:__imp_RegEnumKeyExW
0x180044e00  mov     ebx, eax
0x180044e02  test    eax, eax
0x180044e04  jnz     loc_180044F77
0x180044e0a  cmp     esi, [r14]
0x180044e0d  jnb     loc_180044F77
0x180044e13  lea     r8, [rsp+570h+hKey]; HKEY *
0x180044e18  mov     rcx, r13; this
0x180044e1b  lea     rdx, [rbp+470h+Name]; unsigned __int16 *
0x180044e1f  call    ?OpenSchemeKey@CRegistry@@AEAAJPEBGPEAPEAUHKEY__@@@Z; CRegistry::OpenSchemeKey(ushort const *,HKEY__ * *)
0x180044e24  mov     ebx, eax
0x180044e26  test    eax, eax
0x180044e28  jnz     loc_180044F77
0x180044e2e  mov     rcx, [rsp+570h+hKey]; hKey
0x180044e33  lea     rax, [rsp+570h+cbData]
0x180044e38  mov     [rsp+570h+lpftLastWriteTime], rax; lpcbData
0x180044e3d  lea     r9, [rsp+570h+cchValueName]; lpcchValueName
0x180044e42  lea     rax, [rbp+470h+Data]
0x180044e46  mov     [rsp+570h+cchValueName], r15d
0x180044e4b  mov     [rsp+570h+lpcchClass], rax; lpData
0x180044e50  lea     r8, [rbp+470h+ValueName]; lpValueName
0x180044e57  lea     rax, [rsp+570h+Type]
0x180044e5c  mov     [rsp+570h+cbData], 52h ; 'R'
0x180044e64  mov     [rsp+570h+lpClass], rax; lpType
0x180044e69  xor     edx, edx; dwIndex
0x180044e6b  mov     [rsp+570h+lpReserved], rdi; lpReserved
0x180044e70  call    cs:__imp_RegEnumValueW
0x180044e76  mov     r15d, edi
0x180044e79  mov     [rbp+470h+var_4A0], di
0x180044e7d  mov     ebx, eax
0x180044e7f  test    eax, eax
0x180044e81  jnz     loc_180044F4C
0x180044e87  mov     r13, [rsp+570h+var_508]
0x180044e8c  mov     r12, [rsp+570h+var_500]
0x180044e91  lea     rax, [rbp+470h+ValueName]
0x180044e98  mov     edi, esi
0x180044e9a  lea     r9, [rbp+470h+Name]
0x180044e9e  mov     [rsp+570h+lpReserved], rax
0x180044ea3  lea     r8, aLsLs_0; "%ls:%ls"
0x180044eaa  mov     edx, 180h; unsigned __int64
0x180044eaf  lea     rbx, [rdi+rdi*2]
0x180044eb3  shl     rbx, 8
0x180044eb7  add     rbx, r13
0x180044eba  mov     rcx, rbx; unsigned __int16 *
0x180044ebd  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180044ec2  mov     rcx, rbx; String
0x180044ec5  call    cs:__imp__wcslwr
0x180044ecb  add     rdi, rdi
0x180044ece  lea     rcx, [rbp+470h+Data]; lpsz
0x180044ed2  inc     r15d
0x180044ed5  lea     rdx, [r12+rdi*8]; pclsid
0x180044ed9  call    cs:__imp_CLSIDFromString
0x180044edf  xor     edi, edi
0x180044ee1  test    eax, eax
0x180044ee3  jz      short loc_180044EEA
0x180044ee5  dec     dword ptr [r14]
0x180044ee8  jmp     short loc_180044EEC
0x180044eea  inc     esi
0x180044eec  mov     rcx, [rsp+570h+hKey]; hKey
0x180044ef1  lea     rax, [rsp+570h+cbData]
0x180044ef6  mov     [rsp+570h+lpftLastWriteTime], rax; lpcbData
0x180044efb  lea     r9, [rsp+570h+cchValueName]; lpcchValueName
0x180044f00  lea     rax, [rbp+470h+Data]
0x180044f04  mov     [rsp+570h+cchValueName], 10Eh
0x180044f0c  mov     [rsp+570h+lpcchClass], rax; lpData
0x180044f11  lea     r8, [rbp+470h+ValueName]; lpValueName
0x180044f18  lea     rax, [rsp+570h+Type]
0x180044f1d  mov     [rsp+570h+cbData], 52h ; 'R'
0x180044f25  mov     [rsp+570h+lpClass], rax; lpType
0x180044f2a  mov     edx, r15d; dwIndex
0x180044f2d  mov     [rsp+570h+lpReserved], rdi; lpReserved
0x180044f32  call    cs:__imp_RegEnumValueW
0x180044f38  mov     ebx, eax
0x180044f3a  test    eax, eax
0x180044f3c  jz      loc_180044E91
0x180044f42  mov     r12d, [rsp+570h+var_520]
0x180044f47  mov     r13, [rsp+570h+var_4F8]
0x180044f4c  mov     rcx, [rsp+570h+hKey]; hKey
0x180044f51  call    cs:__imp_RegCloseKey
0x180044f57  cmp     ebx, 103h
0x180044f5d  jnz     short loc_180044F77
0x180044f5f  mov     rcx, [r13+0]
0x180044f63  lea     r15d, [rbx+0Bh]
0x180044f67  inc     r12d
0x180044f6a  mov     [rsp+570h+var_520], r12d
0x180044f6f  mov     edx, r12d
0x180044f72  jmp     loc_180044DD3
0x180044f77  cmp     ebx, 103h
0x180044f7d  mov     eax, edi
0x180044f7f  cmovnz  eax, ebx
0x180044f82  test    byte ptr cs:_bidGblFlags, 2
0x180044f89  jz      short loc_180044FA6
0x180044f8b  mov     rcx, cs:off_1800C83A8; "enduser\\databaseaccess\\src\\mdac\\ole"...
0x180044f92  lea     r8, aCregistryGetal; "<CRegistry::GetAllRegistryVals|Trace|HR"...
0x180044f99  mov     r9d, eax
0x180044f9c  mov     edx, 8F409h
0x180044fa1  call    _bidTraceHR
0x180044fa6  mov     rcx, [rbp+470h+var_50]
0x180044fad  xor     rcx, rsp; StackCookie
0x180044fb0  call    __security_check_cookie
0x180044fb5  add     rsp, 538h
0x180044fbc  pop     r15
0x180044fbe  pop     r14
0x180044fc0  pop     r13
0x180044fc2  pop     r12
0x180044fc4  pop     rdi
0x180044fc5  pop     rsi
0x180044fc6  pop     rbx
0x180044fc7  pop     rbp
0x180044fc8  retn
```
