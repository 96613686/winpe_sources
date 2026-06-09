# AuthzWrapper::Init(void)

- ea: `0x180072dc4`
- end: `0x180072f04`
- name: `?Init@AuthzWrapper@@QEAAHXZ`
- size: `320`
- prototype: `__int64 __fastcall(AuthzWrapper *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002a950`

## callees

- `0x1800074c0`
- `0x180072dc4`
- `0x180072f0c`
- `0x180097010`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180072e10`
- `ntdll!RtlLeaveCriticalSection` at `0x180072ed4`
- `ntdll!RtlLeaveCriticalSection` at `0x180072e10`
- `ntdll!RtlLeaveCriticalSection` at `0x180072ed4`
- `ntdll!RtlEnterCriticalSection` at `0x180072ddb`
- `ntdll!RtlEnterCriticalSection` at `0x180072e61`
- `ntdll!RtlEnterCriticalSection` at `0x180072ddb`
- `ntdll!RtlEnterCriticalSection` at `0x180072e61`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180072df7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180072df7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072e22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ea8`

## string_xrefs

- `0x180072dee`: `authz.dll`
- `0x180072e28`: `authz.dll`
- `0x180072e37`: `AuthzWrapper::Init(): LoadLibrary(%S) failed with %d\n`

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
  v5 = qword_1800DD708;
  if ( !qword_1800DD708 )
  {
    RtlEnterCriticalSection(&CriticalSection);
    if ( !qword_1800DD708
      && (!qword_1800DD738 || !(unsigned int)qword_1800DD738(0, 0, 0, 0, L"Terminal Server", &qword_1800DD708)) )
    {
      v6 = GetLastError();
      _DbgPrintMessage(4, "AuthzWrapper::Init(): AuthzInitializeResourceManager() failed with %d\n", v6);
      qword_1800DD708 = 0;
    }
    RtlLeaveCriticalSection(&CriticalSection);
    v5 = qword_1800DD708;
    v1 = g_authzWrapper;
  }
  return v1 && v5;
}

```

## disassembly

```asm
0x180072dc4  sub     rsp, 48h
0x180072dc8  mov     rax, cs:?g_authzWrapper@@3VAuthzWrapper@@A; AuthzWrapper g_authzWrapper
0x180072dcf  test    rax, rax
0x180072dd2  jnz     short loc_180072E4A
0x180072dd4  lea     rcx, CriticalSection; CriticalSection
0x180072ddb  call    cs:__imp_RtlEnterCriticalSection
0x180072de1  cmp     cs:?g_authzWrapper@@3VAuthzWrapper@@A, 0; AuthzWrapper g_authzWrapper
0x180072de9  jnz     short loc_180072E09
0x180072deb  xor     r8d, r8d; dwFlags
0x180072dee  lea     rcx, aAuthzDll; "authz.dll"
0x180072df5  xor     edx, edx; hFile
0x180072df7  call    cs:__imp_LoadLibraryExW
0x180072dfd  mov     cs:?g_authzWrapper@@3VAuthzWrapper@@A, rax; AuthzWrapper g_authzWrapper
0x180072e04  call    ?InitAuthzFuncPointers@AuthzWrapper@@AEAAHXZ; AuthzWrapper::InitAuthzFuncPointers(void)
0x180072e09  lea     rcx, CriticalSection; CriticalSection
0x180072e10  call    cs:__imp_RtlLeaveCriticalSection
0x180072e16  mov     rax, cs:?g_authzWrapper@@3VAuthzWrapper@@A; AuthzWrapper g_authzWrapper
0x180072e1d  test    rax, rax
0x180072e20  jnz     short loc_180072E4A
0x180072e22  call    cs:__imp_GetLastError
0x180072e28  lea     r8, aAuthzDll; "authz.dll"
0x180072e2f  mov     ecx, 4; int
0x180072e34  mov     r9d, eax
0x180072e37  lea     rdx, aAuthzwrapperIn; "AuthzWrapper::Init(): LoadLibrary(%S) f"...
0x180072e3e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180072e43  xor     eax, eax
0x180072e45  add     rsp, 48h
0x180072e49  retn
0x180072e4a  mov     rcx, cs:qword_1800DD708
0x180072e51  test    rcx, rcx
0x180072e54  jnz     loc_180072EE8
0x180072e5a  lea     rcx, CriticalSection; CriticalSection
0x180072e61  call    cs:__imp_RtlEnterCriticalSection
0x180072e67  cmp     cs:qword_1800DD708, 0
0x180072e6f  jnz     short loc_180072ECD
0x180072e71  mov     rax, cs:qword_1800DD738
0x180072e78  test    rax, rax
0x180072e7b  jz      short loc_180072EA8
0x180072e7d  lea     rcx, qword_1800DD708
0x180072e84  xor     r9d, r9d
0x180072e87  mov     [rsp+48h+var_20], rcx
0x180072e8c  xor     r8d, r8d
0x180072e8f  lea     rcx, aTerminalServer; "Terminal Server"
0x180072e96  xor     edx, edx
0x180072e98  mov     [rsp+48h+var_28], rcx
0x180072e9d  xor     ecx, ecx
0x180072e9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180072ea4  test    eax, eax
0x180072ea6  jnz     short loc_180072ECD
0x180072ea8  call    cs:__imp_GetLastError
0x180072eae  lea     rdx, aAuthzwrapperIn_0; "AuthzWrapper::Init(): AuthzInitializeRe"...
0x180072eb5  mov     ecx, 4; int
0x180072eba  mov     r8d, eax
0x180072ebd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180072ec2  mov     cs:qword_1800DD708, 0
0x180072ecd  lea     rcx, CriticalSection; CriticalSection
0x180072ed4  call    cs:__imp_RtlLeaveCriticalSection
0x180072eda  mov     rcx, cs:qword_1800DD708
0x180072ee1  mov     rax, cs:?g_authzWrapper@@3VAuthzWrapper@@A; AuthzWrapper g_authzWrapper
0x180072ee8  test    rax, rax
0x180072eeb  jz      loc_180072E43
0x180072ef1  test    rcx, rcx
0x180072ef4  jz      loc_180072E43
0x180072efa  mov     eax, 1
0x180072eff  jmp     loc_180072E45
```
