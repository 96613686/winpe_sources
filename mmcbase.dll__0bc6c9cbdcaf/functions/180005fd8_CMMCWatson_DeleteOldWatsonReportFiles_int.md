# CMMCWatson::DeleteOldWatsonReportFiles(int)

- ea: `0x180005fd8`
- end: `0x18000631c`
- name: `?DeleteOldWatsonReportFiles@CMMCWatson@@AEAA_NH@Z`
- size: `836`
- prototype: `char __fastcall(CMMCWatson *this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180005ef0`

## callees

- `0x180005fd8`
- `0x180008630`
- `0x18000bd34`
- `0x18000cbfc`
- `0x18001b522`
- `0x18001b550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000624e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006181`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000624e`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800061c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800061db`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800061eb`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800061c7`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800061db`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800061eb`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180006172`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180006172`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800062bf`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800062bf`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006232`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180006232`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180006240`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180006240`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800060da`
- `api-ms-win-core-file-l1-2-3!GetTempPath2W` at `0x1800060da`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000605e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x18000605e`
- `KERNEL32!SystemTimeToFileTime` at `0x18000606e`
- `KERNEL32!SystemTimeToFileTime` at `0x18000606e`

## pseudocode

```c
char __fastcall CMMCWatson::DeleteOldWatsonReportFiles(CMMCWatson *this)
{
  char v1; // di
  __int64 v2; // rcx
  __int64 v3; // rdx
  __int64 v4; // rax
  int v5; // eax
  HANDLE FirstFileW; // rbx
  unsigned int v7; // eax
  int v8; // eax
  _FILETIME FileTime; // [rsp+30h] [rbp-D0h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-C8h] BYREF
  _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-C0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v14[528]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF
  WCHAR v16[264]; // [rsp+6C0h] [rbp+5C0h] BYREF

  FileTime = 0;
  v1 = 0;
  SystemTime = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  memset_0(v14, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  FileTime2 = 0;
  GetSystemTime(&SystemTime);
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      return v1;
    v3 = 35;
    goto LABEL_36;
  }
  v4 = *(_QWORD *)&FileTime - 1152000000000LL;
  FileTime.dwLowDateTime -= 948764672;
  FileTime.dwHighDateTime = HIDWORD(v4);
  if ( (unsigned int)GetTempPath2W(260, v14) - 1 > 0x102 )
  {
    v2 = WPP_GLOBAL_Control;
    if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || *(_BYTE *)(WPP_GLOBAL_Control + 25LL) < 2u )
      return v1;
    v3 = 36;
LABEL_36:
    WPP_SF_(*(_QWORD *)(v2 + 16), v3, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
    return v1;
  }
  v5 = StringCchPrintfW(FileName, 0x104u, L"%s%s????????.%s", v14, L"mmc", L"xml");
  if ( v5 < 0 )
  {
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        37,
        WPP_bb31105b28713e810f7e3195fae1a055_Traceguids,
        (unsigned int)v5);
    return v1;
  }
  FirstFileW = FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    while ( 1 )
    {
      if ( CompareFileTime(&FindFileData.ftLastWriteTime, &FileTime2) )
      {
        v7 = (unsigned int)CompareFileTime(&FindFileData.ftLastWriteTime, &FileTime) >> 31;
      }
      else
      {
        if ( CompareFileTime(&FindFileData.ftLastAccessTime, &FileTime) >= 0 )
          goto LABEL_23;
        LOBYTE(v7) = 1;
      }
      if ( (_BYTE)v7 )
      {
        v8 = StringCchPrintfW(v16, 0x104u, L"%s%s", v14, FindFileData.cFileName);
        if ( v8 < 0 )
        {
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
            WPP_SF_d(
              *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
              39,
              WPP_bb31105b28713e810f7e3195fae1a055_Traceguids,
              (unsigned int)v8);
LABEL_32:
          FindClose(FirstFileW);
          return v1;
        }
        DeleteFileW(v16);
      }
LABEL_23:
      if ( !FindNextFileW(FirstFileW, &FindFileData) )
      {
        if ( GetLastError() == 18 )
        {
          v1 = 1;
        }
        else if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 40, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids);
        }
        goto LABEL_32;
      }
    }
  }
  if ( GetLastError() == 18 )
    return 1;
  v2 = WPP_GLOBAL_Control;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *(_BYTE *)(WPP_GLOBAL_Control + 25LL) >= 2u )
  {
    v3 = 38;
    goto LABEL_36;
  }
  return v1;
}

```

## disassembly

```asm
0x180005fd8  mov     [rsp-8+arg_0], rbx
0x180005fdd  mov     [rsp-8+arg_8], rdi
0x180005fe2  push    rbp
0x180005fe3  lea     rbp, [rsp-7E0h]
0x180005feb  sub     rsp, 8E0h
0x180005ff2  mov     rax, cs:__security_cookie
0x180005ff9  xor     rax, rsp
0x180005ffc  mov     [rbp+7E0h+var_10], rax
0x180006003  xorps   xmm0, xmm0
0x180006006  mov     qword ptr [rsp+8E0h+FileTime.dwLowDateTime], 0
0x18000600f  xor     edx, edx; Val
0x180006011  lea     rcx, [rsp+8E0h+FindFileData]; void *
0x180006016  mov     r8d, 250h; Size
0x18000601c  xor     dil, dil
0x18000601f  movups  xmmword ptr [rsp+8E0h+SystemTime.wYear], xmm0
0x180006024  call    memset_0
0x180006029  mov     ebx, 208h
0x18000602e  lea     rcx, [rbp+7E0h+var_640]; void *
0x180006035  mov     r8d, ebx; Size
0x180006038  xor     edx, edx; Val
0x18000603a  call    memset_0
0x18000603f  mov     r8d, ebx; Size
0x180006042  lea     rcx, [rbp+7E0h+FileName]; void *
0x180006049  xor     edx, edx; Val
0x18000604b  call    memset_0
0x180006050  lea     rcx, [rsp+8E0h+SystemTime]; lpSystemTime
0x180006055  mov     qword ptr [rsp+8E0h+FileTime2.dwLowDateTime], 0
0x18000605e  call    cs:__imp_GetSystemTime
0x180006064  lea     rdx, [rsp+8E0h+FileTime]; lpFileTime
0x180006069  lea     rcx, [rsp+8E0h+SystemTime]; lpSystemTime
0x18000606e  call    cs:__imp_SystemTimeToFileTime
0x180006074  test    eax, eax
0x180006076  jnz     short loc_1800060A3
0x180006078  mov     rcx, cs:WPP_GLOBAL_Control
0x18000607f  lea     rax, WPP_GLOBAL_Control
0x180006086  cmp     rcx, rax
0x180006089  jz      loc_1800062F5
0x18000608f  cmp     byte ptr [rcx+19h], 2
0x180006093  jb      loc_1800062F5
0x180006099  mov     edx, 23h ; '#'
0x18000609e  jmp     loc_1800062E5
0x1800060a3  mov     eax, [rsp+8E0h+FileTime.dwLowDateTime]
0x1800060a7  lea     rdx, [rbp+7E0h+var_640]
0x1800060ae  mov     ecx, [rsp+8E0h+FileTime.dwHighDateTime]
0x1800060b2  shl     rcx, 20h
0x1800060b6  or      rcx, rax
0x1800060b9  mov     rax, 0FFFFFEF3C7730000h
0x1800060c3  add     rcx, rax
0x1800060c6  mov     rax, rcx
0x1800060c9  mov     [rsp+8E0h+FileTime.dwLowDateTime], ecx
0x1800060cd  shr     rax, 20h
0x1800060d1  mov     ecx, 104h
0x1800060d6  mov     [rsp+8E0h+FileTime.dwHighDateTime], eax
0x1800060da  call    cs:__imp_GetTempPath2W
0x1800060e0  dec     eax
0x1800060e2  cmp     eax, 102h
0x1800060e7  ja      loc_1800062C7
0x1800060ed  lea     rax, aXml; "xml"
0x1800060f4  mov     edx, 104h; unsigned __int64
0x1800060f9  mov     [rsp+8E0h+var_8B8], rax
0x1800060fe  lea     r9, [rbp+7E0h+var_640]
0x180006105  lea     rax, aMmc; "mmc"
0x18000610c  lea     r8, aSSS_2; "%s%s????????.%s"
0x180006113  mov     [rsp+8E0h+var_8C0], rax
0x180006118  lea     rcx, [rbp+7E0h+FileName]; unsigned __int16 *
0x18000611f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006124  mov     r9d, eax
0x180006127  test    eax, eax
0x180006129  jns     short loc_180006166
0x18000612b  mov     rcx, cs:WPP_GLOBAL_Control
0x180006132  lea     rax, WPP_GLOBAL_Control
0x180006139  cmp     rcx, rax
0x18000613c  jz      loc_1800062F5
0x180006142  cmp     byte ptr [rcx+19h], 2
0x180006146  jb      loc_1800062F5
0x18000614c  mov     rcx, [rcx+10h]
0x180006150  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x180006157  mov     edx, 25h ; '%'
0x18000615c  call    WPP_SF_d
0x180006161  jmp     loc_1800062F5
0x180006166  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18000616b  lea     rcx, [rbp+7E0h+FileName]; lpFileName
0x180006172  call    cs:__imp_FindFirstFileW
0x180006178  mov     rbx, rax
0x18000617b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000617f  jnz     short loc_1800061BD
0x180006181  call    cs:__imp_GetLastError
0x180006187  cmp     eax, 12h
0x18000618a  jz      short loc_1800061B5
0x18000618c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006193  lea     rax, WPP_GLOBAL_Control
0x18000619a  cmp     rcx, rax
0x18000619d  jz      loc_1800062F5
0x1800061a3  cmp     byte ptr [rcx+19h], 2
0x1800061a7  jb      loc_1800062F5
0x1800061ad  lea     edx, [rbx+27h]
0x1800061b0  jmp     loc_1800062E5
0x1800061b5  mov     dil, 1
0x1800061b8  jmp     loc_1800062F5
0x1800061bd  lea     rdx, [rsp+8E0h+FileTime2]; lpFileTime2
0x1800061c2  lea     rcx, [rsp+8E0h+FindFileData.ftLastWriteTime]; lpFileTime1
0x1800061c7  call    cs:__imp_CompareFileTime
0x1800061cd  lea     rdx, [rsp+8E0h+FileTime]; lpFileTime2
0x1800061d2  test    eax, eax
0x1800061d4  jz      short loc_1800061E6
0x1800061d6  lea     rcx, [rsp+8E0h+FindFileData.ftLastWriteTime]; lpFileTime1
0x1800061db  call    cs:__imp_CompareFileTime
0x1800061e1  shr     eax, 1Fh
0x1800061e4  jmp     short loc_1800061F7
0x1800061e6  lea     rcx, [rsp+8E0h+FindFileData.ftLastAccessTime]; lpFileTime1
0x1800061eb  call    cs:__imp_CompareFileTime
0x1800061f1  test    eax, eax
0x1800061f3  jns     short loc_180006238
0x1800061f5  mov     al, 1
0x1800061f7  test    al, al
0x1800061f9  jz      short loc_180006238
0x1800061fb  lea     rax, [rsp+8E0h+FindFileData.cFileName]
0x180006200  mov     edx, 104h; unsigned __int64
0x180006205  lea     r9, [rbp+7E0h+var_640]
0x18000620c  mov     [rsp+8E0h+var_8C0], rax
0x180006211  lea     r8, aSS_0; "%s%s"
0x180006218  lea     rcx, [rbp+7E0h+var_220]; unsigned __int16 *
0x18000621f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180006224  mov     r9d, eax
0x180006227  test    eax, eax
0x180006229  js      short loc_180006289
0x18000622b  lea     rcx, [rbp+7E0h+var_220]; lpFileName
0x180006232  call    cs:__imp_DeleteFileW
0x180006238  lea     rdx, [rsp+8E0h+FindFileData]; lpFindFileData
0x18000623d  mov     rcx, rbx; hFindFile
0x180006240  call    cs:__imp_FindNextFileW
0x180006246  test    eax, eax
0x180006248  jnz     loc_1800061BD
0x18000624e  call    cs:__imp_GetLastError
0x180006254  cmp     eax, 12h
0x180006257  jz      short loc_1800062B9
0x180006259  mov     rcx, cs:WPP_GLOBAL_Control
0x180006260  lea     rax, WPP_GLOBAL_Control
0x180006267  cmp     rcx, rax
0x18000626a  jz      short loc_1800062BC
0x18000626c  cmp     byte ptr [rcx+19h], 2
0x180006270  jb      short loc_1800062BC
0x180006272  mov     rcx, [rcx+10h]
0x180006276  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x18000627d  mov     edx, 28h ; '('
0x180006282  call    WPP_SF_
0x180006287  jmp     short loc_1800062BC
0x180006289  mov     rcx, cs:WPP_GLOBAL_Control
0x180006290  lea     rax, WPP_GLOBAL_Control
0x180006297  cmp     rcx, rax
0x18000629a  jz      short loc_1800062BC
0x18000629c  cmp     byte ptr [rcx+19h], 2
0x1800062a0  jb      short loc_1800062BC
0x1800062a2  mov     rcx, [rcx+10h]
0x1800062a6  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x1800062ad  mov     edx, 27h ; '''
0x1800062b2  call    WPP_SF_d
0x1800062b7  jmp     short loc_1800062BC
0x1800062b9  mov     dil, 1
0x1800062bc  mov     rcx, rbx; hFindFile
0x1800062bf  call    cs:__imp_FindClose
0x1800062c5  jmp     short loc_1800062F5
0x1800062c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800062ce  lea     rax, WPP_GLOBAL_Control
0x1800062d5  cmp     rcx, rax
0x1800062d8  jz      short loc_1800062F5
0x1800062da  cmp     byte ptr [rcx+19h], 2
0x1800062de  jb      short loc_1800062F5
0x1800062e0  mov     edx, 24h ; '$'
0x1800062e5  mov     rcx, [rcx+10h]
0x1800062e9  lea     r8, WPP_bb31105b28713e810f7e3195fae1a055_Traceguids
0x1800062f0  call    WPP_SF_
0x1800062f5  mov     al, dil
0x1800062f8  mov     rcx, [rbp+7E0h+var_10]
0x1800062ff  xor     rcx, rsp; StackCookie
0x180006302  call    __security_check_cookie
0x180006307  lea     r11, [rsp+8E0h+var_s0]
0x18000630f  mov     rbx, [r11+10h]
0x180006313  mov     rdi, [r11+18h]
0x180006317  mov     rsp, r11
0x18000631a  pop     rbp
0x18000631b  retn
```
