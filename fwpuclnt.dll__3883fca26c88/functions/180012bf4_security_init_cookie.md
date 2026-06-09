# __security_init_cookie

- ea: `0x180012bf4`
- end: `0x180012ca9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012b80`

## callees

- `0x180012bf4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012c53`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180012c53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012c43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180012c43`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012c29`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180012c29`

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
0x180012bf4  mov     [rsp-8+arg_10], rbx
0x180012bf9  push    rbp
0x180012bfa  mov     rbp, rsp
0x180012bfd  sub     rsp, 30h
0x180012c01  mov     rax, cs:__security_cookie
0x180012c08  mov     rbx, 2B992DDFA232h
0x180012c12  cmp     rax, rbx
0x180012c15  jnz     short loc_180012C94
0x180012c17  xor     eax, eax
0x180012c19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180012c1d  mov     [rbp+var_10], rax
0x180012c21  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180012c25  mov     qword ptr [rbp+PerformanceCount], rax
0x180012c29  call    cs:__imp_GetSystemTimeAsFileTime
0x180012c2f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180012c33  mov     [rbp+var_10], rax
0x180012c37  call    cs:__imp_GetCurrentThreadId
0x180012c3d  mov     eax, eax
0x180012c3f  xor     [rbp+var_10], rax
0x180012c43  call    cs:__imp_GetCurrentProcessId
0x180012c49  mov     eax, eax
0x180012c4b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180012c4f  xor     [rbp+var_10], rax
0x180012c53  call    cs:__imp_QueryPerformanceCounter
0x180012c59  mov     eax, dword ptr [rbp+PerformanceCount]
0x180012c5c  lea     rcx, [rbp+var_10]
0x180012c60  shl     rax, 20h
0x180012c64  xor     rax, qword ptr [rbp+PerformanceCount]
0x180012c68  xor     rax, [rbp+var_10]
0x180012c6c  xor     rax, rcx
0x180012c6f  mov     rcx, 0FFFFFFFFFFFFh
0x180012c79  and     rax, rcx
0x180012c7c  mov     rcx, 2B992DDFA233h
0x180012c86  cmp     rax, rbx
0x180012c89  cmovz   rax, rcx
0x180012c8d  mov     cs:__security_cookie, rax
0x180012c94  mov     rbx, [rsp+30h+arg_10]
0x180012c99  not     rax
0x180012c9c  mov     cs:__security_cookie_complement, rax
0x180012ca3  add     rsp, 30h
0x180012ca7  pop     rbp
0x180012ca8  retn
```
