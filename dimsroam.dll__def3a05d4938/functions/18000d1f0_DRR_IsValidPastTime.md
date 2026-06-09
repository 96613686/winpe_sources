# DRR_IsValidPastTime

- ea: `0x18000d1f0`
- end: `0x18000d2bf`
- name: `DRR_IsValidPastTime`
- size: `207`
- prototype: `__int64 __fastcall(FILETIME *lpFileTime1)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800036c8`

## callees

- `0x18000d1f0`
- `0x18000d8d0`

## import_xrefs

- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d24a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d24a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d254`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18000d254`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d284`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d295`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d284`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d295`

## pseudocode

```c
__int64 __fastcall DRR_IsValidPastTime(FILETIME *lpFileTime1)
{
  unsigned int v2; // ebx
  DWORD v3; // ecx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-30h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-28h] BYREF
  SYSTEMTIME SystemTime; // [rsp+30h] [rbp-20h] BYREF

  SystemTimeAsFileTime = 0;
  SystemTime.wYear = 1990;
  *(_DWORD *)&SystemTime.wMonth = 1;
  SystemTime.wMilliseconds = 0;
  v2 = 1;
  FileTime = 0;
  *(_QWORD *)&SystemTime.wDay = 1;
  SystemTimeToFileTime(&SystemTime, &FileTime);
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  v3 = SystemTimeAsFileTime.dwHighDateTime + 201;
  SystemTimeAsFileTime.dwHighDateTime += 201;
  SystemTimeAsFileTime.dwLowDateTime += 711573504;
  if ( SystemTimeAsFileTime.dwLowDateTime < 0x2A69C000 )
    SystemTimeAsFileTime.dwHighDateTime = v3 + 1;
  if ( CompareFileTime(lpFileTime1, &FileTime) < 0 || CompareFileTime(lpFileTime1, &SystemTimeAsFileTime) >= 0 )
    return 0;
  return v2;
}

```

## disassembly

```asm
0x18000d1f0  mov     [rsp-8+arg_8], rbx
0x18000d1f5  mov     [rsp-8+arg_10], rdi
0x18000d1fa  push    rbp
0x18000d1fb  mov     rbp, rsp
0x18000d1fe  sub     rsp, 50h
0x18000d202  mov     rax, cs:__security_cookie
0x18000d209  xor     rax, rsp
0x18000d20c  mov     [rbp+var_10], rax
0x18000d210  mov     eax, 7C6h
0x18000d215  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18000d21d  mov     [rbp+SystemTime.wYear], ax
0x18000d221  lea     rdx, [rbp+FileTime]; lpFileTime
0x18000d225  xor     eax, eax
0x18000d227  mov     dword ptr [rbp+SystemTime.wMonth], 1
0x18000d22e  mov     rdi, rcx
0x18000d231  mov     [rbp+SystemTime.wMilliseconds], ax
0x18000d235  mov     ebx, 1
0x18000d23a  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18000d242  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x18000d246  mov     qword ptr [rbp+SystemTime.wDay], rbx
0x18000d24a  call    cs:__imp_SystemTimeToFileTime
0x18000d250  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18000d254  call    cs:__imp_GetSystemTimeAsFileTime
0x18000d25a  mov     ecx, [rbp+SystemTimeAsFileTime.dwHighDateTime]
0x18000d25d  mov     edx, 2A69C000h
0x18000d262  mov     eax, [rbp+SystemTimeAsFileTime.dwLowDateTime]
0x18000d265  add     ecx, 0C9h
0x18000d26b  add     eax, edx
0x18000d26d  mov     [rbp+SystemTimeAsFileTime.dwHighDateTime], ecx
0x18000d270  mov     [rbp+SystemTimeAsFileTime.dwLowDateTime], eax
0x18000d273  cmp     eax, edx
0x18000d275  jnb     short loc_18000D27D
0x18000d277  lea     eax, [rcx+1]
0x18000d27a  mov     [rbp+SystemTimeAsFileTime.dwHighDateTime], eax
0x18000d27d  lea     rdx, [rbp+FileTime]; lpFileTime2
0x18000d281  mov     rcx, rdi; lpFileTime1
0x18000d284  call    cs:__imp_CompareFileTime
0x18000d28a  test    eax, eax
0x18000d28c  js      short loc_18000D29F
0x18000d28e  lea     rdx, [rbp+SystemTimeAsFileTime]; lpFileTime2
0x18000d292  mov     rcx, rdi; lpFileTime1
0x18000d295  call    cs:__imp_CompareFileTime
0x18000d29b  test    eax, eax
0x18000d29d  js      short loc_18000D2A1
0x18000d29f  xor     ebx, ebx
0x18000d2a1  mov     eax, ebx
0x18000d2a3  mov     rcx, [rbp+var_10]
0x18000d2a7  xor     rcx, rsp; StackCookie
0x18000d2aa  call    __security_check_cookie
0x18000d2af  mov     rbx, [rsp+50h+arg_8]
0x18000d2b4  mov     rdi, [rsp+50h+arg_10]
0x18000d2b9  add     rsp, 50h
0x18000d2bd  pop     rbp
0x18000d2be  retn
```
