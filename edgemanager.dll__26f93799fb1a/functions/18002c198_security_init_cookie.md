# __security_init_cookie

- ea: `0x18002c198`
- end: `0x18002c24d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b4e0`

## callees

- `0x18002c198`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c1db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002c1db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c1e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002c1e7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c1cd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18002c1cd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c1f7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002c1f7`

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
0x18002c198  mov     [rsp-8+arg_10], rbx
0x18002c19d  push    rbp
0x18002c19e  mov     rbp, rsp
0x18002c1a1  sub     rsp, 30h
0x18002c1a5  mov     rax, cs:__security_cookie
0x18002c1ac  mov     rbx, 2B992DDFA232h
0x18002c1b6  cmp     rax, rbx
0x18002c1b9  jnz     short loc_18002C238
0x18002c1bb  xor     eax, eax
0x18002c1bd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18002c1c1  mov     [rbp+var_10], rax
0x18002c1c5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002c1c9  mov     qword ptr [rbp+PerformanceCount], rax
0x18002c1cd  call    cs:__imp_GetSystemTimeAsFileTime
0x18002c1d3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002c1d7  mov     [rbp+var_10], rax
0x18002c1db  call    cs:__imp_GetCurrentThreadId
0x18002c1e1  mov     eax, eax
0x18002c1e3  xor     [rbp+var_10], rax
0x18002c1e7  call    cs:__imp_GetCurrentProcessId
0x18002c1ed  mov     eax, eax
0x18002c1ef  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18002c1f3  xor     [rbp+var_10], rax
0x18002c1f7  call    cs:__imp_QueryPerformanceCounter
0x18002c1fd  mov     eax, dword ptr [rbp+PerformanceCount]
0x18002c200  lea     rcx, [rbp+var_10]
0x18002c204  shl     rax, 20h
0x18002c208  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002c20c  xor     rax, [rbp+var_10]
0x18002c210  xor     rax, rcx
0x18002c213  mov     rcx, 0FFFFFFFFFFFFh
0x18002c21d  and     rax, rcx
0x18002c220  mov     rcx, 2B992DDFA233h
0x18002c22a  cmp     rax, rbx
0x18002c22d  cmovz   rax, rcx
0x18002c231  mov     cs:__security_cookie, rax
0x18002c238  mov     rbx, [rsp+30h+arg_10]
0x18002c23d  not     rax
0x18002c240  mov     cs:__security_cookie_complement, rax
0x18002c247  add     rsp, 30h
0x18002c24b  pop     rbp
0x18002c24c  retn
```
