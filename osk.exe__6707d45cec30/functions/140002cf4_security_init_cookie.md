# __security_init_cookie

- ea: `0x140002cf4`
- end: `0x140002dd1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002720`

## callees

- `0x140002cf4`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002d47`
- `KERNEL32!GetCurrentThreadId` at `0x140002d47`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140002d2d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x140002d2d`
- `KERNEL32!QueryPerformanceCounter` at `0x140002d7e`
- `KERNEL32!QueryPerformanceCounter` at `0x140002d7e`
- `KERNEL32!GetCurrentProcessId` at `0x140002d3b`
- `KERNEL32!GetCurrentProcessId` at `0x140002d3b`
- `KERNEL32!GetTickCount` at `0x140002d53`
- `KERNEL32!GetTickCount` at `0x140002d63`
- `KERNEL32!GetTickCount` at `0x140002d53`
- `KERNEL32!GetTickCount` at `0x140002d63`

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
0x140002cf4  mov     [rsp-8+arg_18], rbx
0x140002cf9  push    rbp
0x140002cfa  mov     rbp, rsp
0x140002cfd  sub     rsp, 20h
0x140002d01  xor     eax, eax
0x140002d03  mov     rbx, 2B992DDFA232h
0x140002d0d  mov     [rbp+arg_0], rax
0x140002d11  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002d15  mov     qword ptr [rbp+PerformanceCount], rax
0x140002d19  mov     rax, cs:__security_cookie
0x140002d20  cmp     rax, rbx
0x140002d23  jnz     loc_140002DBC
0x140002d29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140002d2d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002d33  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002d37  mov     [rbp+arg_0], rax
0x140002d3b  call    cs:__imp_GetCurrentProcessId
0x140002d41  mov     eax, eax
0x140002d43  xor     [rbp+arg_0], rax
0x140002d47  call    cs:__imp_GetCurrentThreadId
0x140002d4d  mov     eax, eax
0x140002d4f  xor     [rbp+arg_0], rax
0x140002d53  call    cs:__imp_GetTickCount
0x140002d59  mov     eax, eax
0x140002d5b  shl     rax, 18h
0x140002d5f  xor     [rbp+arg_0], rax
0x140002d63  call    cs:__imp_GetTickCount
0x140002d69  mov     eax, eax
0x140002d6b  lea     rcx, [rbp+arg_0]
0x140002d6f  xor     rax, [rbp+arg_0]
0x140002d73  xor     rax, rcx
0x140002d76  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002d7a  mov     [rbp+arg_0], rax
0x140002d7e  call    cs:__imp_QueryPerformanceCounter
0x140002d84  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002d87  mov     rcx, 0FFFFFFFFFFFFh
0x140002d91  shl     rax, 20h
0x140002d95  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002d99  xor     rax, [rbp+arg_0]
0x140002d9d  and     rax, rcx
0x140002da0  mov     rcx, rax
0x140002da3  cmp     rax, rbx
0x140002da6  jnz     short loc_140002DB5
0x140002da8  mov     rax, 2B992DDFA233h
0x140002db2  mov     rcx, rax
0x140002db5  mov     cs:__security_cookie, rcx
0x140002dbc  mov     rbx, [rsp+20h+arg_18]
0x140002dc1  not     rax
0x140002dc4  mov     cs:__security_cookie_complement, rax
0x140002dcb  add     rsp, 20h
0x140002dcf  pop     rbp
0x140002dd0  retn
```
