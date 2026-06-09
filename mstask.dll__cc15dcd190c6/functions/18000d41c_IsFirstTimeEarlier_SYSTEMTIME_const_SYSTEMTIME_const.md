# IsFirstTimeEarlier(_SYSTEMTIME const *,_SYSTEMTIME const *)

- ea: `0x18000d41c`
- end: `0x18000d469`
- name: `?IsFirstTimeEarlier@@YAHPEBU_SYSTEMTIME@@0@Z`
- size: `77`
- prototype: `int(const struct _SYSTEMTIME *, const struct _SYSTEMTIME *)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000cff4`
- `0x18000e7f8`
- `0x18000eef4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d45a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18000d45a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d43c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d44a`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d43c`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000d44a`

## pseudocode

```c
__int64 __fastcall IsFirstTimeEarlier(const struct _SYSTEMTIME *a1, const struct _SYSTEMTIME *a2)
{
  FILETIME FileTime2; // [rsp+40h] [rbp+18h] BYREF
  struct _FILETIME FileTime; // [rsp+48h] [rbp+20h] BYREF

  FileTime = 0;
  FileTime2 = 0;
  SystemTimeToFileTime(a1, &FileTime);
  SystemTimeToFileTime(a2, &FileTime2);
  return (unsigned int)CompareFileTime(&FileTime, &FileTime2) >> 31;
}

```

## disassembly

```asm
0x18000d41c  push    rbx
0x18000d41e  sub     rsp, 20h
0x18000d422  mov     rbx, rdx
0x18000d425  mov     qword ptr [rsp+28h+FileTime.dwLowDateTime], 0
0x18000d42e  lea     rdx, [rsp+28h+FileTime]; lpFileTime
0x18000d433  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], 0
0x18000d43c  call    cs:__imp_SystemTimeToFileTime
0x18000d442  lea     rdx, [rsp+28h+FileTime2]; lpFileTime
0x18000d447  mov     rcx, rbx; lpSystemTime
0x18000d44a  call    cs:__imp_SystemTimeToFileTime
0x18000d450  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x18000d455  lea     rcx, [rsp+28h+FileTime]; lpFileTime1
0x18000d45a  call    cs:__imp_CompareFileTime
0x18000d460  shr     eax, 1Fh
0x18000d463  add     rsp, 20h
0x18000d467  pop     rbx
0x18000d468  retn
```
