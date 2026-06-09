# __security_init_cookie

- ea: `0x180001440`
- end: `0x1800014f5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013b0`

## callees

- `0x180001440`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001475`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180001475`
- `KERNEL32!GetCurrentProcessId` at `0x18000148f`
- `KERNEL32!GetCurrentProcessId` at `0x18000148f`
- `KERNEL32!QueryPerformanceCounter` at `0x18000149f`
- `KERNEL32!QueryPerformanceCounter` at `0x18000149f`
- `KERNEL32!GetCurrentThreadId` at `0x180001483`
- `KERNEL32!GetCurrentThreadId` at `0x180001483`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180001440  mov     [rsp-8+arg_10], rbx
0x180001445  push    rbp
0x180001446  mov     rbp, rsp
0x180001449  sub     rsp, 30h
0x18000144d  mov     rax, cs:__security_cookie
0x180001454  mov     rbx, 2B992DDFA232h
0x18000145e  cmp     rax, rbx
0x180001461  jnz     short loc_1800014E0
0x180001463  xor     eax, eax
0x180001465  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001469  mov     [rbp+var_10], rax
0x18000146d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001471  mov     qword ptr [rbp+PerformanceCount], rax
0x180001475  call    cs:__imp_GetSystemTimeAsFileTime
0x18000147b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000147f  mov     [rbp+var_10], rax
0x180001483  call    cs:__imp_GetCurrentThreadId
0x180001489  mov     eax, eax
0x18000148b  xor     [rbp+var_10], rax
0x18000148f  call    cs:__imp_GetCurrentProcessId
0x180001495  mov     eax, eax
0x180001497  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000149b  xor     [rbp+var_10], rax
0x18000149f  call    cs:__imp_QueryPerformanceCounter
0x1800014a5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800014a8  lea     rcx, [rbp+var_10]
0x1800014ac  shl     rax, 20h
0x1800014b0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800014b4  xor     rax, [rbp+var_10]
0x1800014b8  xor     rax, rcx
0x1800014bb  mov     rcx, 0FFFFFFFFFFFFh
0x1800014c5  and     rax, rcx
0x1800014c8  mov     rcx, 2B992DDFA233h
0x1800014d2  cmp     rax, rbx
0x1800014d5  cmovz   rax, rcx
0x1800014d9  mov     cs:__security_cookie, rax
0x1800014e0  mov     rbx, [rsp+30h+arg_10]
0x1800014e5  not     rax
0x1800014e8  mov     cs:__security_cookie_complement, rax
0x1800014ef  add     rsp, 30h
0x1800014f3  pop     rbp
0x1800014f4  retn
```
