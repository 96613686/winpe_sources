# __security_init_cookie

- ea: `0x180002044`
- end: `0x180002121`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001690`

## callees

- `0x180002044`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x18000208b`
- `KERNEL32!GetCurrentProcessId` at `0x18000208b`
- `KERNEL32!QueryPerformanceCounter` at `0x1800020ce`
- `KERNEL32!QueryPerformanceCounter` at `0x1800020ce`
- `KERNEL32!GetCurrentThreadId` at `0x180002097`
- `KERNEL32!GetCurrentThreadId` at `0x180002097`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000207d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000207d`
- `KERNEL32!GetTickCount` at `0x1800020a3`
- `KERNEL32!GetTickCount` at `0x1800020b3`
- `KERNEL32!GetTickCount` at `0x1800020a3`
- `KERNEL32!GetTickCount` at `0x1800020b3`

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
0x180002044  mov     [rsp-8+arg_18], rbx
0x180002049  push    rbp
0x18000204a  mov     rbp, rsp
0x18000204d  sub     rsp, 20h
0x180002051  xor     eax, eax
0x180002053  mov     rbx, 2B992DDFA232h
0x18000205d  mov     [rbp+arg_0], rax
0x180002061  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002065  mov     qword ptr [rbp+PerformanceCount], rax
0x180002069  mov     rax, cs:__security_cookie
0x180002070  cmp     rax, rbx
0x180002073  jnz     loc_18000210C
0x180002079  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000207d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002083  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002087  mov     [rbp+arg_0], rax
0x18000208b  call    cs:__imp_GetCurrentProcessId
0x180002091  mov     eax, eax
0x180002093  xor     [rbp+arg_0], rax
0x180002097  call    cs:__imp_GetCurrentThreadId
0x18000209d  mov     eax, eax
0x18000209f  xor     [rbp+arg_0], rax
0x1800020a3  call    cs:__imp_GetTickCount
0x1800020a9  mov     eax, eax
0x1800020ab  shl     rax, 18h
0x1800020af  xor     [rbp+arg_0], rax
0x1800020b3  call    cs:__imp_GetTickCount
0x1800020b9  mov     eax, eax
0x1800020bb  lea     rcx, [rbp+arg_0]
0x1800020bf  xor     rax, [rbp+arg_0]
0x1800020c3  xor     rax, rcx
0x1800020c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800020ca  mov     [rbp+arg_0], rax
0x1800020ce  call    cs:__imp_QueryPerformanceCounter
0x1800020d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800020d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800020e1  shl     rax, 20h
0x1800020e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800020e9  xor     rax, [rbp+arg_0]
0x1800020ed  and     rax, rcx
0x1800020f0  mov     rcx, rax
0x1800020f3  cmp     rax, rbx
0x1800020f6  jnz     short loc_180002105
0x1800020f8  mov     rax, 2B992DDFA233h
0x180002102  mov     rcx, rax
0x180002105  mov     cs:__security_cookie, rcx
0x18000210c  mov     rbx, [rsp+20h+arg_18]
0x180002111  not     rax
0x180002114  mov     cs:__security_cookie_complement, rax
0x18000211b  add     rsp, 20h
0x18000211f  pop     rbp
0x180002120  retn
```
