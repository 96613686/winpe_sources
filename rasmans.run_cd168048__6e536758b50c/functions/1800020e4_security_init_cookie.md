# __security_init_cookie

- ea: `0x1800020e4`
- end: `0x1800021c1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a50`

## callees

- `0x1800020e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000212b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000212b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002137`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002143`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002153`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002143`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002153`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000211d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000211d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000216e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000216e`

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
0x1800020e4  mov     [rsp-8+arg_18], rbx
0x1800020e9  push    rbp
0x1800020ea  mov     rbp, rsp
0x1800020ed  sub     rsp, 20h
0x1800020f1  xor     eax, eax
0x1800020f3  mov     rbx, 2B992DDFA232h
0x1800020fd  mov     [rbp+arg_0], rax
0x180002101  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002105  mov     qword ptr [rbp+PerformanceCount], rax
0x180002109  mov     rax, cs:__security_cookie
0x180002110  cmp     rax, rbx
0x180002113  jnz     loc_1800021AC
0x180002119  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000211d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002123  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002127  mov     [rbp+arg_0], rax
0x18000212b  call    cs:__imp_GetCurrentProcessId
0x180002131  mov     eax, eax
0x180002133  xor     [rbp+arg_0], rax
0x180002137  call    cs:__imp_GetCurrentThreadId
0x18000213d  mov     eax, eax
0x18000213f  xor     [rbp+arg_0], rax
0x180002143  call    cs:__imp_GetTickCount
0x180002149  mov     eax, eax
0x18000214b  shl     rax, 18h
0x18000214f  xor     [rbp+arg_0], rax
0x180002153  call    cs:__imp_GetTickCount
0x180002159  mov     eax, eax
0x18000215b  lea     rcx, [rbp+arg_0]
0x18000215f  xor     rax, [rbp+arg_0]
0x180002163  xor     rax, rcx
0x180002166  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000216a  mov     [rbp+arg_0], rax
0x18000216e  call    cs:__imp_QueryPerformanceCounter
0x180002174  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002177  mov     rcx, 0FFFFFFFFFFFFh
0x180002181  shl     rax, 20h
0x180002185  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002189  xor     rax, [rbp+arg_0]
0x18000218d  and     rax, rcx
0x180002190  mov     rcx, rax
0x180002193  cmp     rax, rbx
0x180002196  jnz     short loc_1800021A5
0x180002198  mov     rax, 2B992DDFA233h
0x1800021a2  mov     rcx, rax
0x1800021a5  mov     cs:__security_cookie, rcx
0x1800021ac  mov     rbx, [rsp+20h+arg_18]
0x1800021b1  not     rax
0x1800021b4  mov     cs:__security_cookie_complement, rax
0x1800021bb  add     rsp, 20h
0x1800021bf  pop     rbp
0x1800021c0  retn
```
