# __security_init_cookie

- ea: `0x1400022d0`
- end: `0x140002385`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001c20`

## callees

- `0x1400022d0`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002305`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002305`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000232f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000232f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000231f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000231f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002313`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002313`

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
0x1400022d0  mov     [rsp-8+arg_10], rbx
0x1400022d5  push    rbp
0x1400022d6  mov     rbp, rsp
0x1400022d9  sub     rsp, 30h
0x1400022dd  mov     rax, cs:__security_cookie
0x1400022e4  mov     rbx, 2B992DDFA232h
0x1400022ee  cmp     rax, rbx
0x1400022f1  jnz     short loc_140002370
0x1400022f3  xor     eax, eax
0x1400022f5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400022f9  mov     [rbp+var_10], rax
0x1400022fd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002301  mov     qword ptr [rbp+PerformanceCount], rax
0x140002305  call    cs:__imp_GetSystemTimeAsFileTime
0x14000230b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000230f  mov     [rbp+var_10], rax
0x140002313  call    cs:__imp_GetCurrentThreadId
0x140002319  mov     eax, eax
0x14000231b  xor     [rbp+var_10], rax
0x14000231f  call    cs:__imp_GetCurrentProcessId
0x140002325  mov     eax, eax
0x140002327  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000232b  xor     [rbp+var_10], rax
0x14000232f  call    cs:__imp_QueryPerformanceCounter
0x140002335  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002338  lea     rcx, [rbp+var_10]
0x14000233c  shl     rax, 20h
0x140002340  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002344  xor     rax, [rbp+var_10]
0x140002348  xor     rax, rcx
0x14000234b  mov     rcx, 0FFFFFFFFFFFFh
0x140002355  and     rax, rcx
0x140002358  mov     rcx, 2B992DDFA233h
0x140002362  cmp     rax, rbx
0x140002365  cmovz   rax, rcx
0x140002369  mov     cs:__security_cookie, rax
0x140002370  mov     rbx, [rsp+30h+arg_10]
0x140002375  not     rax
0x140002378  mov     cs:__security_cookie_complement, rax
0x14000237f  add     rsp, 30h
0x140002383  pop     rbp
0x140002384  retn
```
