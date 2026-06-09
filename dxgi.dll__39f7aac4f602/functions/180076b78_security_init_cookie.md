# __security_init_cookie

- ea: `0x180076b78`
- end: `0x180076c2d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180075f50`

## callees

- `0x180076b78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076bbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180076bbb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076bc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180076bc7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180076bd7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180076bd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180076bad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180076bad`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180076b78  mov     [rsp-8+arg_10], rbx
0x180076b7d  push    rbp
0x180076b7e  mov     rbp, rsp
0x180076b81  sub     rsp, 30h
0x180076b85  mov     rax, cs:__security_cookie
0x180076b8c  mov     rbx, 2B992DDFA232h
0x180076b96  cmp     rax, rbx
0x180076b99  jnz     short loc_180076C18
0x180076b9b  xor     eax, eax
0x180076b9d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180076ba1  mov     [rbp+var_10], rax
0x180076ba5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180076ba9  mov     qword ptr [rbp+PerformanceCount], rax
0x180076bad  call    cs:__imp_GetSystemTimeAsFileTime
0x180076bb3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180076bb7  mov     [rbp+var_10], rax
0x180076bbb  call    cs:__imp_GetCurrentThreadId
0x180076bc1  mov     eax, eax
0x180076bc3  xor     [rbp+var_10], rax
0x180076bc7  call    cs:__imp_GetCurrentProcessId
0x180076bcd  mov     eax, eax
0x180076bcf  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180076bd3  xor     [rbp+var_10], rax
0x180076bd7  call    cs:__imp_QueryPerformanceCounter
0x180076bdd  mov     eax, dword ptr [rbp+PerformanceCount]
0x180076be0  lea     rcx, [rbp+var_10]
0x180076be4  shl     rax, 20h
0x180076be8  xor     rax, qword ptr [rbp+PerformanceCount]
0x180076bec  xor     rax, [rbp+var_10]
0x180076bf0  xor     rax, rcx
0x180076bf3  mov     rcx, 0FFFFFFFFFFFFh
0x180076bfd  and     rax, rcx
0x180076c00  mov     rcx, 2B992DDFA233h
0x180076c0a  cmp     rax, rbx
0x180076c0d  cmovz   rax, rcx
0x180076c11  mov     cs:__security_cookie, rax
0x180076c18  mov     rbx, [rsp+30h+arg_10]
0x180076c1d  not     rax
0x180076c20  mov     cs:__security_cookie_complement, rax
0x180076c27  add     rsp, 30h
0x180076c2b  pop     rbp
0x180076c2c  retn
```
