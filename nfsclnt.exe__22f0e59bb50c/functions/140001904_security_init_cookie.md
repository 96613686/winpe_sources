# __security_init_cookie

- ea: `0x140001904`
- end: `0x1400019e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400014c0`

## callees

- `0x140001904`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140001963`
- `KERNEL32!GetTickCount` at `0x140001973`
- `KERNEL32!GetTickCount` at `0x140001963`
- `KERNEL32!GetTickCount` at `0x140001973`
- `KERNEL32!QueryPerformanceCounter` at `0x14000198e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000198e`
- `KERNEL32!GetCurrentProcessId` at `0x14000194b`
- `KERNEL32!GetCurrentProcessId` at `0x14000194b`
- `KERNEL32!GetCurrentThreadId` at `0x140001957`
- `KERNEL32!GetCurrentThreadId` at `0x140001957`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000193d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000193d`

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
0x140001904  mov     [rsp-8+arg_18], rbx
0x140001909  push    rbp
0x14000190a  mov     rbp, rsp
0x14000190d  sub     rsp, 20h
0x140001911  xor     eax, eax
0x140001913  mov     rbx, 2B992DDFA232h
0x14000191d  mov     [rbp+arg_0], rax
0x140001921  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001925  mov     qword ptr [rbp+PerformanceCount], rax
0x140001929  mov     rax, cs:__security_cookie
0x140001930  cmp     rax, rbx
0x140001933  jnz     loc_1400019CC
0x140001939  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000193d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001943  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001947  mov     [rbp+arg_0], rax
0x14000194b  call    cs:__imp_GetCurrentProcessId
0x140001951  mov     eax, eax
0x140001953  xor     [rbp+arg_0], rax
0x140001957  call    cs:__imp_GetCurrentThreadId
0x14000195d  mov     eax, eax
0x14000195f  xor     [rbp+arg_0], rax
0x140001963  call    cs:__imp_GetTickCount
0x140001969  mov     eax, eax
0x14000196b  shl     rax, 18h
0x14000196f  xor     [rbp+arg_0], rax
0x140001973  call    cs:__imp_GetTickCount
0x140001979  mov     eax, eax
0x14000197b  lea     rcx, [rbp+arg_0]
0x14000197f  xor     rax, [rbp+arg_0]
0x140001983  xor     rax, rcx
0x140001986  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000198a  mov     [rbp+arg_0], rax
0x14000198e  call    cs:__imp_QueryPerformanceCounter
0x140001994  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001997  mov     rcx, 0FFFFFFFFFFFFh
0x1400019a1  shl     rax, 20h
0x1400019a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400019a9  xor     rax, [rbp+arg_0]
0x1400019ad  and     rax, rcx
0x1400019b0  mov     rcx, rax
0x1400019b3  cmp     rax, rbx
0x1400019b6  jnz     short loc_1400019C5
0x1400019b8  mov     rax, 2B992DDFA233h
0x1400019c2  mov     rcx, rax
0x1400019c5  mov     cs:__security_cookie, rcx
0x1400019cc  mov     rbx, [rsp+20h+arg_18]
0x1400019d1  not     rax
0x1400019d4  mov     cs:__security_cookie_complement, rax
0x1400019db  add     rsp, 20h
0x1400019df  pop     rbp
0x1400019e0  retn
```
