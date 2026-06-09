# __security_init_cookie

- ea: `0x1800027b4`
- end: `0x180002891`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800022e0`

## callees

- `0x1800027b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800027fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002807`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002807`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000283e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000283e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002813`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002823`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002813`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180002823`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800027ed`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  uintptr_t v1; // rcx
  _FILETIME v2; // [rsp+30h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+38h] [rbp+18h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+20h] BYREF

  v2 = 0;
  SystemTimeAsFileTime = 0;
  PerformanceCount.QuadPart = 0;
  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (_FILETIME)(((unsigned __int64)GetTickCount() << 24) ^ *(_QWORD *)&v2);
    v2 = (_FILETIME)((unsigned __int64)&v2 ^ *(unsigned __int64 *)&v2 ^ GetTickCount());
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
0x1800027b4  mov     [rsp-8+arg_18], rbx
0x1800027b9  push    rbp
0x1800027ba  mov     rbp, rsp
0x1800027bd  sub     rsp, 20h
0x1800027c1  xor     eax, eax
0x1800027c3  mov     rbx, 2B992DDFA232h
0x1800027cd  mov     [rbp+arg_0], rax
0x1800027d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800027d5  mov     qword ptr [rbp+PerformanceCount], rax
0x1800027d9  mov     rax, cs:__security_cookie
0x1800027e0  cmp     rax, rbx
0x1800027e3  jnz     loc_18000287C
0x1800027e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1800027ed  call    cs:__imp_GetSystemTimeAsFileTime
0x1800027f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1800027f7  mov     [rbp+arg_0], rax
0x1800027fb  call    cs:__imp_GetCurrentProcessId
0x180002801  mov     eax, eax
0x180002803  xor     [rbp+arg_0], rax
0x180002807  call    cs:__imp_GetCurrentThreadId
0x18000280d  mov     eax, eax
0x18000280f  xor     [rbp+arg_0], rax
0x180002813  call    cs:__imp_GetTickCount
0x180002819  mov     eax, eax
0x18000281b  shl     rax, 18h
0x18000281f  xor     [rbp+arg_0], rax
0x180002823  call    cs:__imp_GetTickCount
0x180002829  mov     eax, eax
0x18000282b  lea     rcx, [rbp+arg_0]
0x18000282f  xor     rax, [rbp+arg_0]
0x180002833  xor     rax, rcx
0x180002836  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000283a  mov     [rbp+arg_0], rax
0x18000283e  call    cs:__imp_QueryPerformanceCounter
0x180002844  mov     eax, dword ptr [rbp+PerformanceCount]
0x180002847  mov     rcx, 0FFFFFFFFFFFFh
0x180002851  shl     rax, 20h
0x180002855  xor     rax, qword ptr [rbp+PerformanceCount]
0x180002859  xor     rax, [rbp+arg_0]
0x18000285d  and     rax, rcx
0x180002860  mov     rcx, rax
0x180002863  cmp     rax, rbx
0x180002866  jnz     short loc_180002875
0x180002868  mov     rax, 2B992DDFA233h
0x180002872  mov     rcx, rax
0x180002875  mov     cs:__security_cookie, rcx
0x18000287c  mov     rbx, [rsp+20h+arg_18]
0x180002881  not     rax
0x180002884  mov     cs:__security_cookie_complement, rax
0x18000288b  add     rsp, 20h
0x18000288f  pop     rbp
0x180002890  retn
```
