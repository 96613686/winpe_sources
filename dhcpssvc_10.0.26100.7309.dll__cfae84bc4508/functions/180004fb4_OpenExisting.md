# OpenExisting

- ea: `0x180004fb4`
- end: `0x1800050bf`
- name: `OpenExisting`
- size: `267`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180003548`
- `0x1800672f0`

## callees

- `0x180004fb4`
- `0x1800058cc`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x180005049`
- `KERNEL32!CompareFileTime` at `0x180005049`
- `KERNEL32!FindFirstFileW` at `0x180004ff2`
- `KERNEL32!FindFirstFileW` at `0x180004ff2`
- `KERNEL32!FindClose` at `0x18000500b`
- `KERNEL32!FindClose` at `0x18000500b`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005024`
- `KERNEL32!GetSystemTimeAsFileTime` at `0x180005024`
- `KERNEL32!DeleteFileW` at `0x180005097`
- `KERNEL32!DeleteFileW` at `0x180005097`

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
0x180004fcf  and     qword ptr [rsp+298h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180004fd5  mov     rbx, rcx
0x180004fd8  lea     rcx, [rsp+298h+FindFileData]; void *
0x180004fdd  xor     edx, edx; Val
0x180004fdf  mov     r8d, 250h; Size
0x180004fe5  call    memset_0
0x180004fea  lea     rdx, [rsp+298h+FindFileData]; lpFindFileData
0x180004fef  mov     rcx, rbx; lpFileName
0x180004ff2  call    cs:__imp_FindFirstFileW
0x180004ff9  nop     dword ptr [rax+rax+00h]
0x180004ffe  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005002  jz      loc_1800050A3
0x180005008  mov     rcx, rax; hFindFile
0x18000500b  call    cs:__imp_FindClose
0x180005012  nop     dword ptr [rax+rax+00h]
0x180005017  test    eax, eax
0x180005019  jz      loc_1800050A3
0x18000501f  lea     rcx, [rsp+298h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180005024  call    cs:__imp_GetSystemTimeAsFileTime
0x18000502b  nop     dword ptr [rax+rax+00h]
0x180005030  mov     rax, 0C92A69C000h
0x18000503a  lea     rdx, [rsp+298h+SystemTimeAsFileTime]; lpFileTime2
0x18000503f  sub     qword ptr [rsp+298h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180005044  lea     rcx, [rsp+298h+FindFileData.ftLastWriteTime]; lpFileTime1
0x180005049  call    cs:__imp_CompareFileTime
0x180005050  nop     dword ptr [rax+rax+00h]
0x180005055  test    eax, eax
0x180005057  js      short loc_180005094
0x180005059  mov     rcx, cs:WPP_GLOBAL_Control
0x180005060  lea     rax, WPP_GLOBAL_Control
0x180005067  cmp     rcx, rax
0x18000506a  jz      short loc_18000508D
0x18000506c  test    dword ptr [rcx+1Ch], 2000h
0x180005073  jz      short loc_18000508D
0x180005075  mov     rcx, [rcx+10h]
0x180005079  lea     r8, WPP_3f918084cf8d369c2c20a8a49a789173_Traceguids
0x180005080  mov     edx, 0Ah
0x180005085  mov     r9, rbx
0x180005088  call    WPP_SF_S
0x18000508d  mov     eax, 1
0x180005092  jmp     short loc_1800050A5
0x180005094  mov     rcx, rbx; lpFileName
0x180005097  call    cs:__imp_DeleteFileW
0x18000509e  nop     dword ptr [rax+rax+00h]
0x1800050a3  xor     eax, eax
0x1800050a5  mov     rcx, [rsp+298h+var_18]
0x1800050ad  xor     rcx, rsp; StackCookie
0x1800050b0  call    __security_check_cookie
0x1800050b5  add     rsp, 290h
0x1800050bc  pop     rbx
0x1800050bd  retn
```
