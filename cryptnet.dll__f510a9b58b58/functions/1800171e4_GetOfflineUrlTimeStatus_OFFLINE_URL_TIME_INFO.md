# GetOfflineUrlTimeStatus(_OFFLINE_URL_TIME_INFO *)

- ea: `0x1800171e4`
- end: `0x180017266`
- name: `?GetOfflineUrlTimeStatus@@YAJPEAU_OFFLINE_URL_TIME_INFO@@@Z`
- size: `130`
- prototype: `__int64 __fastcall(struct _OFFLINE_URL_TIME_INFO *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180007cc0`
- `0x18000b090`
- `0x18000be30`
- `0x1800170e0`

## callees

- `0x1800171e4`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017214`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180017214`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017223`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001724d`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180017223`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x18001724d`

## pseudocode

```c
__int64 __fastcall GetOfflineUrlTimeStatus(struct _OFFLINE_URL_TIME_INFO *a1)
{
  bool v1; // zf
  struct _FILETIME SystemTimeAsFileTime; // [rsp+30h] [rbp+8h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp+10h] BYREF

  v1 = *(_DWORD *)a1 == 0;
  SystemTimeAsFileTime = 0;
  if ( v1 )
    return 1;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  if ( CompareFileTime(&SystemTimeAsFileTime, (const FILETIME *)((char *)a1 + 4)) < 0 )
  {
    FileTime2 = (FILETIME)(*(_QWORD *)&SystemTimeAsFileTime + 21000000000LL);
    if ( CompareFileTime((const FILETIME *)((char *)a1 + 4), &FileTime2) <= 0 )
      return 0xFFFFFFFFLL;
    *(_DWORD *)a1 = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1800171e4  mov     [rsp+arg_10], rbx
0x1800171e9  push    rdi
0x1800171ea  sub     rsp, 20h
0x1800171ee  cmp     dword ptr [rcx], 0
0x1800171f1  mov     rbx, rcx
0x1800171f4  mov     qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime], 0
0x1800171fd  jnz     short loc_18001720F
0x1800171ff  mov     eax, 1
0x180017204  mov     rbx, [rsp+28h+arg_10]
0x180017209  add     rsp, 20h
0x18001720d  pop     rdi
0x18001720e  retn
0x18001720f  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180017214  call    cs:__imp_GetSystemTimeAsFileTime
0x18001721a  lea     rdx, [rbx+4]; lpFileTime2
0x18001721e  lea     rcx, [rsp+28h+SystemTimeAsFileTime]; lpFileTime1
0x180017223  call    cs:__imp_CompareFileTime
0x180017229  test    eax, eax
0x18001722b  jns     short loc_180017262
0x18001722d  mov     rdx, qword ptr [rsp+28h+SystemTimeAsFileTime.dwLowDateTime]
0x180017232  mov     rcx, 4E3B29200h
0x18001723c  add     rdx, rcx
0x18001723f  lea     rcx, [rbx+4]; lpFileTime1
0x180017243  mov     qword ptr [rsp+28h+FileTime2.dwLowDateTime], rdx
0x180017248  lea     rdx, [rsp+28h+FileTime2]; lpFileTime2
0x18001724d  call    cs:__imp_CompareFileTime
0x180017253  test    eax, eax
0x180017255  jg      short loc_18001725C
0x180017257  or      eax, 0FFFFFFFFh
0x18001725a  jmp     short loc_180017204
0x18001725c  mov     dword ptr [rbx], 0
0x180017262  xor     eax, eax
0x180017264  jmp     short loc_180017204
```
