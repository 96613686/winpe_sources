# __security_init_cookie

- ea: `0x180002804`
- end: `0x1800028e1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001ec0`

## callees

- `0x180002804`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180002863`
- `KERNEL32!GetTickCount` at `0x180002873`
- `KERNEL32!GetTickCount` at `0x180002863`
- `KERNEL32!GetTickCount` at `0x180002873`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000283d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000283d`
- `KERNEL32!GetCurrentThreadId` at `0x180002857`
- `KERNEL32!GetCurrentThreadId` at `0x180002857`
- `KERNEL32!GetCurrentProcessId` at `0x18000284b`
- `KERNEL32!GetCurrentProcessId` at `0x18000284b`
- `KERNEL32!QueryPerformanceCounter` at `0x18000288e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000288e`

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
0x180002804  mov     [rsp-8+arg_18], rbx
0x180002809  push    rbp
0x18000280a  mov     rbp, rsp
0x18000280d  sub     rsp, 20h
0x180002811  xor     eax, eax
0x180002813  mov     rbx, 2B992DDFA232h
0x18000281d  mov     [rbp+arg_0], rax
0x180002821  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002825  mov     qword ptr [rbp+PerformanceCount], rax
0x180002829  mov     rax, cs:__security_cookie
0x180002830  cmp     rax, rbx
0x180002833  jnz     loc_1800028CC
0x180002839  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000283d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002843  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002847  mov     [rbp+arg_0], rax
0x18000284b  call    cs:__imp_GetCurrentProcessId
0x180002851  mov     eax, eax
0x180002853  xor     [rbp+arg_0], rax
0x180002857  call    cs:__imp_GetCurrentThreadId
0x18000285d  mov     eax, eax
0x18000285f  xor     [rbp+arg_0], rax
0x180002863  call    cs:__imp_GetTickCount
0x180002869  mov     eax, eax
0x18000286b  shl     rax, 18h
0x18000286f  xor     [rbp+arg_0], rax
0x180002873  call    cs:__imp_GetTickCount
0x180002879  mov     eax, eax
0x18000287b  lea     rcx, [rbp+arg_0]
0x18000287f  xor     rax, [rbp+arg_0]
0x180002883  xor     rax, rcx
0x180002886  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000288a  mov     [rbp+arg_0], rax
0x18000288e  call    cs:__imp_QueryPerformanceCounter
0x180002894  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002897  mov     rcx, 0FFFFFFFFFFFFh
0x1800028a1  shl     rax, 20h
0x1800028a5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800028a9  xor     rax, [rbp+arg_0]
0x1800028ad  and     rax, rcx
0x1800028b0  mov     rcx, rax
0x1800028b3  cmp     rax, rbx
0x1800028b6  jnz     short loc_1800028C5
0x1800028b8  mov     rax, 2B992DDFA233h
0x1800028c2  mov     rcx, rax
0x1800028c5  mov     cs:__security_cookie, rcx
0x1800028cc  mov     rbx, [rsp+20h+arg_18]
0x1800028d1  not     rax
0x1800028d4  mov     cs:__security_cookie_complement, rax
0x1800028db  add     rsp, 20h
0x1800028df  pop     rbp
0x1800028e0  retn
```
