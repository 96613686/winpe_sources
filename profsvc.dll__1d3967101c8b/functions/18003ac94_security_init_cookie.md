# __security_init_cookie

- ea: `0x18003ac94`
- end: `0x18003ad49`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003a6e0`

## callees

- `0x18003ac94`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ace3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18003ace3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003acd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003acd7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003acc9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18003acc9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003acf3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18003acf3`

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
0x18003ac94  mov     [rsp-8+arg_10], rbx
0x18003ac99  push    rbp
0x18003ac9a  mov     rbp, rsp
0x18003ac9d  sub     rsp, 30h
0x18003aca1  mov     rax, cs:__security_cookie
0x18003aca8  mov     rbx, 2B992DDFA232h
0x18003acb2  cmp     rax, rbx
0x18003acb5  jnz     short loc_18003AD34
0x18003acb7  xor     eax, eax
0x18003acb9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18003acbd  mov     [rbp+var_10], rax
0x18003acc1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18003acc5  mov     qword ptr [rbp+PerformanceCount], rax
0x18003acc9  call    cs:__imp_GetSystemTimeAsFileTime
0x18003accf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18003acd3  mov     [rbp+var_10], rax
0x18003acd7  call    cs:__imp_GetCurrentThreadId
0x18003acdd  mov     eax, eax
0x18003acdf  xor     [rbp+var_10], rax
0x18003ace3  call    cs:__imp_GetCurrentProcessId
0x18003ace9  mov     eax, eax
0x18003aceb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18003acef  xor     [rbp+var_10], rax
0x18003acf3  call    cs:__imp_QueryPerformanceCounter
0x18003acf9  mov     eax, dword ptr [rbp+PerformanceCount]
0x18003acfc  lea     rcx, [rbp+var_10]
0x18003ad00  shl     rax, 20h
0x18003ad04  xor     rax, qword ptr [rbp+PerformanceCount]
0x18003ad08  xor     rax, [rbp+var_10]
0x18003ad0c  xor     rax, rcx
0x18003ad0f  mov     rcx, 0FFFFFFFFFFFFh
0x18003ad19  and     rax, rcx
0x18003ad1c  mov     rcx, 2B992DDFA233h
0x18003ad26  cmp     rax, rbx
0x18003ad29  cmovz   rax, rcx
0x18003ad2d  mov     cs:__security_cookie, rax
0x18003ad34  mov     rbx, [rsp+30h+arg_10]
0x18003ad39  not     rax
0x18003ad3c  mov     cs:__security_cookie_complement, rax
0x18003ad43  add     rsp, 30h
0x18003ad47  pop     rbp
0x18003ad48  retn
```
