# __security_init_cookie

- ea: `0x180001ba4`
- end: `0x180001c81`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001670`

## callees

- `0x180001ba4`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001c2e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001c2e`
- `KERNEL32!GetCurrentProcessId` at `0x180001beb`
- `KERNEL32!GetCurrentProcessId` at `0x180001beb`
- `KERNEL32!GetCurrentThreadId` at `0x180001bf7`
- `KERNEL32!GetCurrentThreadId` at `0x180001bf7`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001bdd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001bdd`
- `KERNEL32!GetTickCount` at `0x180001c03`
- `KERNEL32!GetTickCount` at `0x180001c13`
- `KERNEL32!GetTickCount` at `0x180001c03`
- `KERNEL32!GetTickCount` at `0x180001c13`

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
0x180001ba4  mov     [rsp-8+arg_18], rbx
0x180001ba9  push    rbp
0x180001baa  mov     rbp, rsp
0x180001bad  sub     rsp, 20h
0x180001bb1  xor     eax, eax
0x180001bb3  mov     rbx, 2B992DDFA232h
0x180001bbd  mov     [rbp+arg_0], rax
0x180001bc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001bc5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001bc9  mov     rax, cs:__security_cookie
0x180001bd0  cmp     rax, rbx
0x180001bd3  jnz     loc_180001C6C
0x180001bd9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001bdd  call    cs:__imp_GetSystemTimeAsFileTime
0x180001be3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001be7  mov     [rbp+arg_0], rax
0x180001beb  call    cs:__imp_GetCurrentProcessId
0x180001bf1  mov     eax, eax
0x180001bf3  xor     [rbp+arg_0], rax
0x180001bf7  call    cs:__imp_GetCurrentThreadId
0x180001bfd  mov     eax, eax
0x180001bff  xor     [rbp+arg_0], rax
0x180001c03  call    cs:__imp_GetTickCount
0x180001c09  mov     eax, eax
0x180001c0b  shl     rax, 18h
0x180001c0f  xor     [rbp+arg_0], rax
0x180001c13  call    cs:__imp_GetTickCount
0x180001c19  mov     eax, eax
0x180001c1b  lea     rcx, [rbp+arg_0]
0x180001c1f  xor     rax, [rbp+arg_0]
0x180001c23  xor     rax, rcx
0x180001c26  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c2a  mov     [rbp+arg_0], rax
0x180001c2e  call    cs:__imp_QueryPerformanceCounter
0x180001c34  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c37  mov     rcx, 0FFFFFFFFFFFFh
0x180001c41  shl     rax, 20h
0x180001c45  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c49  xor     rax, [rbp+arg_0]
0x180001c4d  and     rax, rcx
0x180001c50  mov     rcx, rax
0x180001c53  cmp     rax, rbx
0x180001c56  jnz     short loc_180001C65
0x180001c58  mov     rax, 2B992DDFA233h
0x180001c62  mov     rcx, rax
0x180001c65  mov     cs:__security_cookie, rcx
0x180001c6c  mov     rbx, [rsp+20h+arg_18]
0x180001c71  not     rax
0x180001c74  mov     cs:__security_cookie_complement, rax
0x180001c7b  add     rsp, 20h
0x180001c7f  pop     rbp
0x180001c80  retn
```
