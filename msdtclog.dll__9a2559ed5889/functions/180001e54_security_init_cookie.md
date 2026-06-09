# __security_init_cookie

- ea: `0x180001e54`
- end: `0x180001f31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001620`

## callees

- `0x180001e54`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001eb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ec3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001eb3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180001ec3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001e8d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001e8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001e9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001e9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ea7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ea7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001ede`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001ede`

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
0x180001e54  mov     [rsp-8+arg_18], rbx
0x180001e59  push    rbp
0x180001e5a  mov     rbp, rsp
0x180001e5d  sub     rsp, 20h
0x180001e61  xor     eax, eax
0x180001e63  mov     rbx, 2B992DDFA232h
0x180001e6d  mov     [rbp+arg_0], rax
0x180001e71  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001e75  mov     qword ptr [rbp+PerformanceCount], rax
0x180001e79  mov     rax, cs:__security_cookie
0x180001e80  cmp     rax, rbx
0x180001e83  jnz     loc_180001F1C
0x180001e89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001e8d  call    cs:__imp_GetSystemTimeAsFileTime
0x180001e93  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001e97  mov     [rbp+arg_0], rax
0x180001e9b  call    cs:__imp_GetCurrentProcessId
0x180001ea1  mov     eax, eax
0x180001ea3  xor     [rbp+arg_0], rax
0x180001ea7  call    cs:__imp_GetCurrentThreadId
0x180001ead  mov     eax, eax
0x180001eaf  xor     [rbp+arg_0], rax
0x180001eb3  call    cs:__imp_GetTickCount
0x180001eb9  mov     eax, eax
0x180001ebb  shl     rax, 18h
0x180001ebf  xor     [rbp+arg_0], rax
0x180001ec3  call    cs:__imp_GetTickCount
0x180001ec9  mov     eax, eax
0x180001ecb  lea     rcx, [rbp+arg_0]
0x180001ecf  xor     rax, [rbp+arg_0]
0x180001ed3  xor     rax, rcx
0x180001ed6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001eda  mov     [rbp+arg_0], rax
0x180001ede  call    cs:__imp_QueryPerformanceCounter
0x180001ee4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001ee7  mov     rcx, 0FFFFFFFFFFFFh
0x180001ef1  shl     rax, 20h
0x180001ef5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001ef9  xor     rax, [rbp+arg_0]
0x180001efd  and     rax, rcx
0x180001f00  mov     rcx, rax
0x180001f03  cmp     rax, rbx
0x180001f06  jnz     short loc_180001F15
0x180001f08  mov     rax, 2B992DDFA233h
0x180001f12  mov     rcx, rax
0x180001f15  mov     cs:__security_cookie, rcx
0x180001f1c  mov     rbx, [rsp+20h+arg_18]
0x180001f21  not     rax
0x180001f24  mov     cs:__security_cookie_complement, rax
0x180001f2b  add     rsp, 20h
0x180001f2f  pop     rbp
0x180001f30  retn
```
