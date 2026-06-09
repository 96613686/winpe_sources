# __security_init_cookie

- ea: `0x18001ea40`
- end: `0x18001eaf5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001e470`

## callees

- `0x18001ea40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ea75`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001ea75`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ea8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001ea8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ea83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ea83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ea9f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001ea9f`

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
0x18001ea40  mov     [rsp-8+arg_10], rbx
0x18001ea45  push    rbp
0x18001ea46  mov     rbp, rsp
0x18001ea49  sub     rsp, 30h
0x18001ea4d  mov     rax, cs:__security_cookie
0x18001ea54  mov     rbx, 2B992DDFA232h
0x18001ea5e  cmp     rax, rbx
0x18001ea61  jnz     short loc_18001EAE0
0x18001ea63  xor     eax, eax
0x18001ea65  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001ea69  mov     [rbp+var_10], rax
0x18001ea6d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001ea71  mov     qword ptr [rbp+PerformanceCount], rax
0x18001ea75  call    cs:__imp_GetSystemTimeAsFileTime
0x18001ea7b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001ea7f  mov     [rbp+var_10], rax
0x18001ea83  call    cs:__imp_GetCurrentThreadId
0x18001ea89  mov     eax, eax
0x18001ea8b  xor     [rbp+var_10], rax
0x18001ea8f  call    cs:__imp_GetCurrentProcessId
0x18001ea95  mov     eax, eax
0x18001ea97  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001ea9b  xor     [rbp+var_10], rax
0x18001ea9f  call    cs:__imp_QueryPerformanceCounter
0x18001eaa5  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001eaa8  lea     rcx, [rbp+var_10]
0x18001eaac  shl     rax, 20h
0x18001eab0  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001eab4  xor     rax, [rbp+var_10]
0x18001eab8  xor     rax, rcx
0x18001eabb  mov     rcx, 0FFFFFFFFFFFFh
0x18001eac5  and     rax, rcx
0x18001eac8  mov     rcx, 2B992DDFA233h
0x18001ead2  cmp     rax, rbx
0x18001ead5  cmovz   rax, rcx
0x18001ead9  mov     cs:__security_cookie, rax
0x18001eae0  mov     rbx, [rsp+30h+arg_10]
0x18001eae5  not     rax
0x18001eae8  mov     cs:__security_cookie_complement, rax
0x18001eaef  add     rsp, 30h
0x18001eaf3  pop     rbp
0x18001eaf4  retn
```
