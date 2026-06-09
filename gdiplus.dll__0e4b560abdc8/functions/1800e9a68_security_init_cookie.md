# __security_init_cookie

- ea: `0x1800e9a68`
- end: `0x1800e9b19`
- name: `__security_init_cookie`
- size: `177`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800e9330`

## callees

- `0x1800e9a68`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e9aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e9aa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e9ab3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800e9ab3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e9a99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800e9a99`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e9ac3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e9ac3`

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
0x1800e9a68  mov     [rsp-8+arg_10], rbx
0x1800e9a6d  push    rbp
0x1800e9a6e  mov     rbp, rsp
0x1800e9a71  sub     rsp, 30h
0x1800e9a75  mov     rax, cs:__security_cookie
0x1800e9a7c  mov     rbx, 2B992DDFA232h
0x1800e9a86  cmp     rax, rbx
0x1800e9a89  jnz     short loc_1800E9B04
0x1800e9a8b  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800e9a90  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800e9a94  and     qword ptr [rbp+PerformanceCount], 0
0x1800e9a99  call    cs:__imp_GetSystemTimeAsFileTime
0x1800e9a9f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800e9aa3  mov     [rbp+var_10], rax
0x1800e9aa7  call    cs:__imp_GetCurrentThreadId
0x1800e9aad  mov     eax, eax
0x1800e9aaf  xor     [rbp+var_10], rax
0x1800e9ab3  call    cs:__imp_GetCurrentProcessId
0x1800e9ab9  mov     eax, eax
0x1800e9abb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800e9abf  xor     [rbp+var_10], rax
0x1800e9ac3  call    cs:__imp_QueryPerformanceCounter
0x1800e9ac9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800e9acc  lea     rcx, [rbp+var_10]
0x1800e9ad0  shl     rax, 20h
0x1800e9ad4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800e9ad8  xor     rax, [rbp+var_10]
0x1800e9adc  xor     rax, rcx
0x1800e9adf  mov     rcx, 0FFFFFFFFFFFFh
0x1800e9ae9  and     rax, rcx
0x1800e9aec  mov     rcx, 2B992DDFA233h
0x1800e9af6  cmp     rax, rbx
0x1800e9af9  cmovz   rax, rcx
0x1800e9afd  mov     cs:__security_cookie, rax
0x1800e9b04  mov     rbx, [rsp+30h+arg_10]
0x1800e9b09  not     rax
0x1800e9b0c  mov     cs:__security_cookie_complement, rax
0x1800e9b13  add     rsp, 30h
0x1800e9b17  pop     rbp
0x1800e9b18  retn
```
