# __get_entropy

- ea: `0x10122f8c`
- end: `0x10122fdb`
- name: `__get_entropy`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x10122fe1`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10122fc5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10122fc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x10122faf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10122fb8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10122fb8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10122fa0`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x10122fa0`

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
0x10122f8c  mov     edi, edi
0x10122f8e  push    ebp
0x10122f8f  mov     ebp, esp
0x10122f91  sub     esp, 14h
0x10122f94  lea     eax, [ebp+SystemTimeAsFileTime]
0x10122f97  xorps   xmm0, xmm0
0x10122f9a  push    eax; lpSystemTimeAsFileTime
0x10122f9b  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x10122fa0  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x10122fa6  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x10122fa9  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x10122fac  mov     [ebp+var_4], eax
0x10122faf  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10122fb5  xor     [ebp+var_4], eax
0x10122fb8  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x10122fbe  xor     [ebp+var_4], eax
0x10122fc1  lea     eax, [ebp+PerformanceCount]
0x10122fc4  push    eax; lpPerformanceCount
0x10122fc5  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x10122fcb  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x10122fce  lea     ecx, [ebp+var_4]
0x10122fd1  xor     eax, dword ptr [ebp+PerformanceCount]
0x10122fd4  xor     eax, [ebp+var_4]
0x10122fd7  xor     eax, ecx
0x10122fd9  leave
0x10122fda  retn
```
