# __security_init_cookie

- ea: `0x140001584`
- end: `0x140001661`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001340`

## callees

- `0x140001584`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x1400015e3`
- `KERNEL32!GetTickCount` at `0x1400015f3`
- `KERNEL32!GetTickCount` at `0x1400015e3`
- `KERNEL32!GetTickCount` at `0x1400015f3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400015bd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400015bd`
- `KERNEL32!GetCurrentThreadId` at `0x1400015d7`
- `KERNEL32!GetCurrentThreadId` at `0x1400015d7`
- `KERNEL32!GetCurrentProcessId` at `0x1400015cb`
- `KERNEL32!GetCurrentProcessId` at `0x1400015cb`
- `KERNEL32!QueryPerformanceCounter` at `0x14000160e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000160e`

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
0x140001584  mov     [rsp-8+arg_18], rbx
0x140001589  push    rbp
0x14000158a  mov     rbp, rsp
0x14000158d  sub     rsp, 20h
0x140001591  xor     eax, eax
0x140001593  mov     rbx, 2B992DDFA232h
0x14000159d  mov     [rbp+arg_0], rax
0x1400015a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400015a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400015a9  mov     rax, cs:__security_cookie
0x1400015b0  cmp     rax, rbx
0x1400015b3  jnz     loc_14000164C
0x1400015b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400015bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1400015c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400015c7  mov     [rbp+arg_0], rax
0x1400015cb  call    cs:__imp_GetCurrentProcessId
0x1400015d1  mov     eax, eax
0x1400015d3  xor     [rbp+arg_0], rax
0x1400015d7  call    cs:__imp_GetCurrentThreadId
0x1400015dd  mov     eax, eax
0x1400015df  xor     [rbp+arg_0], rax
0x1400015e3  call    cs:__imp_GetTickCount
0x1400015e9  mov     eax, eax
0x1400015eb  shl     rax, 18h
0x1400015ef  xor     [rbp+arg_0], rax
0x1400015f3  call    cs:__imp_GetTickCount
0x1400015f9  mov     eax, eax
0x1400015fb  lea     rcx, [rbp+arg_0]
0x1400015ff  xor     rax, [rbp+arg_0]
0x140001603  xor     rax, rcx
0x140001606  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000160a  mov     [rbp+arg_0], rax
0x14000160e  call    cs:__imp_QueryPerformanceCounter
0x140001614  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001617  mov     rcx, 0FFFFFFFFFFFFh
0x140001621  shl     rax, 20h
0x140001625  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001629  xor     rax, [rbp+arg_0]
0x14000162d  and     rax, rcx
0x140001630  mov     rcx, rax
0x140001633  cmp     rax, rbx
0x140001636  jnz     short loc_140001645
0x140001638  mov     rax, 2B992DDFA233h
0x140001642  mov     rcx, rax
0x140001645  mov     cs:__security_cookie, rcx
0x14000164c  mov     rbx, [rsp+20h+arg_18]
0x140001651  not     rax
0x140001654  mov     cs:__security_cookie_complement, rax
0x14000165b  add     rsp, 20h
0x14000165f  pop     rbp
0x140001660  retn
```
