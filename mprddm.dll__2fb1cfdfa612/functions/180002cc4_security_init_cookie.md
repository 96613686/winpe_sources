# __security_init_cookie

- ea: `0x180002cc4`
- end: `0x180002da1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002450`

## callees

- `0x180002cc4`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002cfd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002cfd`
- `KERNEL32!GetCurrentProcessId` at `0x180002d0b`
- `KERNEL32!GetCurrentProcessId` at `0x180002d0b`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d4e`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d4e`
- `KERNEL32!GetCurrentThreadId` at `0x180002d17`
- `KERNEL32!GetCurrentThreadId` at `0x180002d17`
- `KERNEL32!GetTickCount` at `0x180002d23`
- `KERNEL32!GetTickCount` at `0x180002d33`
- `KERNEL32!GetTickCount` at `0x180002d23`
- `KERNEL32!GetTickCount` at `0x180002d33`

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
0x180002cc4  mov     [rsp-8+arg_18], rbx
0x180002cc9  push    rbp
0x180002cca  mov     rbp, rsp
0x180002ccd  sub     rsp, 20h
0x180002cd1  xor     eax, eax
0x180002cd3  mov     rbx, 2B992DDFA232h
0x180002cdd  mov     [rbp+arg_0], rax
0x180002ce1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002ce5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002ce9  mov     rax, cs:__security_cookie
0x180002cf0  cmp     rax, rbx
0x180002cf3  jnz     loc_180002D8C
0x180002cf9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002cfd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002d03  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002d07  mov     [rbp+arg_0], rax
0x180002d0b  call    cs:__imp_GetCurrentProcessId
0x180002d11  mov     eax, eax
0x180002d13  xor     [rbp+arg_0], rax
0x180002d17  call    cs:__imp_GetCurrentThreadId
0x180002d1d  mov     eax, eax
0x180002d1f  xor     [rbp+arg_0], rax
0x180002d23  call    cs:__imp_GetTickCount
0x180002d29  mov     eax, eax
0x180002d2b  shl     rax, 18h
0x180002d2f  xor     [rbp+arg_0], rax
0x180002d33  call    cs:__imp_GetTickCount
0x180002d39  mov     eax, eax
0x180002d3b  lea     rcx, [rbp+arg_0]
0x180002d3f  xor     rax, [rbp+arg_0]
0x180002d43  xor     rax, rcx
0x180002d46  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002d4a  mov     [rbp+arg_0], rax
0x180002d4e  call    cs:__imp_QueryPerformanceCounter
0x180002d54  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002d57  mov     rcx, 0FFFFFFFFFFFFh
0x180002d61  shl     rax, 20h
0x180002d65  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002d69  xor     rax, [rbp+arg_0]
0x180002d6d  and     rax, rcx
0x180002d70  mov     rcx, rax
0x180002d73  cmp     rax, rbx
0x180002d76  jnz     short loc_180002D85
0x180002d78  mov     rax, 2B992DDFA233h
0x180002d82  mov     rcx, rax
0x180002d85  mov     cs:__security_cookie, rcx
0x180002d8c  mov     rbx, [rsp+20h+arg_18]
0x180002d91  not     rax
0x180002d94  mov     cs:__security_cookie_complement, rax
0x180002d9b  add     rsp, 20h
0x180002d9f  pop     rbp
0x180002da0  retn
```
