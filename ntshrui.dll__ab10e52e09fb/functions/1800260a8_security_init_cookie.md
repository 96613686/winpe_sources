# __security_init_cookie

- ea: `0x1800260a8`
- end: `0x18002615d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180025490`

## callees

- `0x1800260a8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800260f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800260f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800260eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800260eb`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800260dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800260dd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026107`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180026107`

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
0x1800260a8  mov     [rsp-8+arg_10], rbx
0x1800260ad  push    rbp
0x1800260ae  mov     rbp, rsp
0x1800260b1  sub     rsp, 30h
0x1800260b5  mov     rax, cs:__security_cookie
0x1800260bc  mov     rbx, 2B992DDFA232h
0x1800260c6  cmp     rax, rbx
0x1800260c9  jnz     short loc_180026148
0x1800260cb  xor     eax, eax
0x1800260cd  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800260d1  mov     [rbp+var_10], rax
0x1800260d5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800260d9  mov     qword ptr [rbp+PerformanceCount], rax
0x1800260dd  call    cs:__imp_GetSystemTimeAsFileTime
0x1800260e3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800260e7  mov     [rbp+var_10], rax
0x1800260eb  call    cs:__imp_GetCurrentThreadId
0x1800260f1  mov     eax, eax
0x1800260f3  xor     [rbp+var_10], rax
0x1800260f7  call    cs:__imp_GetCurrentProcessId
0x1800260fd  mov     eax, eax
0x1800260ff  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180026103  xor     [rbp+var_10], rax
0x180026107  call    cs:__imp_QueryPerformanceCounter
0x18002610d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180026110  lea     rcx, [rbp+var_10]
0x180026114  shl     rax, 20h
0x180026118  xor     rax, qword ptr [rbp+PerformanceCount]
0x18002611c  xor     rax, [rbp+var_10]
0x180026120  xor     rax, rcx
0x180026123  mov     rcx, 0FFFFFFFFFFFFh
0x18002612d  and     rax, rcx
0x180026130  mov     rcx, 2B992DDFA233h
0x18002613a  cmp     rax, rbx
0x18002613d  cmovz   rax, rcx
0x180026141  mov     cs:__security_cookie, rax
0x180026148  mov     rbx, [rsp+30h+arg_10]
0x18002614d  not     rax
0x180026150  mov     cs:__security_cookie_complement, rax
0x180026157  add     rsp, 30h
0x18002615b  pop     rbp
0x18002615c  retn
```
