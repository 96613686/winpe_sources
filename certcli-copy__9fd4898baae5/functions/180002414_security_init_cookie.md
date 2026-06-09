# __security_init_cookie

- ea: `0x180002414`
- end: `0x1800024f1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a20`

## callees

- `0x180002414`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000244d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000244d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002473`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002483`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002473`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002483`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002467`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000245b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000245b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000249e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000249e`

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
0x180002414  mov     [rsp-8+arg_18], rbx
0x180002419  push    rbp
0x18000241a  mov     rbp, rsp
0x18000241d  sub     rsp, 20h
0x180002421  xor     eax, eax
0x180002423  mov     rbx, 2B992DDFA232h
0x18000242d  mov     [rbp+arg_0], rax
0x180002431  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002435  mov     qword ptr [rbp+PerformanceCount], rax
0x180002439  mov     rax, cs:__security_cookie
0x180002440  cmp     rax, rbx
0x180002443  jnz     loc_1800024DC
0x180002449  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000244d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002453  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002457  mov     [rbp+arg_0], rax
0x18000245b  call    cs:__imp_GetCurrentProcessId
0x180002461  mov     eax, eax
0x180002463  xor     [rbp+arg_0], rax
0x180002467  call    cs:__imp_GetCurrentThreadId
0x18000246d  mov     eax, eax
0x18000246f  xor     [rbp+arg_0], rax
0x180002473  call    cs:__imp_GetTickCount
0x180002479  mov     eax, eax
0x18000247b  shl     rax, 18h
0x18000247f  xor     [rbp+arg_0], rax
0x180002483  call    cs:__imp_GetTickCount
0x180002489  mov     eax, eax
0x18000248b  lea     rcx, [rbp+arg_0]
0x18000248f  xor     rax, [rbp+arg_0]
0x180002493  xor     rax, rcx
0x180002496  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000249a  mov     [rbp+arg_0], rax
0x18000249e  call    cs:__imp_QueryPerformanceCounter
0x1800024a4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800024a7  mov     rcx, 0FFFFFFFFFFFFh
0x1800024b1  shl     rax, 20h
0x1800024b5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800024b9  xor     rax, [rbp+arg_0]
0x1800024bd  and     rax, rcx
0x1800024c0  mov     rcx, rax
0x1800024c3  cmp     rax, rbx
0x1800024c6  jnz     short loc_1800024D5
0x1800024c8  mov     rax, 2B992DDFA233h
0x1800024d2  mov     rcx, rax
0x1800024d5  mov     cs:__security_cookie, rcx
0x1800024dc  mov     rbx, [rsp+20h+arg_18]
0x1800024e1  not     rax
0x1800024e4  mov     cs:__security_cookie_complement, rax
0x1800024eb  add     rsp, 20h
0x1800024ef  pop     rbp
0x1800024f0  retn
```
