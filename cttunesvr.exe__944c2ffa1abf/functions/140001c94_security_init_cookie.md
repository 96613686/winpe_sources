# __security_init_cookie

- ea: `0x140001c94`
- end: `0x140001d71`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400015f0`

## callees

- `0x140001c94`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140001ce7`
- `KERNEL32!GetCurrentThreadId` at `0x140001ce7`
- `KERNEL32!GetTickCount` at `0x140001cf3`
- `KERNEL32!GetTickCount` at `0x140001d03`
- `KERNEL32!GetTickCount` at `0x140001cf3`
- `KERNEL32!GetTickCount` at `0x140001d03`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001ccd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140001ccd`
- `KERNEL32!GetCurrentProcessId` at `0x140001cdb`
- `KERNEL32!GetCurrentProcessId` at `0x140001cdb`
- `KERNEL32!QueryPerformanceCounter` at `0x140001d1e`
- `KERNEL32!QueryPerformanceCounter` at `0x140001d1e`

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
0x140001c94  mov     [rsp-8+arg_18], rbx
0x140001c99  push    rbp
0x140001c9a  mov     rbp, rsp
0x140001c9d  sub     rsp, 20h
0x140001ca1  xor     eax, eax
0x140001ca3  mov     rbx, 2B992DDFA232h
0x140001cad  mov     [rbp+arg_0], rax
0x140001cb1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001cb5  mov     qword ptr [rbp+PerformanceCount], rax
0x140001cb9  mov     rax, cs:__security_cookie
0x140001cc0  cmp     rax, rbx
0x140001cc3  jnz     loc_140001D5C
0x140001cc9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001ccd  call    cs:__imp_GetSystemTimeAsFileTime
0x140001cd3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001cd7  mov     [rbp+arg_0], rax
0x140001cdb  call    cs:__imp_GetCurrentProcessId
0x140001ce1  mov     eax, eax
0x140001ce3  xor     [rbp+arg_0], rax
0x140001ce7  call    cs:__imp_GetCurrentThreadId
0x140001ced  mov     eax, eax
0x140001cef  xor     [rbp+arg_0], rax
0x140001cf3  call    cs:__imp_GetTickCount
0x140001cf9  mov     eax, eax
0x140001cfb  shl     rax, 18h
0x140001cff  xor     [rbp+arg_0], rax
0x140001d03  call    cs:__imp_GetTickCount
0x140001d09  mov     eax, eax
0x140001d0b  lea     rcx, [rbp+arg_0]
0x140001d0f  xor     rax, [rbp+arg_0]
0x140001d13  xor     rax, rcx
0x140001d16  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001d1a  mov     [rbp+arg_0], rax
0x140001d1e  call    cs:__imp_QueryPerformanceCounter
0x140001d24  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001d27  mov     rcx, 0FFFFFFFFFFFFh
0x140001d31  shl     rax, 20h
0x140001d35  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001d39  xor     rax, [rbp+arg_0]
0x140001d3d  and     rax, rcx
0x140001d40  mov     rcx, rax
0x140001d43  cmp     rax, rbx
0x140001d46  jnz     short loc_140001D55
0x140001d48  mov     rax, 2B992DDFA233h
0x140001d52  mov     rcx, rax
0x140001d55  mov     cs:__security_cookie, rcx
0x140001d5c  mov     rbx, [rsp+20h+arg_18]
0x140001d61  not     rax
0x140001d64  mov     cs:__security_cookie_complement, rax
0x140001d6b  add     rsp, 20h
0x140001d6f  pop     rbp
0x140001d70  retn
```
