# ___security_init_cookie

- ea: `0x1004dad9`
- end: `0x1004db71`
- name: `___security_init_cookie`
- size: `152`
- prototype: `void __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1004d100`

## callees

- `0x1004dad9`

## import_xrefs

- `KERNEL32!QueryPerformanceCounter` at `0x1004db3c`
- `KERNEL32!QueryPerformanceCounter` at `0x1004db3c`
- `KERNEL32!GetCurrentThreadId` at `0x1004db1e`
- `KERNEL32!GetCurrentThreadId` at `0x1004db1e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004db06`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x1004db06`
- `KERNEL32!GetTickCount` at `0x1004db27`
- `KERNEL32!GetTickCount` at `0x1004db27`
- `KERNEL32!GetCurrentProcessId` at `0x1004db15`
- `KERNEL32!GetCurrentProcessId` at `0x1004db15`

## pseudocode

```c
void __cdecl __security_init_cookie()
{
  uintptr_t v0; // eax
  uintptr_t v1; // ecx
  LARGE_INTEGER PerformanceCount; // [esp+0h] [ebp-14h] BYREF
  _FILETIME SystemTimeAsFileTime; // [esp+8h] [ebp-Ch] BYREF
  DWORD v4; // [esp+10h] [ebp-4h] BYREF

  v0 = __security_cookie;
  SystemTimeAsFileTime = 0;
  if ( __security_cookie == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v4 = SystemTimeAsFileTime.dwLowDateTime ^ SystemTimeAsFileTime.dwHighDateTime;
    v4 ^= GetCurrentProcessId();
    v4 ^= GetCurrentThreadId();
    v4 ^= (unsigned int)&v4 ^ GetTickCount();
    QueryPerformanceCounter(&PerformanceCount);
    v0 = v4 ^ PerformanceCount.LowPart ^ PerformanceCount.HighPart;
    v1 = v0;
    if ( v0 == -1153374642 || (__security_cookie & 0xFFFF0000) == 0 )
    {
      v0 = -1153374641;
      v1 = -1153374641;
    }
    __security_cookie = v1;
  }
  __security_cookie_complement = ~v0;
}

```

## disassembly

```asm
0x1004dad9  mov     edi, edi
0x1004dadb  push    ebp
0x1004dadc  mov     ebp, esp
0x1004dade  sub     esp, 14h
0x1004dae1  mov     eax, ___security_cookie
0x1004dae6  xorps   xmm0, xmm0
0x1004dae9  push    esi
0x1004daea  push    edi
0x1004daeb  mov     edi, 0BB40E64Eh
0x1004daf0  movlpd  qword ptr [ebp+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x1004daf5  mov     esi, 0FFFF0000h
0x1004dafa  cmp     eax, edi
0x1004dafc  jz      short loc_1004DB02
0x1004dafe  test    esi, eax
0x1004db00  jnz     short loc_1004DB66
0x1004db02  lea     eax, [ebp+SystemTimeAsFileTime]
0x1004db05  push    eax; lpSystemTimeAsFileTime
0x1004db06  call    ds:__imp__GetSystemTimeAsFileTime@4; GetSystemTimeAsFileTime(x)
0x1004db0c  mov     eax, [ebp+SystemTimeAsFileTime.dwHighDateTime]
0x1004db0f  xor     eax, [ebp+SystemTimeAsFileTime.dwLowDateTime]
0x1004db12  mov     [ebp+var_4], eax
0x1004db15  call    ds:__imp__GetCurrentProcessId@0; GetCurrentProcessId()
0x1004db1b  xor     [ebp+var_4], eax
0x1004db1e  call    ds:__imp__GetCurrentThreadId@0; GetCurrentThreadId()
0x1004db24  xor     [ebp+var_4], eax
0x1004db27  call    ds:__imp__GetTickCount@0; GetTickCount()
0x1004db2d  xor     eax, [ebp+var_4]
0x1004db30  lea     ecx, [ebp+var_4]
0x1004db33  xor     eax, ecx
0x1004db35  mov     [ebp+var_4], eax
0x1004db38  lea     eax, [ebp+PerformanceCount]
0x1004db3b  push    eax; lpPerformanceCount
0x1004db3c  call    ds:__imp__QueryPerformanceCounter@4; QueryPerformanceCounter(x)
0x1004db42  mov     eax, dword ptr [ebp+PerformanceCount+4]
0x1004db45  xor     eax, dword ptr [ebp+PerformanceCount]
0x1004db48  xor     eax, [ebp+var_4]
0x1004db4b  mov     ecx, eax
0x1004db4d  cmp     eax, edi
0x1004db4f  jz      short loc_1004DB59
0x1004db51  test    ___security_cookie, esi
0x1004db57  jnz     short loc_1004DB60
0x1004db59  mov     eax, 0BB40E64Fh
0x1004db5e  mov     ecx, eax
0x1004db60  mov     ___security_cookie, ecx
0x1004db66  not     eax
0x1004db68  pop     edi
0x1004db69  mov     ___security_cookie_complement, eax
0x1004db6e  pop     esi
0x1004db6f  leave
0x1004db70  retn
```
