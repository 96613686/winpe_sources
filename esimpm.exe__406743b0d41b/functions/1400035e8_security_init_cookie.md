# __security_init_cookie

- ea: `0x1400035e8`
- end: `0x14000369d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002f30`

## callees

- `0x1400035e8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140003637`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000362b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000362b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000361d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000361d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140003647`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140003647`

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
0x1400035e8  mov     [rsp-8+arg_10], rbx
0x1400035ed  push    rbp
0x1400035ee  mov     rbp, rsp
0x1400035f1  sub     rsp, 30h
0x1400035f5  mov     rax, cs:__security_cookie
0x1400035fc  mov     rbx, 2B992DDFA232h
0x140003606  cmp     rax, rbx
0x140003609  jnz     short loc_140003688
0x14000360b  xor     eax, eax
0x14000360d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003611  mov     [rbp+var_10], rax
0x140003615  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140003619  mov     qword ptr [rbp+PerformanceCount], rax
0x14000361d  call    cs:__imp_GetSystemTimeAsFileTime
0x140003623  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140003627  mov     [rbp+var_10], rax
0x14000362b  call    cs:__imp_GetCurrentThreadId
0x140003631  mov     eax, eax
0x140003633  xor     [rbp+var_10], rax
0x140003637  call    cs:__imp_GetCurrentProcessId
0x14000363d  mov     eax, eax
0x14000363f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140003643  xor     [rbp+var_10], rax
0x140003647  call    cs:__imp_QueryPerformanceCounter
0x14000364d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140003650  lea     rcx, [rbp+var_10]
0x140003654  shl     rax, 20h
0x140003658  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000365c  xor     rax, [rbp+var_10]
0x140003660  xor     rax, rcx
0x140003663  mov     rcx, 0FFFFFFFFFFFFh
0x14000366d  and     rax, rcx
0x140003670  mov     rcx, 2B992DDFA233h
0x14000367a  cmp     rax, rbx
0x14000367d  cmovz   rax, rcx
0x140003681  mov     cs:__security_cookie, rax
0x140003688  mov     rbx, [rsp+30h+arg_10]
0x14000368d  not     rax
0x140003690  mov     cs:__security_cookie_complement, rax
0x140003697  add     rsp, 30h
0x14000369b  pop     rbp
0x14000369c  retn
```
