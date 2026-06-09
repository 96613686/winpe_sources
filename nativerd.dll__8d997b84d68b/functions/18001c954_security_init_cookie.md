# __security_init_cookie

- ea: `0x18001c954`
- end: `0x18001ca31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001c510`

## callees

- `0x18001c954`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c9a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001c9a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001c99b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c98d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001c98d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c9b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c9c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c9b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001c9c3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001c9de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001c9de`

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
0x18001c954  mov     [rsp-8+arg_18], rbx
0x18001c959  push    rbp
0x18001c95a  mov     rbp, rsp
0x18001c95d  sub     rsp, 20h
0x18001c961  xor     eax, eax
0x18001c963  mov     rbx, 2B992DDFA232h
0x18001c96d  mov     [rbp+arg_0], rax
0x18001c971  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001c975  mov     qword ptr [rbp+PerformanceCount], rax
0x18001c979  mov     rax, cs:__security_cookie
0x18001c980  cmp     rax, rbx
0x18001c983  jnz     loc_18001CA1C
0x18001c989  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001c98d  call    cs:__imp_GetSystemTimeAsFileTime
0x18001c993  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001c997  mov     [rbp+arg_0], rax
0x18001c99b  call    cs:__imp_GetCurrentProcessId
0x18001c9a1  mov     eax, eax
0x18001c9a3  xor     [rbp+arg_0], rax
0x18001c9a7  call    cs:__imp_GetCurrentThreadId
0x18001c9ad  mov     eax, eax
0x18001c9af  xor     [rbp+arg_0], rax
0x18001c9b3  call    cs:__imp_GetTickCount
0x18001c9b9  mov     eax, eax
0x18001c9bb  shl     rax, 18h
0x18001c9bf  xor     [rbp+arg_0], rax
0x18001c9c3  call    cs:__imp_GetTickCount
0x18001c9c9  mov     eax, eax
0x18001c9cb  lea     rcx, [rbp+arg_0]
0x18001c9cf  xor     rax, [rbp+arg_0]
0x18001c9d3  xor     rax, rcx
0x18001c9d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001c9da  mov     [rbp+arg_0], rax
0x18001c9de  call    cs:__imp_QueryPerformanceCounter
0x18001c9e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001c9e7  mov     rcx, 0FFFFFFFFFFFFh
0x18001c9f1  shl     rax, 20h
0x18001c9f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001c9f9  xor     rax, [rbp+arg_0]
0x18001c9fd  and     rax, rcx
0x18001ca00  mov     rcx, rax
0x18001ca03  cmp     rax, rbx
0x18001ca06  jnz     short loc_18001CA15
0x18001ca08  mov     rax, 2B992DDFA233h
0x18001ca12  mov     rcx, rax
0x18001ca15  mov     cs:__security_cookie, rcx
0x18001ca1c  mov     rbx, [rsp+20h+arg_18]
0x18001ca21  not     rax
0x18001ca24  mov     cs:__security_cookie_complement, rax
0x18001ca2b  add     rsp, 20h
0x18001ca2f  pop     rbp
0x18001ca30  retn
```
