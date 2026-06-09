# __security_init_cookie

- ea: `0x18004d5d4`
- end: `0x18004d689`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004ca40`

## callees

- `0x18004d5d4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004d609`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004d609`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004d623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004d617`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004d633`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004d633`

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
0x18004d5d4  mov     [rsp-8+arg_10], rbx
0x18004d5d9  push    rbp
0x18004d5da  mov     rbp, rsp
0x18004d5dd  sub     rsp, 30h
0x18004d5e1  mov     rax, cs:__security_cookie
0x18004d5e8  mov     rbx, 2B992DDFA232h
0x18004d5f2  cmp     rax, rbx
0x18004d5f5  jnz     short loc_18004D674
0x18004d5f7  xor     eax, eax
0x18004d5f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004d5fd  mov     [rbp+var_10], rax
0x18004d601  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004d605  mov     qword ptr [rbp+PerformanceCount], rax
0x18004d609  call    cs:__imp_GetSystemTimeAsFileTime
0x18004d60f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004d613  mov     [rbp+var_10], rax
0x18004d617  call    cs:__imp_GetCurrentThreadId
0x18004d61d  mov     eax, eax
0x18004d61f  xor     [rbp+var_10], rax
0x18004d623  call    cs:__imp_GetCurrentProcessId
0x18004d629  mov     eax, eax
0x18004d62b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004d62f  xor     [rbp+var_10], rax
0x18004d633  call    cs:__imp_QueryPerformanceCounter
0x18004d639  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004d63c  lea     rcx, [rbp+var_10]
0x18004d640  shl     rax, 20h
0x18004d644  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004d648  xor     rax, [rbp+var_10]
0x18004d64c  xor     rax, rcx
0x18004d64f  mov     rcx, 0FFFFFFFFFFFFh
0x18004d659  and     rax, rcx
0x18004d65c  mov     rcx, 2B992DDFA233h
0x18004d666  cmp     rax, rbx
0x18004d669  cmovz   rax, rcx
0x18004d66d  mov     cs:__security_cookie, rax
0x18004d674  mov     rbx, [rsp+30h+arg_10]
0x18004d679  not     rax
0x18004d67c  mov     cs:__security_cookie_complement, rax
0x18004d683  add     rsp, 30h
0x18004d687  pop     rbp
0x18004d688  retn
```
