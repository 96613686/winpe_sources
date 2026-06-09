# __security_init_cookie

- ea: `0x180044754`
- end: `0x180044831`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180043de0`

## callees

- `0x180044754`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800447b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800447c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800447b3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800447c3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004478d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18004478d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004479b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18004479b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800447a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800447a7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800447de`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800447de`

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
0x180044754  mov     [rsp-8+arg_18], rbx
0x180044759  push    rbp
0x18004475a  mov     rbp, rsp
0x18004475d  sub     rsp, 20h
0x180044761  xor     eax, eax
0x180044763  mov     rbx, 2B992DDFA232h
0x18004476d  mov     [rbp+arg_0], rax
0x180044771  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180044775  mov     qword ptr [rbp+PerformanceCount], rax
0x180044779  mov     rax, cs:__security_cookie
0x180044780  cmp     rax, rbx
0x180044783  jnz     loc_18004481C
0x180044789  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18004478d  call    cs:__imp_GetSystemTimeAsFileTime
0x180044793  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180044797  mov     [rbp+arg_0], rax
0x18004479b  call    cs:__imp_GetCurrentProcessId
0x1800447a1  mov     eax, eax
0x1800447a3  xor     [rbp+arg_0], rax
0x1800447a7  call    cs:__imp_GetCurrentThreadId
0x1800447ad  mov     eax, eax
0x1800447af  xor     [rbp+arg_0], rax
0x1800447b3  call    cs:__imp_GetTickCount
0x1800447b9  mov     eax, eax
0x1800447bb  shl     rax, 18h
0x1800447bf  xor     [rbp+arg_0], rax
0x1800447c3  call    cs:__imp_GetTickCount
0x1800447c9  mov     eax, eax
0x1800447cb  lea     rcx, [rbp+arg_0]
0x1800447cf  xor     rax, [rbp+arg_0]
0x1800447d3  xor     rax, rcx
0x1800447d6  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1800447da  mov     [rbp+arg_0], rax
0x1800447de  call    cs:__imp_QueryPerformanceCounter
0x1800447e4  mov     eax, dword ptr [rbp+PerformanceCount]
0x1800447e7  mov     rcx, 0FFFFFFFFFFFFh
0x1800447f1  shl     rax, 20h
0x1800447f5  xor     rax, qword ptr [rbp+PerformanceCount]
0x1800447f9  xor     rax, [rbp+arg_0]
0x1800447fd  and     rax, rcx
0x180044800  mov     rcx, rax
0x180044803  cmp     rax, rbx
0x180044806  jnz     short loc_180044815
0x180044808  mov     rax, 2B992DDFA233h
0x180044812  mov     rcx, rax
0x180044815  mov     cs:__security_cookie, rcx
0x18004481c  mov     rbx, [rsp+20h+arg_18]
0x180044821  not     rax
0x180044824  mov     cs:__security_cookie_complement, rax
0x18004482b  add     rsp, 20h
0x18004482f  pop     rbp
0x180044830  retn
```
