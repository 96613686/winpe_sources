# __security_init_cookie

- ea: `0x180013fcc`
- end: `0x180014081`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180013ad0`

## callees

- `0x180013fcc`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014001`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180014001`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001402b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001402b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001400f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001400f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001401b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001401b`

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
0x180013fcc  mov     [rsp-8+arg_10], rbx
0x180013fd1  push    rbp
0x180013fd2  mov     rbp, rsp
0x180013fd5  sub     rsp, 30h
0x180013fd9  mov     rax, cs:__security_cookie
0x180013fe0  mov     rbx, 2B992DDFA232h
0x180013fea  cmp     rax, rbx
0x180013fed  jnz     short loc_18001406C
0x180013fef  xor     eax, eax
0x180013ff1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013ff5  mov     [rbp+var_10], rax
0x180013ff9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180013ffd  mov     qword ptr [rbp+PerformanceCount], rax
0x180014001  call    cs:__imp_GetSystemTimeAsFileTime
0x180014007  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001400b  mov     [rbp+var_10], rax
0x18001400f  call    cs:__imp_GetCurrentThreadId
0x180014015  mov     eax, eax
0x180014017  xor     [rbp+var_10], rax
0x18001401b  call    cs:__imp_GetCurrentProcessId
0x180014021  mov     eax, eax
0x180014023  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180014027  xor     [rbp+var_10], rax
0x18001402b  call    cs:__imp_QueryPerformanceCounter
0x180014031  mov     eax, dword ptr [rbp+PerformanceCount]
0x180014034  lea     rcx, [rbp+var_10]
0x180014038  shl     rax, 20h
0x18001403c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180014040  xor     rax, [rbp+var_10]
0x180014044  xor     rax, rcx
0x180014047  mov     rcx, 0FFFFFFFFFFFFh
0x180014051  and     rax, rcx
0x180014054  mov     rcx, 2B992DDFA233h
0x18001405e  cmp     rax, rbx
0x180014061  cmovz   rax, rcx
0x180014065  mov     cs:__security_cookie, rax
0x18001406c  mov     rbx, [rsp+30h+arg_10]
0x180014071  not     rax
0x180014074  mov     cs:__security_cookie_complement, rax
0x18001407b  add     rsp, 30h
0x18001407f  pop     rbp
0x180014080  retn
```
