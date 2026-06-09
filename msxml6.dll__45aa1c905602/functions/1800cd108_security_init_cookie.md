# __security_init_cookie

- ea: `0x1800cd108`
- end: `0x1800cd1bd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800ccdb4`

## callees

- `0x1800cd108`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cd157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cd157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd14b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd14b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cd167`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cd167`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd13d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd13d`

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
0x1800cd108  mov     [rsp-8+arg_10], rbx
0x1800cd10d  push    rbp
0x1800cd10e  mov     rbp, rsp
0x1800cd111  sub     rsp, 30h
0x1800cd115  mov     rax, cs:__security_cookie
0x1800cd11c  mov     rbx, 2B992DDFA232h
0x1800cd126  cmp     rax, rbx
0x1800cd129  jnz     short loc_1800CD1A8
0x1800cd12b  xor     eax, eax
0x1800cd12d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800cd131  mov     [rbp+var_10], rax
0x1800cd135  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800cd139  mov     qword ptr [rbp+PerformanceCount], rax
0x1800cd13d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800cd143  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800cd147  mov     [rbp+var_10], rax
0x1800cd14b  call    cs:__imp_GetCurrentThreadId
0x1800cd151  mov     eax, eax
0x1800cd153  xor     [rbp+var_10], rax
0x1800cd157  call    cs:__imp_GetCurrentProcessId
0x1800cd15d  mov     eax, eax
0x1800cd15f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800cd163  xor     [rbp+var_10], rax
0x1800cd167  call    cs:__imp_QueryPerformanceCounter
0x1800cd16d  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800cd170  lea     rcx, [rbp+var_10]
0x1800cd174  shl     rax, 20h
0x1800cd178  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800cd17c  xor     rax, [rbp+var_10]
0x1800cd180  xor     rax, rcx
0x1800cd183  mov     rcx, 0FFFFFFFFFFFFh
0x1800cd18d  and     rax, rcx
0x1800cd190  mov     rcx, 2B992DDFA233h
0x1800cd19a  cmp     rax, rbx
0x1800cd19d  cmovz   rax, rcx
0x1800cd1a1  mov     cs:__security_cookie, rax
0x1800cd1a8  mov     rbx, [rsp+30h+arg_10]
0x1800cd1ad  not     rax
0x1800cd1b0  mov     cs:__security_cookie_complement, rax
0x1800cd1b7  add     rsp, 30h
0x1800cd1bb  pop     rbp
0x1800cd1bc  retn
```
