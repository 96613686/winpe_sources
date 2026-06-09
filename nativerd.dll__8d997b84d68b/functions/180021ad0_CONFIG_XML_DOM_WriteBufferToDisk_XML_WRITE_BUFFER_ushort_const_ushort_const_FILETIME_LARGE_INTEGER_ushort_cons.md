# CONFIG_XML_DOM::WriteBufferToDisk(XML_WRITE_BUFFER *,ushort const *,ushort const *,_FILETIME *,_LARGE_INTEGER *,ushort const *,void *)

- ea: `0x180021ad0`
- end: `0x180021f6f`
- name: `?WriteBufferToDisk@CONFIG_XML_DOM@@SAJPEAVXML_WRITE_BUFFER@@PEBG1PEAU_FILETIME@@PEAT_LARGE_INTEGER@@1PEAX@Z`
- size: `1183`
- prototype: `__int64 __fastcall(struct XML_WRITE_BUFFER *, const unsigned __int16 *, const unsigned __int16 *, struct _FILETIME *, union _LARGE_INTEGER *, unsigned __int16 *, __int64 hTransaction)`
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180020660`

## callees

- `0x1800100d0`
- `0x180010468`
- `0x180016440`
- `0x18001a884`
- `0x18001c250`
- `0x18001fda0`
- `0x180021ad0`
- `0x1800222a8`
- `0x180022300`
- `0x1800223e4`
- `0x1800224d8`
- `0x1800225cc`
- `0x1800412fc`
- `0x1800414f0`
- `0x180058ba0`
- `0x180059c30`
- `0x18005b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021df9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021cd4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021d04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021db3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180021df9`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180021cfa`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180021cfa`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180021da9`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180021da9`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180021cca`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180021cca`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180021c5a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180021c5a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021def`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f2f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021def`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180021f2f`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021baf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021d4e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021baf`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180021d4e`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021d8c`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180021d8c`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021f08`
- `OLEAUT32!__imp_SetErrorInfo` at `0x180021f08`

## string_xrefs

- `0x180021b6f`: `CONFIG_XML_DOM::WriteBufferToDisk`

## pseudocode

```c
__int64 __fastcall CONFIG_XML_DOM::WriteBufferToDisk(
        struct XML_WRITE_BUFFER *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct _FILETIME *a4,
        union _LARGE_INTEGER *a5,
        unsigned __int16 *a6,
        __int64 hTransaction)
{
  const unsigned __int16 *v8; // rax
  DWORD *p_dwHighDateTime; // rbx
  unsigned int v11; // r15d
  int v12; // r12d
  __int64 v13; // r14
  DWORD LastError; // eax
  __int64 v15; // rcx
  signed int FileInfo; // edi
  int v17; // r12d
  void *v18; // rdx
  int v19; // r13d
  char v20; // bl
  signed int v21; // eax
  const unsigned __int16 *v22; // r15
  int v23; // ebx
  int v24; // edx
  int v25; // ecx
  signed int v26; // eax
  int v27; // edx
  struct XML_WRITE_BUFFER *v28; // r12
  DWORD v29; // ebx
  const void *Ptr; // rax
  signed int v31; // eax
  int v32; // edx
  signed int v33; // eax
  unsigned int v34; // ebx
  CONFIG_EXCEPTION *v35; // rax
  CONFIG_EXCEPTION *v36; // rax
  IErrorInfo *v37; // rbx
  int v39; // [rsp+40h] [rbp-B1h]
  __int64 v40; // [rsp+48h] [rbp-A9h]
  DWORD NumberOfBytesWritten; // [rsp+68h] [rbp-89h] BYREF
  struct XML_WRITE_BUFFER *v43; // [rsp+70h] [rbp-81h] BYREF
  const unsigned __int16 *v44; // [rsp+78h] [rbp-79h]
  unsigned __int16 *v45; // [rsp+80h] [rbp-71h]
  _BYTE FileInformation[64]; // [rsp+90h] [rbp-61h] BYREF
  _BYTE v47[16]; // [rsp+D0h] [rbp-21h] BYREF

  v8 = a3;
  v43 = a1;
  v45 = a6;
  v44 = a2;
  NumberOfBytesWritten = 0;
  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
  {
    McGenEventWrite_EtwEventWriteTransfer(
      (_DWORD)a6,
      (unsigned int)NATIVERD_EVENT_COMMIT_CHANGES_BEGIN_FILE_WRITE_OPERATION,
      (_DWORD)a3,
      1,
      (__int64)v47);
    v8 = a3;
  }
  p_dwHighDateTime = &a4->dwHighDateTime;
  if ( a4 )
  {
    if ( *p_dwHighDateTime || (v11 = 1, a4->dwLowDateTime) )
      v11 = 3;
  }
  else
  {
    v11 = 4;
  }
  v12 = 0;
  while ( 1 )
  {
    v13 = (__int64)FILE_HELPER::CreateFileAndWriteEvent(
                     L"CONFIG_XML_DOM::WriteBufferToDisk",
                     v8,
                     0xC0000000,
                     0,
                     v11,
                     0x80u,
                     (void *)hTransaction);
    LastError = GetLastError();
    FileInfo = LastError;
    if ( v13 != -1 )
      break;
    if ( LastError == 32 )
    {
      Sleep(0x1F4u);
    }
    else
    {
      if ( LastError - 6800 > 0x63 )
        goto LABEL_15;
      hTransaction = -1;
    }
    v8 = a3;
    if ( (unsigned int)++v12 >= 0xA )
    {
LABEL_15:
      if ( FileInfo <= 0 )
        goto LABEL_52;
      FileInfo = (unsigned __int16)FileInfo;
      goto LABEL_17;
    }
  }
  FileInfo = 0;
  v17 = 1;
  if ( a4 && (*p_dwHighDateTime || a4->dwLowDateTime) )
  {
    v18 = (void *)hTransaction;
    v19 = (int)a3;
    memset(FileInformation, 0, 36);
    FileInfo = FILE_HELPER::GetFileInfo(a3, v18, (struct _WIN32_FILE_ATTRIBUTE_DATA *)FileInformation);
    if ( FileInfo < 0 )
      goto LABEL_53;
    v20 = FileInformation[32];
    if ( a5 && __PAIR64__(*(unsigned int *)&FileInformation[28], *(unsigned int *)&FileInformation[32]) != a5->QuadPart
      || CompareFileTime((const FILETIME *)&FileInformation[20], a4) )
    {
      v17 = 0;
      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 4) != 0 )
        McTemplateU0zztmxtmxt_EtwEventWriteTransfer(
          1,
          (unsigned int)NATIVERD_EVENT_CANNOT_COMMIT_CHANGES_DUE_TO_STALE_CONFIG_VIEW,
          (_DWORD)v44,
          (_DWORD)a3,
          1,
          (__int64)a4,
          a5->QuadPart,
          1,
          (__int64)&FileInformation[12],
          v20,
          0);
      FileInfo = -2147024864;
      goto LABEL_53;
    }
  }
  else
  {
    v19 = (int)a3;
  }
  if ( SetFilePointerEx((HANDLE)v13, 0, 0, 0) )
  {
    v22 = v44;
    v23 = 0;
    while ( !SetEndOfFile((HANDLE)v13) )
    {
      v26 = GetLastError();
      FileInfo = v26;
      if ( v26 > 0 )
        FileInfo = (unsigned __int16)v26 | 0x80070000;
      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
        McTemplateU0pzzqd_EtwEventWriteTransfer(v15, v27, v13, v19, (__int64)v44, 9 - v23, FileInfo);
      if ( FileInfo != -2147023672 )
        goto LABEL_52;
      Sleep(0x1F4u);
      if ( (unsigned int)++v23 >= 0xA )
        goto LABEL_53;
    }
    if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
      McTemplateU0pzzd_EtwEventWriteTransfer(v25, v24, v13, v19, (__int64)v44, FileInfo);
    v28 = v43;
    v29 = *((_DWORD *)v43 + 3);
    Ptr = BUFFER::QueryPtr((struct XML_WRITE_BUFFER *)((char *)v43 + 16));
    if ( WriteFile((HANDLE)v13, Ptr, v29, &NumberOfBytesWritten, 0) )
    {
      if ( CloseHandle((HANDLE)v13) )
      {
        v13 = -1;
      }
      else
      {
        v33 = GetLastError();
        FileInfo = v33;
        if ( v33 > 0 )
          FileInfo = (unsigned __int16)v33 | 0x80070000;
      }
    }
    else
    {
      v31 = GetLastError();
      FileInfo = v31;
      if ( v31 > 0 )
        FileInfo = (unsigned __int16)v31 | 0x80070000;
      if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
        McTemplateU0pzzdd_EtwEventWriteTransfer(v15, v32, v13, v19, (__int64)v22, *((_DWORD *)v28 + 3), FileInfo);
    }
  }
  else
  {
    v21 = GetLastError();
    FileInfo = v21;
    if ( v21 > 0 )
    {
      FileInfo = (unsigned __int16)v21;
LABEL_17:
      FileInfo |= 0x80070000;
    }
  }
LABEL_52:
  v17 = 1;
  if ( FileInfo >= 0 )
    goto LABEL_66;
LABEL_53:
  *(_QWORD *)&FileInformation[8] = 1;
  *(_QWORD *)FileInformation = &PARSE_ERROR_INFO::`vftable';
  *(_DWORD *)&FileInformation[16] = 0;
  memset(&FileInformation[24], 0, 40);
  v43 = 0;
  if ( FileInfo == -2147024891 )
  {
    v34 = -1073739019;
  }
  else if ( FileInfo == -2147024816 || FileInfo == -2147024894 || !v17 )
  {
    FileInfo = -2147024864;
    v34 = -1073739021;
  }
  else
  {
    v34 = -1073739017;
  }
  SMALL_STRU::Copy((SMALL_STRU *)&FileInformation[32], v45);
  PARSE_ERROR_INFO::SetErrorInfo(FileInformation, (unsigned int)FileInfo, 4, v34, &v43, 0, 0, 0, v39, v40);
  v35 = (CONFIG_EXCEPTION *)operator new(0x178u);
  if ( v35 )
  {
    v36 = CONFIG_EXCEPTION::CONFIG_EXCEPTION(v35);
    v37 = (IErrorInfo *)v36;
    if ( v36 )
    {
      if ( (int)CONFIG_EXCEPTION::Create(v36, (struct PARSE_ERROR_INFO *)FileInformation) >= 0 )
        SetErrorInfo(0, v37 + 1);
      ((void (__fastcall *)(IErrorInfo *))v37->lpVtbl->Release)(v37);
    }
  }
  PARSE_ERROR_INFO::~PARSE_ERROR_INFO((PARSE_ERROR_INFO *)FileInformation);
LABEL_66:
  if ( v13 != -1 )
    CloseHandle((HANDLE)v13);
  if ( (Microsoft_Windows_IIS_ConfigurationEnableBits & 0x20) != 0 )
    McTemplateU0q_EtwEventWriteTransfer(
      v15,
      NATIVERD_EVENT_COMMIT_CHANGES_END_FILE_WRITE_OPERATION,
      (unsigned int)FileInfo);
  return (unsigned int)FileInfo;
}

```

## disassembly

```asm
0x180021ad0  push    rbp
0x180021ad2  push    rbx
0x180021ad3  push    rsi
0x180021ad4  push    rdi
0x180021ad5  push    r12
0x180021ad7  push    r13
0x180021ad9  push    r14
0x180021adb  push    r15
0x180021add  lea     rbp, [rsp-7]
0x180021ae2  sub     rsp, 0F8h
0x180021ae9  mov     rax, cs:__security_cookie
0x180021af0  xor     rax, rsp
0x180021af3  mov     [rbp+3Fh+var_50], rax
0x180021af7  mov     r13, [rbp+3Fh+hTransaction]
0x180021afb  xor     edi, edi
0x180021afd  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 20h
0x180021b04  mov     rax, r8
0x180021b07  mov     [rsp+130h+var_C0], rcx
0x180021b0c  mov     rsi, r9
0x180021b0f  mov     rcx, [rbp+3Fh+arg_28]
0x180021b13  mov     [rbp+3Fh+var_B0], rcx
0x180021b17  mov     [rsp+130h+lpFileName], rax
0x180021b1c  mov     [rbp+3Fh+var_B8], rdx
0x180021b20  mov     [rsp+130h+NumberOfBytesWritten], edi
0x180021b24  jz      short loc_180021B44
0x180021b26  lea     rax, [rbp+3Fh+var_60]
0x180021b2a  lea     r9d, [rdi+1]
0x180021b2e  mov     [rsp+130h+lpOverlapped], rax
0x180021b33  lea     rdx, NATIVERD_EVENT_COMMIT_CHANGES_BEGIN_FILE_WRITE_OPERATION
0x180021b3a  call    McGenEventWrite_EtwEventWriteTransfer
0x180021b3f  mov     rax, [rsp+130h+lpFileName]
0x180021b44  lea     rbx, [rsi+4]
0x180021b48  test    rsi, rsi
0x180021b4b  jnz     short loc_180021B53
0x180021b4d  lea     r15d, [rsi+4]
0x180021b51  jmp     short loc_180021B67
0x180021b53  cmp     [rbx], edi
0x180021b55  jnz     short loc_180021B61
0x180021b57  mov     r15d, 1
0x180021b5d  cmp     [rsi], edi
0x180021b5f  jz      short loc_180021B67
0x180021b61  mov     r15d, 3
0x180021b67  mov     r12d, edi
0x180021b6a  mov     [rsp+130h+var_100], r13; void *
0x180021b6f  lea     rcx, aConfigXmlDomWr; "CONFIG_XML_DOM::WriteBufferToDisk"
0x180021b76  mov     [rsp+130h+var_108], 80h; unsigned int
0x180021b7e  xor     r9d, r9d; unsigned int
0x180021b81  mov     r8d, 0C0000000h; unsigned int
0x180021b87  mov     dword ptr [rsp+130h+lpOverlapped], r15d; unsigned int
0x180021b8c  mov     rdx, rax; unsigned __int16 *
0x180021b8f  call    ?CreateFileAndWriteEvent@FILE_HELPER@@SAPEAXPEBG0KKKKPEAX@Z; FILE_HELPER::CreateFileAndWriteEvent(ushort const *,ushort const *,ulong,ulong,ulong,ulong,void *)
0x180021b94  mov     r14, rax
0x180021b97  call    cs:__imp_GetLastError
0x180021b9d  mov     edi, eax
0x180021b9f  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180021ba3  jnz     short loc_180021BE9
0x180021ba5  cmp     eax, 20h ; ' '
0x180021ba8  jnz     short loc_180021BB7
0x180021baa  mov     ecx, 1F4h; dwMilliseconds
0x180021baf  call    cs:__imp_Sleep
0x180021bb5  jmp     short loc_180021BC5
0x180021bb7  add     eax, 0FFFFE570h
0x180021bbc  cmp     eax, 63h ; 'c'
0x180021bbf  ja      short loc_180021BD3
0x180021bc1  or      r13, 0FFFFFFFFFFFFFFFFh
0x180021bc5  mov     rax, [rsp+130h+lpFileName]
0x180021bca  inc     r12d
0x180021bcd  cmp     r12d, 0Ah
0x180021bd1  jb      short loc_180021B6A
0x180021bd3  test    edi, edi
0x180021bd5  jle     loc_180021E10
0x180021bdb  movzx   edi, di
0x180021bde  or      edi, 80070000h
0x180021be4  jmp     loc_180021E10
0x180021be9  xor     edi, edi
0x180021beb  lea     r12d, [rdi+1]
0x180021bef  test    rsi, rsi
0x180021bf2  jz      loc_180021CBA
0x180021bf8  cmp     [rbx], edi
0x180021bfa  jnz     short loc_180021C04
0x180021bfc  cmp     [rsi], edi
0x180021bfe  jz      loc_180021CBA
0x180021c04  xorps   xmm0, xmm0
0x180021c07  lea     r8, [rbp+3Fh+FileInformation]; lpFileInformation
0x180021c0b  mov     rdx, r13; hTransaction
0x180021c0e  xor     eax, eax
0x180021c10  mov     r13, [rsp+130h+lpFileName]
0x180021c15  mov     rcx, r13; lpFileName
0x180021c18  mov     [rbp+3Fh+FileInformation.nFileSizeLow], eax
0x180021c1b  movups  xmmword ptr [rbp+3Fh+FileInformation.dwFileAttributes], xmm0
0x180021c1f  movups  xmmword ptr [rbp+3Fh+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180021c23  call    ?GetFileInfo@FILE_HELPER@@SAJPEBGPEAXPEAU_WIN32_FILE_ATTRIBUTE_DATA@@@Z; FILE_HELPER::GetFileInfo(ushort const *,void *,_WIN32_FILE_ATTRIBUTE_DATA *)
0x180021c28  mov     edi, eax
0x180021c2a  test    eax, eax
0x180021c2c  js      loc_180021E1E
0x180021c32  mov     ecx, [rbp+3Fh+FileInformation.nFileSizeHigh]
0x180021c35  mov     r15, [rbp+3Fh+arg_20]
0x180021c39  mov     dword ptr [rsp+130h+lpFileName+4], ecx
0x180021c3d  mov     ecx, [rbp+3Fh+FileInformation.nFileSizeLow]
0x180021c40  mov     dword ptr [rsp+130h+lpFileName], ecx
0x180021c44  mov     rbx, [rsp+130h+lpFileName]
0x180021c49  test    r15, r15
0x180021c4c  jz      short loc_180021C53
0x180021c4e  cmp     rbx, [r15]
0x180021c51  jnz     short loc_180021C64
0x180021c53  mov     rdx, rsi; lpFileTime2
0x180021c56  lea     rcx, [rbp+3Fh+FileInformation.ftLastWriteTime]; lpFileTime1
0x180021c5a  call    cs:__imp_CompareFileTime
0x180021c60  test    eax, eax
0x180021c62  jz      short loc_180021CBF
0x180021c64  xor     r12d, r12d
0x180021c67  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 4
0x180021c6e  jz      short loc_180021CB0
0x180021c70  mov     r8, [rbp+3Fh+var_B8]
0x180021c74  lea     ecx, [r12+1]
0x180021c79  mov     [rsp+130h+var_E0], r12d
0x180021c7e  lea     rax, [rbp+3Fh+FileInformation.ftLastAccessTime]
0x180021c82  mov     [rsp+130h+var_E8], rbx
0x180021c87  lea     rdx, NATIVERD_EVENT_CANNOT_COMMIT_CHANGES_DUE_TO_STALE_CONFIG_VIEW
0x180021c8e  mov     [rsp+130h+var_F0], rax
0x180021c93  mov     r9, r13
0x180021c96  mov     rax, [r15]
0x180021c99  mov     dword ptr [rsp+130h+var_F8], ecx
0x180021c9d  mov     [rsp+130h+var_100], rax
0x180021ca2  mov     qword ptr [rsp+130h+var_108], rsi
0x180021ca7  mov     dword ptr [rsp+130h+lpOverlapped], ecx
0x180021cab  call    McTemplateU0zztmxtmxt_EtwEventWriteTransfer
0x180021cb0  mov     edi, 80070020h
0x180021cb5  jmp     loc_180021E1E
0x180021cba  mov     r13, [rsp+130h+lpFileName]
0x180021cbf  xor     edx, edx; liDistanceToMove
0x180021cc1  xor     r9d, r9d; dwMoveMethod
0x180021cc4  xor     r8d, r8d; lpNewFilePointer
0x180021cc7  mov     rcx, r14; hFile
0x180021cca  call    cs:__imp_SetFilePointerEx
0x180021cd0  test    eax, eax
0x180021cd2  jnz     short loc_180021CEC
0x180021cd4  call    cs:__imp_GetLastError
0x180021cda  mov     edi, eax
0x180021cdc  test    eax, eax
0x180021cde  jle     loc_180021E10
0x180021ce4  movzx   edi, ax
0x180021ce7  jmp     loc_180021BDE
0x180021cec  mov     r15, [rbp+3Fh+var_B8]
0x180021cf0  xor     ebx, ebx
0x180021cf2  mov     esi, 80070000h
0x180021cf7  mov     rcx, r14; hFile
0x180021cfa  call    cs:__imp_SetEndOfFile
0x180021d00  test    eax, eax
0x180021d02  jnz     short loc_180021D60
0x180021d04  call    cs:__imp_GetLastError
0x180021d0a  mov     edi, eax
0x180021d0c  test    eax, eax
0x180021d0e  jle     short loc_180021D15
0x180021d10  movzx   edi, ax
0x180021d13  or      edi, esi
0x180021d15  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 20h
0x180021d1c  jz      short loc_180021D3D
0x180021d1e  mov     eax, 9
0x180021d23  mov     dword ptr [rsp+130h+var_100], edi
0x180021d27  sub     eax, ebx
0x180021d29  mov     r9, r13
0x180021d2c  mov     [rsp+130h+var_108], eax
0x180021d30  mov     r8, r14
0x180021d33  mov     [rsp+130h+lpOverlapped], r15
0x180021d38  call    McTemplateU0pzzqd_EtwEventWriteTransfer
0x180021d3d  cmp     edi, 800704C8h
0x180021d43  jnz     loc_180021E10
0x180021d49  mov     ecx, 1F4h; dwMilliseconds
0x180021d4e  call    cs:__imp_Sleep
0x180021d54  inc     ebx
0x180021d56  cmp     ebx, 0Ah
0x180021d59  jb      short loc_180021CF7
0x180021d5b  jmp     loc_180021E1E
0x180021d60  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 20h
0x180021d67  jz      short loc_180021D7D
0x180021d69  mov     [rsp+130h+var_108], edi
0x180021d6d  mov     r9, r13
0x180021d70  mov     r8, r14
0x180021d73  mov     [rsp+130h+lpOverlapped], r15
0x180021d78  call    McTemplateU0pzzd_EtwEventWriteTransfer
0x180021d7d  mov     r12, [rsp+130h+var_C0]
0x180021d82  mov     ebx, [r12+0Ch]
0x180021d87  lea     rcx, [r12+10h]
0x180021d8c  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180021d92  lea     r9, [rsp+130h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180021d97  mov     [rsp+130h+lpOverlapped], 0; lpOverlapped
0x180021da0  mov     rdx, rax; lpBuffer
0x180021da3  mov     r8d, ebx; nNumberOfBytesToWrite
0x180021da6  mov     rcx, r14; hFile
0x180021da9  call    cs:__imp_WriteFile
0x180021daf  test    eax, eax
0x180021db1  jnz     short loc_180021DEC
0x180021db3  call    cs:__imp_GetLastError
0x180021db9  mov     edi, eax
0x180021dbb  test    eax, eax
0x180021dbd  jle     short loc_180021DC4
0x180021dbf  movzx   edi, ax
0x180021dc2  or      edi, esi
0x180021dc4  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 20h
0x180021dcb  jz      short loc_180021E10
0x180021dcd  mov     eax, [r12+0Ch]
0x180021dd2  mov     r9, r13
0x180021dd5  mov     dword ptr [rsp+130h+var_100], edi
0x180021dd9  mov     r8, r14
0x180021ddc  mov     [rsp+130h+var_108], eax
0x180021de0  mov     [rsp+130h+lpOverlapped], r15
0x180021de5  call    McTemplateU0pzzdd_EtwEventWriteTransfer
0x180021dea  jmp     short loc_180021E10
0x180021dec  mov     rcx, r14; hObject
0x180021def  call    cs:__imp_CloseHandle
0x180021df5  test    eax, eax
0x180021df7  jnz     short loc_180021E0C
0x180021df9  call    cs:__imp_GetLastError
0x180021dff  mov     edi, eax
0x180021e01  test    eax, eax
0x180021e03  jle     short loc_180021E10
0x180021e05  movzx   edi, ax
0x180021e08  or      edi, esi
0x180021e0a  jmp     short loc_180021E10
0x180021e0c  or      r14, 0FFFFFFFFFFFFFFFFh
0x180021e10  mov     r12d, 1
0x180021e16  test    edi, edi
0x180021e18  jns     loc_180021F26
0x180021e1e  mov     qword ptr [rbp+3Fh+FileInformation.ftCreationTime.dwHighDateTime], 1
0x180021e26  lea     rax, ??_7PARSE_ERROR_INFO@@6B@; const PARSE_ERROR_INFO::`vftable'
0x180021e2d  mov     qword ptr [rbp+3Fh+FileInformation.dwFileAttributes], rax
0x180021e31  xorps   xmm0, xmm0
0x180021e34  movdqa  xmmword ptr [rbp+3Fh+FileInformation.nFileSizeLow], xmm0
0x180021e39  xorps   xmm1, xmm1
0x180021e3c  movdqa  [rbp+3Fh+var_70], xmm1
0x180021e41  mov     [rbp+3Fh+FileInformation.ftLastAccessTime.dwHighDateTime], 0
0x180021e48  mov     qword ptr [rbp+3Fh+FileInformation.ftLastWriteTime.dwHighDateTime], 0
0x180021e50  mov     [rsp+130h+var_C0], 0
0x180021e59  cmp     edi, 80070005h
0x180021e5f  jnz     short loc_180021E68
0x180021e61  mov     ebx, 0C0000AF5h
0x180021e66  jmp     short loc_180021E8E
0x180021e68  cmp     edi, 80070050h
0x180021e6e  jz      short loc_180021E84
0x180021e70  cmp     edi, 80070002h
0x180021e76  jz      short loc_180021E84
0x180021e78  test    r12d, r12d
0x180021e7b  jz      short loc_180021E84
0x180021e7d  mov     ebx, 0C0000AF7h
0x180021e82  jmp     short loc_180021E8E
0x180021e84  mov     edi, 80070020h
0x180021e89  mov     ebx, 0C0000AF3h
0x180021e8e  mov     rdx, [rbp+3Fh+var_B0]; unsigned __int16 *
0x180021e92  lea     rcx, [rbp+3Fh+FileInformation.nFileSizeLow]; this
0x180021e96  call    ?Copy@SMALL_STRU@@QEAAJPEBG@Z; SMALL_STRU::Copy(ushort const *)
0x180021e9b  mov     [rsp+130h+var_F8], 0
0x180021ea4  lea     rax, [rsp+130h+var_C0]
0x180021ea9  mov     [rsp+130h+var_100], 0
0x180021eb2  lea     rcx, [rbp+3Fh+FileInformation]
0x180021eb6  mov     [rsp+130h+var_108], 0
0x180021ebe  mov     r9d, ebx
0x180021ec1  mov     r8d, 4
0x180021ec7  mov     [rsp+130h+lpOverlapped], rax
0x180021ecc  mov     edx, edi
0x180021ece  call    ?SetErrorInfo@PARSE_ERROR_INFO@@QEAAJJW4PARSE_ERROR_TYPE@@KQEAPEBDKPEAVIConfigDom@@PEAVIConfigDomNode@@@Z; PARSE_ERROR_INFO::SetErrorInfo(long,PARSE_ERROR_TYPE,ulong,char const * * const,ulong,IConfigDom *,IConfigDomNode *)
0x180021ed3  mov     ecx, 178h; Size
0x180021ed8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021edd  test    rax, rax
0x180021ee0  jz      short loc_180021F1D
0x180021ee2  mov     rcx, rax; this
0x180021ee5  call    ??0CONFIG_EXCEPTION@@QEAA@XZ; CONFIG_EXCEPTION::CONFIG_EXCEPTION(void)
0x180021eea  mov     rbx, rax
0x180021eed  test    rax, rax
0x180021ef0  jz      short loc_180021F1D
0x180021ef2  lea     rdx, [rbp+3Fh+FileInformation]; struct PARSE_ERROR_INFO *
0x180021ef6  mov     rcx, rax; this
0x180021ef9  call    ?Create@CONFIG_EXCEPTION@@QEAAJPEAVPARSE_ERROR_INFO@@@Z; CONFIG_EXCEPTION::Create(PARSE_ERROR_INFO *)
0x180021efe  test    eax, eax
0x180021f00  js      short loc_180021F0E
0x180021f02  lea     rdx, [rbx+8]; perrinfo
0x180021f06  xor     ecx, ecx; dwReserved
0x180021f08  call    cs:__imp_SetErrorInfo
0x180021f0e  mov     rax, [rbx]
0x180021f11  mov     rcx, rbx
0x180021f14  mov     rax, [rax+10h]
0x180021f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021f1d  lea     rcx, [rbp+3Fh+FileInformation]; this
0x180021f21  call    ??1PARSE_ERROR_INFO@@UEAA@XZ; PARSE_ERROR_INFO::~PARSE_ERROR_INFO(void)
0x180021f26  cmp     r14, 0FFFFFFFFFFFFFFFFh
0x180021f2a  jz      short loc_180021F35
0x180021f2c  mov     rcx, r14; hObject
0x180021f2f  call    cs:__imp_CloseHandle
0x180021f35  test    cs:Microsoft_Windows_IIS_ConfigurationEnableBits, 20h
0x180021f3c  jz      short loc_180021F4D
0x180021f3e  mov     r8d, edi
0x180021f41  lea     rdx, NATIVERD_EVENT_COMMIT_CHANGES_END_FILE_WRITE_OPERATION
0x180021f48  call    McTemplateU0q_EtwEventWriteTransfer
0x180021f4d  mov     eax, edi
0x180021f4f  mov     rcx, [rbp+3Fh+var_50]
0x180021f53  xor     rcx, rsp; StackCookie
0x180021f56  call    __security_check_cookie
0x180021f5b  add     rsp, 0F8h
0x180021f62  pop     r15
0x180021f64  pop     r14
  ... truncated ...
```
