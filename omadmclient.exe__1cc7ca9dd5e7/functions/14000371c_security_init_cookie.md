# __security_init_cookie

- ea: `0x14000371c`
- end: `0x1400037d1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140003420`

## callees

- `0x14000371c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000376b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000376b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000375f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000375f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003751`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003751`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000377b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000377b`

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
0x14000371c  mov     [rsp-8+arg_10], rbx
0x140003721  push    rbp
0x140003722  mov     rbp, rsp
0x140003725  sub     rsp, 30h
0x140003729  mov     rax, cs:__security_cookie
0x140003730  mov     rbx, 2B992DDFA232h
0x14000373a  cmp     rax, rbx
0x14000373d  jnz     short loc_1400037BC
0x14000373f  xor     eax, eax
0x140003741  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003745  mov     [rbp+var_10], rax
0x140003749  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x14000374d  mov     qword ptr [rbp+PerformanceCount], rax
0x140003751  call    cs:__imp_GetSystemTimeAsFileTime
0x140003757  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000375b  mov     [rbp+var_10], rax
0x14000375f  call    cs:__imp_GetCurrentThreadId
0x140003765  mov     eax, eax
0x140003767  xor     [rbp+var_10], rax
0x14000376b  call    cs:__imp_GetCurrentProcessId
0x140003771  mov     eax, eax
0x140003773  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140003777  xor     [rbp+var_10], rax
0x14000377b  call    cs:__imp_QueryPerformanceCounter
0x140003781  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003784  lea     rcx, [rbp+var_10]
0x140003788  shl     rax, 20h
0x14000378c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140003790  xor     rax, [rbp+var_10]
0x140003794  xor     rax, rcx
0x140003797  mov     rcx, 0FFFFFFFFFFFFh
0x1400037a1  and     rax, rcx
0x1400037a4  mov     rcx, 2B992DDFA233h
0x1400037ae  cmp     rax, rbx
0x1400037b1  cmovz   rax, rcx
0x1400037b5  mov     cs:__security_cookie, rax
0x1400037bc  mov     rbx, [rsp+30h+arg_10]
0x1400037c1  not     rax
0x1400037c4  mov     cs:__security_cookie_complement, rax
0x1400037cb  add     rsp, 30h
0x1400037cf  pop     rbp
0x1400037d0  retn
```
