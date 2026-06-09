# __security_init_cookie

- ea: `0x180003654`
- end: `0x180003731`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002dd0`

## callees

- `0x180003654`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000369b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000369b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000368d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000368d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800036b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800036c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800036b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800036c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800036de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800036de`

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
0x180003654  mov     [rsp-8+arg_18], rbx
0x180003659  push    rbp
0x18000365a  mov     rbp, rsp
0x18000365d  sub     rsp, 20h
0x180003661  xor     eax, eax
0x180003663  mov     rbx, 2B992DDFA232h
0x18000366d  mov     [rbp+arg_0], rax
0x180003671  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003675  mov     qword ptr [rbp+PerformanceCount], rax
0x180003679  mov     rax, cs:__security_cookie
0x180003680  cmp     rax, rbx
0x180003683  jnz     loc_18000371C
0x180003689  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000368d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003693  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003697  mov     [rbp+arg_0], rax
0x18000369b  call    cs:__imp_GetCurrentProcessId
0x1800036a1  mov     eax, eax
0x1800036a3  xor     [rbp+arg_0], rax
0x1800036a7  call    cs:__imp_GetCurrentThreadId
0x1800036ad  mov     eax, eax
0x1800036af  xor     [rbp+arg_0], rax
0x1800036b3  call    cs:__imp_GetTickCount
0x1800036b9  mov     eax, eax
0x1800036bb  shl     rax, 18h
0x1800036bf  xor     [rbp+arg_0], rax
0x1800036c3  call    cs:__imp_GetTickCount
0x1800036c9  mov     eax, eax
0x1800036cb  lea     rcx, [rbp+arg_0]
0x1800036cf  xor     rax, [rbp+arg_0]
0x1800036d3  xor     rax, rcx
0x1800036d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800036da  mov     [rbp+arg_0], rax
0x1800036de  call    cs:__imp_QueryPerformanceCounter
0x1800036e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800036e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800036f1  shl     rax, 20h
0x1800036f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800036f9  xor     rax, [rbp+arg_0]
0x1800036fd  and     rax, rcx
0x180003700  mov     rcx, rax
0x180003703  cmp     rax, rbx
0x180003706  jnz     short loc_180003715
0x180003708  mov     rax, 2B992DDFA233h
0x180003712  mov     rcx, rax
0x180003715  mov     cs:__security_cookie, rcx
0x18000371c  mov     rbx, [rsp+20h+arg_18]
0x180003721  not     rax
0x180003724  mov     cs:__security_cookie_complement, rax
0x18000372b  add     rsp, 20h
0x18000372f  pop     rbp
0x180003730  retn
```
