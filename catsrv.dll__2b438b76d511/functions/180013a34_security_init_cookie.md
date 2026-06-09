# __security_init_cookie

- ea: `0x180013a34`
- end: `0x180013b11`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800131d0`

## callees

- `0x180013a34`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013a93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013a93`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180013aa3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013a6d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180013a6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180013a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013a87`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013abe`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180013abe`

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
0x180013a34  mov     [rsp-8+arg_18], rbx
0x180013a39  push    rbp
0x180013a3a  mov     rbp, rsp
0x180013a3d  sub     rsp, 20h
0x180013a41  xor     eax, eax
0x180013a43  mov     rbx, 2B992DDFA232h
0x180013a4d  mov     [rbp+arg_0], rax
0x180013a51  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180013a55  mov     qword ptr [rbp+PerformanceCount], rax
0x180013a59  mov     rax, cs:__security_cookie
0x180013a60  cmp     rax, rbx
0x180013a63  jnz     loc_180013AFC
0x180013a69  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180013a6d  call    cs:__imp_GetSystemTimeAsFileTime
0x180013a73  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180013a77  mov     [rbp+arg_0], rax
0x180013a7b  call    cs:__imp_GetCurrentProcessId
0x180013a81  mov     eax, eax
0x180013a83  xor     [rbp+arg_0], rax
0x180013a87  call    cs:__imp_GetCurrentThreadId
0x180013a8d  mov     eax, eax
0x180013a8f  xor     [rbp+arg_0], rax
0x180013a93  call    cs:__imp_GetTickCount
0x180013a99  mov     eax, eax
0x180013a9b  shl     rax, 18h
0x180013a9f  xor     [rbp+arg_0], rax
0x180013aa3  call    cs:__imp_GetTickCount
0x180013aa9  mov     eax, eax
0x180013aab  lea     rcx, [rbp+arg_0]
0x180013aaf  xor     rax, [rbp+arg_0]
0x180013ab3  xor     rax, rcx
0x180013ab6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180013aba  mov     [rbp+arg_0], rax
0x180013abe  call    cs:__imp_QueryPerformanceCounter
0x180013ac4  mov     eax, dword ptr [rbp+PerformanceCount]
0x180013ac7  mov     rcx, 0FFFFFFFFFFFFh
0x180013ad1  shl     rax, 20h
0x180013ad5  xor     rax, qword ptr [rbp+PerformanceCount]
0x180013ad9  xor     rax, [rbp+arg_0]
0x180013add  and     rax, rcx
0x180013ae0  mov     rcx, rax
0x180013ae3  cmp     rax, rbx
0x180013ae6  jnz     short loc_180013AF5
0x180013ae8  mov     rax, 2B992DDFA233h
0x180013af2  mov     rcx, rax
0x180013af5  mov     cs:__security_cookie, rcx
0x180013afc  mov     rbx, [rsp+20h+arg_18]
0x180013b01  not     rax
0x180013b04  mov     cs:__security_cookie_complement, rax
0x180013b0b  add     rsp, 20h
0x180013b0f  pop     rbp
0x180013b10  retn
```
