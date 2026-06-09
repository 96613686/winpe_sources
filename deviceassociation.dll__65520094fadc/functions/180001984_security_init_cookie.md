# __security_init_cookie

- ea: `0x180001984`
- end: `0x180001a61`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001450`

## callees

- `0x180001984`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800019d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800019cb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a0e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001a0e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800019bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019e3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800019f3`

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
0x180001984  mov     [rsp-8+arg_18], rbx
0x180001989  push    rbp
0x18000198a  mov     rbp, rsp
0x18000198d  sub     rsp, 20h
0x180001991  xor     eax, eax
0x180001993  mov     rbx, 2B992DDFA232h
0x18000199d  mov     [rbp+arg_0], rax
0x1800019a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800019a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800019a9  mov     rax, cs:__security_cookie
0x1800019b0  cmp     rax, rbx
0x1800019b3  jnz     loc_180001A4C
0x1800019b9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800019bd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800019c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800019c7  mov     [rbp+arg_0], rax
0x1800019cb  call    cs:__imp_GetCurrentProcessId
0x1800019d1  mov     eax, eax
0x1800019d3  xor     [rbp+arg_0], rax
0x1800019d7  call    cs:__imp_GetCurrentThreadId
0x1800019dd  mov     eax, eax
0x1800019df  xor     [rbp+arg_0], rax
0x1800019e3  call    cs:__imp_GetTickCount
0x1800019e9  mov     eax, eax
0x1800019eb  shl     rax, 18h
0x1800019ef  xor     [rbp+arg_0], rax
0x1800019f3  call    cs:__imp_GetTickCount
0x1800019f9  mov     eax, eax
0x1800019fb  lea     rcx, [rbp+arg_0]
0x1800019ff  xor     rax, [rbp+arg_0]
0x180001a03  xor     rax, rcx
0x180001a06  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001a0a  mov     [rbp+arg_0], rax
0x180001a0e  call    cs:__imp_QueryPerformanceCounter
0x180001a14  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001a17  mov     rcx, 0FFFFFFFFFFFFh
0x180001a21  shl     rax, 20h
0x180001a25  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001a29  xor     rax, [rbp+arg_0]
0x180001a2d  and     rax, rcx
0x180001a30  mov     rcx, rax
0x180001a33  cmp     rax, rbx
0x180001a36  jnz     short loc_180001A45
0x180001a38  mov     rax, 2B992DDFA233h
0x180001a42  mov     rcx, rax
0x180001a45  mov     cs:__security_cookie, rcx
0x180001a4c  mov     rbx, [rsp+20h+arg_18]
0x180001a51  not     rax
0x180001a54  mov     cs:__security_cookie_complement, rax
0x180001a5b  add     rsp, 20h
0x180001a5f  pop     rbp
0x180001a60  retn
```
