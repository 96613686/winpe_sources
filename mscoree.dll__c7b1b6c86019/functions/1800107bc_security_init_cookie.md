# __security_init_cookie

- ea: `0x1800107bc`
- end: `0x180010899`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000bd64`
- `0x18000bdb0`

## callees

- `0x1800107bc`

## import_xrefs

- `KERNEL32!GetCurrentProcessId` at `0x180010803`
- `KERNEL32!GetCurrentProcessId` at `0x180010803`
- `KERNEL32!GetCurrentThreadId` at `0x18001080f`
- `KERNEL32!GetCurrentThreadId` at `0x18001080f`
- `KERNEL32!QueryPerformanceCounter` at `0x180010846`
- `KERNEL32!QueryPerformanceCounter` at `0x180010846`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800107f5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1800107f5`
- `KERNEL32!GetTickCount` at `0x18001081b`
- `KERNEL32!GetTickCount` at `0x18001082b`
- `KERNEL32!GetTickCount` at `0x18001081b`
- `KERNEL32!GetTickCount` at `0x18001082b`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x1800107bc  mov     [rsp-8+arg_18], rbx
0x1800107c1  push    rbp
0x1800107c2  mov     rbp, rsp
0x1800107c5  sub     rsp, 20h
0x1800107c9  xor     eax, eax
0x1800107cb  mov     rbx, 2B992DDFA232h
0x1800107d5  mov     [rbp+arg_0], rax
0x1800107d9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800107dd  mov     qword ptr [rbp+PerformanceCount], rax
0x1800107e1  mov     rax, cs:__security_cookie
0x1800107e8  cmp     rax, rbx
0x1800107eb  jnz     loc_180010884
0x1800107f1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800107f5  call    cs:__imp_GetSystemTimeAsFileTime
0x1800107fb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800107ff  mov     [rbp+arg_0], rax
0x180010803  call    cs:__imp_GetCurrentProcessId
0x180010809  mov     eax, eax
0x18001080b  xor     [rbp+arg_0], rax
0x18001080f  call    cs:__imp_GetCurrentThreadId
0x180010815  mov     eax, eax
0x180010817  xor     [rbp+arg_0], rax
0x18001081b  call    cs:__imp_GetTickCount
0x180010821  mov     eax, eax
0x180010823  shl     rax, 18h
0x180010827  xor     [rbp+arg_0], rax
0x18001082b  call    cs:__imp_GetTickCount
0x180010831  mov     eax, eax
0x180010833  lea     rcx, [rbp+arg_0]
0x180010837  xor     rax, [rbp+arg_0]
0x18001083b  xor     rax, rcx
0x18001083e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180010842  mov     [rbp+arg_0], rax
0x180010846  call    cs:__imp_QueryPerformanceCounter
0x18001084c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001084f  mov     rcx, 0FFFFFFFFFFFFh
0x180010859  shl     rax, 20h
0x18001085d  xor     rax, qword ptr [rbp+PerformanceCount]
0x180010861  xor     rax, [rbp+arg_0]
0x180010865  and     rax, rcx
0x180010868  mov     rcx, rax
0x18001086b  cmp     rax, rbx
0x18001086e  jnz     short loc_18001087D
0x180010870  mov     rax, 2B992DDFA233h
0x18001087a  mov     rcx, rax
0x18001087d  mov     cs:__security_cookie, rcx
0x180010884  mov     rbx, [rsp+20h+arg_18]
0x180010889  not     rax
0x18001088c  mov     cs:__security_cookie_complement, rax
0x180010893  add     rsp, 20h
0x180010897  pop     rbp
0x180010898  retn
```
