# __security_init_cookie

- ea: `0x180001df4`
- end: `0x180001ed1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001610`

## callees

- `0x180001df4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001e47`
- `KERNEL32!GetCurrentThreadId` at `0x180001e47`
- `KERNEL32!GetCurrentProcessId` at `0x180001e3b`
- `KERNEL32!GetCurrentProcessId` at `0x180001e3b`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e7e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001e7e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e2d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e2d`
- `KERNEL32!GetTickCount` at `0x180001e53`
- `KERNEL32!GetTickCount` at `0x180001e63`
- `KERNEL32!GetTickCount` at `0x180001e53`
- `KERNEL32!GetTickCount` at `0x180001e63`

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
0x180001df4  mov     [rsp-8+arg_18], rbx
0x180001df9  push    rbp
0x180001dfa  mov     rbp, rsp
0x180001dfd  sub     rsp, 20h
0x180001e01  xor     eax, eax
0x180001e03  mov     rbx, 2B992DDFA232h
0x180001e0d  mov     [rbp+arg_0], rax
0x180001e11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001e15  mov     qword ptr [rbp+PerformanceCount], rax
0x180001e19  mov     rax, cs:__security_cookie
0x180001e20  cmp     rax, rbx
0x180001e23  jnz     loc_180001EBC
0x180001e29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e2d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001e33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001e37  mov     [rbp+arg_0], rax
0x180001e3b  call    cs:__imp_GetCurrentProcessId
0x180001e41  mov     eax, eax
0x180001e43  xor     [rbp+arg_0], rax
0x180001e47  call    cs:__imp_GetCurrentThreadId
0x180001e4d  mov     eax, eax
0x180001e4f  xor     [rbp+arg_0], rax
0x180001e53  call    cs:__imp_GetTickCount
0x180001e59  mov     eax, eax
0x180001e5b  shl     rax, 18h
0x180001e5f  xor     [rbp+arg_0], rax
0x180001e63  call    cs:__imp_GetTickCount
0x180001e69  mov     eax, eax
0x180001e6b  lea     rcx, [rbp+arg_0]
0x180001e6f  xor     rax, [rbp+arg_0]
0x180001e73  xor     rax, rcx
0x180001e76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001e7a  mov     [rbp+arg_0], rax
0x180001e7e  call    cs:__imp_QueryPerformanceCounter
0x180001e84  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001e87  mov     rcx, 0FFFFFFFFFFFFh
0x180001e91  shl     rax, 20h
0x180001e95  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001e99  xor     rax, [rbp+arg_0]
0x180001e9d  and     rax, rcx
0x180001ea0  mov     rcx, rax
0x180001ea3  cmp     rax, rbx
0x180001ea6  jnz     short loc_180001EB5
0x180001ea8  mov     rax, 2B992DDFA233h
0x180001eb2  mov     rcx, rax
0x180001eb5  mov     cs:__security_cookie, rcx
0x180001ebc  mov     rbx, [rsp+20h+arg_18]
0x180001ec1  not     rax
0x180001ec4  mov     cs:__security_cookie_complement, rax
0x180001ecb  add     rsp, 20h
0x180001ecf  pop     rbp
0x180001ed0  retn
```
