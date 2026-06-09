# __security_init_cookie

- ea: `0x18000db48`
- end: `0x18000dbfd`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000d794`

## callees

- `0x18000db48`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db8b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000db97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18000db97`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000dba7`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18000dba7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000db7d`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000db7d`

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
0x18000db48  mov     [rsp-8+arg_10], rbx
0x18000db4d  push    rbp
0x18000db4e  mov     rbp, rsp
0x18000db51  sub     rsp, 30h
0x18000db55  mov     rax, cs:__security_cookie
0x18000db5c  mov     rbx, 2B992DDFA232h
0x18000db66  cmp     rax, rbx
0x18000db69  jnz     short loc_18000DBE8
0x18000db6b  xor     eax, eax
0x18000db6d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000db71  mov     [rbp+var_10], rax
0x18000db75  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000db79  mov     qword ptr [rbp+PerformanceCount], rax
0x18000db7d  call    cs:__imp_GetSystemTimeAsFileTime
0x18000db83  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000db87  mov     [rbp+var_10], rax
0x18000db8b  call    cs:__imp_GetCurrentThreadId
0x18000db91  mov     eax, eax
0x18000db93  xor     [rbp+var_10], rax
0x18000db97  call    cs:__imp_GetCurrentProcessId
0x18000db9d  mov     eax, eax
0x18000db9f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000dba3  xor     [rbp+var_10], rax
0x18000dba7  call    cs:__imp_QueryPerformanceCounter
0x18000dbad  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000dbb0  lea     rcx, [rbp+var_10]
0x18000dbb4  shl     rax, 20h
0x18000dbb8  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000dbbc  xor     rax, [rbp+var_10]
0x18000dbc0  xor     rax, rcx
0x18000dbc3  mov     rcx, 0FFFFFFFFFFFFh
0x18000dbcd  and     rax, rcx
0x18000dbd0  mov     rcx, 2B992DDFA233h
0x18000dbda  cmp     rax, rbx
0x18000dbdd  cmovz   rax, rcx
0x18000dbe1  mov     cs:__security_cookie, rax
0x18000dbe8  mov     rbx, [rsp+30h+arg_10]
0x18000dbed  not     rax
0x18000dbf0  mov     cs:__security_cookie_complement, rax
0x18000dbf7  add     rsp, 30h
0x18000dbfb  pop     rbp
0x18000dbfc  retn
```
