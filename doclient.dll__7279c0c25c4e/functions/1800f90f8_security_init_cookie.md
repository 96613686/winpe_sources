# __security_init_cookie

- ea: `0x1800f90f8`
- end: `0x1800f91af`
- name: `__security_init_cookie`
- size: `183`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f8ac0`

## callees

- `0x1800f90f8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f913d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f913d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f9149`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800f9149`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f912f`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800f912f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f9159`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800f9159`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v1
        ^ *(_QWORD *)&v1
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1800f90f8  mov     [rsp-8+arg_10], rbx
0x1800f90fd  push    rbp
0x1800f90fe  mov     rbp, rsp
0x1800f9101  sub     rsp, 30h
0x1800f9105  mov     rax, cs:__security_cookie
0x1800f910c  mov     rbx, 2B992DDFA232h
0x1800f9116  cmp     rax, rbx
0x1800f9119  jnz     short loc_1800F919A
0x1800f911b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800f911f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800f9127  mov     qword ptr [rbp+PerformanceCount], 0
0x1800f912f  call    cs:__imp_GetSystemTimeAsFileTime
0x1800f9135  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800f9139  mov     [rbp+var_10], rax
0x1800f913d  call    cs:__imp_GetCurrentThreadId
0x1800f9143  mov     eax, eax
0x1800f9145  xor     [rbp+var_10], rax
0x1800f9149  call    cs:__imp_GetCurrentProcessId
0x1800f914f  mov     eax, eax
0x1800f9151  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800f9155  xor     [rbp+var_10], rax
0x1800f9159  call    cs:__imp_QueryPerformanceCounter
0x1800f915f  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800f9162  lea     rcx, [rbp+var_10]
0x1800f9166  shl     rax, 20h
0x1800f916a  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800f916e  xor     rax, [rbp+var_10]
0x1800f9172  xor     rax, rcx
0x1800f9175  mov     rcx, 0FFFFFFFFFFFFh
0x1800f917f  and     rax, rcx
0x1800f9182  mov     rcx, 2B992DDFA233h
0x1800f918c  cmp     rax, rbx
0x1800f918f  cmovz   rax, rcx
0x1800f9193  mov     cs:__security_cookie, rax
0x1800f919a  mov     rbx, [rsp+30h+arg_10]
0x1800f919f  not     rax
0x1800f91a2  mov     cs:__security_cookie_complement, rax
0x1800f91a9  add     rsp, 30h
0x1800f91ad  pop     rbp
0x1800f91ae  retn
```
