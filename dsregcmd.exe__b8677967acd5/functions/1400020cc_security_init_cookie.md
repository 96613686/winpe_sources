# __security_init_cookie

- ea: `0x1400020cc`
- end: `0x140002181`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001b30`

## callees

- `0x1400020cc`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000212b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x14000212b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000210f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000210f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000211b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000211b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002101`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002101`

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
0x1400020cc  mov     [rsp-8+arg_10], rbx
0x1400020d1  push    rbp
0x1400020d2  mov     rbp, rsp
0x1400020d5  sub     rsp, 30h
0x1400020d9  mov     rax, cs:__security_cookie
0x1400020e0  mov     rbx, 2B992DDFA232h
0x1400020ea  cmp     rax, rbx
0x1400020ed  jnz     short loc_14000216C
0x1400020ef  xor     eax, eax
0x1400020f1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400020f5  mov     [rbp+var_10], rax
0x1400020f9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400020fd  mov     qword ptr [rbp+PerformanceCount], rax
0x140002101  call    cs:__imp_GetSystemTimeAsFileTime
0x140002107  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x14000210b  mov     [rbp+var_10], rax
0x14000210f  call    cs:__imp_GetCurrentThreadId
0x140002115  mov     eax, eax
0x140002117  xor     [rbp+var_10], rax
0x14000211b  call    cs:__imp_GetCurrentProcessId
0x140002121  mov     eax, eax
0x140002123  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002127  xor     [rbp+var_10], rax
0x14000212b  call    cs:__imp_QueryPerformanceCounter
0x140002131  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002134  lea     rcx, [rbp+var_10]
0x140002138  shl     rax, 20h
0x14000213c  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002140  xor     rax, [rbp+var_10]
0x140002144  xor     rax, rcx
0x140002147  mov     rcx, 0FFFFFFFFFFFFh
0x140002151  and     rax, rcx
0x140002154  mov     rcx, 2B992DDFA233h
0x14000215e  cmp     rax, rbx
0x140002161  cmovz   rax, rcx
0x140002165  mov     cs:__security_cookie, rax
0x14000216c  mov     rbx, [rsp+30h+arg_10]
0x140002171  not     rax
0x140002174  mov     cs:__security_cookie_complement, rax
0x14000217b  add     rsp, 30h
0x14000217f  pop     rbp
0x140002180  retn
```
