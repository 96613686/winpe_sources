# __security_init_cookie

- ea: `0x180001bb0`
- end: `0x180001c65`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001730`

## callees

- `0x180001bb0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001bf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001bf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001bff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001bff`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001be5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001be5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c0f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001c0f`

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
0x180001bb0  mov     [rsp-8+arg_10], rbx
0x180001bb5  push    rbp
0x180001bb6  mov     rbp, rsp
0x180001bb9  sub     rsp, 30h
0x180001bbd  mov     rax, cs:__security_cookie
0x180001bc4  mov     rbx, 2B992DDFA232h
0x180001bce  cmp     rax, rbx
0x180001bd1  jnz     short loc_180001C50
0x180001bd3  xor     eax, eax
0x180001bd5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001bd9  mov     [rbp+var_10], rax
0x180001bdd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001be1  mov     qword ptr [rbp+PerformanceCount], rax
0x180001be5  call    cs:__imp_GetSystemTimeAsFileTime
0x180001beb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001bef  mov     [rbp+var_10], rax
0x180001bf3  call    cs:__imp_GetCurrentThreadId
0x180001bf9  mov     eax, eax
0x180001bfb  xor     [rbp+var_10], rax
0x180001bff  call    cs:__imp_GetCurrentProcessId
0x180001c05  mov     eax, eax
0x180001c07  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001c0b  xor     [rbp+var_10], rax
0x180001c0f  call    cs:__imp_QueryPerformanceCounter
0x180001c15  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001c18  lea     rcx, [rbp+var_10]
0x180001c1c  shl     rax, 20h
0x180001c20  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001c24  xor     rax, [rbp+var_10]
0x180001c28  xor     rax, rcx
0x180001c2b  mov     rcx, 0FFFFFFFFFFFFh
0x180001c35  and     rax, rcx
0x180001c38  mov     rcx, 2B992DDFA233h
0x180001c42  cmp     rax, rbx
0x180001c45  cmovz   rax, rcx
0x180001c49  mov     cs:__security_cookie, rax
0x180001c50  mov     rbx, [rsp+30h+arg_10]
0x180001c55  not     rax
0x180001c58  mov     cs:__security_cookie_complement, rax
0x180001c5f  add     rsp, 30h
0x180001c63  pop     rbp
0x180001c64  retn
```
