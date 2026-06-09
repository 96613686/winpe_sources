# __security_init_cookie

- ea: `0x180002fc4`
- end: `0x1800030a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002c30`

## callees

- `0x180002fc4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000304e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000304e`
- `KERNEL32!GetCurrentProcessId` at `0x18000300b`
- `KERNEL32!GetCurrentProcessId` at `0x18000300b`
- `KERNEL32!GetCurrentThreadId` at `0x180003017`
- `KERNEL32!GetCurrentThreadId` at `0x180003017`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002ffd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002ffd`
- `KERNEL32!GetTickCount` at `0x180003023`
- `KERNEL32!GetTickCount` at `0x180003033`
- `KERNEL32!GetTickCount` at `0x180003023`
- `KERNEL32!GetTickCount` at `0x180003033`

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
0x180002fc4  mov     [rsp-8+arg_18], rbx
0x180002fc9  push    rbp
0x180002fca  mov     rbp, rsp
0x180002fcd  sub     rsp, 20h
0x180002fd1  xor     eax, eax
0x180002fd3  mov     rbx, 2B992DDFA232h
0x180002fdd  mov     [rbp+arg_0], rax
0x180002fe1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002fe5  mov     qword ptr [rbp+PerformanceCount], rax
0x180002fe9  mov     rax, cs:__security_cookie
0x180002ff0  cmp     rax, rbx
0x180002ff3  jnz     loc_18000308C
0x180002ff9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002ffd  call    cs:__imp_GetSystemTimeAsFileTime
0x180003003  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003007  mov     [rbp+arg_0], rax
0x18000300b  call    cs:__imp_GetCurrentProcessId
0x180003011  mov     eax, eax
0x180003013  xor     [rbp+arg_0], rax
0x180003017  call    cs:__imp_GetCurrentThreadId
0x18000301d  mov     eax, eax
0x18000301f  xor     [rbp+arg_0], rax
0x180003023  call    cs:__imp_GetTickCount
0x180003029  mov     eax, eax
0x18000302b  shl     rax, 18h
0x18000302f  xor     [rbp+arg_0], rax
0x180003033  call    cs:__imp_GetTickCount
0x180003039  mov     eax, eax
0x18000303b  lea     rcx, [rbp+arg_0]
0x18000303f  xor     rax, [rbp+arg_0]
0x180003043  xor     rax, rcx
0x180003046  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000304a  mov     [rbp+arg_0], rax
0x18000304e  call    cs:__imp_QueryPerformanceCounter
0x180003054  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003057  mov     rcx, 0FFFFFFFFFFFFh
0x180003061  shl     rax, 20h
0x180003065  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003069  xor     rax, [rbp+arg_0]
0x18000306d  and     rax, rcx
0x180003070  mov     rcx, rax
0x180003073  cmp     rax, rbx
0x180003076  jnz     short loc_180003085
0x180003078  mov     rax, 2B992DDFA233h
0x180003082  mov     rcx, rax
0x180003085  mov     cs:__security_cookie, rcx
0x18000308c  mov     rbx, [rsp+20h+arg_18]
0x180003091  not     rax
0x180003094  mov     cs:__security_cookie_complement, rax
0x18000309b  add     rsp, 20h
0x18000309f  pop     rbp
0x1800030a0  retn
```
