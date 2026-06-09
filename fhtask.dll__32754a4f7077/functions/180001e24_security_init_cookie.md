# __security_init_cookie

- ea: `0x180001e24`
- end: `0x180001f01`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015a0`

## callees

- `0x180001e24`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001eae`
- `KERNEL32!QueryPerformanceCounter` at `0x180001eae`
- `KERNEL32!GetCurrentProcessId` at `0x180001e6b`
- `KERNEL32!GetCurrentProcessId` at `0x180001e6b`
- `KERNEL32!GetCurrentThreadId` at `0x180001e77`
- `KERNEL32!GetCurrentThreadId` at `0x180001e77`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e5d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001e5d`
- `KERNEL32!GetTickCount` at `0x180001e83`
- `KERNEL32!GetTickCount` at `0x180001e93`
- `KERNEL32!GetTickCount` at `0x180001e83`
- `KERNEL32!GetTickCount` at `0x180001e93`

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
0x180001e24  mov     [rsp-8+arg_18], rbx
0x180001e29  push    rbp
0x180001e2a  mov     rbp, rsp
0x180001e2d  sub     rsp, 20h
0x180001e31  xor     eax, eax
0x180001e33  mov     rbx, 2B992DDFA232h
0x180001e3d  mov     [rbp+arg_0], rax
0x180001e41  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001e45  mov     qword ptr [rbp+PerformanceCount], rax
0x180001e49  mov     rax, cs:__security_cookie
0x180001e50  cmp     rax, rbx
0x180001e53  jnz     loc_180001EEC
0x180001e59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e5d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001e63  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001e67  mov     [rbp+arg_0], rax
0x180001e6b  call    cs:__imp_GetCurrentProcessId
0x180001e71  mov     eax, eax
0x180001e73  xor     [rbp+arg_0], rax
0x180001e77  call    cs:__imp_GetCurrentThreadId
0x180001e7d  mov     eax, eax
0x180001e7f  xor     [rbp+arg_0], rax
0x180001e83  call    cs:__imp_GetTickCount
0x180001e89  mov     eax, eax
0x180001e8b  shl     rax, 18h
0x180001e8f  xor     [rbp+arg_0], rax
0x180001e93  call    cs:__imp_GetTickCount
0x180001e99  mov     eax, eax
0x180001e9b  lea     rcx, [rbp+arg_0]
0x180001e9f  xor     rax, [rbp+arg_0]
0x180001ea3  xor     rax, rcx
0x180001ea6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001eaa  mov     [rbp+arg_0], rax
0x180001eae  call    cs:__imp_QueryPerformanceCounter
0x180001eb4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001eb7  mov     rcx, 0FFFFFFFFFFFFh
0x180001ec1  shl     rax, 20h
0x180001ec5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ec9  xor     rax, [rbp+arg_0]
0x180001ecd  and     rax, rcx
0x180001ed0  mov     rcx, rax
0x180001ed3  cmp     rax, rbx
0x180001ed6  jnz     short loc_180001EE5
0x180001ed8  mov     rax, 2B992DDFA233h
0x180001ee2  mov     rcx, rax
0x180001ee5  mov     cs:__security_cookie, rcx
0x180001eec  mov     rbx, [rsp+20h+arg_18]
0x180001ef1  not     rax
0x180001ef4  mov     cs:__security_cookie_complement, rax
0x180001efb  add     rsp, 20h
0x180001eff  pop     rbp
0x180001f00  retn
```
