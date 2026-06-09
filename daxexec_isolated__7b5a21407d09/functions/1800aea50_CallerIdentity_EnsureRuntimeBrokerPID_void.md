# CallerIdentity::_EnsureRuntimeBrokerPID(void)

- ea: `0x1800aea50`
- end: `0x1800aeb43`
- name: `?_EnsureRuntimeBrokerPID@CallerIdentity@@YAXXZ`
- size: `243`
- prototype: `void __fastcall(CallerIdentity *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ae4d4`

## callees

- `0x180004f70`
- `0x1800aea50`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeab1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800aeab1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800aeb10`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1800aeb10`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800aea78`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800aea78`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aeafc`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800aeafc`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800aeaa1`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x1800aeaa1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800aead1`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x1800aead1`

## string_xrefs

- `0x1800aeaca`: `%SystemRoot%\System32\RuntimeBroker.exe`

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
0x1800aea50  push    rbx
0x1800aea52  sub     rsp, 470h
0x1800aea59  mov     rax, cs:__security_cookie
0x1800aea60  xor     rax, rsp
0x1800aea63  mov     [rsp+478h+var_18], rax
0x1800aea6b  cmp     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 0; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800aea72  jnz     loc_1800AEB29
0x1800aea78  call    cs:__imp_GetCurrentProcess
0x1800aea7f  nop     dword ptr [rax+rax+00h]
0x1800aea84  lea     r9, [rsp+478h+dwSize]; lpdwSize
0x1800aea89  mov     [rsp+478h+dwSize], 104h
0x1800aea91  mov     rcx, rax; hProcess
0x1800aea94  lea     r8, [rsp+478h+ExeName]; lpExeName
0x1800aea9c  xor     edx, edx; dwFlags
0x1800aea9e  mov     rbx, rax
0x1800aeaa1  call    cs:__imp_QueryFullProcessImageNameW
0x1800aeaa8  nop     dword ptr [rax+rax+00h]
0x1800aeaad  test    eax, eax
0x1800aeaaf  jnz     short loc_1800AEABF
0x1800aeab1  call    cs:__imp_GetLastError
0x1800aeab8  nop     dword ptr [rax+rax+00h]
0x1800aeabd  jmp     short loc_1800AEB22
0x1800aeabf  mov     r8d, 104h; nSize
0x1800aeac5  lea     rdx, [rsp+478h+Dst]; lpDst
0x1800aeaca  lea     rcx, aSystemrootSyst; "%SystemRoot%\\System32\\RuntimeBroker.e"...
0x1800aead1  call    cs:__imp_ExpandEnvironmentStringsW
0x1800aead8  nop     dword ptr [rax+rax+00h]
0x1800aeadd  test    eax, eax
0x1800aeadf  jz      short loc_1800AEB22
0x1800aeae1  or      edx, 0FFFFFFFFh; cchCount1
0x1800aeae4  mov     [rsp+478h+bIgnoreCase], 1; bIgnoreCase
0x1800aeaec  mov     r9d, edx; cchCount2
0x1800aeaef  lea     r8, [rsp+478h+Dst]; lpString2
0x1800aeaf4  lea     rcx, [rsp+478h+ExeName]; lpString1
0x1800aeafc  call    cs:__imp_CompareStringOrdinal
0x1800aeb03  nop     dword ptr [rax+rax+00h]
0x1800aeb08  cmp     eax, 2
0x1800aeb0b  jnz     short loc_1800AEB22
0x1800aeb0d  mov     rcx, rbx; Process
0x1800aeb10  call    cs:__imp_GetProcessId
0x1800aeb17  nop     dword ptr [rax+rax+00h]
0x1800aeb1c  mov     cs:?g_dwRuntimeBrokerProcessId@CallerIdentity@@3KA, eax; ulong CallerIdentity::g_dwRuntimeBrokerProcessId
0x1800aeb22  mov     cs:?g_fRuntimeBrokerProcessIdInitialize@CallerIdentity@@3_NA, 1; bool CallerIdentity::g_fRuntimeBrokerProcessIdInitialize
0x1800aeb29  mov     rcx, [rsp+478h+var_18]
0x1800aeb31  xor     rcx, rsp; StackCookie
0x1800aeb34  call    __security_check_cookie
0x1800aeb39  add     rsp, 470h
0x1800aeb40  pop     rbx
0x1800aeb41  retn
```
