# __security_init_cookie

- ea: `0x180002214`
- end: `0x1800022f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001860`

## callees

- `0x180002214`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002273`
- `KERNEL32!GetTickCount` at `0x180002283`
- `KERNEL32!GetTickCount` at `0x180002273`
- `KERNEL32!GetTickCount` at `0x180002283`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000224d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000224d`
- `KERNEL32!QueryPerformanceCounter` at `0x18000229e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000229e`
- `KERNEL32!GetCurrentThreadId` at `0x180002267`
- `KERNEL32!GetCurrentThreadId` at `0x180002267`
- `KERNEL32!GetCurrentProcessId` at `0x18000225b`
- `KERNEL32!GetCurrentProcessId` at `0x18000225b`

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
0x180002214  mov     [rsp-8+arg_18], rbx
0x180002219  push    rbp
0x18000221a  mov     rbp, rsp
0x18000221d  sub     rsp, 20h
0x180002221  xor     eax, eax
0x180002223  mov     rbx, 2B992DDFA232h
0x18000222d  mov     [rbp+arg_0], rax
0x180002231  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002235  mov     qword ptr [rbp+PerformanceCount], rax
0x180002239  mov     rax, cs:__security_cookie
0x180002240  cmp     rax, rbx
0x180002243  jnz     loc_1800022DC
0x180002249  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000224d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002253  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002257  mov     [rbp+arg_0], rax
0x18000225b  call    cs:__imp_GetCurrentProcessId
0x180002261  mov     eax, eax
0x180002263  xor     [rbp+arg_0], rax
0x180002267  call    cs:__imp_GetCurrentThreadId
0x18000226d  mov     eax, eax
0x18000226f  xor     [rbp+arg_0], rax
0x180002273  call    cs:__imp_GetTickCount
0x180002279  mov     eax, eax
0x18000227b  shl     rax, 18h
0x18000227f  xor     [rbp+arg_0], rax
0x180002283  call    cs:__imp_GetTickCount
0x180002289  mov     eax, eax
0x18000228b  lea     rcx, [rbp+arg_0]
0x18000228f  xor     rax, [rbp+arg_0]
0x180002293  xor     rax, rcx
0x180002296  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000229a  mov     [rbp+arg_0], rax
0x18000229e  call    cs:__imp_QueryPerformanceCounter
0x1800022a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800022a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800022b1  shl     rax, 20h
0x1800022b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800022b9  xor     rax, [rbp+arg_0]
0x1800022bd  and     rax, rcx
0x1800022c0  mov     rcx, rax
0x1800022c3  cmp     rax, rbx
0x1800022c6  jnz     short loc_1800022D5
0x1800022c8  mov     rax, 2B992DDFA233h
0x1800022d2  mov     rcx, rax
0x1800022d5  mov     cs:__security_cookie, rcx
0x1800022dc  mov     rbx, [rsp+20h+arg_18]
0x1800022e1  not     rax
0x1800022e4  mov     cs:__security_cookie_complement, rax
0x1800022eb  add     rsp, 20h
0x1800022ef  pop     rbp
0x1800022f0  retn
```
