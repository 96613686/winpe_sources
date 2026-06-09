# GetMaxAsyncWorkerThreads

- ea: `0x140004ed8`
- end: `0x140004fb3`
- name: `GetMaxAsyncWorkerThreads`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000508c`

## callees

- `0x140004ed8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004f23`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140004f23`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004f70`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x140004f70`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140004efd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemInfo` at `0x140004efd`

## string_xrefs

- `0x140004f62`: `MaxAsyncWorkerThreadsPerCpu`

## pseudocode

```c
unsigned __int64 GetMaxAsyncWorkerThreads()
{
  DWORD dwNumberOfProcessors; // edx
  unsigned __int64 result; // rax
  _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-38h] BYREF
  DWORD Type; // [rsp+80h] [rbp+18h] BYREF
  DWORD cbData; // [rsp+88h] [rbp+20h] BYREF
  unsigned int Data; // [rsp+90h] [rbp+28h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+30h] BYREF

  hKey = 0;
  memset(&SystemInfo, 0, sizeof(SystemInfo));
  GetSystemInfo(&SystemInfo);
  if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Lsa", 0, 1u, &hKey)
    && hKey
    && (Data = 2,
        Type = 4,
        cbData = 4,
        !RegQueryValueExW(hKey, L"MaxAsyncWorkerThreadsPerCpu", 0, &Type, (LPBYTE)&Data, &cbData))
    && Type == 4
    && cbData == 4
    && Data )
  {
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
    result = Data * (unsigned __int64)SystemInfo.dwNumberOfProcessors;
    if ( result <= 0xFFFFFFFF )
      return result;
  }
  else
  {
    dwNumberOfProcessors = SystemInfo.dwNumberOfProcessors;
  }
  result = 2LL * dwNumberOfProcessors;
  if ( result > 0xFFFFFFFF )
    return dwNumberOfProcessors;
  return result;
}

```

## disassembly

```asm
0x140004ed8  push    rbp
0x140004eda  push    rdi
0x140004edb  mov     rbp, rsp
0x140004ede  sub     rsp, 68h
0x140004ee2  xorps   xmm0, xmm0
0x140004ee5  mov     [rbp+hKey], 0
0x140004eed  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x140004ef1  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x140004ef5  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x140004ef9  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x140004efd  call    cs:__imp_GetSystemInfo
0x140004f03  lea     rax, [rbp+hKey]
0x140004f07  mov     r9d, 1; samDesired
0x140004f0d  xor     r8d, r8d; ulOptions
0x140004f10  mov     [rsp+68h+phkResult], rax; phkResult
0x140004f15  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\Lsa"
0x140004f1c  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140004f23  call    cs:__imp_RegOpenKeyExW
0x140004f29  mov     edi, 0FFFFFFFFh
0x140004f2e  test    eax, eax
0x140004f30  jnz     short loc_140004F9D
0x140004f32  mov     rcx, [rbp+hKey]; hKey
0x140004f36  test    rcx, rcx
0x140004f39  jz      short loc_140004F9D
0x140004f3b  lea     rax, [rbp+cbData]
0x140004f3f  mov     [rbp+Data], 2
0x140004f46  mov     [rsp+68h+lpcbData], rax; lpcbData
0x140004f4b  lea     r9, [rbp+Type]; lpType
0x140004f4f  lea     rax, [rbp+Data]
0x140004f53  mov     [rbp+Type], 4
0x140004f5a  xor     r8d, r8d; lpReserved
0x140004f5d  mov     [rsp+68h+phkResult], rax; lpData
0x140004f62  lea     rdx, aMaxasyncworker; "MaxAsyncWorkerThreadsPerCpu"
0x140004f69  mov     [rbp+cbData], 4
0x140004f70  call    cs:__imp_RegQueryValueExW
0x140004f76  test    eax, eax
0x140004f78  jnz     short loc_140004F9D
0x140004f7a  cmp     [rbp+Type], 4
0x140004f7e  jnz     short loc_140004F9D
0x140004f80  cmp     [rbp+cbData], 4
0x140004f84  jnz     short loc_140004F9D
0x140004f86  mov     ecx, [rbp+Data]
0x140004f89  test    ecx, ecx
0x140004f8b  jz      short loc_140004F9D
0x140004f8d  mov     edx, [rbp+SystemInfo.dwNumberOfProcessors]
0x140004f90  mov     eax, edx
0x140004f92  imul    rax, rcx
0x140004f96  cmp     rax, rdi
0x140004f99  ja      short loc_140004FA0
0x140004f9b  jmp     short loc_140004FAC
0x140004f9d  mov     edx, [rbp+SystemInfo.dwNumberOfProcessors]
0x140004fa0  mov     eax, edx
0x140004fa2  add     rax, rax
0x140004fa5  cmp     rax, rdi
0x140004fa8  jbe     short loc_140004FAC
0x140004faa  mov     eax, edx
0x140004fac  add     rsp, 68h
0x140004fb0  pop     rdi
0x140004fb1  pop     rbp
0x140004fb2  retn
```
