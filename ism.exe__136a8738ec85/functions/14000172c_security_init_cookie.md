# __security_init_cookie

- ea: `0x14000172c`
- end: `0x1400017e1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001430`

## callees

- `0x14000172c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000176f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000176f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000177b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000177b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000178b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000178b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001761`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001761`

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
0x14000172c  mov     [rsp-8+arg_10], rbx
0x140001731  push    rbp
0x140001732  mov     rbp, rsp
0x140001735  sub     rsp, 30h
0x140001739  mov     rax, cs:__security_cookie
0x140001740  mov     rbx, 2B992DDFA232h
0x14000174a  cmp     rax, rbx
0x14000174d  jnz     short loc_1400017CC
0x14000174f  xor     eax, eax
0x140001751  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140001755  mov     [rbp+var_10], rax
0x140001759  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000175d  mov     qword ptr [rbp+PerformanceCount], rax
0x140001761  call    cs:__imp_GetSystemTimeAsFileTime
0x140001767  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000176b  mov     [rbp+var_10], rax
0x14000176f  call    cs:__imp_GetCurrentThreadId
0x140001775  mov     eax, eax
0x140001777  xor     [rbp+var_10], rax
0x14000177b  call    cs:__imp_GetCurrentProcessId
0x140001781  mov     eax, eax
0x140001783  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140001787  xor     [rbp+var_10], rax
0x14000178b  call    cs:__imp_QueryPerformanceCounter
0x140001791  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001794  lea     rcx, [rbp+var_10]
0x140001798  shl     rax, 20h
0x14000179c  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400017a0  xor     rax, [rbp+var_10]
0x1400017a4  xor     rax, rcx
0x1400017a7  mov     rcx, 0FFFFFFFFFFFFh
0x1400017b1  and     rax, rcx
0x1400017b4  mov     rcx, 2B992DDFA233h
0x1400017be  cmp     rax, rbx
0x1400017c1  cmovz   rax, rcx
0x1400017c5  mov     cs:__security_cookie, rax
0x1400017cc  mov     rbx, [rsp+30h+arg_10]
0x1400017d1  not     rax
0x1400017d4  mov     cs:__security_cookie_complement, rax
0x1400017db  add     rsp, 30h
0x1400017df  pop     rbp
0x1400017e0  retn
```
