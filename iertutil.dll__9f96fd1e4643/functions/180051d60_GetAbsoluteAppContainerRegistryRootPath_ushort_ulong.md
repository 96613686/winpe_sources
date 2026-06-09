# GetAbsoluteAppContainerRegistryRootPath(ushort *,ulong)

- ea: `0x180051d60`
- end: `0x180051f1e`
- name: `?GetAbsoluteAppContainerRegistryRootPath@@YAXPEAGK@Z`
- size: `446`
- prototype: `void __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180051bb0`

## callees

- `0x180021d38`
- `0x180031670`
- `0x180051d60`
- `0x18005e8e4`
- `0x180083be6`
- `0x180083c10`
- `0x180085010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051db4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180051db4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051d9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180051d9d`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180051e52`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrStrW` at `0x180051e52`

## string_xrefs

- `0x180051e16`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x180051e87`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x180051ea4`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x180051ec4`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x180051ee4`: `onecoreuap\inetcore\iertutil\ieconfiguration.cpp`
- `0x180051d8b`: `profapi.dll`

## pseudocode

```c
void __fastcall GetAbsoluteAppContainerRegistryRootPath(unsigned __int16 *a1, unsigned int a2)
{
  unsigned __int64 v2; // rsi
  int v4; // ebx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  int v7; // eax
  PWSTR v8; // rax
  int v9; // eax
  int v10; // [rsp+20h] [rbp-238h]
  int v11; // [rsp+20h] [rbp-238h]
  wchar_t String1[264]; // [rsp+30h] [rbp-228h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+258h] [rbp+0h]

  v2 = a2;
  v4 = -2147467259;
  Library = LoadLibraryExW(L"profapi.dll", 0, 0x800u);
  if ( !Library
    || (ProcAddress = GetProcAddress(Library, (LPCSTR)0x70)) == 0
    || (v4 = ((__int64 (__fastcall *)(wchar_t *, __int64))ProcAddress)(String1, 260), v4 < 0) )
  {
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xA66,
      (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
      (const char *)(unsigned int)v4,
      v10);
  }
  if ( !wcsncmp_0(String1, L"HKCU", 4u) )
  {
    v7 = StringCchCopyW(a1, (unsigned int)v2, String1);
    if ( v7 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xA6A,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)(unsigned int)v7,
        v10);
  }
  else
  {
    if ( wcsncmp_0(String1, L"S-", 2u) )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xA7C,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)0x8000FFFFLL,
        v10);
    v8 = StrStrW(String1, L"\\");
    if ( !v8 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xA76,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)0x80004005LL,
        v10);
    v11 = (int)v8;
    v9 = StringCchPrintfW(a1, v2, L"%s%s", L"HKCU");
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xA72,
        (unsigned int)"onecoreuap\\inetcore\\iertutil\\ieconfiguration.cpp",
        (const char *)(unsigned int)v9,
        v11);
  }
}

```

## disassembly

```asm
0x180051d60  mov     [rsp+arg_10], rbx
0x180051d65  mov     [rsp+arg_18], rsi
0x180051d6a  push    rdi
0x180051d6b  sub     rsp, 250h
0x180051d72  mov     rax, cs:__security_cookie
0x180051d79  xor     rax, rsp
0x180051d7c  mov     [rsp+258h+var_18], rax
0x180051d84  mov     esi, edx
0x180051d86  mov     rdi, rcx
0x180051d89  xor     edx, edx; hFile
0x180051d8b  lea     rcx, aProfapiDll_0; "profapi.dll"
0x180051d92  mov     r8d, 800h; dwFlags
0x180051d98  mov     ebx, 80004005h
0x180051d9d  call    cs:__imp_LoadLibraryExW
0x180051da3  test    rax, rax
0x180051da6  jz      loc_180051EDC
0x180051dac  mov     edx, 70h ; 'p'; lpProcName
0x180051db1  mov     rcx, rax; hModule
0x180051db4  call    cs:__imp_GetProcAddress
0x180051dba  test    rax, rax
0x180051dbd  jz      loc_180051EDC
0x180051dc3  mov     edx, 104h
0x180051dc8  lea     rcx, [rsp+258h+String1]
0x180051dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051dd2  mov     ebx, eax
0x180051dd4  test    eax, eax
0x180051dd6  js      loc_180051EDC
0x180051ddc  mov     r8d, 4; MaxCount
0x180051de2  lea     rdx, aHkcu_0; "HKCU"
0x180051de9  lea     rcx, [rsp+258h+String1]; String1
0x180051dee  call    wcsncmp_0
0x180051df3  test    eax, eax
0x180051df5  jnz     short loc_180051E2B
0x180051df7  mov     edx, esi; unsigned __int64
0x180051df9  lea     r8, [rsp+258h+String1]; unsigned __int16 *
0x180051dfe  mov     rcx, rdi; unsigned __int16 *
0x180051e01  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180051e06  test    eax, eax
0x180051e08  jns     loc_180051EF9
0x180051e0e  mov     rcx, [rsp+258h]; this
0x180051e16  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180051e1d  mov     r9d, eax; char *
0x180051e20  mov     edx, 0A6Ah; void *
0x180051e25  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180051e2b  mov     r8d, 2; MaxCount
0x180051e31  lea     rdx, aS_14; "S-"
0x180051e38  lea     rcx, [rsp+258h+String1]; String1
0x180051e3d  call    wcsncmp_0
0x180051e42  test    eax, eax
0x180051e44  jnz     short loc_180051EBC
0x180051e46  lea     rdx, Delimiter; "\\"
0x180051e4d  lea     rcx, [rsp+258h+String1]; pszFirst
0x180051e52  call    cs:__imp_StrStrW
0x180051e58  test    rax, rax
0x180051e5b  jz      short loc_180051E9C
0x180051e5d  mov     rdx, rsi; unsigned __int64
0x180051e60  mov     qword ptr [rsp+258h+var_238], rax; int
0x180051e65  lea     r9, aHkcu_0; "HKCU"
0x180051e6c  mov     rcx, rdi; unsigned __int16 *
0x180051e6f  lea     r8, aSS_1; "%s%s"
0x180051e76  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180051e7b  test    eax, eax
0x180051e7d  jns     short loc_180051EF9
0x180051e7f  mov     rcx, [rsp+258h]; this
0x180051e87  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180051e8e  mov     r9d, eax; char *
0x180051e91  mov     edx, 0A72h; void *
0x180051e96  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180051e9c  mov     rcx, [rsp+258h]; this
0x180051ea4  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180051eab  mov     r9d, 80004005h; char *
0x180051eb1  mov     edx, 0A76h; void *
0x180051eb6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180051ebc  mov     rcx, [rsp+258h]; this
0x180051ec4  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180051ecb  mov     r9d, 8000FFFFh; char *
0x180051ed1  mov     edx, 0A7Ch; void *
0x180051ed6  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180051edc  mov     rcx, [rsp+258h]; this
0x180051ee4  lea     r8, aOnecoreuapInet_11; "onecoreuap\\inetcore\\iertutil\\ieconfi"...
0x180051eeb  mov     r9d, ebx; char *
0x180051eee  mov     edx, 0A66h; void *
0x180051ef3  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180051ef9  mov     rcx, [rsp+258h+var_18]
0x180051f01  xor     rcx, rsp; StackCookie
0x180051f04  call    __security_check_cookie
0x180051f09  lea     r11, [rsp+258h+var_8]
0x180051f11  mov     rbx, [r11+20h]
0x180051f15  mov     rsi, [r11+28h]
0x180051f19  mov     rsp, r11
0x180051f1c  pop     rdi
0x180051f1d  retn
```
