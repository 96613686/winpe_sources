# __security_init_cookie

- ea: `0x180001a84`
- end: `0x180001b61`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800014d0`

## callees

- `0x180001a84`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001abd`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001abd`
- `KERNEL32!GetCurrentProcessId` at `0x180001acb`
- `KERNEL32!GetCurrentProcessId` at `0x180001acb`
- `KERNEL32!GetCurrentThreadId` at `0x180001ad7`
- `KERNEL32!GetCurrentThreadId` at `0x180001ad7`
- `KERNEL32!GetTickCount` at `0x180001ae3`
- `KERNEL32!GetTickCount` at `0x180001af3`
- `KERNEL32!GetTickCount` at `0x180001ae3`
- `KERNEL32!GetTickCount` at `0x180001af3`
- `KERNEL32!QueryPerformanceCounter` at `0x180001b0e`
- `KERNEL32!QueryPerformanceCounter` at `0x180001b0e`

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
0x180001a84  mov     [rsp-8+arg_18], rbx
0x180001a89  push    rbp
0x180001a8a  mov     rbp, rsp
0x180001a8d  sub     rsp, 20h
0x180001a91  xor     eax, eax
0x180001a93  mov     rbx, 2B992DDFA232h
0x180001a9d  mov     [rbp+arg_0], rax
0x180001aa1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001aa5  mov     qword ptr [rbp+PerformanceCount], rax
0x180001aa9  mov     rax, cs:__security_cookie
0x180001ab0  cmp     rax, rbx
0x180001ab3  jnz     loc_180001B4C
0x180001ab9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001abd  call    cs:__imp_GetSystemTimeAsFileTime
0x180001ac3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ac7  mov     [rbp+arg_0], rax
0x180001acb  call    cs:__imp_GetCurrentProcessId
0x180001ad1  mov     eax, eax
0x180001ad3  xor     [rbp+arg_0], rax
0x180001ad7  call    cs:__imp_GetCurrentThreadId
0x180001add  mov     eax, eax
0x180001adf  xor     [rbp+arg_0], rax
0x180001ae3  call    cs:__imp_GetTickCount
0x180001ae9  mov     eax, eax
0x180001aeb  shl     rax, 18h
0x180001aef  xor     [rbp+arg_0], rax
0x180001af3  call    cs:__imp_GetTickCount
0x180001af9  mov     eax, eax
0x180001afb  lea     rcx, [rbp+arg_0]
0x180001aff  xor     rax, [rbp+arg_0]
0x180001b03  xor     rax, rcx
0x180001b06  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001b0a  mov     [rbp+arg_0], rax
0x180001b0e  call    cs:__imp_QueryPerformanceCounter
0x180001b14  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001b17  mov     rcx, 0FFFFFFFFFFFFh
0x180001b21  shl     rax, 20h
0x180001b25  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001b29  xor     rax, [rbp+arg_0]
0x180001b2d  and     rax, rcx
0x180001b30  mov     rcx, rax
0x180001b33  cmp     rax, rbx
0x180001b36  jnz     short loc_180001B45
0x180001b38  mov     rax, 2B992DDFA233h
0x180001b42  mov     rcx, rax
0x180001b45  mov     cs:__security_cookie, rcx
0x180001b4c  mov     rbx, [rsp+20h+arg_18]
0x180001b51  not     rax
0x180001b54  mov     cs:__security_cookie_complement, rax
0x180001b5b  add     rsp, 20h
0x180001b5f  pop     rbp
0x180001b60  retn
```
