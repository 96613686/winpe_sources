# __security_init_cookie

- ea: `0x1800524f4`
- end: `0x1800525a9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180051ed0`

## callees

- `0x1800524f4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180052537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052543`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180052543`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180052529`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180052529`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180052553`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180052553`

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
0x1800524f4  mov     [rsp-8+arg_10], rbx
0x1800524f9  push    rbp
0x1800524fa  mov     rbp, rsp
0x1800524fd  sub     rsp, 30h
0x180052501  mov     rax, cs:__security_cookie
0x180052508  mov     rbx, 2B992DDFA232h
0x180052512  cmp     rax, rbx
0x180052515  jnz     short loc_180052594
0x180052517  xor     eax, eax
0x180052519  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005251d  mov     [rbp+var_10], rax
0x180052521  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180052525  mov     qword ptr [rbp+PerformanceCount], rax
0x180052529  call    cs:__imp_GetSystemTimeAsFileTime
0x18005252f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180052533  mov     [rbp+var_10], rax
0x180052537  call    cs:__imp_GetCurrentThreadId
0x18005253d  mov     eax, eax
0x18005253f  xor     [rbp+var_10], rax
0x180052543  call    cs:__imp_GetCurrentProcessId
0x180052549  mov     eax, eax
0x18005254b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18005254f  xor     [rbp+var_10], rax
0x180052553  call    cs:__imp_QueryPerformanceCounter
0x180052559  mov     eax, dword ptr [rbp+PerformanceCount]
0x18005255c  lea     rcx, [rbp+var_10]
0x180052560  shl     rax, 20h
0x180052564  xor     rax, qword ptr [rbp+PerformanceCount]
0x180052568  xor     rax, [rbp+var_10]
0x18005256c  xor     rax, rcx
0x18005256f  mov     rcx, 0FFFFFFFFFFFFh
0x180052579  and     rax, rcx
0x18005257c  mov     rcx, 2B992DDFA233h
0x180052586  cmp     rax, rbx
0x180052589  cmovz   rax, rcx
0x18005258d  mov     cs:__security_cookie, rax
0x180052594  mov     rbx, [rsp+30h+arg_10]
0x180052599  not     rax
0x18005259c  mov     cs:__security_cookie_complement, rax
0x1800525a3  add     rsp, 30h
0x1800525a7  pop     rbp
0x1800525a8  retn
```
