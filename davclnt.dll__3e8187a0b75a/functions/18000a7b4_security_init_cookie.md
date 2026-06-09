# __security_init_cookie

- ea: `0x18000a7b4`
- end: `0x18000a891`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a270`

## callees

- `0x18000a7b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a7fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000a7fb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a83e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000a83e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a813`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a813`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18000a823`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a7ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000a7ed`

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
0x18000a7b4  mov     [rsp-8+arg_18], rbx
0x18000a7b9  push    rbp
0x18000a7ba  mov     rbp, rsp
0x18000a7bd  sub     rsp, 20h
0x18000a7c1  xor     eax, eax
0x18000a7c3  mov     rbx, 2B992DDFA232h
0x18000a7cd  mov     [rbp+arg_0], rax
0x18000a7d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000a7d5  mov     qword ptr [rbp+PerformanceCount], rax
0x18000a7d9  mov     rax, cs:__security_cookie
0x18000a7e0  cmp     rax, rbx
0x18000a7e3  jnz     loc_18000A87C
0x18000a7e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000a7ed  call    cs:__imp_GetSystemTimeAsFileTime
0x18000a7f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000a7f7  mov     [rbp+arg_0], rax
0x18000a7fb  call    cs:__imp_GetCurrentProcessId
0x18000a801  mov     eax, eax
0x18000a803  xor     [rbp+arg_0], rax
0x18000a807  call    cs:__imp_GetCurrentThreadId
0x18000a80d  mov     eax, eax
0x18000a80f  xor     [rbp+arg_0], rax
0x18000a813  call    cs:__imp_GetTickCount
0x18000a819  mov     eax, eax
0x18000a81b  shl     rax, 18h
0x18000a81f  xor     [rbp+arg_0], rax
0x18000a823  call    cs:__imp_GetTickCount
0x18000a829  mov     eax, eax
0x18000a82b  lea     rcx, [rbp+arg_0]
0x18000a82f  xor     rax, [rbp+arg_0]
0x18000a833  xor     rax, rcx
0x18000a836  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000a83a  mov     [rbp+arg_0], rax
0x18000a83e  call    cs:__imp_QueryPerformanceCounter
0x18000a844  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000a847  mov     rcx, 0FFFFFFFFFFFFh
0x18000a851  shl     rax, 20h
0x18000a855  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000a859  xor     rax, [rbp+arg_0]
0x18000a85d  and     rax, rcx
0x18000a860  mov     rcx, rax
0x18000a863  cmp     rax, rbx
0x18000a866  jnz     short loc_18000A875
0x18000a868  mov     rax, 2B992DDFA233h
0x18000a872  mov     rcx, rax
0x18000a875  mov     cs:__security_cookie, rcx
0x18000a87c  mov     rbx, [rsp+20h+arg_18]
0x18000a881  not     rax
0x18000a884  mov     cs:__security_cookie_complement, rax
0x18000a88b  add     rsp, 20h
0x18000a88f  pop     rbp
0x18000a890  retn
```
