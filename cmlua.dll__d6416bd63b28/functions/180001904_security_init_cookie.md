# __security_init_cookie

- ea: `0x180001904`
- end: `0x1800019e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001280`

## callees

- `0x180001904`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000198e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000198e`
- `KERNEL32!GetCurrentProcessId` at `0x18000194b`
- `KERNEL32!GetCurrentProcessId` at `0x18000194b`
- `KERNEL32!GetCurrentThreadId` at `0x180001957`
- `KERNEL32!GetCurrentThreadId` at `0x180001957`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000193d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000193d`
- `KERNEL32!GetTickCount` at `0x180001963`
- `KERNEL32!GetTickCount` at `0x180001973`
- `KERNEL32!GetTickCount` at `0x180001963`
- `KERNEL32!GetTickCount` at `0x180001973`

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
0x180001904  mov     [rsp-8+arg_18], rbx
0x180001909  push    rbp
0x18000190a  mov     rbp, rsp
0x18000190d  sub     rsp, 20h
0x180001911  xor     eax, eax
0x180001913  mov     rbx, 2B992DDFA232h
0x18000191d  mov     [rbp+arg_0], rax
0x180001921  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001925  mov     qword ptr [rbp+PerformanceCount], rax
0x180001929  mov     rax, cs:__security_cookie
0x180001930  cmp     rax, rbx
0x180001933  jnz     loc_1800019CC
0x180001939  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000193d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001943  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001947  mov     [rbp+arg_0], rax
0x18000194b  call    cs:__imp_GetCurrentProcessId
0x180001951  mov     eax, eax
0x180001953  xor     [rbp+arg_0], rax
0x180001957  call    cs:__imp_GetCurrentThreadId
0x18000195d  mov     eax, eax
0x18000195f  xor     [rbp+arg_0], rax
0x180001963  call    cs:__imp_GetTickCount
0x180001969  mov     eax, eax
0x18000196b  shl     rax, 18h
0x18000196f  xor     [rbp+arg_0], rax
0x180001973  call    cs:__imp_GetTickCount
0x180001979  mov     eax, eax
0x18000197b  lea     rcx, [rbp+arg_0]
0x18000197f  xor     rax, [rbp+arg_0]
0x180001983  xor     rax, rcx
0x180001986  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000198a  mov     [rbp+arg_0], rax
0x18000198e  call    cs:__imp_QueryPerformanceCounter
0x180001994  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001997  mov     rcx, 0FFFFFFFFFFFFh
0x1800019a1  shl     rax, 20h
0x1800019a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800019a9  xor     rax, [rbp+arg_0]
0x1800019ad  and     rax, rcx
0x1800019b0  mov     rcx, rax
0x1800019b3  cmp     rax, rbx
0x1800019b6  jnz     short loc_1800019C5
0x1800019b8  mov     rax, 2B992DDFA233h
0x1800019c2  mov     rcx, rax
0x1800019c5  mov     cs:__security_cookie, rcx
0x1800019cc  mov     rbx, [rsp+20h+arg_18]
0x1800019d1  not     rax
0x1800019d4  mov     cs:__security_cookie_complement, rax
0x1800019db  add     rsp, 20h
0x1800019df  pop     rbp
0x1800019e0  retn
```
