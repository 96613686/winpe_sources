# __security_init_cookie

- ea: `0x180001c34`
- end: `0x180001d11`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001400`

## callees

- `0x180001c34`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001cbe`
- `KERNEL32!QueryPerformanceCounter` at `0x180001cbe`
- `KERNEL32!GetCurrentProcessId` at `0x180001c7b`
- `KERNEL32!GetCurrentProcessId` at `0x180001c7b`
- `KERNEL32!GetCurrentThreadId` at `0x180001c87`
- `KERNEL32!GetCurrentThreadId` at `0x180001c87`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c6d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001c6d`
- `KERNEL32!GetTickCount` at `0x180001c93`
- `KERNEL32!GetTickCount` at `0x180001ca3`
- `KERNEL32!GetTickCount` at `0x180001c93`
- `KERNEL32!GetTickCount` at `0x180001ca3`

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
0x180001c34  mov     [rsp-8+arg_18], rbx
0x180001c39  push    rbp
0x180001c3a  mov     rbp, rsp
0x180001c3d  sub     rsp, 20h
0x180001c41  xor     eax, eax
0x180001c43  mov     rbx, 2B992DDFA232h
0x180001c4d  mov     [rbp+arg_0], rax
0x180001c51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001c55  mov     qword ptr [rbp+PerformanceCount], rax
0x180001c59  mov     rax, cs:__security_cookie
0x180001c60  cmp     rax, rbx
0x180001c63  jnz     loc_180001CFC
0x180001c69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001c6d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001c73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001c77  mov     [rbp+arg_0], rax
0x180001c7b  call    cs:__imp_GetCurrentProcessId
0x180001c81  mov     eax, eax
0x180001c83  xor     [rbp+arg_0], rax
0x180001c87  call    cs:__imp_GetCurrentThreadId
0x180001c8d  mov     eax, eax
0x180001c8f  xor     [rbp+arg_0], rax
0x180001c93  call    cs:__imp_GetTickCount
0x180001c99  mov     eax, eax
0x180001c9b  shl     rax, 18h
0x180001c9f  xor     [rbp+arg_0], rax
0x180001ca3  call    cs:__imp_GetTickCount
0x180001ca9  mov     eax, eax
0x180001cab  lea     rcx, [rbp+arg_0]
0x180001caf  xor     rax, [rbp+arg_0]
0x180001cb3  xor     rax, rcx
0x180001cb6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001cba  mov     [rbp+arg_0], rax
0x180001cbe  call    cs:__imp_QueryPerformanceCounter
0x180001cc4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001cc7  mov     rcx, 0FFFFFFFFFFFFh
0x180001cd1  shl     rax, 20h
0x180001cd5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001cd9  xor     rax, [rbp+arg_0]
0x180001cdd  and     rax, rcx
0x180001ce0  mov     rcx, rax
0x180001ce3  cmp     rax, rbx
0x180001ce6  jnz     short loc_180001CF5
0x180001ce8  mov     rax, 2B992DDFA233h
0x180001cf2  mov     rcx, rax
0x180001cf5  mov     cs:__security_cookie, rcx
0x180001cfc  mov     rbx, [rsp+20h+arg_18]
0x180001d01  not     rax
0x180001d04  mov     cs:__security_cookie_complement, rax
0x180001d0b  add     rsp, 20h
0x180001d0f  pop     rbp
0x180001d10  retn
```
