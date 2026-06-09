# __security_init_cookie

- ea: `0x180002394`
- end: `0x180002449`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001f10`

## callees

- `0x180002394`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800023d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800023e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023c9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800023c9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023f3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800023f3`

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
0x180002394  mov     [rsp-8+arg_10], rbx
0x180002399  push    rbp
0x18000239a  mov     rbp, rsp
0x18000239d  sub     rsp, 30h
0x1800023a1  mov     rax, cs:__security_cookie
0x1800023a8  mov     rbx, 2B992DDFA232h
0x1800023b2  cmp     rax, rbx
0x1800023b5  jnz     short loc_180002434
0x1800023b7  xor     eax, eax
0x1800023b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800023bd  mov     [rbp+var_10], rax
0x1800023c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800023c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800023c9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800023cf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800023d3  mov     [rbp+var_10], rax
0x1800023d7  call    cs:__imp_GetCurrentThreadId
0x1800023dd  mov     eax, eax
0x1800023df  xor     [rbp+var_10], rax
0x1800023e3  call    cs:__imp_GetCurrentProcessId
0x1800023e9  mov     eax, eax
0x1800023eb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800023ef  xor     [rbp+var_10], rax
0x1800023f3  call    cs:__imp_QueryPerformanceCounter
0x1800023f9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800023fc  lea     rcx, [rbp+var_10]
0x180002400  shl     rax, 20h
0x180002404  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002408  xor     rax, [rbp+var_10]
0x18000240c  xor     rax, rcx
0x18000240f  mov     rcx, 0FFFFFFFFFFFFh
0x180002419  and     rax, rcx
0x18000241c  mov     rcx, 2B992DDFA233h
0x180002426  cmp     rax, rbx
0x180002429  cmovz   rax, rcx
0x18000242d  mov     cs:__security_cookie, rax
0x180002434  mov     rbx, [rsp+30h+arg_10]
0x180002439  not     rax
0x18000243c  mov     cs:__security_cookie_complement, rax
0x180002443  add     rsp, 30h
0x180002447  pop     rbp
0x180002448  retn
```
