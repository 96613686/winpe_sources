# CUSTOM_ERROR_HANDLER::Initialize(void)

- ea: `0x180001d3c`
- end: `0x180001f3a`
- name: `?Initialize@CUSTOM_ERROR_HANDLER@@SAJXZ`
- size: `510`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180004670`

## callees

- `0x180001d3c`
- `0x180001f40`
- `0x180001ff0`
- `0x180007836`
- `0x180007870`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001e2e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001db0`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180001db0`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dea`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180001dea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180001e0a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001e1c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180001e1c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180001ebf`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180001ebf`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180001e9c`
- `iisutil!?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z` at `0x180001e9c`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x180001e6c`
- `iisutil!??0LANG_STRING@@QEAA@XZ` at `0x180001e6c`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180001ef2`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x180001ef2`

## string_xrefs

- `0x180001da2`: `System\CurrentControlSet\Services\w3svc\Parameters`
- `0x180001e13`: `iisres.dll`

## pseudocode

```c
__int64 CUSTOM_ERROR_HANDLER::Initialize(void)
{
  signed int LastError; // eax
  signed int v1; // ebx
  LANG_STRING *v2; // rax
  LANG_STRING *v3; // rax
  DWORD cbData; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  BYTE Data[8]; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+50h] [rbp-B0h] BYREF

  hKey = 0;
  Type = 0;
  cbData = 0;
  *(_DWORD *)Data = 0;
  memset_0(&VersionInformation, 0, sizeof(VersionInformation));
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Services\\w3svc\\Parameters", 0, 0x20019u, &hKey) )
  {
    cbData = 4;
    if ( !RegQueryValueExW(hKey, L"IgnoreAppPoolForCustomErrors", 0, &Type, Data, &cbData) && Type == 4 )
      CUSTOM_ERROR_HANDLER::sm_fIgnoreAppPoolForCustomErrors = *(_DWORD *)Data;
    RegCloseKey(hKey);
  }
  CUSTOM_ERROR_HANDLER::sm_hResourceDll = LoadLibraryExW(L"iisres.dll", 0, 0);
  if ( !CUSTOM_ERROR_HANDLER::sm_hResourceDll )
    goto LABEL_7;
  CUSTOM_ERROR_HANDLER::sm_StartupState = 1;
  v2 = (LANG_STRING *)operator new(0x58u);
  if ( !v2 )
  {
    CUSTOM_ERROR_HANDLER::sm_pLangString = 0;
    goto LABEL_17;
  }
  v3 = LANG_STRING::LANG_STRING(v2);
  CUSTOM_ERROR_HANDLER::sm_pLangString = v3;
  if ( !v3 )
  {
LABEL_17:
    v1 = -2147024888;
    goto LABEL_18;
  }
  CUSTOM_ERROR_HANDLER::sm_StartupState = 2;
  v1 = LANG_STRING::Initialize(v3, CUSTOM_ERROR_HANDLER::sm_hResourceDll, 0x7Bu);
  if ( v1 < 0 )
  {
LABEL_18:
    CUSTOM_ERROR_HANDLER::Terminate();
    return (unsigned int)v1;
  }
  CUSTOM_ERROR_HANDLER::sm_StartupState = 3;
  VersionInformation.dwOSVersionInfoSize = 276;
  if ( !GetVersionExW(&VersionInformation) )
  {
LABEL_7:
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_18;
  }
  CUSTOM_ERROR_HANDLER::sm_dwOSBuildNumber = VersionInformation.dwBuildNumber;
  if ( _InterlockedIncrement(&MIME_MAP_TABLE::sm_lInitializeCount) == 1 )
    InitializeSRWLock(&MIME_MAP_TABLE::sm_GlobalLock);
  CUSTOM_ERROR_HANDLER::sm_StartupState = 5;
  return 0;
}

```

## disassembly

```asm
0x180001d3c  mov     [rsp-8+arg_0], rbx
0x180001d41  push    rbp
0x180001d42  lea     rbp, [rsp-80h]
0x180001d47  sub     rsp, 180h
0x180001d4e  mov     rax, cs:__security_cookie
0x180001d55  xor     rax, rsp
0x180001d58  mov     [rbp+80h+var_10], rax
0x180001d5c  xor     edx, edx; Val
0x180001d5e  mov     [rsp+180h+hKey], 0
0x180001d67  mov     r8d, 114h; Size
0x180001d6d  mov     [rsp+180h+Type], 0
0x180001d75  lea     rcx, [rsp+180h+VersionInformation]; void *
0x180001d7a  mov     [rsp+180h+cbData], 0
0x180001d82  mov     dword ptr [rsp+180h+Data], 0
0x180001d8a  call    memset_0
0x180001d8f  lea     rax, [rsp+180h+hKey]
0x180001d94  mov     r9d, 20019h; samDesired
0x180001d9a  xor     r8d, r8d; ulOptions
0x180001d9d  mov     [rsp+180h+phkResult], rax; phkResult
0x180001da2  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\w3"...
0x180001da9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180001db0  call    cs:__imp_RegOpenKeyExW
0x180001db6  test    eax, eax
0x180001db8  jnz     short loc_180001E10
0x180001dba  mov     rcx, [rsp+180h+hKey]; hKey
0x180001dbf  lea     rax, [rsp+180h+cbData]
0x180001dc4  mov     [rsp+180h+lpcbData], rax; lpcbData
0x180001dc9  lea     r9, [rsp+180h+Type]; lpType
0x180001dce  lea     rax, [rsp+180h+Data]
0x180001dd3  mov     [rsp+180h+cbData], 4
0x180001ddb  xor     r8d, r8d; lpReserved
0x180001dde  mov     [rsp+180h+phkResult], rax; lpData
0x180001de3  lea     rdx, ValueName; "IgnoreAppPoolForCustomErrors"
0x180001dea  call    cs:__imp_RegQueryValueExW
0x180001df0  test    eax, eax
0x180001df2  jnz     short loc_180001E05
0x180001df4  cmp     [rsp+180h+Type], 4
0x180001df9  jnz     short loc_180001E05
0x180001dfb  mov     eax, dword ptr [rsp+180h+Data]
0x180001dff  mov     cs:?sm_fIgnoreAppPoolForCustomErrors@CUSTOM_ERROR_HANDLER@@0HA, eax; int CUSTOM_ERROR_HANDLER::sm_fIgnoreAppPoolForCustomErrors
0x180001e05  mov     rcx, [rsp+180h+hKey]; hKey
0x180001e0a  call    cs:__imp_RegCloseKey
0x180001e10  xor     r8d, r8d; dwFlags
0x180001e13  lea     rcx, LibFileName; "iisres.dll"
0x180001e1a  xor     edx, edx; hFile
0x180001e1c  call    cs:__imp_LoadLibraryExW
0x180001e22  mov     cs:?sm_hResourceDll@CUSTOM_ERROR_HANDLER@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CUSTOM_ERROR_HANDLER::sm_hResourceDll
0x180001e29  test    rax, rax
0x180001e2c  jnz     short loc_180001E4C
0x180001e2e  call    cs:__imp_GetLastError
0x180001e34  mov     ebx, eax
0x180001e36  test    eax, eax
0x180001e38  jle     loc_180001F16
0x180001e3e  movzx   ebx, ax
0x180001e41  or      ebx, 80070000h
0x180001e47  jmp     loc_180001F16
0x180001e4c  mov     ecx, 58h ; 'X'; Size
0x180001e51  mov     cs:?sm_StartupState@CUSTOM_ERROR_HANDLER@@0W4CusterrStartup@@A, 1; CusterrStartup CUSTOM_ERROR_HANDLER::sm_StartupState
0x180001e5b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180001e60  test    rax, rax
0x180001e63  jz      loc_180001F06
0x180001e69  mov     rcx, rax
0x180001e6c  call    cs:__imp_??0LANG_STRING@@QEAA@XZ; LANG_STRING::LANG_STRING(void)
0x180001e72  mov     cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA, rax; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180001e79  test    rax, rax
0x180001e7c  jz      loc_180001F11
0x180001e82  mov     rdx, cs:?sm_hResourceDll@CUSTOM_ERROR_HANDLER@@0PEAUHINSTANCE__@@EA; HINSTANCE__ * CUSTOM_ERROR_HANDLER::sm_hResourceDll
0x180001e89  mov     r8d, 7Bh ; '{'
0x180001e8f  mov     rcx, rax
0x180001e92  mov     cs:?sm_StartupState@CUSTOM_ERROR_HANDLER@@0W4CusterrStartup@@A, 2; CusterrStartup CUSTOM_ERROR_HANDLER::sm_StartupState
0x180001e9c  call    cs:__imp_?Initialize@LANG_STRING@@QEAAJPEAUHINSTANCE__@@K@Z; LANG_STRING::Initialize(HINSTANCE__ *,ulong)
0x180001ea2  mov     ebx, eax
0x180001ea4  test    eax, eax
0x180001ea6  js      short loc_180001F16
0x180001ea8  lea     rcx, [rsp+180h+VersionInformation]; lpVersionInformation
0x180001ead  mov     cs:?sm_StartupState@CUSTOM_ERROR_HANDLER@@0W4CusterrStartup@@A, 3; CusterrStartup CUSTOM_ERROR_HANDLER::sm_StartupState
0x180001eb7  mov     [rsp+180h+VersionInformation.dwOSVersionInfoSize], 114h
0x180001ebf  call    cs:__imp_GetVersionExW
0x180001ec5  test    eax, eax
0x180001ec7  jz      loc_180001E2E
0x180001ecd  mov     eax, [rsp+180h+VersionInformation.dwBuildNumber]
0x180001ed1  mov     cs:?sm_dwOSBuildNumber@CUSTOM_ERROR_HANDLER@@0KA, eax; ulong CUSTOM_ERROR_HANDLER::sm_dwOSBuildNumber
0x180001ed7  mov     eax, 1
0x180001edc  lock xadd cs:?sm_lInitializeCount@MIME_MAP_TABLE@@0JA, eax; long MIME_MAP_TABLE::sm_lInitializeCount
0x180001ee4  inc     eax
0x180001ee6  cmp     eax, 1
0x180001ee9  jnz     short loc_180001EF8
0x180001eeb  lea     rcx, ?sm_GlobalLock@MIME_MAP_TABLE@@0U_RTL_SRWLOCK@@A; SRWLock
0x180001ef2  call    cs:__imp_InitializeSRWLock
0x180001ef8  mov     cs:?sm_StartupState@CUSTOM_ERROR_HANDLER@@0W4CusterrStartup@@A, 5; CusterrStartup CUSTOM_ERROR_HANDLER::sm_StartupState
0x180001f02  xor     eax, eax
0x180001f04  jmp     short loc_180001F1D
0x180001f06  mov     cs:?sm_pLangString@CUSTOM_ERROR_HANDLER@@2PEAVLANG_STRING@@EA, 0; LANG_STRING * CUSTOM_ERROR_HANDLER::sm_pLangString
0x180001f11  mov     ebx, 80070008h
0x180001f16  call    ?Terminate@CUSTOM_ERROR_HANDLER@@SAXXZ; CUSTOM_ERROR_HANDLER::Terminate(void)
0x180001f1b  mov     eax, ebx
0x180001f1d  mov     rcx, [rbp+80h+var_10]
0x180001f21  xor     rcx, rsp; StackCookie
0x180001f24  call    __security_check_cookie
0x180001f29  mov     rbx, [rsp+180h+arg_0]
0x180001f31  add     rsp, 180h
0x180001f38  pop     rbp
0x180001f39  retn
```
