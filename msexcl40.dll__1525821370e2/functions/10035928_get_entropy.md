# __get_entropy

- ea: `0x10035928`
- end: `0x10035977`
- name: `__get_entropy`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1003597d`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10035961`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x10035961`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10035954`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x10035954`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1003594b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1003594b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1003593c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1003593c`

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
0x10035928  mov     edi, edi
0x1003592a  push    ebp
0x1003592b  mov     ebp, esp
0x1003592d  sub     esp, 14h
0x10035930  lea     eax, [ebp+SystemTimeAsFileTime]
0x10035933  xorps   xmm0, xmm0
0x10035936  push    eax; lpSystemTimeAsFileTime
0x10035937  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x1003593c  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x10035942  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x10035945  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x10035948  mov     [ebp+var_4], eax
0x1003594b  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x10035951  xor     [ebp+var_4], eax
0x10035954  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1003595a  xor     [ebp+var_4], eax
0x1003595d  lea     eax, [ebp+PerformanceCount]
0x10035960  push    eax; lpPerformanceCount
0x10035961  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x10035967  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x1003596a  lea     ecx, [ebp+var_4]
0x1003596d  xor     eax, dword ptr [ebp+PerformanceCount]
0x10035970  xor     eax, [ebp+var_4]
0x10035973  xor     eax, ecx
0x10035975  leave
0x10035976  retn
```
