# __security_init_cookie

- ea: `0x140009cc8`
- end: `0x140009da5`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cc20`

## callees

- `0x140009cc8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140009d1b`
- `KERNEL32!GetCurrentThreadId` at `0x140009d1b`
- `KERNEL32!GetCurrentProcessId` at `0x140009d0f`
- `KERNEL32!GetCurrentProcessId` at `0x140009d0f`
- `KERNEL32!QueryPerformanceCounter` at `0x140009d52`
- `KERNEL32!QueryPerformanceCounter` at `0x140009d52`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140009d01`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140009d01`
- `KERNEL32!GetTickCount` at `0x140009d27`
- `KERNEL32!GetTickCount` at `0x140009d37`
- `KERNEL32!GetTickCount` at `0x140009d27`
- `KERNEL32!GetTickCount` at `0x140009d37`

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
0x140009cc8  mov     [rsp-8+arg_18], rbx
0x140009ccd  push    rbp
0x140009cce  mov     rbp, rsp
0x140009cd1  sub     rsp, 20h
0x140009cd5  xor     eax, eax
0x140009cd7  mov     rbx, 2B992DDFA232h
0x140009ce1  mov     [rbp+arg_0], rax
0x140009ce5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140009ce9  mov     qword ptr [rbp+PerformanceCount], rax
0x140009ced  mov     rax, cs:__security_cookie
0x140009cf4  cmp     rax, rbx
0x140009cf7  jnz     loc_140009D90
0x140009cfd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140009d01  call    cs:__imp_GetSystemTimeAsFileTime
0x140009d07  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140009d0b  mov     [rbp+arg_0], rax
0x140009d0f  call    cs:__imp_GetCurrentProcessId
0x140009d15  mov     eax, eax
0x140009d17  xor     [rbp+arg_0], rax
0x140009d1b  call    cs:__imp_GetCurrentThreadId
0x140009d21  mov     eax, eax
0x140009d23  xor     [rbp+arg_0], rax
0x140009d27  call    cs:__imp_GetTickCount
0x140009d2d  mov     eax, eax
0x140009d2f  shl     rax, 18h
0x140009d33  xor     [rbp+arg_0], rax
0x140009d37  call    cs:__imp_GetTickCount
0x140009d3d  mov     eax, eax
0x140009d3f  lea     rcx, [rbp+arg_0]
0x140009d43  xor     rax, [rbp+arg_0]
0x140009d47  xor     rax, rcx
0x140009d4a  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140009d4e  mov     [rbp+arg_0], rax
0x140009d52  call    cs:__imp_QueryPerformanceCounter
0x140009d58  mov     eax, dword ptr [rbp+PerformanceCount]
0x140009d5b  mov     rcx, 0FFFFFFFFFFFFh
0x140009d65  shl     rax, 20h
0x140009d69  xor     rax, qword ptr [rbp+PerformanceCount]
0x140009d6d  xor     rax, [rbp+arg_0]
0x140009d71  and     rax, rcx
0x140009d74  mov     rcx, rax
0x140009d77  cmp     rax, rbx
0x140009d7a  jnz     short loc_140009D89
0x140009d7c  mov     rax, 2B992DDFA233h
0x140009d86  mov     rcx, rax
0x140009d89  mov     cs:__security_cookie, rcx
0x140009d90  mov     rbx, [rsp+20h+arg_18]
0x140009d95  not     rax
0x140009d98  mov     cs:__security_cookie_complement, rax
0x140009d9f  add     rsp, 20h
0x140009da3  pop     rbp
0x140009da4  retn
```
