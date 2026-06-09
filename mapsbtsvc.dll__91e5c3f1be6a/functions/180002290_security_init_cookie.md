# __security_init_cookie

- ea: `0x180002290`
- end: `0x180002345`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001e10`

## callees

- `0x180002290`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800022ef`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800022ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800022df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800022df`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800022d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800022d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800022c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800022c5`

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
0x180002290  mov     [rsp-8+arg_10], rbx
0x180002295  push    rbp
0x180002296  mov     rbp, rsp
0x180002299  sub     rsp, 30h
0x18000229d  mov     rax, cs:__security_cookie
0x1800022a4  mov     rbx, 2B992DDFA232h
0x1800022ae  cmp     rax, rbx
0x1800022b1  jnz     short loc_180002330
0x1800022b3  xor     eax, eax
0x1800022b5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800022b9  mov     [rbp+var_10], rax
0x1800022bd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800022c1  mov     qword ptr [rbp+PerformanceCount], rax
0x1800022c5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800022cb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800022cf  mov     [rbp+var_10], rax
0x1800022d3  call    cs:__imp_GetCurrentThreadId
0x1800022d9  mov     eax, eax
0x1800022db  xor     [rbp+var_10], rax
0x1800022df  call    cs:__imp_GetCurrentProcessId
0x1800022e5  mov     eax, eax
0x1800022e7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800022eb  xor     [rbp+var_10], rax
0x1800022ef  call    cs:__imp_QueryPerformanceCounter
0x1800022f5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800022f8  lea     rcx, [rbp+var_10]
0x1800022fc  shl     rax, 20h
0x180002300  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002304  xor     rax, [rbp+var_10]
0x180002308  xor     rax, rcx
0x18000230b  mov     rcx, 0FFFFFFFFFFFFh
0x180002315  and     rax, rcx
0x180002318  mov     rcx, 2B992DDFA233h
0x180002322  cmp     rax, rbx
0x180002325  cmovz   rax, rcx
0x180002329  mov     cs:__security_cookie, rax
0x180002330  mov     rbx, [rsp+30h+arg_10]
0x180002335  not     rax
0x180002338  mov     cs:__security_cookie_complement, rax
0x18000233f  add     rsp, 30h
0x180002343  pop     rbp
0x180002344  retn
```
