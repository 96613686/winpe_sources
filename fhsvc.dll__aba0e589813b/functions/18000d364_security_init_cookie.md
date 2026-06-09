# __security_init_cookie

- ea: `0x18000d364`
- end: `0x18000d441`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000cde0`

## callees

- `0x18000d364`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000d3ee`
- `KERNEL32!QueryPerformanceCounter` at `0x18000d3ee`
- `KERNEL32!GetCurrentProcessId` at `0x18000d3ab`
- `KERNEL32!GetCurrentProcessId` at `0x18000d3ab`
- `KERNEL32!GetCurrentThreadId` at `0x18000d3b7`
- `KERNEL32!GetCurrentThreadId` at `0x18000d3b7`
- `KERNEL32!GetTickCount` at `0x18000d3c3`
- `KERNEL32!GetTickCount` at `0x18000d3d3`
- `KERNEL32!GetTickCount` at `0x18000d3c3`
- `KERNEL32!GetTickCount` at `0x18000d3d3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d39d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000d39d`

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
0x18000d364  mov     [rsp-8+arg_18], rbx
0x18000d369  push    rbp
0x18000d36a  mov     rbp, rsp
0x18000d36d  sub     rsp, 20h
0x18000d371  xor     eax, eax
0x18000d373  mov     rbx, 2B992DDFA232h
0x18000d37d  mov     [rbp+arg_0], rax
0x18000d381  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d385  mov     qword ptr [rbp+PerformanceCount], rax
0x18000d389  mov     rax, cs:__security_cookie
0x18000d390  cmp     rax, rbx
0x18000d393  jnz     loc_18000D42C
0x18000d399  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d39d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d3a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d3a7  mov     [rbp+arg_0], rax
0x18000d3ab  call    cs:__imp_GetCurrentProcessId
0x18000d3b1  mov     eax, eax
0x18000d3b3  xor     [rbp+arg_0], rax
0x18000d3b7  call    cs:__imp_GetCurrentThreadId
0x18000d3bd  mov     eax, eax
0x18000d3bf  xor     [rbp+arg_0], rax
0x18000d3c3  call    cs:__imp_GetTickCount
0x18000d3c9  mov     eax, eax
0x18000d3cb  shl     rax, 18h
0x18000d3cf  xor     [rbp+arg_0], rax
0x18000d3d3  call    cs:__imp_GetTickCount
0x18000d3d9  mov     eax, eax
0x18000d3db  lea     rcx, [rbp+arg_0]
0x18000d3df  xor     rax, [rbp+arg_0]
0x18000d3e3  xor     rax, rcx
0x18000d3e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000d3ea  mov     [rbp+arg_0], rax
0x18000d3ee  call    cs:__imp_QueryPerformanceCounter
0x18000d3f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000d3f7  mov     rcx, 0FFFFFFFFFFFFh
0x18000d401  shl     rax, 20h
0x18000d405  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000d409  xor     rax, [rbp+arg_0]
0x18000d40d  and     rax, rcx
0x18000d410  mov     rcx, rax
0x18000d413  cmp     rax, rbx
0x18000d416  jnz     short loc_18000D425
0x18000d418  mov     rax, 2B992DDFA233h
0x18000d422  mov     rcx, rax
0x18000d425  mov     cs:__security_cookie, rcx
0x18000d42c  mov     rbx, [rsp+20h+arg_18]
0x18000d431  not     rax
0x18000d434  mov     cs:__security_cookie_complement, rax
0x18000d43b  add     rsp, 20h
0x18000d43f  pop     rbp
0x18000d440  retn
```
