# __security_init_cookie

- ea: `0x180003644`
- end: `0x180003721`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002ad0`

## callees

- `0x180003644`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800036ce`
- `KERNEL32!QueryPerformanceCounter` at `0x1800036ce`
- `KERNEL32!GetCurrentThreadId` at `0x180003697`
- `KERNEL32!GetCurrentThreadId` at `0x180003697`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000367d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000367d`
- `KERNEL32!GetTickCount` at `0x1800036a3`
- `KERNEL32!GetTickCount` at `0x1800036b3`
- `KERNEL32!GetTickCount` at `0x1800036a3`
- `KERNEL32!GetTickCount` at `0x1800036b3`
- `KERNEL32!GetCurrentProcessId` at `0x18000368b`
- `KERNEL32!GetCurrentProcessId` at `0x18000368b`

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
0x180003644  mov     [rsp-8+arg_18], rbx
0x180003649  push    rbp
0x18000364a  mov     rbp, rsp
0x18000364d  sub     rsp, 20h
0x180003651  xor     eax, eax
0x180003653  mov     rbx, 2B992DDFA232h
0x18000365d  mov     [rbp+arg_0], rax
0x180003661  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180003665  mov     qword ptr [rbp+PerformanceCount], rax
0x180003669  mov     rax, cs:__security_cookie
0x180003670  cmp     rax, rbx
0x180003673  jnz     loc_18000370C
0x180003679  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000367d  call    cs:__imp_GetSystemTimeAsFileTime
0x180003683  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003687  mov     [rbp+arg_0], rax
0x18000368b  call    cs:__imp_GetCurrentProcessId
0x180003691  mov     eax, eax
0x180003693  xor     [rbp+arg_0], rax
0x180003697  call    cs:__imp_GetCurrentThreadId
0x18000369d  mov     eax, eax
0x18000369f  xor     [rbp+arg_0], rax
0x1800036a3  call    cs:__imp_GetTickCount
0x1800036a9  mov     eax, eax
0x1800036ab  shl     rax, 18h
0x1800036af  xor     [rbp+arg_0], rax
0x1800036b3  call    cs:__imp_GetTickCount
0x1800036b9  mov     eax, eax
0x1800036bb  lea     rcx, [rbp+arg_0]
0x1800036bf  xor     rax, [rbp+arg_0]
0x1800036c3  xor     rax, rcx
0x1800036c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800036ca  mov     [rbp+arg_0], rax
0x1800036ce  call    cs:__imp_QueryPerformanceCounter
0x1800036d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800036d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800036e1  shl     rax, 20h
0x1800036e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800036e9  xor     rax, [rbp+arg_0]
0x1800036ed  and     rax, rcx
0x1800036f0  mov     rcx, rax
0x1800036f3  cmp     rax, rbx
0x1800036f6  jnz     short loc_180003705
0x1800036f8  mov     rax, 2B992DDFA233h
0x180003702  mov     rcx, rax
0x180003705  mov     cs:__security_cookie, rcx
0x18000370c  mov     rbx, [rsp+20h+arg_18]
0x180003711  not     rax
0x180003714  mov     cs:__security_cookie_complement, rax
0x18000371b  add     rsp, 20h
0x18000371f  pop     rbp
0x180003720  retn
```
