# __security_init_cookie

- ea: `0x180057954`
- end: `0x180057a31`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057180`

## callees

- `0x180057954`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800579a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800579a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005799b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18005799b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800579de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800579de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005798d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18005798d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800579b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800579c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800579b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800579c3`

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
0x180057954  mov     [rsp-8+arg_18], rbx
0x180057959  push    rbp
0x18005795a  mov     rbp, rsp
0x18005795d  sub     rsp, 20h
0x180057961  xor     eax, eax
0x180057963  mov     rbx, 2B992DDFA232h
0x18005796d  mov     [rbp+arg_0], rax
0x180057971  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180057975  mov     qword ptr [rbp+PerformanceCount], rax
0x180057979  mov     rax, cs:__security_cookie
0x180057980  cmp     rax, rbx
0x180057983  jnz     loc_180057A1C
0x180057989  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005798d  call    cs:__imp_GetSystemTimeAsFileTime
0x180057993  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180057997  mov     [rbp+arg_0], rax
0x18005799b  call    cs:__imp_GetCurrentProcessId
0x1800579a1  mov     eax, eax
0x1800579a3  xor     [rbp+arg_0], rax
0x1800579a7  call    cs:__imp_GetCurrentThreadId
0x1800579ad  mov     eax, eax
0x1800579af  xor     [rbp+arg_0], rax
0x1800579b3  call    cs:__imp_GetTickCount
0x1800579b9  mov     eax, eax
0x1800579bb  shl     rax, 18h
0x1800579bf  xor     [rbp+arg_0], rax
0x1800579c3  call    cs:__imp_GetTickCount
0x1800579c9  mov     eax, eax
0x1800579cb  lea     rcx, [rbp+arg_0]
0x1800579cf  xor     rax, [rbp+arg_0]
0x1800579d3  xor     rax, rcx
0x1800579d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800579da  mov     [rbp+arg_0], rax
0x1800579de  call    cs:__imp_QueryPerformanceCounter
0x1800579e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800579e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800579f1  shl     rax, 20h
0x1800579f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800579f9  xor     rax, [rbp+arg_0]
0x1800579fd  and     rax, rcx
0x180057a00  mov     rcx, rax
0x180057a03  cmp     rax, rbx
0x180057a06  jnz     short loc_180057A15
0x180057a08  mov     rax, 2B992DDFA233h
0x180057a12  mov     rcx, rax
0x180057a15  mov     cs:__security_cookie, rcx
0x180057a1c  mov     rbx, [rsp+20h+arg_18]
0x180057a21  not     rax
0x180057a24  mov     cs:__security_cookie_complement, rax
0x180057a2b  add     rsp, 20h
0x180057a2f  pop     rbp
0x180057a30  retn
```
