# __security_init_cookie

- ea: `0x1800048e4`
- end: `0x180004999`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004870`

## callees

- `0x1800048e4`

## import_xrefs

- `api-ms-win-downlevel-kernel32-l1-1-0!QueryPerformanceCounter` at `0x180004943`
- `api-ms-win-downlevel-kernel32-l1-1-0!QueryPerformanceCounter` at `0x180004943`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentThreadId` at `0x180004927`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentThreadId` at `0x180004927`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetSystemTimeAsFileTime` at `0x180004919`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetSystemTimeAsFileTime` at `0x180004919`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x180004933`
- `api-ms-win-downlevel-kernel32-l1-1-0!GetCurrentProcessId` at `0x180004933`

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
0x1800048e4  mov     [rsp-8+arg_10], rbx
0x1800048e9  push    rbp
0x1800048ea  mov     rbp, rsp
0x1800048ed  sub     rsp, 30h
0x1800048f1  mov     rax, cs:__security_cookie
0x1800048f8  mov     rbx, 2B992DDFA232h
0x180004902  cmp     rax, rbx
0x180004905  jnz     short loc_180004984
0x180004907  xor     eax, eax
0x180004909  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000490d  mov     [rbp+var_10], rax
0x180004911  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004915  mov     qword ptr [rbp+PerformanceCount], rax
0x180004919  call    cs:__imp_GetSystemTimeAsFileTime
0x18000491f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004923  mov     [rbp+var_10], rax
0x180004927  call    cs:__imp_GetCurrentThreadId
0x18000492d  mov     eax, eax
0x18000492f  xor     [rbp+var_10], rax
0x180004933  call    cs:__imp_GetCurrentProcessId
0x180004939  mov     eax, eax
0x18000493b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000493f  xor     [rbp+var_10], rax
0x180004943  call    cs:__imp_QueryPerformanceCounter
0x180004949  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000494c  lea     rcx, [rbp+var_10]
0x180004950  shl     rax, 20h
0x180004954  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004958  xor     rax, [rbp+var_10]
0x18000495c  xor     rax, rcx
0x18000495f  mov     rcx, 0FFFFFFFFFFFFh
0x180004969  and     rax, rcx
0x18000496c  mov     rcx, 2B992DDFA233h
0x180004976  cmp     rax, rbx
0x180004979  cmovz   rax, rcx
0x18000497d  mov     cs:__security_cookie, rax
0x180004984  mov     rbx, [rsp+30h+arg_10]
0x180004989  not     rax
0x18000498c  mov     cs:__security_cookie_complement, rax
0x180004993  add     rsp, 30h
0x180004997  pop     rbp
0x180004998  retn
```
