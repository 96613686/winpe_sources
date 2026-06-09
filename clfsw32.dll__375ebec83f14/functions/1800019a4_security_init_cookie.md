# __security_init_cookie

- ea: `0x1800019a4`
- end: `0x180001a81`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001540`

## callees

- `0x1800019a4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019f7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a2e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a2e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a13`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a03`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001a13`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019dd`

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
0x1800019a4  mov     [rsp-8+arg_18], rbx
0x1800019a9  push    rbp
0x1800019aa  mov     rbp, rsp
0x1800019ad  sub     rsp, 20h
0x1800019b1  xor     eax, eax
0x1800019b3  mov     rbx, 2B992DDFA232h
0x1800019bd  mov     [rbp+arg_0], rax
0x1800019c1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019c5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019c9  mov     rax, cs:__security_cookie
0x1800019d0  cmp     rax, rbx
0x1800019d3  jnz     loc_180001A6C
0x1800019d9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019e7  mov     [rbp+arg_0], rax
0x1800019eb  call    cs:__imp_GetCurrentProcessId
0x1800019f1  mov     eax, eax
0x1800019f3  xor     [rbp+arg_0], rax
0x1800019f7  call    cs:__imp_GetCurrentThreadId
0x1800019fd  mov     eax, eax
0x1800019ff  xor     [rbp+arg_0], rax
0x180001a03  call    cs:__imp_GetTickCount
0x180001a09  mov     eax, eax
0x180001a0b  shl     rax, 18h
0x180001a0f  xor     [rbp+arg_0], rax
0x180001a13  call    cs:__imp_GetTickCount
0x180001a19  mov     eax, eax
0x180001a1b  lea     rcx, [rbp+arg_0]
0x180001a1f  xor     rax, [rbp+arg_0]
0x180001a23  xor     rax, rcx
0x180001a26  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a2a  mov     [rbp+arg_0], rax
0x180001a2e  call    cs:__imp_QueryPerformanceCounter
0x180001a34  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a37  mov     rcx, 0FFFFFFFFFFFFh
0x180001a41  shl     rax, 20h
0x180001a45  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a49  xor     rax, [rbp+arg_0]
0x180001a4d  and     rax, rcx
0x180001a50  mov     rcx, rax
0x180001a53  cmp     rax, rbx
0x180001a56  jnz     short loc_180001A65
0x180001a58  mov     rax, 2B992DDFA233h
0x180001a62  mov     rcx, rax
0x180001a65  mov     cs:__security_cookie, rcx
0x180001a6c  mov     rbx, [rsp+20h+arg_18]
0x180001a71  not     rax
0x180001a74  mov     cs:__security_cookie_complement, rax
0x180001a7b  add     rsp, 20h
0x180001a7f  pop     rbp
0x180001a80  retn
```
