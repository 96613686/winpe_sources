# LogServerTime(NtTimeEpoch,__int64)

- ea: `0x1800171dc`
- end: `0x180017338`
- name: `?LogServerTime@@YAJUNtTimeEpoch@@_J@Z`
- size: `348`
- prototype: `__int64 __fastcall(FILETIME)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18001692c`

## callees

- `0x180006b48`
- `0x180014660`
- `0x1800148c4`
- `0x1800171dc`
- `0x18001a5e0`
- `0x18001a6a0`

## import_xrefs

- `KERNEL32!FileTimeToSystemTime` at `0x18001724a`
- `KERNEL32!FileTimeToSystemTime` at `0x18001724a`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180017232`
- `KERNEL32!FileTimeToLocalFileTime` at `0x180017232`
- `KERNEL32!GetDateFormatW` at `0x18001727b`
- `KERNEL32!GetDateFormatW` at `0x18001727b`
- `KERNEL32!GetTimeFormatW` at `0x1800172a3`
- `KERNEL32!GetTimeFormatW` at `0x1800172a3`

## string_xrefs

- `0x1800172dd`: `base\diagnosis\ra\racommon\src\ratimeutils.cpp`

## pseudocode

```c
__int64 __fastcall LogServerTime(FILETIME a1)
{
  unsigned int v1; // ebx
  signed int v2; // eax
  const struct _EVENT_DESCRIPTOR *v3; // rdx
  CEventLogger *v4; // rcx
  struct _FILETIME LocalFileTime; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME FileTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR TimeStr[1024]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR DateStr[1024]; // [rsp+850h] [rbp+750h] BYREF
  unsigned __int16 v11[1024]; // [rsp+1050h] [rbp+F50h] BYREF

  FileTime = a1;
  LocalFileTime = 0;
  v1 = -2147467259;
  SystemTime = 0;
  if ( FileTimeToLocalFileTime(&FileTime, &LocalFileTime)
    && FileTimeToSystemTime(&LocalFileTime, &SystemTime)
    && GetDateFormatW(0x400u, 0x40u, &SystemTime, 0, DateStr, 1024)
    && GetTimeFormatW(0x400u, 0, &SystemTime, 0, TimeStr, 1024) )
  {
    v2 = StringCchPrintfW(v11, 0x400u, L"%s %s", DateStr, TimeStr);
    v1 = v2;
    if ( v2 >= 0 )
    {
      CEventLogger::LogEvent(v4, &NTPServer_Current_Time, v11);
      return 0;
    }
    else
    {
      CEventLogger::LogError(
        v4,
        v3,
        L"base\\diagnosis\\ra\\racommon\\src\\ratimeutils.cpp",
        0x1E6u,
        L"LogServerTime",
        v2);
    }
  }
  return v1;
}

```

## disassembly

```asm
0x1800171dc  mov     [rsp-8+arg_8], rbx
0x1800171e1  mov     [rsp-8+arg_10], rdi
0x1800171e6  push    rbp
0x1800171e7  lea     rbp, [rsp-1760h]
0x1800171ef  mov     eax, 1860h
0x1800171f4  call    _alloca_probe
0x1800171f9  sub     rsp, rax
0x1800171fc  mov     rax, cs:__security_cookie
0x180017203  xor     rax, rsp
0x180017206  mov     [rbp+1760h+var_10], rax
0x18001720d  mov     qword ptr [rsp+1860h+FileTime.dwLowDateTime], rcx
0x180017212  lea     rdx, [rsp+1860h+LocalFileTime]; lpLocalFileTime
0x180017217  xorps   xmm0, xmm0
0x18001721a  mov     qword ptr [rsp+1860h+LocalFileTime.dwLowDateTime], 0
0x180017223  lea     rcx, [rsp+1860h+FileTime]; lpFileTime
0x180017228  mov     ebx, 80004005h
0x18001722d  movups  xmmword ptr [rsp+1860h+SystemTime.wYear], xmm0
0x180017232  call    cs:__imp_FileTimeToLocalFileTime
0x180017238  test    eax, eax
0x18001723a  jz      loc_180017312
0x180017240  lea     rdx, [rsp+1860h+SystemTime]; lpSystemTime
0x180017245  lea     rcx, [rsp+1860h+LocalFileTime]; lpFileTime
0x18001724a  call    cs:__imp_FileTimeToSystemTime
0x180017250  test    eax, eax
0x180017252  jz      loc_180017312
0x180017258  xor     r9d, r9d; lpFormat
0x18001725b  lea     rax, [rbp+1760h+DateStr]
0x180017262  mov     edi, 400h
0x180017267  lea     r8, [rsp+1860h+SystemTime]; lpDate
0x18001726c  mov     [rsp+1860h+cchDate], edi; cchDate
0x180017270  mov     ecx, edi; Locale
0x180017272  mov     [rsp+1860h+lpDateStr], rax; lpDateStr
0x180017277  lea     edx, [r9+40h]; dwFlags
0x18001727b  call    cs:__imp_GetDateFormatW
0x180017281  test    eax, eax
0x180017283  jz      loc_180017312
0x180017289  lea     rax, [rsp+1860h+TimeStr]
0x18001728e  mov     [rsp+1860h+cchDate], edi; cchTime
0x180017292  xor     r9d, r9d; lpFormat
0x180017295  mov     [rsp+1860h+lpDateStr], rax; lpTimeStr
0x18001729a  lea     r8, [rsp+1860h+SystemTime]; lpTime
0x18001729f  xor     edx, edx; dwFlags
0x1800172a1  mov     ecx, edi; Locale
0x1800172a3  call    cs:__imp_GetTimeFormatW
0x1800172a9  test    eax, eax
0x1800172ab  jz      short loc_180017312
0x1800172ad  lea     rax, [rsp+1860h+TimeStr]
0x1800172b2  mov     edx, edi; unsigned __int64
0x1800172b4  lea     r9, [rbp+1760h+DateStr]
0x1800172bb  mov     [rsp+1860h+lpDateStr], rax
0x1800172c0  lea     r8, aSS_0; "%s %s"
0x1800172c7  lea     rcx, [rbp+1760h+var_810]; unsigned __int16 *
0x1800172ce  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800172d3  mov     ebx, eax
0x1800172d5  test    eax, eax
0x1800172d7  jns     short loc_1800172FD
0x1800172d9  mov     [rsp+1860h+cchDate], eax; unsigned int
0x1800172dd  lea     r8, aBaseDiagnosisR_3; "base\\diagnosis\\ra\\racommon\\src\\rat"...
0x1800172e4  lea     rax, aLogservertime; "LogServerTime"
0x1800172eb  mov     r9d, 1E6h; unsigned int
0x1800172f1  mov     [rsp+1860h+lpDateStr], rax; unsigned __int16 *
0x1800172f6  call    ?LogError@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAGI1I@Z; CEventLogger::LogError(_EVENT_DESCRIPTOR const *,ushort *,uint,ushort *,uint)
0x1800172fb  jmp     short loc_180017312
0x1800172fd  lea     r8, [rbp+1760h+var_810]; unsigned __int16 *
0x180017304  lea     rdx, NTPServer_Current_Time; struct _EVENT_DESCRIPTOR *
0x18001730b  call    ?LogEvent@CEventLogger@@QEAAJPEBU_EVENT_DESCRIPTOR@@PEAG@Z; CEventLogger::LogEvent(_EVENT_DESCRIPTOR const *,ushort *)
0x180017310  xor     ebx, ebx
0x180017312  mov     eax, ebx
0x180017314  mov     rcx, [rbp+1760h+var_10]
0x18001731b  xor     rcx, rsp; StackCookie
0x18001731e  call    __security_check_cookie
0x180017323  lea     r11, [rsp+1860h+var_s0]
0x18001732b  mov     rbx, [r11+18h]
0x18001732f  mov     rdi, [r11+20h]
0x180017333  mov     rsp, r11
0x180017336  pop     rbp
0x180017337  retn
```
