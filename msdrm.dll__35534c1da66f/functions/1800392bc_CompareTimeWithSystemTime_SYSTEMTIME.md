# CompareTimeWithSystemTime(_SYSTEMTIME *)

- ea: `0x1800392bc`
- end: `0x180039347`
- name: `?CompareTimeWithSystemTime@@YAHPEAU_SYSTEMTIME@@@Z`
- size: `139`
- prototype: `__int64 __fastcall(SYSTEMTIME *lpSystemTime)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dd1c`
- `0x180039c80`
- `0x18003a29c`
- `0x18003a3f8`
- `0x18003b018`

## callees

- `0x1800392bc`
- `0x18005bdc0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180039329`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180039329`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180039303`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180039315`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180039303`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180039315`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800392f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x1800392f3`

## pseudocode

```c
LONG __fastcall CompareTimeWithSystemTime(SYSTEMTIME *lpSystemTime)
{
  struct _FILETIME FileTime; // [rsp+20h] [rbp-38h] BYREF
  FILETIME FileTime1; // [rsp+28h] [rbp-30h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+30h] [rbp-28h] BYREF

  FileTime = 0;
  FileTime1 = 0;
  SystemTime = 0;
  GetSystemTime(&SystemTime);
  if ( SystemTimeToFileTime(&SystemTime, &FileTime) && SystemTimeToFileTime(lpSystemTime, &FileTime1) )
    return CompareFileTime(&FileTime1, &FileTime);
  else
    return -1;
}

```

## disassembly

```asm
0x1800392bc  push    rbx
0x1800392be  sub     rsp, 50h
0x1800392c2  mov     rax, cs:__security_cookie
0x1800392c9  xor     rax, rsp
0x1800392cc  mov     [rsp+58h+var_18], rax
0x1800392d1  mov     rbx, rcx
0x1800392d4  mov     qword ptr [rsp+58h+FileTime.dwLowDateTime], 0
0x1800392dd  xorps   xmm0, xmm0
0x1800392e0  mov     qword ptr [rsp+58h+FileTime1.dwLowDateTime], 0
0x1800392e9  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x1800392ee  movups  xmmword ptr [rsp+58h+SystemTime.wYear], xmm0
0x1800392f3  call    cs:__imp_GetSystemTime
0x1800392f9  lea     rdx, [rsp+58h+FileTime]; lpFileTime
0x1800392fe  lea     rcx, [rsp+58h+SystemTime]; lpSystemTime
0x180039303  call    cs:__imp_SystemTimeToFileTime
0x180039309  test    eax, eax
0x18003930b  jz      short loc_180039331
0x18003930d  lea     rdx, [rsp+58h+FileTime1]; lpFileTime
0x180039312  mov     rcx, rbx; lpSystemTime
0x180039315  call    cs:__imp_SystemTimeToFileTime
0x18003931b  test    eax, eax
0x18003931d  jz      short loc_180039331
0x18003931f  lea     rdx, [rsp+58h+FileTime]; lpFileTime2
0x180039324  lea     rcx, [rsp+58h+FileTime1]; lpFileTime1
0x180039329  call    cs:__imp_CompareFileTime
0x18003932f  jmp     short loc_180039334
0x180039331  or      eax, 0FFFFFFFFh
0x180039334  mov     rcx, [rsp+58h+var_18]
0x180039339  xor     rcx, rsp; StackCookie
0x18003933c  call    __security_check_cookie
0x180039341  add     rsp, 50h
0x180039345  pop     rbx
0x180039346  retn
```
