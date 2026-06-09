# __security_init_cookie

- ea: `0x1800020f8`
- end: `0x1800021ad`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c90`

## callees

- `0x1800020f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000213b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000213b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002147`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002147`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002157`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002157`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000212d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000212d`

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
0x1800020f8  mov     [rsp-8+arg_10], rbx
0x1800020fd  push    rbp
0x1800020fe  mov     rbp, rsp
0x180002101  sub     rsp, 30h
0x180002105  mov     rax, cs:__security_cookie
0x18000210c  mov     rbx, 2B992DDFA232h
0x180002116  cmp     rax, rbx
0x180002119  jnz     short loc_180002198
0x18000211b  xor     eax, eax
0x18000211d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002121  mov     [rbp+var_10], rax
0x180002125  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002129  mov     qword ptr [rbp+PerformanceCount], rax
0x18000212d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002133  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002137  mov     [rbp+var_10], rax
0x18000213b  call    cs:__imp_GetCurrentThreadId
0x180002141  mov     eax, eax
0x180002143  xor     [rbp+var_10], rax
0x180002147  call    cs:__imp_GetCurrentProcessId
0x18000214d  mov     eax, eax
0x18000214f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002153  xor     [rbp+var_10], rax
0x180002157  call    cs:__imp_QueryPerformanceCounter
0x18000215d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002160  lea     rcx, [rbp+var_10]
0x180002164  shl     rax, 20h
0x180002168  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000216c  xor     rax, [rbp+var_10]
0x180002170  xor     rax, rcx
0x180002173  mov     rcx, 0FFFFFFFFFFFFh
0x18000217d  and     rax, rcx
0x180002180  mov     rcx, 2B992DDFA233h
0x18000218a  cmp     rax, rbx
0x18000218d  cmovz   rax, rcx
0x180002191  mov     cs:__security_cookie, rax
0x180002198  mov     rbx, [rsp+30h+arg_10]
0x18000219d  not     rax
0x1800021a0  mov     cs:__security_cookie_complement, rax
0x1800021a7  add     rsp, 30h
0x1800021ab  pop     rbp
0x1800021ac  retn
```
