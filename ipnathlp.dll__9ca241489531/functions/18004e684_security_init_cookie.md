# __security_init_cookie

- ea: `0x18004e684`
- end: `0x18004e739`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004e060`

## callees

- `0x18004e684`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e6c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004e6c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e6d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004e6d3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e6b9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004e6b9`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004e6e3`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18004e6e3`

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
0x18004e684  mov     [rsp-8+arg_10], rbx
0x18004e689  push    rbp
0x18004e68a  mov     rbp, rsp
0x18004e68d  sub     rsp, 30h
0x18004e691  mov     rax, cs:__security_cookie
0x18004e698  mov     rbx, 2B992DDFA232h
0x18004e6a2  cmp     rax, rbx
0x18004e6a5  jnz     short loc_18004E724
0x18004e6a7  xor     eax, eax
0x18004e6a9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004e6ad  mov     [rbp+var_10], rax
0x18004e6b1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18004e6b5  mov     qword ptr [rbp+PerformanceCount], rax
0x18004e6b9  call    cs:__imp_GetSystemTimeAsFileTime
0x18004e6bf  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18004e6c3  mov     [rbp+var_10], rax
0x18004e6c7  call    cs:__imp_GetCurrentThreadId
0x18004e6cd  mov     eax, eax
0x18004e6cf  xor     [rbp+var_10], rax
0x18004e6d3  call    cs:__imp_GetCurrentProcessId
0x18004e6d9  mov     eax, eax
0x18004e6db  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18004e6df  xor     [rbp+var_10], rax
0x18004e6e3  call    cs:__imp_QueryPerformanceCounter
0x18004e6e9  mov     eax, dword ptr [rbp+PerformanceCount]
0x18004e6ec  lea     rcx, [rbp+var_10]
0x18004e6f0  shl     rax, 20h
0x18004e6f4  xor     rax, qword ptr [rbp+PerformanceCount]
0x18004e6f8  xor     rax, [rbp+var_10]
0x18004e6fc  xor     rax, rcx
0x18004e6ff  mov     rcx, 0FFFFFFFFFFFFh
0x18004e709  and     rax, rcx
0x18004e70c  mov     rcx, 2B992DDFA233h
0x18004e716  cmp     rax, rbx
0x18004e719  cmovz   rax, rcx
0x18004e71d  mov     cs:__security_cookie, rax
0x18004e724  mov     rbx, [rsp+30h+arg_10]
0x18004e729  not     rax
0x18004e72c  mov     cs:__security_cookie_complement, rax
0x18004e733  add     rsp, 30h
0x18004e737  pop     rbp
0x18004e738  retn
```
