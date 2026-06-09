# __security_init_cookie

- ea: `0x1800057cc`
- end: `0x18000587d`
- name: `__security_init_cookie`
- size: `177`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005350`

## callees

- `0x1800057cc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180005817`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000580b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000580b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005827`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180005827`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800057fd`

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
0x1800057cc  mov     [rsp-8+arg_10], rbx
0x1800057d1  push    rbp
0x1800057d2  mov     rbp, rsp
0x1800057d5  sub     rsp, 30h
0x1800057d9  mov     rax, cs:__security_cookie
0x1800057e0  mov     rbx, 2B992DDFA232h
0x1800057ea  cmp     rax, rbx
0x1800057ed  jnz     short loc_180005868
0x1800057ef  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800057f4  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800057f8  and     qword ptr [rbp+PerformanceCount], 0
0x1800057fd  call    cs:__imp_GetSystemTimeAsFileTime
0x180005803  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180005807  mov     [rbp+var_10], rax
0x18000580b  call    cs:__imp_GetCurrentThreadId
0x180005811  mov     eax, eax
0x180005813  xor     [rbp+var_10], rax
0x180005817  call    cs:__imp_GetCurrentProcessId
0x18000581d  mov     eax, eax
0x18000581f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180005823  xor     [rbp+var_10], rax
0x180005827  call    cs:__imp_QueryPerformanceCounter
0x18000582d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180005830  lea     rcx, [rbp+var_10]
0x180005834  shl     rax, 20h
0x180005838  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000583c  xor     rax, [rbp+var_10]
0x180005840  xor     rax, rcx
0x180005843  mov     rcx, 0FFFFFFFFFFFFh
0x18000584d  and     rax, rcx
0x180005850  mov     rcx, 2B992DDFA233h
0x18000585a  cmp     rax, rbx
0x18000585d  cmovz   rax, rcx
0x180005861  mov     cs:__security_cookie, rax
0x180005868  mov     rbx, [rsp+30h+arg_10]
0x18000586d  not     rax
0x180005870  mov     cs:__security_cookie_complement, rax
0x180005877  add     rsp, 30h
0x18000587b  pop     rbp
0x18000587c  retn
```
