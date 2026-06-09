# __security_init_cookie

- ea: `0x1005492cc`
- end: `0x100549378`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x100548f30`

## callees

- `0x1005492cc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x100549312`
- `KERNEL32!GetCurrentProcessId` at `0x100549312`
- `KERNEL32!QueryPerformanceCounter` at `0x100549322`
- `KERNEL32!QueryPerformanceCounter` at `0x100549322`
- `KERNEL32!GetCurrentThreadId` at `0x100549306`
- `KERNEL32!GetCurrentThreadId` at `0x100549306`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005492f8`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1005492f8`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1005492cc  mov     [rsp-8+arg_18], rbx
0x1005492d1  push    rbp
0x1005492d2  mov     rbp, rsp
0x1005492d5  sub     rsp, 20h
0x1005492d9  mov     rax, cs:__security_cookie
0x1005492e0  mov     rbx, 2B992DDFA232h
0x1005492ea  cmp     rax, rbx
0x1005492ed  jnz     short loc_100549363
0x1005492ef  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1005492f4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1005492f8  call    cs:__imp_GetSystemTimeAsFileTime
0x1005492fe  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x100549302  mov     [rbp+arg_0], rax
0x100549306  call    cs:__imp_GetCurrentThreadId
0x10054930c  mov     eax, eax
0x10054930e  xor     [rbp+arg_0], rax
0x100549312  call    cs:__imp_GetCurrentProcessId
0x100549318  mov     eax, eax
0x10054931a  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x10054931e  xor     [rbp+arg_0], rax
0x100549322  call    cs:__imp_QueryPerformanceCounter
0x100549328  mov     eax, dword ptr [rbp+PerformanceCount]
0x10054932b  lea     rcx, [rbp+arg_0]
0x10054932f  shl     rax, 20h
0x100549333  xor     rax, qword ptr [rbp+PerformanceCount]
0x100549337  xor     rax, [rbp+arg_0]
0x10054933b  xor     rax, rcx
0x10054933e  mov     rcx, 0FFFFFFFFFFFFh
0x100549348  and     rax, rcx
0x10054934b  mov     rcx, 2B992DDFA233h
0x100549355  cmp     rax, rbx
0x100549358  cmovz   rax, rcx
0x10054935c  mov     cs:__security_cookie, rax
0x100549363  mov     rbx, [rsp+20h+arg_18]
0x100549368  not     rax
0x10054936b  mov     cs:__security_cookie_complement, rax
0x100549372  add     rsp, 20h
0x100549376  pop     rbp
0x100549377  retn
```
