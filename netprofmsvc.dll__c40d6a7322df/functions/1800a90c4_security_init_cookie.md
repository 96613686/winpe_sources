# __security_init_cookie

- ea: `0x1800a90c4`
- end: `0x1800a9179`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800a8850`

## callees

- `0x1800a90c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a9113`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800a9113`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a9107`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a9107`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a90f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800a90f9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a9123`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800a9123`

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
0x1800a90c4  mov     [rsp-8+arg_10], rbx
0x1800a90c9  push    rbp
0x1800a90ca  mov     rbp, rsp
0x1800a90cd  sub     rsp, 30h
0x1800a90d1  mov     rax, cs:__security_cookie
0x1800a90d8  mov     rbx, 2B992DDFA232h
0x1800a90e2  cmp     rax, rbx
0x1800a90e5  jnz     short loc_1800A9164
0x1800a90e7  xor     eax, eax
0x1800a90e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800a90ed  mov     [rbp+var_10], rax
0x1800a90f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800a90f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800a90f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800a90ff  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800a9103  mov     [rbp+var_10], rax
0x1800a9107  call    cs:__imp_GetCurrentThreadId
0x1800a910d  mov     eax, eax
0x1800a910f  xor     [rbp+var_10], rax
0x1800a9113  call    cs:__imp_GetCurrentProcessId
0x1800a9119  mov     eax, eax
0x1800a911b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800a911f  xor     [rbp+var_10], rax
0x1800a9123  call    cs:__imp_QueryPerformanceCounter
0x1800a9129  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800a912c  lea     rcx, [rbp+var_10]
0x1800a9130  shl     rax, 20h
0x1800a9134  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800a9138  xor     rax, [rbp+var_10]
0x1800a913c  xor     rax, rcx
0x1800a913f  mov     rcx, 0FFFFFFFFFFFFh
0x1800a9149  and     rax, rcx
0x1800a914c  mov     rcx, 2B992DDFA233h
0x1800a9156  cmp     rax, rbx
0x1800a9159  cmovz   rax, rcx
0x1800a915d  mov     cs:__security_cookie, rax
0x1800a9164  mov     rbx, [rsp+30h+arg_10]
0x1800a9169  not     rax
0x1800a916c  mov     cs:__security_cookie_complement, rax
0x1800a9173  add     rsp, 30h
0x1800a9177  pop     rbp
0x1800a9178  retn
```
