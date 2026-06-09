# __security_init_cookie

- ea: `0x18001b804`
- end: `0x18001b8b9`
- name: `__security_init_cookie`
- size: `181`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001b790`

## callees

- `0x18001b804`

## import_xrefs

- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b863`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18001b863`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001b853`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001b847`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b839`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18001b839`

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
0x18001b804  mov     [rsp-8+arg_10], rbx
0x18001b809  push    rbp
0x18001b80a  mov     rbp, rsp
0x18001b80d  sub     rsp, 30h
0x18001b811  mov     rax, cs:__security_cookie
0x18001b818  mov     rbx, 2B992DDFA232h
0x18001b822  cmp     rax, rbx
0x18001b825  jnz     short loc_18001B8A4
0x18001b827  xor     eax, eax
0x18001b829  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18001b82d  mov     [rbp+var_10], rax
0x18001b831  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], rax
0x18001b835  mov     qword ptr [rbp+PerformanceCount], rax
0x18001b839  call    cs:__imp_GetSystemTimeAsFileTime
0x18001b83f  mov     rax, qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18001b843  mov     [rbp+var_10], rax
0x18001b847  call    cs:__imp_GetCurrentThreadId
0x18001b84d  mov     eax, eax
0x18001b84f  xor     [rbp+var_10], rax
0x18001b853  call    cs:__imp_GetCurrentProcessId
0x18001b859  mov     eax, eax
0x18001b85b  lea     rcx, [rbp+PerformanceCount]; lpPerformanceCount
0x18001b85f  xor     [rbp+var_10], rax
0x18001b863  call    cs:__imp_QueryPerformanceCounter
0x18001b869  mov     eax, dword ptr [rbp+PerformanceCount]
0x18001b86c  lea     rcx, [rbp+var_10]
0x18001b870  shl     rax, 20h
0x18001b874  xor     rax, qword ptr [rbp+PerformanceCount]
0x18001b878  xor     rax, [rbp+var_10]
0x18001b87c  xor     rax, rcx
0x18001b87f  mov     rcx, 0FFFFFFFFFFFFh
0x18001b889  and     rax, rcx
0x18001b88c  mov     rcx, 2B992DDFA233h
0x18001b896  cmp     rax, rbx
0x18001b899  cmovz   rax, rcx
0x18001b89d  mov     cs:__security_cookie, rax
0x18001b8a4  mov     rbx, [rsp+30h+arg_10]
0x18001b8a9  not     rax
0x18001b8ac  mov     cs:__security_cookie_complement, rax
0x18001b8b3  add     rsp, 30h
0x18001b8b7  pop     rbp
0x18001b8b8  retn
```
