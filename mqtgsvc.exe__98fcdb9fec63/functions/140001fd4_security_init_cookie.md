# __security_init_cookie

- ea: `0x140001fd4`
- end: `0x1400020b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001870`

## callees

- `0x140001fd4`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x140002033`
- `KERNEL32!GetTickCount` at `0x140002043`
- `KERNEL32!GetTickCount` at `0x140002033`
- `KERNEL32!GetTickCount` at `0x140002043`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000200d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x14000200d`
- `KERNEL32!GetCurrentThreadId` at `0x140002027`
- `KERNEL32!GetCurrentThreadId` at `0x140002027`
- `KERNEL32!QueryPerformanceCounter` at `0x14000205e`
- `KERNEL32!QueryPerformanceCounter` at `0x14000205e`
- `KERNEL32!GetCurrentProcessId` at `0x14000201b`
- `KERNEL32!GetCurrentProcessId` at `0x14000201b`

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
0x140001fd4  mov     [rsp-8+arg_18], rbx
0x140001fd9  push    rbp
0x140001fda  mov     rbp, rsp
0x140001fdd  sub     rsp, 20h
0x140001fe1  xor     eax, eax
0x140001fe3  mov     rbx, 2B992DDFA232h
0x140001fed  mov     [rbp+arg_0], rax
0x140001ff1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001ff5  mov     qword ptr [rbp+PerformanceCount], rax
0x140001ff9  mov     rax, cs:__security_cookie
0x140002000  cmp     rax, rbx
0x140002003  jnz     loc_14000209C
0x140002009  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000200d  call    cs:__imp_GetSystemTimeAsFileTime
0x140002013  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002017  mov     [rbp+arg_0], rax
0x14000201b  call    cs:__imp_GetCurrentProcessId
0x140002021  mov     eax, eax
0x140002023  xor     [rbp+arg_0], rax
0x140002027  call    cs:__imp_GetCurrentThreadId
0x14000202d  mov     eax, eax
0x14000202f  xor     [rbp+arg_0], rax
0x140002033  call    cs:__imp_GetTickCount
0x140002039  mov     eax, eax
0x14000203b  shl     rax, 18h
0x14000203f  xor     [rbp+arg_0], rax
0x140002043  call    cs:__imp_GetTickCount
0x140002049  mov     eax, eax
0x14000204b  lea     rcx, [rbp+arg_0]
0x14000204f  xor     rax, [rbp+arg_0]
0x140002053  xor     rax, rcx
0x140002056  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000205a  mov     [rbp+arg_0], rax
0x14000205e  call    cs:__imp_QueryPerformanceCounter
0x140002064  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002067  mov     rcx, 0FFFFFFFFFFFFh
0x140002071  shl     rax, 20h
0x140002075  xor     rax, qword ptr [rbp+PerformanceCount]
0x140002079  xor     rax, [rbp+arg_0]
0x14000207d  and     rax, rcx
0x140002080  mov     rcx, rax
0x140002083  cmp     rax, rbx
0x140002086  jnz     short loc_140002095
0x140002088  mov     rax, 2B992DDFA233h
0x140002092  mov     rcx, rax
0x140002095  mov     cs:__security_cookie, rcx
0x14000209c  mov     rbx, [rsp+20h+arg_18]
0x1400020a1  not     rax
0x1400020a4  mov     cs:__security_cookie_complement, rax
0x1400020ab  add     rsp, 20h
0x1400020af  pop     rbp
0x1400020b0  retn
```
