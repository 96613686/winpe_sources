# __security_init_cookie

- ea: `0x1801cb954`
- end: `0x1801cba31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801cada0`

## callees

- `0x1801cb954`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1801cb9de`
- `KERNEL32!QueryPerformanceCounter` at `0x1801cb9de`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801cb98d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801cb98d`
- `KERNEL32!GetTickCount` at `0x1801cb9b3`
- `KERNEL32!GetTickCount` at `0x1801cb9c3`
- `KERNEL32!GetTickCount` at `0x1801cb9b3`
- `KERNEL32!GetTickCount` at `0x1801cb9c3`
- `KERNEL32!GetCurrentProcessId` at `0x1801cb99b`
- `KERNEL32!GetCurrentProcessId` at `0x1801cb99b`
- `KERNEL32!GetCurrentThreadId` at `0x1801cb9a7`
- `KERNEL32!GetCurrentThreadId` at `0x1801cb9a7`

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
0x1801cb954  mov     [rsp-8+arg_18], rbx
0x1801cb959  push    rbp
0x1801cb95a  mov     rbp, rsp
0x1801cb95d  sub     rsp, 20h
0x1801cb961  xor     eax, eax
0x1801cb963  mov     rbx, 2B992DDFA232h
0x1801cb96d  mov     [rbp+arg_0], rax
0x1801cb971  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1801cb975  mov     qword ptr [rbp+PerformanceCount], rax
0x1801cb979  mov     rax, cs:__security_cookie
0x1801cb980  cmp     rax, rbx
0x1801cb983  jnz     loc_1801CBA1C
0x1801cb989  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801cb98d  call    cs:__imp_GetSystemTimeAsFileTime
0x1801cb993  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801cb997  mov     [rbp+arg_0], rax
0x1801cb99b  call    cs:__imp_GetCurrentProcessId
0x1801cb9a1  mov     eax, eax
0x1801cb9a3  xor     [rbp+arg_0], rax
0x1801cb9a7  call    cs:__imp_GetCurrentThreadId
0x1801cb9ad  mov     eax, eax
0x1801cb9af  xor     [rbp+arg_0], rax
0x1801cb9b3  call    cs:__imp_GetTickCount
0x1801cb9b9  mov     eax, eax
0x1801cb9bb  shl     rax, 18h
0x1801cb9bf  xor     [rbp+arg_0], rax
0x1801cb9c3  call    cs:__imp_GetTickCount
0x1801cb9c9  mov     eax, eax
0x1801cb9cb  lea     rcx, [rbp+arg_0]
0x1801cb9cf  xor     rax, [rbp+arg_0]
0x1801cb9d3  xor     rax, rcx
0x1801cb9d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1801cb9da  mov     [rbp+arg_0], rax
0x1801cb9de  call    cs:__imp_QueryPerformanceCounter
0x1801cb9e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801cb9e7  mov     rcx, 0FFFFFFFFFFFFh
0x1801cb9f1  shl     rax, 20h
0x1801cb9f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801cb9f9  xor     rax, [rbp+arg_0]
0x1801cb9fd  and     rax, rcx
0x1801cba00  mov     rcx, rax
0x1801cba03  cmp     rax, rbx
0x1801cba06  jnz     short loc_1801CBA15
0x1801cba08  mov     rax, 2B992DDFA233h
0x1801cba12  mov     rcx, rax
0x1801cba15  mov     cs:__security_cookie, rcx
0x1801cba1c  mov     rbx, [rsp+20h+arg_18]
0x1801cba21  not     rax
0x1801cba24  mov     cs:__security_cookie_complement, rax
0x1801cba2b  add     rsp, 20h
0x1801cba2f  pop     rbp
0x1801cba30  retn
```
