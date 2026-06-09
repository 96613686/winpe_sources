# ___get_entropy

- ea: `0x181289e5`
- end: `0x18128a32`
- name: `___get_entropy`
- size: `77`
- prototype: `unsigned int()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x18128a32`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18128a06`
- `KERNEL32!GetCurrentThreadId` at `0x18128a06`
- `KERNEL32!GetCurrentProcessId` at `0x18128a0f`
- `KERNEL32!GetCurrentProcessId` at `0x18128a0f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x181289f7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x181289f7`
- `KERNEL32!QueryPerformanceCounter` at `0x18128a1c`
- `KERNEL32!QueryPerformanceCounter` at `0x18128a1c`

## pseudocode

```c
unsigned int __get_entropy()
{
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
  DWORD v3; // [esp+10h] [ebp-4h] BYREF

  SystemTimeAsFileTime.dwLowDateTime = 0;
  SystemTimeAsFileTime.dwHighDateTime = 0;
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
0x181289e5  push    ebp
0x181289e6  mov     ebp, esp
0x181289e8  sub     esp, 14h
0x181289eb  and     [ebp+SystemTimeAsFileTime.dwLowDateTime], 0
0x181289ef  lea     eax, [ebp+SystemTimeAsFileTime]
0x181289f2  and     [ebp+SystemTimeAsFileTime.dwHighDateTime], 0
0x181289f6  push    eax; lpSystemTimeAsFileTime
0x181289f7  call    ds:GetSystemTimeAsFileTime
0x181289fd  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x18128a00  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x18128a03  mov     [ebp+var_4], eax
0x18128a06  call    ds:__imp_GetCurrentThreadId
0x18128a0c  xor     [ebp+var_4], eax
0x18128a0f  call    ds:GetCurrentProcessId
0x18128a15  xor     [ebp+var_4], eax
0x18128a18  lea     eax, [ebp+PerformanceCount]
0x18128a1b  push    eax; lpPerformanceCount
0x18128a1c  call    ds:QueryPerformanceCounter
0x18128a22  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x18128a25  lea     ecx, [ebp+var_4]
0x18128a28  xor     eax, dword ptr [ebp+PerformanceCount]
0x18128a2b  xor     eax, [ebp+var_4]
0x18128a2e  xor     eax, ecx
0x18128a30  leave
0x18128a31  retn
```
