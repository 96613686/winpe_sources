# __security_init_cookie

- ea: `0x180120488`
- end: `0x18012053d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180120414`

## callees

- `0x180120488`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801204e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1801204e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801204cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1801204cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801204d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1801204d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801204bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1801204bd`

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
0x180120488  mov     [rsp-8+arg_10], rbx
0x18012048d  push    rbp
0x18012048e  mov     rbp, rsp
0x180120491  sub     rsp, 30h
0x180120495  mov     rax, cs:__security_cookie
0x18012049c  mov     rbx, 2B992DDFA232h
0x1801204a6  cmp     rax, rbx
0x1801204a9  jnz     short loc_180120528
0x1801204ab  xor     eax, eax
0x1801204ad  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801204b1  mov     [rbp+var_10], rax
0x1801204b5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1801204b9  mov     qword ptr [rbp+PerformanceCount], rax
0x1801204bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1801204c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801204c7  mov     [rbp+var_10], rax
0x1801204cb  call    cs:__imp_GetCurrentThreadId
0x1801204d1  mov     eax, eax
0x1801204d3  xor     [rbp+var_10], rax
0x1801204d7  call    cs:__imp_GetCurrentProcessId
0x1801204dd  mov     eax, eax
0x1801204df  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1801204e3  xor     [rbp+var_10], rax
0x1801204e7  call    cs:__imp_QueryPerformanceCounter
0x1801204ed  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801204f0  lea     rcx, [rbp+var_10]
0x1801204f4  shl     rax, 20h
0x1801204f8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801204fc  xor     rax, [rbp+var_10]
0x180120500  xor     rax, rcx
0x180120503  mov     rcx, 0FFFFFFFFFFFFh
0x18012050d  and     rax, rcx
0x180120510  mov     rcx, 2B992DDFA233h
0x18012051a  cmp     rax, rbx
0x18012051d  cmovz   rax, rcx
0x180120521  mov     cs:__security_cookie, rax
0x180120528  mov     rbx, [rsp+30h+arg_10]
0x18012052d  not     rax
0x180120530  mov     cs:__security_cookie_complement, rax
0x180120537  add     rsp, 30h
0x18012053b  pop     rbp
0x18012053c  retn
```
