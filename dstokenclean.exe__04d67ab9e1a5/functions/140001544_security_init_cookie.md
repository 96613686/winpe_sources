# __security_init_cookie

- ea: `0x140001544`
- end: `0x140001621`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001310`

## callees

- `0x140001544`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400015ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400015ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000158b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x14000158b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001597`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001597`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400015a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400015b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400015a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400015b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000157d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x14000157d`

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
0x140001544  mov     [rsp-8+arg_18], rbx
0x140001549  push    rbp
0x14000154a  mov     rbp, rsp
0x14000154d  sub     rsp, 20h
0x140001551  xor     eax, eax
0x140001553  mov     rbx, 2B992DDFA232h
0x14000155d  mov     [rbp+arg_0], rax
0x140001561  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001565  mov     qword ptr [rbp+PerformanceCount], rax
0x140001569  mov     rax, cs:__security_cookie
0x140001570  cmp     rax, rbx
0x140001573  jnz     loc_14000160C
0x140001579  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000157d  call    cs:__imp_GetSystemTimeAsFileTime
0x140001583  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001587  mov     [rbp+arg_0], rax
0x14000158b  call    cs:__imp_GetCurrentProcessId
0x140001591  mov     eax, eax
0x140001593  xor     [rbp+arg_0], rax
0x140001597  call    cs:__imp_GetCurrentThreadId
0x14000159d  mov     eax, eax
0x14000159f  xor     [rbp+arg_0], rax
0x1400015a3  call    cs:__imp_GetTickCount
0x1400015a9  mov     eax, eax
0x1400015ab  shl     rax, 18h
0x1400015af  xor     [rbp+arg_0], rax
0x1400015b3  call    cs:__imp_GetTickCount
0x1400015b9  mov     eax, eax
0x1400015bb  lea     rcx, [rbp+arg_0]
0x1400015bf  xor     rax, [rbp+arg_0]
0x1400015c3  xor     rax, rcx
0x1400015c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400015ca  mov     [rbp+arg_0], rax
0x1400015ce  call    cs:__imp_QueryPerformanceCounter
0x1400015d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400015d7  mov     rcx, 0FFFFFFFFFFFFh
0x1400015e1  shl     rax, 20h
0x1400015e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400015e9  xor     rax, [rbp+arg_0]
0x1400015ed  and     rax, rcx
0x1400015f0  mov     rcx, rax
0x1400015f3  cmp     rax, rbx
0x1400015f6  jnz     short loc_140001605
0x1400015f8  mov     rax, 2B992DDFA233h
0x140001602  mov     rcx, rax
0x140001605  mov     cs:__security_cookie, rcx
0x14000160c  mov     rbx, [rsp+20h+arg_18]
0x140001611  not     rax
0x140001614  mov     cs:__security_cookie_complement, rax
0x14000161b  add     rsp, 20h
0x14000161f  pop     rbp
0x140001620  retn
```
