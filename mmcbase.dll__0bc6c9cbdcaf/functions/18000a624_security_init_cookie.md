# __security_init_cookie

- ea: `0x18000a624`
- end: `0x18000a701`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009df0`

## callees

- `0x18000a624`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a66b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a66b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a677`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a6ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a6ae`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a683`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a693`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a683`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a693`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a65d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a65d`

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
0x18000a624  mov     [rsp-8+arg_18], rbx
0x18000a629  push    rbp
0x18000a62a  mov     rbp, rsp
0x18000a62d  sub     rsp, 20h
0x18000a631  xor     eax, eax
0x18000a633  mov     rbx, 2B992DDFA232h
0x18000a63d  mov     [rbp+arg_0], rax
0x18000a641  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000a645  mov     qword ptr [rbp+PerformanceCount], rax
0x18000a649  mov     rax, cs:__security_cookie
0x18000a650  cmp     rax, rbx
0x18000a653  jnz     loc_18000A6EC
0x18000a659  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a65d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a663  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000a667  mov     [rbp+arg_0], rax
0x18000a66b  call    cs:__imp_GetCurrentProcessId
0x18000a671  mov     eax, eax
0x18000a673  xor     [rbp+arg_0], rax
0x18000a677  call    cs:__imp_GetCurrentThreadId
0x18000a67d  mov     eax, eax
0x18000a67f  xor     [rbp+arg_0], rax
0x18000a683  call    cs:__imp_GetTickCount
0x18000a689  mov     eax, eax
0x18000a68b  shl     rax, 18h
0x18000a68f  xor     [rbp+arg_0], rax
0x18000a693  call    cs:__imp_GetTickCount
0x18000a699  mov     eax, eax
0x18000a69b  lea     rcx, [rbp+arg_0]
0x18000a69f  xor     rax, [rbp+arg_0]
0x18000a6a3  xor     rax, rcx
0x18000a6a6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000a6aa  mov     [rbp+arg_0], rax
0x18000a6ae  call    cs:__imp_QueryPerformanceCounter
0x18000a6b4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000a6b7  mov     rcx, 0FFFFFFFFFFFFh
0x18000a6c1  shl     rax, 20h
0x18000a6c5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000a6c9  xor     rax, [rbp+arg_0]
0x18000a6cd  and     rax, rcx
0x18000a6d0  mov     rcx, rax
0x18000a6d3  cmp     rax, rbx
0x18000a6d6  jnz     short loc_18000A6E5
0x18000a6d8  mov     rax, 2B992DDFA233h
0x18000a6e2  mov     rcx, rax
0x18000a6e5  mov     cs:__security_cookie, rcx
0x18000a6ec  mov     rbx, [rsp+20h+arg_18]
0x18000a6f1  not     rax
0x18000a6f4  mov     cs:__security_cookie_complement, rax
0x18000a6fb  add     rsp, 20h
0x18000a6ff  pop     rbp
0x18000a700  retn
```
