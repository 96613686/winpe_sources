# __security_init_cookie

- ea: `0x180010964`
- end: `0x180010a41`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800100b0`

## callees

- `0x180010964`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1800109ee`
- `KERNEL32!QueryPerformanceCounter` at `0x1800109ee`
- `KERNEL32!GetCurrentProcessId` at `0x1800109ab`
- `KERNEL32!GetCurrentProcessId` at `0x1800109ab`
- `KERNEL32!GetCurrentThreadId` at `0x1800109b7`
- `KERNEL32!GetCurrentThreadId` at `0x1800109b7`
- `KERNEL32!GetTickCount` at `0x1800109c3`
- `KERNEL32!GetTickCount` at `0x1800109d3`
- `KERNEL32!GetTickCount` at `0x1800109c3`
- `KERNEL32!GetTickCount` at `0x1800109d3`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001099d`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001099d`

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
0x180010964  mov     [rsp-8+arg_18], rbx
0x180010969  push    rbp
0x18001096a  mov     rbp, rsp
0x18001096d  sub     rsp, 20h
0x180010971  xor     eax, eax
0x180010973  mov     rbx, 2B992DDFA232h
0x18001097d  mov     [rbp+arg_0], rax
0x180010981  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180010985  mov     qword ptr [rbp+PerformanceCount], rax
0x180010989  mov     rax, cs:__security_cookie
0x180010990  cmp     rax, rbx
0x180010993  jnz     loc_180010A2C
0x180010999  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001099d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800109a3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800109a7  mov     [rbp+arg_0], rax
0x1800109ab  call    cs:__imp_GetCurrentProcessId
0x1800109b1  mov     eax, eax
0x1800109b3  xor     [rbp+arg_0], rax
0x1800109b7  call    cs:__imp_GetCurrentThreadId
0x1800109bd  mov     eax, eax
0x1800109bf  xor     [rbp+arg_0], rax
0x1800109c3  call    cs:__imp_GetTickCount
0x1800109c9  mov     eax, eax
0x1800109cb  shl     rax, 18h
0x1800109cf  xor     [rbp+arg_0], rax
0x1800109d3  call    cs:__imp_GetTickCount
0x1800109d9  mov     eax, eax
0x1800109db  lea     rcx, [rbp+arg_0]
0x1800109df  xor     rax, [rbp+arg_0]
0x1800109e3  xor     rax, rcx
0x1800109e6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800109ea  mov     [rbp+arg_0], rax
0x1800109ee  call    cs:__imp_QueryPerformanceCounter
0x1800109f4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800109f7  mov     rcx, 0FFFFFFFFFFFFh
0x180010a01  shl     rax, 20h
0x180010a05  xor     rax, qword ptr [rbp+PerformanceCount]
0x180010a09  xor     rax, [rbp+arg_0]
0x180010a0d  and     rax, rcx
0x180010a10  mov     rcx, rax
0x180010a13  cmp     rax, rbx
0x180010a16  jnz     short loc_180010A25
0x180010a18  mov     rax, 2B992DDFA233h
0x180010a22  mov     rcx, rax
0x180010a25  mov     cs:__security_cookie, rcx
0x180010a2c  mov     rbx, [rsp+20h+arg_18]
0x180010a31  not     rax
0x180010a34  mov     cs:__security_cookie_complement, rax
0x180010a3b  add     rsp, 20h
0x180010a3f  pop     rbp
0x180010a40  retn
```
