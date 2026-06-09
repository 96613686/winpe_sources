# __security_init_cookie

- ea: `0x180019c04`
- end: `0x180019cb9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019020`

## callees

- `0x180019c04`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019c39`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019c39`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019c63`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019c63`

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
0x180019c04  mov     [rsp-8+arg_10], rbx
0x180019c09  push    rbp
0x180019c0a  mov     rbp, rsp
0x180019c0d  sub     rsp, 30h
0x180019c11  mov     rax, cs:__security_cookie
0x180019c18  mov     rbx, 2B992DDFA232h
0x180019c22  cmp     rax, rbx
0x180019c25  jnz     short loc_180019CA4
0x180019c27  xor     eax, eax
0x180019c29  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019c2d  mov     [rbp+var_10], rax
0x180019c31  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180019c35  mov     qword ptr [rbp+PerformanceCount], rax
0x180019c39  call    cs:__imp_GetSystemTimeAsFileTime
0x180019c3f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180019c43  mov     [rbp+var_10], rax
0x180019c47  call    cs:__imp_GetCurrentThreadId
0x180019c4d  mov     eax, eax
0x180019c4f  xor     [rbp+var_10], rax
0x180019c53  call    cs:__imp_GetCurrentProcessId
0x180019c59  mov     eax, eax
0x180019c5b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180019c5f  xor     [rbp+var_10], rax
0x180019c63  call    cs:__imp_QueryPerformanceCounter
0x180019c69  mov     eax, dword ptr [rbp+PerformanceCount]
0x180019c6c  lea     rcx, [rbp+var_10]
0x180019c70  shl     rax, 20h
0x180019c74  xor     rax, qword ptr [rbp+PerformanceCount]
0x180019c78  xor     rax, [rbp+var_10]
0x180019c7c  xor     rax, rcx
0x180019c7f  mov     rcx, 0FFFFFFFFFFFFh
0x180019c89  and     rax, rcx
0x180019c8c  mov     rcx, 2B992DDFA233h
0x180019c96  cmp     rax, rbx
0x180019c99  cmovz   rax, rcx
0x180019c9d  mov     cs:__security_cookie, rax
0x180019ca4  mov     rbx, [rsp+30h+arg_10]
0x180019ca9  not     rax
0x180019cac  mov     cs:__security_cookie_complement, rax
0x180019cb3  add     rsp, 30h
0x180019cb7  pop     rbp
0x180019cb8  retn
```
