# __security_init_cookie

- ea: `0x180001eb4`
- end: `0x180001f91`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001720`

## callees

- `0x180001eb4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001f07`
- `KERNEL32!GetCurrentThreadId` at `0x180001f07`
- `KERNEL32!GetCurrentProcessId` at `0x180001efb`
- `KERNEL32!GetCurrentProcessId` at `0x180001efb`
- `KERNEL32!QueryPerformanceCounter` at `0x180001f3e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001f3e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001eed`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001eed`
- `KERNEL32!GetTickCount` at `0x180001f13`
- `KERNEL32!GetTickCount` at `0x180001f23`
- `KERNEL32!GetTickCount` at `0x180001f13`
- `KERNEL32!GetTickCount` at `0x180001f23`

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
0x180001eb4  mov     [rsp-8+arg_18], rbx
0x180001eb9  push    rbp
0x180001eba  mov     rbp, rsp
0x180001ebd  sub     rsp, 20h
0x180001ec1  xor     eax, eax
0x180001ec3  mov     rbx, 2B992DDFA232h
0x180001ecd  mov     [rbp+arg_0], rax
0x180001ed1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001ed5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001ed9  mov     rax, cs:__security_cookie
0x180001ee0  cmp     rax, rbx
0x180001ee3  jnz     loc_180001F7C
0x180001ee9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001eed  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ef3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ef7  mov     [rbp+arg_0], rax
0x180001efb  call    cs:__imp_GetCurrentProcessId
0x180001f01  mov     eax, eax
0x180001f03  xor     [rbp+arg_0], rax
0x180001f07  call    cs:__imp_GetCurrentThreadId
0x180001f0d  mov     eax, eax
0x180001f0f  xor     [rbp+arg_0], rax
0x180001f13  call    cs:__imp_GetTickCount
0x180001f19  mov     eax, eax
0x180001f1b  shl     rax, 18h
0x180001f1f  xor     [rbp+arg_0], rax
0x180001f23  call    cs:__imp_GetTickCount
0x180001f29  mov     eax, eax
0x180001f2b  lea     rcx, [rbp+arg_0]
0x180001f2f  xor     rax, [rbp+arg_0]
0x180001f33  xor     rax, rcx
0x180001f36  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f3a  mov     [rbp+arg_0], rax
0x180001f3e  call    cs:__imp_QueryPerformanceCounter
0x180001f44  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f47  mov     rcx, 0FFFFFFFFFFFFh
0x180001f51  shl     rax, 20h
0x180001f55  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f59  xor     rax, [rbp+arg_0]
0x180001f5d  and     rax, rcx
0x180001f60  mov     rcx, rax
0x180001f63  cmp     rax, rbx
0x180001f66  jnz     short loc_180001F75
0x180001f68  mov     rax, 2B992DDFA233h
0x180001f72  mov     rcx, rax
0x180001f75  mov     cs:__security_cookie, rcx
0x180001f7c  mov     rbx, [rsp+20h+arg_18]
0x180001f81  not     rax
0x180001f84  mov     cs:__security_cookie_complement, rax
0x180001f8b  add     rsp, 20h
0x180001f8f  pop     rbp
0x180001f90  retn
```
