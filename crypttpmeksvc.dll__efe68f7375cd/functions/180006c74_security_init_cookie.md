# __security_init_cookie

- ea: `0x180006c74`
- end: `0x180006d51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006740`

## callees

- `0x180006c74`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006cad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006cad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006cd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006ce3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006cd3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006ce3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006cbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180006cbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cc7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006cfe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006cfe`

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
0x180006c74  mov     [rsp-8+arg_18], rbx
0x180006c79  push    rbp
0x180006c7a  mov     rbp, rsp
0x180006c7d  sub     rsp, 20h
0x180006c81  xor     eax, eax
0x180006c83  mov     rbx, 2B992DDFA232h
0x180006c8d  mov     [rbp+arg_0], rax
0x180006c91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006c95  mov     qword ptr [rbp+PerformanceCount], rax
0x180006c99  mov     rax, cs:__security_cookie
0x180006ca0  cmp     rax, rbx
0x180006ca3  jnz     loc_180006D3C
0x180006ca9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006cad  call    cs:__imp_GetSystemTimeAsFileTime
0x180006cb3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180006cb7  mov     [rbp+arg_0], rax
0x180006cbb  call    cs:__imp_GetCurrentProcessId
0x180006cc1  mov     eax, eax
0x180006cc3  xor     [rbp+arg_0], rax
0x180006cc7  call    cs:__imp_GetCurrentThreadId
0x180006ccd  mov     eax, eax
0x180006ccf  xor     [rbp+arg_0], rax
0x180006cd3  call    cs:__imp_GetTickCount
0x180006cd9  mov     eax, eax
0x180006cdb  shl     rax, 18h
0x180006cdf  xor     [rbp+arg_0], rax
0x180006ce3  call    cs:__imp_GetTickCount
0x180006ce9  mov     eax, eax
0x180006ceb  lea     rcx, [rbp+arg_0]
0x180006cef  xor     rax, [rbp+arg_0]
0x180006cf3  xor     rax, rcx
0x180006cf6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180006cfa  mov     [rbp+arg_0], rax
0x180006cfe  call    cs:__imp_QueryPerformanceCounter
0x180006d04  mov     eax, dword ptr [rbp+PerformanceCount]
0x180006d07  mov     rcx, 0FFFFFFFFFFFFh
0x180006d11  shl     rax, 20h
0x180006d15  xor     rax, qword ptr [rbp+PerformanceCount]
0x180006d19  xor     rax, [rbp+arg_0]
0x180006d1d  and     rax, rcx
0x180006d20  mov     rcx, rax
0x180006d23  cmp     rax, rbx
0x180006d26  jnz     short loc_180006D35
0x180006d28  mov     rax, 2B992DDFA233h
0x180006d32  mov     rcx, rax
0x180006d35  mov     cs:__security_cookie, rcx
0x180006d3c  mov     rbx, [rsp+20h+arg_18]
0x180006d41  not     rax
0x180006d44  mov     cs:__security_cookie_complement, rax
0x180006d4b  add     rsp, 20h
0x180006d4f  pop     rbp
0x180006d50  retn
```
