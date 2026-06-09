# __security_init_cookie

- ea: `0x1800022fc`
- end: `0x1800023b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ea0`

## callees

- `0x1800022fc`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002331`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180002331`
- `KERNEL32!GetCurrentThreadId` at `0x18000233f`
- `KERNEL32!GetCurrentThreadId` at `0x18000233f`
- `KERNEL32!GetCurrentProcessId` at `0x18000234b`
- `KERNEL32!GetCurrentProcessId` at `0x18000234b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000235b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000235b`

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
0x1800022fc  mov     [rsp-8+arg_10], rbx
0x180002301  push    rbp
0x180002302  mov     rbp, rsp
0x180002305  sub     rsp, 30h
0x180002309  mov     rax, cs:__security_cookie
0x180002310  mov     rbx, 2B992DDFA232h
0x18000231a  cmp     rax, rbx
0x18000231d  jnz     short loc_18000239C
0x18000231f  xor     eax, eax
0x180002321  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002325  mov     [rbp+var_10], rax
0x180002329  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000232d  mov     qword ptr [rbp+PerformanceCount], rax
0x180002331  call    cs:__imp_GetSystemTimeAsFileTime
0x180002337  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000233b  mov     [rbp+var_10], rax
0x18000233f  call    cs:__imp_GetCurrentThreadId
0x180002345  mov     eax, eax
0x180002347  xor     [rbp+var_10], rax
0x18000234b  call    cs:__imp_GetCurrentProcessId
0x180002351  mov     eax, eax
0x180002353  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002357  xor     [rbp+var_10], rax
0x18000235b  call    cs:__imp_QueryPerformanceCounter
0x180002361  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002364  lea     rcx, [rbp+var_10]
0x180002368  shl     rax, 20h
0x18000236c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002370  xor     rax, [rbp+var_10]
0x180002374  xor     rax, rcx
0x180002377  mov     rcx, 0FFFFFFFFFFFFh
0x180002381  and     rax, rcx
0x180002384  mov     rcx, 2B992DDFA233h
0x18000238e  cmp     rax, rbx
0x180002391  cmovz   rax, rcx
0x180002395  mov     cs:__security_cookie, rax
0x18000239c  mov     rbx, [rsp+30h+arg_10]
0x1800023a1  not     rax
0x1800023a4  mov     cs:__security_cookie_complement, rax
0x1800023ab  add     rsp, 30h
0x1800023af  pop     rbp
0x1800023b0  retn
```
