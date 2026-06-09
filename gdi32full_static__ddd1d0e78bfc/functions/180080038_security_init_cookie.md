# __security_init_cookie

- ea: `0x180080038`
- end: `0x1800800ed`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007fb44`

## callees

- `0x180080038`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008007b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18008007b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180080087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180080087`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008006d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18008006d`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180080097`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180080097`

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
0x180080038  mov     [rsp-8+arg_10], rbx
0x18008003d  push    rbp
0x18008003e  mov     rbp, rsp
0x180080041  sub     rsp, 30h
0x180080045  mov     rax, cs:__security_cookie
0x18008004c  mov     rbx, 2B992DDFA232h
0x180080056  cmp     rax, rbx
0x180080059  jnz     short loc_1800800D8
0x18008005b  xor     eax, eax
0x18008005d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180080061  mov     [rbp+var_10], rax
0x180080065  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180080069  mov     qword ptr [rbp+PerformanceCount], rax
0x18008006d  call    cs:__imp_GetSystemTimeAsFileTime
0x180080073  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180080077  mov     [rbp+var_10], rax
0x18008007b  call    cs:__imp_GetCurrentThreadId
0x180080081  mov     eax, eax
0x180080083  xor     [rbp+var_10], rax
0x180080087  call    cs:__imp_GetCurrentProcessId
0x18008008d  mov     eax, eax
0x18008008f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180080093  xor     [rbp+var_10], rax
0x180080097  call    cs:__imp_QueryPerformanceCounter
0x18008009d  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800800a0  lea     rcx, [rbp+var_10]
0x1800800a4  shl     rax, 20h
0x1800800a8  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800800ac  xor     rax, [rbp+var_10]
0x1800800b0  xor     rax, rcx
0x1800800b3  mov     rcx, 0FFFFFFFFFFFFh
0x1800800bd  and     rax, rcx
0x1800800c0  mov     rcx, 2B992DDFA233h
0x1800800ca  cmp     rax, rbx
0x1800800cd  cmovz   rax, rcx
0x1800800d1  mov     cs:__security_cookie, rax
0x1800800d8  mov     rbx, [rsp+30h+arg_10]
0x1800800dd  not     rax
0x1800800e0  mov     cs:__security_cookie_complement, rax
0x1800800e7  add     rsp, 30h
0x1800800eb  pop     rbp
0x1800800ec  retn
```
