# CLogonTaskFramework::s_WriteOutOOBEDataForOEMApp(LogonFrameworkTelemetry::LogonTask *,bool)

- ea: `0x140089c7c`
- end: `0x14008a0e1`
- name: `?s_WriteOutOOBEDataForOEMApp@CLogonTaskFramework@@CAXPEAVLogonTask@LogonFrameworkTelemetry@@_N@Z`
- size: `1125`
- prototype: `void __fastcall(struct LogonFrameworkTelemetry::LogonTask *, bool)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1400334f4`

## callees

- `0x14000d890`
- `0x140016b10`
- `0x14001eba8`
- `0x140034d20`
- `0x140089c7c`
- `0x14009943c`
- `0x1400aa27c`
- `0x1401040e0`
- `0x140139e64`
- `0x14018ee98`
- `0x1401ca600`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140089f5d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x140089f5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140089edc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140089edc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140089f27`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x140089f27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140089f68`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140089f68`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089d28`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140089d28`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x140089f86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!SHExpandEnvironmentStringsW` at `0x140089f86`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x140089ea2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x140089ea2`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x140089e2a`
- `api-ms-win-shcore-registry-l1-1-0!SHRegGetValueW` at `0x140089e2a`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x140089e83`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x140089fdf`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008a00b`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x140089e83`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x140089fdf`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x14008a00b`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x14008a042`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x14008a042`

## string_xrefs

- `0x140089e41`: `shell\lib\logontasks\logontasks.cpp`
- `0x140089fbb`: `userchoices.xml`
- `0x140089f7f`: `%systemroot%\system32\oobe\info`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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

  if ( (byte_140253B81 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_WriteDataForOEMApp_Start,
      a3,
      1);
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
        (void *)0x1D29,
        (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
        (const char *)(unsigned int)v8,
        pdwType);
LABEL_25:
      if ( !(unsigned int)SHExpandEnvironmentStringsW(L"%systemroot%\\system32\\oobe\\info", v38, 260) )
      {
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0x1D42,
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
          v18 = 7499;
        }
        else
        {
          v18 = 7496;
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
            (void *)0x1D35,
            (unsigned int)"shell\\lib\\logontasks\\logontasks.cpp",
            (const char *)(unsigned int)Error,
            pdwType);
          DeleteFileW(pszPathOut);
        }
        CloseHandle(hFile);
        goto LABEL_25;
      }
      v11 = 7474;
    }
    else
    {
      v11 = 7469;
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
  if ( (byte_140253B81 & 0x20) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      Explorer_WriteDataForOEMApp_Stop,
      v6,
      1);
}

```

## disassembly

```asm
0x140089c7c  mov     [rsp-8+arg_8], rbx
0x140089c81  mov     [rsp-8+arg_10], rsi
0x140089c86  push    rbp
0x140089c87  push    rdi
0x140089c88  push    r13
0x140089c8a  push    r14
0x140089c8c  push    r15
0x140089c8e  lea     rbp, [rsp-720h]
0x140089c96  sub     rsp, 820h
0x140089c9d  mov     rax, cs:__security_cookie
0x140089ca4  xor     rax, rsp
0x140089ca7  mov     [rbp+740h+var_30], rax
0x140089cae  mov     dil, dl
0x140089cb1  mov     rsi, rcx
0x140089cb4  test    cs:byte_140253B81, 20h
0x140089cbb  jz      short loc_140089CDF
0x140089cbd  lea     rax, [rbp+740h+Buffer]
0x140089cc1  mov     [rsp+840h+pdwType], rax
0x140089cc6  mov     r9d, 1
0x140089ccc  lea     rdx, Explorer_WriteDataForOEMApp_Start
0x140089cd3  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x140089cda  call    McGenEventWrite_EventWriteTransfer
0x140089cdf  xor     r14d, r14d
0x140089ce2  mov     [rsp+840h+var_7FF], r14b
0x140089ce7  mov     [rsp+840h+var_800], r14b
0x140089cec  mov     [rsp+840h+var_7FC], 104h
0x140089cf4  lea     rax, [rsp+840h+var_7FC]
0x140089cf9  mov     [rsp+840h+pcbData], rax; pcbData
0x140089cfe  lea     rax, [rbp+740h+var_770]
0x140089d02  mov     [rsp+840h+pvData], rax; pvData
0x140089d07  mov     [rsp+840h+pdwType], r14; pdwType
0x140089d0c  lea     r9d, [r14+2]; dwFlags
0x140089d10  lea     r8, aOemappid; "OEMAppId"
0x140089d17  lea     rdx, SubKey; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140089d1e  mov     r13, 0FFFFFFFF80000002h
0x140089d25  mov     rcx, r13; hkey
0x140089d28  call    cs:__imp_RegGetValueW
0x140089d2e  mov     r15d, 80070000h
0x140089d34  test    eax, eax
0x140089d36  jz      short loc_140089D47
0x140089d38  mov     [rbp+740h+var_770], r14w
0x140089d3d  jle     short loc_140089D47
0x140089d3f  movzx   eax, ax
0x140089d42  or      eax, r15d
0x140089d45  test    eax, eax
0x140089d47  js      loc_14008A074
0x140089d4d  mov     [rsp+840h+var_7FF], 1
0x140089d52  mov     [rsp+840h+sourceString], r14
0x140089d57  mov     [rsp+840h+var_7C8], r14
0x140089d5c  mov     [rbp+740h+var_7C0], r14
0x140089d60  mov     [rbp+740h+var_7B8], r14
0x140089d64  mov     [rbp+740h+var_7B0], r14
0x140089d68  mov     [rbp+740h+var_7A8], r14
0x140089d6c  lea     rcx, [rbp+740h+var_7B8]
0x140089d70  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x140089d75  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140089d79  mov     [rbp+740h+var_7B0], rbx
0x140089d7d  mov     [rbp+740h+var_7A8], rbx
0x140089d81  lea     rcx, [rsp+840h+sourceString]
0x140089d86  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x140089d8b  mov     [rsp+840h+var_7C8], rbx
0x140089d90  mov     [rbp+740h+var_7C0], rbx
0x140089d94  lea     r8, [rbp+740h+var_7B8]; unsigned __int16 **
0x140089d98  lea     rdx, [rsp+840h+sourceString]; unsigned __int16 **
0x140089d9d  lea     rcx, [rbp+740h+var_770]; unsigned __int16 *
0x140089da1  call    ?ParseAppUserModelId@@YAJPEBGPEAPEAG1@Z; ParseAppUserModelId(ushort const *,ushort * *,ushort * *)
0x140089da6  test    eax, eax
0x140089da8  js      loc_14008A060
0x140089dae  mov     [rsp+840h+pszPathIn], r14
0x140089db3  mov     [rsp+840h+var_7E0], r14
0x140089db8  mov     [rsp+840h+var_7D8], r14
0x140089dbd  lea     rcx, [rsp+840h+pszPathIn]
0x140089dc2  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x140089dc7  mov     [rsp+840h+var_7E0], rbx
0x140089dcc  mov     [rsp+840h+var_7D8], rbx
0x140089dd1  lea     r8, [rsp+840h+pszPathIn]
0x140089dd6  mov     rcx, [rsp+840h+sourceString]; sourceString
0x140089ddb  call    GetImmersiveApplicationAppDataPath
0x140089de0  test    eax, eax
0x140089de2  js      loc_14008A055
0x140089de8  mov     [rsp+840h+var_800], 1
0x140089ded  xorps   xmm0, xmm0
0x140089df0  movups  [rbp+740h+Buffer], xmm0
0x140089df4  mov     ebx, 10h
0x140089df9  mov     [rsp+840h+var_7FC], ebx
0x140089dfd  lea     rax, [rsp+840h+var_7FC]
0x140089e02  mov     [rsp+840h+pcbData], rax; pcbData
0x140089e07  lea     rax, [rbp+740h+Buffer]
0x140089e0b  mov     [rsp+840h+pvData], rax; pvData
0x140089e10  mov     [rsp+840h+pdwType], r14; int
0x140089e15  lea     r9d, [rbx-8]; srrfFlags
0x140089e19  lea     r8, aEndtimestamp; "EndTimeStamp"
0x140089e20  lea     rdx, aSoftwareMicros_112; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x140089e27  mov     rcx, r13; hkey
0x140089e2a  call    cs:__imp_SHRegGetValueW
0x140089e30  test    eax, eax
0x140089e32  jle     short loc_140089E3A
0x140089e34  movzx   eax, ax
0x140089e37  or      eax, r15d
0x140089e3a  mov     rcx, [rbp+748h]; this
0x140089e41  lea     r15, aShellLibLogont_5; "shell\\lib\\logontasks\\logontasks.cpp"
0x140089e48  test    eax, eax
0x140089e4a  jns     short loc_140089E67
0x140089e4c  mov     r9d, eax; char *
0x140089e4f  mov     r8, r15; unsigned int
0x140089e52  mov     edx, 1D29h; void *
0x140089e57  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140089e5c  mov     r13d, 104h
0x140089e62  jmp     loc_140089F6E
0x140089e67  lea     r9, aTimestampBlob; "timestamp.blob"
0x140089e6e  mov     r8, [rsp+840h+pszPathIn]; pszPathIn
0x140089e73  mov     r13d, 104h
0x140089e79  mov     edx, r13d; cchPathOut
0x140089e7c  lea     rcx, [rbp+740h+pszPathOut]; pszPathOut
0x140089e83  call    cs:__imp_PathCchCombine
0x140089e89  mov     rcx, [rbp+748h]
0x140089e90  test    eax, eax
0x140089e92  jns     short loc_140089E9B
0x140089e94  mov     edx, 1D2Dh
0x140089e99  jmp     short loc_140089EFF
0x140089e9b  lea     rcx, [rbp+740h+pszPathOut]; pszPath
0x140089ea2  call    cs:__imp_PathFileExistsW
0x140089ea8  test    eax, eax
0x140089eaa  jnz     loc_140089F6E
0x140089eb0  mov     [rsp+840h+hFile], r14
0x140089eb5  mov     [rsp+840h+pcbData], r14; hTemplateFile
0x140089eba  mov     dword ptr [rsp+840h+pvData], 80h; dwFlagsAndAttributes
0x140089ec2  mov     dword ptr [rsp+840h+pdwType], 2; int
0x140089eca  xor     r9d, r9d; lpSecurityAttributes
0x140089ecd  xor     r8d, r8d; dwShareMode
0x140089ed0  mov     edx, 40000000h; dwDesiredAccess
0x140089ed5  lea     rcx, [rbp+740h+pszPathOut]; lpFileName
0x140089edc  call    cs:__imp_CreateFileW
0x140089ee2  mov     rcx, rax; void *
0x140089ee5  lea     rdx, [rsp+840h+hFile]; void **
0x140089eea  call    ?ResultFromWin32Handle@@YAJPEAXPEAPEAX@Z; ResultFromWin32Handle(void *,void * *)
0x140089eef  mov     rcx, [rbp+748h]; this
0x140089ef6  test    eax, eax
0x140089ef8  jns     short loc_140089F0C
0x140089efa  mov     edx, 1D32h; void *
0x140089eff  mov     r8, r15; unsigned int
0x140089f02  mov     r9d, eax; char *
0x140089f05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140089f0a  jmp     short loc_140089F6E
0x140089f0c  mov     [rsp+840h+NumberOfBytesWritten], r14d
0x140089f11  mov     [rsp+840h+pdwType], r14; int
0x140089f16  lea     r9, [rsp+840h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x140089f1b  mov     r8d, ebx; nNumberOfBytesToWrite
0x140089f1e  lea     rdx, [rbp+740h+Buffer]; lpBuffer
0x140089f22  mov     rcx, [rsp+840h+hFile]; hFile
0x140089f27  call    cs:__imp_WriteFile
0x140089f2d  test    eax, eax
0x140089f2f  jz      short loc_140089F36
0x140089f31  mov     eax, r14d
0x140089f34  jmp     short loc_140089F3B
0x140089f36  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x140089f3b  mov     rcx, [rbp+748h]; this
0x140089f42  test    eax, eax
0x140089f44  jns     short loc_140089F63
0x140089f46  mov     r9d, eax; char *
0x140089f49  mov     r8, r15; unsigned int
0x140089f4c  mov     edx, 1D35h; void *
0x140089f51  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140089f56  lea     rcx, [rbp+740h+pszPathOut]; lpFileName
0x140089f5d  call    cs:__imp_DeleteFileW
0x140089f63  mov     rcx, [rsp+840h+hFile]; hObject
0x140089f68  call    cs:__imp_CloseHandle
0x140089f6e  mov     rbx, [rbp+748h]
0x140089f75  mov     r8d, r13d
0x140089f78  lea     rdx, [rbp+740h+var_450]
0x140089f7f  lea     rcx, aSystemrootSyst_0; "%systemroot%\\system32\\oobe\\info"
0x140089f86  call    cs:__imp_SHExpandEnvironmentStringsW
0x140089f8c  test    eax, eax
0x140089f8e  jnz     short loc_140089FA5
0x140089f90  mov     r8, r15; unsigned int
0x140089f93  mov     edx, 1D42h; void *
0x140089f98  mov     rcx, rbx; this
0x140089f9b  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x140089fa0  jmp     loc_14008A055
0x140089fa5  lea     rax, aUserdataBlob; "userdata.blob"
0x140089fac  mov     [rbp+740h+pszMore], rax
0x140089fb0  lea     rax, aSessionkeyBlob; "sessionkey.blob"
0x140089fb7  mov     [rbp+740h+var_798], rax
0x140089fbb  lea     rax, aUserchoicesXml; "userchoices.xml"
0x140089fc2  mov     [rbp+740h+var_790], rax
0x140089fc6  mov     rbx, r14
0x140089fc9  mov     r9, [rbp+rbx*8+740h+pszMore]; pszMore
0x140089fce  lea     r8, [rbp+740h+var_450]; pszPathIn
0x140089fd5  mov     rdx, r13; cchPathOut
0x140089fd8  lea     rcx, [rbp+740h+ExistingFileName]; pszPathOut
0x140089fdf  call    cs:__imp_PathCchCombine
0x140089fe5  mov     rcx, [rbp+748h]
0x140089fec  test    eax, eax
0x140089fee  jns     short loc_140089FF7
0x140089ff0  mov     edx, 1D48h
0x140089ff5  jmp     short loc_14008A021
0x140089ff7  mov     r9, [rbp+rbx*8+740h+pszMore]; pszMore
0x140089ffc  mov     r8, [rsp+840h+pszPathIn]; pszPathIn
0x14008a001  mov     rdx, r13; cchPathOut
0x14008a004  lea     rcx, [rbp+740h+pszPathOut]; pszPathOut
0x14008a00b  call    cs:__imp_PathCchCombine
0x14008a011  mov     rcx, [rbp+748h]; this
0x14008a018  test    eax, eax
0x14008a01a  jns     short loc_14008A02E
0x14008a01c  mov     edx, 1D4Bh; void *
0x14008a021  mov     r8, r15; unsigned int
0x14008a024  mov     r9d, eax; char *
0x14008a027  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14008a02c  jmp     short loc_14008A048
0x14008a02e  mov     r8d, 1; bFailIfExists
0x14008a034  lea     rdx, [rbp+740h+pszPathOut]; lpNewFileName
0x14008a03b  lea     rcx, [rbp+740h+ExistingFileName]; lpExistingFileName
0x14008a042  call    cs:__imp_CopyFileW
0x14008a048  inc     rbx
0x14008a04b  cmp     rbx, 3
0x14008a04f  jnz     loc_140089FC9
0x14008a055  lea     rcx, [rsp+840h+pszPathIn]
0x14008a05a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008a05f  nop
0x14008a060  lea     rcx, [rbp+740h+var_7B8]
0x14008a064  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008a069  nop
0x14008a06a  lea     rcx, [rsp+840h+sourceString]
0x14008a06f  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x14008a074  test    dil, dil
0x14008a077  jz      short loc_14008A08B
0x14008a079  lea     r8, [rsp+840h+var_800]
0x14008a07e  lea     rdx, [rsp+840h+var_7FF]
0x14008a083  mov     rcx, rsi
0x14008a086  call    ??$WriteDataForOemApp@AEA_NAEA_N@LogonTask@LogonFrameworkTelemetry@@QEAAXAEA_N0@Z; LogonFrameworkTelemetry::LogonTask::WriteDataForOemApp<bool &,bool &>(bool &,bool &)
0x14008a08b  test    cs:byte_140253B81, 20h
0x14008a092  jz      short loc_14008A0B6
0x14008a094  lea     rax, [rbp+740h+Buffer]
0x14008a098  mov     [rsp+840h+pdwType], rax
0x14008a09d  mov     r9d, 1
0x14008a0a3  lea     rdx, Explorer_WriteDataForOEMApp_Stop
0x14008a0aa  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x14008a0b1  call    McGenEventWrite_EventWriteTransfer
0x14008a0b6  mov     rcx, [rbp+740h+var_30]
0x14008a0bd  xor     rcx, rsp; StackCookie
0x14008a0c0  call    __security_check_cookie
0x14008a0c5  lea     r11, [rsp+840h+var_20]
0x14008a0cd  mov     rbx, [r11+38h]
0x14008a0d1  mov     rsi, [r11+40h]
0x14008a0d5  mov     rsp, r11
0x14008a0d8  pop     r15
0x14008a0da  pop     r14
0x14008a0dc  pop     r13
0x14008a0de  pop     rdi
0x14008a0df  pop     rbp
0x14008a0e0  retn
```
