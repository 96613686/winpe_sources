# GetInstallRoot(VERSION_ARCHITECTURE)

- ea: `0x180003890`
- end: `0x180003d44`
- name: `?GetInstallRoot@@YAPEAGW4VERSION_ARCHITECTURE@@@Z`
- size: `1204`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x180002710`
- `0x1800297ac`
- `0x18002dfb4`
- `0x18003145c`

## callees

- `0x180003070`
- `0x180003740`
- `0x180003840`
- `0x180003890`
- `0x180004d50`
- `0x18000c1a8`
- `0x18000d264`
- `0x18000d614`
- `0x180041ac0`

## import_xrefs

- `KERNEL32!GetFullPathNameW` at `0x180003abb`
- `KERNEL32!GetFullPathNameW` at `0x180003b13`
- `KERNEL32!GetFullPathNameW` at `0x180003c8e`
- `KERNEL32!GetFullPathNameW` at `0x180003abb`
- `KERNEL32!GetFullPathNameW` at `0x180003b13`
- `KERNEL32!GetFullPathNameW` at `0x180003c8e`
- `KERNEL32!GetLastError` at `0x18000393f`
- `KERNEL32!GetLastError` at `0x180003a21`
- `KERNEL32!GetLastError` at `0x180003adb`
- `KERNEL32!GetLastError` at `0x180003b67`
- `KERNEL32!GetLastError` at `0x180003be4`
- `KERNEL32!GetLastError` at `0x180003c00`
- `KERNEL32!GetLastError` at `0x18000393f`
- `KERNEL32!GetLastError` at `0x180003a21`
- `KERNEL32!GetLastError` at `0x180003adb`
- `KERNEL32!GetLastError` at `0x180003b67`
- `KERNEL32!GetLastError` at `0x180003be4`
- `KERNEL32!GetLastError` at `0x180003c00`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000391c`
- `KERNEL32!GetEnvironmentVariableW` at `0x180003d0b`
- `KERNEL32!GetEnvironmentVariableW` at `0x18000391c`
- `KERNEL32!GetEnvironmentVariableW` at `0x180003d0b`
- `KERNEL32!GetModuleFileNameW` at `0x180003b90`
- `KERNEL32!GetModuleFileNameW` at `0x180003c66`
- `KERNEL32!GetModuleFileNameW` at `0x180003b90`
- `KERNEL32!GetModuleFileNameW` at `0x180003c66`
- `KERNEL32!GetFileAttributesW` at `0x180003bbe`
- `KERNEL32!GetFileAttributesW` at `0x180003bbe`
- `KERNEL32!SetLastError` at `0x180003b74`
- `KERNEL32!SetLastError` at `0x180003bf5`
- `KERNEL32!SetLastError` at `0x180003c10`
- `KERNEL32!SetLastError` at `0x180003b74`
- `KERNEL32!SetLastError` at `0x180003bf5`
- `KERNEL32!SetLastError` at `0x180003c10`
- `ADVAPI32!RegOpenKeyExW` at `0x1800039c4`
- `ADVAPI32!RegOpenKeyExW` at `0x1800039c4`
- `ADVAPI32!RegQueryValueExW` at `0x1800039f5`
- `ADVAPI32!RegQueryValueExW` at `0x180003a70`
- `ADVAPI32!RegQueryValueExW` at `0x1800039f5`
- `ADVAPI32!RegQueryValueExW` at `0x180003a70`
- `ADVAPI32!RegCloseKey` at `0x180003a80`
- `ADVAPI32!RegCloseKey` at `0x180003a80`

## string_xrefs

- `0x1800038fc`: `InstallRoot`
- `0x1800039e9`: `InstallRoot`
- `0x180003a64`: `InstallRoot`
- `0x1800038e6`: `COMPlus_`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
wchar_t *__fastcall GetInstallRoot(int a1)
{
  int v2; // eax
  signed int EnvironmentVariableW; // eax
  DWORD v4; // esi
  unsigned __int64 v5; // rbx
  DWORD LastError; // r14d
  WCHAR *v7; // rbx
  REGSAM v8; // r9d
  int v9; // eax
  unsigned __int64 v10; // rbx
  DWORD v11; // edi
  int v12; // esi
  int v13; // eax
  DWORD FullPathNameW; // eax
  DWORD v15; // r14d
  unsigned __int64 v16; // rdi
  DWORD v17; // r15d
  void *v18; // rdi
  bool v20; // zf
  unsigned __int64 v21; // rdi
  unsigned __int128 v22; // rax
  wchar_t *v23; // rbx
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+40h] [rbp-C0h]
  DWORD Type; // [rsp+48h] [rbp-B8h] BYREF
  DWORD v28; // [rsp+50h] [rbp-B0h]
  int v29; // [rsp+54h] [rbp-ACh]
  wchar_t Destination[64]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer[264]; // [rsp+E0h] [rbp-20h] BYREF
  WCHAR Filename[272]; // [rsp+2F0h] [rbp+1F0h] BYREF
  WCHAR FileName[264]; // [rsp+510h] [rbp+410h] BYREF

  v2 = g_UseLocalRuntime;
  if ( g_UseLocalRuntime == -1 )
  {
    if ( GetModuleFileNameW(g_hShimMod, Filename, 0x104u) - 1 <= 0x102 )
    {
      wcscat_s(Filename, 0x10Bu, L".local");
      if ( GetFileAttributesW(Filename) != -1 )
      {
        g_UseLocalRuntime = 1;
LABEL_57:
        hKey = 0;
        if ( GetModuleFileNameW(g_hShimMod, FileName, 0x104u) - 1 <= 0x102
          && GetFullPathNameW(FileName, 0x104u, Buffer, (LPWSTR *)&hKey) - 1 <= 0x102 )
        {
          v21 = (((char *)hKey - (char *)Buffer) >> 1) + 1;
          v22 = v21 * (unsigned __int128)2uLL;
          if ( !is_mul_ok(v21, 2u) )
            *(_QWORD *)&v22 = -1;
          v23 = (wchar_t *)operator new(v22, *((const struct NoThrow **)&v22 + 1));
          if ( v23 )
          {
            wcsncpy_s(v23, v21, Buffer, ((char *)hKey - (char *)Buffer) >> 1);
            return v23;
          }
        }
        return 0;
      }
    }
    v2 = g_UseLocalRuntime;
    if ( g_UseLocalRuntime == -1 )
    {
      g_UseLocalRuntime = 0;
      goto LABEL_3;
    }
  }
  if ( v2 )
    goto LABEL_57;
LABEL_3:
  hKey = 0;
  Type = 0;
  cbData = 0;
  wcscpy_s(Destination, 0x40u, L"COMPlus_");
  wcscat_s(Destination, 0x40u, L"InstallRoot");
  EnvironmentVariableW = GetEnvironmentVariableW(Destination, 0, 0);
  v4 = EnvironmentVariableW;
  if ( EnvironmentVariableW )
  {
    v5 = 2LL * EnvironmentVariableW;
    if ( !is_mul_ok(EnvironmentVariableW, 2u) )
      v5 = -1;
    LastError = GetLastError();
    v28 = LastError;
    v29 = 2;
    v7 = (WCHAR *)ClrAllocInProcessHeapBootstrap(0, v5);
    if ( LastError && !GetLastError() )
      SetLastError(LastError);
    if ( v7 )
    {
      GetEnvironmentVariableW(Destination, v7, v4);
      if ( *v7 )
      {
        hKey = (HKEY)v7;
        v26 = 0;
LABEL_25:
        v12 = 1;
        v26 = 1;
        v13 = 1;
        goto LABEL_26;
      }
      operator delete(v7);
    }
  }
  v7 = 0;
  v8 = 131097;
  if ( g_OSVersionInfo.dwMajorVersion > 5 || g_OSVersionInfo.dwMajorVersion == 5 && g_OSVersionInfo.dwMinorVersion )
  {
    v9 = 131609;
    if ( a1 != 1 )
      v9 = 131097;
    v8 = v9;
    if ( (unsigned int)(a1 - 2) <= 1 )
      v8 = v9 | 0x100;
  }
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\.NETFramework", 0, v8, &hKey)
    && !RegQueryValueExW(hKey, L"InstallRoot", 0, &Type, 0, &cbData)
    && Type == 1
    && cbData > 1 )
  {
    v10 = 2LL * (cbData + 1);
    if ( !is_mul_ok(cbData + 1, 2u) )
      v10 = -1;
    v11 = GetLastError();
    v28 = v11;
    v29 = 2;
    v7 = (WCHAR *)ClrAllocInProcessHeapBootstrap(0, v10);
    if ( v11 && !GetLastError() )
      SetLastError(v11);
    if ( v7 )
      RegQueryValueExW(hKey, L"InstallRoot", 0, 0, (LPBYTE)v7, &cbData);
  }
  if ( hKey )
    RegCloseKey(hKey);
  hKey = (HKEY)v7;
  v12 = 0;
  v26 = 0;
  if ( v7 )
    goto LABEL_25;
  v13 = 0;
LABEL_26:
  if ( !v7 )
  {
    v20 = v13 == 0;
LABEL_38:
    if ( !v20 )
      operator delete(v7);
    return 0;
  }
  FullPathNameW = GetFullPathNameW(v7, 0, 0, 0);
  v15 = FullPathNameW;
  if ( !FullPathNameW )
  {
    Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>::~Wrapper<unsigned short *,&void DoNothing<unsigned short *>(unsigned short *),&void DeleteArray<unsigned short>(unsigned short *),0,&int CompareDefault<unsigned short *>(unsigned short *,unsigned short *),2>(&hKey);
    return 0;
  }
  v16 = 2LL * FullPathNameW;
  if ( !is_mul_ok(FullPathNameW, 2u) )
    v16 = -1;
  v17 = GetLastError();
  v28 = v17;
  v29 = 2;
  v18 = ClrAllocInProcessHeapBootstrap(0, v16);
  if ( v17 && !GetLastError() )
    SetLastError(v17);
  if ( !v18 )
  {
LABEL_37:
    v20 = v12 == 0;
    goto LABEL_38;
  }
  if ( v15 < GetFullPathNameW(v7, v15, (LPWSTR)v18, 0) )
  {
    operator delete(v18);
    goto LABEL_37;
  }
  if ( v12 )
    operator delete(v7);
  return (wchar_t *)v18;
}

```

## disassembly

```asm
0x180003890  push    rbp
0x180003892  push    rbx
0x180003893  push    rsi
0x180003894  push    rdi
0x180003895  push    r12
0x180003897  push    r14
0x180003899  push    r15
0x18000389b  lea     rbp, [rsp-630h]
0x1800038a3  sub     rsp, 730h
0x1800038aa  mov     rax, cs:__security_cookie
0x1800038b1  xor     rax, rsp
0x1800038b4  mov     [rbp+660h+var_40], rax
0x1800038bb  mov     edi, ecx
0x1800038bd  xor     r12d, r12d
0x1800038c0  mov     eax, cs:?g_UseLocalRuntime@@3HA; int g_UseLocalRuntime
0x1800038c6  cmp     eax, 0FFFFFFFFh
0x1800038c9  jz      loc_180003B7C
0x1800038cf  test    eax, eax
0x1800038d1  jnz     loc_180003C4D
0x1800038d7  mov     [rsp+760h+hKey], r12
0x1800038dc  mov     [rsp+760h+Type], r12d
0x1800038e1  mov     [rsp+760h+cbData], r12d
0x1800038e6  lea     r8, aComplus; "COMPlus_"
0x1800038ed  mov     edx, 40h ; '@'; SizeInWords
0x1800038f2  lea     rcx, [rsp+760h+Destination]; Destination
0x1800038f7  call    wcscpy_s
0x1800038fc  lea     r8, aInstallroot; "InstallRoot"
0x180003903  mov     edx, 40h ; '@'; SizeInWords
0x180003908  lea     rcx, [rsp+760h+Destination]; Destination
0x18000390d  call    wcscat_s
0x180003912  xor     r8d, r8d; nSize
0x180003915  xor     edx, edx; lpBuffer
0x180003917  lea     rcx, [rsp+760h+Destination]; lpName
0x18000391c  call    cs:__imp_GetEnvironmentVariableW
0x180003922  movsxd  rsi, eax
0x180003925  mov     r15, 0FFFFFFFFFFFFFFFFh
0x18000392c  test    eax, eax
0x18000392e  jz      short loc_180003973
0x180003930  mov     eax, 2
0x180003935  mul     rsi
0x180003938  mov     rbx, rax
0x18000393b  cmovb   rbx, r15
0x18000393f  call    cs:__imp_GetLastError
0x180003945  mov     r14d, eax
0x180003948  mov     [rsp+760h+var_710], eax
0x18000394c  mov     [rsp+760h+var_70C], 2
0x180003954  mov     rdx, rbx; unsigned __int64
0x180003957  xor     ecx, ecx; unsigned int
0x180003959  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x18000395e  mov     rbx, rax
0x180003961  test    r14d, r14d
0x180003964  jnz     loc_180003BE4
0x18000396a  test    rbx, rbx
0x18000396d  jnz     loc_180003D00
0x180003973  mov     rbx, r12
0x180003976  mov     r9d, 20019h
0x18000397c  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMajorVersion, 5; _OSVERSIONINFOW g_OSVersionInfo ...
0x180003983  jbe     loc_180003C1B
0x180003989  mov     eax, 20219h
0x18000398e  cmp     edi, 1
0x180003991  cmovnz  eax, r9d
0x180003995  mov     r9d, eax
0x180003998  lea     eax, [rdi-2]
0x18000399b  mov     ecx, r9d
0x18000399e  bts     ecx, 8
0x1800039a2  cmp     eax, 1
0x1800039a5  cmovbe  r9d, ecx; samDesired
0x1800039a9  lea     rax, [rsp+760h+hKey]
0x1800039ae  mov     [rsp+760h+phkResult], rax; phkResult
0x1800039b3  xor     r8d, r8d; ulOptions
0x1800039b6  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\.NETFramework"
0x1800039bd  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800039c4  call    cs:__imp_RegOpenKeyExW
0x1800039ca  test    eax, eax
0x1800039cc  jnz     loc_180003A76
0x1800039d2  lea     rax, [rsp+760h+cbData]
0x1800039d7  mov     [rsp+760h+lpcbData], rax; lpcbData
0x1800039dc  mov     [rsp+760h+phkResult], r12; lpData
0x1800039e1  lea     r9, [rsp+760h+Type]; lpType
0x1800039e6  xor     r8d, r8d; lpReserved
0x1800039e9  lea     rdx, aInstallroot; "InstallRoot"
0x1800039f0  mov     rcx, [rsp+760h+hKey]; hKey
0x1800039f5  call    cs:__imp_RegQueryValueExW
0x1800039fb  test    eax, eax
0x1800039fd  jnz     short loc_180003A76
0x1800039ff  cmp     [rsp+760h+Type], 1
0x180003a04  jnz     short loc_180003A76
0x180003a06  mov     eax, [rsp+760h+cbData]
0x180003a0a  cmp     eax, 1
0x180003a0d  jbe     short loc_180003A76
0x180003a0f  lea     ecx, [rax+1]
0x180003a12  mov     eax, 2
0x180003a17  mul     rcx
0x180003a1a  mov     rbx, rax
0x180003a1d  cmovb   rbx, r15
0x180003a21  call    cs:__imp_GetLastError
0x180003a27  mov     edi, eax
0x180003a29  mov     [rsp+760h+var_710], eax
0x180003a2d  mov     [rsp+760h+var_70C], 2
0x180003a35  mov     rdx, rbx; unsigned __int64
0x180003a38  xor     ecx, ecx; unsigned int
0x180003a3a  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x180003a3f  mov     rbx, rax
0x180003a42  test    edi, edi
0x180003a44  jnz     loc_180003C00
0x180003a4a  test    rbx, rbx
0x180003a4d  jz      short loc_180003A76
0x180003a4f  lea     rax, [rsp+760h+cbData]
0x180003a54  mov     [rsp+760h+lpcbData], rax; lpcbData
0x180003a59  mov     [rsp+760h+phkResult], rbx; lpData
0x180003a5e  xor     r9d, r9d; lpType
0x180003a61  xor     r8d, r8d; lpReserved
0x180003a64  lea     rdx, aInstallroot; "InstallRoot"
0x180003a6b  mov     rcx, [rsp+760h+hKey]; hKey
0x180003a70  call    cs:__imp_RegQueryValueExW
0x180003a76  mov     rcx, [rsp+760h+hKey]; hKey
0x180003a7b  test    rcx, rcx
0x180003a7e  jz      short loc_180003A86
0x180003a80  call    cs:__imp_RegCloseKey
0x180003a86  mov     [rsp+760h+hKey], rbx
0x180003a8b  mov     esi, r12d
0x180003a8e  mov     [rsp+760h+var_720], r12d
0x180003a93  test    rbx, rbx
0x180003a96  jz      loc_180003C33
0x180003a9c  mov     esi, 1
0x180003aa1  mov     [rsp+760h+var_720], esi
0x180003aa5  mov     eax, esi
0x180003aa7  test    rbx, rbx
0x180003aaa  jz      loc_180003C3B
0x180003ab0  xor     r9d, r9d; lpFilePart
0x180003ab3  xor     r8d, r8d; lpBuffer
0x180003ab6  xor     edx, edx; nBufferLength
0x180003ab8  mov     rcx, rbx; lpFileName
0x180003abb  call    cs:__imp_GetFullPathNameW
0x180003ac1  mov     r14d, eax
0x180003ac4  test    eax, eax
0x180003ac6  jz      loc_180003D33
0x180003acc  mov     eax, 2
0x180003ad1  mul     r14
0x180003ad4  mov     rdi, rax
0x180003ad7  cmovb   rdi, r15
0x180003adb  call    cs:__imp_GetLastError
0x180003ae1  mov     r15d, eax
0x180003ae4  mov     [rsp+760h+var_710], eax
0x180003ae8  mov     [rsp+760h+var_70C], 2
0x180003af0  mov     rdx, rdi; unsigned __int64
0x180003af3  xor     ecx, ecx; unsigned int
0x180003af5  call    ?ClrAllocInProcessHeapBootstrap@@YAPEAXK_K@Z; ClrAllocInProcessHeapBootstrap(ulong,unsigned __int64)
0x180003afa  mov     rdi, rax
0x180003afd  test    r15d, r15d
0x180003b00  jnz     short loc_180003B67
0x180003b02  test    rdi, rdi
0x180003b05  jz      short loc_180003B57
0x180003b07  xor     r9d, r9d; lpFilePart
0x180003b0a  mov     r8, rdi; lpBuffer
0x180003b0d  mov     edx, r14d; nBufferLength
0x180003b10  mov     rcx, rbx; lpFileName
0x180003b13  call    cs:__imp_GetFullPathNameW
0x180003b19  cmp     r14d, eax
0x180003b1c  jb      short loc_180003B4E
0x180003b1e  test    esi, esi
0x180003b20  jz      short loc_180003B2A
0x180003b22  mov     rcx, rbx; void *
0x180003b25  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b2a  mov     rax, rdi
0x180003b2d  mov     rcx, [rbp+660h+var_40]
0x180003b34  xor     rcx, rsp; StackCookie
0x180003b37  call    __security_check_cookie
0x180003b3c  add     rsp, 730h
0x180003b43  pop     r15
0x180003b45  pop     r14
0x180003b47  pop     r12
0x180003b49  pop     rdi
0x180003b4a  pop     rsi
0x180003b4b  pop     rbx
0x180003b4c  pop     rbp
0x180003b4d  retn
0x180003b4e  mov     rcx, rdi; void *
0x180003b51  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b56  nop
0x180003b57  test    esi, esi
0x180003b59  jz      short loc_180003B63
0x180003b5b  mov     rcx, rbx; void *
0x180003b5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003b63  xor     eax, eax
0x180003b65  jmp     short loc_180003B2D
0x180003b67  call    cs:__imp_GetLastError
0x180003b6d  test    eax, eax
0x180003b6f  jnz     short loc_180003B02
0x180003b71  mov     ecx, r15d; dwErrCode
0x180003b74  call    cs:__imp_SetLastError
0x180003b7a  jmp     short loc_180003B02
0x180003b7c  mov     r8d, 104h; nSize
0x180003b82  lea     rdx, [rbp+660h+Filename]; lpFilename
0x180003b89  mov     rcx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; hModule
0x180003b90  call    cs:__imp_GetModuleFileNameW
0x180003b96  dec     eax
0x180003b98  cmp     eax, 102h
0x180003b9d  ja      short loc_180003BC9
0x180003b9f  lea     r8, aLocal; ".local"
0x180003ba6  mov     edx, 10Bh; SizeInWords
0x180003bab  lea     rcx, [rbp+660h+Filename]; Destination
0x180003bb2  call    wcscat_s
0x180003bb7  lea     rcx, [rbp+660h+Filename]; lpFileName
0x180003bbe  call    cs:__imp_GetFileAttributesW
0x180003bc4  cmp     eax, 0FFFFFFFFh
0x180003bc7  jnz     short loc_180003C42
0x180003bc9  mov     eax, cs:?g_UseLocalRuntime@@3HA; int g_UseLocalRuntime
0x180003bcf  cmp     eax, 0FFFFFFFFh
0x180003bd2  jnz     loc_1800038CF
0x180003bd8  mov     cs:?g_UseLocalRuntime@@3HA, r12d; int g_UseLocalRuntime
0x180003bdf  jmp     loc_1800038D7
0x180003be4  call    cs:__imp_GetLastError
0x180003bea  test    eax, eax
0x180003bec  jnz     loc_18000396A
0x180003bf2  mov     ecx, r14d; dwErrCode
0x180003bf5  call    cs:__imp_SetLastError
0x180003bfb  jmp     loc_18000396A
0x180003c00  call    cs:__imp_GetLastError
0x180003c06  test    eax, eax
0x180003c08  jnz     loc_180003A4A
0x180003c0e  mov     ecx, edi; dwErrCode
0x180003c10  call    cs:__imp_SetLastError
0x180003c16  jmp     loc_180003A4A
0x180003c1b  jnz     loc_1800039A9
0x180003c21  cmp     cs:?g_OSVersionInfo@@3U_OSVERSIONINFOW@@A.dwMinorVersion, 0; _OSVERSIONINFOW g_OSVersionInfo ...
0x180003c28  jbe     loc_1800039A9
0x180003c2e  jmp     loc_180003989
0x180003c33  mov     eax, r12d
0x180003c36  jmp     loc_180003AA7
0x180003c3b  test    eax, eax
0x180003c3d  jmp     loc_180003B59
0x180003c42  mov     esi, 1
0x180003c47  mov     cs:?g_UseLocalRuntime@@3HA, esi; int g_UseLocalRuntime
0x180003c4d  mov     [rsp+760h+hKey], r12
0x180003c52  mov     r8d, 104h; nSize
0x180003c58  lea     rdx, [rbp+660h+FileName]; lpFilename
0x180003c5f  mov     rcx, cs:?g_hShimMod@@3PEAUHINSTANCE__@@EA; hModule
0x180003c66  call    cs:__imp_GetModuleFileNameW
0x180003c6c  dec     eax
0x180003c6e  cmp     eax, 102h
0x180003c73  ja      loc_180003B63
0x180003c79  lea     r9, [rsp+760h+hKey]; lpFilePart
0x180003c7e  lea     r8, [rbp+660h+Buffer]; lpBuffer
0x180003c82  mov     edx, 104h; nBufferLength
0x180003c87  lea     rcx, [rbp+660h+FileName]; lpFileName
0x180003c8e  call    cs:__imp_GetFullPathNameW
0x180003c94  dec     eax
0x180003c96  cmp     eax, 102h
0x180003c9b  ja      loc_180003B63
0x180003ca1  lea     rcx, [rbp+660h+Buffer]
0x180003ca5  mov     rdi, [rsp+760h+hKey]
0x180003caa  sub     rdi, rcx
0x180003cad  sar     rdi, 1
0x180003cb0  inc     rdi
0x180003cb3  mov     eax, 2
0x180003cb8  mul     rdi
0x180003cbb  mov     r15, 0FFFFFFFFFFFFFFFFh
0x180003cc2  cmovb   rax, r15
0x180003cc6  mov     rcx, rax; unsigned __int64
0x180003cc9  call    ??2@YAPEAX_KAEBUNoThrow@@@Z; operator new(unsigned __int64,NoThrow const &)
0x180003cce  mov     rbx, rax
0x180003cd1  test    rax, rax
0x180003cd4  jz      loc_180003B63
0x180003cda  lea     rax, [rbp+660h+Buffer]
0x180003cde  mov     r9, [rsp+760h+hKey]
0x180003ce3  sub     r9, rax
0x180003ce6  sar     r9, 1; MaxCount
0x180003ce9  lea     r8, [rbp+660h+Buffer]; Source
0x180003ced  mov     rdx, rdi; SizeInWords
0x180003cf0  mov     rcx, rbx; Destination
0x180003cf3  call    wcsncpy_s
0x180003cf8  mov     rax, rbx
0x180003cfb  jmp     loc_180003B2D
0x180003d00  mov     r8d, esi; nSize
0x180003d03  mov     rdx, rbx; lpBuffer
0x180003d06  lea     rcx, [rsp+760h+Destination]; lpName
0x180003d0b  call    cs:__imp_GetEnvironmentVariableW
0x180003d11  cmp     word ptr [rbx], 0
0x180003d15  jz      short loc_180003D26
0x180003d17  mov     [rsp+760h+hKey], rbx
0x180003d1c  mov     [rsp+760h+var_720], r12d
0x180003d21  jmp     loc_180003A9C
0x180003d26  mov     rcx, rbx; void *
0x180003d29  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003d2e  jmp     loc_180003973
0x180003d33  lea     rcx, [rsp+760h+hKey]
0x180003d38  call    ??1?$Wrapper@PEAG$1??$DoNothing@PEAG@@YAXPEAG@Z$1??$DeleteArray@G@@YAX0@Z$0A@$1??$CompareDefault@PEAG@@YAH00@Z$01@@QEAA@XZ; Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>::~Wrapper<ushort *,&DoNothing<ushort *>(ushort *),&DeleteArray<ushort>(ushort *),0,&CompareDefault<ushort *>(ushort *,ushort *),2>(void)
0x180003d3d  xor     eax, eax
0x180003d3f  jmp     loc_180003B2D
```
