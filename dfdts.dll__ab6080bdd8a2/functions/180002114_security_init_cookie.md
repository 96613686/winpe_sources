# __security_init_cookie

- ea: `0x180002114`
- end: `0x1800021f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001c30`

## callees

- `0x180002114`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002173`
- `KERNEL32!GetTickCount` at `0x180002183`
- `KERNEL32!GetTickCount` at `0x180002173`
- `KERNEL32!GetTickCount` at `0x180002183`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000214d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000214d`
- `KERNEL32!GetCurrentThreadId` at `0x180002167`
- `KERNEL32!GetCurrentThreadId` at `0x180002167`
- `KERNEL32!GetCurrentProcessId` at `0x18000215b`
- `KERNEL32!GetCurrentProcessId` at `0x18000215b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000219e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000219e`

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
0x180002114  mov     [rsp-8+arg_18], rbx
0x180002119  push    rbp
0x18000211a  mov     rbp, rsp
0x18000211d  sub     rsp, 20h
0x180002121  xor     eax, eax
0x180002123  mov     rbx, 2B992DDFA232h
0x18000212d  mov     [rbp+arg_0], rax
0x180002131  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002135  mov     qword ptr [rbp+PerformanceCount], rax
0x180002139  mov     rax, cs:__security_cookie
0x180002140  cmp     rax, rbx
0x180002143  jnz     loc_1800021DC
0x180002149  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000214d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002153  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002157  mov     [rbp+arg_0], rax
0x18000215b  call    cs:__imp_GetCurrentProcessId
0x180002161  mov     eax, eax
0x180002163  xor     [rbp+arg_0], rax
0x180002167  call    cs:__imp_GetCurrentThreadId
0x18000216d  mov     eax, eax
0x18000216f  xor     [rbp+arg_0], rax
0x180002173  call    cs:__imp_GetTickCount
0x180002179  mov     eax, eax
0x18000217b  shl     rax, 18h
0x18000217f  xor     [rbp+arg_0], rax
0x180002183  call    cs:__imp_GetTickCount
0x180002189  mov     eax, eax
0x18000218b  lea     rcx, [rbp+arg_0]
0x18000218f  xor     rax, [rbp+arg_0]
0x180002193  xor     rax, rcx
0x180002196  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000219a  mov     [rbp+arg_0], rax
0x18000219e  call    cs:__imp_QueryPerformanceCounter
0x1800021a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800021a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800021b1  shl     rax, 20h
0x1800021b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800021b9  xor     rax, [rbp+arg_0]
0x1800021bd  and     rax, rcx
0x1800021c0  mov     rcx, rax
0x1800021c3  cmp     rax, rbx
0x1800021c6  jnz     short loc_1800021D5
0x1800021c8  mov     rax, 2B992DDFA233h
0x1800021d2  mov     rcx, rax
0x1800021d5  mov     cs:__security_cookie, rcx
0x1800021dc  mov     rbx, [rsp+20h+arg_18]
0x1800021e1  not     rax
0x1800021e4  mov     cs:__security_cookie_complement, rax
0x1800021eb  add     rsp, 20h
0x1800021ef  pop     rbp
0x1800021f0  retn
```
