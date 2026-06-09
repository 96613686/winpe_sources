# IsFirstLogonTaskPerformanceReport

- ea: `0x1400113e0`
- end: `0x1400114e2`
- name: `IsFirstLogonTaskPerformanceReport`
- size: `258`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x140010430`
- `0x140011094`

## callees

- `0x1400113e0`
- `0x14001eba8`
- `0x14012f27c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140011471`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x140011471`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400114c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400114d2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400114c3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1400114d2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400114ae`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1400114ae`
- `SHELL32!__imp_SHCreateSessionKey` at `0x140011401`
- `SHELL32!__imp_SHCreateSessionKey` at `0x140011401`

## string_xrefs

- `0x14001142c`: `LogonTasksReported`
- `0x14001140f`: `shell\lib\logontasks\logontasks.cpp`
- `0x14001147f`: `shell\lib\logontasks\logontasks.cpp`

## pseudocode

```c
bool __fastcall IsFirstLogonTaskPerformanceReport(char a1)
{
  bool v2; // bl
  int v3; // eax
  unsigned int v4; // eax
  int dwOptions; // [rsp+20h] [rbp-30h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  DWORD dwDisposition; // [rsp+78h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+80h] [rbp+30h] BYREF
  HKEY phkResult; // [rsp+88h] [rbp+38h] BYREF

  hKey = 0;
  v2 = 0;
  v3 = SHCreateSessionKey(131078, &hKey);
  if ( v3 >= 0 )
  {
    phkResult = 0;
    if ( a1 )
    {
      dwDisposition = 0;
      v4 = RegCreateKeyExW(hKey, L"LogonTasksReported", 0, 0, 1u, 0x20006u, 0, &phkResult, &dwDisposition);
      if ( v4 )
        wil::details::in1diag3::_Log_Win32(
          retaddr,
          (void *)0x2F22,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)v4,
          dwOptionsa);
      else
        v2 = dwDisposition == 1;
    }
    else
    {
      v2 = RegOpenKeyExW(hKey, L"LogonTasksReported", 0, 0x20019u, &phkResult) == 2;
    }
    if ( phkResult )
      RegCloseKey(phkResult);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2F1C,
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
0x1400113e0  push    rbp
0x1400113e2  push    rbx
0x1400113e3  push    rdi
0x1400113e4  mov     rbp, rsp
0x1400113e7  sub     rsp, 50h
0x1400113eb  mov     dil, cl
0x1400113ee  mov     [rbp+hKey], 0
0x1400113f6  mov     ecx, 20006h
0x1400113fb  lea     rdx, [rbp+hKey]
0x1400113ff  xor     bl, bl
0x140011401  call    cs:__imp_SHCreateSessionKey
0x140011407  test    eax, eax
0x140011409  jns     short loc_140011428
0x14001140b  mov     rcx, [rbp+18h]; this
0x14001140f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140011416  mov     r9d, eax; char *
0x140011419  mov     edx, 2F1Ch; void *
0x14001141e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140011423  jmp     loc_1400114C9
0x140011428  mov     rcx, [rbp+hKey]; hKey
0x14001142c  lea     rdx, aLogontasksrepo; "LogonTasksReported"
0x140011433  xor     r8d, r8d; ulOptions
0x140011436  mov     [rbp+arg_18], 0
0x14001143e  test    dil, dil
0x140011441  jz      short loc_14001149F
0x140011443  lea     rax, [rbp+dwDisposition]
0x140011447  mov     [rbp+dwDisposition], r8d
0x14001144b  mov     [rsp+50h+lpdwDisposition], rax; lpdwDisposition
0x140011450  xor     r9d, r9d; lpClass
0x140011453  lea     rax, [rbp+arg_18]
0x140011457  mov     [rsp+50h+phkResult], rax; phkResult
0x14001145c  mov     [rsp+50h+lpSecurityAttributes], r8; lpSecurityAttributes
0x140011461  mov     [rsp+50h+samDesired], 20006h; samDesired
0x140011469  mov     [rsp+50h+dwOptions], 1; unsigned int
0x140011471  call    cs:__imp_RegCreateKeyExW
0x140011477  test    eax, eax
0x140011479  jz      short loc_140011495
0x14001147b  mov     rcx, [rbp+18h]; this
0x14001147f  lea     r8, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140011486  mov     r9d, eax; char *
0x140011489  mov     edx, 2F22h; void *
0x14001148e  call    ?_Log_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::_Log_Win32(void *,uint,char const *,ulong)
0x140011493  jmp     short loc_1400114BA
0x140011495  cmp     [rbp+dwDisposition], 1
0x140011499  jnz     short loc_1400114BA
0x14001149b  mov     bl, 1
0x14001149d  jmp     short loc_1400114BA
0x14001149f  lea     rax, [rbp+arg_18]
0x1400114a3  mov     r9d, 20019h; samDesired
0x1400114a9  mov     qword ptr [rsp+50h+dwOptions], rax; phkResult
0x1400114ae  call    cs:__imp_RegOpenKeyExW
0x1400114b4  cmp     eax, 2
0x1400114b7  setz    bl
0x1400114ba  mov     rcx, [rbp+arg_18]; hKey
0x1400114be  test    rcx, rcx
0x1400114c1  jz      short loc_1400114C9
0x1400114c3  call    cs:__imp_RegCloseKey
0x1400114c9  mov     rcx, [rbp+hKey]; hKey
0x1400114cd  test    rcx, rcx
0x1400114d0  jz      short loc_1400114D8
0x1400114d2  call    cs:__imp_RegCloseKey
0x1400114d8  mov     al, bl
0x1400114da  add     rsp, 50h
0x1400114de  pop     rdi
0x1400114df  pop     rbx
0x1400114e0  pop     rbp
0x1400114e1  retn
```
