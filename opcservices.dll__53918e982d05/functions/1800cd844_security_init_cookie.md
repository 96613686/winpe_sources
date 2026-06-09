# __security_init_cookie

- ea: `0x1800cd844`
- end: `0x1800cd921`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800cd450`

## callees

- `0x1800cd844`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cd8ce`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800cd8ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cd88b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800cd88b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800cd897`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd8a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd8b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd8a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800cd8b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd87d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800cd87d`

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
0x1800cd844  mov     [rsp-8+arg_18], rbx
0x1800cd849  push    rbp
0x1800cd84a  mov     rbp, rsp
0x1800cd84d  sub     rsp, 20h
0x1800cd851  xor     eax, eax
0x1800cd853  mov     rbx, 2B992DDFA232h
0x1800cd85d  mov     [rbp+arg_0], rax
0x1800cd861  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800cd865  mov     qword ptr [rbp+PerformanceCount], rax
0x1800cd869  mov     rax, cs:__security_cookie
0x1800cd870  cmp     rax, rbx
0x1800cd873  jnz     loc_1800CD90C
0x1800cd879  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800cd87d  call    cs:__imp_GetSystemTimeAsFileTime
0x1800cd883  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800cd887  mov     [rbp+arg_0], rax
0x1800cd88b  call    cs:__imp_GetCurrentProcessId
0x1800cd891  mov     eax, eax
0x1800cd893  xor     [rbp+arg_0], rax
0x1800cd897  call    cs:__imp_GetCurrentThreadId
0x1800cd89d  mov     eax, eax
0x1800cd89f  xor     [rbp+arg_0], rax
0x1800cd8a3  call    cs:__imp_GetTickCount
0x1800cd8a9  mov     eax, eax
0x1800cd8ab  shl     rax, 18h
0x1800cd8af  xor     [rbp+arg_0], rax
0x1800cd8b3  call    cs:__imp_GetTickCount
0x1800cd8b9  mov     eax, eax
0x1800cd8bb  lea     rcx, [rbp+arg_0]
0x1800cd8bf  xor     rax, [rbp+arg_0]
0x1800cd8c3  xor     rax, rcx
0x1800cd8c6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800cd8ca  mov     [rbp+arg_0], rax
0x1800cd8ce  call    cs:__imp_QueryPerformanceCounter
0x1800cd8d4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800cd8d7  mov     rcx, 0FFFFFFFFFFFFh
0x1800cd8e1  shl     rax, 20h
0x1800cd8e5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800cd8e9  xor     rax, [rbp+arg_0]
0x1800cd8ed  and     rax, rcx
0x1800cd8f0  mov     rcx, rax
0x1800cd8f3  cmp     rax, rbx
0x1800cd8f6  jnz     short loc_1800CD905
0x1800cd8f8  mov     rax, 2B992DDFA233h
0x1800cd902  mov     rcx, rax
0x1800cd905  mov     cs:__security_cookie, rcx
0x1800cd90c  mov     rbx, [rsp+20h+arg_18]
0x1800cd911  not     rax
0x1800cd914  mov     cs:__security_cookie_complement, rax
0x1800cd91b  add     rsp, 20h
0x1800cd91f  pop     rbp
0x1800cd920  retn
```
