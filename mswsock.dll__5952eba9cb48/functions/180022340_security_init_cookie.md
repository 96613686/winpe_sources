# __security_init_cookie

- ea: `0x180022340`
- end: `0x1800223f5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800222a0`

## callees

- `0x180022340`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002238f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002238f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022383`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022383`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022375`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180022375`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002239f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002239f`

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
0x180022340  mov     [rsp-8+arg_10], rbx
0x180022345  push    rbp
0x180022346  mov     rbp, rsp
0x180022349  sub     rsp, 30h
0x18002234d  mov     rax, cs:__security_cookie
0x180022354  mov     rbx, 2B992DDFA232h
0x18002235e  cmp     rax, rbx
0x180022361  jnz     short loc_1800223E0
0x180022363  xor     eax, eax
0x180022365  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180022369  mov     [rbp+var_10], rax
0x18002236d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180022371  mov     qword ptr [rbp+PerformanceCount], rax
0x180022375  call    cs:__imp_GetSystemTimeAsFileTime
0x18002237b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002237f  mov     [rbp+var_10], rax
0x180022383  call    cs:__imp_GetCurrentThreadId
0x180022389  mov     eax, eax
0x18002238b  xor     [rbp+var_10], rax
0x18002238f  call    cs:__imp_GetCurrentProcessId
0x180022395  mov     eax, eax
0x180022397  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002239b  xor     [rbp+var_10], rax
0x18002239f  call    cs:__imp_QueryPerformanceCounter
0x1800223a5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800223a8  lea     rcx, [rbp+var_10]
0x1800223ac  shl     rax, 20h
0x1800223b0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800223b4  xor     rax, [rbp+var_10]
0x1800223b8  xor     rax, rcx
0x1800223bb  mov     rcx, 0FFFFFFFFFFFFh
0x1800223c5  and     rax, rcx
0x1800223c8  mov     rcx, 2B992DDFA233h
0x1800223d2  cmp     rax, rbx
0x1800223d5  cmovz   rax, rcx
0x1800223d9  mov     cs:__security_cookie, rax
0x1800223e0  mov     rbx, [rsp+30h+arg_10]
0x1800223e5  not     rax
0x1800223e8  mov     cs:__security_cookie_complement, rax
0x1800223ef  add     rsp, 30h
0x1800223f3  pop     rbp
0x1800223f4  retn
```
