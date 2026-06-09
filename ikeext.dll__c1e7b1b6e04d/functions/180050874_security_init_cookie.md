# __security_init_cookie

- ea: `0x180050874`
- end: `0x180050929`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180050800`

## callees

- `0x180050874`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800508d3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800508d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800508b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800508b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800508c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800508c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800508a9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800508a9`

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
0x180050874  mov     [rsp-8+arg_10], rbx
0x180050879  push    rbp
0x18005087a  mov     rbp, rsp
0x18005087d  sub     rsp, 30h
0x180050881  mov     rax, cs:__security_cookie
0x180050888  mov     rbx, 2B992DDFA232h
0x180050892  cmp     rax, rbx
0x180050895  jnz     short loc_180050914
0x180050897  xor     eax, eax
0x180050899  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18005089d  mov     [rbp+var_10], rax
0x1800508a1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800508a5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800508a9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800508af  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800508b3  mov     [rbp+var_10], rax
0x1800508b7  call    cs:__imp_GetCurrentThreadId
0x1800508bd  mov     eax, eax
0x1800508bf  xor     [rbp+var_10], rax
0x1800508c3  call    cs:__imp_GetCurrentProcessId
0x1800508c9  mov     eax, eax
0x1800508cb  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800508cf  xor     [rbp+var_10], rax
0x1800508d3  call    cs:__imp_QueryPerformanceCounter
0x1800508d9  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800508dc  lea     rcx, [rbp+var_10]
0x1800508e0  shl     rax, 20h
0x1800508e4  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800508e8  xor     rax, [rbp+var_10]
0x1800508ec  xor     rax, rcx
0x1800508ef  mov     rcx, 0FFFFFFFFFFFFh
0x1800508f9  and     rax, rcx
0x1800508fc  mov     rcx, 2B992DDFA233h
0x180050906  cmp     rax, rbx
0x180050909  cmovz   rax, rcx
0x18005090d  mov     cs:__security_cookie, rax
0x180050914  mov     rbx, [rsp+30h+arg_10]
0x180050919  not     rax
0x18005091c  mov     cs:__security_cookie_complement, rax
0x180050923  add     rsp, 30h
0x180050927  pop     rbp
0x180050928  retn
```
