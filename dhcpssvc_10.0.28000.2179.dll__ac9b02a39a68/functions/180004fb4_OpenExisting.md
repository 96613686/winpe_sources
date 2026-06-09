# OpenExisting

- ea: `0x180004fb4`
- end: `0x1800050c2`
- name: `OpenExisting`
- size: `270`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000353c`
- `0x180067094`

## callees

- `0x180004fb4`
- `0x1800058bc`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x18000504c`
- `KERNEL32!CompareFileTime` at `0x18000504c`
- `KERNEL32!FindFirstFileW` at `0x180004ff5`
- `KERNEL32!FindFirstFileW` at `0x180004ff5`
- `KERNEL32!FindClose` at `0x18000500e`
- `KERNEL32!FindClose` at `0x18000500e`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005027`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005027`
- `KERNEL32!DeleteFileW` at `0x18000509a`
- `KERNEL32!DeleteFileW` at `0x18000509a`

## pseudocode

```c
__int64 __fastcall OpenExisting(LPCWSTR lpFileName)
{
  HANDLE FirstFileW; // rax
  struct _FILETIME SystemTimeAsFileTime; // [rsp+20h] [rbp-278h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+30h] [rbp-268h] BYREF

  SystemTimeAsFileTime = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = FindFirstFileW(lpFileName, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL || !FindClose(FirstFileW) )
    return 0;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
  *(_QWORD *)&SystemTimeAsFileTime -= 864000000000LL;
  if ( CompareFileTime(&FindFileData.ftLastWriteTime, &SystemTimeAsFileTime) < 0 )
  {
    DeleteFileW(lpFileName);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x2000) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids, lpFileName);
  return 1;
}

```

## disassembly

```asm
0x180004fb4  push    rbx
0x180004fb6  sub     rsp, 290h
0x180004fbd  mov     rax, cs:__security_cookie
0x180004fc4  xor     rax, rsp
0x180004fc7  mov     [rsp+298h+var_18], rax
0x180004fcf  mov     rbx, rcx
0x180004fd2  mov     qword ptr [rsp+298h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180004fdb  lea     rcx, [rsp+298h+FindFileData]; void *
0x180004fe0  xor     edx, edx; Val
0x180004fe2  mov     r8d, 250h; Size
0x180004fe8  call    memset_0
0x180004fed  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x180004ff2  mov     rcx, rbx; lpFileName
0x180004ff5  call    cs:__imp_FindFirstFileW
0x180004ffc  nop     dword ptr [rax+rax+00h]
0x180005001  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005005  jz      loc_1800050A6
0x18000500b  mov     rcx, rax; hFindFile
0x18000500e  call    cs:__imp_FindClose
0x180005015  nop     dword ptr [rax+rax+00h]
0x18000501a  test    eax, eax
0x18000501c  jz      loc_1800050A6
0x180005022  lea     rcx, [rsp+298h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005027  call    cs:__imp_GetSystemTimeAsFileTime
0x18000502e  nop     dword ptr [rax+rax+00h]
0x180005033  mov     rax, 0C92A69C000h
0x18000503d  lea     rdx, [rsp+298h+SystemTimeAsFileTime]; lpFileTime2
0x180005042  sub     qword ptr [rsp+298h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005047  lea     rcx, [rsp+298h+FindFileData.ftLastWriteTime]; lpFileTime1
0x18000504c  call    cs:__imp_CompareFileTime
0x180005053  nop     dword ptr [rax+rax+00h]
0x180005058  test    eax, eax
0x18000505a  js      short loc_180005097
0x18000505c  mov     rcx, cs:WPP_GLOBAL_Control
0x180005063  lea     rax, WPP_GLOBAL_Control
0x18000506a  cmp     rcx, rax
0x18000506d  jz      short loc_180005090
0x18000506f  test    dword ptr [rcx+1Ch], 2000h
0x180005076  jz      short loc_180005090
0x180005078  mov     rcx, [rcx+10h]
0x18000507c  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180005083  mov     edx, 0Ah
0x180005088  mov     r9, rbx
0x18000508b  call    WPP_SF_S
0x180005090  mov     eax, 1
0x180005095  jmp     short loc_1800050A8
0x180005097  mov     rcx, rbx; lpFileName
0x18000509a  call    cs:__imp_DeleteFileW
0x1800050a1  nop     dword ptr [rax+rax+00h]
0x1800050a6  xor     eax, eax
0x1800050a8  mov     rcx, [rsp+298h+var_18]
0x1800050b0  xor     rcx, rsp; StackCookie
0x1800050b3  call    __security_check_cookie
0x1800050b8  add     rsp, 290h
0x1800050bf  pop     rbx
0x1800050c0  retn
```
