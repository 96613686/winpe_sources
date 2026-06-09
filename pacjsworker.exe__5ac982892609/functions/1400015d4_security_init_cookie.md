# __security_init_cookie

- ea: `0x1400015d4`
- end: `0x140001689`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140001310`

## callees

- `0x1400015d4`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001633`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140001633`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140001623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140001617`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001609`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140001609`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  _FILETIME v1; // [rsp+20h] [rbp-10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+10h] BYREF
  _FILETIME SystemTimeAsFileTime; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    PerformanceCount.QuadPart = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v1 = SystemTimeAsFileTime;
    v1 = (_FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v1);
    v1 = (_FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v1);
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
0x1400015d4  mov     [rsp-8+arg_10], rbx
0x1400015d9  push    rbp
0x1400015da  mov     rbp, rsp
0x1400015dd  sub     rsp, 30h
0x1400015e1  mov     rax, cs:__security_cookie
0x1400015e8  mov     rbx, 2B992DDFA232h
0x1400015f2  cmp     rax, rbx
0x1400015f5  jnz     short loc_140001674
0x1400015f7  xor     eax, eax
0x1400015f9  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400015fd  mov     [rbp+var_10], rax
0x140001601  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x140001605  mov     qword ptr [rbp+PerformanceCount], rax
0x140001609  call    cs:__imp_GetSystemTimeAsFileTime
0x14000160f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140001613  mov     [rbp+var_10], rax
0x140001617  call    cs:__imp_GetCurrentThreadId
0x14000161d  mov     eax, eax
0x14000161f  xor     [rbp+var_10], rax
0x140001623  call    cs:__imp_GetCurrentProcessId
0x140001629  mov     eax, eax
0x14000162b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x14000162f  xor     [rbp+var_10], rax
0x140001633  call    cs:__imp_QueryPerformanceCounter
0x140001639  mov     eax, dword ptr [rbp+PerformanceCount]
0x14000163c  lea     rcx, [rbp+var_10]
0x140001640  shl     rax, 20h
0x140001644  xor     rax, qword ptr [rbp+PerformanceCount]
0x140001648  xor     rax, [rbp+var_10]
0x14000164c  xor     rax, rcx
0x14000164f  mov     rcx, 0FFFFFFFFFFFFh
0x140001659  and     rax, rcx
0x14000165c  mov     rcx, 2B992DDFA233h
0x140001666  cmp     rax, rbx
0x140001669  cmovz   rax, rcx
0x14000166d  mov     cs:__security_cookie, rax
0x140001674  mov     rbx, [rsp+30h+arg_10]
0x140001679  not     rax
0x14000167c  mov     cs:__security_cookie_complement, rax
0x140001683  add     rsp, 30h
0x140001687  pop     rbp
0x140001688  retn
```
