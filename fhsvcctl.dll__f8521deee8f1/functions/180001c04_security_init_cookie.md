# __security_init_cookie

- ea: `0x180001c04`
- end: `0x180001ce1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001870`

## callees

- `0x180001c04`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001c63`
- `KERNEL32!GetTickCount` at `0x180001c73`
- `KERNEL32!GetTickCount` at `0x180001c63`
- `KERNEL32!GetTickCount` at `0x180001c73`
- `KERNEL32!QueryPerformanceCounter` at `0x180001c8e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001c8e`
- `KERNEL32!GetCurrentProcessId` at `0x180001c4b`
- `KERNEL32!GetCurrentProcessId` at `0x180001c4b`
- `KERNEL32!GetCurrentThreadId` at `0x180001c57`
- `KERNEL32!GetCurrentThreadId` at `0x180001c57`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c3d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c3d`

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
0x180001c04  mov     [rsp-8+arg_18], rbx
0x180001c09  push    rbp
0x180001c0a  mov     rbp, rsp
0x180001c0d  sub     rsp, 20h
0x180001c11  xor     eax, eax
0x180001c13  mov     rbx, 2B992DDFA232h
0x180001c1d  mov     [rbp+arg_0], rax
0x180001c21  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c25  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c29  mov     rax, cs:__security_cookie
0x180001c30  cmp     rax, rbx
0x180001c33  jnz     loc_180001CCC
0x180001c39  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001c3d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c43  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001c47  mov     [rbp+arg_0], rax
0x180001c4b  call    cs:__imp_GetCurrentProcessId
0x180001c51  mov     eax, eax
0x180001c53  xor     [rbp+arg_0], rax
0x180001c57  call    cs:__imp_GetCurrentThreadId
0x180001c5d  mov     eax, eax
0x180001c5f  xor     [rbp+arg_0], rax
0x180001c63  call    cs:__imp_GetTickCount
0x180001c69  mov     eax, eax
0x180001c6b  shl     rax, 18h
0x180001c6f  xor     [rbp+arg_0], rax
0x180001c73  call    cs:__imp_GetTickCount
0x180001c79  mov     eax, eax
0x180001c7b  lea     rcx, [rbp+arg_0]
0x180001c7f  xor     rax, [rbp+arg_0]
0x180001c83  xor     rax, rcx
0x180001c86  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c8a  mov     [rbp+arg_0], rax
0x180001c8e  call    cs:__imp_QueryPerformanceCounter
0x180001c94  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c97  mov     rcx, 0FFFFFFFFFFFFh
0x180001ca1  shl     rax, 20h
0x180001ca5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ca9  xor     rax, [rbp+arg_0]
0x180001cad  and     rax, rcx
0x180001cb0  mov     rcx, rax
0x180001cb3  cmp     rax, rbx
0x180001cb6  jnz     short loc_180001CC5
0x180001cb8  mov     rax, 2B992DDFA233h
0x180001cc2  mov     rcx, rax
0x180001cc5  mov     cs:__security_cookie, rcx
0x180001ccc  mov     rbx, [rsp+20h+arg_18]
0x180001cd1  not     rax
0x180001cd4  mov     cs:__security_cookie_complement, rax
0x180001cdb  add     rsp, 20h
0x180001cdf  pop     rbp
0x180001ce0  retn
```
