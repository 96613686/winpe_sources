# __security_init_cookie

- ea: `0x1400109e4`
- end: `0x140010ac1`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140010200`

## callees

- `0x1400109e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010a2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140010a2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010a37`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140010a6e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140010a6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140010a43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140010a53`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140010a43`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140010a53`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140010a1d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140010a1d`

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
0x1400109e4  mov     [rsp-8+arg_18], rbx
0x1400109e9  push    rbp
0x1400109ea  mov     rbp, rsp
0x1400109ed  sub     rsp, 20h
0x1400109f1  xor     eax, eax
0x1400109f3  mov     rbx, 2B992DDFA232h
0x1400109fd  mov     [rbp+arg_0], rax
0x140010a01  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140010a05  mov     qword ptr [rbp+PerformanceCount], rax
0x140010a09  mov     rax, cs:__security_cookie
0x140010a10  cmp     rax, rbx
0x140010a13  jnz     loc_140010AAC
0x140010a19  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140010a1d  call    cs:__imp_GetSystemTimeAsFileTime
0x140010a23  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140010a27  mov     [rbp+arg_0], rax
0x140010a2b  call    cs:__imp_GetCurrentProcessId
0x140010a31  mov     eax, eax
0x140010a33  xor     [rbp+arg_0], rax
0x140010a37  call    cs:__imp_GetCurrentThreadId
0x140010a3d  mov     eax, eax
0x140010a3f  xor     [rbp+arg_0], rax
0x140010a43  call    cs:__imp_GetTickCount
0x140010a49  mov     eax, eax
0x140010a4b  shl     rax, 18h
0x140010a4f  xor     [rbp+arg_0], rax
0x140010a53  call    cs:__imp_GetTickCount
0x140010a59  mov     eax, eax
0x140010a5b  lea     rcx, [rbp+arg_0]
0x140010a5f  xor     rax, [rbp+arg_0]
0x140010a63  xor     rax, rcx
0x140010a66  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140010a6a  mov     [rbp+arg_0], rax
0x140010a6e  call    cs:__imp_QueryPerformanceCounter
0x140010a74  mov     eax, dword ptr [rbp+PerformanceCount]
0x140010a77  mov     rcx, 0FFFFFFFFFFFFh
0x140010a81  shl     rax, 20h
0x140010a85  xor     rax, qword ptr [rbp+PerformanceCount]
0x140010a89  xor     rax, [rbp+arg_0]
0x140010a8d  and     rax, rcx
0x140010a90  mov     rcx, rax
0x140010a93  cmp     rax, rbx
0x140010a96  jnz     short loc_140010AA5
0x140010a98  mov     rax, 2B992DDFA233h
0x140010aa2  mov     rcx, rax
0x140010aa5  mov     cs:__security_cookie, rcx
0x140010aac  mov     rbx, [rsp+20h+arg_18]
0x140010ab1  not     rax
0x140010ab4  mov     cs:__security_cookie_complement, rax
0x140010abb  add     rsp, 20h
0x140010abf  pop     rbp
0x140010ac0  retn
```
