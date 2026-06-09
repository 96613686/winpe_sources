# Win32LiveSystemProvider::CheckForAuxProvider(ushort *,ushort *,ulong,void * *)

- ea: `0x180011430`
- end: `0x180011768`
- name: `?CheckForAuxProvider@Win32LiveSystemProvider@@UEAAJPEAG0KPEAPEAX@Z`
- size: `824`
- prototype: `int(Win32LiveSystemProvider *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001710`
- `0x1800021f4`
- `0x180011430`
- `0x180012404`
- `0x180016198`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800115c5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1800115c5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001162c`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18001162c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115dd`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011592`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180011592`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180011535`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800116d7`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x180011535`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800116d7`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1800114bf`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x18001166c`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1800114bf`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x18001166c`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800115a5`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180011714`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1800115a5`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x180011714`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1800114f8`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18001169d`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1800114f8`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x18001169d`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x18001156f`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x180011707`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x18001156f`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x180011707`

## string_xrefs

- `0x1800114ae`: `Software\Microsoft\Windows NT\CurrentVersion\MiniDumpAuxiliaryDlls`
- `0x18001165e`: `Software\Microsoft\Windows NT\CurrentVersion\KnownManagedDebuggingDlls`

## pseudocode

```c
int __fastcall Win32LiveSystemProvider::CheckForAuxProvider(
        Win32LiveSystemProvider *this,
        unsigned __int16 *a2,
        BYTE *a3,
        unsigned int a4,
        void **a5)
{
  int v8; // r15d
  LSTATUS v9; // ebx
  int IsTrusted; // ebx
  HMODULE Library; // rdi
  int result; // eax
  const unsigned __int16 *v13; // r8
  Win32LiveSystemProvider *v14; // r14
  LSTATUS v15; // edi
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v19; // [rsp+50h] [rbp-B0h] BYREF
  Win32LiveSystemProvider *v20; // [rsp+58h] [rbp-A8h]
  BYTE Data[368]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR MultiByteStr[368]; // [rsp+1D0h] [rbp+D0h] BYREF

  v20 = this;
  hKey = 0;
  Type = 0;
  cbData = 0;
  memset_0(Data, 0, 0x168u);
  v19 = 0;
  *a5 = 0;
  v8 = 0;
  if ( RegOpenKeyExA(
         HKEY_LOCAL_MACHINE,
         "Software\\Microsoft\\Windows NT\\CurrentVersion\\MiniDumpAuxiliaryDlls",
         0,
         0x20019u,
         &hKey) )
  {
    return -2147024891;
  }
  cbData = 2 * a4;
  v9 = RegQueryValueExW(hKey, a2, 0, &Type, a3, &cbData);
  if ( v9 == 120 )
  {
    if ( WideCharToMultiByte(0, 0x400u, a2, -1, MultiByteStr, 360, 0, 0) )
    {
      cbData = 360;
      v9 = RegQueryValueExA(hKey, MultiByteStr, 0, &Type, Data, &cbData);
      if ( !v9 && !MultiByteToWideChar(0, 0, (LPCCH)Data, -1, (LPWSTR)a3, a4) )
        v9 = 87;
    }
  }
  RegCloseKey(hKey);
  if ( !v9 )
  {
    IsTrusted = 0;
    if ( Type == 1 )
    {
      v14 = v20;
LABEL_18:
      if ( !RegOpenKeyExA(
              HKEY_LOCAL_MACHINE,
              "Software\\Microsoft\\Windows NT\\CurrentVersion\\KnownManagedDebuggingDlls",
              0,
              0x20019u,
              &hKey) )
      {
        cbData = 0;
        v15 = RegQueryValueExW(hKey, (LPCWSTR)a3, 0, &Type, 0, &cbData);
        if ( v15 == 120 && WideCharToMultiByte(0, 0x400u, (LPCWCH)a3, -1, (LPSTR)Data, 360, 0, 0) )
        {
          cbData = 0;
          v15 = RegQueryValueExA(hKey, (LPCSTR)Data, 0, &Type, 0, &cbData);
        }
        RegCloseKey(hKey);
        if ( v15 )
          IsTrusted = Win32LiveSystemProvider::VerifyModuleIsTrusted(v14, (const unsigned __int16 *)a3, a5);
        if ( !v8 )
          *a5 = 0;
        return IsTrusted;
      }
      return -2147024891;
    }
  }
  Library = LoadLibraryExW(a2, 0, 2u);
  if ( Library )
  {
    v13 = a2;
    v14 = v20;
    IsTrusted = Win32LiveSystemProvider::GetAuxiliaryProviderFromImageResource(
                  v20,
                  Library,
                  v13,
                  (unsigned __int16 *)a3,
                  a4,
                  &v19);
    FreeLibrary(Library);
    if ( IsTrusted < 0 )
      return IsTrusted;
    v8 = v19;
    goto LABEL_18;
  }
  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180011430  push    rbp
0x180011432  push    rbx
0x180011433  push    rsi
0x180011434  push    rdi
0x180011435  push    r12
0x180011437  push    r13
0x180011439  push    r14
0x18001143b  push    r15
0x18001143d  lea     rbp, [rsp-258h]
0x180011445  sub     rsp, 358h
0x18001144c  mov     rax, cs:__security_cookie
0x180011453  xor     rax, rsp
0x180011456  mov     [rbp+290h+var_50], rax
0x18001145d  mov     r12, [rbp+290h+arg_20]
0x180011464  xor     edi, edi
0x180011466  mov     rsi, r8
0x180011469  mov     [rsp+390h+var_338], rcx
0x18001146e  mov     r14, rdx
0x180011471  mov     [rsp+390h+hKey], rdi
0x180011476  xor     edx, edx; Val
0x180011478  mov     [rsp+390h+Type], edi
0x18001147c  mov     r8d, 168h; Size
0x180011482  mov     [rsp+390h+cbData], edi
0x180011486  lea     rcx, [rsp+390h+Data]; void *
0x18001148b  mov     r13d, r9d
0x18001148e  call    memset_0
0x180011493  lea     rax, [rsp+390h+hKey]
0x180011498  mov     [rsp+390h+var_340], edi
0x18001149c  mov     r9d, 20019h; samDesired
0x1800114a2  mov     [rsp+390h+phkResult], rax; phkResult
0x1800114a7  xor     r8d, r8d; ulOptions
0x1800114aa  mov     [r12], rdi
0x1800114ae  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800114b5  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800114bc  mov     r15d, edi
0x1800114bf  call    cs:__imp_RegOpenKeyExA
0x1800114c5  test    eax, eax
0x1800114c7  jnz     loc_180011740
0x1800114cd  mov     rcx, [rsp+390h+hKey]; hKey
0x1800114d2  lea     eax, ds:0[r13*2]
0x1800114da  mov     [rsp+390h+cbData], eax
0x1800114de  lea     r9, [rsp+390h+Type]; lpType
0x1800114e3  lea     rax, [rsp+390h+cbData]
0x1800114e8  xor     r8d, r8d; lpReserved
0x1800114eb  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1800114f0  mov     rdx, r14; lpValueName
0x1800114f3  mov     [rsp+390h+phkResult], rsi; lpData
0x1800114f8  call    cs:__imp_RegQueryValueExW
0x1800114fe  mov     ebx, eax
0x180011500  cmp     eax, 78h ; 'x'
0x180011503  jnz     loc_1800115A0
0x180011509  mov     [rsp+390h+lpUsedDefaultChar], rdi; lpUsedDefaultChar
0x18001150e  lea     rax, [rbp+290h+MultiByteStr]
0x180011515  mov     [rsp+390h+lpDefaultChar], rdi; lpDefaultChar
0x18001151a  or      r9d, 0FFFFFFFFh; cchWideChar
0x18001151e  mov     dword ptr [rsp+390h+lpcbData], 168h; cbMultiByte
0x180011526  mov     r8, r14; lpWideCharStr
0x180011529  mov     edx, 400h; dwFlags
0x18001152e  mov     [rsp+390h+phkResult], rax; lpMultiByteStr
0x180011533  xor     ecx, ecx; CodePage
0x180011535  call    cs:__imp_WideCharToMultiByte
0x18001153b  test    eax, eax
0x18001153d  jz      short loc_1800115A0
0x18001153f  mov     rcx, [rsp+390h+hKey]; hKey
0x180011544  lea     rax, [rsp+390h+cbData]
0x180011549  mov     [rsp+390h+lpcbData], rax; lpcbData
0x18001154e  lea     r9, [rsp+390h+Type]; lpType
0x180011553  lea     rax, [rsp+390h+Data]
0x180011558  mov     [rsp+390h+cbData], 168h
0x180011560  xor     r8d, r8d; lpReserved
0x180011563  mov     [rsp+390h+phkResult], rax; lpData
0x180011568  lea     rdx, [rbp+290h+MultiByteStr]; lpValueName
0x18001156f  call    cs:__imp_RegQueryValueExA
0x180011575  mov     ebx, eax
0x180011577  test    eax, eax
0x180011579  jnz     short loc_1800115A0
0x18001157b  mov     dword ptr [rsp+390h+lpcbData], r13d; cchWideChar
0x180011580  lea     r8, [rsp+390h+Data]; lpMultiByteStr
0x180011585  or      r9d, 0FFFFFFFFh; cbMultiByte
0x180011589  mov     [rsp+390h+phkResult], rsi; lpWideCharStr
0x18001158e  xor     edx, edx; dwFlags
0x180011590  xor     ecx, ecx; CodePage
0x180011592  call    cs:__imp_MultiByteToWideChar
0x180011598  test    eax, eax
0x18001159a  lea     ecx, [rdi+57h]
0x18001159d  cmovz   ebx, ecx
0x1800115a0  mov     rcx, [rsp+390h+hKey]; hKey
0x1800115a5  call    cs:__imp_RegCloseKey
0x1800115ab  test    ebx, ebx
0x1800115ad  jnz     short loc_1800115BC
0x1800115af  cmp     [rsp+390h+Type], 1
0x1800115b4  mov     ebx, edi
0x1800115b6  jz      loc_180011646
0x1800115bc  xor     edx, edx; hFile
0x1800115be  mov     rcx, r14; lpLibFileName
0x1800115c1  lea     r8d, [rdx+2]; dwFlags
0x1800115c5  call    cs:__imp_LoadLibraryExW
0x1800115cb  mov     rdi, rax
0x1800115ce  test    rax, rax
0x1800115d1  jnz     short loc_180011602
0x1800115d3  call    cs:__imp_GetLastError
0x1800115d9  test    eax, eax
0x1800115db  jz      short loc_1800115F8
0x1800115dd  call    cs:__imp_GetLastError
0x1800115e3  test    eax, eax
0x1800115e5  jle     loc_180011745
0x1800115eb  movzx   eax, ax
0x1800115ee  or      eax, 80070000h
0x1800115f3  jmp     loc_180011745
0x1800115f8  mov     eax, 80004005h
0x1800115fd  jmp     loc_180011745
0x180011602  mov     r8, r14; unsigned __int16 *
0x180011605  lea     rax, [rsp+390h+var_340]
0x18001160a  mov     r14, [rsp+390h+var_338]
0x18001160f  mov     r9, rsi; unsigned __int16 *
0x180011612  mov     [rsp+390h+lpcbData], rax; int *
0x180011617  mov     rcx, r14; this
0x18001161a  mov     rdx, rdi; HINSTANCE
0x18001161d  mov     dword ptr [rsp+390h+phkResult], r13d; unsigned int
0x180011622  call    ?GetAuxiliaryProviderFromImageResource@Win32LiveSystemProvider@@AEAAJPEAUHINSTANCE__@@PEBGPEAGKPEAH@Z; Win32LiveSystemProvider::GetAuxiliaryProviderFromImageResource(HINSTANCE__ *,ushort const *,ushort *,ulong,int *)
0x180011627  mov     rcx, rdi; hLibModule
0x18001162a  mov     ebx, eax
0x18001162c  call    cs:__imp_FreeLibrary
0x180011632  xor     edi, edi
0x180011634  test    ebx, ebx
0x180011636  jns     short loc_18001163F
0x180011638  mov     eax, ebx
0x18001163a  jmp     loc_180011745
0x18001163f  mov     r15d, [rsp+390h+var_340]
0x180011644  jmp     short loc_18001164B
0x180011646  mov     r14, [rsp+390h+var_338]
0x18001164b  lea     rax, [rsp+390h+hKey]
0x180011650  mov     r9d, 20019h; samDesired
0x180011656  xor     r8d, r8d; ulOptions
0x180011659  mov     [rsp+390h+phkResult], rax; phkResult
0x18001165e  lea     rdx, aSoftwareMicros_3; "Software\\Microsoft\\Windows NT\\Curren"...
0x180011665  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001166c  call    cs:__imp_RegOpenKeyExA
0x180011672  test    eax, eax
0x180011674  jnz     loc_180011740
0x18001167a  mov     rcx, [rsp+390h+hKey]; hKey
0x18001167f  lea     rax, [rsp+390h+cbData]
0x180011684  mov     [rsp+390h+lpcbData], rax; lpcbData
0x180011689  lea     r9, [rsp+390h+Type]; lpType
0x18001168e  xor     r8d, r8d; lpReserved
0x180011691  mov     [rsp+390h+phkResult], rdi; lpData
0x180011696  mov     rdx, rsi; lpValueName
0x180011699  mov     [rsp+390h+cbData], edi
0x18001169d  call    cs:__imp_RegQueryValueExW
0x1800116a3  xor     r13d, r13d
0x1800116a6  mov     edi, eax
0x1800116a8  cmp     eax, 78h ; 'x'
0x1800116ab  jnz     short loc_18001170F
0x1800116ad  mov     [rsp+390h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800116b2  lea     rax, [rsp+390h+Data]
0x1800116b7  mov     [rsp+390h+lpDefaultChar], r13; lpDefaultChar
0x1800116bc  or      r9d, 0FFFFFFFFh; cchWideChar
0x1800116c0  mov     dword ptr [rsp+390h+lpcbData], 168h; cbMultiByte
0x1800116c8  mov     r8, rsi; lpWideCharStr
0x1800116cb  mov     edx, 400h; dwFlags
0x1800116d0  mov     [rsp+390h+phkResult], rax; lpMultiByteStr
0x1800116d5  xor     ecx, ecx; CodePage
0x1800116d7  call    cs:__imp_WideCharToMultiByte
0x1800116dd  test    eax, eax
0x1800116df  jz      short loc_18001170F
0x1800116e1  mov     rcx, [rsp+390h+hKey]; hKey
0x1800116e6  lea     rax, [rsp+390h+cbData]
0x1800116eb  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1800116f0  lea     r9, [rsp+390h+Type]; lpType
0x1800116f5  xor     r8d, r8d; lpReserved
0x1800116f8  mov     [rsp+390h+phkResult], r13; lpData
0x1800116fd  lea     rdx, [rsp+390h+Data]; lpValueName
0x180011702  mov     [rsp+390h+cbData], r13d
0x180011707  call    cs:__imp_RegQueryValueExA
0x18001170d  mov     edi, eax
0x18001170f  mov     rcx, [rsp+390h+hKey]; hKey
0x180011714  call    cs:__imp_RegCloseKey
0x18001171a  test    edi, edi
0x18001171c  jz      short loc_18001172E
0x18001171e  mov     r8, r12; void **
0x180011721  mov     rdx, rsi; unsigned __int16 *
0x180011724  mov     rcx, r14; this
0x180011727  call    ?VerifyModuleIsTrusted@Win32LiveSystemProvider@@IEAAJPEBGPEAPEAX@Z; Win32LiveSystemProvider::VerifyModuleIsTrusted(ushort const *,void * *)
0x18001172c  mov     ebx, eax
0x18001172e  test    r15d, r15d
0x180011731  jnz     loc_180011638
0x180011737  mov     [r12], r13
0x18001173b  jmp     loc_180011638
0x180011740  mov     eax, 80070005h
0x180011745  mov     rcx, [rbp+290h+var_50]
0x18001174c  xor     rcx, rsp; StackCookie
0x18001174f  call    __security_check_cookie
0x180011754  add     rsp, 358h
0x18001175b  pop     r15
0x18001175d  pop     r14
0x18001175f  pop     r13
0x180011761  pop     r12
0x180011763  pop     rdi
0x180011764  pop     rsi
0x180011765  pop     rbx
0x180011766  pop     rbp
0x180011767  retn
```
