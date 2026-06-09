# __get_entropy

- ea: `0x1006c0df`
- end: `0x1006c12e`
- name: `__get_entropy`
- size: `79`
- prototype: `unsigned int __cdecl()`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation`

## callers

- `0x1006c134`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006c10b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1006c10b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006c102`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1006c102`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1006c118`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1006c118`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1006c0f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1006c0f3`

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
0x1006c0df  mov     edi, edi
0x1006c0e1  push    ebp
0x1006c0e2  mov     ebp, esp
0x1006c0e4  sub     esp, 14h
0x1006c0e7  lea     eax, [ebp+systime]
0x1006c0ea  xorps   xmm0, xmm0
0x1006c0ed  push    eax; lpSystemTimeAsFileTime
0x1006c0ee  movlpd  qword ptr [ebp+systime], xmm0
0x1006c0f3  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x1006c0f9  mov     eax, dword ptr [ebp+systime+4]
0x1006c0fc  xor     eax, dword ptr [ebp+systime]
0x1006c0ff  mov     [ebp+cookie], eax
0x1006c102  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1006c108  xor     [ebp+cookie], eax
0x1006c10b  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1006c111  xor     [ebp+cookie], eax
0x1006c114  lea     eax, [ebp+perfctr]
0x1006c117  push    eax; lpPerformanceCount
0x1006c118  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1006c11e  mov     eax, dword ptr [ebp+perfctr+4]
0x1006c121  lea     ecx, [ebp+cookie]
0x1006c124  xor     eax, dword ptr [ebp+perfctr]
0x1006c127  xor     eax, [ebp+cookie]
0x1006c12a  xor     eax, ecx
0x1006c12c  leave
0x1006c12d  retn
```
