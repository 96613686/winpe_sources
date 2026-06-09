# AuthzWrapper::Init(void)

- ea: `0x180076f44`
- end: `0x1800770b3`
- name: `?Init@AuthzWrapper@@QEAAHXZ`
- size: `367`
- prototype: `__int64 __fastcall(AuthzWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002c990`

## callees

- `0x1800077a0`
- `0x180076f44`
- `0x1800770bc`
- `0x18009c010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180076fa0`
- `ntdll!RtlLeaveCriticalSection` at `0x18007707d`
- `ntdll!RtlLeaveCriticalSection` at `0x180076fa0`
- `ntdll!RtlLeaveCriticalSection` at `0x18007707d`
- `ntdll!RtlEnterCriticalSection` at `0x180076f5f`
- `ntdll!RtlEnterCriticalSection` at `0x180076ffe`
- `ntdll!RtlEnterCriticalSection` at `0x180076f5f`
- `ntdll!RtlEnterCriticalSection` at `0x180076ffe`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180076f81`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180076f81`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007704b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076fb8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007704b`

## string_xrefs

- `0x180076f78`: `authz.dll`
- `0x180076fc4`: `authz.dll`
- `0x180076fd3`: `AuthzWrapper::Init(): LoadLibrary(%S) failed with %d\n`

## pseudocode

```c
_BOOL8 __fastcall AuthzWrapper::Init(AuthzWrapper *this)
{
  HMODULE v1; // rax
  AuthzWrapper *v2; // rcx
  DWORD LastError; // eax
  __int64 v5; // rcx
  DWORD v6; // eax

  v1 = g_authzWrapper;
  if ( !g_authzWrapper )
  {
    RtlEnterCriticalSection(&CriticalSection);
    if ( !g_authzWrapper )
    {
      g_authzWrapper = LoadLibraryExW(L"authz.dll", 0, 0);
      AuthzWrapper::InitAuthzFuncPointers(v2);
    }
    RtlLeaveCriticalSection(&CriticalSection);
    v1 = g_authzWrapper;
    if ( !g_authzWrapper )
    {
      LastError = GetLastError();
      _DbgPrintMessage(4, "AuthzWrapper::Init(): LoadLibrary(%S) failed with %d\n", L"authz.dll", LastError);
      return 0;
    }
  }
  v5 = qword_1800E2718;
  if ( !qword_1800E2718 )
  {
    RtlEnterCriticalSection(&CriticalSection);
    if ( !qword_1800E2718
      && (!qword_1800E2748 || !(unsigned int)qword_1800E2748(0, 0, 0, 0, L"Terminal Server", &qword_1800E2718)) )
    {
      v6 = GetLastError();
      _DbgPrintMessage(4, "AuthzWrapper::Init(): AuthzInitializeResourceManager() failed with %d\n", v6);
      qword_1800E2718 = 0;
    }
    RtlLeaveCriticalSection(&CriticalSection);
    v5 = qword_1800E2718;
    v1 = g_authzWrapper;
  }
  return v1 && v5;
}

```

## disassembly

```asm
0x180076f44  sub     rsp, 48h
0x180076f48  mov     rax, cs:?g_authzWrapper@@3VAuthzWrapper@@A; AuthzWrapper g_authzWrapper
0x180076f4f  test    rax, rax
0x180076f52  jnz     loc_180076FE7
0x180076f58  lea     rcx, CriticalSection; CriticalSection
0x180076f5f  call    cs:__imp_RtlEnterCriticalSection
0x180076f66  nop     dword ptr [rax+rax+00h]
0x180076f6b  cmp     cs:?g_authzWrapper@@3VAuthzWrapper@@A, 0; AuthzWrapper g_authzWrapper
0x180076f73  jnz     short loc_180076F99
0x180076f75  xor     r8d, r8d; dwFlags
0x180076f78  lea     rcx, aAuthzDll; "authz.dll"
0x180076f7f  xor     edx, edx; hFile
0x180076f81  call    cs:__imp_LoadLibraryExW
0x180076f88  nop     dword ptr [rax+rax+00h]
0x180076f8d  mov     cs:?g_authzWrapper@@3VAuthzWrapper@@A, rax; AuthzWrapper g_authzWrapper
0x180076f94  call    ?InitAuthzFuncPointers@AuthzWrapper@@AEAAHXZ; AuthzWrapper::InitAuthzFuncPointers(void)
0x180076f99  lea     rcx, CriticalSection; CriticalSection
0x180076fa0  call    cs:__imp_RtlLeaveCriticalSection
0x180076fa7  nop     dword ptr [rax+rax+00h]
0x180076fac  mov     rax, cs:?g_authzWrapper@@3VAuthzWrapper@@A; AuthzWrapper g_authzWrapper
0x180076fb3  test    rax, rax
0x180076fb6  jnz     short loc_180076FE7
0x180076fb8  call    cs:__imp_GetLastError
0x180076fbf  nop     dword ptr [rax+rax+00h]
0x180076fc4  lea     r8, aAuthzDll; "authz.dll"
0x180076fcb  mov     ecx, 4; int
0x180076fd0  mov     r9d, eax
0x180076fd3  lea     rdx, aAuthzwrapperIn; "AuthzWrapper::Init(): LoadLibrary(%S) f"...
0x180076fda  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180076fdf  xor     eax, eax
0x180076fe1  add     rsp, 48h
0x180076fe5  retn
0x180076fe7  mov     rcx, cs:qword_1800E2718
0x180076fee  test    rcx, rcx
0x180076ff1  jnz     loc_180077097
0x180076ff7  lea     rcx, CriticalSection; CriticalSection
0x180076ffe  call    cs:__imp_RtlEnterCriticalSection
0x180077005  nop     dword ptr [rax+rax+00h]
0x18007700a  cmp     cs:qword_1800E2718, 0
0x180077012  jnz     short loc_180077076
0x180077014  mov     rax, cs:qword_1800E2748
0x18007701b  test    rax, rax
0x18007701e  jz      short loc_18007704B
0x180077020  lea     rcx, qword_1800E2718
0x180077027  xor     r9d, r9d
0x18007702a  mov     [rsp+48h+var_20], rcx
0x18007702f  xor     r8d, r8d
0x180077032  lea     rcx, aTerminalServer; "Terminal Server"
0x180077039  xor     edx, edx
0x18007703b  mov     [rsp+48h+var_28], rcx
0x180077040  xor     ecx, ecx
0x180077042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077047  test    eax, eax
0x180077049  jnz     short loc_180077076
0x18007704b  call    cs:__imp_GetLastError
0x180077052  nop     dword ptr [rax+rax+00h]
0x180077057  lea     rdx, aAuthzwrapperIn_0; "AuthzWrapper::Init(): AuthzInitializeRe"...
0x18007705e  mov     ecx, 4; int
0x180077063  mov     r8d, eax
0x180077066  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18007706b  mov     cs:qword_1800E2718, 0
0x180077076  lea     rcx, CriticalSection; CriticalSection
0x18007707d  call    cs:__imp_RtlLeaveCriticalSection
0x180077084  nop     dword ptr [rax+rax+00h]
0x180077089  mov     rcx, cs:qword_1800E2718
0x180077090  mov     rax, cs:?g_authzWrapper@@3VAuthzWrapper@@A; AuthzWrapper g_authzWrapper
0x180077097  test    rax, rax
0x18007709a  jz      loc_180076FDF
0x1800770a0  test    rcx, rcx
0x1800770a3  jz      loc_180076FDF
0x1800770a9  mov     eax, 1
0x1800770ae  jmp     loc_180076FE1
```
