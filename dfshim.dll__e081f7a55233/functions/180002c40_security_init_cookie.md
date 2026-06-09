# __security_init_cookie

- ea: `0x180002c40`
- end: `0x180002d1d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001024`
- `0x180001070`

## callees

- `0x180002c40`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180002c93`
- `KERNEL32!GetCurrentThreadId` at `0x180002c93`
- `KERNEL32!QueryPerformanceCounter` at `0x180002cca`
- `KERNEL32!QueryPerformanceCounter` at `0x180002cca`
- `KERNEL32!GetCurrentProcessId` at `0x180002c87`
- `KERNEL32!GetCurrentProcessId` at `0x180002c87`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002c79`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002c79`
- `KERNEL32!GetTickCount` at `0x180002c9f`
- `KERNEL32!GetTickCount` at `0x180002caf`
- `KERNEL32!GetTickCount` at `0x180002c9f`
- `KERNEL32!GetTickCount` at `0x180002caf`

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
0x180002c40  mov     [rsp-8+arg_18], rbx
0x180002c45  push    rbp
0x180002c46  mov     rbp, rsp
0x180002c49  sub     rsp, 20h
0x180002c4d  xor     eax, eax
0x180002c4f  mov     rbx, 2B992DDFA232h
0x180002c59  mov     [rbp+arg_0], rax
0x180002c5d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002c61  mov     qword ptr [rbp+PerformanceCount], rax
0x180002c65  mov     rax, cs:__security_cookie
0x180002c6c  cmp     rax, rbx
0x180002c6f  jnz     loc_180002D08
0x180002c75  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002c79  call    cs:__imp_GetSystemTimeAsFileTime
0x180002c7f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002c83  mov     [rbp+arg_0], rax
0x180002c87  call    cs:__imp_GetCurrentProcessId
0x180002c8d  mov     eax, eax
0x180002c8f  xor     [rbp+arg_0], rax
0x180002c93  call    cs:__imp_GetCurrentThreadId
0x180002c99  mov     eax, eax
0x180002c9b  xor     [rbp+arg_0], rax
0x180002c9f  call    cs:__imp_GetTickCount
0x180002ca5  mov     eax, eax
0x180002ca7  shl     rax, 18h
0x180002cab  xor     [rbp+arg_0], rax
0x180002caf  call    cs:__imp_GetTickCount
0x180002cb5  mov     eax, eax
0x180002cb7  lea     rcx, [rbp+arg_0]
0x180002cbb  xor     rax, [rbp+arg_0]
0x180002cbf  xor     rax, rcx
0x180002cc2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002cc6  mov     [rbp+arg_0], rax
0x180002cca  call    cs:__imp_QueryPerformanceCounter
0x180002cd0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002cd3  mov     rcx, 0FFFFFFFFFFFFh
0x180002cdd  shl     rax, 20h
0x180002ce1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002ce5  xor     rax, [rbp+arg_0]
0x180002ce9  and     rax, rcx
0x180002cec  mov     rcx, rax
0x180002cef  cmp     rax, rbx
0x180002cf2  jnz     short loc_180002D01
0x180002cf4  mov     rax, 2B992DDFA233h
0x180002cfe  mov     rcx, rax
0x180002d01  mov     cs:__security_cookie, rcx
0x180002d08  mov     rbx, [rsp+20h+arg_18]
0x180002d0d  not     rax
0x180002d10  mov     cs:__security_cookie_complement, rax
0x180002d17  add     rsp, 20h
0x180002d1b  pop     rbp
0x180002d1c  retn
```
