# __security_init_cookie

- ea: `0x180033ba0`
- end: `0x180033c7d`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800079e0`

## callees

- `0x180033ba0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033be7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180033be7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033bf3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180033bf3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180033c2a`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180033c2a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033bd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180033bd9`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033bff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033c0f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033bff`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180033c0f`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  struct _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (struct _FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
    QueryPerformanceCounter(&PerformanceCount);
    v0 = (*(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    v1 = v0;
    if ( v0 == 0x2B992DDFA232LL )
    {
      v0 = 0x2B992DDFA233LL;
      v1 = 0x2B992DDFA233LL;
    }
    _security_cookie = v1;
  }
  _security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x180033ba0  mov     [rsp-8+arg_18], rbx
0x180033ba5  push    rbp
0x180033ba6  mov     rbp, rsp
0x180033ba9  sub     rsp, 20h
0x180033bad  xor     eax, eax
0x180033baf  mov     rbx, 2B992DDFA232h
0x180033bb9  mov     [rbp+arg_0], rax
0x180033bbd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180033bc1  mov     qword ptr [rbp+PerformanceCount], rax
0x180033bc5  mov     rax, cs:__security_cookie
0x180033bcc  cmp     rax, rbx
0x180033bcf  jnz     loc_180033C68
0x180033bd5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180033bd9  call    cs:__imp_GetSystemTimeAsFileTime
0x180033bdf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180033be3  mov     [rbp+arg_0], rax
0x180033be7  call    cs:__imp_GetCurrentProcessId
0x180033bed  mov     eax, eax
0x180033bef  xor     [rbp+arg_0], rax
0x180033bf3  call    cs:__imp_GetCurrentThreadId
0x180033bf9  mov     eax, eax
0x180033bfb  xor     [rbp+arg_0], rax
0x180033bff  call    cs:__imp_GetTickCount
0x180033c05  mov     eax, eax
0x180033c07  shl     rax, 18h
0x180033c0b  xor     [rbp+arg_0], rax
0x180033c0f  call    cs:__imp_GetTickCount
0x180033c15  mov     eax, eax
0x180033c17  lea     rcx, [rbp+arg_0]
0x180033c1b  xor     rax, [rbp+arg_0]
0x180033c1f  xor     rax, rcx
0x180033c22  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180033c26  mov     [rbp+arg_0], rax
0x180033c2a  call    cs:__imp_QueryPerformanceCounter
0x180033c30  mov     eax, dword ptr [rbp+PerformanceCount]
0x180033c33  mov     rcx, 0FFFFFFFFFFFFh
0x180033c3d  shl     rax, 20h
0x180033c41  xor     rax, qword ptr [rbp+PerformanceCount]
0x180033c45  xor     rax, [rbp+arg_0]
0x180033c49  and     rax, rcx
0x180033c4c  mov     rcx, rax
0x180033c4f  cmp     rax, rbx
0x180033c52  jnz     short loc_180033C61
0x180033c54  mov     rax, 2B992DDFA233h
0x180033c5e  mov     rcx, rax
0x180033c61  mov     cs:__security_cookie, rcx
0x180033c68  mov     rbx, [rsp+20h+arg_18]
0x180033c6d  not     rax
0x180033c70  mov     cs:__security_cookie_complement, rax
0x180033c77  add     rsp, 20h
0x180033c7b  pop     rbp
0x180033c7c  retn
```
