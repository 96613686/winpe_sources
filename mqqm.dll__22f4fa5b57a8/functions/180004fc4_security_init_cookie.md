# __security_init_cookie

- ea: `0x180004fc4`
- end: `0x1800050a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004320`

## callees

- `0x180004fc4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000504e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000504e`
- `KERNEL32!GetCurrentThreadId` at `0x180005017`
- `KERNEL32!GetCurrentThreadId` at `0x180005017`
- `KERNEL32!GetCurrentProcessId` at `0x18000500b`
- `KERNEL32!GetCurrentProcessId` at `0x18000500b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004ffd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180004ffd`
- `KERNEL32!GetTickCount` at `0x180005023`
- `KERNEL32!GetTickCount` at `0x180005033`
- `KERNEL32!GetTickCount` at `0x180005023`
- `KERNEL32!GetTickCount` at `0x180005033`

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
0x180004fc4  mov     [rsp-8+arg_18], rbx
0x180004fc9  push    rbp
0x180004fca  mov     rbp, rsp
0x180004fcd  sub     rsp, 20h
0x180004fd1  xor     eax, eax
0x180004fd3  mov     rbx, 2B992DDFA232h
0x180004fdd  mov     [rbp+arg_0], rax
0x180004fe1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004fe5  mov     qword ptr [rbp+PerformanceCount], rax
0x180004fe9  mov     rax, cs:__security_cookie
0x180004ff0  cmp     rax, rbx
0x180004ff3  jnz     loc_18000508C
0x180004ff9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004ffd  call    cs:__imp_GetSystemTimeAsFileTime
0x180005003  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005007  mov     [rbp+arg_0], rax
0x18000500b  call    cs:__imp_GetCurrentProcessId
0x180005011  mov     eax, eax
0x180005013  xor     [rbp+arg_0], rax
0x180005017  call    cs:__imp_GetCurrentThreadId
0x18000501d  mov     eax, eax
0x18000501f  xor     [rbp+arg_0], rax
0x180005023  call    cs:__imp_GetTickCount
0x180005029  mov     eax, eax
0x18000502b  shl     rax, 18h
0x18000502f  xor     [rbp+arg_0], rax
0x180005033  call    cs:__imp_GetTickCount
0x180005039  mov     eax, eax
0x18000503b  lea     rcx, [rbp+arg_0]
0x18000503f  xor     rax, [rbp+arg_0]
0x180005043  xor     rax, rcx
0x180005046  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000504a  mov     [rbp+arg_0], rax
0x18000504e  call    cs:__imp_QueryPerformanceCounter
0x180005054  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005057  mov     rcx, 0FFFFFFFFFFFFh
0x180005061  shl     rax, 20h
0x180005065  xor     rax, qword ptr [rbp+PerformanceCount]
0x180005069  xor     rax, [rbp+arg_0]
0x18000506d  and     rax, rcx
0x180005070  mov     rcx, rax
0x180005073  cmp     rax, rbx
0x180005076  jnz     short loc_180005085
0x180005078  mov     rax, 2B992DDFA233h
0x180005082  mov     rcx, rax
0x180005085  mov     cs:__security_cookie, rcx
0x18000508c  mov     rbx, [rsp+20h+arg_18]
0x180005091  not     rax
0x180005094  mov     cs:__security_cookie_complement, rax
0x18000509b  add     rsp, 20h
0x18000509f  pop     rbp
0x1800050a0  retn
```
