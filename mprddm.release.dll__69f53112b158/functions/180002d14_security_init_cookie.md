# __security_init_cookie

- ea: `0x180002d14`
- end: `0x180002ded`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800024a0`

## callees

- `0x180002d14`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002d49`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002d49`
- `KERNEL32!GetCurrentProcessId` at `0x180002d57`
- `KERNEL32!GetCurrentProcessId` at `0x180002d57`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d9a`
- `KERNEL32!QueryPerformanceCounter` at `0x180002d9a`
- `KERNEL32!GetCurrentThreadId` at `0x180002d63`
- `KERNEL32!GetCurrentThreadId` at `0x180002d63`
- `KERNEL32!GetTickCount` at `0x180002d6f`
- `KERNEL32!GetTickCount` at `0x180002d7f`
- `KERNEL32!GetTickCount` at `0x180002d6f`
- `KERNEL32!GetTickCount` at `0x180002d7f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180002d14  mov     [rsp-8+arg_18], rbx
0x180002d19  push    rbp
0x180002d1a  mov     rbp, rsp
0x180002d1d  sub     rsp, 20h
0x180002d21  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180002d26  mov     rbx, 2B992DDFA232h
0x180002d30  and     qword ptr [rbp+PerformanceCount], 0
0x180002d35  mov     rax, cs:__security_cookie
0x180002d3c  cmp     rax, rbx
0x180002d3f  jnz     loc_180002DD8
0x180002d45  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002d49  call    cs:__imp_GetSystemTimeAsFileTime
0x180002d4f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002d53  mov     [rbp+arg_0], rax
0x180002d57  call    cs:__imp_GetCurrentProcessId
0x180002d5d  mov     eax, eax
0x180002d5f  xor     [rbp+arg_0], rax
0x180002d63  call    cs:__imp_GetCurrentThreadId
0x180002d69  mov     eax, eax
0x180002d6b  xor     [rbp+arg_0], rax
0x180002d6f  call    cs:__imp_GetTickCount
0x180002d75  mov     eax, eax
0x180002d77  shl     rax, 18h
0x180002d7b  xor     [rbp+arg_0], rax
0x180002d7f  call    cs:__imp_GetTickCount
0x180002d85  mov     eax, eax
0x180002d87  lea     rcx, [rbp+arg_0]
0x180002d8b  xor     rax, [rbp+arg_0]
0x180002d8f  xor     rax, rcx
0x180002d92  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002d96  mov     [rbp+arg_0], rax
0x180002d9a  call    cs:__imp_QueryPerformanceCounter
0x180002da0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002da3  mov     rcx, 0FFFFFFFFFFFFh
0x180002dad  shl     rax, 20h
0x180002db1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002db5  xor     rax, [rbp+arg_0]
0x180002db9  and     rax, rcx
0x180002dbc  mov     rcx, rax
0x180002dbf  cmp     rax, rbx
0x180002dc2  jnz     short loc_180002DD1
0x180002dc4  mov     rax, 2B992DDFA233h
0x180002dce  mov     rcx, rax
0x180002dd1  mov     cs:__security_cookie, rcx
0x180002dd8  mov     rbx, [rsp+20h+arg_18]
0x180002ddd  not     rax
0x180002de0  mov     cs:__security_cookie_complement, rax
0x180002de7  add     rsp, 20h
0x180002deb  pop     rbp
0x180002dec  retn
```
