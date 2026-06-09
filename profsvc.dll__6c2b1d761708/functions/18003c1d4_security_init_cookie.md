# __security_init_cookie

- ea: `0x18003c1d4`
- end: `0x18003c289`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003bc20`

## callees

- `0x18003c1d4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003c223`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c217`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c209`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003c209`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003c233`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003c233`

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
0x18003c1d4  mov     [rsp-8+arg_10], rbx
0x18003c1d9  push    rbp
0x18003c1da  mov     rbp, rsp
0x18003c1dd  sub     rsp, 30h
0x18003c1e1  mov     rax, cs:__security_cookie
0x18003c1e8  mov     rbx, 2B992DDFA232h
0x18003c1f2  cmp     rax, rbx
0x18003c1f5  jnz     short loc_18003C274
0x18003c1f7  xor     eax, eax
0x18003c1f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003c1fd  mov     [rbp+var_10], rax
0x18003c201  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003c205  mov     qword ptr [rbp+PerformanceCount], rax
0x18003c209  call    cs:__imp_GetSystemTimeAsFileTime
0x18003c20f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003c213  mov     [rbp+var_10], rax
0x18003c217  call    cs:__imp_GetCurrentThreadId
0x18003c21d  mov     eax, eax
0x18003c21f  xor     [rbp+var_10], rax
0x18003c223  call    cs:__imp_GetCurrentProcessId
0x18003c229  mov     eax, eax
0x18003c22b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003c22f  xor     [rbp+var_10], rax
0x18003c233  call    cs:__imp_QueryPerformanceCounter
0x18003c239  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003c23c  lea     rcx, [rbp+var_10]
0x18003c240  shl     rax, 20h
0x18003c244  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003c248  xor     rax, [rbp+var_10]
0x18003c24c  xor     rax, rcx
0x18003c24f  mov     rcx, 0FFFFFFFFFFFFh
0x18003c259  and     rax, rcx
0x18003c25c  mov     rcx, 2B992DDFA233h
0x18003c266  cmp     rax, rbx
0x18003c269  cmovz   rax, rcx
0x18003c26d  mov     cs:__security_cookie, rax
0x18003c274  mov     rbx, [rsp+30h+arg_10]
0x18003c279  not     rax
0x18003c27c  mov     cs:__security_cookie_complement, rax
0x18003c283  add     rsp, 30h
0x18003c287  pop     rbp
0x18003c288  retn
```
