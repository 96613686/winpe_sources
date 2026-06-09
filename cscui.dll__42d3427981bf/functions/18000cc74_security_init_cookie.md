# __security_init_cookie

- ea: `0x18000cc74`
- end: `0x18000cd51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000c4b0`

## callees

- `0x18000cc74`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ccbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000ccbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ccc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ccad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000ccad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ccd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000cce3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000ccd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000cce3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ccfe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000ccfe`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x18000cc74  mov     [rsp-8+arg_18], rbx
0x18000cc79  push    rbp
0x18000cc7a  mov     rbp, rsp
0x18000cc7d  sub     rsp, 20h
0x18000cc81  xor     eax, eax
0x18000cc83  mov     rbx, 2B992DDFA232h
0x18000cc8d  mov     [rbp+arg_0], rax
0x18000cc91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000cc95  mov     qword ptr [rbp+PerformanceCount], rax
0x18000cc99  mov     rax, cs:__security_cookie
0x18000cca0  cmp     rax, rbx
0x18000cca3  jnz     loc_18000CD3C
0x18000cca9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000ccad  call    cs:__imp_GetSystemTimeAsFileTime
0x18000ccb3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000ccb7  mov     [rbp+arg_0], rax
0x18000ccbb  call    cs:__imp_GetCurrentProcessId
0x18000ccc1  mov     eax, eax
0x18000ccc3  xor     [rbp+arg_0], rax
0x18000ccc7  call    cs:__imp_GetCurrentThreadId
0x18000cccd  mov     eax, eax
0x18000cccf  xor     [rbp+arg_0], rax
0x18000ccd3  call    cs:__imp_GetTickCount
0x18000ccd9  mov     eax, eax
0x18000ccdb  shl     rax, 18h
0x18000ccdf  xor     [rbp+arg_0], rax
0x18000cce3  call    cs:__imp_GetTickCount
0x18000cce9  mov     eax, eax
0x18000cceb  lea     rcx, [rbp+arg_0]
0x18000ccef  xor     rax, [rbp+arg_0]
0x18000ccf3  xor     rax, rcx
0x18000ccf6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000ccfa  mov     [rbp+arg_0], rax
0x18000ccfe  call    cs:__imp_QueryPerformanceCounter
0x18000cd04  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000cd07  mov     rcx, 0FFFFFFFFFFFFh
0x18000cd11  shl     rax, 20h
0x18000cd15  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000cd19  xor     rax, [rbp+arg_0]
0x18000cd1d  and     rax, rcx
0x18000cd20  mov     rcx, rax
0x18000cd23  cmp     rax, rbx
0x18000cd26  jnz     short loc_18000CD35
0x18000cd28  mov     rax, 2B992DDFA233h
0x18000cd32  mov     rcx, rax
0x18000cd35  mov     cs:__security_cookie, rcx
0x18000cd3c  mov     rbx, [rsp+20h+arg_18]
0x18000cd41  not     rax
0x18000cd44  mov     cs:__security_cookie_complement, rax
0x18000cd4b  add     rsp, 20h
0x18000cd4f  pop     rbp
0x18000cd50  retn
```
