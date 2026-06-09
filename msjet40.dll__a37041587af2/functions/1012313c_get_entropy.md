# __get_entropy

- ea: `0x1012313c`
- end: `0x1012318b`
- name: `__get_entropy`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10123191`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10123175`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10123175`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1012315f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1012315f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10123168`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10123168`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10123150`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10123150`

## pseudocode

```c
unsigned int _get_entropy()
{
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
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
0x1012313c  mov     edi, edi
0x1012313e  push    ebp
0x1012313f  mov     ebp, esp
0x10123141  sub     esp, 14h
0x10123144  lea     eax, [ebp+SystemTimeAsFileTime]
0x10123147  xorps   xmm0, xmm0
0x1012314a  push    eax; lpSystemTimeAsFileTime
0x1012314b  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x10123150  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x10123156  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x10123159  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x1012315c  mov     [ebp+var_4], eax
0x1012315f  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10123165  xor     [ebp+var_4], eax
0x10123168  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1012316e  xor     [ebp+var_4], eax
0x10123171  lea     eax, [ebp+PerformanceCount]
0x10123174  push    eax; lpPerformanceCount
0x10123175  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1012317b  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x1012317e  lea     ecx, [ebp+var_4]
0x10123181  xor     eax, dword ptr [ebp+PerformanceCount]
0x10123184  xor     eax, [ebp+var_4]
0x10123187  xor     eax, ecx
0x10123189  leave
0x1012318a  retn
```
