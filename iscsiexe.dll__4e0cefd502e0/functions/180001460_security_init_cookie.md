# __security_init_cookie

- ea: `0x180001460`
- end: `0x180001515`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800013c0`

## callees

- `0x180001460`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800014af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800014a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001495`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001495`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014bf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800014bf`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x180001460  mov     [rsp-8+arg_10], rbx
0x180001465  push    rbp
0x180001466  mov     rbp, rsp
0x180001469  sub     rsp, 30h
0x18000146d  mov     rax, cs:__security_cookie
0x180001474  mov     rbx, 2B992DDFA232h
0x18000147e  cmp     rax, rbx
0x180001481  jnz     short loc_180001500
0x180001483  xor     eax, eax
0x180001485  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001489  mov     [rbp+var_10], rax
0x18000148d  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001491  mov     qword ptr [rbp+PerformanceCount], rax
0x180001495  call    cs:__imp_GetSystemTimeAsFileTime
0x18000149b  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000149f  mov     [rbp+var_10], rax
0x1800014a3  call    cs:__imp_GetCurrentThreadId
0x1800014a9  mov     eax, eax
0x1800014ab  xor     [rbp+var_10], rax
0x1800014af  call    cs:__imp_GetCurrentProcessId
0x1800014b5  mov     eax, eax
0x1800014b7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800014bb  xor     [rbp+var_10], rax
0x1800014bf  call    cs:__imp_QueryPerformanceCounter
0x1800014c5  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800014c8  lea     rcx, [rbp+var_10]
0x1800014cc  shl     rax, 20h
0x1800014d0  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800014d4  xor     rax, [rbp+var_10]
0x1800014d8  xor     rax, rcx
0x1800014db  mov     rcx, 0FFFFFFFFFFFFh
0x1800014e5  and     rax, rcx
0x1800014e8  mov     rcx, 2B992DDFA233h
0x1800014f2  cmp     rax, rbx
0x1800014f5  cmovz   rax, rcx
0x1800014f9  mov     cs:__security_cookie, rax
0x180001500  mov     rbx, [rsp+30h+arg_10]
0x180001505  not     rax
0x180001508  mov     cs:__security_cookie_complement, rax
0x18000150f  add     rsp, 30h
0x180001513  pop     rbp
0x180001514  retn
```
