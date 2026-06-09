# __security_init_cookie

- ea: `0x140002244`
- end: `0x140002321`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001b40`

## callees

- `0x140002244`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000228b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000228b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002297`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002297`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400022ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400022ce`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400022a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400022b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400022a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400022b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000227d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000227d`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x140002244  mov     [rsp-8+arg_18], rbx
0x140002249  push    rbp
0x14000224a  mov     rbp, rsp
0x14000224d  sub     rsp, 20h
0x140002251  xor     eax, eax
0x140002253  mov     rbx, 2B992DDFA232h
0x14000225d  mov     [rbp+arg_0], rax
0x140002261  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002265  mov     qword ptr [rbp+PerformanceCount], rax
0x140002269  mov     rax, cs:__security_cookie
0x140002270  cmp     rax, rbx
0x140002273  jnz     loc_14000230C
0x140002279  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000227d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002283  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002287  mov     [rbp+arg_0], rax
0x14000228b  call    cs:__imp_GetCurrentProcessId
0x140002291  mov     eax, eax
0x140002293  xor     [rbp+arg_0], rax
0x140002297  call    cs:__imp_GetCurrentThreadId
0x14000229d  mov     eax, eax
0x14000229f  xor     [rbp+arg_0], rax
0x1400022a3  call    cs:__imp_GetTickCount
0x1400022a9  mov     eax, eax
0x1400022ab  shl     rax, 18h
0x1400022af  xor     [rbp+arg_0], rax
0x1400022b3  call    cs:__imp_GetTickCount
0x1400022b9  mov     eax, eax
0x1400022bb  lea     rcx, [rbp+arg_0]
0x1400022bf  xor     rax, [rbp+arg_0]
0x1400022c3  xor     rax, rcx
0x1400022c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400022ca  mov     [rbp+arg_0], rax
0x1400022ce  call    cs:__imp_QueryPerformanceCounter
0x1400022d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400022d7  mov     rcx, 0FFFFFFFFFFFFh
0x1400022e1  shl     rax, 20h
0x1400022e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400022e9  xor     rax, [rbp+arg_0]
0x1400022ed  and     rax, rcx
0x1400022f0  mov     rcx, rax
0x1400022f3  cmp     rax, rbx
0x1400022f6  jnz     short loc_140002305
0x1400022f8  mov     rax, 2B992DDFA233h
0x140002302  mov     rcx, rax
0x140002305  mov     cs:__security_cookie, rcx
0x14000230c  mov     rbx, [rsp+20h+arg_18]
0x140002311  not     rax
0x140002314  mov     cs:__security_cookie_complement, rax
0x14000231b  add     rsp, 20h
0x14000231f  pop     rbp
0x140002320  retn
```
