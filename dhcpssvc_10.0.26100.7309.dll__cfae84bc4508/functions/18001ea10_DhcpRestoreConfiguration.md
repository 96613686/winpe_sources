# DhcpRestoreConfiguration

- ea: `0x18001ea10`
- end: `0x18001ecb2`
- name: `DhcpRestoreConfiguration`
- size: `674`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025bf4`
- `0x1800277f8`

## callees

- `0x180002854`
- `0x1800057f4`
- `0x1800058cc`
- `0x18001d5ec`
- `0x18001ea10`
- `0x18009be2c`
- `0x18009cd50`
- `0x1800cc99a`
- `0x1800cc9e0`

## import_xrefs

- `KERNEL32!ReadFile` at `0x18001eb72`
- `KERNEL32!ReadFile` at `0x18001eb72`
- `KERNEL32!SearchPathW` at `0x18001eac4`
- `KERNEL32!SearchPathW` at `0x18001eac4`
- `KERNEL32!GetFileSize` at `0x18001eb2e`
- `KERNEL32!GetFileSize` at `0x18001eb2e`
- `KERNEL32!GetLastError` at `0x18001eb9b`
- `KERNEL32!GetLastError` at `0x18001ec0e`
- `KERNEL32!GetLastError` at `0x18001eb9b`
- `KERNEL32!GetLastError` at `0x18001ec0e`
- `KERNEL32!CloseHandle` at `0x18001ebb9`
- `KERNEL32!CloseHandle` at `0x18001ebb9`
- `KERNEL32!EnterCriticalSection` at `0x18001ea77`
- `KERNEL32!EnterCriticalSection` at `0x18001ea77`
- `KERNEL32!LeaveCriticalSection` at `0x18001ec7a`
- `KERNEL32!LeaveCriticalSection` at `0x18001ec7a`
- `KERNEL32!CreateFileW` at `0x18001eb07`
- `KERNEL32!CreateFileW` at `0x18001eb07`

## pseudocode

```c
__int64 __fastcall DhcpRestoreConfiguration(LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  unsigned int v4; // ebx
  _BYTE *v5; // rax
  DWORD LastError; // eax
  unsigned int v7; // eax
  _WORD v9[2]; // [rsp+40h] [rbp-238h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-234h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-230h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids, lpFileName);
  EnterCriticalSection(&DhcpGlobalRegCritSect);
  memset_0(Buffer, 0, 0x208u);
  FilePart = 0;
  g_FileErrorStringID = 0;
  if ( SearchPathW(0, lpFileName, 0, 0x104u, Buffer, &FilePart) - 1 > 0x103
    || (FileW = CreateFileW(Buffer, 0x80000000, 1u, &DhcpGlobalDirSecurityAttr, 3u, 0x80u, 0),
        hFile = FileW,
        FileW == (HANDLE)-1LL) )
  {
    hFile = 0;
  }
  else
  {
    v9[0] = 0;
    NumberOfBytesRead = 0;
    FileSize = GetFileSize(FileW, 0);
    dword_18013EE98 = 0;
    dword_18013EE90 = 0;
    dword_18013EE94 = FileSize / 0x64;
    if ( ReadFile(hFile, v9, 2u, &NumberOfBytesRead, 0) )
    {
      LODWORD(qword_18013EE88) = 0;
      SkipWhitespace();
      ImportNewerRegFile();
      goto LABEL_10;
    }
  }
  g_FileErrorStringID = GetLastError();
LABEL_10:
  if ( hFile )
    CloseHandle(hFile);
  v4 = g_FileErrorStringID;
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids, lpFileName);
    v5 = WPP_GLOBAL_Control;
  }
  if ( v4 )
  {
    if ( v5 != (_BYTE *)&WPP_GLOBAL_Control && (v5[28] & 0x10) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_dD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids,
        v4,
        LastError);
    }
  }
  else
  {
    v7 = DhcpCheckPaths();
    v4 = v7;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids, v7);
  }
  LeaveCriticalSection(&DhcpGlobalRegCritSect);
  return v4;
}

```

## disassembly

```asm
0x18001ea10  mov     [rsp+arg_8], rbx
0x18001ea15  mov     [rsp+arg_10], rbp
0x18001ea1a  mov     [rsp+arg_18], rsi
0x18001ea1f  push    rdi
0x18001ea20  sub     rsp, 270h
0x18001ea27  mov     rax, cs:__security_cookie
0x18001ea2e  xor     rax, rsp
0x18001ea31  mov     [rsp+278h+var_18], rax
0x18001ea39  mov     rdi, rcx
0x18001ea3c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ea43  lea     rbp, WPP_GLOBAL_Control
0x18001ea4a  cmp     rcx, rbp
0x18001ea4d  jz      short loc_18001EA70
0x18001ea4f  test    dword ptr [rcx+1Ch], 400h
0x18001ea56  jz      short loc_18001EA70
0x18001ea58  mov     rcx, [rcx+10h]
0x18001ea5c  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001ea63  mov     edx, 27h ; '''
0x18001ea68  mov     r9, rdi
0x18001ea6b  call    WPP_SF_S
0x18001ea70  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x18001ea77  call    cs:__imp_EnterCriticalSection
0x18001ea7e  nop     dword ptr [rax+rax+00h]
0x18001ea83  xor     edx, edx; Val
0x18001ea85  lea     rcx, [rsp+278h+Buffer]; void *
0x18001ea8a  mov     r8d, 208h; Size
0x18001ea90  call    memset_0
0x18001ea95  lea     rax, [rsp+278h+FilePart]
0x18001ea9a  xor     esi, esi
0x18001ea9c  mov     [rsp+278h+lpFilePart], rax; lpFilePart
0x18001eaa1  mov     r9d, 104h; nBufferLength
0x18001eaa7  lea     rax, [rsp+278h+Buffer]
0x18001eaac  mov     [rsp+278h+FilePart], rsi
0x18001eab1  xor     r8d, r8d; lpExtension
0x18001eab4  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001eab9  mov     rdx, rdi; lpFileName
0x18001eabc  mov     cs:g_FileErrorStringID, esi
0x18001eac2  xor     ecx, ecx; lpPath
0x18001eac4  call    cs:__imp_SearchPathW
0x18001eacb  nop     dword ptr [rax+rax+00h]
0x18001ead0  dec     eax
0x18001ead2  cmp     eax, 103h
0x18001ead7  ja      loc_18001EB94
0x18001eadd  mov     [rsp+278h+hTemplateFile], rsi; hTemplateFile
0x18001eae2  lea     r9, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x18001eae9  mov     dword ptr [rsp+278h+lpFilePart], 80h; dwFlagsAndAttributes
0x18001eaf1  lea     r8d, [rsi+1]; dwShareMode
0x18001eaf5  mov     edx, 80000000h; dwDesiredAccess
0x18001eafa  mov     dword ptr [rsp+278h+lpBuffer], 3; dwCreationDisposition
0x18001eb02  lea     rcx, [rsp+278h+Buffer]; lpFileName
0x18001eb07  call    cs:__imp_CreateFileW
0x18001eb0e  nop     dword ptr [rax+rax+00h]
0x18001eb13  mov     cs:hFile, rax
0x18001eb1a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001eb1e  jz      short loc_18001EB94
0x18001eb20  xor     edx, edx; lpFileSizeHigh
0x18001eb22  mov     [rsp+278h+var_238], si
0x18001eb27  mov     rcx, rax; hFile
0x18001eb2a  mov     [rsp+278h+NumberOfBytesRead], esi
0x18001eb2e  call    cs:__imp_GetFileSize
0x18001eb35  nop     dword ptr [rax+rax+00h]
0x18001eb3a  lea     r9, [rsp+278h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001eb3f  mov     cs:dword_18013EE98, esi
0x18001eb45  mov     ecx, eax
0x18001eb47  mov     cs:dword_18013EE90, esi
0x18001eb4d  mov     eax, 51EB851Fh
0x18001eb52  mov     [rsp+278h+lpBuffer], rsi; lpOverlapped
0x18001eb57  mul     ecx
0x18001eb59  mov     rcx, cs:hFile; hFile
0x18001eb60  lea     r8d, [rsi+2]; nNumberOfBytesToRead
0x18001eb64  shr     edx, 5
0x18001eb67  mov     cs:dword_18013EE94, edx
0x18001eb6d  lea     rdx, [rsp+278h+var_238]; lpBuffer
0x18001eb72  call    cs:__imp_ReadFile
0x18001eb79  nop     dword ptr [rax+rax+00h]
0x18001eb7e  test    eax, eax
0x18001eb80  jz      short loc_18001EB9B
0x18001eb82  mov     dword ptr cs:qword_18013EE88, esi
0x18001eb88  call    SkipWhitespace
0x18001eb8d  call    ImportNewerRegFile
0x18001eb92  jmp     short loc_18001EBAD
0x18001eb94  mov     cs:hFile, rsi
0x18001eb9b  call    cs:__imp_GetLastError
0x18001eba2  nop     dword ptr [rax+rax+00h]
0x18001eba7  mov     cs:g_FileErrorStringID, eax
0x18001ebad  mov     rcx, cs:hFile; hObject
0x18001ebb4  test    rcx, rcx
0x18001ebb7  jz      short loc_18001EBC5
0x18001ebb9  call    cs:__imp_CloseHandle
0x18001ebc0  nop     dword ptr [rax+rax+00h]
0x18001ebc5  mov     ebx, cs:g_FileErrorStringID
0x18001ebcb  mov     rax, cs:WPP_GLOBAL_Control
0x18001ebd2  cmp     rax, rbp
0x18001ebd5  jz      short loc_18001EBFF
0x18001ebd7  test    dword ptr [rax+1Ch], 400h
0x18001ebde  jz      short loc_18001EBFF
0x18001ebe0  mov     rcx, [rax+10h]
0x18001ebe4  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001ebeb  mov     edx, 28h ; '('
0x18001ebf0  mov     r9, rdi
0x18001ebf3  call    WPP_SF_S
0x18001ebf8  mov     rax, cs:WPP_GLOBAL_Control
0x18001ebff  test    ebx, ebx
0x18001ec01  jz      short loc_18001EC3F
0x18001ec03  cmp     rax, rbp
0x18001ec06  jz      short loc_18001EC73
0x18001ec08  test    byte ptr [rax+1Ch], 10h
0x18001ec0c  jz      short loc_18001EC73
0x18001ec0e  call    cs:__imp_GetLastError
0x18001ec15  nop     dword ptr [rax+rax+00h]
0x18001ec1a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec21  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001ec28  mov     edx, 29h ; ')'
0x18001ec2d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001ec31  mov     r9d, ebx
0x18001ec34  mov     rcx, [rcx+10h]
0x18001ec38  call    WPP_SF_dD
0x18001ec3d  jmp     short loc_18001EC73
0x18001ec3f  call    DhcpCheckPaths
0x18001ec44  mov     ebx, eax
0x18001ec46  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ec4d  cmp     rcx, rbp
0x18001ec50  jz      short loc_18001EC73
0x18001ec52  test    dword ptr [rcx+1Ch], 400h
0x18001ec59  jz      short loc_18001EC73
0x18001ec5b  mov     rcx, [rcx+10h]
0x18001ec5f  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001ec66  mov     edx, 2Ah ; '*'
0x18001ec6b  mov     r9d, eax
0x18001ec6e  call    WPP_SF_D
0x18001ec73  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x18001ec7a  call    cs:__imp_LeaveCriticalSection
0x18001ec81  nop     dword ptr [rax+rax+00h]
0x18001ec86  mov     eax, ebx
0x18001ec88  mov     rcx, [rsp+278h+var_18]
0x18001ec90  xor     rcx, rsp; StackCookie
0x18001ec93  call    __security_check_cookie
0x18001ec98  lea     r11, [rsp+278h+var_8]
0x18001eca0  mov     rbx, [r11+18h]
0x18001eca4  mov     rbp, [r11+20h]
0x18001eca8  mov     rsi, [r11+28h]
0x18001ecac  mov     rsp, r11
0x18001ecaf  pop     rdi
0x18001ecb0  retn
```
