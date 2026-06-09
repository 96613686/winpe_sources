# __security_init_cookie

- ea: `0x1400024a8`
- end: `0x14000255d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002040`

## callees

- `0x1400024a8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400024eb`
- `KERNEL32!GetCurrentThreadId` at `0x1400024eb`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400024dd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400024dd`
- `KERNEL32!GetCurrentProcessId` at `0x1400024f7`
- `KERNEL32!GetCurrentProcessId` at `0x1400024f7`
- `KERNEL32!QueryPerformanceCounter` at `0x140002507`
- `KERNEL32!QueryPerformanceCounter` at `0x140002507`

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
0x1400024a8  mov     [rsp-8+arg_10], rbx
0x1400024ad  push    rbp
0x1400024ae  mov     rbp, rsp
0x1400024b1  sub     rsp, 30h
0x1400024b5  mov     rax, cs:__security_cookie
0x1400024bc  mov     rbx, 2B992DDFA232h
0x1400024c6  cmp     rax, rbx
0x1400024c9  jnz     short loc_140002548
0x1400024cb  xor     eax, eax
0x1400024cd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400024d1  mov     [rbp+var_10], rax
0x1400024d5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400024d9  mov     qword ptr [rbp+PerformanceCount], rax
0x1400024dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400024e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400024e7  mov     [rbp+var_10], rax
0x1400024eb  call    cs:__imp_GetCurrentThreadId
0x1400024f1  mov     eax, eax
0x1400024f3  xor     [rbp+var_10], rax
0x1400024f7  call    cs:__imp_GetCurrentProcessId
0x1400024fd  mov     eax, eax
0x1400024ff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002503  xor     [rbp+var_10], rax
0x140002507  call    cs:__imp_QueryPerformanceCounter
0x14000250d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002510  lea     rcx, [rbp+var_10]
0x140002514  shl     rax, 20h
0x140002518  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000251c  xor     rax, [rbp+var_10]
0x140002520  xor     rax, rcx
0x140002523  mov     rcx, 0FFFFFFFFFFFFh
0x14000252d  and     rax, rcx
0x140002530  mov     rcx, 2B992DDFA233h
0x14000253a  cmp     rax, rbx
0x14000253d  cmovz   rax, rcx
0x140002541  mov     cs:__security_cookie, rax
0x140002548  mov     rbx, [rsp+30h+arg_10]
0x14000254d  not     rax
0x140002550  mov     cs:__security_cookie_complement, rax
0x140002557  add     rsp, 30h
0x14000255b  pop     rbp
0x14000255c  retn
```
