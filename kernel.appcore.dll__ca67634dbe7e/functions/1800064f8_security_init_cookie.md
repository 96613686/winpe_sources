# __security_init_cookie

- ea: `0x1800064f8`
- end: `0x1800065d5`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005350`

## callees

- `0x1800064f8`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006582`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180006582`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000653f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000653f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000654b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000654b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006531`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180006531`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006557`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006567`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006557`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180006567`

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
0x1800064f8  mov     [rsp-8+arg_18], rbx
0x1800064fd  push    rbp
0x1800064fe  mov     rbp, rsp
0x180006501  sub     rsp, 20h
0x180006505  xor     eax, eax
0x180006507  mov     rbx, 2B992DDFA232h
0x180006511  mov     [rbp+arg_0], rax
0x180006515  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180006519  mov     qword ptr [rbp+PerformanceCount], rax
0x18000651d  mov     rax, cs:__security_cookie
0x180006524  cmp     rax, rbx
0x180006527  jnz     loc_1800065C0
0x18000652d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180006531  call    cs:__imp_GetSystemTimeAsFileTime
0x180006537  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000653b  mov     [rbp+arg_0], rax
0x18000653f  call    cs:__imp_GetCurrentProcessId
0x180006545  mov     eax, eax
0x180006547  xor     [rbp+arg_0], rax
0x18000654b  call    cs:__imp_GetCurrentThreadId
0x180006551  mov     eax, eax
0x180006553  xor     [rbp+arg_0], rax
0x180006557  call    cs:__imp_GetTickCount
0x18000655d  mov     eax, eax
0x18000655f  shl     rax, 18h
0x180006563  xor     [rbp+arg_0], rax
0x180006567  call    cs:__imp_GetTickCount
0x18000656d  mov     eax, eax
0x18000656f  lea     rcx, [rbp+arg_0]
0x180006573  xor     rax, [rbp+arg_0]
0x180006577  xor     rax, rcx
0x18000657a  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000657e  mov     [rbp+arg_0], rax
0x180006582  call    cs:__imp_QueryPerformanceCounter
0x180006588  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000658b  mov     rcx, 0FFFFFFFFFFFFh
0x180006595  shl     rax, 20h
0x180006599  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000659d  xor     rax, [rbp+arg_0]
0x1800065a1  and     rax, rcx
0x1800065a4  mov     rcx, rax
0x1800065a7  cmp     rax, rbx
0x1800065aa  jnz     short loc_1800065B9
0x1800065ac  mov     rax, 2B992DDFA233h
0x1800065b6  mov     rcx, rax
0x1800065b9  mov     cs:__security_cookie, rcx
0x1800065c0  mov     rbx, [rsp+20h+arg_18]
0x1800065c5  not     rax
0x1800065c8  mov     cs:__security_cookie_complement, rax
0x1800065cf  add     rsp, 20h
0x1800065d3  pop     rbp
0x1800065d4  retn
```
