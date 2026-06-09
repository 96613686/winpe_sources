# __security_init_cookie

- ea: `0x18007b488`
- end: `0x18007b53d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007af94`

## callees

- `0x18007b488`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b4cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18007b4cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b4d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18007b4d7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007b4bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18007b4bd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007b4e7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18007b4e7`

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
0x18007b488  mov     [rsp-8+arg_10], rbx
0x18007b48d  push    rbp
0x18007b48e  mov     rbp, rsp
0x18007b491  sub     rsp, 30h
0x18007b495  mov     rax, cs:__security_cookie
0x18007b49c  mov     rbx, 2B992DDFA232h
0x18007b4a6  cmp     rax, rbx
0x18007b4a9  jnz     short loc_18007B528
0x18007b4ab  xor     eax, eax
0x18007b4ad  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18007b4b1  mov     [rbp+var_10], rax
0x18007b4b5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18007b4b9  mov     qword ptr [rbp+PerformanceCount], rax
0x18007b4bd  call    cs:__imp_GetSystemTimeAsFileTime
0x18007b4c3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18007b4c7  mov     [rbp+var_10], rax
0x18007b4cb  call    cs:__imp_GetCurrentThreadId
0x18007b4d1  mov     eax, eax
0x18007b4d3  xor     [rbp+var_10], rax
0x18007b4d7  call    cs:__imp_GetCurrentProcessId
0x18007b4dd  mov     eax, eax
0x18007b4df  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18007b4e3  xor     [rbp+var_10], rax
0x18007b4e7  call    cs:__imp_QueryPerformanceCounter
0x18007b4ed  mov     eax, dword ptr [rbp+PerformanceCount]
0x18007b4f0  lea     rcx, [rbp+var_10]
0x18007b4f4  shl     rax, 20h
0x18007b4f8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18007b4fc  xor     rax, [rbp+var_10]
0x18007b500  xor     rax, rcx
0x18007b503  mov     rcx, 0FFFFFFFFFFFFh
0x18007b50d  and     rax, rcx
0x18007b510  mov     rcx, 2B992DDFA233h
0x18007b51a  cmp     rax, rbx
0x18007b51d  cmovz   rax, rcx
0x18007b521  mov     cs:__security_cookie, rax
0x18007b528  mov     rbx, [rsp+30h+arg_10]
0x18007b52d  not     rax
0x18007b530  mov     cs:__security_cookie_complement, rax
0x18007b537  add     rsp, 30h
0x18007b53b  pop     rbp
0x18007b53c  retn
```
