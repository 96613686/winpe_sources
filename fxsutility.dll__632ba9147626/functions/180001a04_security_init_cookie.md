# __security_init_cookie

- ea: `0x180001a04`
- end: `0x180001ae1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800015d0`

## callees

- `0x180001a04`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180001a8e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001a8e`
- `KERNEL32!GetCurrentProcessId` at `0x180001a4b`
- `KERNEL32!GetCurrentProcessId` at `0x180001a4b`
- `KERNEL32!GetCurrentThreadId` at `0x180001a57`
- `KERNEL32!GetCurrentThreadId` at `0x180001a57`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a3d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001a3d`
- `KERNEL32!GetTickCount` at `0x180001a63`
- `KERNEL32!GetTickCount` at `0x180001a73`
- `KERNEL32!GetTickCount` at `0x180001a63`
- `KERNEL32!GetTickCount` at `0x180001a73`

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
0x180001a04  mov     [rsp-8+arg_18], rbx
0x180001a09  push    rbp
0x180001a0a  mov     rbp, rsp
0x180001a0d  sub     rsp, 20h
0x180001a11  xor     eax, eax
0x180001a13  mov     rbx, 2B992DDFA232h
0x180001a1d  mov     [rbp+arg_0], rax
0x180001a21  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a25  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a29  mov     rax, cs:__security_cookie
0x180001a30  cmp     rax, rbx
0x180001a33  jnz     loc_180001ACC
0x180001a39  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a3d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a43  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a47  mov     [rbp+arg_0], rax
0x180001a4b  call    cs:__imp_GetCurrentProcessId
0x180001a51  mov     eax, eax
0x180001a53  xor     [rbp+arg_0], rax
0x180001a57  call    cs:__imp_GetCurrentThreadId
0x180001a5d  mov     eax, eax
0x180001a5f  xor     [rbp+arg_0], rax
0x180001a63  call    cs:__imp_GetTickCount
0x180001a69  mov     eax, eax
0x180001a6b  shl     rax, 18h
0x180001a6f  xor     [rbp+arg_0], rax
0x180001a73  call    cs:__imp_GetTickCount
0x180001a79  mov     eax, eax
0x180001a7b  lea     rcx, [rbp+arg_0]
0x180001a7f  xor     rax, [rbp+arg_0]
0x180001a83  xor     rax, rcx
0x180001a86  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a8a  mov     [rbp+arg_0], rax
0x180001a8e  call    cs:__imp_QueryPerformanceCounter
0x180001a94  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a97  mov     rcx, 0FFFFFFFFFFFFh
0x180001aa1  shl     rax, 20h
0x180001aa5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001aa9  xor     rax, [rbp+arg_0]
0x180001aad  and     rax, rcx
0x180001ab0  mov     rcx, rax
0x180001ab3  cmp     rax, rbx
0x180001ab6  jnz     short loc_180001AC5
0x180001ab8  mov     rax, 2B992DDFA233h
0x180001ac2  mov     rcx, rax
0x180001ac5  mov     cs:__security_cookie, rcx
0x180001acc  mov     rbx, [rsp+20h+arg_18]
0x180001ad1  not     rax
0x180001ad4  mov     cs:__security_cookie_complement, rax
0x180001adb  add     rsp, 20h
0x180001adf  pop     rbp
0x180001ae0  retn
```
