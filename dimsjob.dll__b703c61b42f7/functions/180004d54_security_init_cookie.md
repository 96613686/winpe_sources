# __security_init_cookie

- ea: `0x180004d54`
- end: `0x180004e31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180004610`

## callees

- `0x180004d54`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180004d9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004da7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004da7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004db3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004dc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004db3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180004dc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180004d8d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004dde`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180004dde`

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
0x180004d54  mov     [rsp-8+arg_18], rbx
0x180004d59  push    rbp
0x180004d5a  mov     rbp, rsp
0x180004d5d  sub     rsp, 20h
0x180004d61  xor     eax, eax
0x180004d63  mov     rbx, 2B992DDFA232h
0x180004d6d  mov     [rbp+arg_0], rax
0x180004d71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180004d75  mov     qword ptr [rbp+PerformanceCount], rax
0x180004d79  mov     rax, cs:__security_cookie
0x180004d80  cmp     rax, rbx
0x180004d83  jnz     loc_180004E1C
0x180004d89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180004d8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180004d93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180004d97  mov     [rbp+arg_0], rax
0x180004d9b  call    cs:__imp_GetCurrentProcessId
0x180004da1  mov     eax, eax
0x180004da3  xor     [rbp+arg_0], rax
0x180004da7  call    cs:__imp_GetCurrentThreadId
0x180004dad  mov     eax, eax
0x180004daf  xor     [rbp+arg_0], rax
0x180004db3  call    cs:__imp_GetTickCount
0x180004db9  mov     eax, eax
0x180004dbb  shl     rax, 18h
0x180004dbf  xor     [rbp+arg_0], rax
0x180004dc3  call    cs:__imp_GetTickCount
0x180004dc9  mov     eax, eax
0x180004dcb  lea     rcx, [rbp+arg_0]
0x180004dcf  xor     rax, [rbp+arg_0]
0x180004dd3  xor     rax, rcx
0x180004dd6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180004dda  mov     [rbp+arg_0], rax
0x180004dde  call    cs:__imp_QueryPerformanceCounter
0x180004de4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180004de7  mov     rcx, 0FFFFFFFFFFFFh
0x180004df1  shl     rax, 20h
0x180004df5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180004df9  xor     rax, [rbp+arg_0]
0x180004dfd  and     rax, rcx
0x180004e00  mov     rcx, rax
0x180004e03  cmp     rax, rbx
0x180004e06  jnz     short loc_180004E15
0x180004e08  mov     rax, 2B992DDFA233h
0x180004e12  mov     rcx, rax
0x180004e15  mov     cs:__security_cookie, rcx
0x180004e1c  mov     rbx, [rsp+20h+arg_18]
0x180004e21  not     rax
0x180004e24  mov     cs:__security_cookie_complement, rax
0x180004e2b  add     rsp, 20h
0x180004e2f  pop     rbp
0x180004e30  retn
```
