# __security_init_cookie

- ea: `0x180002380`
- end: `0x180002435`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b50`

## callees

- `0x180002380`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023b5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023df`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023df`

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
0x180002380  mov     [rsp-8+arg_10], rbx
0x180002385  push    rbp
0x180002386  mov     rbp, rsp
0x180002389  sub     rsp, 30h
0x18000238d  mov     rax, cs:__security_cookie
0x180002394  mov     rbx, 2B992DDFA232h
0x18000239e  cmp     rax, rbx
0x1800023a1  jnz     short loc_180002420
0x1800023a3  xor     eax, eax
0x1800023a5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800023a9  mov     [rbp+var_10], rax
0x1800023ad  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800023b1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800023b5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800023bb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800023bf  mov     [rbp+var_10], rax
0x1800023c3  call    cs:__imp_GetCurrentThreadId
0x1800023c9  mov     eax, eax
0x1800023cb  xor     [rbp+var_10], rax
0x1800023cf  call    cs:__imp_GetCurrentProcessId
0x1800023d5  mov     eax, eax
0x1800023d7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800023db  xor     [rbp+var_10], rax
0x1800023df  call    cs:__imp_QueryPerformanceCounter
0x1800023e5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800023e8  lea     rcx, [rbp+var_10]
0x1800023ec  shl     rax, 20h
0x1800023f0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800023f4  xor     rax, [rbp+var_10]
0x1800023f8  xor     rax, rcx
0x1800023fb  mov     rcx, 0FFFFFFFFFFFFh
0x180002405  and     rax, rcx
0x180002408  mov     rcx, 2B992DDFA233h
0x180002412  cmp     rax, rbx
0x180002415  cmovz   rax, rcx
0x180002419  mov     cs:__security_cookie, rax
0x180002420  mov     rbx, [rsp+30h+arg_10]
0x180002425  not     rax
0x180002428  mov     cs:__security_cookie_complement, rax
0x18000242f  add     rsp, 30h
0x180002433  pop     rbp
0x180002434  retn
```
