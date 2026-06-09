# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x1800ad58c`
- end: `0x1800ad67f`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `243`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ad050`

## callees

- `0x1800053a0`
- `0x1800ad58c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad5ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad5ed`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ad5b4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800ad5b4`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800ad64c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800ad64c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ad638`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800ad638`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ad5dd`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800ad5dd`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ad60d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800ad60d`

## string_xrefs

- `0x1800ad606`: `%SystemRoot%\System32\RuntimeBroker.exe`

## pseudocode

```c
void __fastcall CallerIdentity::_EnsureRuntimeBrokerPID(CallerIdentity *this)
{
  HANDLE CurrentProcess; // rbx
  DWORD dwSize[4]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR Dst[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR ExeName[264]; // [rsp+250h] [rbp-228h] BYREF

  if ( !CallerIdentity::g_fRuntimeBrokerProcessIdInitialize )
  {
    dwSize[0] = 260;
    CurrentProcess = GetCurrentProcess();
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, ExeName, dwSize) )
    {
      if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\RuntimeBroker.exe", Dst, 0x104u) )
      {
        if ( CompareStringOrdinal(ExeName, -1, Dst, -1, 1) == 2 )
          CallerIdentity::g_dwRuntimeBrokerProcessId = GetProcessId(CurrentProcess);
      }
    }
    else
    {
      GetLastError();
    }
    CallerIdentity::g_fRuntimeBrokerProcessIdInitialize = 1;
  }
}

```

## disassembly

```asm
0x1800ad58c  push    rbx
0x1800ad58e  sub     rsp, 470h
0x1800ad595  mov     rax, cs:__security_cookie
0x1800ad59c  xor     rax, rsp
0x1800ad59f  mov     [rsp+478h+var_18], rax
0x1800ad5a7  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800ad5ae  jnz     loc_1800AD665
0x1800ad5b4  call    cs:__imp_GetCurrentProcess
0x1800ad5bb  nop     dword ptr [rax+rax+00h]
0x1800ad5c0  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800ad5c5  mov     [rsp+478h+dwSize], 104h
0x1800ad5cd  mov     rcx, rax; hProcess
0x1800ad5d0  lea     r8, [rsp+478h+ExeName]; lpExeName
0x1800ad5d8  xor     edx, edx; dwFlags
0x1800ad5da  mov     rbx, rax
0x1800ad5dd  call    cs:__imp_QueryFullProcessImageNameW
0x1800ad5e4  nop     dword ptr [rax+rax+00h]
0x1800ad5e9  test    eax, eax
0x1800ad5eb  jnz     short loc_1800AD5FB
0x1800ad5ed  call    cs:__imp_GetLastError
0x1800ad5f4  nop     dword ptr [rax+rax+00h]
0x1800ad5f9  jmp     short loc_1800AD65E
0x1800ad5fb  mov     r8d, 104h; nSize
0x1800ad601  lea     rdx, [rsp+478h+Dst]; lpDst
0x1800ad606  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x1800ad60d  call    cs:__imp_ExpandEnvironmentStringsW
0x1800ad614  nop     dword ptr [rax+rax+00h]
0x1800ad619  test    eax, eax
0x1800ad61b  jz      short loc_1800AD65E
0x1800ad61d  or      edx, 0FFFFFFFFh; cchCount1
0x1800ad620  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x1800ad628  mov     r9d, edx; cchCount2
0x1800ad62b  lea     r8, [rsp+478h+Dst]; lpString2
0x1800ad630  lea     rcx, [rsp+478h+ExeName]; lpString1
0x1800ad638  call    cs:__imp_CompareStringOrdinal
0x1800ad63f  nop     dword ptr [rax+rax+00h]
0x1800ad644  cmp     eax, 2
0x1800ad647  jnz     short loc_1800AD65E
0x1800ad649  mov     rcx, rbx; Process
0x1800ad64c  call    cs:__imp_GetProcessId
0x1800ad653  nop     dword ptr [rax+rax+00h]
0x1800ad658  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x1800ad65e  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800ad665  mov     rcx, [rsp+478h+var_18]
0x1800ad66d  xor     rcx, rsp; StackCookie
0x1800ad670  call    __security_check_cookie
0x1800ad675  add     rsp, 470h
0x1800ad67c  pop     rbx
0x1800ad67d  retn
```
