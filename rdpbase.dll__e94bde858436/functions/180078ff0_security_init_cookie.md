# __security_init_cookie

- ea: `0x180078ff0`
- end: `0x1800790a5`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180078bd0`

## callees

- `0x180078ff0`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007904f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007904f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007903f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007903f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079033`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180079033`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180079025`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180079025`

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
0x180078ff0  mov     [rsp-8+arg_10], rbx
0x180078ff5  push    rbp
0x180078ff6  mov     rbp, rsp
0x180078ff9  sub     rsp, 30h
0x180078ffd  mov     rax, cs:__security_cookie
0x180079004  mov     rbx, 2B992DDFA232h
0x18007900e  cmp     rax, rbx
0x180079011  jnz     short loc_180079090
0x180079013  xor     eax, eax
0x180079015  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180079019  mov     [rbp+var_10], rax
0x18007901d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180079021  mov     qword ptr [rbp+PerformanceCount], rax
0x180079025  call    cs:__imp_GetSystemTimeAsFileTime
0x18007902b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18007902f  mov     [rbp+var_10], rax
0x180079033  call    cs:__imp_GetCurrentThreadId
0x180079039  mov     eax, eax
0x18007903b  xor     [rbp+var_10], rax
0x18007903f  call    cs:__imp_GetCurrentProcessId
0x180079045  mov     eax, eax
0x180079047  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18007904b  xor     [rbp+var_10], rax
0x18007904f  call    cs:__imp_QueryPerformanceCounter
0x180079055  mov     eax, dword ptr [rbp+PerformanceCount]
0x180079058  lea     rcx, [rbp+var_10]
0x18007905c  shl     rax, 20h
0x180079060  xor     rax, qword ptr [rbp+PerformanceCount]
0x180079064  xor     rax, [rbp+var_10]
0x180079068  xor     rax, rcx
0x18007906b  mov     rcx, 0FFFFFFFFFFFFh
0x180079075  and     rax, rcx
0x180079078  mov     rcx, 2B992DDFA233h
0x180079082  cmp     rax, rbx
0x180079085  cmovz   rax, rcx
0x180079089  mov     cs:__security_cookie, rax
0x180079090  mov     rbx, [rsp+30h+arg_10]
0x180079095  not     rax
0x180079098  mov     cs:__security_cookie_complement, rax
0x18007909f  add     rsp, 30h
0x1800790a3  pop     rbp
0x1800790a4  retn
```
