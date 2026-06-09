# __get_entropy

- ea: `0x1005e9b9`
- end: `0x1005ea08`
- name: `__get_entropy`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1005ea0e`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1005e9e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1005e9e5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005e9dc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1005e9dc`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1005e9cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1005e9cd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1005e9f2`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1005e9f2`

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
0x1005e9b9  mov     edi, edi
0x1005e9bb  push    ebp
0x1005e9bc  mov     ebp, esp
0x1005e9be  sub     esp, 14h
0x1005e9c1  lea     eax, [ebp+SystemTimeAsFileTime]
0x1005e9c4  xorps   xmm0, xmm0
0x1005e9c7  push    eax; lpSystemTimeAsFileTime
0x1005e9c8  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x1005e9cd  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x1005e9d3  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x1005e9d6  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x1005e9d9  mov     [ebp+var_4], eax
0x1005e9dc  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1005e9e2  xor     [ebp+var_4], eax
0x1005e9e5  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1005e9eb  xor     [ebp+var_4], eax
0x1005e9ee  lea     eax, [ebp+PerformanceCount]
0x1005e9f1  push    eax; lpPerformanceCount
0x1005e9f2  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1005e9f8  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x1005e9fb  lea     ecx, [ebp+var_4]
0x1005e9fe  xor     eax, dword ptr [ebp+PerformanceCount]
0x1005ea01  xor     eax, [ebp+var_4]
0x1005ea04  xor     eax, ecx
0x1005ea06  leave
0x1005ea07  retn
```
