# __security_init_cookie

- ea: `0x180025304`
- end: `0x1800253e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024850`

## callees

- `0x180025304`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180025357`
- `KERNEL32!GetCurrentThreadId` at `0x180025357`
- `KERNEL32!GetCurrentProcessId` at `0x18002534b`
- `KERNEL32!GetCurrentProcessId` at `0x18002534b`
- `KERNEL32!QueryPerformanceCounter` at `0x18002538e`
- `KERNEL32!QueryPerformanceCounter` at `0x18002538e`
- `KERNEL32!GetTickCount` at `0x180025363`
- `KERNEL32!GetTickCount` at `0x180025373`
- `KERNEL32!GetTickCount` at `0x180025363`
- `KERNEL32!GetTickCount` at `0x180025373`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002533d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18002533d`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x180025304  mov     [rsp-8+arg_18], rbx
0x180025309  push    rbp
0x18002530a  mov     rbp, rsp
0x18002530d  sub     rsp, 20h
0x180025311  xor     eax, eax
0x180025313  mov     rbx, 2B992DDFA232h
0x18002531d  mov     [rbp+arg_0], rax
0x180025321  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180025325  mov     qword ptr [rbp+PerformanceCount], rax
0x180025329  mov     rax, cs:__security_cookie
0x180025330  cmp     rax, rbx
0x180025333  jnz     loc_1800253CC
0x180025339  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002533d  call    cs:__imp_GetSystemTimeAsFileTime
0x180025343  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180025347  mov     [rbp+arg_0], rax
0x18002534b  call    cs:__imp_GetCurrentProcessId
0x180025351  mov     eax, eax
0x180025353  xor     [rbp+arg_0], rax
0x180025357  call    cs:__imp_GetCurrentThreadId
0x18002535d  mov     eax, eax
0x18002535f  xor     [rbp+arg_0], rax
0x180025363  call    cs:__imp_GetTickCount
0x180025369  mov     eax, eax
0x18002536b  shl     rax, 18h
0x18002536f  xor     [rbp+arg_0], rax
0x180025373  call    cs:__imp_GetTickCount
0x180025379  mov     eax, eax
0x18002537b  lea     rcx, [rbp+arg_0]
0x18002537f  xor     rax, [rbp+arg_0]
0x180025383  xor     rax, rcx
0x180025386  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002538a  mov     [rbp+arg_0], rax
0x18002538e  call    cs:__imp_QueryPerformanceCounter
0x180025394  mov     eax, dword ptr [rbp+PerformanceCount]
0x180025397  mov     rcx, 0FFFFFFFFFFFFh
0x1800253a1  shl     rax, 20h
0x1800253a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800253a9  xor     rax, [rbp+arg_0]
0x1800253ad  and     rax, rcx
0x1800253b0  mov     rcx, rax
0x1800253b3  cmp     rax, rbx
0x1800253b6  jnz     short loc_1800253C5
0x1800253b8  mov     rax, 2B992DDFA233h
0x1800253c2  mov     rcx, rax
0x1800253c5  mov     cs:__security_cookie, rcx
0x1800253cc  mov     rbx, [rsp+20h+arg_18]
0x1800253d1  not     rax
0x1800253d4  mov     cs:__security_cookie_complement, rax
0x1800253db  add     rsp, 20h
0x1800253df  pop     rbp
0x1800253e0  retn
```
