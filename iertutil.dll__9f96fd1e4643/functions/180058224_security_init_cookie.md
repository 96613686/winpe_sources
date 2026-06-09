# __security_init_cookie

- ea: `0x180058224`
- end: `0x180058301`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800577c0`

## callees

- `0x180058224`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005826b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005826b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058277`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180058277`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058283`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058293`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058283`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180058293`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005825d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005825d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800582ae`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800582ae`

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
0x180058224  mov     [rsp-8+arg_18], rbx
0x180058229  push    rbp
0x18005822a  mov     rbp, rsp
0x18005822d  sub     rsp, 20h
0x180058231  xor     eax, eax
0x180058233  mov     rbx, 2B992DDFA232h
0x18005823d  mov     [rbp+arg_0], rax
0x180058241  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180058245  mov     qword ptr [rbp+PerformanceCount], rax
0x180058249  mov     rax, cs:__security_cookie
0x180058250  cmp     rax, rbx
0x180058253  jnz     loc_1800582EC
0x180058259  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005825d  call    cs:__imp_GetSystemTimeAsFileTime
0x180058263  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180058267  mov     [rbp+arg_0], rax
0x18005826b  call    cs:__imp_GetCurrentProcessId
0x180058271  mov     eax, eax
0x180058273  xor     [rbp+arg_0], rax
0x180058277  call    cs:__imp_GetCurrentThreadId
0x18005827d  mov     eax, eax
0x18005827f  xor     [rbp+arg_0], rax
0x180058283  call    cs:__imp_GetTickCount
0x180058289  mov     eax, eax
0x18005828b  shl     rax, 18h
0x18005828f  xor     [rbp+arg_0], rax
0x180058293  call    cs:__imp_GetTickCount
0x180058299  mov     eax, eax
0x18005829b  lea     rcx, [rbp+arg_0]
0x18005829f  xor     rax, [rbp+arg_0]
0x1800582a3  xor     rax, rcx
0x1800582a6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800582aa  mov     [rbp+arg_0], rax
0x1800582ae  call    cs:__imp_QueryPerformanceCounter
0x1800582b4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800582b7  mov     rcx, 0FFFFFFFFFFFFh
0x1800582c1  shl     rax, 20h
0x1800582c5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800582c9  xor     rax, [rbp+arg_0]
0x1800582cd  and     rax, rcx
0x1800582d0  mov     rcx, rax
0x1800582d3  cmp     rax, rbx
0x1800582d6  jnz     short loc_1800582E5
0x1800582d8  mov     rax, 2B992DDFA233h
0x1800582e2  mov     rcx, rax
0x1800582e5  mov     cs:__security_cookie, rcx
0x1800582ec  mov     rbx, [rsp+20h+arg_18]
0x1800582f1  not     rax
0x1800582f4  mov     cs:__security_cookie_complement, rax
0x1800582fb  add     rsp, 20h
0x1800582ff  pop     rbp
0x180058300  retn
```
