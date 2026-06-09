# __security_init_cookie

- ea: `0x180001954`
- end: `0x180001a31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001340`

## callees

- `0x180001954`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000199b`
- `KERNEL32!GetCurrentProcessId` at `0x18000199b`
- `KERNEL32!QueryPerformanceCounter` at `0x1800019de`
- `KERNEL32!QueryPerformanceCounter` at `0x1800019de`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000198d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000198d`
- `KERNEL32!GetTickCount` at `0x1800019b3`
- `KERNEL32!GetTickCount` at `0x1800019c3`
- `KERNEL32!GetTickCount` at `0x1800019b3`
- `KERNEL32!GetTickCount` at `0x1800019c3`
- `KERNEL32!GetCurrentThreadId` at `0x1800019a7`
- `KERNEL32!GetCurrentThreadId` at `0x1800019a7`

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
0x180001954  mov     [rsp-8+arg_18], rbx
0x180001959  push    rbp
0x18000195a  mov     rbp, rsp
0x18000195d  sub     rsp, 20h
0x180001961  xor     eax, eax
0x180001963  mov     rbx, 2B992DDFA232h
0x18000196d  mov     [rbp+arg_0], rax
0x180001971  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001975  mov     qword ptr [rbp+PerformanceCount], rax
0x180001979  mov     rax, cs:__security_cookie
0x180001980  cmp     rax, rbx
0x180001983  jnz     loc_180001A1C
0x180001989  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000198d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001993  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001997  mov     [rbp+arg_0], rax
0x18000199b  call    cs:__imp_GetCurrentProcessId
0x1800019a1  mov     eax, eax
0x1800019a3  xor     [rbp+arg_0], rax
0x1800019a7  call    cs:__imp_GetCurrentThreadId
0x1800019ad  mov     eax, eax
0x1800019af  xor     [rbp+arg_0], rax
0x1800019b3  call    cs:__imp_GetTickCount
0x1800019b9  mov     eax, eax
0x1800019bb  shl     rax, 18h
0x1800019bf  xor     [rbp+arg_0], rax
0x1800019c3  call    cs:__imp_GetTickCount
0x1800019c9  mov     eax, eax
0x1800019cb  lea     rcx, [rbp+arg_0]
0x1800019cf  xor     rax, [rbp+arg_0]
0x1800019d3  xor     rax, rcx
0x1800019d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800019da  mov     [rbp+arg_0], rax
0x1800019de  call    cs:__imp_QueryPerformanceCounter
0x1800019e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800019e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800019f1  shl     rax, 20h
0x1800019f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800019f9  xor     rax, [rbp+arg_0]
0x1800019fd  and     rax, rcx
0x180001a00  mov     rcx, rax
0x180001a03  cmp     rax, rbx
0x180001a06  jnz     short loc_180001A15
0x180001a08  mov     rax, 2B992DDFA233h
0x180001a12  mov     rcx, rax
0x180001a15  mov     cs:__security_cookie, rcx
0x180001a1c  mov     rbx, [rsp+20h+arg_18]
0x180001a21  not     rax
0x180001a24  mov     cs:__security_cookie_complement, rax
0x180001a2b  add     rsp, 20h
0x180001a2f  pop     rbp
0x180001a30  retn
```
