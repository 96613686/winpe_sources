# __security_init_cookie

- ea: `0x180001b24`
- end: `0x180001c03`
- name: `__security_init_cookie`
- size: `223`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013e0`

## callees

- `0x180001b24`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001b85`
- `KERNEL32!GetTickCount` at `0x180001b95`
- `KERNEL32!GetTickCount` at `0x180001b85`
- `KERNEL32!GetTickCount` at `0x180001b95`
- `KERNEL32!QueryPerformanceCounter` at `0x180001bb0`
- `KERNEL32!QueryPerformanceCounter` at `0x180001bb0`
- `KERNEL32!GetCurrentProcessId` at `0x180001b6d`
- `KERNEL32!GetCurrentProcessId` at `0x180001b6d`
- `KERNEL32!GetCurrentThreadId` at `0x180001b79`
- `KERNEL32!GetCurrentThreadId` at `0x180001b79`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001b5f`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001b5f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
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
0x180001b24  mov     [rsp-8+arg_18], rbx
0x180001b29  push    rbp
0x180001b2a  mov     rbp, rsp
0x180001b2d  sub     rsp, 20h
0x180001b31  mov     rax, cs:__security_cookie
0x180001b38  mov     rbx, 2B992DDFA232h
0x180001b42  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001b4a  mov     qword ptr [rbp+PerformanceCount], 0
0x180001b52  cmp     rax, rbx
0x180001b55  jnz     loc_180001BEE
0x180001b5b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b5f  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b65  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b69  mov     [rbp+arg_0], rax
0x180001b6d  call    cs:__imp_GetCurrentProcessId
0x180001b73  mov     eax, eax
0x180001b75  xor     [rbp+arg_0], rax
0x180001b79  call    cs:__imp_GetCurrentThreadId
0x180001b7f  mov     eax, eax
0x180001b81  xor     [rbp+arg_0], rax
0x180001b85  call    cs:__imp_GetTickCount
0x180001b8b  mov     eax, eax
0x180001b8d  shl     rax, 18h
0x180001b91  xor     [rbp+arg_0], rax
0x180001b95  call    cs:__imp_GetTickCount
0x180001b9b  mov     eax, eax
0x180001b9d  lea     rcx, [rbp+arg_0]
0x180001ba1  xor     rax, [rbp+arg_0]
0x180001ba5  xor     rax, rcx
0x180001ba8  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001bac  mov     [rbp+arg_0], rax
0x180001bb0  call    cs:__imp_QueryPerformanceCounter
0x180001bb6  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001bb9  mov     rcx, 0FFFFFFFFFFFFh
0x180001bc3  shl     rax, 20h
0x180001bc7  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001bcb  xor     rax, [rbp+arg_0]
0x180001bcf  and     rax, rcx
0x180001bd2  mov     rcx, rax
0x180001bd5  cmp     rax, rbx
0x180001bd8  jnz     short loc_180001BE7
0x180001bda  mov     rax, 2B992DDFA233h
0x180001be4  mov     rcx, rax
0x180001be7  mov     cs:__security_cookie, rcx
0x180001bee  mov     rbx, [rsp+20h+arg_18]
0x180001bf3  not     rax
0x180001bf6  mov     cs:__security_cookie_complement, rax
0x180001bfd  add     rsp, 20h
0x180001c01  pop     rbp
0x180001c02  retn
```
