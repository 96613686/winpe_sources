# __security_init_cookie

- ea: `0x180013010`
- end: `0x1800130bc`
- name: `__security_init_cookie`
- size: `172`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012af0`

## callees

- `0x180013010`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x180013066`
- `KERNEL32!QueryPerformanceCounter` at `0x180013066`
- `KERNEL32!GetCurrentProcessId` at `0x180013056`
- `KERNEL32!GetCurrentProcessId` at `0x180013056`
- `KERNEL32!GetCurrentThreadId` at `0x18001304a`
- `KERNEL32!GetCurrentThreadId` at `0x18001304a`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001303c`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18001303c`

## pseudocode

```c
void __cdecl _security_init_cookie()
{
  uintptr_t v0; // rax
  struct _FILETIME v1; // [rsp+30h] [rbp+10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp+18h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+40h] [rbp+20h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
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
0x180013010  mov     [rsp-8+arg_18], rbx
0x180013015  push    rbp
0x180013016  mov     rbp, rsp
0x180013019  sub     rsp, 20h
0x18001301d  mov     rax, cs:__security_cookie
0x180013024  mov     rbx, 2B992DDFA232h
0x18001302e  cmp     rax, rbx
0x180013031  jnz     short loc_1800130A7
0x180013033  and     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180013038  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001303c  call    cs:__imp_GetSystemTimeAsFileTime
0x180013042  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x180013046  mov     [rbp+arg_0], rax
0x18001304a  call    cs:__imp_GetCurrentThreadId
0x180013050  mov     eax, eax
0x180013052  xor     [rbp+arg_0], rax
0x180013056  call    cs:__imp_GetCurrentProcessId
0x18001305c  mov     eax, eax
0x18001305e  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x180013062  xor     [rbp+arg_0], rax
0x180013066  call    cs:__imp_QueryPerformanceCounter
0x18001306c  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001306f  lea     rcx, [rbp+arg_0]
0x180013073  shl     rax, 20h
0x180013077  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001307b  xor     rax, [rbp+arg_0]
0x18001307f  xor     rax, rcx
0x180013082  mov     rcx, 0FFFFFFFFFFFFh
0x18001308c  and     rax, rcx
0x18001308f  mov     rcx, 2B992DDFA233h
0x180013099  cmp     rax, rbx
0x18001309c  cmovz   rax, rcx
0x1800130a0  mov     cs:__security_cookie, rax
0x1800130a7  mov     rbx, [rsp+20h+arg_18]
0x1800130ac  not     rax
0x1800130af  mov     cs:__security_cookie_complement, rax
0x1800130b6  add     rsp, 20h
0x1800130ba  pop     rbp
0x1800130bb  retn
```
