# __security_init_cookie

- ea: `0x180002e44`
- end: `0x180002f21`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002650`

## callees

- `0x180002e44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002e97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002e8b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002ece`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002ece`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002e7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ea3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002eb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002ea3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002eb3`

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
0x180002e44  mov     [rsp-8+arg_18], rbx
0x180002e49  push    rbp
0x180002e4a  mov     rbp, rsp
0x180002e4d  sub     rsp, 20h
0x180002e51  xor     eax, eax
0x180002e53  mov     rbx, 2B992DDFA232h
0x180002e5d  mov     [rbp+arg_0], rax
0x180002e61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002e65  mov     qword ptr [rbp+PerformanceCount], rax
0x180002e69  mov     rax, cs:__security_cookie
0x180002e70  cmp     rax, rbx
0x180002e73  jnz     loc_180002F0C
0x180002e79  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002e7d  call    cs:__imp_GetSystemTimeAsFileTime
0x180002e83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002e87  mov     [rbp+arg_0], rax
0x180002e8b  call    cs:__imp_GetCurrentProcessId
0x180002e91  mov     eax, eax
0x180002e93  xor     [rbp+arg_0], rax
0x180002e97  call    cs:__imp_GetCurrentThreadId
0x180002e9d  mov     eax, eax
0x180002e9f  xor     [rbp+arg_0], rax
0x180002ea3  call    cs:__imp_GetTickCount
0x180002ea9  mov     eax, eax
0x180002eab  shl     rax, 18h
0x180002eaf  xor     [rbp+arg_0], rax
0x180002eb3  call    cs:__imp_GetTickCount
0x180002eb9  mov     eax, eax
0x180002ebb  lea     rcx, [rbp+arg_0]
0x180002ebf  xor     rax, [rbp+arg_0]
0x180002ec3  xor     rax, rcx
0x180002ec6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002eca  mov     [rbp+arg_0], rax
0x180002ece  call    cs:__imp_QueryPerformanceCounter
0x180002ed4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002ed7  mov     rcx, 0FFFFFFFFFFFFh
0x180002ee1  shl     rax, 20h
0x180002ee5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002ee9  xor     rax, [rbp+arg_0]
0x180002eed  and     rax, rcx
0x180002ef0  mov     rcx, rax
0x180002ef3  cmp     rax, rbx
0x180002ef6  jnz     short loc_180002F05
0x180002ef8  mov     rax, 2B992DDFA233h
0x180002f02  mov     rcx, rax
0x180002f05  mov     cs:__security_cookie, rcx
0x180002f0c  mov     rbx, [rsp+20h+arg_18]
0x180002f11  not     rax
0x180002f14  mov     cs:__security_cookie_complement, rax
0x180002f1b  add     rsp, 20h
0x180002f1f  pop     rbp
0x180002f20  retn
```
