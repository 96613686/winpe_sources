# DhcpRestoreConfiguration

- ea: `0x18001dfc8`
- end: `0x18001e263`
- name: `DhcpRestoreConfiguration`
- size: `667`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `9`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180025144`
- `0x180026d78`

## callees

- `0x18000282c`
- `0x1800057e0`
- `0x1800058bc`
- `0x18001cb90`
- `0x18001dfc8`
- `0x18009cafc`
- `0x18009da18`
- `0x1800cda7a`
- `0x1800cdac0`

## import_xrefs

- `KERNEL32!SearchPathW` at `0x18001e07a`
- `KERNEL32!SearchPathW` at `0x18001e07a`
- `KERNEL32!ReadFile` at `0x18001e128`
- `KERNEL32!ReadFile` at `0x18001e128`
- `KERNEL32!GetFileSize` at `0x18001e0e4`
- `KERNEL32!GetFileSize` at `0x18001e0e4`
- `KERNEL32!GetLastError` at `0x18001e151`
- `KERNEL32!GetLastError` at `0x18001e1c8`
- `KERNEL32!GetLastError` at `0x18001e151`
- `KERNEL32!GetLastError` at `0x18001e1c8`
- `KERNEL32!CloseHandle` at `0x18001e16f`
- `KERNEL32!CloseHandle` at `0x18001e16f`
- `KERNEL32!EnterCriticalSection` at `0x18001e02d`
- `KERNEL32!EnterCriticalSection` at `0x18001e02d`
- `KERNEL32!LeaveCriticalSection` at `0x18001e22c`
- `KERNEL32!LeaveCriticalSection` at `0x18001e22c`
- `KERNEL32!CreateFileW` at `0x18001e0bd`
- `KERNEL32!CreateFileW` at `0x18001e0bd`

## pseudocode

```c
__int64 __fastcall DhcpRestoreConfiguration(LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  DWORD FileSize; // eax
  unsigned int v4; // edi
  _QWORD *v5; // rbx
  __int64 v6; // rbx
  DWORD LastError; // eax
  unsigned int v8; // eax
  _WORD v10[2]; // [rsp+40h] [rbp-248h] BYREF
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-244h] BYREF
  LPWSTR FilePart; // [rsp+48h] [rbp-240h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-238h] BYREF

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
    v10[0] = 0;
    NumberOfBytesRead = 0;
    FileSize = GetFileSize(FileW, 0);
    dword_180140E78 = 0;
    dword_180140E70 = 0;
    dword_180140E74 = FileSize / 0x64;
    if ( ReadFile(hFile, v10, 2u, &NumberOfBytesRead, 0) )
    {
      LODWORD(qword_180140E68) = 0;
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
    if ( v5 != &WPP_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 0x10) != 0 )
    {
      v6 = v5[2];
      LastError = GetLastError();
      WPP_SF_dD(v6, 41, &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids, v4, LastError);
    }
  }
  else
  {
    v8 = DhcpCheckPaths();
    v4 = v8;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
      WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids, v8);
  }
  LeaveCriticalSection(&DhcpGlobalRegCritSect);
  return v4;
}

```

## disassembly

```asm
0x18001dfc8  mov     [rsp+arg_8], rbx
0x18001dfcd  mov     [rsp+arg_10], rbp
0x18001dfd2  push    rsi
0x18001dfd3  push    rdi
0x18001dfd4  push    r14
0x18001dfd6  sub     rsp, 270h
0x18001dfdd  mov     rax, cs:__security_cookie
0x18001dfe4  xor     rax, rsp
0x18001dfe7  mov     [rsp+288h+var_28], rax
0x18001dfef  mov     rsi, rcx
0x18001dff2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dff9  lea     r14, WPP_GLOBAL_Control
0x18001e000  cmp     rcx, r14
0x18001e003  jz      short loc_18001E026
0x18001e005  test    dword ptr [rcx+1Ch], 400h
0x18001e00c  jz      short loc_18001E026
0x18001e00e  mov     rcx, [rcx+10h]
0x18001e012  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001e019  mov     edx, 27h ; '''
0x18001e01e  mov     r9, rsi
0x18001e021  call    WPP_SF_S
0x18001e026  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x18001e02d  call    cs:__imp_EnterCriticalSection
0x18001e034  nop     dword ptr [rax+rax+00h]
0x18001e039  xor     edx, edx; Val
0x18001e03b  lea     rcx, [rsp+288h+Buffer]; void *
0x18001e040  mov     r8d, 208h; Size
0x18001e046  call    memset_0
0x18001e04b  lea     rax, [rsp+288h+FilePart]
0x18001e050  xor     ebp, ebp
0x18001e052  mov     [rsp+288h+lpFilePart], rax; lpFilePart
0x18001e057  mov     r9d, 104h; nBufferLength
0x18001e05d  lea     rax, [rsp+288h+Buffer]
0x18001e062  mov     [rsp+288h+FilePart], rbp
0x18001e067  xor     r8d, r8d; lpExtension
0x18001e06a  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18001e06f  mov     rdx, rsi; lpFileName
0x18001e072  mov     cs:g_FileErrorStringID, ebp
0x18001e078  xor     ecx, ecx; lpPath
0x18001e07a  call    cs:__imp_SearchPathW
0x18001e081  nop     dword ptr [rax+rax+00h]
0x18001e086  dec     eax
0x18001e088  cmp     eax, 103h
0x18001e08d  ja      loc_18001E14A
0x18001e093  mov     [rsp+288h+hTemplateFile], rbp; hTemplateFile
0x18001e098  lea     r9, DhcpGlobalDirSecurityAttr; lpSecurityAttributes
0x18001e09f  mov     dword ptr [rsp+288h+lpFilePart], 80h; dwFlagsAndAttributes
0x18001e0a7  lea     r8d, [rbp+1]; dwShareMode
0x18001e0ab  mov     edx, 80000000h; dwDesiredAccess
0x18001e0b0  mov     dword ptr [rsp+288h+lpBuffer], 3; dwCreationDisposition
0x18001e0b8  lea     rcx, [rsp+288h+Buffer]; lpFileName
0x18001e0bd  call    cs:__imp_CreateFileW
0x18001e0c4  nop     dword ptr [rax+rax+00h]
0x18001e0c9  mov     cs:hFile, rax
0x18001e0d0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e0d4  jz      short loc_18001E14A
0x18001e0d6  xor     edx, edx; lpFileSizeHigh
0x18001e0d8  mov     [rsp+288h+var_248], bp
0x18001e0dd  mov     rcx, rax; hFile
0x18001e0e0  mov     [rsp+288h+NumberOfBytesRead], ebp
0x18001e0e4  call    cs:__imp_GetFileSize
0x18001e0eb  nop     dword ptr [rax+rax+00h]
0x18001e0f0  lea     r9, [rsp+288h+NumberOfBytesRead]; lpNumberOfBytesRead
0x18001e0f5  mov     cs:dword_180140E78, ebp
0x18001e0fb  mov     ecx, eax
0x18001e0fd  mov     cs:dword_180140E70, ebp
0x18001e103  mov     eax, 51EB851Fh
0x18001e108  mov     [rsp+288h+lpBuffer], rbp; lpOverlapped
0x18001e10d  mul     ecx
0x18001e10f  mov     rcx, cs:hFile; hFile
0x18001e116  lea     r8d, [rbp+2]; nNumberOfBytesToRead
0x18001e11a  shr     edx, 5
0x18001e11d  mov     cs:dword_180140E74, edx
0x18001e123  lea     rdx, [rsp+288h+var_248]; lpBuffer
0x18001e128  call    cs:__imp_ReadFile
0x18001e12f  nop     dword ptr [rax+rax+00h]
0x18001e134  test    eax, eax
0x18001e136  jz      short loc_18001E151
0x18001e138  mov     dword ptr cs:qword_180140E68, ebp
0x18001e13e  call    SkipWhitespace
0x18001e143  call    ImportNewerRegFile
0x18001e148  jmp     short loc_18001E163
0x18001e14a  mov     cs:hFile, rbp
0x18001e151  call    cs:__imp_GetLastError
0x18001e158  nop     dword ptr [rax+rax+00h]
0x18001e15d  mov     cs:g_FileErrorStringID, eax
0x18001e163  mov     rcx, cs:hFile; hObject
0x18001e16a  test    rcx, rcx
0x18001e16d  jz      short loc_18001E17B
0x18001e16f  call    cs:__imp_CloseHandle
0x18001e176  nop     dword ptr [rax+rax+00h]
0x18001e17b  mov     edi, cs:g_FileErrorStringID
0x18001e181  mov     rbx, cs:WPP_GLOBAL_Control
0x18001e188  cmp     rbx, r14
0x18001e18b  jz      short loc_18001E1B5
0x18001e18d  test    dword ptr [rbx+1Ch], 400h
0x18001e194  jz      short loc_18001E1B5
0x18001e196  mov     rcx, [rbx+10h]
0x18001e19a  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001e1a1  mov     edx, 28h ; '('
0x18001e1a6  mov     r9, rsi
0x18001e1a9  call    WPP_SF_S
0x18001e1ae  mov     rbx, cs:WPP_GLOBAL_Control
0x18001e1b5  test    edi, edi
0x18001e1b7  jz      short loc_18001E1F1
0x18001e1b9  cmp     rbx, r14
0x18001e1bc  jz      short loc_18001E225
0x18001e1be  test    byte ptr [rbx+1Ch], 10h
0x18001e1c2  jz      short loc_18001E225
0x18001e1c4  mov     rbx, [rbx+10h]
0x18001e1c8  call    cs:__imp_GetLastError
0x18001e1cf  nop     dword ptr [rax+rax+00h]
0x18001e1d4  mov     edx, 29h ; ')'
0x18001e1d9  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001e1e0  mov     r9d, edi
0x18001e1e3  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18001e1e7  mov     rcx, rbx
0x18001e1ea  call    WPP_SF_dD
0x18001e1ef  jmp     short loc_18001E225
0x18001e1f1  call    DhcpCheckPaths
0x18001e1f6  mov     edi, eax
0x18001e1f8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e1ff  cmp     rcx, r14
0x18001e202  jz      short loc_18001E225
0x18001e204  test    dword ptr [rcx+1Ch], 400h
0x18001e20b  jz      short loc_18001E225
0x18001e20d  mov     rcx, [rcx+10h]
0x18001e211  lea     r8, WPP_81df4701b76732600b79d94e3cc7dc7e_Traceguids
0x18001e218  mov     edx, 2Ah ; '*'
0x18001e21d  mov     r9d, eax
0x18001e220  call    WPP_SF_D
0x18001e225  lea     rcx, DhcpGlobalRegCritSect; lpCriticalSection
0x18001e22c  call    cs:__imp_LeaveCriticalSection
0x18001e233  nop     dword ptr [rax+rax+00h]
0x18001e238  mov     eax, edi
0x18001e23a  mov     rcx, [rsp+288h+var_28]
0x18001e242  xor     rcx, rsp; StackCookie
0x18001e245  call    __security_check_cookie
0x18001e24a  lea     r11, [rsp+288h+var_18]
0x18001e252  mov     rbx, [r11+28h]
0x18001e256  mov     rbp, [r11+30h]
0x18001e25a  mov     rsp, r11
0x18001e25d  pop     r14
0x18001e25f  pop     rdi
0x18001e260  pop     rsi
0x18001e261  retn
```
