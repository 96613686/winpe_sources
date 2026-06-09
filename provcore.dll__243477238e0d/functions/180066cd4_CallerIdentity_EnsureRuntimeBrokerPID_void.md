# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x180066cd4`
- end: `0x180066da3`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `207`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180066614`

## callees

- `0x180002790`
- `0x180066b68`
- `0x180066cd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180066cfc`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180066d77`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180066d77`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066d69`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180066d69`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066d44`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180066d44`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180066d1f`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x180066d1f`

## string_xrefs

- `0x180066d3d`: `%SystemRoot%\System32\RuntimeBroker.exe`

## pseudocode

```c
void __fastcall CallerIdentity::_EnsureRuntimeBrokerPID(CallerIdentity *this)
{
  HANDLE CurrentProcess; // rbx
  unsigned int dwSize[4]; // [rsp+30h] [rbp-448h] BYREF
  WCHAR szExpandedPath[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR szImageName[264]; // [rsp+250h] [rbp-228h] BYREF

  if ( !CallerIdentity::g_fRuntimeBrokerProcessIdInitialize )
  {
    dwSize[0] = 260;
    CurrentProcess = GetCurrentProcess();
    if ( QueryFullProcessImageNameW(CurrentProcess, 0, szImageName, dwSize) || ResultFromKnownLastError() >= 0 )
    {
      if ( ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\RuntimeBroker.exe", szExpandedPath, 0x104u) )
      {
        if ( CompareStringOrdinal(szImageName, -1, szExpandedPath, -1, 1) == 2 )
          CallerIdentity::g_dwRuntimeBrokerProcessId = GetProcessId(CurrentProcess);
      }
    }
    CallerIdentity::g_fRuntimeBrokerProcessIdInitialize = 1;
  }
}

```

## disassembly

```asm
0x180066cd4  push    rbx
0x180066cd6  sub     rsp, 470h
0x180066cdd  mov     rax, cs:__security_cookie
0x180066ce4  xor     rax, rsp
0x180066ce7  mov     [rsp+478h+var_18], rax
0x180066cef  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180066cf6  jnz     loc_180066D8A
0x180066cfc  call    cs:__imp_GetCurrentProcess
0x180066d02  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x180066d07  mov     [rsp+478h+dwSize], 104h
0x180066d0f  mov     rcx, rax; hProcess
0x180066d12  lea     r8, [rsp+478h+szImageName]; lpExeName
0x180066d1a  xor     edx, edx; dwFlags
0x180066d1c  mov     rbx, rax
0x180066d1f  call    cs:__imp_QueryFullProcessImageNameW
0x180066d25  test    eax, eax
0x180066d27  jnz     short loc_180066D32
0x180066d29  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180066d2e  test    eax, eax
0x180066d30  js      short loc_180066D83
0x180066d32  mov     r8d, 104h; nSize
0x180066d38  lea     rdx, [rsp+478h+szExpandedPath]; lpDst
0x180066d3d  lea     rcx, Src; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x180066d44  call    cs:__imp_ExpandEnvironmentStringsW
0x180066d4a  test    eax, eax
0x180066d4c  jz      short loc_180066D83
0x180066d4e  or      edx, 0FFFFFFFFh; cchCount1
0x180066d51  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x180066d59  mov     r9d, edx; cchCount2
0x180066d5c  lea     r8, [rsp+478h+szExpandedPath]; lpString2
0x180066d61  lea     rcx, [rsp+478h+szImageName]; lpString1
0x180066d69  call    cs:__imp_CompareStringOrdinal
0x180066d6f  cmp     eax, 2
0x180066d72  jnz     short loc_180066D83
0x180066d74  mov     rcx, rbx; Process
0x180066d77  call    cs:__imp_GetProcessId
0x180066d7d  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x180066d83  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x180066d8a  mov     rcx, [rsp+478h+var_18]
0x180066d92  xor     rcx, rsp; StackCookie
0x180066d95  call    __security_check_cookie
0x180066d9a  add     rsp, 470h
0x180066da1  pop     rbx
0x180066da2  retn
```
