# __security_init_cookie

- ea: `0x180001ee4`
- end: `0x180001fc1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001500`

## callees

- `0x180001ee4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001f6e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001f6e`
- `KERNEL32!GetCurrentProcessId` at `0x180001f2b`
- `KERNEL32!GetCurrentProcessId` at `0x180001f2b`
- `KERNEL32!GetCurrentThreadId` at `0x180001f37`
- `KERNEL32!GetCurrentThreadId` at `0x180001f37`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f1d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f1d`
- `KERNEL32!GetTickCount` at `0x180001f43`
- `KERNEL32!GetTickCount` at `0x180001f53`
- `KERNEL32!GetTickCount` at `0x180001f43`
- `KERNEL32!GetTickCount` at `0x180001f53`

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
0x180001ee4  mov     [rsp-8+arg_18], rbx
0x180001ee9  push    rbp
0x180001eea  mov     rbp, rsp
0x180001eed  sub     rsp, 20h
0x180001ef1  xor     eax, eax
0x180001ef3  mov     rbx, 2B992DDFA232h
0x180001efd  mov     [rbp+arg_0], rax
0x180001f01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f05  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f09  mov     rax, cs:__security_cookie
0x180001f10  cmp     rax, rbx
0x180001f13  jnz     loc_180001FAC
0x180001f19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f27  mov     [rbp+arg_0], rax
0x180001f2b  call    cs:__imp_GetCurrentProcessId
0x180001f31  mov     eax, eax
0x180001f33  xor     [rbp+arg_0], rax
0x180001f37  call    cs:__imp_GetCurrentThreadId
0x180001f3d  mov     eax, eax
0x180001f3f  xor     [rbp+arg_0], rax
0x180001f43  call    cs:__imp_GetTickCount
0x180001f49  mov     eax, eax
0x180001f4b  shl     rax, 18h
0x180001f4f  xor     [rbp+arg_0], rax
0x180001f53  call    cs:__imp_GetTickCount
0x180001f59  mov     eax, eax
0x180001f5b  lea     rcx, [rbp+arg_0]
0x180001f5f  xor     rax, [rbp+arg_0]
0x180001f63  xor     rax, rcx
0x180001f66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001f6a  mov     [rbp+arg_0], rax
0x180001f6e  call    cs:__imp_QueryPerformanceCounter
0x180001f74  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001f77  mov     rcx, 0FFFFFFFFFFFFh
0x180001f81  shl     rax, 20h
0x180001f85  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001f89  xor     rax, [rbp+arg_0]
0x180001f8d  and     rax, rcx
0x180001f90  mov     rcx, rax
0x180001f93  cmp     rax, rbx
0x180001f96  jnz     short loc_180001FA5
0x180001f98  mov     rax, 2B992DDFA233h
0x180001fa2  mov     rcx, rax
0x180001fa5  mov     cs:__security_cookie, rcx
0x180001fac  mov     rbx, [rsp+20h+arg_18]
0x180001fb1  not     rax
0x180001fb4  mov     cs:__security_cookie_complement, rax
0x180001fbb  add     rsp, 20h
0x180001fbf  pop     rbp
0x180001fc0  retn
```
