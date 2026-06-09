# __security_init_cookie

- ea: `0x18001b1b4`
- end: `0x18001b291`
- name: `__security_init_cookie`
- size: `221`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001adf0`

## callees

- `0x18001b1b4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b1fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b1fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b207`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b207`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b1ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b1ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b213`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b223`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b213`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x18001b223`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b23e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b23e`

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
0x18001b1b4  mov     [rsp-8+arg_18], rbx
0x18001b1b9  push    rbp
0x18001b1ba  mov     rbp, rsp
0x18001b1bd  sub     rsp, 20h
0x18001b1c1  xor     eax, eax
0x18001b1c3  mov     rbx, 2B992DDFA232h
0x18001b1cd  mov     [rbp+arg_0], rax
0x18001b1d1  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001b1d5  mov     qword ptr [rbp+PerformanceCount], rax
0x18001b1d9  mov     rax, cs:__security_cookie
0x18001b1e0  cmp     rax, rbx
0x18001b1e3  jnz     loc_18001B27C
0x18001b1e9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001b1ed  call    cs:__imp_GetSystemTimeAsFileTime
0x18001b1f3  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001b1f7  mov     [rbp+arg_0], rax
0x18001b1fb  call    cs:__imp_GetCurrentProcessId
0x18001b201  mov     eax, eax
0x18001b203  xor     [rbp+arg_0], rax
0x18001b207  call    cs:__imp_GetCurrentThreadId
0x18001b20d  mov     eax, eax
0x18001b20f  xor     [rbp+arg_0], rax
0x18001b213  call    cs:__imp_GetTickCount
0x18001b219  mov     eax, eax
0x18001b21b  shl     rax, 18h
0x18001b21f  xor     [rbp+arg_0], rax
0x18001b223  call    cs:__imp_GetTickCount
0x18001b229  mov     eax, eax
0x18001b22b  lea     rcx, [rbp+arg_0]
0x18001b22f  xor     rax, [rbp+arg_0]
0x18001b233  xor     rax, rcx
0x18001b236  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001b23a  mov     [rbp+arg_0], rax
0x18001b23e  call    cs:__imp_QueryPerformanceCounter
0x18001b244  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001b247  mov     rcx, 0FFFFFFFFFFFFh
0x18001b251  shl     rax, 20h
0x18001b255  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001b259  xor     rax, [rbp+arg_0]
0x18001b25d  and     rax, rcx
0x18001b260  mov     rcx, rax
0x18001b263  cmp     rax, rbx
0x18001b266  jnz     short loc_18001B275
0x18001b268  mov     rax, 2B992DDFA233h
0x18001b272  mov     rcx, rax
0x18001b275  mov     cs:__security_cookie, rcx
0x18001b27c  mov     rbx, [rsp+20h+arg_18]
0x18001b281  not     rax
0x18001b284  mov     cs:__security_cookie_complement, rax
0x18001b28b  add     rsp, 20h
0x18001b28f  pop     rbp
0x18001b290  retn
```
