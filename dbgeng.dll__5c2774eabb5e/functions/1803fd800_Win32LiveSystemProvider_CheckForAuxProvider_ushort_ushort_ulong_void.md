# Win32LiveSystemProvider::CheckForAuxProvider(ushort *,ushort *,ulong,void * *)

- ea: `0x1803fd800`
- end: `0x1803fdb94`
- name: `?CheckForAuxProvider@Win32LiveSystemProvider@@UEAAJPEAG0KPEAPEAX@Z`
- size: `916`
- prototype: `__int64 __fastcall(Win32LiveSystemProvider *__hidden this, unsigned __int16 *, unsigned __int16 *, unsigned int, void **)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800f0f40`
- `0x1803fd800`
- `0x1803fe6dc`
- `0x1803fe820`
- `0x180402690`
- `0x1804da4c0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1803fda3d`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1803fda3d`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803fd9b0`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x1803fd9b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fd9c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fd9d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fd9c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803fd9d4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1803fd971`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1803fd971`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1803fd908`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1803fdaee`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1803fd908`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1803fdaee`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x1803fd948`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x1803fdb24`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x1803fd948`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExA` at `0x1803fdb24`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803fd98a`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803fdb37`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803fd98a`
- `api-ms-win-core-localregistry-l1-1-0!RegCloseKey` at `0x1803fdb37`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1803fd8c5`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1803fdaae`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1803fd8c5`
- `api-ms-win-core-localregistry-l1-1-0!RegQueryValueExW` at `0x1803fdaae`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1803fd88a`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1803fda77`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1803fd88a`
- `api-ms-win-core-localregistry-l1-1-0!RegOpenKeyExA` at `0x1803fda77`

## string_xrefs

- `0x1803fd87c`: `Software\Microsoft\Windows NT\CurrentVersion\MiniDumpAuxiliaryDlls`
- `0x1803fda69`: `Software\Microsoft\Windows NT\CurrentVersion\KnownManagedDebuggingDlls`

## pseudocode

```c
signed int __fastcall Win32LiveSystemProvider::CheckForAuxProvider(
        Win32LiveSystemProvider *this,
        unsigned __int16 *a2,
        BYTE *a3,
        unsigned int a4,
        void **a5)
{
  LSTATUS v9; // ebx
  int IsTrusted; // ebx
  HMODULE Library; // rax
  HMODULE v12; // rsi
  signed int result; // eax
  const unsigned __int16 *v14; // r8
  LSTATUS v15; // esi
  DWORD cbData; // [rsp+40h] [rbp-C0h] BYREF
  DWORD Type; // [rsp+44h] [rbp-BCh] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  int v19[4]; // [rsp+50h] [rbp-B0h] BYREF
  BYTE Data[368]; // [rsp+60h] [rbp-A0h] BYREF
  CHAR MultiByteStr[368]; // [rsp+1D0h] [rbp+D0h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  memset(Data, 0, 0x168u);
  v19[0] = 0;
  *a5 = 0;
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
          IsTrusted = Win32LiveSystemProvider::VerifyModuleIsTrusted(this, (const unsigned __int16 *)a3, a5);
        if ( !v19[0] )
          *a5 = 0;
        return IsTrusted;
      }
      return -2147024891;
    }
  }
  Library = LoadLibraryExW(a2, 0, 2u);
  v12 = Library;
  if ( Library )
  {
    IsTrusted = Win32LiveSystemProvider::GetAuxiliaryProviderFromPathImageResource(
                  this,
                  Library,
                  a2,
                  (unsigned __int16 *)a3,
                  a4);
    if ( IsTrusted < 0 )
      IsTrusted = Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(
                    this,
                    v12,
                    v14,
                    (unsigned __int16 *)a3,
                    a4,
                    v19);
    FreeLibrary(v12);
    if ( IsTrusted < 0 )
      return IsTrusted;
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
0x1803fd800  push    rbp
0x1803fd802  push    rbx
0x1803fd803  push    rsi
0x1803fd804  push    rdi
0x1803fd805  push    r12
0x1803fd807  push    r13
0x1803fd809  push    r14
0x1803fd80b  push    r15
0x1803fd80d  lea     rbp, [rsp-258h]
0x1803fd815  sub     rsp, 358h
0x1803fd81c  mov     rax, cs:__security_cookie
0x1803fd823  xor     rax, rsp
0x1803fd826  mov     [rbp+290h+var_50], rax
0x1803fd82d  mov     r12, [rbp+290h+arg_20]
0x1803fd834  xor     esi, esi
0x1803fd836  mov     rdi, r8
0x1803fd839  mov     [rsp+390h+hKey], rsi
0x1803fd83e  mov     r14, rdx
0x1803fd841  mov     [rsp+390h+Type], esi
0x1803fd845  mov     r13, rcx
0x1803fd848  mov     [rsp+390h+cbData], esi
0x1803fd84c  xor     edx, edx; Val
0x1803fd84e  lea     rcx, [rsp+390h+Data]; void *
0x1803fd853  mov     r8d, 168h; Size
0x1803fd859  mov     r15d, r9d
0x1803fd85c  call    memset
0x1803fd861  lea     rax, [rsp+390h+hKey]
0x1803fd866  mov     [rsp+390h+var_340], esi
0x1803fd86a  mov     r9d, 20019h; samDesired
0x1803fd870  mov     [rsp+390h+phkResult], rax; phkResult
0x1803fd875  xor     r8d, r8d; ulOptions
0x1803fd878  mov     [r12], rsi
0x1803fd87c  lea     rdx, aSoftwareMicros_8; "Software\\Microsoft\\Windows NT\\Curren"...
0x1803fd883  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1803fd88a  call    cs:__imp_RegOpenKeyExA
0x1803fd891  nop     dword ptr [rax+rax+00h]
0x1803fd896  test    eax, eax
0x1803fd898  jnz     loc_1803FDB6B
0x1803fd89e  mov     rcx, [rsp+390h+hKey]; hKey
0x1803fd8a3  lea     eax, [r15+r15]
0x1803fd8a7  mov     [rsp+390h+cbData], eax
0x1803fd8ab  lea     r9, [rsp+390h+Type]; lpType
0x1803fd8b0  lea     rax, [rsp+390h+cbData]
0x1803fd8b5  xor     r8d, r8d; lpReserved
0x1803fd8b8  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1803fd8bd  mov     rdx, r14; lpValueName
0x1803fd8c0  mov     [rsp+390h+phkResult], rdi; lpData
0x1803fd8c5  call    cs:__imp_RegQueryValueExW
0x1803fd8cc  nop     dword ptr [rax+rax+00h]
0x1803fd8d1  mov     ebx, eax
0x1803fd8d3  cmp     eax, 78h ; 'x'
0x1803fd8d6  jnz     loc_1803FD985
0x1803fd8dc  mov     [rsp+390h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x1803fd8e1  lea     rax, [rbp+290h+MultiByteStr]
0x1803fd8e8  mov     [rsp+390h+lpDefaultChar], rsi; lpDefaultChar
0x1803fd8ed  or      r9d, 0FFFFFFFFh; cchWideChar
0x1803fd8f1  mov     dword ptr [rsp+390h+lpcbData], 168h; cbMultiByte
0x1803fd8f9  mov     r8, r14; lpWideCharStr
0x1803fd8fc  mov     edx, 400h; dwFlags
0x1803fd901  mov     [rsp+390h+phkResult], rax; lpMultiByteStr
0x1803fd906  xor     ecx, ecx; CodePage
0x1803fd908  call    cs:__imp_WideCharToMultiByte
0x1803fd90f  nop     dword ptr [rax+rax+00h]
0x1803fd914  test    eax, eax
0x1803fd916  jz      short loc_1803FD985
0x1803fd918  mov     rcx, [rsp+390h+hKey]; hKey
0x1803fd91d  lea     rax, [rsp+390h+cbData]
0x1803fd922  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1803fd927  lea     r9, [rsp+390h+Type]; lpType
0x1803fd92c  lea     rax, [rsp+390h+Data]
0x1803fd931  mov     [rsp+390h+cbData], 168h
0x1803fd939  xor     r8d, r8d; lpReserved
0x1803fd93c  mov     [rsp+390h+phkResult], rax; lpData
0x1803fd941  lea     rdx, [rbp+290h+MultiByteStr]; lpValueName
0x1803fd948  call    cs:__imp_RegQueryValueExA
0x1803fd94f  nop     dword ptr [rax+rax+00h]
0x1803fd954  mov     ebx, eax
0x1803fd956  test    eax, eax
0x1803fd958  jnz     short loc_1803FD985
0x1803fd95a  mov     dword ptr [rsp+390h+lpcbData], r15d; cchWideChar
0x1803fd95f  lea     r8, [rsp+390h+Data]; lpMultiByteStr
0x1803fd964  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1803fd968  mov     [rsp+390h+phkResult], rdi; lpWideCharStr
0x1803fd96d  xor     edx, edx; dwFlags
0x1803fd96f  xor     ecx, ecx; CodePage
0x1803fd971  call    cs:__imp_MultiByteToWideChar
0x1803fd978  nop     dword ptr [rax+rax+00h]
0x1803fd97d  test    eax, eax
0x1803fd97f  lea     ecx, [rsi+57h]
0x1803fd982  cmovz   ebx, ecx
0x1803fd985  mov     rcx, [rsp+390h+hKey]; hKey
0x1803fd98a  call    cs:__imp_RegCloseKey
0x1803fd991  nop     dword ptr [rax+rax+00h]
0x1803fd996  test    ebx, ebx
0x1803fd998  jnz     short loc_1803FD9A7
0x1803fd99a  cmp     [rsp+390h+Type], 1
0x1803fd99f  mov     ebx, esi
0x1803fd9a1  jz      loc_1803FDA56
0x1803fd9a7  xor     edx, edx; hFile
0x1803fd9a9  mov     rcx, r14; lpLibFileName
0x1803fd9ac  lea     r8d, [rdx+2]; dwFlags
0x1803fd9b0  call    cs:__imp_LoadLibraryExW
0x1803fd9b7  nop     dword ptr [rax+rax+00h]
0x1803fd9bc  mov     rsi, rax
0x1803fd9bf  test    rax, rax
0x1803fd9c2  jnz     short loc_1803FD9FF
0x1803fd9c4  call    cs:__imp_GetLastError
0x1803fd9cb  nop     dword ptr [rax+rax+00h]
0x1803fd9d0  test    eax, eax
0x1803fd9d2  jz      short loc_1803FD9F5
0x1803fd9d4  call    cs:__imp_GetLastError
0x1803fd9db  nop     dword ptr [rax+rax+00h]
0x1803fd9e0  test    eax, eax
0x1803fd9e2  jle     loc_1803FDB70
0x1803fd9e8  movzx   eax, ax
0x1803fd9eb  or      eax, 80070000h
0x1803fd9f0  jmp     loc_1803FDB70
0x1803fd9f5  mov     eax, 80004005h
0x1803fd9fa  jmp     loc_1803FDB70
0x1803fd9ff  mov     r9, rdi; unsigned __int16 *
0x1803fda02  mov     dword ptr [rsp+390h+phkResult], r15d; unsigned int
0x1803fda07  mov     r8, r14; unsigned __int16 *
0x1803fda0a  mov     rdx, rsi; HINSTANCE
0x1803fda0d  mov     rcx, r13; this
0x1803fda10  call    ?GetAuxiliaryProviderFromPathImageResource@Win32LiveSystemProvider@@AEAAJPEAUHINSTANCE__@@PEBGPEAGK@Z; Win32LiveSystemProvider::GetAuxiliaryProviderFromPathImageResource(HINSTANCE__ *,ushort const *,ushort *,ulong)
0x1803fda15  mov     ebx, eax
0x1803fda17  test    eax, eax
0x1803fda19  jns     short loc_1803FDA3A
0x1803fda1b  lea     rax, [rsp+390h+var_340]
0x1803fda20  mov     r9, rdi; unsigned __int16 *
0x1803fda23  mov     [rsp+390h+lpcbData], rax; int *
0x1803fda28  mov     rdx, rsi; HINSTANCE
0x1803fda2b  mov     rcx, r13; this
0x1803fda2e  mov     dword ptr [rsp+390h+phkResult], r15d; unsigned int
0x1803fda33  call    ?GetAuxiliaryProviderPathFromEmbeddedImageResource@Win32LiveSystemProvider@@AEAAJPEAUHINSTANCE__@@PEBGPEAGKPEAH@Z; Win32LiveSystemProvider::GetAuxiliaryProviderPathFromEmbeddedImageResource(HINSTANCE__ *,ushort const *,ushort *,ulong,int *)
0x1803fda38  mov     ebx, eax
0x1803fda3a  mov     rcx, rsi; hLibModule
0x1803fda3d  call    cs:__imp_FreeLibrary
0x1803fda44  nop     dword ptr [rax+rax+00h]
0x1803fda49  xor     esi, esi
0x1803fda4b  test    ebx, ebx
0x1803fda4d  jns     short loc_1803FDA56
0x1803fda4f  mov     eax, ebx
0x1803fda51  jmp     loc_1803FDB70
0x1803fda56  lea     rax, [rsp+390h+hKey]
0x1803fda5b  mov     r9d, 20019h; samDesired
0x1803fda61  xor     r8d, r8d; ulOptions
0x1803fda64  mov     [rsp+390h+phkResult], rax; phkResult
0x1803fda69  lea     rdx, aSoftwareMicros_10; "Software\\Microsoft\\Windows NT\\Curren"...
0x1803fda70  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1803fda77  call    cs:__imp_RegOpenKeyExA
0x1803fda7e  nop     dword ptr [rax+rax+00h]
0x1803fda83  test    eax, eax
0x1803fda85  jnz     loc_1803FDB6B
0x1803fda8b  mov     rcx, [rsp+390h+hKey]; hKey
0x1803fda90  lea     rax, [rsp+390h+cbData]
0x1803fda95  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1803fda9a  lea     r9, [rsp+390h+Type]; lpType
0x1803fda9f  xor     r8d, r8d; lpReserved
0x1803fdaa2  mov     [rsp+390h+phkResult], rsi; lpData
0x1803fdaa7  mov     rdx, rdi; lpValueName
0x1803fdaaa  mov     [rsp+390h+cbData], esi
0x1803fdaae  call    cs:__imp_RegQueryValueExW
0x1803fdab5  nop     dword ptr [rax+rax+00h]
0x1803fdaba  xor     r14d, r14d
0x1803fdabd  mov     esi, eax
0x1803fdabf  cmp     eax, 78h ; 'x'
0x1803fdac2  jnz     short loc_1803FDB32
0x1803fdac4  mov     [rsp+390h+lpUsedDefaultChar], r14; lpUsedDefaultChar
0x1803fdac9  lea     rax, [rsp+390h+Data]
0x1803fdace  mov     [rsp+390h+lpDefaultChar], r14; lpDefaultChar
0x1803fdad3  or      r9d, 0FFFFFFFFh; cchWideChar
0x1803fdad7  mov     dword ptr [rsp+390h+lpcbData], 168h; cbMultiByte
0x1803fdadf  mov     r8, rdi; lpWideCharStr
0x1803fdae2  mov     edx, 400h; dwFlags
0x1803fdae7  mov     [rsp+390h+phkResult], rax; lpMultiByteStr
0x1803fdaec  xor     ecx, ecx; CodePage
0x1803fdaee  call    cs:__imp_WideCharToMultiByte
0x1803fdaf5  nop     dword ptr [rax+rax+00h]
0x1803fdafa  test    eax, eax
0x1803fdafc  jz      short loc_1803FDB32
0x1803fdafe  mov     rcx, [rsp+390h+hKey]; hKey
0x1803fdb03  lea     rax, [rsp+390h+cbData]
0x1803fdb08  mov     [rsp+390h+lpcbData], rax; lpcbData
0x1803fdb0d  lea     r9, [rsp+390h+Type]; lpType
0x1803fdb12  xor     r8d, r8d; lpReserved
0x1803fdb15  mov     [rsp+390h+phkResult], r14; lpData
0x1803fdb1a  lea     rdx, [rsp+390h+Data]; lpValueName
0x1803fdb1f  mov     [rsp+390h+cbData], r14d
0x1803fdb24  call    cs:__imp_RegQueryValueExA
0x1803fdb2b  nop     dword ptr [rax+rax+00h]
0x1803fdb30  mov     esi, eax
0x1803fdb32  mov     rcx, [rsp+390h+hKey]; hKey
0x1803fdb37  call    cs:__imp_RegCloseKey
0x1803fdb3e  nop     dword ptr [rax+rax+00h]
0x1803fdb43  test    esi, esi
0x1803fdb45  jz      short loc_1803FDB57
0x1803fdb47  mov     r8, r12; void **
0x1803fdb4a  mov     rdx, rdi; unsigned __int16 *
0x1803fdb4d  mov     rcx, r13; this
0x1803fdb50  call    ?VerifyModuleIsTrusted@Win32LiveSystemProvider@@IEAAJPEBGPEAPEAX@Z; Win32LiveSystemProvider::VerifyModuleIsTrusted(ushort const *,void * *)
0x1803fdb55  mov     ebx, eax
0x1803fdb57  cmp     [rsp+390h+var_340], r14d
0x1803fdb5c  jnz     loc_1803FDA4F
0x1803fdb62  mov     [r12], r14
0x1803fdb66  jmp     loc_1803FDA4F
0x1803fdb6b  mov     eax, 80070005h
0x1803fdb70  mov     rcx, [rbp+290h+var_50]
0x1803fdb77  xor     rcx, rsp; StackCookie
0x1803fdb7a  call    __security_check_cookie
0x1803fdb7f  add     rsp, 358h
0x1803fdb86  pop     r15
0x1803fdb88  pop     r14
0x1803fdb8a  pop     r13
0x1803fdb8c  pop     r12
0x1803fdb8e  pop     rdi
0x1803fdb8f  pop     rsi
0x1803fdb90  pop     rbx
0x1803fdb91  pop     rbp
0x1803fdb92  retn
```
