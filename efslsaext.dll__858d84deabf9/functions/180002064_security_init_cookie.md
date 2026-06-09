# __security_init_cookie

- ea: `0x180002064`
- end: `0x180002141`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c40`

## callees

- `0x180002064`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800020b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800020b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800020ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800020ab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800020ee`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800020ee`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000209d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000209d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800020d3`

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
0x180002064  mov     [rsp-8+arg_18], rbx
0x180002069  push    rbp
0x18000206a  mov     rbp, rsp
0x18000206d  sub     rsp, 20h
0x180002071  xor     eax, eax
0x180002073  mov     rbx, 2B992DDFA232h
0x18000207d  mov     [rbp+arg_0], rax
0x180002081  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002085  mov     qword ptr [rbp+PerformanceCount], rax
0x180002089  mov     rax, cs:__security_cookie
0x180002090  cmp     rax, rbx
0x180002093  jnz     loc_18000212C
0x180002099  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000209d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800020a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800020a7  mov     [rbp+arg_0], rax
0x1800020ab  call    cs:__imp_GetCurrentProcessId
0x1800020b1  mov     eax, eax
0x1800020b3  xor     [rbp+arg_0], rax
0x1800020b7  call    cs:__imp_GetCurrentThreadId
0x1800020bd  mov     eax, eax
0x1800020bf  xor     [rbp+arg_0], rax
0x1800020c3  call    cs:__imp_GetTickCount
0x1800020c9  mov     eax, eax
0x1800020cb  shl     rax, 18h
0x1800020cf  xor     [rbp+arg_0], rax
0x1800020d3  call    cs:__imp_GetTickCount
0x1800020d9  mov     eax, eax
0x1800020db  lea     rcx, [rbp+arg_0]
0x1800020df  xor     rax, [rbp+arg_0]
0x1800020e3  xor     rax, rcx
0x1800020e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800020ea  mov     [rbp+arg_0], rax
0x1800020ee  call    cs:__imp_QueryPerformanceCounter
0x1800020f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800020f7  mov     rcx, 0FFFFFFFFFFFFh
0x180002101  shl     rax, 20h
0x180002105  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002109  xor     rax, [rbp+arg_0]
0x18000210d  and     rax, rcx
0x180002110  mov     rcx, rax
0x180002113  cmp     rax, rbx
0x180002116  jnz     short loc_180002125
0x180002118  mov     rax, 2B992DDFA233h
0x180002122  mov     rcx, rax
0x180002125  mov     cs:__security_cookie, rcx
0x18000212c  mov     rbx, [rsp+20h+arg_18]
0x180002131  not     rax
0x180002134  mov     cs:__security_cookie_complement, rax
0x18000213b  add     rsp, 20h
0x18000213f  pop     rbp
0x180002140  retn
```
