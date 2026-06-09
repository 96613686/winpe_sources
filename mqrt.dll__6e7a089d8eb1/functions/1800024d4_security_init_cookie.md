# __security_init_cookie

- ea: `0x1800024d4`
- end: `0x1800025b1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001bf0`

## callees

- `0x1800024d4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x18000255e`
- `KERNEL32!QueryPerformanceCounter` at `0x18000255e`
- `KERNEL32!GetTickCount` at `0x180002533`
- `KERNEL32!GetTickCount` at `0x180002543`
- `KERNEL32!GetTickCount` at `0x180002533`
- `KERNEL32!GetTickCount` at `0x180002543`
- `KERNEL32!GetCurrentThreadId` at `0x180002527`
- `KERNEL32!GetCurrentThreadId` at `0x180002527`
- `KERNEL32!GetCurrentProcessId` at `0x18000251b`
- `KERNEL32!GetCurrentProcessId` at `0x18000251b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000250d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000250d`

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
0x1800024d4  mov     [rsp-8+arg_18], rbx
0x1800024d9  push    rbp
0x1800024da  mov     rbp, rsp
0x1800024dd  sub     rsp, 20h
0x1800024e1  xor     eax, eax
0x1800024e3  mov     rbx, 2B992DDFA232h
0x1800024ed  mov     [rbp+arg_0], rax
0x1800024f1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800024f5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800024f9  mov     rax, cs:__security_cookie
0x180002500  cmp     rax, rbx
0x180002503  jnz     loc_18000259C
0x180002509  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000250d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002513  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002517  mov     [rbp+arg_0], rax
0x18000251b  call    cs:__imp_GetCurrentProcessId
0x180002521  mov     eax, eax
0x180002523  xor     [rbp+arg_0], rax
0x180002527  call    cs:__imp_GetCurrentThreadId
0x18000252d  mov     eax, eax
0x18000252f  xor     [rbp+arg_0], rax
0x180002533  call    cs:__imp_GetTickCount
0x180002539  mov     eax, eax
0x18000253b  shl     rax, 18h
0x18000253f  xor     [rbp+arg_0], rax
0x180002543  call    cs:__imp_GetTickCount
0x180002549  mov     eax, eax
0x18000254b  lea     rcx, [rbp+arg_0]
0x18000254f  xor     rax, [rbp+arg_0]
0x180002553  xor     rax, rcx
0x180002556  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000255a  mov     [rbp+arg_0], rax
0x18000255e  call    cs:__imp_QueryPerformanceCounter
0x180002564  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002567  mov     rcx, 0FFFFFFFFFFFFh
0x180002571  shl     rax, 20h
0x180002575  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002579  xor     rax, [rbp+arg_0]
0x18000257d  and     rax, rcx
0x180002580  mov     rcx, rax
0x180002583  cmp     rax, rbx
0x180002586  jnz     short loc_180002595
0x180002588  mov     rax, 2B992DDFA233h
0x180002592  mov     rcx, rax
0x180002595  mov     cs:__security_cookie, rcx
0x18000259c  mov     rbx, [rsp+20h+arg_18]
0x1800025a1  not     rax
0x1800025a4  mov     cs:__security_cookie_complement, rax
0x1800025ab  add     rsp, 20h
0x1800025af  pop     rbp
0x1800025b0  retn
```
