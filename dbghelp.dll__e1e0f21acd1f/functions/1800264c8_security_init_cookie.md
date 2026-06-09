# __security_init_cookie

- ea: `0x1800264c8`
- end: `0x18002659c`
- name: `__security_init_cookie`
- size: `212`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026930`

## callees

- `0x1800264c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026520`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026514`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180026514`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002652c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002653c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002652c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18002653c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026506`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180026506`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026557`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026557`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rcx
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  v1 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  if ( !_security_cookie || _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v1);
    v1 = (struct _FILETIME)((unsigned __int64)&v1 ^ *(unsigned __int64 *)&v1 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = 0x2B992DDFA232LL;
    if ( ((*(_QWORD *)&v1
         ^ PerformanceCount.QuadPart
         ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
        & 0xFFFFFFFFFFFFLL) != 0 )
      v0 = (*(_QWORD *)&v1
          ^ PerformanceCount.QuadPart
          ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
         & 0xFFFFFFFFFFFFLL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800264c8  mov     [rsp-8+arg_18], rbx
0x1800264cd  push    rbp
0x1800264ce  mov     rbp, rsp
0x1800264d1  sub     rsp, 20h
0x1800264d5  mov     rcx, cs:__security_cookie
0x1800264dc  xor     eax, eax
0x1800264de  mov     [rbp+arg_0], rax
0x1800264e2  mov     rbx, 2B992DDFA232h
0x1800264ec  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800264f0  mov     qword ptr [rbp+PerformanceCount], rax
0x1800264f4  test    rcx, rcx
0x1800264f7  jz      short loc_180026502
0x1800264f9  cmp     rcx, rbx
0x1800264fc  jnz     loc_180026587
0x180026502  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180026506  call    cs:__imp_GetSystemTimeAsFileTime
0x18002650c  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180026510  mov     [rbp+arg_0], rax
0x180026514  call    cs:__imp_GetCurrentProcessId
0x18002651a  mov     eax, eax
0x18002651c  xor     [rbp+arg_0], rax
0x180026520  call    cs:__imp_GetCurrentThreadId
0x180026526  mov     eax, eax
0x180026528  xor     [rbp+arg_0], rax
0x18002652c  call    cs:__imp_GetTickCount
0x180026532  mov     eax, eax
0x180026534  shl     rax, 18h
0x180026538  xor     [rbp+arg_0], rax
0x18002653c  call    cs:__imp_GetTickCount
0x180026542  mov     eax, eax
0x180026544  lea     rcx, [rbp+arg_0]
0x180026548  xor     rax, [rbp+arg_0]
0x18002654c  xor     rax, rcx
0x18002654f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180026553  mov     [rbp+arg_0], rax
0x180026557  call    cs:__imp_QueryPerformanceCounter
0x18002655d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180026560  mov     rcx, 0FFFFFFFFFFFFh
0x18002656a  shl     rax, 20h
0x18002656e  xor     rax, qword ptr [rbp+PerformanceCount]
0x180026572  xor     rax, [rbp+arg_0]
0x180026576  and     rax, rcx
0x180026579  mov     rcx, rbx
0x18002657c  cmovnz  rcx, rax
0x180026580  mov     cs:__security_cookie, rcx
0x180026587  mov     rbx, [rsp+20h+arg_18]
0x18002658c  not     rcx
0x18002658f  mov     cs:__security_cookie_complement, rcx
0x180026596  add     rsp, 20h
0x18002659a  pop     rbp
0x18002659b  retn
```
