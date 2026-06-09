# __security_init_cookie

- ea: `0x1800020c4`
- end: `0x1800021a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800017f0`

## callees

- `0x1800020c4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002123`
- `KERNEL32!GetTickCount` at `0x180002133`
- `KERNEL32!GetTickCount` at `0x180002123`
- `KERNEL32!GetTickCount` at `0x180002133`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020fd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800020fd`
- `KERNEL32!GetCurrentProcessId` at `0x18000210b`
- `KERNEL32!GetCurrentProcessId` at `0x18000210b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000214e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000214e`
- `KERNEL32!GetCurrentThreadId` at `0x180002117`
- `KERNEL32!GetCurrentThreadId` at `0x180002117`

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
0x1800020c4  mov     [rsp-8+arg_18], rbx
0x1800020c9  push    rbp
0x1800020ca  mov     rbp, rsp
0x1800020cd  sub     rsp, 20h
0x1800020d1  xor     eax, eax
0x1800020d3  mov     rbx, 2B992DDFA232h
0x1800020dd  mov     [rbp+arg_0], rax
0x1800020e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800020e5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800020e9  mov     rax, cs:__security_cookie
0x1800020f0  cmp     rax, rbx
0x1800020f3  jnz     loc_18000218C
0x1800020f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800020fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180002103  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002107  mov     [rbp+arg_0], rax
0x18000210b  call    cs:__imp_GetCurrentProcessId
0x180002111  mov     eax, eax
0x180002113  xor     [rbp+arg_0], rax
0x180002117  call    cs:__imp_GetCurrentThreadId
0x18000211d  mov     eax, eax
0x18000211f  xor     [rbp+arg_0], rax
0x180002123  call    cs:__imp_GetTickCount
0x180002129  mov     eax, eax
0x18000212b  shl     rax, 18h
0x18000212f  xor     [rbp+arg_0], rax
0x180002133  call    cs:__imp_GetTickCount
0x180002139  mov     eax, eax
0x18000213b  lea     rcx, [rbp+arg_0]
0x18000213f  xor     rax, [rbp+arg_0]
0x180002143  xor     rax, rcx
0x180002146  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000214a  mov     [rbp+arg_0], rax
0x18000214e  call    cs:__imp_QueryPerformanceCounter
0x180002154  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002157  mov     rcx, 0FFFFFFFFFFFFh
0x180002161  shl     rax, 20h
0x180002165  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002169  xor     rax, [rbp+arg_0]
0x18000216d  and     rax, rcx
0x180002170  mov     rcx, rax
0x180002173  cmp     rax, rbx
0x180002176  jnz     short loc_180002185
0x180002178  mov     rax, 2B992DDFA233h
0x180002182  mov     rcx, rax
0x180002185  mov     cs:__security_cookie, rcx
0x18000218c  mov     rbx, [rsp+20h+arg_18]
0x180002191  not     rax
0x180002194  mov     cs:__security_cookie_complement, rax
0x18000219b  add     rsp, 20h
0x18000219f  pop     rbp
0x1800021a0  retn
```
