# __security_init_cookie

- ea: `0x18000d7c4`
- end: `0x18000d8a1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d290`

## callees

- `0x18000d7c4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d80b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000d80b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d7fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d7fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d833`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000d833`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d84e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000d84e`

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
0x18000d7c4  mov     [rsp-8+arg_18], rbx
0x18000d7c9  push    rbp
0x18000d7ca  mov     rbp, rsp
0x18000d7cd  sub     rsp, 20h
0x18000d7d1  xor     eax, eax
0x18000d7d3  mov     rbx, 2B992DDFA232h
0x18000d7dd  mov     [rbp+arg_0], rax
0x18000d7e1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000d7e5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000d7e9  mov     rax, cs:__security_cookie
0x18000d7f0  cmp     rax, rbx
0x18000d7f3  jnz     loc_18000D88C
0x18000d7f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d7fd  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d803  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d807  mov     [rbp+arg_0], rax
0x18000d80b  call    cs:__imp_GetCurrentProcessId
0x18000d811  mov     eax, eax
0x18000d813  xor     [rbp+arg_0], rax
0x18000d817  call    cs:__imp_GetCurrentThreadId
0x18000d81d  mov     eax, eax
0x18000d81f  xor     [rbp+arg_0], rax
0x18000d823  call    cs:__imp_GetTickCount
0x18000d829  mov     eax, eax
0x18000d82b  shl     rax, 18h
0x18000d82f  xor     [rbp+arg_0], rax
0x18000d833  call    cs:__imp_GetTickCount
0x18000d839  mov     eax, eax
0x18000d83b  lea     rcx, [rbp+arg_0]
0x18000d83f  xor     rax, [rbp+arg_0]
0x18000d843  xor     rax, rcx
0x18000d846  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000d84a  mov     [rbp+arg_0], rax
0x18000d84e  call    cs:__imp_QueryPerformanceCounter
0x18000d854  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000d857  mov     rcx, 0FFFFFFFFFFFFh
0x18000d861  shl     rax, 20h
0x18000d865  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000d869  xor     rax, [rbp+arg_0]
0x18000d86d  and     rax, rcx
0x18000d870  mov     rcx, rax
0x18000d873  cmp     rax, rbx
0x18000d876  jnz     short loc_18000D885
0x18000d878  mov     rax, 2B992DDFA233h
0x18000d882  mov     rcx, rax
0x18000d885  mov     cs:__security_cookie, rcx
0x18000d88c  mov     rbx, [rsp+20h+arg_18]
0x18000d891  not     rax
0x18000d894  mov     cs:__security_cookie_complement, rax
0x18000d89b  add     rsp, 20h
0x18000d89f  pop     rbp
0x18000d8a0  retn
```
