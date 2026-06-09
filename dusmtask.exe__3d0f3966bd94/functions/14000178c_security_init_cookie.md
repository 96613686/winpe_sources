# __security_init_cookie

- ea: `0x14000178c`
- end: `0x140001841`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001440`

## callees

- `0x14000178c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400017db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1400017db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400017cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400017cf`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017eb`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1400017eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017c1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400017c1`

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
0x14000178c  mov     [rsp-8+arg_10], rbx
0x140001791  push    rbp
0x140001792  mov     rbp, rsp
0x140001795  sub     rsp, 30h
0x140001799  mov     rax, cs:__security_cookie
0x1400017a0  mov     rbx, 2B992DDFA232h
0x1400017aa  cmp     rax, rbx
0x1400017ad  jnz     short loc_14000182C
0x1400017af  xor     eax, eax
0x1400017b1  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400017b5  mov     [rbp+var_10], rax
0x1400017b9  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400017bd  mov     qword ptr [rbp+PerformanceCount], rax
0x1400017c1  call    cs:__imp_GetSystemTimeAsFileTime
0x1400017c7  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1400017cb  mov     [rbp+var_10], rax
0x1400017cf  call    cs:__imp_GetCurrentThreadId
0x1400017d5  mov     eax, eax
0x1400017d7  xor     [rbp+var_10], rax
0x1400017db  call    cs:__imp_GetCurrentProcessId
0x1400017e1  mov     eax, eax
0x1400017e3  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1400017e7  xor     [rbp+var_10], rax
0x1400017eb  call    cs:__imp_QueryPerformanceCounter
0x1400017f1  mov     eax, dword ptr [rbp+PerformanceCount]
0x1400017f4  lea     rcx, [rbp+var_10]
0x1400017f8  shl     rax, 20h
0x1400017fc  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001800  xor     rax, [rbp+var_10]
0x140001804  xor     rax, rcx
0x140001807  mov     rcx, 0FFFFFFFFFFFFh
0x140001811  and     rax, rcx
0x140001814  mov     rcx, 2B992DDFA233h
0x14000181e  cmp     rax, rbx
0x140001821  cmovz   rax, rcx
0x140001825  mov     cs:__security_cookie, rax
0x14000182c  mov     rbx, [rsp+30h+arg_10]
0x140001831  not     rax
0x140001834  mov     cs:__security_cookie_complement, rax
0x14000183b  add     rsp, 30h
0x14000183f  pop     rbp
0x140001840  retn
```
