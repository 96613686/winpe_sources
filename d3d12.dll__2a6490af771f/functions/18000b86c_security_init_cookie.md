# __security_init_cookie

- ea: `0x18000b86c`
- end: `0x18000b921`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b3b0`

## callees

- `0x18000b86c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b8af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b8af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b8bb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000b8bb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b8a1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000b8a1`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b8cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000b8cb`

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
0x18000b86c  mov     [rsp-8+arg_10], rbx
0x18000b871  push    rbp
0x18000b872  mov     rbp, rsp
0x18000b875  sub     rsp, 30h
0x18000b879  mov     rax, cs:__security_cookie
0x18000b880  mov     rbx, 2B992DDFA232h
0x18000b88a  cmp     rax, rbx
0x18000b88d  jnz     short loc_18000B90C
0x18000b88f  xor     eax, eax
0x18000b891  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000b895  mov     [rbp+var_10], rax
0x18000b899  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000b89d  mov     qword ptr [rbp+PerformanceCount], rax
0x18000b8a1  call    cs:__imp_GetSystemTimeAsFileTime
0x18000b8a7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000b8ab  mov     [rbp+var_10], rax
0x18000b8af  call    cs:__imp_GetCurrentThreadId
0x18000b8b5  mov     eax, eax
0x18000b8b7  xor     [rbp+var_10], rax
0x18000b8bb  call    cs:__imp_GetCurrentProcessId
0x18000b8c1  mov     eax, eax
0x18000b8c3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000b8c7  xor     [rbp+var_10], rax
0x18000b8cb  call    cs:__imp_QueryPerformanceCounter
0x18000b8d1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000b8d4  lea     rcx, [rbp+var_10]
0x18000b8d8  shl     rax, 20h
0x18000b8dc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000b8e0  xor     rax, [rbp+var_10]
0x18000b8e4  xor     rax, rcx
0x18000b8e7  mov     rcx, 0FFFFFFFFFFFFh
0x18000b8f1  and     rax, rcx
0x18000b8f4  mov     rcx, 2B992DDFA233h
0x18000b8fe  cmp     rax, rbx
0x18000b901  cmovz   rax, rcx
0x18000b905  mov     cs:__security_cookie, rax
0x18000b90c  mov     rbx, [rsp+30h+arg_10]
0x18000b911  not     rax
0x18000b914  mov     cs:__security_cookie_complement, rax
0x18000b91b  add     rsp, 30h
0x18000b91f  pop     rbp
0x18000b920  retn
```
