# __security_init_cookie

- ea: `0x18000fea0`
- end: `0x18000ff55`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000f920`

## callees

- `0x18000fea0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000fee3`
- `KERNEL32!GetCurrentThreadId` at `0x18000fee3`
- `KERNEL32!GetCurrentProcessId` at `0x18000feef`
- `KERNEL32!GetCurrentProcessId` at `0x18000feef`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000fed5`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x18000fed5`
- `KERNEL32!QueryPerformanceCounter` at `0x18000feff`
- `KERNEL32!QueryPerformanceCounter` at `0x18000feff`

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
0x18000fea0  mov     [rsp-8+arg_10], rbx
0x18000fea5  push    rbp
0x18000fea6  mov     rbp, rsp
0x18000fea9  sub     rsp, 30h
0x18000fead  mov     rax, cs:__security_cookie
0x18000feb4  mov     rbx, 2B992DDFA232h
0x18000febe  cmp     rax, rbx
0x18000fec1  jnz     short loc_18000FF40
0x18000fec3  xor     eax, eax
0x18000fec5  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000fec9  mov     [rbp+var_10], rax
0x18000fecd  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18000fed1  mov     qword ptr [rbp+PerformanceCount], rax
0x18000fed5  call    cs:__imp_GetSystemTimeAsFileTime
0x18000fedb  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000fedf  mov     [rbp+var_10], rax
0x18000fee3  call    cs:__imp_GetCurrentThreadId
0x18000fee9  mov     eax, eax
0x18000feeb  xor     [rbp+var_10], rax
0x18000feef  call    cs:__imp_GetCurrentProcessId
0x18000fef5  mov     eax, eax
0x18000fef7  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18000fefb  xor     [rbp+var_10], rax
0x18000feff  call    cs:__imp_QueryPerformanceCounter
0x18000ff05  mov     eax, dword ptr [rbp+PerformanceCount]
0x18000ff08  lea     rcx, [rbp+var_10]
0x18000ff0c  shl     rax, 20h
0x18000ff10  xor     rax, qword ptr [rbp+PerformanceCount]
0x18000ff14  xor     rax, [rbp+var_10]
0x18000ff18  xor     rax, rcx
0x18000ff1b  mov     rcx, 0FFFFFFFFFFFFh
0x18000ff25  and     rax, rcx
0x18000ff28  mov     rcx, 2B992DDFA233h
0x18000ff32  cmp     rax, rbx
0x18000ff35  cmovz   rax, rcx
0x18000ff39  mov     cs:__security_cookie, rax
0x18000ff40  mov     rbx, [rsp+30h+arg_10]
0x18000ff45  not     rax
0x18000ff48  mov     cs:__security_cookie_complement, rax
0x18000ff4f  add     rsp, 30h
0x18000ff53  pop     rbp
0x18000ff54  retn
```
