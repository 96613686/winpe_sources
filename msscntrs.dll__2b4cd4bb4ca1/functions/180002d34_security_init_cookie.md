# __security_init_cookie

- ea: `0x180002d34`
- end: `0x180002de9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180002440`

## callees

- `0x180002d34`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002d77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002d83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002d83`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002d93`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180002d93`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002d69`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180002d69`

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
0x180002d34  mov     [rsp-8+arg_10], rbx
0x180002d39  push    rbp
0x180002d3a  mov     rbp, rsp
0x180002d3d  sub     rsp, 30h
0x180002d41  mov     rax, cs:__security_cookie
0x180002d48  mov     rbx, 2B992DDFA232h
0x180002d52  cmp     rax, rbx
0x180002d55  jnz     short loc_180002DD4
0x180002d57  xor     eax, eax
0x180002d59  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180002d5d  mov     [rbp+var_10], rax
0x180002d61  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180002d65  mov     qword ptr [rbp+PerformanceCount], rax
0x180002d69  call    cs:__imp_GetSystemTimeAsFileTime
0x180002d6f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180002d73  mov     [rbp+var_10], rax
0x180002d77  call    cs:__imp_GetCurrentThreadId
0x180002d7d  mov     eax, eax
0x180002d7f  xor     [rbp+var_10], rax
0x180002d83  call    cs:__imp_GetCurrentProcessId
0x180002d89  mov     eax, eax
0x180002d8b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180002d8f  xor     [rbp+var_10], rax
0x180002d93  call    cs:__imp_QueryPerformanceCounter
0x180002d99  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002d9c  lea     rcx, [rbp+var_10]
0x180002da0  shl     rax, 20h
0x180002da4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002da8  xor     rax, [rbp+var_10]
0x180002dac  xor     rax, rcx
0x180002daf  mov     rcx, 0FFFFFFFFFFFFh
0x180002db9  and     rax, rcx
0x180002dbc  mov     rcx, 2B992DDFA233h
0x180002dc6  cmp     rax, rbx
0x180002dc9  cmovz   rax, rcx
0x180002dcd  mov     cs:__security_cookie, rax
0x180002dd4  mov     rbx, [rsp+30h+arg_10]
0x180002dd9  not     rax
0x180002ddc  mov     cs:__security_cookie_complement, rax
0x180002de3  add     rsp, 30h
0x180002de7  pop     rbp
0x180002de8  retn
```
