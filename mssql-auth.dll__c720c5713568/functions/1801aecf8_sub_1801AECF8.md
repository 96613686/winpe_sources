# sub_1801AECF8

- ea: `0x1801aecf8`
- end: `0x1801aeda7`
- name: `sub_1801AECF8`
- size: `175`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801ae0b0`

## callees

- `0x1801aecf8`

## import_xrefs

- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801aed27`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1801aed27`
- `KERNEL32!GetCurrentProcessId` at `0x1801aed41`
- `KERNEL32!GetCurrentProcessId` at `0x1801aed41`
- `KERNEL32!GetCurrentThreadId` at `0x1801aed35`
- `KERNEL32!GetCurrentThreadId` at `0x1801aed35`
- `KERNEL32!QueryPerformanceCounter` at `0x1801aed51`
- `KERNEL32!QueryPerformanceCounter` at `0x1801aed51`

## pseudocode

```c
__int64 sub_1801AECF8()
{
  uintptr_t v0; // rax
  __int64 result; // rax
  struct _FILETIME v2; // [rsp+20h] [rbp-10h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp+10h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp+18h] BYREF

  v0 = _security_cookie;
  if ( _security_cookie == 0x2B992DDFA232LL )
  {
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v2 = SystemTimeAsFileTime;
    v2 = (struct _FILETIME)(GetCurrentThreadId() ^ *(unsigned __int64 *)&v2);
    v2 = (struct _FILETIME)(GetCurrentProcessId() ^ *(unsigned __int64 *)&v2);
    QueryPerformanceCounter(&PerformanceCount);
    v0 = ((unsigned __int64)&v2
        ^ *(_QWORD *)&v2
        ^ PerformanceCount.QuadPart
        ^ ((unsigned __int64)PerformanceCount.LowPart << 32))
       & 0xFFFFFFFFFFFFLL;
    if ( v0 == 0x2B992DDFA232LL )
      v0 = 0x2B992DDFA233LL;
    _security_cookie = v0;
  }
  result = ~v0;
  qword_1805C4F00 = result;
  return result;
}

```

## disassembly

```asm
0x1801aecf8  mov     [rsp-8+arg_10], rbx
0x1801aecfd  push    rbp
0x1801aecfe  mov     rbp, rsp
0x1801aed01  sub     rsp, 30h
0x1801aed05  mov     rax, cs:__security_cookie
0x1801aed0c  mov     rbx, 2B992DDFA232h
0x1801aed16  cmp     rax, rbx
0x1801aed19  jnz     short loc_1801AED92
0x1801aed1b  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1801aed1f  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x1801aed27  call    cs:GetSystemTimeAsFileTime
0x1801aed2d  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x1801aed31  mov     [rbp+var_10], rax
0x1801aed35  call    cs:__imp_GetCurrentThreadId
0x1801aed3b  mov     eax, eax
0x1801aed3d  xor     [rbp+var_10], rax
0x1801aed41  call    cs:GetCurrentProcessId
0x1801aed47  mov     eax, eax
0x1801aed49  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x1801aed4d  xor     [rbp+var_10], rax
0x1801aed51  call    cs:QueryPerformanceCounter
0x1801aed57  mov     eax, dword ptr [rbp+PerformanceCount]
0x1801aed5a  lea     rcx, [rbp+var_10]
0x1801aed5e  shl     rax, 20h
0x1801aed62  xor     rax, qword ptr [rbp+PerformanceCount]
0x1801aed66  xor     rax, [rbp+var_10]
0x1801aed6a  xor     rax, rcx
0x1801aed6d  mov     rcx, 0FFFFFFFFFFFFh
0x1801aed77  and     rax, rcx
0x1801aed7a  mov     rcx, 2B992DDFA233h
0x1801aed84  cmp     rax, rbx
0x1801aed87  cmovz   rax, rcx
0x1801aed8b  mov     cs:__security_cookie, rax
0x1801aed92  mov     rbx, [rsp+30h+arg_10]
0x1801aed97  not     rax
0x1801aed9a  mov     cs:qword_1805C4F00, rax
0x1801aeda1  add     rsp, 30h
0x1801aeda5  pop     rbp
0x1801aeda6  retn
```
