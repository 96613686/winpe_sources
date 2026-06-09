# __security_init_cookie

- ea: `0x180004844`
- end: `0x180004921`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800044d0`

## callees

- `0x180004844`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800048ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800048ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000488b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000488b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000487d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000487d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800048a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800048b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800048a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800048b3`

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
0x180004844  mov     [rsp-8+arg_18], rbx
0x180004849  push    rbp
0x18000484a  mov     rbp, rsp
0x18000484d  sub     rsp, 20h
0x180004851  xor     eax, eax
0x180004853  mov     rbx, 2B992DDFA232h
0x18000485d  mov     [rbp+arg_0], rax
0x180004861  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004865  mov     qword ptr [rbp+PerformanceCount], rax
0x180004869  mov     rax, cs:__security_cookie
0x180004870  cmp     rax, rbx
0x180004873  jnz     loc_18000490C
0x180004879  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000487d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004883  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004887  mov     [rbp+arg_0], rax
0x18000488b  call    cs:__imp_GetCurrentProcessId
0x180004891  mov     eax, eax
0x180004893  xor     [rbp+arg_0], rax
0x180004897  call    cs:__imp_GetCurrentThreadId
0x18000489d  mov     eax, eax
0x18000489f  xor     [rbp+arg_0], rax
0x1800048a3  call    cs:__imp_GetTickCount
0x1800048a9  mov     eax, eax
0x1800048ab  shl     rax, 18h
0x1800048af  xor     [rbp+arg_0], rax
0x1800048b3  call    cs:__imp_GetTickCount
0x1800048b9  mov     eax, eax
0x1800048bb  lea     rcx, [rbp+arg_0]
0x1800048bf  xor     rax, [rbp+arg_0]
0x1800048c3  xor     rax, rcx
0x1800048c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800048ca  mov     [rbp+arg_0], rax
0x1800048ce  call    cs:__imp_QueryPerformanceCounter
0x1800048d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800048d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800048e1  shl     rax, 20h
0x1800048e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800048e9  xor     rax, [rbp+arg_0]
0x1800048ed  and     rax, rcx
0x1800048f0  mov     rcx, rax
0x1800048f3  cmp     rax, rbx
0x1800048f6  jnz     short loc_180004905
0x1800048f8  mov     rax, 2B992DDFA233h
0x180004902  mov     rcx, rax
0x180004905  mov     cs:__security_cookie, rcx
0x18000490c  mov     rbx, [rsp+20h+arg_18]
0x180004911  not     rax
0x180004914  mov     cs:__security_cookie_complement, rax
0x18000491b  add     rsp, 20h
0x18000491f  pop     rbp
0x180004920  retn
```
