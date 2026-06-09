# __security_init_cookie

- ea: `0x180001d44`
- end: `0x180001e21`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001520`

## callees

- `0x180001d44`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001dce`
- `KERNEL32!QueryPerformanceCounter` at `0x180001dce`
- `KERNEL32!GetCurrentProcessId` at `0x180001d8b`
- `KERNEL32!GetCurrentProcessId` at `0x180001d8b`
- `KERNEL32!GetCurrentThreadId` at `0x180001d97`
- `KERNEL32!GetCurrentThreadId` at `0x180001d97`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d7d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d7d`
- `KERNEL32!GetTickCount` at `0x180001da3`
- `KERNEL32!GetTickCount` at `0x180001db3`
- `KERNEL32!GetTickCount` at `0x180001da3`
- `KERNEL32!GetTickCount` at `0x180001db3`

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
0x180001d44  mov     [rsp-8+arg_18], rbx
0x180001d49  push    rbp
0x180001d4a  mov     rbp, rsp
0x180001d4d  sub     rsp, 20h
0x180001d51  xor     eax, eax
0x180001d53  mov     rbx, 2B992DDFA232h
0x180001d5d  mov     [rbp+arg_0], rax
0x180001d61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d65  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d69  mov     rax, cs:__security_cookie
0x180001d70  cmp     rax, rbx
0x180001d73  jnz     loc_180001E0C
0x180001d79  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d87  mov     [rbp+arg_0], rax
0x180001d8b  call    cs:__imp_GetCurrentProcessId
0x180001d91  mov     eax, eax
0x180001d93  xor     [rbp+arg_0], rax
0x180001d97  call    cs:__imp_GetCurrentThreadId
0x180001d9d  mov     eax, eax
0x180001d9f  xor     [rbp+arg_0], rax
0x180001da3  call    cs:__imp_GetTickCount
0x180001da9  mov     eax, eax
0x180001dab  shl     rax, 18h
0x180001daf  xor     [rbp+arg_0], rax
0x180001db3  call    cs:__imp_GetTickCount
0x180001db9  mov     eax, eax
0x180001dbb  lea     rcx, [rbp+arg_0]
0x180001dbf  xor     rax, [rbp+arg_0]
0x180001dc3  xor     rax, rcx
0x180001dc6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001dca  mov     [rbp+arg_0], rax
0x180001dce  call    cs:__imp_QueryPerformanceCounter
0x180001dd4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001dd7  mov     rcx, 0FFFFFFFFFFFFh
0x180001de1  shl     rax, 20h
0x180001de5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001de9  xor     rax, [rbp+arg_0]
0x180001ded  and     rax, rcx
0x180001df0  mov     rcx, rax
0x180001df3  cmp     rax, rbx
0x180001df6  jnz     short loc_180001E05
0x180001df8  mov     rax, 2B992DDFA233h
0x180001e02  mov     rcx, rax
0x180001e05  mov     cs:__security_cookie, rcx
0x180001e0c  mov     rbx, [rsp+20h+arg_18]
0x180001e11  not     rax
0x180001e14  mov     cs:__security_cookie_complement, rax
0x180001e1b  add     rsp, 20h
0x180001e1f  pop     rbp
0x180001e20  retn
```
