# IsFirstLogonTaskPerformanceReport

- ea: `0x140047dc8`
- end: `0x140047f04`
- name: `IsFirstLogonTaskPerformanceReport`
- size: `316`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x140046970`
- `0x140047a3c`

## callees

- `0x14001b2c8`
- `0x140047dc8`
- `0x140047f0c`
- `0x14013af98`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140047e6b`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140047e6b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140047ebd`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140047ebd`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047ed8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047eed`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047ed8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140047eed`
- `SHELL32!__imp_SHCreateSessionKey` at `0x140047de9`
- `SHELL32!__imp_SHCreateSessionKey` at `0x140047de9`

## string_xrefs

- `0x140047dfd`: `shell\lib\logontasks\logontasks.cpp`
- `0x140047e7f`: `shell\lib\logontasks\logontasks.cpp`
- `0x140047e3f`: `LogonTasksReported`
- `0x140047ea8`: `LogonTasksReported`

## pseudocode

```c
bool __fastcall IsFirstLogonTaskPerformanceReport(char a1)
{
  bool v2; // bl
  int v3; // eax
  HKEY *phkResult; // rax
  unsigned int v5; // eax
  HKEY *v6; // rax
  int dwOptions; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD dwDisposition; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  HKEY v13; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v2 = 0;
  v3 = SHCreateSessionKey(131078, &hKey);
  if ( v3 >= 0 )
  {
    v13 = 0;
    if ( a1 )
    {
      dwDisposition = 0;
      phkResult = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v13);
      v5 = RegCreateKeyExW(hKey, L"LogonTasksReported", 0, 0, 1u, 0x20006u, 0, phkResult, &dwDisposition);
      if ( v5 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x2F40,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)v5,
          dwOptionsa);
      else
        v2 = dwDisposition == 1;
    }
    else
    {
      v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(&v13);
      v2 = RegOpenKeyExW(hKey, L"LogonTasksReported", 0, 0x20019u, v6) == 2;
    }
    if ( v13 )
      RegCloseKey(v13);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2F3A,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v3,
      dwOptions);
  }
  if ( hKey )
    RegCloseKey(hKey);
  return v2;
}

```

## disassembly

```asm
0x140047dc8  push    rbp
0x140047dca  push    rbx
0x140047dcb  push    rdi
0x140047dcc  mov     rbp, rsp
0x140047dcf  sub     rsp, 50h
0x140047dd3  mov     dil, cl
0x140047dd6  mov     [rbp+hKey], 0
0x140047dde  mov     ecx, 20006h
0x140047de3  lea     rdx, [rbp+hKey]
0x140047de7  xor     bl, bl
0x140047de9  call    cs:__imp_SHCreateSessionKey
0x140047df0  nop     dword ptr [rax+rax+00h]
0x140047df5  test    eax, eax
0x140047df7  jns     short loc_140047E16
0x140047df9  mov     rcx, [rbp+18h]; this
0x140047dfd  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140047e04  mov     r9d, eax; char *
0x140047e07  mov     edx, 2F3Ah; void *
0x140047e0c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140047e11  jmp     loc_140047EE4
0x140047e16  mov     [rbp+arg_18], 0
0x140047e1e  lea     rcx, [rbp+arg_18]
0x140047e22  test    dil, dil
0x140047e25  jz      short loc_140047E9F
0x140047e27  mov     [rbp+dwDisposition], 0
0x140047e2e  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140047e33  lea     rcx, [rbp+dwDisposition]
0x140047e37  xor     r9d, r9d; lpClass
0x140047e3a  mov     [rsp+50h+lpdwDisposition], rcx; lpdwDisposition
0x140047e3f  lea     rdx, aLogontasksrepo; "LogonTasksReported"
0x140047e46  mov     rcx, [rbp+hKey]; hKey
0x140047e4a  xor     r8d, r8d; Reserved
0x140047e4d  mov     [rsp+50h+phkResult], rax; phkResult
0x140047e52  mov     [rsp+50h+lpSecurityAttributes], 0; lpSecurityAttributes
0x140047e5b  mov     [rsp+50h+samDesired], 20006h; samDesired
0x140047e63  mov     [rsp+50h+dwOptions], 1; unsigned int
0x140047e6b  call    cs:__imp_RegCreateKeyExW
0x140047e72  nop     dword ptr [rax+rax+00h]
0x140047e77  test    eax, eax
0x140047e79  jz      short loc_140047E95
0x140047e7b  mov     rcx, [rbp+18h]; this
0x140047e7f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140047e86  mov     r9d, eax; char *
0x140047e89  mov     edx, 2F40h; void *
0x140047e8e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140047e93  jmp     short loc_140047ECF
0x140047e95  cmp     [rbp+dwDisposition], 1
0x140047e99  jnz     short loc_140047ECF
0x140047e9b  mov     bl, 1
0x140047e9d  jmp     short loc_140047ECF
0x140047e9f  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x140047ea4  mov     rcx, [rbp+hKey]; hKey
0x140047ea8  lea     rdx, aLogontasksrepo; "LogonTasksReported"
0x140047eaf  mov     r9d, 20019h; samDesired
0x140047eb5  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x140047eba  xor     r8d, r8d; ulOptions
0x140047ebd  call    cs:__imp_RegOpenKeyExW
0x140047ec4  nop     dword ptr [rax+rax+00h]
0x140047ec9  cmp     eax, 2
0x140047ecc  setz    bl
0x140047ecf  mov     rcx, [rbp+arg_18]; hKey
0x140047ed3  test    rcx, rcx
0x140047ed6  jz      short loc_140047EE4
0x140047ed8  call    cs:__imp_RegCloseKey
0x140047edf  nop     dword ptr [rax+rax+00h]
0x140047ee4  mov     rcx, [rbp+hKey]; hKey
0x140047ee8  test    rcx, rcx
0x140047eeb  jz      short loc_140047EF9
0x140047eed  call    cs:__imp_RegCloseKey
0x140047ef4  nop     dword ptr [rax+rax+00h]
0x140047ef9  mov     al, bl
0x140047efb  add     rsp, 50h
0x140047eff  pop     rdi
0x140047f00  pop     rbx
0x140047f01  pop     rbp
0x140047f02  retn
```
