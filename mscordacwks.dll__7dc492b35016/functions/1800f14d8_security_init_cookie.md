# __security_init_cookie

- ea: `0x1800f14d8`
- end: `0x1800f1584`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f0cd0`

## callees

- `0x1800f14d8`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800f1512`
- `KERNEL32!GetCurrentThreadId` at `0x1800f1512`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800f1504`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800f1504`
- `KERNEL32!QueryPerformanceCounter` at `0x1800f152e`
- `KERNEL32!QueryPerformanceCounter` at `0x1800f152e`
- `KERNEL32!GetCurrentProcessId` at `0x1800f151e`
- `KERNEL32!GetCurrentProcessId` at `0x1800f151e`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x1800f14d8  mov     [rsp-8+arg_18], rbx
0x1800f14dd  push    rbp
0x1800f14de  mov     rbp, rsp
0x1800f14e1  sub     rsp, 20h
0x1800f14e5  mov     rax, cs:__security_cookie
0x1800f14ec  mov     rbx, 2B992DDFA232h
0x1800f14f6  cmp     rax, rbx
0x1800f14f9  jnz     short loc_1800F156F
0x1800f14fb  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800f1500  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800f1504  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f150a  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800f150e  mov     [rbp+arg_0], rax
0x1800f1512  call    cs:__imp_GetCurrentThreadId
0x1800f1518  mov     eax, eax
0x1800f151a  xor     [rbp+arg_0], rax
0x1800f151e  call    cs:__imp_GetCurrentProcessId
0x1800f1524  mov     eax, eax
0x1800f1526  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800f152a  xor     [rbp+arg_0], rax
0x1800f152e  call    cs:__imp_QueryPerformanceCounter
0x1800f1534  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800f1537  lea     rcx, [rbp+arg_0]
0x1800f153b  shl     rax, 20h
0x1800f153f  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800f1543  xor     rax, [rbp+arg_0]
0x1800f1547  xor     rax, rcx
0x1800f154a  mov     rcx, 0FFFFFFFFFFFFh
0x1800f1554  and     rax, rcx
0x1800f1557  mov     rcx, 2B992DDFA233h
0x1800f1561  cmp     rax, rbx
0x1800f1564  cmovz   rax, rcx
0x1800f1568  mov     cs:__security_cookie, rax
0x1800f156f  mov     rbx, [rsp+20h+arg_18]
0x1800f1574  not     rax
0x1800f1577  mov     cs:__security_cookie_complement, rax
0x1800f157e  add     rsp, 20h
0x1800f1582  pop     rbp
0x1800f1583  retn
```
