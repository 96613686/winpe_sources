# __get_entropy

- ea: `0x1003afb3`
- end: `0x1003b002`
- name: `__get_entropy`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1003b008`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1003afd6`
- `KERNEL32!GetCurrentThreadId` at `0x1003afd6`
- `KERNEL32!GetCurrentProcessId` at `0x1003afdf`
- `KERNEL32!GetCurrentProcessId` at `0x1003afdf`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1003afc7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1003afc7`
- `KERNEL32!QueryPerformanceCounter` at `0x1003afec`
- `KERNEL32!QueryPerformanceCounter` at `0x1003afec`

## pseudocode

```c
unsigned int _get_entropy()
{
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
  unsigned int v3; // [esp+10h] [ebp-4h] BYREF

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
0x1003afb3  mov     edi, edi
0x1003afb5  push    ebp
0x1003afb6  mov     ebp, esp
0x1003afb8  sub     esp, 14h
0x1003afbb  lea     eax, [ebp+SystemTimeAsFileTime]
0x1003afbe  xorps   xmm0, xmm0
0x1003afc1  push    eax; lpSystemTimeAsFileTime
0x1003afc2  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x1003afc7  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x1003afcd  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x1003afd0  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x1003afd3  mov     [ebp+var_4], eax
0x1003afd6  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1003afdc  xor     [ebp+var_4], eax
0x1003afdf  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1003afe5  xor     [ebp+var_4], eax
0x1003afe8  lea     eax, [ebp+PerformanceCount]
0x1003afeb  push    eax; lpPerformanceCount
0x1003afec  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1003aff2  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x1003aff5  lea     ecx, [ebp+var_4]
0x1003aff8  xor     eax, dword ptr [ebp+PerformanceCount]
0x1003affb  xor     eax, [ebp+var_4]
0x1003affe  xor     eax, ecx
0x1003b000  leave
0x1003b001  retn
```
