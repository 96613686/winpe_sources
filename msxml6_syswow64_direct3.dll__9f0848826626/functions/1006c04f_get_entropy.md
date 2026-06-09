# __get_entropy

- ea: `0x1006c04f`
- end: `0x1006c09e`
- name: `__get_entropy`
- size: `79`
- prototype: `unsigned int __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1006c0a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006c07b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006c07b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006c072`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006c072`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1006c088`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1006c088`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1006c063`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1006c063`

## pseudocode

```c
unsigned int __cdecl _get_entropy()
{
  _LARGE_INTEGER perfctr; // [esp+0h] [ebp-14h] BYREF
  FT systime; // [esp+8h] [ebp-Ch] BYREF
  unsigned int cookie; // [esp+10h] [ebp-4h] BYREF

  systime.ft_scalar = 0;
  GetSystemTimeAsFileTime((LPFILETIME)&systime);
  cookie = systime.ft_struct.dwLowDateTime ^ systime.ft_struct.dwHighDateTime;
  cookie ^= GetCurrentThreadId();
  cookie ^= GetCurrentProcessId();
  QueryPerformanceCounter(&perfctr);
  return (unsigned int)&cookie ^ cookie ^ perfctr.LowPart ^ perfctr.HighPart;
}

```

## disassembly

```asm
0x1006c04f  mov     edi, edi
0x1006c051  push    ebp
0x1006c052  mov     ebp, esp
0x1006c054  sub     esp, 14h
0x1006c057  lea     eax, [ebp+systime]
0x1006c05a  xorps   xmm0, xmm0
0x1006c05d  push    eax; lpSystemTimeAsFileTime
0x1006c05e  movlpd  qword ptr [ebp+systime], xmm0
0x1006c063  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x1006c069  mov     eax, dword ptr [ebp+systime+4]
0x1006c06c  xor     eax, dword ptr [ebp+systime]
0x1006c06f  mov     [ebp+cookie], eax
0x1006c072  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1006c078  xor     [ebp+cookie], eax
0x1006c07b  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1006c081  xor     [ebp+cookie], eax
0x1006c084  lea     eax, [ebp+perfctr]
0x1006c087  push    eax; lpPerformanceCount
0x1006c088  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1006c08e  mov     eax, dword ptr [ebp+perfctr+4]
0x1006c091  lea     ecx, [ebp+cookie]
0x1006c094  xor     eax, dword ptr [ebp+perfctr]
0x1006c097  xor     eax, [ebp+cookie]
0x1006c09a  xor     eax, ecx
0x1006c09c  leave
0x1006c09d  retn
```
