# __security_init_cookie

- ea: `0x180001b64`
- end: `0x180001c19`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180001a10`

## callees

- `0x180001b64`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001bb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180001bb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ba7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180001ba7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001bc3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180001bc3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b99`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180001b99`

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
0x180001b64  mov     [rsp-8+arg_10], rbx
0x180001b69  push    rbp
0x180001b6a  mov     rbp, rsp
0x180001b6d  sub     rsp, 30h
0x180001b71  mov     rax, cs:__security_cookie
0x180001b78  mov     rbx, 2B992DDFA232h
0x180001b82  cmp     rax, rbx
0x180001b85  jnz     short loc_180001C04
0x180001b87  xor     eax, eax
0x180001b89  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180001b8d  mov     [rbp+var_10], rax
0x180001b91  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180001b95  mov     qword ptr [rbp+PerformanceCount], rax
0x180001b99  call    cs:__imp_GetSystemTimeAsFileTime
0x180001b9f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180001ba3  mov     [rbp+var_10], rax
0x180001ba7  call    cs:__imp_GetCurrentThreadId
0x180001bad  mov     eax, eax
0x180001baf  xor     [rbp+var_10], rax
0x180001bb3  call    cs:__imp_GetCurrentProcessId
0x180001bb9  mov     eax, eax
0x180001bbb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180001bbf  xor     [rbp+var_10], rax
0x180001bc3  call    cs:__imp_QueryPerformanceCounter
0x180001bc9  mov     eax, dword ptr [rbp+PerformanceCount]
0x180001bcc  lea     rcx, [rbp+var_10]
0x180001bd0  shl     rax, 20h
0x180001bd4  xor     rax, qword ptr [rbp+PerformanceCount]
0x180001bd8  xor     rax, [rbp+var_10]
0x180001bdc  xor     rax, rcx
0x180001bdf  mov     rcx, 0FFFFFFFFFFFFh
0x180001be9  and     rax, rcx
0x180001bec  mov     rcx, 2B992DDFA233h
0x180001bf6  cmp     rax, rbx
0x180001bf9  cmovz   rax, rcx
0x180001bfd  mov     cs:__security_cookie, rax
0x180001c04  mov     rbx, [rsp+30h+arg_10]
0x180001c09  not     rax
0x180001c0c  mov     cs:__security_cookie_complement, rax
0x180001c13  add     rsp, 30h
0x180001c17  pop     rbp
0x180001c18  retn
```
