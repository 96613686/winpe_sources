# FvePersistentRequest::SaveRequest(void *,ulong)

- ea: `0x1800ef200`
- end: `0x1800ef7ea`
- name: `?SaveRequest@FvePersistentRequest@@QEAAJPEAXK@Z`
- size: `1514`
- prototype: `void __noreturn(FvePersistentRequest *__hidden this, void *, unsigned int)`
- caller_count: `4`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800f19c0`
- `0x1800f2a20`
- `0x1800f42a0`
- `0x1800f48c0`

## callees

- `0x1800045f8`
- `0x180008d70`
- `0x1800090c0`
- `0x180019128`
- `0x180045ff0`
- `0x1800485f0`
- `0x18004ad74`
- `0x1800ed528`
- `0x1800edec4`
- `0x1800ef0d0`
- `0x1800ef200`
- `0x1800f0a00`
- `0x18011efce`
- `0x18011f010`
- `0x180129010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef66d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef3ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef49f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef516`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef591`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef608`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ef66d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef776`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef4ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef5e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ef776`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ef486`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ef578`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ef486`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x1800ef578`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef503`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef5f5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef503`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1800ef5f5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ef3d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800ef3d5`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800ef655`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x1800ef655`

## string_xrefs

- `0x1800ef412`: `CreateFile`
- `0x1800ef649`: `WriteFileData`
- `0x1800ef557`: `WriteFileHeader`

## pseudocode

```c
void __fastcall __noreturn FvePersistentRequest::SaveRequest(FvePersistentRequest *this, void *a2, DWORD a3)
{
  unsigned int v5; // edi
  __int64 FileW; // r14
  BOOL v7; // r15d
  const wchar_t *v8; // rsi
  int FolderName; // ebx
  signed int LastError; // eax
  signed int v11; // eax
  signed int v12; // eax
  signed int v13; // eax
  signed int v14; // eax
  signed int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // r8
  __int64 v18; // r9
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  int v20; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  struct _GUID v22; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v23[24]; // [rsp+60h] [rbp-A0h] BYREF
  DWORD nNumberOfBytesToWrite; // [rsp+78h] [rbp-88h] BYREF
  DWORD NumberOfBytesWritten; // [rsp+80h] [rbp-80h] BYREF
  __int64 Buffer; // [rsp+88h] [rbp-78h] BYREF
  DWORD v27; // [rsp+90h] [rbp-70h]
  WCHAR FileName[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v29[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  unsigned __int16 v30[264]; // [rsp+4C0h] [rbp+3C0h] BYREF

  nNumberOfBytesToWrite = a3;
  Buffer = 0;
  v27 = 0;
  NumberOfBytesWritten = 0;
  v5 = 0;
  FileW = -1;
  memset_0(v29, 0, 0x208u);
  memset_0(v30, 0, 0x208u);
  v7 = 0;
  v8 = L"NA";
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids);
  FolderName = FvePersistentRequest::GetFolderName(*((unsigned int *)this + 2), v29);
  if ( FolderName )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
    if ( FolderName < 0 )
      goto LABEL_61;
  }
  FolderName = MakeSystemVolumeInformationPath((const unsigned __int16 *)this + 6, v29, v30);
  if ( FolderName )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
    if ( FolderName < 0 )
      goto LABEL_61;
  }
  v22 = (struct _GUID)*((_OWORD *)this + 66);
  FolderName = FvePersistentRequest::BuildPersistentRequestFilePath(v30, &v22, FileName);
  if ( FolderName )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
    if ( FolderName < 0 )
      goto LABEL_61;
  }
  FileW = (__int64)CreateFileW(FileName, 0x40000000u, 0, 0, 1u, 0x80u, 0);
  if ( FileW == -1 )
  {
    LastError = GetLastError();
    FolderName = LastError;
    if ( LastError > 0 )
      FolderName = (unsigned __int16)LastError | 0x80070000;
    if ( FolderName != -2147024864 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    v8 = L"CreateFile";
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        68,
        &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
        (unsigned int)FolderName);
  }
  else
  {
    HIDWORD(Buffer) = *((_DWORD *)this + 2);
    v27 = nNumberOfBytesToWrite;
    LODWORD(Buffer) = 1;
    NumberOfBytesWritten = 12;
    if ( WriteFile((HANDLE)FileW, &Buffer, 0xCu, &NumberOfBytesWritten, 0) )
    {
      if ( WriteFile((HANDLE)FileW, a2, nNumberOfBytesToWrite, &nNumberOfBytesToWrite, 0) )
      {
        v7 = FlushFileBuffers((HANDLE)FileW);
        if ( !v7 )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs();
          v15 = GetLastError();
          v5 = v15;
          if ( v15 > 0 )
            v5 = (unsigned __int16)v15 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v5);
          v8 = L"FlushFileBuffers";
        }
      }
      else
      {
        MicrosoftTelemetryAssertTriggeredNoArgs();
        v13 = GetLastError();
        FolderName = v13;
        if ( v13 > 0 )
          FolderName = (unsigned __int16)v13 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_D(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            71,
            &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
            (unsigned int)FolderName);
        CloseHandle((HANDLE)FileW);
        FileW = -1;
        v7 = DeleteFileW(FileName);
        if ( !v7 )
        {
          v14 = GetLastError();
          v5 = v14;
          if ( v14 > 0 )
            v5 = (unsigned __int16)v14 | 0x80070000;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 72, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v5);
        }
        v8 = L"WriteFileData";
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredNoArgs();
      v11 = GetLastError();
      FolderName = v11;
      if ( v11 > 0 )
        FolderName = (unsigned __int16)v11 | 0x80070000;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_D(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          69,
          &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
          (unsigned int)FolderName);
      CloseHandle((HANDLE)FileW);
      FileW = -1;
      v7 = DeleteFileW(FileName);
      if ( !v7 )
      {
        v12 = GetLastError();
        v5 = v12;
        if ( v12 > 0 )
          v5 = (unsigned __int16)v12 | 0x80070000;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_D(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids, v5);
      }
      v8 = L"WriteFileHeader";
    }
  }
  if ( FolderName < 0 )
LABEL_61:
    (*(void (__fastcall **)(FvePersistentRequest *, _QWORD))(*(_QWORD *)this + 24LL))(this, (unsigned int)FolderName);
  TelemetryProviderRegistrar::TelemetryProviderRegistrar(
    (TelemetryProviderRegistrar *)v23,
    &g_hBitLockerKeyRollProvider,
    &g_bitLockerKeyRollProviderInitLock,
    &g_bitLockerKeyRollProviderRefCount);
  if ( (FolderName < 0 || !v7)
    && (unsigned int)dword_180172588 > 5
    && (unsigned __int8)tlgKeywordOn(&dword_180172588, 0x400000000000LL) )
  {
    v21 = 0x1000000;
    *(_QWORD *)&v22.Data1 = v8;
    v19 = v5;
    v20 = FolderName;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<8>>(
      v16,
      (int)&dword_18016046C,
      v17,
      v18,
      (__int64)&v20,
      (__int64)&v19,
      (const size_t **)&v22,
      (__int64)&v21);
  }
  if ( FileW != -1 )
    CloseHandle((HANDLE)FileW);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      74,
      &WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids,
      (unsigned int)FolderName);
  TelemetryProviderRegistrar::~TelemetryProviderRegistrar((TelemetryProviderRegistrar *)v23);
}

```

## disassembly

```asm
0x1800ef200  mov     [rsp-8+arg_18], rbx
0x1800ef205  push    rbp
0x1800ef206  push    rsi
0x1800ef207  push    rdi
0x1800ef208  push    r12
0x1800ef20a  push    r13
0x1800ef20c  push    r14
0x1800ef20e  push    r15
0x1800ef210  lea     rbp, [rsp-5E0h]
0x1800ef218  sub     rsp, 6E0h
0x1800ef21f  mov     rax, cs:__security_cookie
0x1800ef226  xor     rax, rsp
0x1800ef229  mov     [rbp+610h+var_40], rax
0x1800ef230  xor     eax, eax
0x1800ef232  mov     [rsp+710h+nNumberOfBytesToWrite], r8d
0x1800ef237  mov     r12, rdx
0x1800ef23a  mov     [rbp+610h+Buffer], rax
0x1800ef23e  mov     r13, rcx
0x1800ef241  mov     [rbp+610h+var_680], eax
0x1800ef244  mov     ebx, 208h
0x1800ef249  mov     [rbp+610h+NumberOfBytesWritten], eax
0x1800ef24c  mov     r8d, ebx; Size
0x1800ef24f  lea     rcx, [rbp+610h+var_460]; void *
0x1800ef256  xor     edx, edx; Val
0x1800ef258  xor     edi, edi
0x1800ef25a  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ef25e  call    memset_0
0x1800ef263  mov     r8d, ebx; Size
0x1800ef266  lea     rcx, [rbp+610h+var_250]; void *
0x1800ef26d  xor     edx, edx; Val
0x1800ef26f  call    memset_0
0x1800ef274  xor     r15d, r15d
0x1800ef277  lea     rsi, aNa
0x1800ef27e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef285  lea     rax, WPP_GLOBAL_Control
0x1800ef28c  cmp     rcx, rax
0x1800ef28f  jz      short loc_1800EF2AA
0x1800ef291  test    byte ptr [rcx+1Ch], 20h
0x1800ef295  jz      short loc_1800EF2AA
0x1800ef297  mov     rcx, [rcx+10h]
0x1800ef29b  lea     edx, [rdi+40h]
0x1800ef29e  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef2a5  call    WPP_SF_
0x1800ef2aa  mov     ecx, [r13+8]
0x1800ef2ae  lea     rdx, [rbp+610h+var_460]
0x1800ef2b5  call    ?GetFolderName@FvePersistentRequest@@SAJW4_FVE_REQUEST_TYPE@@PEAGK@Z
0x1800ef2ba  mov     ebx, eax
0x1800ef2bc  test    eax, eax
0x1800ef2be  jz      short loc_1800EF2F9
0x1800ef2c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef2c7  lea     rax, WPP_GLOBAL_Control
0x1800ef2ce  cmp     rcx, rax
0x1800ef2d1  jz      short loc_1800EF2F1
0x1800ef2d3  test    byte ptr [rcx+1Ch], 40h
0x1800ef2d7  jz      short loc_1800EF2F1
0x1800ef2d9  mov     rcx, [rcx+10h]
0x1800ef2dd  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef2e4  mov     edx, 41h ; 'A'
0x1800ef2e9  mov     r9d, ebx
0x1800ef2ec  call    WPP_SF_d
0x1800ef2f1  test    ebx, ebx
0x1800ef2f3  js      loc_1800EF6C4
0x1800ef2f9  lea     rcx, [r13+0Ch]; unsigned __int16 *
0x1800ef2fd  lea     r8, [rbp+610h+var_250]; unsigned __int16 *
0x1800ef304  lea     rdx, [rbp+610h+var_460]; unsigned __int16 *
0x1800ef30b  call    ?MakeSystemVolumeInformationPath@@YAJPEBG0PEAGK@Z
0x1800ef310  mov     ebx, eax
0x1800ef312  test    eax, eax
0x1800ef314  jz      short loc_1800EF34F
0x1800ef316  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef31d  lea     rax, WPP_GLOBAL_Control
0x1800ef324  cmp     rcx, rax
0x1800ef327  jz      short loc_1800EF347
0x1800ef329  test    byte ptr [rcx+1Ch], 40h
0x1800ef32d  jz      short loc_1800EF347
0x1800ef32f  mov     rcx, [rcx+10h]
0x1800ef333  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef33a  mov     edx, 42h ; 'B'
0x1800ef33f  mov     r9d, ebx
0x1800ef342  call    WPP_SF_d
0x1800ef347  test    ebx, ebx
0x1800ef349  js      loc_1800EF6C4
0x1800ef34f  movups  xmm0, xmmword ptr [r13+420h]
0x1800ef357  lea     r8, [rbp+610h+FileName]; unsigned __int16 *
0x1800ef35b  lea     rdx, [rsp+710h+var_6C0]; struct _GUID
0x1800ef360  lea     rcx, [rbp+610h+var_250]; unsigned __int16 *
0x1800ef367  movdqu  xmmword ptr [rsp+710h+var_6C0.Data1], xmm0
0x1800ef36d  call    ?BuildPersistentRequestFilePath@FvePersistentRequest@@SAJPEBGU_GUID@@PEAGK@Z
0x1800ef372  mov     ebx, eax
0x1800ef374  test    eax, eax
0x1800ef376  jz      short loc_1800EF3B1
0x1800ef378  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef37f  lea     rax, WPP_GLOBAL_Control
0x1800ef386  cmp     rcx, rax
0x1800ef389  jz      short loc_1800EF3A9
0x1800ef38b  test    byte ptr [rcx+1Ch], 40h
0x1800ef38f  jz      short loc_1800EF3A9
0x1800ef391  mov     rcx, [rcx+10h]
0x1800ef395  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef39c  mov     edx, 43h ; 'C'
0x1800ef3a1  mov     r9d, ebx
0x1800ef3a4  call    WPP_SF_d
0x1800ef3a9  test    ebx, ebx
0x1800ef3ab  js      loc_1800EF6C4
0x1800ef3b1  mov     [rsp+710h+hTemplateFile], rdi; hTemplateFile
0x1800ef3b6  lea     rcx, [rbp+610h+FileName]; lpFileName
0x1800ef3ba  mov     [rsp+710h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800ef3c2  xor     r9d, r9d; lpSecurityAttributes
0x1800ef3c5  xor     r8d, r8d; dwShareMode
0x1800ef3c8  mov     [rsp+710h+dwCreationDisposition], 1; dwCreationDisposition
0x1800ef3d0  mov     edx, 40000000h; dwDesiredAccess
0x1800ef3d5  call    cs:__imp_CreateFileW
0x1800ef3dc  nop     dword ptr [rax+rax+00h]
0x1800ef3e1  mov     r14, rax
0x1800ef3e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ef3e8  jnz     short loc_1800EF457
0x1800ef3ea  call    cs:__imp_GetLastError
0x1800ef3f1  nop     dword ptr [rax+rax+00h]
0x1800ef3f6  mov     ebx, eax
0x1800ef3f8  test    eax, eax
0x1800ef3fa  jle     short loc_1800EF405
0x1800ef3fc  movzx   ebx, ax
0x1800ef3ff  or      ebx, 80070000h
0x1800ef405  cmp     ebx, 80070020h
0x1800ef40b  jz      short loc_1800EF412
0x1800ef40d  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ef412  lea     rsi, aCreatefile
0x1800ef419  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef420  lea     r12, WPP_GLOBAL_Control
0x1800ef427  cmp     rcx, r12
0x1800ef42a  jz      loc_1800EF6C0
0x1800ef430  test    byte ptr [rcx+1Ch], 40h
0x1800ef434  jz      loc_1800EF6C0
0x1800ef43a  mov     rcx, [rcx+10h]
0x1800ef43e  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef445  mov     edx, 44h ; 'D'
0x1800ef44a  mov     r9d, ebx
0x1800ef44d  call    WPP_SF_d
0x1800ef452  jmp     loc_1800EF6C0
0x1800ef457  mov     eax, [r13+8]
0x1800ef45b  lea     r9, [rbp+610h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800ef45f  mov     dword ptr [rbp+610h+Buffer+4], eax
0x1800ef462  lea     rdx, [rbp+610h+Buffer]; lpBuffer
0x1800ef466  mov     eax, [rsp+710h+nNumberOfBytesToWrite]
0x1800ef46a  mov     r8d, 0Ch; nNumberOfBytesToWrite
0x1800ef470  mov     rcx, r14; hFile
0x1800ef473  mov     [rbp+610h+var_680], eax
0x1800ef476  mov     dword ptr [rbp+610h+Buffer], 1
0x1800ef47d  mov     [rbp+610h+NumberOfBytesWritten], r8d
0x1800ef481  mov     qword ptr [rsp+710h+dwCreationDisposition], rdi; lpOverlapped
0x1800ef486  call    cs:__imp_WriteFile
0x1800ef48d  nop     dword ptr [rax+rax+00h]
0x1800ef492  test    eax, eax
0x1800ef494  jnz     loc_1800EF563
0x1800ef49a  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ef49f  call    cs:__imp_GetLastError
0x1800ef4a6  nop     dword ptr [rax+rax+00h]
0x1800ef4ab  mov     ebx, eax
0x1800ef4ad  mov     esi, 80070000h
0x1800ef4b2  test    eax, eax
0x1800ef4b4  jle     short loc_1800EF4BB
0x1800ef4b6  movzx   ebx, ax
0x1800ef4b9  or      ebx, esi
0x1800ef4bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef4c2  lea     r12, WPP_GLOBAL_Control
0x1800ef4c9  cmp     rcx, r12
0x1800ef4cc  jz      short loc_1800EF4EC
0x1800ef4ce  test    byte ptr [rcx+1Ch], 2
0x1800ef4d2  jz      short loc_1800EF4EC
0x1800ef4d4  mov     rcx, [rcx+10h]
0x1800ef4d8  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef4df  mov     edx, 45h ; 'E'
0x1800ef4e4  mov     r9d, ebx
0x1800ef4e7  call    WPP_SF_D
0x1800ef4ec  mov     rcx, r14; hObject
0x1800ef4ef  call    cs:__imp_CloseHandle
0x1800ef4f6  nop     dword ptr [rax+rax+00h]
0x1800ef4fb  lea     rcx, [rbp+610h+FileName]; lpFileName
0x1800ef4ff  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ef503  call    cs:__imp_DeleteFileW
0x1800ef50a  nop     dword ptr [rax+rax+00h]
0x1800ef50f  mov     r15d, eax
0x1800ef512  test    eax, eax
0x1800ef514  jnz     short loc_1800EF557
0x1800ef516  call    cs:__imp_GetLastError
0x1800ef51d  nop     dword ptr [rax+rax+00h]
0x1800ef522  mov     edi, eax
0x1800ef524  test    eax, eax
0x1800ef526  jle     short loc_1800EF52D
0x1800ef528  movzx   edi, ax
0x1800ef52b  or      edi, esi
0x1800ef52d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef534  cmp     rcx, r12
0x1800ef537  jz      short loc_1800EF557
0x1800ef539  test    byte ptr [rcx+1Ch], 2
0x1800ef53d  jz      short loc_1800EF557
0x1800ef53f  mov     rcx, [rcx+10h]
0x1800ef543  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef54a  mov     edx, 46h ; 'F'
0x1800ef54f  mov     r9d, edi
0x1800ef552  call    WPP_SF_D
0x1800ef557  lea     rsi, aWritefileheade
0x1800ef55e  jmp     loc_1800EF6C0
0x1800ef563  mov     r8d, [rsp+710h+nNumberOfBytesToWrite]; nNumberOfBytesToWrite
0x1800ef568  lea     r9, [rsp+710h+nNumberOfBytesToWrite]; lpNumberOfBytesWritten
0x1800ef56d  mov     rdx, r12; lpBuffer
0x1800ef570  mov     qword ptr [rsp+710h+dwCreationDisposition], rdi; lpOverlapped
0x1800ef575  mov     rcx, r14; hFile
0x1800ef578  call    cs:__imp_WriteFile
0x1800ef57f  nop     dword ptr [rax+rax+00h]
0x1800ef584  test    eax, eax
0x1800ef586  jnz     loc_1800EF652
0x1800ef58c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ef591  call    cs:__imp_GetLastError
0x1800ef598  nop     dword ptr [rax+rax+00h]
0x1800ef59d  mov     ebx, eax
0x1800ef59f  mov     esi, 80070000h
0x1800ef5a4  test    eax, eax
0x1800ef5a6  jle     short loc_1800EF5AD
0x1800ef5a8  movzx   ebx, ax
0x1800ef5ab  or      ebx, esi
0x1800ef5ad  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef5b4  lea     r12, WPP_GLOBAL_Control
0x1800ef5bb  cmp     rcx, r12
0x1800ef5be  jz      short loc_1800EF5DE
0x1800ef5c0  test    byte ptr [rcx+1Ch], 2
0x1800ef5c4  jz      short loc_1800EF5DE
0x1800ef5c6  mov     rcx, [rcx+10h]
0x1800ef5ca  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef5d1  mov     edx, 47h ; 'G'
0x1800ef5d6  mov     r9d, ebx
0x1800ef5d9  call    WPP_SF_D
0x1800ef5de  mov     rcx, r14; hObject
0x1800ef5e1  call    cs:__imp_CloseHandle
0x1800ef5e8  nop     dword ptr [rax+rax+00h]
0x1800ef5ed  lea     rcx, [rbp+610h+FileName]; lpFileName
0x1800ef5f1  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800ef5f5  call    cs:__imp_DeleteFileW
0x1800ef5fc  nop     dword ptr [rax+rax+00h]
0x1800ef601  mov     r15d, eax
0x1800ef604  test    eax, eax
0x1800ef606  jnz     short loc_1800EF649
0x1800ef608  call    cs:__imp_GetLastError
0x1800ef60f  nop     dword ptr [rax+rax+00h]
0x1800ef614  mov     edi, eax
0x1800ef616  test    eax, eax
0x1800ef618  jle     short loc_1800EF61F
0x1800ef61a  movzx   edi, ax
0x1800ef61d  or      edi, esi
0x1800ef61f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef626  cmp     rcx, r12
0x1800ef629  jz      short loc_1800EF649
0x1800ef62b  test    byte ptr [rcx+1Ch], 2
0x1800ef62f  jz      short loc_1800EF649
0x1800ef631  mov     rcx, [rcx+10h]
0x1800ef635  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef63c  mov     edx, 48h ; 'H'
0x1800ef641  mov     r9d, edi
0x1800ef644  call    WPP_SF_D
0x1800ef649  lea     rsi, aWritefiledata
0x1800ef650  jmp     short loc_1800EF6C0
0x1800ef652  mov     rcx, r14; hFile
0x1800ef655  call    cs:__imp_FlushFileBuffers
0x1800ef65c  nop     dword ptr [rax+rax+00h]
0x1800ef661  mov     r15d, eax
0x1800ef664  test    eax, eax
0x1800ef666  jnz     short loc_1800EF6C0
0x1800ef668  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800ef66d  call    cs:__imp_GetLastError
0x1800ef674  nop     dword ptr [rax+rax+00h]
0x1800ef679  mov     edi, eax
0x1800ef67b  test    eax, eax
0x1800ef67d  jle     short loc_1800EF688
0x1800ef67f  movzx   edi, ax
0x1800ef682  or      edi, 80070000h
0x1800ef688  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ef68f  lea     rax, WPP_GLOBAL_Control
0x1800ef696  cmp     rcx, rax
0x1800ef699  jz      short loc_1800EF6B9
0x1800ef69b  test    byte ptr [rcx+1Ch], 2
0x1800ef69f  jz      short loc_1800EF6B9
0x1800ef6a1  mov     rcx, [rcx+10h]
0x1800ef6a5  lea     r8, WPP_ca4cf9acdf9f36f83f89016d740473cc_Traceguids
0x1800ef6ac  mov     edx, 49h ; 'I'
0x1800ef6b1  mov     r9d, edi
0x1800ef6b4  call    WPP_SF_D
0x1800ef6b9  lea     rsi, aFlushfilebuffe
0x1800ef6c0  test    ebx, ebx
0x1800ef6c2  jns     short loc_1800EF6D6
0x1800ef6c4  mov     rax, [r13+0]
0x1800ef6c8  mov     edx, ebx
0x1800ef6ca  mov     rcx, r13
0x1800ef6cd  mov     rax, [rax+18h]
0x1800ef6d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ef6d6  lea     r9, ?g_bitLockerKeyRollProviderRefCount@@3JC; volatile int *
0x1800ef6dd  lea     r8, ?g_bitLockerKeyRollProviderInitLock@@3U_RTL_SRWLOCK@@A; struct _RTL_SRWLOCK *
0x1800ef6e4  lea     rdx, g_hBitLockerKeyRollProvider; struct _tlgProvider_t **
0x1800ef6eb  lea     rcx, [rsp+710h+var_6B0]; this
0x1800ef6f0  call    ??0TelemetryProviderRegistrar@@QEAA@PEBQEBU_tlgProvider_t@@PEAU_RTL_SRWLOCK@@PECJ@Z
0x1800ef6f5  test    ebx, ebx
  ... truncated ...
```
