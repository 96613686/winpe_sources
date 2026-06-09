# __security_init_cookie

- ea: `0x180001b34`
- end: `0x180001c0d`
- name: `__security_init_cookie`
- size: `217`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013e0`

## callees

- `0x180001b34`

## import_xrefs

- `KERNEL32!GetTickCount` at `0x180001b8f`
- `KERNEL32!GetTickCount` at `0x180001b9f`
- `KERNEL32!GetTickCount` at `0x180001b8f`
- `KERNEL32!GetTickCount` at `0x180001b9f`
- `KERNEL32!GetCurrentThreadId` at `0x180001b83`
- `KERNEL32!GetCurrentThreadId` at `0x180001b83`
- `KERNEL32!QueryPerformanceCounter` at `0x180001bba`
- `KERNEL32!QueryPerformanceCounter` at `0x180001bba`
- `KERNEL32!GetCurrentProcessId` at `0x180001b77`
- `KERNEL32!GetCurrentProcessId` at `0x180001b77`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001b69`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001b69`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

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
0x180001b34  mov     [rsp-8+arg_18], rbx
0x180001b39  push    rbp
0x180001b3a  mov     rbp, rsp
0x180001b3d  sub     rsp, 20h
0x180001b41  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180001b46  mov     rbx, 2B992DDFA232h
0x180001b50  and     qword ptr [rbp+PerformanceCount], 0
0x180001b55  mov     rax, cs:__security_cookie
0x180001b5c  cmp     rax, rbx
0x180001b5f  jnz     loc_180001BF8
0x180001b65  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b69  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b6f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001b73  mov     [rbp+arg_0], rax
0x180001b77  call    cs:__imp_GetCurrentProcessId
0x180001b7d  mov     eax, eax
0x180001b7f  xor     [rbp+arg_0], rax
0x180001b83  call    cs:__imp_GetCurrentThreadId
0x180001b89  mov     eax, eax
0x180001b8b  xor     [rbp+arg_0], rax
0x180001b8f  call    cs:__imp_GetTickCount
0x180001b95  mov     eax, eax
0x180001b97  shl     rax, 18h
0x180001b9b  xor     [rbp+arg_0], rax
0x180001b9f  call    cs:__imp_GetTickCount
0x180001ba5  mov     eax, eax
0x180001ba7  lea     rcx, [rbp+arg_0]
0x180001bab  xor     rax, [rbp+arg_0]
0x180001baf  xor     rax, rcx
0x180001bb2  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001bb6  mov     [rbp+arg_0], rax
0x180001bba  call    cs:__imp_QueryPerformanceCounter
0x180001bc0  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001bc3  mov     rcx, 0FFFFFFFFFFFFh
0x180001bcd  shl     rax, 20h
0x180001bd1  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001bd5  xor     rax, [rbp+arg_0]
0x180001bd9  and     rax, rcx
0x180001bdc  mov     rcx, rax
0x180001bdf  cmp     rax, rbx
0x180001be2  jnz     short loc_180001BF1
0x180001be4  mov     rax, 2B992DDFA233h
0x180001bee  mov     rcx, rax
0x180001bf1  mov     cs:__security_cookie, rcx
0x180001bf8  mov     rbx, [rsp+20h+arg_18]
0x180001bfd  not     rax
0x180001c00  mov     cs:__security_cookie_complement, rax
0x180001c07  add     rsp, 20h
0x180001c0b  pop     rbp
0x180001c0c  retn
```
