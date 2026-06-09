# __security_init_cookie

- ea: `0x180011bd4`
- end: `0x180011cb1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800113a0`

## callees

- `0x180011bd4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180011c1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011c27`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011c5e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180011c5e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011c0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180011c0d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c33`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180011c43`

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
0x180011bd4  mov     [rsp-8+arg_18], rbx
0x180011bd9  push    rbp
0x180011bda  mov     rbp, rsp
0x180011bdd  sub     rsp, 20h
0x180011be1  xor     eax, eax
0x180011be3  mov     rbx, 2B992DDFA232h
0x180011bed  mov     [rbp+arg_0], rax
0x180011bf1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180011bf5  mov     qword ptr [rbp+PerformanceCount], rax
0x180011bf9  mov     rax, cs:__security_cookie
0x180011c00  cmp     rax, rbx
0x180011c03  jnz     loc_180011C9C
0x180011c09  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180011c0d  call    cs:__imp_GetSystemTimeAsFileTime
0x180011c13  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180011c17  mov     [rbp+arg_0], rax
0x180011c1b  call    cs:__imp_GetCurrentProcessId
0x180011c21  mov     eax, eax
0x180011c23  xor     [rbp+arg_0], rax
0x180011c27  call    cs:__imp_GetCurrentThreadId
0x180011c2d  mov     eax, eax
0x180011c2f  xor     [rbp+arg_0], rax
0x180011c33  call    cs:__imp_GetTickCount
0x180011c39  mov     eax, eax
0x180011c3b  shl     rax, 18h
0x180011c3f  xor     [rbp+arg_0], rax
0x180011c43  call    cs:__imp_GetTickCount
0x180011c49  mov     eax, eax
0x180011c4b  lea     rcx, [rbp+arg_0]
0x180011c4f  xor     rax, [rbp+arg_0]
0x180011c53  xor     rax, rcx
0x180011c56  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180011c5a  mov     [rbp+arg_0], rax
0x180011c5e  call    cs:__imp_QueryPerformanceCounter
0x180011c64  mov     eax, dword ptr [rbp+PerformanceCount]
0x180011c67  mov     rcx, 0FFFFFFFFFFFFh
0x180011c71  shl     rax, 20h
0x180011c75  xor     rax, qword ptr [rbp+PerformanceCount]
0x180011c79  xor     rax, [rbp+arg_0]
0x180011c7d  and     rax, rcx
0x180011c80  mov     rcx, rax
0x180011c83  cmp     rax, rbx
0x180011c86  jnz     short loc_180011C95
0x180011c88  mov     rax, 2B992DDFA233h
0x180011c92  mov     rcx, rax
0x180011c95  mov     cs:__security_cookie, rcx
0x180011c9c  mov     rbx, [rsp+20h+arg_18]
0x180011ca1  not     rax
0x180011ca4  mov     cs:__security_cookie_complement, rax
0x180011cab  add     rsp, 20h
0x180011caf  pop     rbp
0x180011cb0  retn
```
