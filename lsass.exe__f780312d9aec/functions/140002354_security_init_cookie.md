# __security_init_cookie

- ea: `0x140002354`
- end: `0x140002409`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002090`

## callees

- `0x140002354`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002397`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400023a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400023a3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002389`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140002389`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400023b3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400023b3`

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
0x140002354  mov     [rsp-8+arg_10], rbx
0x140002359  push    rbp
0x14000235a  mov     rbp, rsp
0x14000235d  sub     rsp, 30h
0x140002361  mov     rax, cs:__security_cookie
0x140002368  mov     rbx, 2B992DDFA232h
0x140002372  cmp     rax, rbx
0x140002375  jnz     short loc_1400023F4
0x140002377  xor     eax, eax
0x140002379  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x14000237d  mov     [rbp+var_10], rax
0x140002381  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140002385  mov     qword ptr [rbp+PerformanceCount], rax
0x140002389  call    cs:__imp_GetSystemTimeAsFileTime
0x14000238f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002393  mov     [rbp+var_10], rax
0x140002397  call    cs:__imp_GetCurrentThreadId
0x14000239d  mov     eax, eax
0x14000239f  xor     [rbp+var_10], rax
0x1400023a3  call    cs:__imp_GetCurrentProcessId
0x1400023a9  mov     eax, eax
0x1400023ab  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400023af  xor     [rbp+var_10], rax
0x1400023b3  call    cs:__imp_QueryPerformanceCounter
0x1400023b9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400023bc  lea     rcx, [rbp+var_10]
0x1400023c0  shl     rax, 20h
0x1400023c4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1400023c8  xor     rax, [rbp+var_10]
0x1400023cc  xor     rax, rcx
0x1400023cf  mov     rcx, 0FFFFFFFFFFFFh
0x1400023d9  and     rax, rcx
0x1400023dc  mov     rcx, 2B992DDFA233h
0x1400023e6  cmp     rax, rbx
0x1400023e9  cmovz   rax, rcx
0x1400023ed  mov     cs:__security_cookie, rax
0x1400023f4  mov     rbx, [rsp+30h+arg_10]
0x1400023f9  not     rax
0x1400023fc  mov     cs:__security_cookie_complement, rax
0x140002403  add     rsp, 30h
0x140002407  pop     rbp
0x140002408  retn
```
