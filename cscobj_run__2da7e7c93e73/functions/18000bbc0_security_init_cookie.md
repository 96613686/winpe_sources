# __security_init_cookie

- ea: `0x18000bbc0`
- end: `0x18000bc75`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000b770`

## callees

- `0x18000bbc0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bc0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000bc0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000bc03`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bbf5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000bbf5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000bc1f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000bc1f`

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
0x18000bbc0  mov     [rsp-8+arg_10], rbx
0x18000bbc5  push    rbp
0x18000bbc6  mov     rbp, rsp
0x18000bbc9  sub     rsp, 30h
0x18000bbcd  mov     rax, cs:__security_cookie
0x18000bbd4  mov     rbx, 2B992DDFA232h
0x18000bbde  cmp     rax, rbx
0x18000bbe1  jnz     short loc_18000BC60
0x18000bbe3  xor     eax, eax
0x18000bbe5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000bbe9  mov     [rbp+var_10], rax
0x18000bbed  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000bbf1  mov     qword ptr [rbp+PerformanceCount], rax
0x18000bbf5  call    cs:__imp_GetSystemTimeAsFileTime
0x18000bbfb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000bbff  mov     [rbp+var_10], rax
0x18000bc03  call    cs:__imp_GetCurrentThreadId
0x18000bc09  mov     eax, eax
0x18000bc0b  xor     [rbp+var_10], rax
0x18000bc0f  call    cs:__imp_GetCurrentProcessId
0x18000bc15  mov     eax, eax
0x18000bc17  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000bc1b  xor     [rbp+var_10], rax
0x18000bc1f  call    cs:__imp_QueryPerformanceCounter
0x18000bc25  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000bc28  lea     rcx, [rbp+var_10]
0x18000bc2c  shl     rax, 20h
0x18000bc30  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000bc34  xor     rax, [rbp+var_10]
0x18000bc38  xor     rax, rcx
0x18000bc3b  mov     rcx, 0FFFFFFFFFFFFh
0x18000bc45  and     rax, rcx
0x18000bc48  mov     rcx, 2B992DDFA233h
0x18000bc52  cmp     rax, rbx
0x18000bc55  cmovz   rax, rcx
0x18000bc59  mov     cs:__security_cookie, rax
0x18000bc60  mov     rbx, [rsp+30h+arg_10]
0x18000bc65  not     rax
0x18000bc68  mov     cs:__security_cookie_complement, rax
0x18000bc6f  add     rsp, 30h
0x18000bc73  pop     rbp
0x18000bc74  retn
```
