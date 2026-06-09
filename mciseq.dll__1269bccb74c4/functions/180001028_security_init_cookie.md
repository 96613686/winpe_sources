# __security_init_cookie

- ea: `0x180001028`
- end: `0x1800010fc`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001008`

## callees

- `0x180001028`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800010b7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800010b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001080`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001074`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001074`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000108c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000109c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000108c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000109c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001066`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001066`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (_FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001028  mov     [rsp-8+arg_18], rbx
0x18000102d  push    rbp
0x18000102e  mov     rbp, rsp
0x180001031  sub     rsp, 20h
0x180001035  mov     rcx, cs:__security_cookie
0x18000103c  xor     eax, eax
0x18000103e  mov     [rbp+arg_0], rax
0x180001042  mov     rbx, 2B992DDFA232h
0x18000104c  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001050  mov     qword ptr [rbp+PerformanceCount], rax
0x180001054  test    rcx, rcx
0x180001057  jz      short loc_180001062
0x180001059  cmp     rcx, rbx
0x18000105c  jnz     loc_1800010E7
0x180001062  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001066  call    cs:__imp_GetSystemTimeAsFileTime
0x18000106c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001070  mov     [rbp+arg_0], rax
0x180001074  call    cs:__imp_GetCurrentProcessId
0x18000107a  mov     eax, eax
0x18000107c  xor     [rbp+arg_0], rax
0x180001080  call    cs:__imp_GetCurrentThreadId
0x180001086  mov     eax, eax
0x180001088  xor     [rbp+arg_0], rax
0x18000108c  call    cs:__imp_GetTickCount
0x180001092  mov     eax, eax
0x180001094  shl     rax, 18h
0x180001098  xor     [rbp+arg_0], rax
0x18000109c  call    cs:__imp_GetTickCount
0x1800010a2  mov     eax, eax
0x1800010a4  lea     rcx, [rbp+arg_0]
0x1800010a8  xor     rax, [rbp+arg_0]
0x1800010ac  xor     rax, rcx
0x1800010af  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800010b3  mov     [rbp+arg_0], rax
0x1800010b7  call    cs:__imp_QueryPerformanceCounter
0x1800010bd  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800010c0  mov     rcx, 0FFFFFFFFFFFFh
0x1800010ca  shl     rax, 20h
0x1800010ce  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800010d2  xor     rax, [rbp+arg_0]
0x1800010d6  and     rax, rcx
0x1800010d9  mov     rcx, rbx
0x1800010dc  cmovnz  rcx, rax
0x1800010e0  mov     cs:__security_cookie, rcx
0x1800010e7  mov     rbx, [rsp+20h+arg_18]
0x1800010ec  not     rcx
0x1800010ef  mov     cs:__security_cookie_complement, rcx
0x1800010f6  add     rsp, 20h
0x1800010fa  pop     rbp
0x1800010fb  retn
```
