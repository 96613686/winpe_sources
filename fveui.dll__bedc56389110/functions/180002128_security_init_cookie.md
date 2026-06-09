# __security_init_cookie

- ea: `0x180002128`
- end: `0x1800021dd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001b60`

## callees

- `0x180002128`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000215d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000215d`
- `KERNEL32!QueryPerformanceCounter` at `0x180002187`
- `KERNEL32!QueryPerformanceCounter` at `0x180002187`
- `KERNEL32!GetCurrentProcessId` at `0x180002177`
- `KERNEL32!GetCurrentProcessId` at `0x180002177`
- `KERNEL32!GetCurrentThreadId` at `0x18000216b`
- `KERNEL32!GetCurrentThreadId` at `0x18000216b`

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
0x180002128  mov     [rsp-8+arg_10], rbx
0x18000212d  push    rbp
0x18000212e  mov     rbp, rsp
0x180002131  sub     rsp, 30h
0x180002135  mov     rax, cs:__security_cookie
0x18000213c  mov     rbx, 2B992DDFA232h
0x180002146  cmp     rax, rbx
0x180002149  jnz     short loc_1800021C8
0x18000214b  xor     eax, eax
0x18000214d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002151  mov     [rbp+var_10], rax
0x180002155  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002159  mov     qword ptr [rbp+PerformanceCount], rax
0x18000215d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002163  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002167  mov     [rbp+var_10], rax
0x18000216b  call    cs:__imp_GetCurrentThreadId
0x180002171  mov     eax, eax
0x180002173  xor     [rbp+var_10], rax
0x180002177  call    cs:__imp_GetCurrentProcessId
0x18000217d  mov     eax, eax
0x18000217f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002183  xor     [rbp+var_10], rax
0x180002187  call    cs:__imp_QueryPerformanceCounter
0x18000218d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002190  lea     rcx, [rbp+var_10]
0x180002194  shl     rax, 20h
0x180002198  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000219c  xor     rax, [rbp+var_10]
0x1800021a0  xor     rax, rcx
0x1800021a3  mov     rcx, 0FFFFFFFFFFFFh
0x1800021ad  and     rax, rcx
0x1800021b0  mov     rcx, 2B992DDFA233h
0x1800021ba  cmp     rax, rbx
0x1800021bd  cmovz   rax, rcx
0x1800021c1  mov     cs:__security_cookie, rax
0x1800021c8  mov     rbx, [rsp+30h+arg_10]
0x1800021cd  not     rax
0x1800021d0  mov     cs:__security_cookie_complement, rax
0x1800021d7  add     rsp, 30h
0x1800021db  pop     rbp
0x1800021dc  retn
```
