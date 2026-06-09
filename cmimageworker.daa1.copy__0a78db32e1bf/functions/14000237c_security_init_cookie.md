# __security_init_cookie

- ea: `0x14000237c`
- end: `0x140002431`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002080`

## callees

- `0x14000237c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400023bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400023bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400023cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400023cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400023db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400023db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400023b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400023b1`

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
0x14000237c  mov     [rsp-8+arg_10], rbx
0x140002381  push    rbp
0x140002382  mov     rbp, rsp
0x140002385  sub     rsp, 30h
0x140002389  mov     rax, cs:__security_cookie
0x140002390  mov     rbx, 2B992DDFA232h
0x14000239a  cmp     rax, rbx
0x14000239d  jnz     short loc_14000241C
0x14000239f  xor     eax, eax
0x1400023a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400023a5  mov     [rbp+var_10], rax
0x1400023a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400023ad  mov     qword ptr [rbp+PerformanceCount], rax
0x1400023b1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400023b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400023bb  mov     [rbp+var_10], rax
0x1400023bf  call    cs:__imp_GetCurrentThreadId
0x1400023c5  mov     eax, eax
0x1400023c7  xor     [rbp+var_10], rax
0x1400023cb  call    cs:__imp_GetCurrentProcessId
0x1400023d1  mov     eax, eax
0x1400023d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400023d7  xor     [rbp+var_10], rax
0x1400023db  call    cs:__imp_QueryPerformanceCounter
0x1400023e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400023e4  lea     rcx, [rbp+var_10]
0x1400023e8  shl     rax, 20h
0x1400023ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400023f0  xor     rax, [rbp+var_10]
0x1400023f4  xor     rax, rcx
0x1400023f7  mov     rcx, 0FFFFFFFFFFFFh
0x140002401  and     rax, rcx
0x140002404  mov     rcx, 2B992DDFA233h
0x14000240e  cmp     rax, rbx
0x140002411  cmovz   rax, rcx
0x140002415  mov     cs:__security_cookie, rax
0x14000241c  mov     rbx, [rsp+30h+arg_10]
0x140002421  not     rax
0x140002424  mov     cs:__security_cookie_complement, rax
0x14000242b  add     rsp, 30h
0x14000242f  pop     rbp
0x140002430  retn
```
