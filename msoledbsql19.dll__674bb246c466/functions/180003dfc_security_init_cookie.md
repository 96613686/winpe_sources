# __security_init_cookie

- ea: `0x180003dfc`
- end: `0x180003ea8`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800037e0`

## callees

- `0x180003dfc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003e28`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180003e28`
- `KERNEL32!GetCurrentThreadId` at `0x180003e36`
- `KERNEL32!GetCurrentThreadId` at `0x180003e36`
- `KERNEL32!GetCurrentProcessId` at `0x180003e42`
- `KERNEL32!GetCurrentProcessId` at `0x180003e42`
- `KERNEL32!QueryPerformanceCounter` at `0x180003e52`
- `KERNEL32!QueryPerformanceCounter` at `0x180003e52`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x180003dfc  mov     [rsp-8+arg_10], rbx
0x180003e01  push    rbp
0x180003e02  mov     rbp, rsp
0x180003e05  sub     rsp, 30h
0x180003e09  mov     rax, cs:__security_cookie
0x180003e10  mov     rbx, 2B992DDFA232h
0x180003e1a  cmp     rax, rbx
0x180003e1d  jnz     short loc_180003E93
0x180003e1f  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180003e24  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180003e28  call    cs:__imp_GetSystemTimeAsFileTime
0x180003e2e  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180003e32  mov     [rbp+var_10], rax
0x180003e36  call    cs:__imp_GetCurrentThreadId
0x180003e3c  mov     eax, eax
0x180003e3e  xor     [rbp+var_10], rax
0x180003e42  call    cs:__imp_GetCurrentProcessId
0x180003e48  mov     eax, eax
0x180003e4a  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180003e4e  xor     [rbp+var_10], rax
0x180003e52  call    cs:__imp_QueryPerformanceCounter
0x180003e58  mov     eax, dword ptr [rbp+PerformanceCount]
0x180003e5b  lea     rcx, [rbp+var_10]
0x180003e5f  shl     rax, 20h
0x180003e63  xor     rax, qword ptr [rbp+PerformanceCount]
0x180003e67  xor     rax, [rbp+var_10]
0x180003e6b  xor     rax, rcx
0x180003e6e  mov     rcx, 0FFFFFFFFFFFFh
0x180003e78  and     rax, rcx
0x180003e7b  mov     rcx, 2B992DDFA233h
0x180003e85  cmp     rax, rbx
0x180003e88  cmovz   rax, rcx
0x180003e8c  mov     cs:__security_cookie, rax
0x180003e93  mov     rbx, [rsp+30h+arg_10]
0x180003e98  not     rax
0x180003e9b  mov     cs:__security_cookie_complement, rax
0x180003ea2  add     rsp, 30h
0x180003ea6  pop     rbp
0x180003ea7  retn
```
