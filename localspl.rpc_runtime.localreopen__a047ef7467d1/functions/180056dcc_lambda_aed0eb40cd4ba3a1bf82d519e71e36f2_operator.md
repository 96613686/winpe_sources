# _lambda_aed0eb40cd4ba3a1bf82d519e71e36f2_::operator()

- ea: `0x180056dcc`
- end: `0x180057282`
- name: `_lambda_aed0eb40cd4ba3a1bf82d519e71e36f2_::operator()`
- size: `1206`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, loader_planting`

## callers

- `0x1800563ec`

## callees

- `0x180006830`
- `0x180008520`
- `0x180008560`
- `0x1800085ac`
- `0x180008730`
- `0x18000a07c`
- `0x18001fb10`
- `0x1800250ac`
- `0x18002a550`
- `0x1800381cc`
- `0x180038d84`
- `0x180038fec`
- `0x18003ea2c`
- `0x1800430b8`
- `0x180054638`
- `0x180056dcc`
- `0x180067140`
- `0x180068470`
- `0x1800ccbd8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056e72`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180056e72`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056e86`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180056e86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005713d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ea8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056ed5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180056fd2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057040`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005713d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056e9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057133`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056e9e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056ecb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180056f2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180057133`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056fb1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180056fb1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800570f1`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x1800570f1`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180057102`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x180057102`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180057120`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180057120`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180056f1d`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180056f1d`
- `SPOOLSS!DllFreeSplMem` at `0x180056f35`
- `SPOOLSS!DllFreeSplMem` at `0x180057098`
- `SPOOLSS!DllFreeSplMem` at `0x1800570a1`
- `SPOOLSS!DllFreeSplMem` at `0x180056f35`
- `SPOOLSS!DllFreeSplMem` at `0x180057098`
- `SPOOLSS!DllFreeSplMem` at `0x1800570a1`
- `SPOOLSS!ClosePrinter` at `0x180057165`
- `SPOOLSS!ClosePrinter` at `0x180057165`

## string_xrefs

- `0x180057270`: `printscan\print\spooler\localspl\openprn.c`
- `0x180056eae`: `Failed to close WaitForWrite handle.  Error %d`
- `0x180056edb`: `Failed to close WaitForRead handle.  Error %d`
- `0x18005704a`: `Failed to delete spool file '%ws' on handle close. Error %d`
- `0x180057202`: `Could not find pSpool %p in linked list.`

## pseudocode

```c
__int64 __fastcall lambda_aed0eb40cd4ba3a1bf82d519e71e36f2_::operator()(__int64 **a1)
{
  __int64 *v1; // rax
  __int64 v3; // rbx
  int v4; // eax
  __int64 v5; // rcx
  int v6; // edi
  const char *v7; // r9
  __int64 v8; // rsi
  __int64 v9; // rcx
  DWORD LastError; // eax
  __int64 v11; // rcx
  DWORD v12; // eax
  const void *v13; // rcx
  void *v14; // rcx
  _QWORD *v15; // rdi
  __int64 v16; // rcx
  __int64 v17; // r15
  __int64 v18; // rcx
  DWORD v19; // eax
  const unsigned __int16 *v20; // rdx
  struct SplLogType *v21; // rax
  DWORD v22; // eax
  __int64 v23; // rax
  __int64 *v24; // rdi
  void *v25; // rcx
  LARGE_INTEGER *v26; // rdx
  void *v27; // rcx
  DWORD v28; // eax
  DWORD v29; // eax
  void *v30; // rcx
  __int64 v31; // rcx
  __int64 *v32; // rcx
  int v33; // eax
  __int64 v34; // rax
  __int64 v35; // rax
  __int64 v36; // rcx
  int v38; // [rsp+40h] [rbp-69h] BYREF
  __int64 v39; // [rsp+48h] [rbp-61h]
  int v40; // [rsp+50h] [rbp-59h]
  DWORD v41; // [rsp+58h] [rbp-51h] BYREF
  __int64 v42; // [rsp+60h] [rbp-49h]
  int v43; // [rsp+68h] [rbp-41h]
  int v44; // [rsp+70h] [rbp-39h] BYREF
  __int64 v45; // [rsp+78h] [rbp-31h]
  int v46; // [rsp+80h] [rbp-29h]
  _QWORD v47[2]; // [rsp+88h] [rbp-21h] BYREF
  int v48; // [rsp+98h] [rbp-11h]
  _BYTE v49[96]; // [rsp+A0h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]
  int v51; // [rsp+110h] [rbp+67h] BYREF

  v1 = *a1;
  v51 = 0;
  v3 = *v1;
  EnterSplSem(0);
  *(_DWORD *)(v3 + 112) &= ~0x80u;
  if ( (*(_DWORD *)(v3 + 88) & 0x100) != 0 )
    v4 = ValidateXcvHandle(*(_QWORD *)(v3 + 176));
  else
    v4 = ValidateSpoolHandle(v3, 0);
  v6 = v4;
  LeaveSplSem(v5);
  if ( !v6 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x8DC,
      (unsigned int)"printscan\\print\\spooler\\localspl\\openprn.c",
      v7);
  v8 = 0;
  if ( (*(_BYTE *)(v3 + 112) & 1) != 0 )
    SplEndDocPrinter(**a1);
  if ( (*(_BYTE *)(v3 + 88) & 0xA) == 0xA )
  {
    v9 = *(_QWORD *)(v3 + 80);
    if ( *(_DWORD *)(v9 + 208) )
    {
      SetEvent(*(HANDLE *)(v9 + 216));
      WaitForSingleObject(*(HANDLE *)(*(_QWORD *)(v3 + 80) + 224LL), 0xFFFFFFFF);
      EnterSplSem(0);
      if ( !CloseHandle(*(HANDLE *)(*(_QWORD *)(v3 + 80) + 224LL)) )
      {
        LastError = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "SplClosePrinter::<lambda_aed0eb40cd4ba3a1bf82d519e71e36f2>::operator ()",
          L"Failed to close WaitForWrite handle.  Error %d",
          LastError);
      }
      if ( !CloseHandle(*(HANDLE *)(*(_QWORD *)(v3 + 80) + 216LL)) )
      {
        v12 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "SplClosePrinter::<lambda_aed0eb40cd4ba3a1bf82d519e71e36f2>::operator ()",
          L"Failed to close WaitForRead handle.  Error %d",
          v12);
      }
      *(_QWORD *)(*(_QWORD *)(v3 + 80) + 216LL) = 0;
      *(_QWORD *)(*(_QWORD *)(v3 + 80) + 224LL) = 0;
      LeaveSplSem(v11);
    }
  }
  while ( 1 )
  {
    v15 = *(_QWORD **)(v3 + 264);
    if ( !v15 )
      break;
    *(_QWORD *)(v3 + 264) = *v15;
    v13 = (const void *)v15[2];
    if ( v13 )
      UnmapViewOfFile(v13);
    v14 = (void *)v15[1];
    if ( v14 )
      CloseHandle(v14);
    DllFreeSplMem(v15);
  }
  EnterSplSem(0);
  *(_DWORD *)(v3 + 160) |= 0x10u;
  while ( 1 )
  {
    v24 = *(__int64 **)(v3 + 272);
    if ( !v24 )
      break;
    v17 = *v24;
    if ( (*(_BYTE *)(v3 + 88) & 2) == 0 && (*((_BYTE *)v24 + 20) & 2) != 0 )
    {
      LeaveSplSem(v16);
      SplScheduleJob(**a1, *((unsigned int *)v24 + 4));
      EnterSplSem(0);
    }
    v18 = *(_QWORD *)(v3 + 64);
    *(_QWORD *)(v3 + 272) = v17;
    if ( !v18 || !FindJob(v18, *((unsigned int *)v24 + 4), &v51) )
    {
      LeaveSplSem(v18);
      if ( !DeleteFileW((LPCWSTR)v24[1]) )
      {
        v38 = 104;
        v39 = 4;
        v40 = 0;
        v19 = GetLastError();
        v20 = (const unsigned __int16 *)v24[1];
        v41 = v19;
        v47[0] = L"-";
        v42 = 4;
        v43 = 0;
        v44 = 0;
        v45 = 4;
        v46 = 0;
        v47[1] = 4;
        v48 = 1;
        v21 = SplLogType::SplLogType((SplLogType *)v49, v20);
        SplLogEvent2(&SPOOLER_DELETE_FILE_FAILED, v21, v47, &v44, &v41, &v38, 0);
        v22 = GetLastError();
        LocalSpoolerTelemetry::WriteDbgTraceError(
          "SplClosePrinter::<lambda_aed0eb40cd4ba3a1bf82d519e71e36f2>::operator ()",
          L"Failed to delete spool file '%ws' on handle close. Error %d",
          v24[1],
          v22);
      }
      EnterSplSem(0);
      v23 = *(_QWORD *)(v3 + 64);
      if ( v23 )
        *(_DWORD *)(**(_QWORD **)(*(_QWORD *)(v23 + 280) + 264LL)
                  + 4 * ((unsigned __int64)*((unsigned int *)v24 + 4) >> 5)) &= ~(1 << *((_DWORD *)v24 + 4));
    }
    DllFreeSplMem(v24[1]);
    DllFreeSplMem(v24);
  }
  LeaveSplSem(v16);
  v25 = *(void **)(v3 + 216);
  if ( v25 != (void *)-1LL )
  {
    v26 = *(LARGE_INTEGER **)(v3 + 80);
    if ( (v26[4].LowPart & 0x8000000) != 0 && v26[23].QuadPart == -1 && SetFilePointerEx(v25, v26[41], 0, 0) )
      SetEndOfFile(*(HANDLE *)(v3 + 216));
    v27 = *(void **)(v3 + 216);
    if ( *(_BYTE *)(v3 + 328) )
    {
      v28 = SetFilePointer(v27, 0, 0, 0);
      if ( v28 )
        LocalSpoolerTelemetry::WriteDbgTraceWarning(
          "SplClosePrinter::<lambda_aed0eb40cd4ba3a1bf82d519e71e36f2>::operator ()",
          L"Failed to set file pointer for %p.  Error %d",
          *(_QWORD *)(v3 + 216),
          v28);
    }
    else if ( !CloseHandle(v27) )
    {
      v29 = GetLastError();
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplClosePrinter::<lambda_aed0eb40cd4ba3a1bf82d519e71e36f2>::operator ()",
        L"Failed to close file handle %p.  Error %d",
        *(_QWORD *)(v3 + 216),
        v29);
    }
  }
  v30 = *(void **)(v3 + 104);
  if ( v30 )
    ClosePrinter(v30);
  EnterSplSem(0);
  if ( (*(_BYTE *)(v3 + 88) & 6) != 0 )
  {
    v31 = *(_QWORD *)(v3 + 80);
    if ( v31 )
    {
      SafeDecrementReference((unsigned int *)(v31 + 24));
      DeleteJobCheck(*(_QWORD *)(v3 + 80));
    }
  }
  if ( (*(_BYTE *)(v3 + 88) & 1) != 0 )
  {
    v32 = (__int64 *)(*(_QWORD *)(v3 + 64) + 200LL);
  }
  else
  {
    v33 = *(_DWORD *)(v3 + 88) & 0x100;
    if ( (*(_BYTE *)(v3 + 88) & 0x10) == 0 && !v33 )
      goto LABEL_61;
    if ( v33 )
      XcvClose(*(_QWORD *)(v3 + 176));
    v8 = *(_QWORD *)(v3 + 168);
    v32 = (__int64 *)(v8 + 88);
  }
  if ( v32 )
  {
    v34 = *v32;
    if ( !*v32 )
      goto LABEL_60;
    do
    {
      if ( v34 == v3 )
        break;
      v32 = (__int64 *)(v34 + 8);
      v34 = *(_QWORD *)(v34 + 8);
    }
    while ( v34 );
    if ( *v32 )
      *v32 = *(_QWORD *)(v3 + 8);
    else
LABEL_60:
      LocalSpoolerTelemetry::WriteDbgTraceWarning(
        "SplClosePrinter::<lambda_aed0eb40cd4ba3a1bf82d519e71e36f2>::operator ()",
        L"Could not find pSpool %p in linked list.",
        v3);
  }
LABEL_61:
  v35 = *(_QWORD *)(v3 + 64);
  if ( v35 )
  {
    if ( *(_DWORD *)(v35 + 16) )
      SafeDecrementReference((unsigned int *)(v35 + 16));
    DeletePrinterCheck(*(_INIPRINTER **)(v3 + 64));
  }
  DeletePrinterHandle((struct _SPOOL *)v3);
  if ( v8 )
  {
    if ( *(_DWORD *)(v8 + 16) )
      SafeDecrementReference((unsigned int *)(v8 + 16));
    DeleteSpoolerCheck(v8);
  }
  return LeaveSplSem(v36);
}

```

## disassembly

```asm
0x180056dcc  push    rbp
0x180056dce  push    rbx
0x180056dcf  push    rsi
0x180056dd0  push    rdi
0x180056dd1  push    r12
0x180056dd3  push    r13
0x180056dd5  push    r14
0x180056dd7  push    r15
0x180056dd9  lea     rbp, [rsp-1Fh]
0x180056dde  sub     rsp, 0C8h
0x180056de5  mov     rax, [rcx]
0x180056de8  mov     r14, rcx
0x180056deb  xor     r12d, r12d
0x180056dee  xor     ecx, ecx
0x180056df0  mov     [rbp+57h+arg_0], r12d
0x180056df4  mov     rbx, [rax]
0x180056df7  call    EnterSplSem
0x180056dfc  btr     dword ptr [rbx+70h], 7
0x180056e01  test    dword ptr [rbx+58h], 100h
0x180056e08  jz      short loc_180056E18
0x180056e0a  mov     rcx, [rbx+0B0h]
0x180056e11  call    ValidateXcvHandle
0x180056e16  jmp     short loc_180056E22
0x180056e18  xor     edx, edx
0x180056e1a  mov     rcx, rbx
0x180056e1d  call    ValidateSpoolHandle
0x180056e22  mov     edi, eax
0x180056e24  call    LeaveSplSem
0x180056e29  test    edi, edi
0x180056e2b  jz      loc_18005726C
0x180056e31  test    byte ptr [rbx+70h], 1
0x180056e35  mov     rsi, r12
0x180056e38  jz      short loc_180056E45
0x180056e3a  mov     rcx, [r14]
0x180056e3d  mov     rcx, [rcx]
0x180056e40  call    SplEndDocPrinter
0x180056e45  mov     eax, [rbx+58h]
0x180056e48  lea     r13, aSplcloseprinte_1; "SplClosePrinter::<lambda_aed0eb40cd4ba3"...
0x180056e4f  and     eax, 0Ah
0x180056e52  cmp     al, 0Ah
0x180056e54  jnz     loc_180056F3B
0x180056e5a  mov     rcx, [rbx+50h]
0x180056e5e  cmp     [rcx+0D0h], r12d
0x180056e65  jz      loc_180056F3B
0x180056e6b  mov     rcx, [rcx+0D8h]; hEvent
0x180056e72  call    cs:__imp_SetEvent
0x180056e78  mov     rcx, [rbx+50h]
0x180056e7c  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180056e7f  mov     rcx, [rcx+0E0h]; hHandle
0x180056e86  call    cs:__imp_WaitForSingleObject
0x180056e8c  xor     ecx, ecx
0x180056e8e  call    EnterSplSem
0x180056e93  mov     rcx, [rbx+50h]
0x180056e97  mov     rcx, [rcx+0E0h]; hObject
0x180056e9e  call    cs:__imp_CloseHandle
0x180056ea4  test    eax, eax
0x180056ea6  jnz     short loc_180056EC0
0x180056ea8  call    cs:__imp_GetLastError
0x180056eae  lea     rdx, aFailedToCloseW_0; "Failed to close WaitForWrite handle.  E"...
0x180056eb5  mov     rcx, r13; char *
0x180056eb8  mov     r8d, eax
0x180056ebb  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180056ec0  mov     rcx, [rbx+50h]
0x180056ec4  mov     rcx, [rcx+0D8h]; hObject
0x180056ecb  call    cs:__imp_CloseHandle
0x180056ed1  test    eax, eax
0x180056ed3  jnz     short loc_180056EED
0x180056ed5  call    cs:__imp_GetLastError
0x180056edb  lea     rdx, aFailedToCloseW; "Failed to close WaitForRead handle.  Er"...
0x180056ee2  mov     rcx, r13; char *
0x180056ee5  mov     r8d, eax
0x180056ee8  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180056eed  mov     rax, [rbx+50h]
0x180056ef1  mov     [rax+0D8h], r12
0x180056ef8  mov     rax, [rbx+50h]
0x180056efc  mov     [rax+0E0h], r12
0x180056f03  call    LeaveSplSem
0x180056f08  jmp     short loc_180056F3B
0x180056f0a  mov     rax, [rdi]
0x180056f0d  mov     [rbx+108h], rax
0x180056f14  mov     rcx, [rdi+10h]; lpBaseAddress
0x180056f18  test    rcx, rcx
0x180056f1b  jz      short loc_180056F23
0x180056f1d  call    cs:__imp_UnmapViewOfFile
0x180056f23  mov     rcx, [rdi+8]; hObject
0x180056f27  test    rcx, rcx
0x180056f2a  jz      short loc_180056F32
0x180056f2c  call    cs:__imp_CloseHandle
0x180056f32  mov     rcx, rdi
0x180056f35  call    cs:__imp_DllFreeSplMem
0x180056f3b  mov     rdi, [rbx+108h]
0x180056f42  test    rdi, rdi
0x180056f45  jnz     short loc_180056F0A
0x180056f47  xor     ecx, ecx
0x180056f49  call    EnterSplSem
0x180056f4e  or      dword ptr [rbx+0A0h], 10h
0x180056f55  jmp     loc_1800570A7
0x180056f5a  test    byte ptr [rbx+58h], 2
0x180056f5e  mov     r15, [rdi]
0x180056f61  jnz     short loc_180056F83
0x180056f63  test    byte ptr [rdi+14h], 2
0x180056f67  jz      short loc_180056F83
0x180056f69  call    LeaveSplSem
0x180056f6e  mov     rcx, [r14]
0x180056f71  mov     edx, [rdi+10h]
0x180056f74  mov     rcx, [rcx]
0x180056f77  call    SplScheduleJob
0x180056f7c  xor     ecx, ecx
0x180056f7e  call    EnterSplSem
0x180056f83  mov     rcx, [rbx+40h]
0x180056f87  mov     [rbx+110h], r15
0x180056f8e  test    rcx, rcx
0x180056f91  jz      short loc_180056FA8
0x180056f93  mov     edx, [rdi+10h]
0x180056f96  lea     r8, [rbp+57h+arg_0]
0x180056f9a  call    FindJob
0x180056f9f  test    rax, rax
0x180056fa2  jnz     loc_180057094
0x180056fa8  call    LeaveSplSem
0x180056fad  mov     rcx, [rdi+8]; lpFileName
0x180056fb1  call    cs:__imp_DeleteFileW
0x180056fb7  test    eax, eax
0x180056fb9  jnz     loc_18005705C
0x180056fbf  lea     r15d, [rax+4]
0x180056fc3  mov     [rbp+57h+var_C0], 68h ; 'h'
0x180056fca  mov     [rbp+57h+var_B8], r15
0x180056fce  mov     [rbp+57h+var_B0], r12d
0x180056fd2  call    cs:__imp_GetLastError
0x180056fd8  mov     rdx, [rdi+8]; unsigned __int16 *
0x180056fdc  lea     rcx, [rbp+57h+var_60]; this
0x180056fe0  mov     [rbp+57h+var_A8], eax
0x180056fe3  lea     rax, asc_1800ECF90; "-"
0x180056fea  mov     [rbp+57h+var_78], rax
0x180056fee  mov     [rbp+57h+var_A0], r15
0x180056ff2  mov     [rbp+57h+var_98], r12d
0x180056ff6  mov     [rbp+57h+var_90], r12d
0x180056ffa  mov     [rbp+57h+var_88], r15
0x180056ffe  mov     [rbp+57h+var_80], r12d
0x180057002  mov     [rbp+57h+var_70], r15
0x180057006  mov     [rbp+57h+var_68], 1
0x18005700d  call    ??0SplLogType@@QEAA@PEBG@Z; SplLogType::SplLogType(ushort const *)
0x180057012  lea     rcx, [rbp+57h+var_C0]
0x180057016  mov     [rsp+100h+var_D0], r12
0x18005701b  mov     [rsp+100h+var_D8], rcx
0x180057020  lea     r9, [rbp+57h+var_90]
0x180057024  lea     rcx, [rbp+57h+var_A8]
0x180057028  mov     rdx, rax; struct SplLogType *
0x18005702b  mov     [rsp+100h+var_E0], rcx
0x180057030  lea     r8, [rbp+57h+var_78]
0x180057034  lea     rcx, SPOOLER_DELETE_FILE_FAILED; struct _EVENT_DESCRIPTOR *
0x18005703b  call    ?SplLogEvent2@@YAXPEBU_EVENT_DESCRIPTOR@@PEAVSplLogType@@ZZ; SplLogEvent2(_EVENT_DESCRIPTOR const *,SplLogType *,...)
0x180057040  call    cs:__imp_GetLastError
0x180057046  mov     r8, [rdi+8]
0x18005704a  lea     rdx, aFailedToDelete_5; "Failed to delete spool file '%ws' on ha"...
0x180057051  mov     r9d, eax
0x180057054  mov     rcx, r13; char *
0x180057057  call    ?WriteDbgTraceError@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x18005705c  xor     ecx, ecx
0x18005705e  call    EnterSplSem
0x180057063  mov     rax, [rbx+40h]
0x180057067  test    rax, rax
0x18005706a  jz      short loc_180057094
0x18005706c  mov     rax, [rax+118h]
0x180057073  mov     ecx, [rdi+10h]
0x180057076  mov     r9d, ecx
0x180057079  shr     r9, 5
0x18005707d  mov     rdx, [rax+108h]
0x180057084  mov     eax, 1
0x180057089  shl     eax, cl
0x18005708b  not     eax
0x18005708d  mov     r8, [rdx]
0x180057090  and     [r8+r9*4], eax
0x180057094  mov     rcx, [rdi+8]
0x180057098  call    cs:__imp_DllFreeSplMem
0x18005709e  mov     rcx, rdi
0x1800570a1  call    cs:__imp_DllFreeSplMem
0x1800570a7  mov     rdi, [rbx+110h]
0x1800570ae  test    rdi, rdi
0x1800570b1  jnz     loc_180056F5A
0x1800570b7  call    LeaveSplSem
0x1800570bc  mov     rcx, [rbx+0D8h]; hFile
0x1800570c3  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800570c7  jz      loc_18005715C
0x1800570cd  mov     rdx, [rbx+50h]
0x1800570d1  test    dword ptr [rdx+20h], 8000000h
0x1800570d8  jz      short loc_180057108
0x1800570da  cmp     qword ptr [rdx+0B8h], 0FFFFFFFFFFFFFFFFh
0x1800570e2  jnz     short loc_180057108
0x1800570e4  mov     rdx, [rdx+148h]; liDistanceToMove
0x1800570eb  xor     r9d, r9d; dwMoveMethod
0x1800570ee  xor     r8d, r8d; lpNewFilePointer
0x1800570f1  call    cs:__imp_SetFilePointerEx
0x1800570f7  test    eax, eax
0x1800570f9  jz      short loc_180057108
0x1800570fb  mov     rcx, [rbx+0D8h]; hFile
0x180057102  call    cs:__imp_SetEndOfFile
0x180057108  mov     rcx, [rbx+0D8h]; hObject
0x18005710f  cmp     [rbx+148h], r12b
0x180057116  jz      short loc_180057133
0x180057118  xor     r9d, r9d; dwMoveMethod
0x18005711b  xor     r8d, r8d; lpDistanceToMoveHigh
0x18005711e  xor     edx, edx; lDistanceToMove
0x180057120  call    cs:__imp_SetFilePointer
0x180057126  test    eax, eax
0x180057128  jz      short loc_18005715C
0x18005712a  lea     rdx, aFailedToSetFil_0; "Failed to set file pointer for %p.  Err"...
0x180057131  jmp     short loc_18005714A
0x180057133  call    cs:__imp_CloseHandle
0x180057139  test    eax, eax
0x18005713b  jnz     short loc_18005715C
0x18005713d  call    cs:__imp_GetLastError
0x180057143  lea     rdx, aFailedToCloseF; "Failed to close file handle %p.  Error "...
0x18005714a  mov     r8, [rbx+0D8h]
0x180057151  mov     r9d, eax
0x180057154  mov     rcx, r13; char *
0x180057157  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x18005715c  mov     rcx, [rbx+68h]; hPrinter
0x180057160  test    rcx, rcx
0x180057163  jz      short loc_18005716B
0x180057165  call    cs:__imp_ClosePrinter
0x18005716b  xor     ecx, ecx
0x18005716d  call    EnterSplSem
0x180057172  test    byte ptr [rbx+58h], 6
0x180057176  jz      short loc_180057193
0x180057178  mov     rcx, [rbx+50h]
0x18005717c  test    rcx, rcx
0x18005717f  jz      short loc_180057193
0x180057181  add     rcx, 18h; unsigned int *
0x180057185  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18005718a  mov     rcx, [rbx+50h]
0x18005718e  call    DeleteJobCheck
0x180057193  test    byte ptr [rbx+58h], 1
0x180057197  jz      short loc_1800571A6
0x180057199  mov     rcx, [rbx+40h]
0x18005719d  add     rcx, 0C8h
0x1800571a4  jmp     short loc_1800571D3
0x1800571a6  mov     eax, [rbx+58h]
0x1800571a9  and     eax, 100h
0x1800571ae  test    byte ptr [rbx+58h], 10h
0x1800571b2  jnz     short loc_1800571B8
0x1800571b4  test    eax, eax
0x1800571b6  jz      short loc_180057211
0x1800571b8  test    eax, eax
0x1800571ba  jz      short loc_1800571C8
0x1800571bc  mov     rcx, [rbx+0B0h]
0x1800571c3  call    XcvClose
0x1800571c8  mov     rsi, [rbx+0A8h]
0x1800571cf  lea     rcx, [rsi+58h]
0x1800571d3  test    rcx, rcx
0x1800571d6  jz      short loc_180057211
0x1800571d8  mov     rax, [rcx]
0x1800571db  test    rax, rax
0x1800571de  jz      short loc_1800571FF
0x1800571e0  cmp     rax, rbx
0x1800571e3  jz      short loc_1800571F1
0x1800571e5  lea     rcx, [rax+8]
0x1800571e9  mov     rax, [rcx]
0x1800571ec  test    rax, rax
0x1800571ef  jnz     short loc_1800571E0
0x1800571f1  cmp     [rcx], r12
0x1800571f4  jz      short loc_1800571FF
0x1800571f6  mov     rax, [rbx+8]
0x1800571fa  mov     [rcx], rax
0x1800571fd  jmp     short loc_180057211
0x1800571ff  mov     r8, rbx
0x180057202  lea     rdx, aCouldNotFindPs; "Could not find pSpool %p in linked list"...
0x180057209  mov     rcx, r13; char *
0x18005720c  call    ?WriteDbgTraceWarning@LocalSpoolerTelemetry@@SAXPEADPEAGZZ; LocalSpoolerTelemetry::WriteDbgTraceWarning(char *,ushort *,...)
0x180057211  mov     rax, [rbx+40h]
0x180057215  test    rax, rax
0x180057218  jz      short loc_180057231
0x18005721a  lea     rcx, [rax+10h]; unsigned int *
0x18005721e  cmp     [rcx], r12d
0x180057221  jz      short loc_180057228
0x180057223  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x180057228  mov     rcx, [rbx+40h]; this
0x18005722c  call    DeletePrinterCheck
0x180057231  mov     rcx, rbx; struct _SPOOL *
0x180057234  call    ?DeletePrinterHandle@@YAHPEAU_SPOOL@@@Z; DeletePrinterHandle(_SPOOL *)
0x180057239  test    rsi, rsi
0x18005723c  jz      short loc_180057254
0x18005723e  lea     rcx, [rsi+10h]; unsigned int *
0x180057242  cmp     [rcx], r12d
0x180057245  jz      short loc_18005724C
0x180057247  call    ?SafeDecrementReference@@YAKPEAK@Z; SafeDecrementReference(ulong *)
0x18005724c  mov     rcx, rsi
0x18005724f  call    DeleteSpoolerCheck
0x180057254  add     rsp, 0C8h
0x18005725b  pop     r15
0x18005725d  pop     r14
0x18005725f  pop     r13
0x180057261  pop     r12
0x180057263  pop     rdi
0x180057264  pop     rsi
0x180057265  pop     rbx
0x180057266  pop     rbp
0x180057267  jmp     LeaveSplSem
0x18005726c  mov     rcx, [rbp+5Fh]; this
0x180057270  lea     r8, aPrintscanPrint_18; "printscan\\print\\spooler\\localspl\\op"...
0x180057277  mov     edx, 8DCh; void *
  ... truncated ...
```
