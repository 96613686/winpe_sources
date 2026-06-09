# __security_init_cookie

- ea: `0x18006f87c`
- end: `0x18006f931`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006ecd0`

## callees

- `0x18006f87c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f8bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006f8bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f8cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18006f8cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006f8db`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18006f8db`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006f8b1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006f8b1`

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
0x18006f87c  mov     [rsp-8+arg_10], rbx
0x18006f881  push    rbp
0x18006f882  mov     rbp, rsp
0x18006f885  sub     rsp, 30h
0x18006f889  mov     rax, cs:__security_cookie
0x18006f890  mov     rbx, 2B992DDFA232h
0x18006f89a  cmp     rax, rbx
0x18006f89d  jnz     short loc_18006F91C
0x18006f89f  xor     eax, eax
0x18006f8a1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006f8a5  mov     [rbp+var_10], rax
0x18006f8a9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18006f8ad  mov     qword ptr [rbp+PerformanceCount], rax
0x18006f8b1  call    cs:__imp_GetSystemTimeAsFileTime
0x18006f8b7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18006f8bb  mov     [rbp+var_10], rax
0x18006f8bf  call    cs:__imp_GetCurrentThreadId
0x18006f8c5  mov     eax, eax
0x18006f8c7  xor     [rbp+var_10], rax
0x18006f8cb  call    cs:__imp_GetCurrentProcessId
0x18006f8d1  mov     eax, eax
0x18006f8d3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18006f8d7  xor     [rbp+var_10], rax
0x18006f8db  call    cs:__imp_QueryPerformanceCounter
0x18006f8e1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18006f8e4  lea     rcx, [rbp+var_10]
0x18006f8e8  shl     rax, 20h
0x18006f8ec  xor     rax, qword ptr [rbp+PerformanceCount]
0x18006f8f0  xor     rax, [rbp+var_10]
0x18006f8f4  xor     rax, rcx
0x18006f8f7  mov     rcx, 0FFFFFFFFFFFFh
0x18006f901  and     rax, rcx
0x18006f904  mov     rcx, 2B992DDFA233h
0x18006f90e  cmp     rax, rbx
0x18006f911  cmovz   rax, rcx
0x18006f915  mov     cs:__security_cookie, rax
0x18006f91c  mov     rbx, [rsp+30h+arg_10]
0x18006f921  not     rax
0x18006f924  mov     cs:__security_cookie_complement, rax
0x18006f92b  add     rsp, 30h
0x18006f92f  pop     rbp
0x18006f930  retn
```
