# __security_init_cookie

- ea: `0x180002454`
- end: `0x180002531`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c90`

## callees

- `0x180002454`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800024a7`
- `KERNEL32!GetCurrentThreadId` at `0x1800024a7`
- `KERNEL32!GetCurrentProcessId` at `0x18000249b`
- `KERNEL32!GetCurrentProcessId` at `0x18000249b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000248d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000248d`
- `KERNEL32!GetTickCount` at `0x1800024b3`
- `KERNEL32!GetTickCount` at `0x1800024c3`
- `KERNEL32!GetTickCount` at `0x1800024b3`
- `KERNEL32!GetTickCount` at `0x1800024c3`
- `KERNEL32!QueryPerformanceCounter` at `0x1800024de`
- `KERNEL32!QueryPerformanceCounter` at `0x1800024de`

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
0x180002454  mov     [rsp-8+arg_18], rbx
0x180002459  push    rbp
0x18000245a  mov     rbp, rsp
0x18000245d  sub     rsp, 20h
0x180002461  xor     eax, eax
0x180002463  mov     rbx, 2B992DDFA232h
0x18000246d  mov     [rbp+arg_0], rax
0x180002471  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002475  mov     qword ptr [rbp+PerformanceCount], rax
0x180002479  mov     rax, cs:__security_cookie
0x180002480  cmp     rax, rbx
0x180002483  jnz     loc_18000251C
0x180002489  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000248d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002493  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002497  mov     [rbp+arg_0], rax
0x18000249b  call    cs:__imp_GetCurrentProcessId
0x1800024a1  mov     eax, eax
0x1800024a3  xor     [rbp+arg_0], rax
0x1800024a7  call    cs:__imp_GetCurrentThreadId
0x1800024ad  mov     eax, eax
0x1800024af  xor     [rbp+arg_0], rax
0x1800024b3  call    cs:__imp_GetTickCount
0x1800024b9  mov     eax, eax
0x1800024bb  shl     rax, 18h
0x1800024bf  xor     [rbp+arg_0], rax
0x1800024c3  call    cs:__imp_GetTickCount
0x1800024c9  mov     eax, eax
0x1800024cb  lea     rcx, [rbp+arg_0]
0x1800024cf  xor     rax, [rbp+arg_0]
0x1800024d3  xor     rax, rcx
0x1800024d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800024da  mov     [rbp+arg_0], rax
0x1800024de  call    cs:__imp_QueryPerformanceCounter
0x1800024e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800024e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800024f1  shl     rax, 20h
0x1800024f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800024f9  xor     rax, [rbp+arg_0]
0x1800024fd  and     rax, rcx
0x180002500  mov     rcx, rax
0x180002503  cmp     rax, rbx
0x180002506  jnz     short loc_180002515
0x180002508  mov     rax, 2B992DDFA233h
0x180002512  mov     rcx, rax
0x180002515  mov     cs:__security_cookie, rcx
0x18000251c  mov     rbx, [rsp+20h+arg_18]
0x180002521  not     rax
0x180002524  mov     cs:__security_cookie_complement, rax
0x18000252b  add     rsp, 20h
0x18000252f  pop     rbp
0x180002530  retn
```
