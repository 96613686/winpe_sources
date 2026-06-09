# __get_entropy

- ea: `0x10012b64`
- end: `0x10012bb3`
- name: `__get_entropy`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10012bb9`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10012b9d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10012b9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10012b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10012b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10012b90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10012b90`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10012b78`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10012b78`

## pseudocode

```c
unsigned int _get_entropy()
{
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
  DWORD v3; // [esp+10h] [ebp-4h] BYREF

  SystemTimeAsFileTime = 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = SystemTimeAsFileTime.dwLowDateTime ^ SystemTimeAsFileTime.dwHighDateTime;
  v3 ^= GetCurrentThreadId();
  v3 ^= GetCurrentProcessId();
  QueryPerformanceCounter(&PerformanceCount);
  return (unsigned int)&v3 ^ v3 ^ PerformanceCount.LowPart ^ PerformanceCount.HighPart;
}

```

## disassembly

```asm
0x10012b64  mov     edi, edi
0x10012b66  push    ebp
0x10012b67  mov     ebp, esp
0x10012b69  sub     esp, 14h
0x10012b6c  lea     eax, [ebp+SystemTimeAsFileTime]
0x10012b6f  xorps   xmm0, xmm0
0x10012b72  push    eax; lpSystemTimeAsFileTime
0x10012b73  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x10012b78  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x10012b7e  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x10012b81  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x10012b84  mov     [ebp+var_4], eax
0x10012b87  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10012b8d  xor     [ebp+var_4], eax
0x10012b90  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10012b96  xor     [ebp+var_4], eax
0x10012b99  lea     eax, [ebp+PerformanceCount]
0x10012b9c  push    eax; lpPerformanceCount
0x10012b9d  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x10012ba3  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x10012ba6  lea     ecx, [ebp+var_4]
0x10012ba9  xor     eax, dword ptr [ebp+PerformanceCount]
0x10012bac  xor     eax, [ebp+var_4]
0x10012baf  xor     eax, ecx
0x10012bb1  leave
0x10012bb2  retn
```
