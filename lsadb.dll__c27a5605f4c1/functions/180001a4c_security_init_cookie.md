# __security_init_cookie

- ea: `0x180001a4c`
- end: `0x180001b01`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001620`

## callees

- `0x180001a4c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001a8f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001a9b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a81`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001a81`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aab`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001aab`

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
0x180001a4c  mov     [rsp-8+arg_10], rbx
0x180001a51  push    rbp
0x180001a52  mov     rbp, rsp
0x180001a55  sub     rsp, 30h
0x180001a59  mov     rax, cs:__security_cookie
0x180001a60  mov     rbx, 2B992DDFA232h
0x180001a6a  cmp     rax, rbx
0x180001a6d  jnz     short loc_180001AEC
0x180001a6f  xor     eax, eax
0x180001a71  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001a75  mov     [rbp+var_10], rax
0x180001a79  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001a7d  mov     qword ptr [rbp+PerformanceCount], rax
0x180001a81  call    cs:__imp_GetSystemTimeAsFileTime
0x180001a87  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001a8b  mov     [rbp+var_10], rax
0x180001a8f  call    cs:__imp_GetCurrentThreadId
0x180001a95  mov     eax, eax
0x180001a97  xor     [rbp+var_10], rax
0x180001a9b  call    cs:__imp_GetCurrentProcessId
0x180001aa1  mov     eax, eax
0x180001aa3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001aa7  xor     [rbp+var_10], rax
0x180001aab  call    cs:__imp_QueryPerformanceCounter
0x180001ab1  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ab4  lea     rcx, [rbp+var_10]
0x180001ab8  shl     rax, 20h
0x180001abc  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ac0  xor     rax, [rbp+var_10]
0x180001ac4  xor     rax, rcx
0x180001ac7  mov     rcx, 0FFFFFFFFFFFFh
0x180001ad1  and     rax, rcx
0x180001ad4  mov     rcx, 2B992DDFA233h
0x180001ade  cmp     rax, rbx
0x180001ae1  cmovz   rax, rcx
0x180001ae5  mov     cs:__security_cookie, rax
0x180001aec  mov     rbx, [rsp+30h+arg_10]
0x180001af1  not     rax
0x180001af4  mov     cs:__security_cookie_complement, rax
0x180001afb  add     rsp, 30h
0x180001aff  pop     rbp
0x180001b00  retn
```
