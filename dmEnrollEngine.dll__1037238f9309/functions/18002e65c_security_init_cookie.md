# __security_init_cookie

- ea: `0x18002e65c`
- end: `0x18002e711`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002e140`

## callees

- `0x18002e65c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e6ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e6ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e69f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e69f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002e691`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002e691`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e6bb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002e6bb`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x18002e65c  mov     [rsp-8+arg_10], rbx
0x18002e661  push    rbp
0x18002e662  mov     rbp, rsp
0x18002e665  sub     rsp, 30h
0x18002e669  mov     rax, cs:__security_cookie
0x18002e670  mov     rbx, 2B992DDFA232h
0x18002e67a  cmp     rax, rbx
0x18002e67d  jnz     short loc_18002E6FC
0x18002e67f  xor     eax, eax
0x18002e681  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002e685  mov     [rbp+var_10], rax
0x18002e689  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002e68d  mov     qword ptr [rbp+PerformanceCount], rax
0x18002e691  call    cs:__imp_GetSystemTimeAsFileTime
0x18002e697  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002e69b  mov     [rbp+var_10], rax
0x18002e69f  call    cs:__imp_GetCurrentThreadId
0x18002e6a5  mov     eax, eax
0x18002e6a7  xor     [rbp+var_10], rax
0x18002e6ab  call    cs:__imp_GetCurrentProcessId
0x18002e6b1  mov     eax, eax
0x18002e6b3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002e6b7  xor     [rbp+var_10], rax
0x18002e6bb  call    cs:__imp_QueryPerformanceCounter
0x18002e6c1  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002e6c4  lea     rcx, [rbp+var_10]
0x18002e6c8  shl     rax, 20h
0x18002e6cc  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002e6d0  xor     rax, [rbp+var_10]
0x18002e6d4  xor     rax, rcx
0x18002e6d7  mov     rcx, 0FFFFFFFFFFFFh
0x18002e6e1  and     rax, rcx
0x18002e6e4  mov     rcx, 2B992DDFA233h
0x18002e6ee  cmp     rax, rbx
0x18002e6f1  cmovz   rax, rcx
0x18002e6f5  mov     cs:__security_cookie, rax
0x18002e6fc  mov     rbx, [rsp+30h+arg_10]
0x18002e701  not     rax
0x18002e704  mov     cs:__security_cookie_complement, rax
0x18002e70b  add     rsp, 30h
0x18002e70f  pop     rbp
0x18002e710  retn
```
