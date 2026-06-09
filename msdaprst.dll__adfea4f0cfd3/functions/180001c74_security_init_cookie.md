# __security_init_cookie

- ea: `0x180001c74`
- end: `0x180001d51`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001390`

## callees

- `0x180001c74`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001cd3`
- `KERNEL32!GetTickCount` at `0x180001ce3`
- `KERNEL32!GetTickCount` at `0x180001cd3`
- `KERNEL32!GetTickCount` at `0x180001ce3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001cad`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001cad`
- `KERNEL32!QueryPerformanceCounter` at `0x180001cfe`
- `KERNEL32!QueryPerformanceCounter` at `0x180001cfe`
- `KERNEL32!GetCurrentProcessId` at `0x180001cbb`
- `KERNEL32!GetCurrentProcessId` at `0x180001cbb`
- `KERNEL32!GetCurrentThreadId` at `0x180001cc7`
- `KERNEL32!GetCurrentThreadId` at `0x180001cc7`

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
0x180001c74  mov     [rsp-8+arg_18], rbx
0x180001c79  push    rbp
0x180001c7a  mov     rbp, rsp
0x180001c7d  sub     rsp, 20h
0x180001c81  xor     eax, eax
0x180001c83  mov     rbx, 2B992DDFA232h
0x180001c8d  mov     [rbp+arg_0], rax
0x180001c91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c95  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c99  mov     rax, cs:__security_cookie
0x180001ca0  cmp     rax, rbx
0x180001ca3  jnz     loc_180001D3C
0x180001ca9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001cad  call    cs:__imp_GetSystemTimeAsFileTime
0x180001cb3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001cb7  mov     [rbp+arg_0], rax
0x180001cbb  call    cs:__imp_GetCurrentProcessId
0x180001cc1  mov     eax, eax
0x180001cc3  xor     [rbp+arg_0], rax
0x180001cc7  call    cs:__imp_GetCurrentThreadId
0x180001ccd  mov     eax, eax
0x180001ccf  xor     [rbp+arg_0], rax
0x180001cd3  call    cs:__imp_GetTickCount
0x180001cd9  mov     eax, eax
0x180001cdb  shl     rax, 18h
0x180001cdf  xor     [rbp+arg_0], rax
0x180001ce3  call    cs:__imp_GetTickCount
0x180001ce9  mov     eax, eax
0x180001ceb  lea     rcx, [rbp+arg_0]
0x180001cef  xor     rax, [rbp+arg_0]
0x180001cf3  xor     rax, rcx
0x180001cf6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001cfa  mov     [rbp+arg_0], rax
0x180001cfe  call    cs:__imp_QueryPerformanceCounter
0x180001d04  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001d07  mov     rcx, 0FFFFFFFFFFFFh
0x180001d11  shl     rax, 20h
0x180001d15  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001d19  xor     rax, [rbp+arg_0]
0x180001d1d  and     rax, rcx
0x180001d20  mov     rcx, rax
0x180001d23  cmp     rax, rbx
0x180001d26  jnz     short loc_180001D35
0x180001d28  mov     rax, 2B992DDFA233h
0x180001d32  mov     rcx, rax
0x180001d35  mov     cs:__security_cookie, rcx
0x180001d3c  mov     rbx, [rsp+20h+arg_18]
0x180001d41  not     rax
0x180001d44  mov     cs:__security_cookie_complement, rax
0x180001d4b  add     rsp, 20h
0x180001d4f  pop     rbp
0x180001d50  retn
```
