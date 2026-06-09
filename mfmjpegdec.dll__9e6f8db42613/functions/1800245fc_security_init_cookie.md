# __security_init_cookie

- ea: `0x1800245fc`
- end: `0x1800246b1`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800241d0`

## callees

- `0x1800245fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002463f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002463f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002464b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002464b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002465b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18002465b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024631`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180024631`

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
0x1800245fc  mov     [rsp-8+arg_10], rbx
0x180024601  push    rbp
0x180024602  mov     rbp, rsp
0x180024605  sub     rsp, 30h
0x180024609  mov     rax, cs:__security_cookie
0x180024610  mov     rbx, 2B992DDFA232h
0x18002461a  cmp     rax, rbx
0x18002461d  jnz     short loc_18002469C
0x18002461f  xor     eax, eax
0x180024621  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180024625  mov     [rbp+var_10], rax
0x180024629  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18002462d  mov     qword ptr [rbp+PerformanceCount], rax
0x180024631  call    cs:__imp_GetSystemTimeAsFileTime
0x180024637  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18002463b  mov     [rbp+var_10], rax
0x18002463f  call    cs:__imp_GetCurrentThreadId
0x180024645  mov     eax, eax
0x180024647  xor     [rbp+var_10], rax
0x18002464b  call    cs:__imp_GetCurrentProcessId
0x180024651  mov     eax, eax
0x180024653  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180024657  xor     [rbp+var_10], rax
0x18002465b  call    cs:__imp_QueryPerformanceCounter
0x180024661  mov     eax, dword ptr [rbp+PerformanceCount]
0x180024664  lea     rcx, [rbp+var_10]
0x180024668  shl     rax, 20h
0x18002466c  xor     rax, qword ptr [rbp+PerformanceCount]
0x180024670  xor     rax, [rbp+var_10]
0x180024674  xor     rax, rcx
0x180024677  mov     rcx, 0FFFFFFFFFFFFh
0x180024681  and     rax, rcx
0x180024684  mov     rcx, 2B992DDFA233h
0x18002468e  cmp     rax, rbx
0x180024691  cmovz   rax, rcx
0x180024695  mov     cs:__security_cookie, rax
0x18002469c  mov     rbx, [rsp+30h+arg_10]
0x1800246a1  not     rax
0x1800246a4  mov     cs:__security_cookie_complement, rax
0x1800246ab  add     rsp, 30h
0x1800246af  pop     rbp
0x1800246b0  retn
```
