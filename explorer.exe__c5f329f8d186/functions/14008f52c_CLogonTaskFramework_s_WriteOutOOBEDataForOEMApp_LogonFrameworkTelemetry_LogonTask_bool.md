# CLogonTaskFramework::s_WriteOutOOBEDataForOEMApp(LogonFrameworkTelemetry::LogonTask *,bool)

- ea: `0x14008f52c`
- end: `0x14008f9da`
- name: `?s_WriteOutOOBEDataForOEMApp@CLogonTaskFramework@@CAXPEAVLogonTask@LogonFrameworkTelemetry@@_N@Z`
- size: `1198`
- prototype: `void __fastcall(struct LogonFrameworkTelemetry::LogonTask *, char, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x140025e1c`

## callees

- `0x14000bb20`
- `0x14001b2c8`
- `0x14001c330`
- `0x140027508`
- `0x14008f52c`
- `0x14009ea84`
- `0x1400aff60`
- `0x14010e160`
- `0x1401460b4`
- `0x14019b6c4`
- `0x1401c93e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008f831`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14008f831`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14008f7a4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14008f7a4`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14008f7f5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x14008f7f5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008f842`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14008f842`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14008f5d8`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x14008f5d8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x14008f764`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x14008f764`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x14008f866`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x14008f866`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x14008f6e0`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x14008f6e0`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008f73f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008f8c5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008f8f7`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008f73f`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008f8c5`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008f8f7`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x14008f934`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x14008f934`

## string_xrefs

- `0x14008f6fd`: `shell\lib\logontasks\logontasks.cpp`
- `0x14008f85f`: `%systemroot%\system32\oobe\info`
- `0x14008f8a1`: `userchoices.xml`

## pseudocode

```c
void __fastcall CLogonTaskFramework::s_WriteOutOOBEDataForOEMApp(
        struct LogonFrameworkTelemetry::LogonTask *a1,
        char a2,
        __int64 a3)
{
  LSTATUS ValueW; // eax
  __int64 v6; // r8
  bool v7; // sf
  int v8; // eax
  HRESULT v9; // eax
  wil::details::in1diag3 *v10; // rcx
  __int64 v11; // rdx
  HANDLE FileW; // rax
  int Error; // eax
  const char *v14; // r9
  __int64 v15; // rbx
  HRESULT v16; // eax
  wil::details::in1diag3 *v17; // rcx
  __int64 v18; // rdx
  int pdwType; // [rsp+20h] [rbp-E0h]
  char v20; // [rsp+40h] [rbp-C0h] BYREF
  char v21[3]; // [rsp+41h] [rbp-BFh] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD NumberOfBytesWritten; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  PCWSTR pszPathIn; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  PCNZWCH sourceString; // [rsp+70h] [rbp-90h] BYREF
  __int64 v29; // [rsp+78h] [rbp-88h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  unsigned __int16 *v31; // [rsp+88h] [rbp-78h] BYREF
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  PCWSTR pszMore[3]; // [rsp+A0h] [rbp-60h]
  __int128 Buffer; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 pvData[136]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR pszPathOut[264]; // [rsp+1E0h] [rbp+E0h] BYREF
  WCHAR v38[264]; // [rsp+3F0h] [rbp+2F0h] BYREF
  WCHAR ExistingFileName[264]; // [rsp+600h] [rbp+500h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+848h] [rbp+748h]

  if ( (byte_14024FCC1 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_WriteDataForOEMApp_Start,
      a3,
      1,
      &Buffer);
  v21[0] = 0;
  v20 = 0;
  pcbData = 260;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE",
             L"OEMAppId",
             2u,
             0,
             pvData,
             &pcbData);
  v7 = ValueW < 0;
  if ( ValueW )
  {
    pvData[0] = 0;
    if ( ValueW > 0 )
      v7 = 1;
  }
  if ( !v7 )
  {
    v21[0] = 1;
    sourceString = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
    v32 = -1;
    v33 = -1;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
    v29 = -1;
    v30 = -1;
    if ( (int)ParseAppUserModelId(pvData, (unsigned __int16 **)&sourceString, &v31) < 0 )
    {
LABEL_36:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v31);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&sourceString);
      goto LABEL_37;
    }
    pszPathIn = 0;
    v26 = 0;
    v27 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPathIn);
    v26 = -1;
    v27 = -1;
    if ( (int)GetImmersiveApplicationAppDataPath(sourceString) < 0 )
    {
LABEL_35:
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pszPathIn);
      goto LABEL_36;
    }
    v20 = 1;
    Buffer = 0;
    pcbData = 16;
    v8 = SHRegGetValueW(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\OOBE\\Stats",
           L"EndTimeStamp",
           8,
           0,
           &Buffer,
           &pcbData);
    if ( v8 > 0 )
      v8 = (unsigned __int16)v8 | 0x80070000;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1D43,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v8,
        pdwType);
LABEL_25:
      if ( !(unsigned int)SHExpandEnvironmentStringsW(L"%systemroot%\\system32\\oobe\\info", v38, 260) )
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x1D5C,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          v14);
        goto LABEL_35;
      }
      pszMore[0] = L"userdata.blob";
      pszMore[1] = L"sessionkey.blob";
      pszMore[2] = L"userchoices.xml";
      v15 = 0;
      while ( 1 )
      {
        v16 = PathCchCombine(ExistingFileName, 0x104u, v38, pszMore[v15]);
        v17 = retaddr;
        if ( v16 >= 0 )
        {
          v16 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, pszMore[v15]);
          v17 = retaddr;
          if ( v16 >= 0 )
          {
            CopyFileW(ExistingFileName, pszPathOut, 1);
            goto LABEL_34;
          }
          v18 = 7525;
        }
        else
        {
          v18 = 7522;
        }
        wil::details::in1diag3::_Log_Hr(
          v17,
          (void *)v18,
          (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
          (const char *)(unsigned int)v16,
          pdwType);
LABEL_34:
        if ( ++v15 == 3 )
          goto LABEL_35;
      }
    }
    v9 = PathCchCombine(pszPathOut, 0x104u, pszPathIn, L"timestamp.blob");
    v10 = retaddr;
    if ( v9 >= 0 )
    {
      if ( PathFileExistsW(pszPathOut) )
        goto LABEL_25;
      hFile = 0;
      FileW = CreateFileW(pszPathOut, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      v9 = ResultFromWin32Handle(FileW, &hFile);
      v10 = retaddr;
      if ( v9 >= 0 )
      {
        NumberOfBytesWritten = 0;
        if ( WriteFile(hFile, &Buffer, 0x10u, &NumberOfBytesWritten, 0) )
          Error = 0;
        else
          Error = ResultFromKnownLastError();
        if ( Error < 0 )
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1D4F,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)Error,
            pdwType);
          DeleteFileW(pszPathOut);
        }
        CloseHandle(hFile);
        goto LABEL_25;
      }
      v11 = 7500;
    }
    else
    {
      v11 = 7495;
    }
    wil::details::in1diag3::_Log_Hr(
      v10,
      (void *)v11,
      (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
      (const char *)(unsigned int)v9,
      pdwType);
    goto LABEL_25;
  }
LABEL_37:
  if ( a2 )
    LogonFrameworkTelemetry::LogonTask::WriteDataForOemApp<bool &,bool &>(a1, v21, &v20);
  if ( (byte_14024FCC1 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_WriteDataForOEMApp_Stop,
      v6,
      1,
      &Buffer);
}

```

## disassembly

```asm
0x14008f52c  mov     [rsp-8+arg_8], rbx
0x14008f531  mov     [rsp-8+arg_10], rsi
0x14008f536  push    rbp
0x14008f537  push    rdi
0x14008f538  push    r13
0x14008f53a  push    r14
0x14008f53c  push    r15
0x14008f53e  lea     rbp, [rsp-720h]
0x14008f546  sub     rsp, 820h
0x14008f54d  mov     rax, cs:__security_cookie
0x14008f554  xor     rax, rsp
0x14008f557  mov     [rbp+740h+var_30], rax
0x14008f55e  mov     dil, dl
0x14008f561  mov     rsi, rcx
0x14008f564  test    cs:byte_14024FCC1, 20h
0x14008f56b  jz      short loc_14008F58F
0x14008f56d  lea     rax, [rbp+740h+Buffer]
0x14008f571  mov     [rsp+840h+pdwType], rax
0x14008f576  mov     r9d, 1
0x14008f57c  lea     rdx, Explorer_WriteDataForOEMApp_Start
0x14008f583  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14008f58a  call    McGenEventWrite_EventWriteTransfer
0x14008f58f  xor     r14d, r14d
0x14008f592  mov     [rsp+840h+var_7FF], r14b
0x14008f597  mov     [rsp+840h+var_800], r14b
0x14008f59c  mov     [rsp+840h+var_7FC], 104h
0x14008f5a4  lea     rax, [rsp+840h+var_7FC]
0x14008f5a9  mov     [rsp+840h+pcbData], rax; pcbData
0x14008f5ae  lea     rax, [rbp+740h+var_770]
0x14008f5b2  mov     [rsp+840h+pvData], rax; pvData
0x14008f5b7  mov     [rsp+840h+pdwType], r14; pdwType
0x14008f5bc  lea     r9d, [r14+2]; dwFlags
0x14008f5c0  lea     r8, aOemappid; "OEMAppId"
0x14008f5c7  lea     rdx, aSoftwareMicros_14; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14008f5ce  mov     r13, 0FFFFFFFF80000002h
0x14008f5d5  mov     rcx, r13; hkey
0x14008f5d8  call    cs:__imp_RegGetValueW
0x14008f5df  nop     dword ptr [rax+rax+00h]
0x14008f5e4  mov     r15d, 80070000h
0x14008f5ea  test    eax, eax
0x14008f5ec  jz      short loc_14008F5FD
0x14008f5ee  mov     [rbp+740h+var_770], r14w
0x14008f5f3  jle     short loc_14008F5FD
0x14008f5f5  movzx   eax, ax
0x14008f5f8  or      eax, r15d
0x14008f5fb  test    eax, eax
0x14008f5fd  js      loc_14008F96C
0x14008f603  mov     [rsp+840h+var_7FF], 1
0x14008f608  mov     [rsp+840h+sourceString], r14
0x14008f60d  mov     [rsp+840h+var_7C8], r14
0x14008f612  mov     [rbp+740h+var_7C0], r14
0x14008f616  mov     [rbp+740h+var_7B8], r14
0x14008f61a  mov     [rbp+740h+var_7B0], r14
0x14008f61e  mov     [rbp+740h+var_7A8], r14
0x14008f622  lea     rcx, [rbp+740h+var_7B8]
0x14008f626  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008f62b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x14008f62f  mov     [rbp+740h+var_7B0], rbx
0x14008f633  mov     [rbp+740h+var_7A8], rbx
0x14008f637  lea     rcx, [rsp+840h+sourceString]
0x14008f63c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008f641  mov     [rsp+840h+var_7C8], rbx
0x14008f646  mov     [rbp+740h+var_7C0], rbx
0x14008f64a  lea     r8, [rbp+740h+var_7B8]; unsigned __int16 **
0x14008f64e  lea     rdx, [rsp+840h+sourceString]; unsigned __int16 **
0x14008f653  lea     rcx, [rbp+740h+var_770]; unsigned __int16 *
0x14008f657  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x14008f65c  test    eax, eax
0x14008f65e  js      loc_14008F958
0x14008f664  mov     [rsp+840h+pszPathIn], r14
0x14008f669  mov     [rsp+840h+var_7E0], r14
0x14008f66e  mov     [rsp+840h+var_7D8], r14
0x14008f673  lea     rcx, [rsp+840h+pszPathIn]
0x14008f678  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008f67d  mov     [rsp+840h+var_7E0], rbx
0x14008f682  mov     [rsp+840h+var_7D8], rbx
0x14008f687  lea     r8, [rsp+840h+pszPathIn]
0x14008f68c  mov     rcx, [rsp+840h+sourceString]; sourceString
0x14008f691  call    GetImmersiveApplicationAppDataPath
0x14008f696  test    eax, eax
0x14008f698  js      loc_14008F94D
0x14008f69e  mov     [rsp+840h+var_800], 1
0x14008f6a3  xorps   xmm0, xmm0
0x14008f6a6  movups  [rbp+740h+Buffer], xmm0
0x14008f6aa  mov     ebx, 10h
0x14008f6af  mov     [rsp+840h+var_7FC], ebx
0x14008f6b3  lea     rax, [rsp+840h+var_7FC]
0x14008f6b8  mov     [rsp+840h+pcbData], rax; pcbData
0x14008f6bd  lea     rax, [rbp+740h+Buffer]
0x14008f6c1  mov     [rsp+840h+pvData], rax; pvData
0x14008f6c6  mov     [rsp+840h+pdwType], r14; int
0x14008f6cb  lea     r9d, [rbx-8]; srrfFlags
0x14008f6cf  lea     r8, aEndtimestamp; "EndTimeStamp"
0x14008f6d6  lea     rdx, aSoftwareMicros_113; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x14008f6dd  mov     rcx, r13; hkey
0x14008f6e0  call    cs:__imp_SHRegGetValueW
0x14008f6e7  nop     dword ptr [rax+rax+00h]
0x14008f6ec  test    eax, eax
0x14008f6ee  jle     short loc_14008F6F6
0x14008f6f0  movzx   eax, ax
0x14008f6f3  or      eax, r15d
0x14008f6f6  mov     rcx, [rbp+748h]; this
0x14008f6fd  lea     r15, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x14008f704  test    eax, eax
0x14008f706  jns     short loc_14008F723
0x14008f708  mov     r9d, eax; char *
0x14008f70b  mov     r8, r15; unsigned int
0x14008f70e  mov     edx, 1D43h; void *
0x14008f713  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008f718  mov     r13d, 104h
0x14008f71e  jmp     loc_14008F84E
0x14008f723  lea     r9, aTimestampBlob; "timestamp.blob"
0x14008f72a  mov     r8, [rsp+840h+pszPathIn]; pszPathIn
0x14008f72f  mov     r13d, 104h
0x14008f735  mov     edx, r13d; cchPathOut
0x14008f738  lea     rcx, [rbp+740h+pszPathOut]; pszPathOut
0x14008f73f  call    cs:__imp_PathCchCombine
0x14008f746  nop     dword ptr [rax+rax+00h]
0x14008f74b  mov     rcx, [rbp+748h]
0x14008f752  test    eax, eax
0x14008f754  jns     short loc_14008F75D
0x14008f756  mov     edx, 1D47h
0x14008f75b  jmp     short loc_14008F7CD
0x14008f75d  lea     rcx, [rbp+740h+pszPathOut]; pszPath
0x14008f764  call    cs:__imp_PathFileExistsW
0x14008f76b  nop     dword ptr [rax+rax+00h]
0x14008f770  test    eax, eax
0x14008f772  jnz     loc_14008F84E
0x14008f778  mov     [rsp+840h+hFile], r14
0x14008f77d  mov     [rsp+840h+pcbData], r14; hTemplateFile
0x14008f782  mov     dword ptr [rsp+840h+pvData], 80h; dwFlagsAndAttributes
0x14008f78a  mov     dword ptr [rsp+840h+pdwType], 2; int
0x14008f792  xor     r9d, r9d; lpSecurityAttributes
0x14008f795  xor     r8d, r8d; dwShareMode
0x14008f798  mov     edx, 40000000h; dwDesiredAccess
0x14008f79d  lea     rcx, [rbp+740h+pszPathOut]; lpFileName
0x14008f7a4  call    cs:__imp_CreateFileW
0x14008f7ab  nop     dword ptr [rax+rax+00h]
0x14008f7b0  mov     rcx, rax; void *
0x14008f7b3  lea     rdx, [rsp+840h+hFile]; void **
0x14008f7b8  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x14008f7bd  mov     rcx, [rbp+748h]; this
0x14008f7c4  test    eax, eax
0x14008f7c6  jns     short loc_14008F7DA
0x14008f7c8  mov     edx, 1D4Ch; void *
0x14008f7cd  mov     r8, r15; unsigned int
0x14008f7d0  mov     r9d, eax; char *
0x14008f7d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008f7d8  jmp     short loc_14008F84E
0x14008f7da  mov     [rsp+840h+NumberOfBytesWritten], r14d
0x14008f7df  mov     [rsp+840h+pdwType], r14; int
0x14008f7e4  lea     r9, [rsp+840h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x14008f7e9  mov     r8d, ebx; nNumberOfBytesToWrite
0x14008f7ec  lea     rdx, [rbp+740h+Buffer]; lpBuffer
0x14008f7f0  mov     rcx, [rsp+840h+hFile]; hFile
0x14008f7f5  call    cs:__imp_WriteFile
0x14008f7fc  nop     dword ptr [rax+rax+00h]
0x14008f801  test    eax, eax
0x14008f803  jz      short loc_14008F80A
0x14008f805  mov     eax, r14d
0x14008f808  jmp     short loc_14008F80F
0x14008f80a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14008f80f  mov     rcx, [rbp+748h]; this
0x14008f816  test    eax, eax
0x14008f818  jns     short loc_14008F83D
0x14008f81a  mov     r9d, eax; char *
0x14008f81d  mov     r8, r15; unsigned int
0x14008f820  mov     edx, 1D4Fh; void *
0x14008f825  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008f82a  lea     rcx, [rbp+740h+pszPathOut]; lpFileName
0x14008f831  call    cs:__imp_DeleteFileW
0x14008f838  nop     dword ptr [rax+rax+00h]
0x14008f83d  mov     rcx, [rsp+840h+hFile]; hObject
0x14008f842  call    cs:__imp_CloseHandle
0x14008f849  nop     dword ptr [rax+rax+00h]
0x14008f84e  mov     rbx, [rbp+748h]
0x14008f855  mov     r8d, r13d
0x14008f858  lea     rdx, [rbp+740h+var_450]
0x14008f85f  lea     rcx, aSystemrootSyst_0; "%systemroot%\\system32\\oobe\\info"
0x14008f866  call    cs:__imp_SHExpandEnvironmentStringsW
0x14008f86d  nop     dword ptr [rax+rax+00h]
0x14008f872  test    eax, eax
0x14008f874  jnz     short loc_14008F88B
0x14008f876  mov     r8, r15; unsigned int
0x14008f879  mov     edx, 1D5Ch; void *
0x14008f87e  mov     rcx, rbx; this
0x14008f881  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x14008f886  jmp     loc_14008F94D
0x14008f88b  lea     rax, aUserdataBlob; "userdata.blob"
0x14008f892  mov     [rbp+740h+pszMore], rax
0x14008f896  lea     rax, aSessionkeyBlob; "sessionkey.blob"
0x14008f89d  mov     [rbp+740h+var_798], rax
0x14008f8a1  lea     rax, aUserchoicesXml; "userchoices.xml"
0x14008f8a8  mov     [rbp+740h+var_790], rax
0x14008f8ac  mov     rbx, r14
0x14008f8af  mov     r9, [rbp+rbx*8+740h+pszMore]; pszMore
0x14008f8b4  lea     r8, [rbp+740h+var_450]; pszPathIn
0x14008f8bb  mov     rdx, r13; cchPathOut
0x14008f8be  lea     rcx, [rbp+740h+ExistingFileName]; pszPathOut
0x14008f8c5  call    cs:__imp_PathCchCombine
0x14008f8cc  nop     dword ptr [rax+rax+00h]
0x14008f8d1  mov     rcx, [rbp+748h]
0x14008f8d8  test    eax, eax
0x14008f8da  jns     short loc_14008F8E3
0x14008f8dc  mov     edx, 1D62h
0x14008f8e1  jmp     short loc_14008F913
0x14008f8e3  mov     r9, [rbp+rbx*8+740h+pszMore]; pszMore
0x14008f8e8  mov     r8, [rsp+840h+pszPathIn]; pszPathIn
0x14008f8ed  mov     rdx, r13; cchPathOut
0x14008f8f0  lea     rcx, [rbp+740h+pszPathOut]; pszPathOut
0x14008f8f7  call    cs:__imp_PathCchCombine
0x14008f8fe  nop     dword ptr [rax+rax+00h]
0x14008f903  mov     rcx, [rbp+748h]; this
0x14008f90a  test    eax, eax
0x14008f90c  jns     short loc_14008F920
0x14008f90e  mov     edx, 1D65h; void *
0x14008f913  mov     r8, r15; unsigned int
0x14008f916  mov     r9d, eax; char *
0x14008f919  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008f91e  jmp     short loc_14008F940
0x14008f920  mov     r8d, 1; bFailIfExists
0x14008f926  lea     rdx, [rbp+740h+pszPathOut]; lpNewFileName
0x14008f92d  lea     rcx, [rbp+740h+ExistingFileName]; lpExistingFileName
0x14008f934  call    cs:__imp_CopyFileW
0x14008f93b  nop     dword ptr [rax+rax+00h]
0x14008f940  inc     rbx
0x14008f943  cmp     rbx, 3
0x14008f947  jnz     loc_14008F8AF
0x14008f94d  lea     rcx, [rsp+840h+pszPathIn]
0x14008f952  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008f957  nop
0x14008f958  lea     rcx, [rbp+740h+var_7B8]
0x14008f95c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008f961  nop
0x14008f962  lea     rcx, [rsp+840h+sourceString]
0x14008f967  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008f96c  test    dil, dil
0x14008f96f  jz      short loc_14008F983
0x14008f971  lea     r8, [rsp+840h+var_800]
0x14008f976  lea     rdx, [rsp+840h+var_7FF]
0x14008f97b  mov     rcx, rsi
0x14008f97e  call    ??$WriteDataForOemApp@AEA_NAEA_N@LogonTask@LogonFrameworkTelemetry@@QEAAXAEA_N0@Z; LogonFrameworkTelemetry::LogonTask::WriteDataForOemApp<bool &,bool &>(bool &,bool &)
0x14008f983  test    cs:byte_14024FCC1, 20h
0x14008f98a  jz      short loc_14008F9AE
0x14008f98c  lea     rax, [rbp+740h+Buffer]
0x14008f990  mov     [rsp+840h+pdwType], rax
0x14008f995  mov     r9d, 1
0x14008f99b  lea     rdx, Explorer_WriteDataForOEMApp_Stop
0x14008f9a2  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14008f9a9  call    McGenEventWrite_EventWriteTransfer
0x14008f9ae  mov     rcx, [rbp+740h+var_30]
0x14008f9b5  xor     rcx, rsp; StackCookie
0x14008f9b8  call    __security_check_cookie
0x14008f9bd  lea     r11, [rsp+840h+var_20]
0x14008f9c5  mov     rbx, [r11+38h]
0x14008f9c9  mov     rsi, [r11+40h]
0x14008f9cd  mov     rsp, r11
0x14008f9d0  pop     r15
0x14008f9d2  pop     r14
0x14008f9d4  pop     r13
0x14008f9d6  pop     rdi
0x14008f9d7  pop     rbp
0x14008f9d8  retn
```
