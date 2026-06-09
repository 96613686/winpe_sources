# __security_init_cookie

- ea: `0x180019be4`
- end: `0x180019cc1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180019820`

## callees

- `0x180019be4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180019c2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019c37`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019c1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180019c1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019c43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019c53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019c43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180019c53`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019c6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180019c6e`

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
0x180019be4  mov     [rsp-8+arg_18], rbx
0x180019be9  push    rbp
0x180019bea  mov     rbp, rsp
0x180019bed  sub     rsp, 20h
0x180019bf1  xor     eax, eax
0x180019bf3  mov     rbx, 2B992DDFA232h
0x180019bfd  mov     [rbp+arg_0], rax
0x180019c01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180019c05  mov     qword ptr [rbp+PerformanceCount], rax
0x180019c09  mov     rax, cs:__security_cookie
0x180019c10  cmp     rax, rbx
0x180019c13  jnz     loc_180019CAC
0x180019c19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180019c1d  call    cs:__imp_GetSystemTimeAsFileTime
0x180019c23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180019c27  mov     [rbp+arg_0], rax
0x180019c2b  call    cs:__imp_GetCurrentProcessId
0x180019c31  mov     eax, eax
0x180019c33  xor     [rbp+arg_0], rax
0x180019c37  call    cs:__imp_GetCurrentThreadId
0x180019c3d  mov     eax, eax
0x180019c3f  xor     [rbp+arg_0], rax
0x180019c43  call    cs:__imp_GetTickCount
0x180019c49  mov     eax, eax
0x180019c4b  shl     rax, 18h
0x180019c4f  xor     [rbp+arg_0], rax
0x180019c53  call    cs:__imp_GetTickCount
0x180019c59  mov     eax, eax
0x180019c5b  lea     rcx, [rbp+arg_0]
0x180019c5f  xor     rax, [rbp+arg_0]
0x180019c63  xor     rax, rcx
0x180019c66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180019c6a  mov     [rbp+arg_0], rax
0x180019c6e  call    cs:__imp_QueryPerformanceCounter
0x180019c74  mov     eax, dword ptr [rbp+PerformanceCount]
0x180019c77  mov     rcx, 0FFFFFFFFFFFFh
0x180019c81  shl     rax, 20h
0x180019c85  xor     rax, qword ptr [rbp+PerformanceCount]
0x180019c89  xor     rax, [rbp+arg_0]
0x180019c8d  and     rax, rcx
0x180019c90  mov     rcx, rax
0x180019c93  cmp     rax, rbx
0x180019c96  jnz     short loc_180019CA5
0x180019c98  mov     rax, 2B992DDFA233h
0x180019ca2  mov     rcx, rax
0x180019ca5  mov     cs:__security_cookie, rcx
0x180019cac  mov     rbx, [rsp+20h+arg_18]
0x180019cb1  not     rax
0x180019cb4  mov     cs:__security_cookie_complement, rax
0x180019cbb  add     rsp, 20h
0x180019cbf  pop     rbp
0x180019cc0  retn
```
