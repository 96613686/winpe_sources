# __security_init_cookie

- ea: `0x18000e314`
- end: `0x18000e3c9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000e2a0`

## callees

- `0x18000e314`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000e363`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e357`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e357`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e373`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000e373`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e349`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000e349`

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
0x18000e314  mov     [rsp-8+arg_10], rbx
0x18000e319  push    rbp
0x18000e31a  mov     rbp, rsp
0x18000e31d  sub     rsp, 30h
0x18000e321  mov     rax, cs:__security_cookie
0x18000e328  mov     rbx, 2B992DDFA232h
0x18000e332  cmp     rax, rbx
0x18000e335  jnz     short loc_18000E3B4
0x18000e337  xor     eax, eax
0x18000e339  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000e33d  mov     [rbp+var_10], rax
0x18000e341  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000e345  mov     qword ptr [rbp+PerformanceCount], rax
0x18000e349  call    cs:__imp_GetSystemTimeAsFileTime
0x18000e34f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000e353  mov     [rbp+var_10], rax
0x18000e357  call    cs:__imp_GetCurrentThreadId
0x18000e35d  mov     eax, eax
0x18000e35f  xor     [rbp+var_10], rax
0x18000e363  call    cs:__imp_GetCurrentProcessId
0x18000e369  mov     eax, eax
0x18000e36b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000e36f  xor     [rbp+var_10], rax
0x18000e373  call    cs:__imp_QueryPerformanceCounter
0x18000e379  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000e37c  lea     rcx, [rbp+var_10]
0x18000e380  shl     rax, 20h
0x18000e384  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000e388  xor     rax, [rbp+var_10]
0x18000e38c  xor     rax, rcx
0x18000e38f  mov     rcx, 0FFFFFFFFFFFFh
0x18000e399  and     rax, rcx
0x18000e39c  mov     rcx, 2B992DDFA233h
0x18000e3a6  cmp     rax, rbx
0x18000e3a9  cmovz   rax, rcx
0x18000e3ad  mov     cs:__security_cookie, rax
0x18000e3b4  mov     rbx, [rsp+30h+arg_10]
0x18000e3b9  not     rax
0x18000e3bc  mov     cs:__security_cookie_complement, rax
0x18000e3c3  add     rsp, 30h
0x18000e3c7  pop     rbp
0x18000e3c8  retn
```
