# __security_init_cookie

- ea: `0x140002374`
- end: `0x140002451`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001a70`

## callees

- `0x140002374`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400023d3`
- `KERNEL32!GetTickCount` at `0x1400023e3`
- `KERNEL32!GetTickCount` at `0x1400023d3`
- `KERNEL32!GetTickCount` at `0x1400023e3`
- `KERNEL32!GetCurrentProcessId` at `0x1400023bb`
- `KERNEL32!GetCurrentProcessId` at `0x1400023bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400023c7`
- `KERNEL32!GetCurrentThreadId` at `0x1400023c7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400023ad`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400023ad`
- `KERNEL32!QueryPerformanceCounter` at `0x1400023fe`
- `KERNEL32!QueryPerformanceCounter` at `0x1400023fe`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x140002374  mov     [rsp-8+arg_18], rbx
0x140002379  push    rbp
0x14000237a  mov     rbp, rsp
0x14000237d  sub     rsp, 20h
0x140002381  xor     eax, eax
0x140002383  mov     rbx, 2B992DDFA232h
0x14000238d  mov     [rbp+arg_0], rax
0x140002391  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002395  mov     qword ptr [rbp+PerformanceCount], rax
0x140002399  mov     rax, cs:__security_cookie
0x1400023a0  cmp     rax, rbx
0x1400023a3  jnz     loc_14000243C
0x1400023a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400023ad  call    cs:__imp_GetSystemTimeAsFileTime
0x1400023b3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400023b7  mov     [rbp+arg_0], rax
0x1400023bb  call    cs:__imp_GetCurrentProcessId
0x1400023c1  mov     eax, eax
0x1400023c3  xor     [rbp+arg_0], rax
0x1400023c7  call    cs:__imp_GetCurrentThreadId
0x1400023cd  mov     eax, eax
0x1400023cf  xor     [rbp+arg_0], rax
0x1400023d3  call    cs:__imp_GetTickCount
0x1400023d9  mov     eax, eax
0x1400023db  shl     rax, 18h
0x1400023df  xor     [rbp+arg_0], rax
0x1400023e3  call    cs:__imp_GetTickCount
0x1400023e9  mov     eax, eax
0x1400023eb  lea     rcx, [rbp+arg_0]
0x1400023ef  xor     rax, [rbp+arg_0]
0x1400023f3  xor     rax, rcx
0x1400023f6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400023fa  mov     [rbp+arg_0], rax
0x1400023fe  call    cs:__imp_QueryPerformanceCounter
0x140002404  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002407  mov     rcx, 0FFFFFFFFFFFFh
0x140002411  shl     rax, 20h
0x140002415  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002419  xor     rax, [rbp+arg_0]
0x14000241d  and     rax, rcx
0x140002420  mov     rcx, rax
0x140002423  cmp     rax, rbx
0x140002426  jnz     short loc_140002435
0x140002428  mov     rax, 2B992DDFA233h
0x140002432  mov     rcx, rax
0x140002435  mov     cs:__security_cookie, rcx
0x14000243c  mov     rbx, [rsp+20h+arg_18]
0x140002441  not     rax
0x140002444  mov     cs:__security_cookie_complement, rax
0x14000244b  add     rsp, 20h
0x14000244f  pop     rbp
0x140002450  retn
```
