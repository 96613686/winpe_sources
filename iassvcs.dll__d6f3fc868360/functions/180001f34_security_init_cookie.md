# __security_init_cookie

- ea: `0x180001f34`
- end: `0x180002011`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001590`

## callees

- `0x180001f34`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180001f87`
- `KERNEL32!GetCurrentThreadId` at `0x180001f87`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f6d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001f6d`
- `KERNEL32!GetTickCount` at `0x180001f93`
- `KERNEL32!GetTickCount` at `0x180001fa3`
- `KERNEL32!GetTickCount` at `0x180001f93`
- `KERNEL32!GetTickCount` at `0x180001fa3`
- `KERNEL32!GetCurrentProcessId` at `0x180001f7b`
- `KERNEL32!GetCurrentProcessId` at `0x180001f7b`
- `KERNEL32!QueryPerformanceCounter` at `0x180001fbe`
- `KERNEL32!QueryPerformanceCounter` at `0x180001fbe`

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
0x180001f34  mov     [rsp-8+arg_18], rbx
0x180001f39  push    rbp
0x180001f3a  mov     rbp, rsp
0x180001f3d  sub     rsp, 20h
0x180001f41  xor     eax, eax
0x180001f43  mov     rbx, 2B992DDFA232h
0x180001f4d  mov     [rbp+arg_0], rax
0x180001f51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001f55  mov     qword ptr [rbp+PerformanceCount], rax
0x180001f59  mov     rax, cs:__security_cookie
0x180001f60  cmp     rax, rbx
0x180001f63  jnz     loc_180001FFC
0x180001f69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001f6d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001f73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001f77  mov     [rbp+arg_0], rax
0x180001f7b  call    cs:__imp_GetCurrentProcessId
0x180001f81  mov     eax, eax
0x180001f83  xor     [rbp+arg_0], rax
0x180001f87  call    cs:__imp_GetCurrentThreadId
0x180001f8d  mov     eax, eax
0x180001f8f  xor     [rbp+arg_0], rax
0x180001f93  call    cs:__imp_GetTickCount
0x180001f99  mov     eax, eax
0x180001f9b  shl     rax, 18h
0x180001f9f  xor     [rbp+arg_0], rax
0x180001fa3  call    cs:__imp_GetTickCount
0x180001fa9  mov     eax, eax
0x180001fab  lea     rcx, [rbp+arg_0]
0x180001faf  xor     rax, [rbp+arg_0]
0x180001fb3  xor     rax, rcx
0x180001fb6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001fba  mov     [rbp+arg_0], rax
0x180001fbe  call    cs:__imp_QueryPerformanceCounter
0x180001fc4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001fc7  mov     rcx, 0FFFFFFFFFFFFh
0x180001fd1  shl     rax, 20h
0x180001fd5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001fd9  xor     rax, [rbp+arg_0]
0x180001fdd  and     rax, rcx
0x180001fe0  mov     rcx, rax
0x180001fe3  cmp     rax, rbx
0x180001fe6  jnz     short loc_180001FF5
0x180001fe8  mov     rax, 2B992DDFA233h
0x180001ff2  mov     rcx, rax
0x180001ff5  mov     cs:__security_cookie, rcx
0x180001ffc  mov     rbx, [rsp+20h+arg_18]
0x180002001  not     rax
0x180002004  mov     cs:__security_cookie_complement, rax
0x18000200b  add     rsp, 20h
0x18000200f  pop     rbp
0x180002010  retn
```
