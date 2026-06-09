# __security_init_cookie

- ea: `0x1400015b4`
- end: `0x140001691`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001370`

## callees

- `0x1400015b4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140001613`
- `KERNEL32!GetTickCount` at `0x140001623`
- `KERNEL32!GetTickCount` at `0x140001613`
- `KERNEL32!GetTickCount` at `0x140001623`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400015ed`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1400015ed`
- `KERNEL32!GetCurrentThreadId` at `0x140001607`
- `KERNEL32!GetCurrentThreadId` at `0x140001607`
- `KERNEL32!GetCurrentProcessId` at `0x1400015fb`
- `KERNEL32!GetCurrentProcessId` at `0x1400015fb`
- `KERNEL32!QueryPerformanceCounter` at `0x14000163e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000163e`

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
0x1400015b4  mov     [rsp-8+arg_18], rbx
0x1400015b9  push    rbp
0x1400015ba  mov     rbp, rsp
0x1400015bd  sub     rsp, 20h
0x1400015c1  xor     eax, eax
0x1400015c3  mov     rbx, 2B992DDFA232h
0x1400015cd  mov     [rbp+arg_0], rax
0x1400015d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400015d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1400015d9  mov     rax, cs:__security_cookie
0x1400015e0  cmp     rax, rbx
0x1400015e3  jnz     loc_14000167C
0x1400015e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400015ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1400015f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400015f7  mov     [rbp+arg_0], rax
0x1400015fb  call    cs:__imp_GetCurrentProcessId
0x140001601  mov     eax, eax
0x140001603  xor     [rbp+arg_0], rax
0x140001607  call    cs:__imp_GetCurrentThreadId
0x14000160d  mov     eax, eax
0x14000160f  xor     [rbp+arg_0], rax
0x140001613  call    cs:__imp_GetTickCount
0x140001619  mov     eax, eax
0x14000161b  shl     rax, 18h
0x14000161f  xor     [rbp+arg_0], rax
0x140001623  call    cs:__imp_GetTickCount
0x140001629  mov     eax, eax
0x14000162b  lea     rcx, [rbp+arg_0]
0x14000162f  xor     rax, [rbp+arg_0]
0x140001633  xor     rax, rcx
0x140001636  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000163a  mov     [rbp+arg_0], rax
0x14000163e  call    cs:__imp_QueryPerformanceCounter
0x140001644  mov     eax, dword ptr [rbp+PerformanceCount]
0x140001647  mov     rcx, 0FFFFFFFFFFFFh
0x140001651  shl     rax, 20h
0x140001655  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001659  xor     rax, [rbp+arg_0]
0x14000165d  and     rax, rcx
0x140001660  mov     rcx, rax
0x140001663  cmp     rax, rbx
0x140001666  jnz     short loc_140001675
0x140001668  mov     rax, 2B992DDFA233h
0x140001672  mov     rcx, rax
0x140001675  mov     cs:__security_cookie, rcx
0x14000167c  mov     rbx, [rsp+20h+arg_18]
0x140001681  not     rax
0x140001684  mov     cs:__security_cookie_complement, rax
0x14000168b  add     rsp, 20h
0x14000168f  pop     rbp
0x140001690  retn
```
