# DeletePoolFile(FileListItem * *)

- ea: `0x1800a83b8`
- end: `0x1800a867a`
- name: `?DeletePoolFile@@YAXPEAPEAUFileListItem@@@Z`
- size: `706`
- prototype: `void __fastcall(struct FileListItem **)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting`

## callers

- `0x1800278e8`
- `0x180034f5c`
- `0x1800a8730`
- `0x1800a899c`

## callees

- `0x18001fb10`
- `0x18003ea2c`
- `0x1800750e4`
- `0x1800a83b8`
- `0x1800a8680`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a83fd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800a83fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a843a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a853b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a855e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a85b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a85e1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a843a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a853b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a855e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a85b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800a85e1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8556`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800a8556`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a8524`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800a8524`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8505`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800a8505`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8531`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x1800a8531`
- `SPOOLSS!DllFreeSplMem` at `0x1800a8585`
- `SPOOLSS!DllFreeSplMem` at `0x1800a864c`
- `SPOOLSS!DllFreeSplMem` at `0x1800a8655`
- `SPOOLSS!DllFreeSplMem` at `0x1800a8585`
- `SPOOLSS!DllFreeSplMem` at `0x1800a864c`
- `SPOOLSS!DllFreeSplMem` at `0x1800a8655`

## string_xrefs

- `0x1800a8412`: `DeletePoolFile`
- `0x1800a84d5`: `Failed to delete pool file %ws. Error %d`
- `0x1800a8568`: `Failed to open pool file %ws. Error %d`

## pseudocode

```c
void __fastcall DeletePoolFile(struct FileListItem **a1, int a2)
{
  struct FileListItem *v3; // rbx
  __int64 v4; // rcx
  DWORD LastError; // eax
  const unsigned __int16 *v6; // rdx
  DWORD v7; // esi
  struct SplLogType *v8; // rax
  __int64 v9; // r8
  HANDLE FileW; // rax
  void *v11; // rsi
  DWORD v12; // eax
  DWORD v13; // eax
  __int64 v14; // rcx
  DWORD v15; // eax
  DWORD v16; // eax
  const unsigned __int16 *v17; // rdx
  struct SplLogType *v18; // rax
  const wchar_t *v19; // [rsp+40h] [rbp-49h] BYREF
  __int64 v20; // [rsp+48h] [rbp-41h]
  int v21; // [rsp+50h] [rbp-39h]
  DWORD v22; // [rsp+58h] [rbp-31h] BYREF
  __int64 v23; // [rsp+60h] [rbp-29h]
  int v24; // [rsp+68h] [rbp-21h]
  DWORD v25; // [rsp+70h] [rbp-19h] BYREF
  __int64 v26; // [rsp+78h] [rbp-11h]
  int v27; // [rsp+80h] [rbp-9h]
  const wchar_t *v28; // [rsp+88h] [rbp-1h] BYREF
  __int64 v29; // [rsp+90h] [rbp+7h]
  int v30; // [rsp+98h] [rbp+Fh]
  _BYTE v31[32]; // [rsp+A0h] [rbp+17h] BYREF
  __int64 v32; // [rsp+F0h] [rbp+67h] BYREF

  if ( a1 )
  {
    v3 = *a1;
    if ( *a1 )
    {
      FPCloseFiles(*a1, a2);
      DeleteCriticalSection((LPCRITICAL_SECTION)((char *)v3 + 24));
      v4 = *((_QWORD *)v3 + 9);
      if ( v4 )
      {
        LODWORD(v32) = 1;
        if ( !(unsigned int)SafeDeleteFileByHandle(v4, &v32) )
        {
          LastError = GetLastError();
          v6 = (const unsigned __int16 *)*((_QWORD *)v3 + 9);
          v7 = LastError;
          v22 = LastError;
          LODWORD(v19) = 104;
          v28 = L"-";
          v20 = 4;
          v21 = 0;
          v23 = 4;
          v24 = 0;
          v25 = 0;
          v26 = 4;
          v27 = 0;
          v29 = 4;
          v30 = 1;
          v8 = SplLogType::SplLogType((SplLogType *)v31, v6);
          SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v8, &v28, &v25, &v22, &v19, 0);
          v9 = *((_QWORD *)v3 + 9);
          if ( (_DWORD)v32 )
          {
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "DeletePoolFile",
              L"Failed to delete pool file %ws. Error %d",
              v9,
              v7);
            FileW = CreateFileW(*((LPCWSTR *)v3 + 9), 0xC0000000, 3u, 0, 3u, 0x8200080u, 0);
            v11 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              v13 = GetLastError();
              LocalSpoolerTelemetry::WriteDbgTraceError(
                "DeletePoolFile",
                L"Failed to open pool file %ws. Error %d",
                *((_QWORD *)v3 + 9),
                v13);
            }
            else
            {
              v32 = 0;
              if ( SetFilePointerEx(FileW, 0, 0, 0) && !SetEndOfFile(v11) )
              {
                v12 = GetLastError();
                LocalSpoolerTelemetry::WriteDbgTraceError(
                  "DeletePoolFile",
                  L"SetEndOfFile failed with error code %d",
                  v12);
              }
              CloseHandle(v11);
            }
          }
          else
          {
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "DeletePoolFile",
              L"Deletion failed. Invalid SPL file %ws. Error %d",
              v9,
              v7);
          }
        }
        DllFreeSplMem(*((_QWORD *)v3 + 9));
      }
      v14 = *((_QWORD *)v3 + 10);
      if ( v14 )
      {
        LODWORD(v32) = 1;
        if ( !(unsigned int)SafeDeleteFileByHandle(v14, &v32) )
        {
          if ( !(_DWORD)v32 )
          {
            v15 = GetLastError();
            LocalSpoolerTelemetry::WriteDbgTraceError(
              "DeletePoolFile",
              L"Deletion failed. Invalid SHD file %ws. Error %d",
              *((_QWORD *)v3 + 10),
              v15);
          }
          LODWORD(v28) = 104;
          v29 = 4;
          v30 = 0;
          v16 = GetLastError();
          v17 = (const unsigned __int16 *)*((_QWORD *)v3 + 10);
          v25 = v16;
          v26 = 4;
          v27 = 0;
          v22 = 0;
          v23 = 4;
          v24 = 0;
          v19 = L"-";
          v20 = 4;
          v21 = 1;
          v18 = SplLogType::SplLogType((SplLogType *)v31, v17);
          SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v18, &v19, &v22, &v25, &v28, 0);
        }
        DllFreeSplMem(*((_QWORD *)v3 + 10));
      }
      DllFreeSplMem(v3);
    }
  }
  *a1 = 0;
}

```

## disassembly

```asm
0x1800a83b8  mov     [rsp-8+arg_8], rbx
0x1800a83bd  mov     [rsp-8+arg_10], rsi
0x1800a83c2  push    rbp
0x1800a83c3  push    rdi
0x1800a83c4  push    r12
0x1800a83c6  push    r14
0x1800a83c8  push    r15
0x1800a83ca  lea     rbp, [rsp-37h]
0x1800a83cf  sub     rsp, 0C0h
0x1800a83d6  xor     r14d, r14d
0x1800a83d9  mov     rdi, rcx
0x1800a83dc  test    rcx, rcx
0x1800a83df  jz      loc_1800A865B
0x1800a83e5  mov     rbx, [rcx]
0x1800a83e8  test    rbx, rbx
0x1800a83eb  jz      loc_1800A865B
0x1800a83f1  mov     rcx, rbx; struct FileListItem *
0x1800a83f4  call    ?FPCloseFiles@@YAXPEAUFileListItem@@H@Z; FPCloseFiles(FileListItem *,int)
0x1800a83f9  lea     rcx, [rbx+18h]; lpCriticalSection
0x1800a83fd  call    cs:__imp_DeleteCriticalSection
0x1800a8403  mov     rcx, [rbx+48h]
0x1800a8407  lea     r12d, [r14+4]
0x1800a840b  lea     rsi, asc_1800ECF90; "-"
0x1800a8412  lea     r15, aDeletepoolfile; "DeletePoolFile"
0x1800a8419  test    rcx, rcx
0x1800a841c  jz      loc_1800A858B
0x1800a8422  lea     rdx, [rbp+57h+arg_0]
0x1800a8426  mov     dword ptr [rbp+57h+arg_0], 1
0x1800a842d  call    SafeDeleteFileByHandle
0x1800a8432  test    eax, eax
0x1800a8434  jnz     loc_1800A8581
0x1800a843a  call    cs:__imp_GetLastError
0x1800a8440  mov     rdx, [rbx+48h]; unsigned __int16 *
0x1800a8444  lea     rcx, [rbp+57h+var_40]; this
0x1800a8448  mov     esi, eax
0x1800a844a  mov     [rbp+57h+var_88], eax
0x1800a844d  lea     rax, asc_1800ECF90; "-"
0x1800a8454  mov     dword ptr [rbp+57h+var_A0], 68h ; 'h'
0x1800a845b  mov     [rbp+57h+var_58], rax
0x1800a845f  mov     [rbp+57h+var_98], r12
0x1800a8463  mov     [rbp+57h+var_90], r14d
0x1800a8467  mov     [rbp+57h+var_80], r12
0x1800a846b  mov     [rbp+57h+var_78], r14d
0x1800a846f  mov     [rbp+57h+var_70], r14d
0x1800a8473  mov     [rbp+57h+var_68], r12
0x1800a8477  mov     [rbp+57h+var_60], r14d
0x1800a847b  mov     [rbp+57h+var_50], r12
0x1800a847f  mov     [rbp+57h+var_48], 1
0x1800a8486  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800a848b  lea     rcx, [rbp+57h+var_A0]
0x1800a848f  mov     [rsp+0E0h+hTemplateFile], r14
0x1800a8494  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rcx
0x1800a8499  lea     r9, [rbp+57h+var_70]
0x1800a849d  lea     rcx, [rbp+57h+var_88]
0x1800a84a1  mov     rdx, rax; struct SplLogType *
0x1800a84a4  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rcx
0x1800a84a9  lea     r8, [rbp+57h+var_58]
0x1800a84ad  lea     rcx, SPOOLER_DELETE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800a84b4  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800a84b9  mov     r9d, esi
0x1800a84bc  mov     r8, [rbx+48h]
0x1800a84c0  mov     rcx, r15; char *
0x1800a84c3  cmp     dword ptr [rbp+57h+arg_0], r14d
0x1800a84c7  jnz     short loc_1800A84D5
0x1800a84c9  lea     rdx, aDeletionFailed; "Deletion failed. Invalid SPL file %ws. "...
0x1800a84d0  jmp     loc_1800A8575
0x1800a84d5  lea     rdx, aFailedToDelete_10; "Failed to delete pool file %ws. Error %"...
0x1800a84dc  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a84e1  mov     rcx, [rbx+48h]; lpFileName
0x1800a84e5  mov     r8d, 3; dwShareMode
0x1800a84eb  mov     [rsp+0E0h+hTemplateFile], r14; hTemplateFile
0x1800a84f0  xor     r9d, r9d; lpSecurityAttributes
0x1800a84f3  mov     [rsp+0E0h+dwFlagsAndAttributes], 8200080h; dwFlagsAndAttributes
0x1800a84fb  mov     edx, 0C0000000h; dwDesiredAccess
0x1800a8500  mov     [rsp+0E0h+dwCreationDisposition], r8d; dwCreationDisposition
0x1800a8505  call    cs:__imp_CreateFileW
0x1800a850b  mov     rsi, rax
0x1800a850e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800a8512  jz      short loc_1800A855E
0x1800a8514  xor     r9d, r9d; dwMoveMethod
0x1800a8517  mov     [rbp+57h+arg_0], r14
0x1800a851b  xor     r8d, r8d; lpNewFilePointer
0x1800a851e  mov     rdx, r14; liDistanceToMove
0x1800a8521  mov     rcx, rax; hFile
0x1800a8524  call    cs:__imp_SetFilePointerEx
0x1800a852a  test    eax, eax
0x1800a852c  jz      short loc_1800A8553
0x1800a852e  mov     rcx, rsi; hFile
0x1800a8531  call    cs:__imp_SetEndOfFile
0x1800a8537  test    eax, eax
0x1800a8539  jnz     short loc_1800A8553
0x1800a853b  call    cs:__imp_GetLastError
0x1800a8541  lea     rdx, aSetendoffileFa; "SetEndOfFile failed with error code %d"
0x1800a8548  mov     rcx, r15; char *
0x1800a854b  mov     r8d, eax
0x1800a854e  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a8553  mov     rcx, rsi; hObject
0x1800a8556  call    cs:__imp_CloseHandle
0x1800a855c  jmp     short loc_1800A857A
0x1800a855e  call    cs:__imp_GetLastError
0x1800a8564  mov     r8, [rbx+48h]
0x1800a8568  lea     rdx, aFailedToOpenPo; "Failed to open pool file %ws. Error %d"
0x1800a856f  mov     r9d, eax
0x1800a8572  mov     rcx, r15; char *
0x1800a8575  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a857a  lea     rsi, asc_1800ECF90; "-"
0x1800a8581  mov     rcx, [rbx+48h]
0x1800a8585  call    cs:__imp_DllFreeSplMem
0x1800a858b  mov     rcx, [rbx+50h]
0x1800a858f  test    rcx, rcx
0x1800a8592  jz      loc_1800A8652
0x1800a8598  lea     rdx, [rbp+57h+arg_0]
0x1800a859c  mov     dword ptr [rbp+57h+arg_0], 1
0x1800a85a3  call    SafeDeleteFileByHandle
0x1800a85a8  test    eax, eax
0x1800a85aa  jnz     loc_1800A8648
0x1800a85b0  cmp     dword ptr [rbp+57h+arg_0], r14d
0x1800a85b4  jnz     short loc_1800A85D2
0x1800a85b6  call    cs:__imp_GetLastError
0x1800a85bc  mov     r8, [rbx+50h]
0x1800a85c0  lea     rdx, aDeletionFailed_0; "Deletion failed. Invalid SHD file %ws. "...
0x1800a85c7  mov     r9d, eax
0x1800a85ca  mov     rcx, r15; char *
0x1800a85cd  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x1800a85d2  mov     dword ptr [rbp+57h+var_58], 68h ; 'h'
0x1800a85d9  mov     [rbp+57h+var_50], r12
0x1800a85dd  mov     [rbp+57h+var_48], r14d
0x1800a85e1  call    cs:__imp_GetLastError
0x1800a85e7  mov     rdx, [rbx+50h]; unsigned __int16 *
0x1800a85eb  lea     rcx, [rbp+57h+var_40]; this
0x1800a85ef  mov     [rbp+57h+var_70], eax
0x1800a85f2  mov     [rbp+57h+var_68], r12
0x1800a85f6  mov     [rbp+57h+var_60], r14d
0x1800a85fa  mov     [rbp+57h+var_88], r14d
0x1800a85fe  mov     [rbp+57h+var_80], r12
0x1800a8602  mov     [rbp+57h+var_78], r14d
0x1800a8606  mov     [rbp+57h+var_A0], rsi
0x1800a860a  mov     [rbp+57h+var_98], r12
0x1800a860e  mov     [rbp+57h+var_90], 1
0x1800a8615  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x1800a861a  lea     rdx, [rbp+57h+var_58]
0x1800a861e  mov     [rsp+0E0h+hTemplateFile], r14
0x1800a8623  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rdx
0x1800a8628  lea     r9, [rbp+57h+var_88]
0x1800a862c  lea     rdx, [rbp+57h+var_70]
0x1800a8630  mov     qword ptr [rsp+0E0h+dwCreationDisposition], rdx
0x1800a8635  lea     r8, [rbp+57h+var_A0]
0x1800a8639  mov     rdx, rax; struct SplLogType *
0x1800a863c  lea     rcx, SPOOLER_DELETE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x1800a8643  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x1800a8648  mov     rcx, [rbx+50h]
0x1800a864c  call    cs:__imp_DllFreeSplMem
0x1800a8652  mov     rcx, rbx
0x1800a8655  call    cs:__imp_DllFreeSplMem
0x1800a865b  lea     r11, [rsp+0E0h+var_20]
0x1800a8663  mov     [rdi], r14
0x1800a8666  mov     rbx, [r11+38h]
0x1800a866a  mov     rsi, [r11+40h]
0x1800a866e  mov     rsp, r11
0x1800a8671  pop     r15
0x1800a8673  pop     r14
0x1800a8675  pop     r12
0x1800a8677  pop     rdi
0x1800a8678  pop     rbp
0x1800a8679  retn
```
