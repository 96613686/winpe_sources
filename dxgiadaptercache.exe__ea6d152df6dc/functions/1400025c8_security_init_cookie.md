# __security_init_cookie

- ea: `0x1400025c8`
- end: `0x14000267d`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140002270`

## callees

- `0x1400025c8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000260b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000260b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x140002617`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400025fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400025fd`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002627`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x140002627`

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
0x1400025c8  mov     [rsp-8+arg_10], rbx
0x1400025cd  push    rbp
0x1400025ce  mov     rbp, rsp
0x1400025d1  sub     rsp, 30h
0x1400025d5  mov     rax, cs:__security_cookie
0x1400025dc  mov     rbx, 2B992DDFA232h
0x1400025e6  cmp     rax, rbx
0x1400025e9  jnz     short loc_140002668
0x1400025eb  xor     eax, eax
0x1400025ed  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400025f1  mov     [rbp+var_10], rax
0x1400025f5  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x1400025f9  mov     qword ptr [rbp+PerformanceCount], rax
0x1400025fd  call    cs:__imp_GetSystemTimeAsFileTime
0x140002603  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x140002607  mov     [rbp+var_10], rax
0x14000260b  call    cs:__imp_GetCurrentThreadId
0x140002611  mov     eax, eax
0x140002613  xor     [rbp+var_10], rax
0x140002617  call    cs:__imp_GetCurrentProcessId
0x14000261d  mov     eax, eax
0x14000261f  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x140002623  xor     [rbp+var_10], rax
0x140002627  call    cs:__imp_QueryPerformanceCounter
0x14000262d  mov     eax, dword ptr [rbp+PerformanceCount]
0x140002630  lea     rcx, [rbp+var_10]
0x140002634  shl     rax, 20h
0x140002638  xor     rax, qword ptr [rbp+PerformanceCount]
0x14000263c  xor     rax, [rbp+var_10]
0x140002640  xor     rax, rcx
0x140002643  mov     rcx, 0FFFFFFFFFFFFh
0x14000264d  and     rax, rcx
0x140002650  mov     rcx, 2B992DDFA233h
0x14000265a  cmp     rax, rbx
0x14000265d  cmovz   rax, rcx
0x140002661  mov     cs:__security_cookie, rax
0x140002668  mov     rbx, [rsp+30h+arg_10]
0x14000266d  not     rax
0x140002670  mov     cs:__security_cookie_complement, rax
0x140002677  add     rsp, 30h
0x14000267b  pop     rbp
0x14000267c  retn
```
