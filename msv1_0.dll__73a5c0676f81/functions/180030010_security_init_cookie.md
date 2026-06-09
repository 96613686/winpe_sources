# __security_init_cookie

- ea: `0x180030010`
- end: `0x1800300c5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002fb00`

## callees

- `0x180030010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003005f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003005f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030045`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180030045`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003006f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003006f`

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
0x180030010  mov     [rsp-8+arg_10], rbx
0x180030015  push    rbp
0x180030016  mov     rbp, rsp
0x180030019  sub     rsp, 30h
0x18003001d  mov     rax, cs:__security_cookie
0x180030024  mov     rbx, 2B992DDFA232h
0x18003002e  cmp     rax, rbx
0x180030031  jnz     short loc_1800300B0
0x180030033  xor     eax, eax
0x180030035  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180030039  mov     [rbp+var_10], rax
0x18003003d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180030041  mov     qword ptr [rbp+PerformanceCount], rax
0x180030045  call    cs:__imp_GetSystemTimeAsFileTime
0x18003004b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003004f  mov     [rbp+var_10], rax
0x180030053  call    cs:__imp_GetCurrentThreadId
0x180030059  mov     eax, eax
0x18003005b  xor     [rbp+var_10], rax
0x18003005f  call    cs:__imp_GetCurrentProcessId
0x180030065  mov     eax, eax
0x180030067  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003006b  xor     [rbp+var_10], rax
0x18003006f  call    cs:__imp_QueryPerformanceCounter
0x180030075  mov     eax, dword ptr [rbp+PerformanceCount]
0x180030078  lea     rcx, [rbp+var_10]
0x18003007c  shl     rax, 20h
0x180030080  xor     rax, qword ptr [rbp+PerformanceCount]
0x180030084  xor     rax, [rbp+var_10]
0x180030088  xor     rax, rcx
0x18003008b  mov     rcx, 0FFFFFFFFFFFFh
0x180030095  and     rax, rcx
0x180030098  mov     rcx, 2B992DDFA233h
0x1800300a2  cmp     rax, rbx
0x1800300a5  cmovz   rax, rcx
0x1800300a9  mov     cs:__security_cookie, rax
0x1800300b0  mov     rbx, [rsp+30h+arg_10]
0x1800300b5  not     rax
0x1800300b8  mov     cs:__security_cookie_complement, rax
0x1800300bf  add     rsp, 30h
0x1800300c3  pop     rbp
0x1800300c4  retn
```
