# __security_init_cookie

- ea: `0x180001d04`
- end: `0x180001db9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c90`

## callees

- `0x180001d04`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001d47`
- `KERNEL32!GetCurrentThreadId` at `0x180001d47`
- `KERNEL32!QueryPerformanceCounter` at `0x180001d63`
- `KERNEL32!QueryPerformanceCounter` at `0x180001d63`
- `KERNEL32!GetCurrentProcessId` at `0x180001d53`
- `KERNEL32!GetCurrentProcessId` at `0x180001d53`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d39`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001d39`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001d04  mov     [rsp-8+arg_10], rbx
0x180001d09  push    rbp
0x180001d0a  mov     rbp, rsp
0x180001d0d  sub     rsp, 30h
0x180001d11  mov     rax, cs:__security_cookie
0x180001d18  mov     rbx, 2B992DDFA232h
0x180001d22  cmp     rax, rbx
0x180001d25  jnz     short loc_180001DA4
0x180001d27  xor     eax, eax
0x180001d29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001d2d  mov     [rbp+var_10], rax
0x180001d31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001d35  mov     qword ptr [rbp+PerformanceCount], rax
0x180001d39  call    cs:__imp_GetSystemTimeAsFileTime
0x180001d3f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001d43  mov     [rbp+var_10], rax
0x180001d47  call    cs:__imp_GetCurrentThreadId
0x180001d4d  mov     eax, eax
0x180001d4f  xor     [rbp+var_10], rax
0x180001d53  call    cs:__imp_GetCurrentProcessId
0x180001d59  mov     eax, eax
0x180001d5b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001d5f  xor     [rbp+var_10], rax
0x180001d63  call    cs:__imp_QueryPerformanceCounter
0x180001d69  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001d6c  lea     rcx, [rbp+var_10]
0x180001d70  shl     rax, 20h
0x180001d74  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001d78  xor     rax, [rbp+var_10]
0x180001d7c  xor     rax, rcx
0x180001d7f  mov     rcx, 0FFFFFFFFFFFFh
0x180001d89  and     rax, rcx
0x180001d8c  mov     rcx, 2B992DDFA233h
0x180001d96  cmp     rax, rbx
0x180001d99  cmovz   rax, rcx
0x180001d9d  mov     cs:__security_cookie, rax
0x180001da4  mov     rbx, [rsp+30h+arg_10]
0x180001da9  not     rax
0x180001dac  mov     cs:__security_cookie_complement, rax
0x180001db3  add     rsp, 30h
0x180001db7  pop     rbp
0x180001db8  retn
```
