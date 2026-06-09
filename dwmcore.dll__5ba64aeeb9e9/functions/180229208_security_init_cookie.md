# __security_init_cookie

- ea: `0x180229208`
- end: `0x1802292bd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180228ba4`

## callees

- `0x180229208`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180229257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180229257`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18022924b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18022924b`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180229267`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180229267`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18022923d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18022923d`

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
0x180229208  mov     [rsp-8+arg_10], rbx
0x18022920d  push    rbp
0x18022920e  mov     rbp, rsp
0x180229211  sub     rsp, 30h
0x180229215  mov     rax, cs:__security_cookie
0x18022921c  mov     rbx, 2B992DDFA232h
0x180229226  cmp     rax, rbx
0x180229229  jnz     short loc_1802292A8
0x18022922b  xor     eax, eax
0x18022922d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180229231  mov     [rbp+var_10], rax
0x180229235  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x180229239  mov     qword ptr [rbp+PerformanceCount], rax
0x18022923d  call    cs:__imp_GetSystemTimeAsFileTime
0x180229243  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180229247  mov     [rbp+var_10], rax
0x18022924b  call    cs:__imp_GetCurrentThreadId
0x180229251  mov     eax, eax
0x180229253  xor     [rbp+var_10], rax
0x180229257  call    cs:__imp_GetCurrentProcessId
0x18022925d  mov     eax, eax
0x18022925f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180229263  xor     [rbp+var_10], rax
0x180229267  call    cs:__imp_QueryPerformanceCounter
0x18022926d  mov     eax, dword ptr [rbp+PerformanceCount]
0x180229270  lea     rcx, [rbp+var_10]
0x180229274  shl     rax, 20h
0x180229278  xor     rax, qword ptr [rbp+PerformanceCount]
0x18022927c  xor     rax, [rbp+var_10]
0x180229280  xor     rax, rcx
0x180229283  mov     rcx, 0FFFFFFFFFFFFh
0x18022928d  and     rax, rcx
0x180229290  mov     rcx, 2B992DDFA233h
0x18022929a  cmp     rax, rbx
0x18022929d  cmovz   rax, rcx
0x1802292a1  mov     cs:__security_cookie, rax
0x1802292a8  mov     rbx, [rsp+30h+arg_10]
0x1802292ad  not     rax
0x1802292b0  mov     cs:__security_cookie_complement, rax
0x1802292b7  add     rsp, 30h
0x1802292bb  pop     rbp
0x1802292bc  retn
```
