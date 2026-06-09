# TextLogRenameLogFile

- ea: `0x1800054d4`
- end: `0x1800057a1`
- name: `TextLogRenameLogFile`
- size: `717`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800063bc`

## callees

- `0x180003820`
- `0x180003988`
- `0x180004cb4`
- `0x180004e0c`
- `0x180004ec4`
- `0x1800054d4`
- `0x1800058a0`
- `0x1800059f4`
- `0x180006fb0`
- `0x180007b4c`
- `0x180007ff0`
- `0x1800080b8`
- `0x18000a1a0`

## import_xrefs

- `ntdll!NtClose` at `0x1800055e4`
- `ntdll!NtClose` at `0x1800055e4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005773`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055ed`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800056bc`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005773`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000560a`
- `KERNEL32!DeleteFileW` at `0x18000576b`
- `KERNEL32!DeleteFileW` at `0x18000576b`
- `KERNEL32!GetFileInformationByHandle` at `0x18000574f`
- `KERNEL32!GetFileInformationByHandle` at `0x18000574f`
- `KERNEL32!CreateHardLinkW` at `0x18000564c`
- `KERNEL32!CreateHardLinkW` at `0x18000564c`
- `KERNEL32!FlushFileBuffers` at `0x1800056ca`
- `KERNEL32!FlushFileBuffers` at `0x1800056ca`

## string_xrefs

- `0x18000556b`: `SYSTEM\Setup\SetupapiLogRename`

## pseudocode

```c
__int64 __fastcall TextLogRenameLogFile(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // ebx
  DWORD LastError; // edi
  int v6; // r12d
  __int64 v7; // rax
  const WCHAR *FileTitle; // r13
  DWORD Value; // r14d
  int v10; // r14d
  DWORD v11; // r13d
  unsigned int v12; // r14d
  __int64 v14; // [rsp+34h] [rbp-2D4h] BYREF
  int v15; // [rsp+3Ch] [rbp-2CCh]
  int v16; // [rsp+40h] [rbp-2C8h]
  int v17; // [rsp+44h] [rbp-2C4h]
  HANDLE Handle; // [rsp+48h] [rbp-2C0h] BYREF
  int v19; // [rsp+50h] [rbp-2B8h]
  __int64 v20; // [rsp+58h] [rbp-2B0h]
  __int128 v21; // [rsp+60h] [rbp-2A8h] BYREF
  int v22; // [rsp+70h] [rbp-298h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-290h] BYREF
  WCHAR FileName[264]; // [rsp+B0h] [rbp-258h] BYREF

  v20 = a1;
  v4 = 0;
  LastError = 0;
  v15 = 0;
  v6 = 0;
  v16 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  v7 = *(_QWORD *)(a1 + 32);
  Handle = 0;
  v17 = 0;
  v14 = 0;
  FileTitle = *(const WCHAR **)(v7 + 16);
  if ( !TextLogOffline )
    FileTitle = (const WCHAR *)pSetupGetFileTitle(*(_QWORD *)(v7 + 16));
  Value = pSetupOpenKey(-2147483646, L"SYSTEM\\Setup\\SetupapiLogRename", a3, 1, &Handle);
  HIDWORD(v14) = Value;
  if ( !Value )
  {
    LODWORD(v14) = 520;
    Value = pSetupQueryValue(Handle, FileTitle, (__int64)&v14);
    HIDWORD(v14) = Value;
    if ( !Value && (v17 != 1 || (unsigned int)v14 <= 2) )
    {
      Value = 13;
      HIDWORD(v14) = 13;
    }
  }
  if ( Handle )
    NtClose((HANDLE)(unsigned int)Handle);
  SetLastError(Value);
  if ( Value )
  {
    if ( !*(_DWORD *)(a1 + 48)
      || !(unsigned int)TextLogGenerateBackupLogFileName(*(_QWORD *)(*(_QWORD *)(a1 + 32) + 16LL), FileName) )
    {
LABEL_13:
      LastError = GetLastError();
      goto LABEL_29;
    }
    v10 = v15;
  }
  else
  {
    v10 = 1;
    v15 = 1;
  }
  if ( !CreateHardLinkW(FileName, *(LPCWSTR *)(*(_QWORD *)(a1 + 32) + 16LL), 0) )
    goto LABEL_13;
  v6 = 1;
  v16 = 1;
  if ( v10 )
  {
    v11 = 0;
    v12 = 0;
    v19 = 0;
    v21 = 0;
    v22 = 0;
    while ( (unsigned int)TextLogEnumerateOpenSections(a1, v12, &v21) )
    {
      if ( !DWORD1(v21) && (v22 & 0x10000) != 0 )
      {
        v11 = TextLogDeleteCtlTag(a1, v12);
        break;
      }
      v19 = ++v12;
    }
    SetLastError(v11);
    v10 = v15;
  }
  FlushFileBuffers(*(HANDLE *)a1);
  *(_DWORD *)(a1 + 44) = 0;
  pSetupUnmapFileAndSetEOF(*(HANDLE *)a1, *(HANDLE *)(a1 + 8), *(LPCVOID *)(a1 + 16));
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 8) = 0;
  if ( !(unsigned int)pSetupDeleteFileByHandle(*(HANDLE *)a1) )
    goto LABEL_13;
  v6 = 0;
  v16 = 0;
  if ( v10 )
    TextLogSetLogRenameFilename(*(_QWORD *)(a1 + 32));
  TextLogUnmapFile(a1);
  pSetupSetFileCompressionState(FileName);
LABEL_29:
  if ( v6
    && *(_QWORD *)a1 != -1
    && GetFileInformationByHandle(*(HANDLE *)a1, &FileInformation)
    && FileInformation.nNumberOfLinks > 1 )
  {
    DeleteFileW(FileName);
  }
  SetLastError(LastError);
  LOBYTE(v4) = LastError == 0;
  return v4;
}

```

## disassembly

```asm
0x1800054d4  push    rbx
0x1800054d6  push    rsi
0x1800054d7  push    rdi
0x1800054d8  push    r12
0x1800054da  push    r13
0x1800054dc  push    r14
0x1800054de  sub     rsp, 2D8h
0x1800054e5  mov     rax, cs:__security_cookie
0x1800054ec  xor     rax, rsp
0x1800054ef  mov     [rsp+308h+var_48], rax
0x1800054f7  mov     rsi, rcx
0x1800054fa  mov     [rsp+308h+var_2B0], rcx
0x1800054ff  xor     ebx, ebx
0x180005501  mov     edi, ebx
0x180005503  mov     [rsp+308h+var_2CC], ebx
0x180005507  mov     r12d, ebx
0x18000550a  mov     [rsp+308h+var_2C8], ebx
0x18000550e  xorps   xmm0, xmm0
0x180005511  xor     eax, eax
0x180005513  movups  xmmword ptr [rsp+308h+FileInformation.dwFileAttributes], xmm0
0x180005518  movups  xmmword ptr [rsp+308h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x180005520  movups  xmmword ptr [rsp+308h+FileInformation.nFileSizeHigh], xmm0
0x180005528  mov     [rsp+308h+FileInformation.nFileIndexLow], eax
0x18000552f  mov     rax, [rcx+20h]
0x180005533  mov     dword ptr [rsp+308h+var_2D4+4], ebx
0x180005537  mov     [rsp+308h+Handle], rbx
0x18000553c  mov     [rsp+308h+var_2C4], ebx
0x180005540  mov     dword ptr [rsp+308h+var_2D4], ebx
0x180005544  mov     r13, [rax+10h]
0x180005548  cmp     cs:TextLogOffline, ebx
0x18000554e  jnz     short loc_18000555B
0x180005550  mov     rcx, r13
0x180005553  call    pSetupGetFileTitle
0x180005558  mov     r13, rax
0x18000555b  lea     rax, [rsp+308h+Handle]
0x180005560  mov     [rsp+308h+var_2E8], rax
0x180005565  mov     r9d, 1
0x18000556b  lea     rdx, aSystemSetupSet; "SYSTEM\\Setup\\SetupapiLogRename"
0x180005572  mov     rcx, 0FFFFFFFF80000002h
0x180005579  call    pSetupOpenKey
0x18000557e  mov     r14d, eax
0x180005581  mov     dword ptr [rsp+308h+var_2D4+4], eax
0x180005585  test    eax, eax
0x180005587  jnz     short loc_1800055D9
0x180005589  mov     dword ptr [rsp+308h+var_2D4], 208h
0x180005591  lea     rax, [rsp+308h+var_2D4]
0x180005596  mov     [rsp+308h+var_2E8], rax; __int64
0x18000559b  lea     r9, [rsp+308h+FileName]
0x1800055a3  lea     r8, [rsp+308h+var_2C4]
0x1800055a8  mov     rdx, r13; SourceString
0x1800055ab  mov     rcx, [rsp+308h+Handle]; KeyHandle
0x1800055b0  call    pSetupQueryValue
0x1800055b5  mov     r14d, eax
0x1800055b8  mov     dword ptr [rsp+308h+var_2D4+4], eax
0x1800055bc  test    eax, eax
0x1800055be  jnz     short loc_1800055D9
0x1800055c0  cmp     [rsp+308h+var_2C4], 1
0x1800055c5  jnz     short loc_1800055CE
0x1800055c7  cmp     dword ptr [rsp+308h+var_2D4], 2
0x1800055cc  ja      short loc_1800055D9
0x1800055ce  mov     r14d, 0Dh
0x1800055d4  mov     dword ptr [rsp+308h+var_2D4+4], r14d
0x1800055d9  cmp     [rsp+308h+Handle], rbx
0x1800055de  jz      short loc_1800055EA
0x1800055e0  mov     ecx, dword ptr [rsp+308h+Handle]; Handle
0x1800055e4  call    cs:__imp_NtClose
0x1800055ea  mov     ecx, r14d; dwErrCode
0x1800055ed  call    cs:__imp_SetLastError
0x1800055f3  test    r14d, r14d
0x1800055f6  jnz     short loc_180005605
0x1800055f8  mov     r14d, 1
0x1800055fe  mov     [rsp+308h+var_2CC], r14d
0x180005603  jmp     short loc_180005639
0x180005605  cmp     [rsi+30h], ebx
0x180005608  jnz     short loc_18000561B
0x18000560a  call    cs:__imp_GetLastError
0x180005610  mov     edi, eax
0x180005612  mov     [rsp+308h+var_2D8], eax
0x180005616  jmp     loc_180005725
0x18000561b  mov     rcx, [rsi+20h]
0x18000561f  lea     rdx, [rsp+308h+FileName]
0x180005627  mov     rcx, [rcx+10h]
0x18000562b  call    TextLogGenerateBackupLogFileName
0x180005630  test    eax, eax
0x180005632  jz      short loc_18000560A
0x180005634  mov     r14d, [rsp+308h+var_2CC]
0x180005639  mov     rdx, [rsi+20h]
0x18000563d  xor     r8d, r8d; lpSecurityAttributes
0x180005640  mov     rdx, [rdx+10h]; lpExistingFileName
0x180005644  lea     rcx, [rsp+308h+FileName]; lpFileName
0x18000564c  call    cs:__imp_CreateHardLinkW
0x180005652  test    eax, eax
0x180005654  jz      short loc_18000560A
0x180005656  mov     r12d, 1
0x18000565c  mov     [rsp+308h+var_2C8], r12d
0x180005661  test    r14d, r14d
0x180005664  jz      short loc_1800056C7
0x180005666  mov     r13d, ebx
0x180005669  mov     r14d, ebx
0x18000566c  mov     [rsp+308h+var_2B8], ebx
0x180005670  xorps   xmm0, xmm0
0x180005673  xor     eax, eax
0x180005675  movups  [rsp+308h+var_2A8], xmm0
0x18000567a  mov     [rsp+308h+var_298], eax
0x18000567e  lea     r8, [rsp+308h+var_2A8]
0x180005683  mov     edx, r14d
0x180005686  mov     rcx, rsi
0x180005689  call    TextLogEnumerateOpenSections
0x18000568e  test    eax, eax
0x180005690  jz      short loc_1800056B9
0x180005692  cmp     dword ptr [rsp+308h+var_2A8+4], ebx
0x180005696  jnz     short loc_1800056AF
0x180005698  test    byte ptr [rsp+308h+var_298+2], r12b
0x18000569d  jz      short loc_1800056AF
0x18000569f  mov     edx, r14d
0x1800056a2  mov     rcx, rsi
0x1800056a5  call    TextLogDeleteCtlTag
0x1800056aa  mov     r13d, eax
0x1800056ad  jmp     short loc_1800056B9
0x1800056af  inc     r14d
0x1800056b2  mov     [rsp+308h+var_2B8], r14d
0x1800056b7  jmp     short loc_18000567E
0x1800056b9  mov     ecx, r13d; dwErrCode
0x1800056bc  call    cs:__imp_SetLastError
0x1800056c2  mov     r14d, [rsp+308h+var_2CC]
0x1800056c7  mov     rcx, [rsi]; hFile
0x1800056ca  call    cs:__imp_FlushFileBuffers
0x1800056d0  mov     [rsi+2Ch], ebx
0x1800056d3  mov     r8, [rsi+10h]; lpBaseAddress
0x1800056d7  mov     rdx, [rsi+8]; hObject
0x1800056db  mov     rcx, [rsi]; hFile
0x1800056de  call    pSetupUnmapFileAndSetEOF
0x1800056e3  mov     [rsi+10h], rbx
0x1800056e7  mov     [rsi+8], rbx
0x1800056eb  mov     rcx, [rsi]; FileHandle
0x1800056ee  call    pSetupDeleteFileByHandle
0x1800056f3  test    eax, eax
0x1800056f5  jz      loc_18000560A
0x1800056fb  mov     r12d, ebx
0x1800056fe  mov     [rsp+308h+var_2C8], ebx
0x180005702  test    r14d, r14d
0x180005705  jz      short loc_180005710
0x180005707  mov     rcx, [rsi+20h]
0x18000570b  call    TextLogSetLogRenameFilename
0x180005710  mov     rcx, rsi
0x180005713  call    TextLogUnmapFile
0x180005718  lea     rcx, [rsp+308h+FileName]
0x180005720  call    pSetupSetFileCompressionState
0x180005725  jmp     short loc_18000573C
0x180005727  mov     edi, 54Fh
0x18000572c  mov     [rsp+308h+var_2D8], edi
0x180005730  xor     ebx, ebx
0x180005732  mov     r12d, [rsp+308h+var_2C8]
0x180005737  mov     rsi, [rsp+308h+var_2B0]
0x18000573c  test    r12d, r12d
0x18000573f  jz      short loc_180005771
0x180005741  cmp     qword ptr [rsi], 0FFFFFFFFFFFFFFFFh
0x180005745  jz      short loc_180005771
0x180005747  lea     rdx, [rsp+308h+FileInformation]; lpFileInformation
0x18000574c  mov     rcx, [rsi]; hFile
0x18000574f  call    cs:__imp_GetFileInformationByHandle
0x180005755  test    eax, eax
0x180005757  jz      short loc_180005771
0x180005759  cmp     [rsp+308h+FileInformation.nNumberOfLinks], 1
0x180005761  jbe     short loc_180005771
0x180005763  lea     rcx, [rsp+308h+FileName]; lpFileName
0x18000576b  call    cs:__imp_DeleteFileW
0x180005771  mov     ecx, edi; dwErrCode
0x180005773  call    cs:__imp_SetLastError
0x180005779  test    edi, edi
0x18000577b  setz    bl
0x18000577e  mov     eax, ebx
0x180005780  mov     rcx, [rsp+308h+var_48]
0x180005788  xor     rcx, rsp; StackCookie
0x18000578b  call    __security_check_cookie
0x180005790  add     rsp, 2D8h
0x180005797  pop     r14
0x180005799  pop     r13
0x18000579b  pop     r12
0x18000579d  pop     rdi
0x18000579e  pop     rsi
0x18000579f  pop     rbx
0x1800057a0  retn
```
