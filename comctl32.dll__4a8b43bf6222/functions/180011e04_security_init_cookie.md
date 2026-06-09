# __security_init_cookie

- ea: `0x180011e04`
- end: `0x180011eb9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800115a0`

## callees

- `0x180011e04`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180011e53`
- `KERNEL32!GetCurrentProcessId` at `0x180011e53`
- `KERNEL32!GetCurrentThreadId` at `0x180011e47`
- `KERNEL32!GetCurrentThreadId` at `0x180011e47`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180011e39`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180011e39`
- `KERNEL32!QueryPerformanceCounter` at `0x180011e63`
- `KERNEL32!QueryPerformanceCounter` at `0x180011e63`

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
0x180011e04  mov     [rsp-8+arg_10], rbx
0x180011e09  push    rbp
0x180011e0a  mov     rbp, rsp
0x180011e0d  sub     rsp, 30h
0x180011e11  mov     rax, cs:__security_cookie
0x180011e18  mov     rbx, 2B992DDFA232h
0x180011e22  cmp     rax, rbx
0x180011e25  jnz     short loc_180011EA4
0x180011e27  xor     eax, eax
0x180011e29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180011e2d  mov     [rbp+var_10], rax
0x180011e31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180011e35  mov     qword ptr [rbp+PerformanceCount], rax
0x180011e39  call    cs:__imp_GetSystemTimeAsFileTime
0x180011e3f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180011e43  mov     [rbp+var_10], rax
0x180011e47  call    cs:__imp_GetCurrentThreadId
0x180011e4d  mov     eax, eax
0x180011e4f  xor     [rbp+var_10], rax
0x180011e53  call    cs:__imp_GetCurrentProcessId
0x180011e59  mov     eax, eax
0x180011e5b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180011e5f  xor     [rbp+var_10], rax
0x180011e63  call    cs:__imp_QueryPerformanceCounter
0x180011e69  mov     eax, dword ptr [rbp+PerformanceCount]
0x180011e6c  lea     rcx, [rbp+var_10]
0x180011e70  shl     rax, 20h
0x180011e74  xor     rax, qword ptr [rbp+PerformanceCount]
0x180011e78  xor     rax, [rbp+var_10]
0x180011e7c  xor     rax, rcx
0x180011e7f  mov     rcx, 0FFFFFFFFFFFFh
0x180011e89  and     rax, rcx
0x180011e8c  mov     rcx, 2B992DDFA233h
0x180011e96  cmp     rax, rbx
0x180011e99  cmovz   rax, rcx
0x180011e9d  mov     cs:__security_cookie, rax
0x180011ea4  mov     rbx, [rsp+30h+arg_10]
0x180011ea9  not     rax
0x180011eac  mov     cs:__security_cookie_complement, rax
0x180011eb3  add     rsp, 30h
0x180011eb7  pop     rbp
0x180011eb8  retn
```
