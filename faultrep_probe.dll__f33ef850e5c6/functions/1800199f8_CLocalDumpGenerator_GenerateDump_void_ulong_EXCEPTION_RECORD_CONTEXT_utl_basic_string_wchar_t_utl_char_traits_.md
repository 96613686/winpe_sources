# CLocalDumpGenerator::GenerateDump(void *,ulong,_EXCEPTION_RECORD *,_CONTEXT *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)

- ea: `0x1800199f8`
- end: `0x18001a39e`
- name: `?GenerateDump@CLocalDumpGenerator@@QEAAJPEAXKPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `2470`
- prototype: ``
- caller_count: `4`
- callee_count: `18`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000ff8c`
- `0x1800143a8`
- `0x1800144d4`
- `0x18001611c`

## callees

- `0x18000113c`
- `0x180001758`
- `0x180002890`
- `0x180003474`
- `0x180009ed8`
- `0x180009f00`
- `0x180009f40`
- `0x1800196bc`
- `0x1800199f8`
- `0x18001ace4`
- `0x18001b08c`
- `0x18003bd80`
- `0x18003cc4c`
- `0x18003d194`
- `0x18003de94`
- `0x18003dfd4`
- `0x18003e5a8`
- `0x18004b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180019d3c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x180019d3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019c67`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019d55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ee1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a1db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a375`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a360`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001a375`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019c51`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180019c51`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001a1bf`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x18001a1bf`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x180019afc`
- `api-ms-win-core-debug-l1-1-1!CheckRemoteDebuggerPresent` at `0x180019afc`
- `dbghelp!MiniDumpWriteDump` at `0x180019ed4`
- `dbghelp!MiniDumpWriteDump` at `0x180019ed4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CLocalDumpGenerator::GenerateDump(__int64 a1, void *a2, DWORD a3, void *a4, __int64 a5)
{
  struct _SECURITY_ATTRIBUTES *v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r8
  HANDLE v10; // r13
  int v11; // eax
  __int64 v12; // r12
  void *v13; // r9
  int TempFile; // edi
  _QWORD *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // r9
  char *FileW; // rcx
  signed int LastError; // eax
  int v20; // eax
  DWORD ProcessId; // r12d
  signed int v22; // eax
  bool v23; // sf
  int UniqueDumpFile; // eax
  int v25; // ecx
  int v26; // ecx
  int v27; // ecx
  MINIDUMP_TYPE v28; // ebx
  struct _MINIDUMP_EXCEPTION_INFORMATION *p_ExceptionParam; // rax
  HANDLE v30; // r8
  int v31; // r9d
  BOOL v32; // r12d
  _BYTE *v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r9
  __int64 v36; // rbx
  int v37; // eax
  HANDLE v38; // rbx
  signed int v39; // eax
  _WORD *v40; // rax
  _WORD *v41; // rdx
  __int64 v42; // rcx
  int v43; // ecx
  int v44; // eax
  unsigned int v45; // edx
  __int64 dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  DWORD v48; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v49; // [rsp+58h] [rbp-A8h] BYREF
  WINBOOL pbDebuggerPresent; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE v51; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-90h]
  void *v53; // [rsp+78h] [rbp-88h] BYREF
  HANDLE hProcess; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h]
  __int128 v56; // [rsp+90h] [rbp-70h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-60h] BYREF
  _MINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v59; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v60; // [rsp+C8h] [rbp-38h] BYREF
  _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v62; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v63[4]; // [rsp+100h] [rbp+0h] BYREF
  __int64 v64; // [rsp+120h] [rbp+20h]
  char v65[32]; // [rsp+150h] [rbp+50h] BYREF
  __int128 *v66; // [rsp+170h] [rbp+70h]
  __int64 v67; // [rsp+178h] [rbp+78h]
  __int64 *v68; // [rsp+180h] [rbp+80h]
  __int64 v69; // [rsp+188h] [rbp+88h]
  _WORD *v70; // [rsp+190h] [rbp+90h]
  int v71; // [rsp+198h] [rbp+98h]
  int v72; // [rsp+19Ch] [rbp+9Ch]
  _WORD *v73; // [rsp+1A0h] [rbp+A0h]
  int v74; // [rsp+1A8h] [rbp+A8h]
  int v75; // [rsp+1ACh] [rbp+ACh]
  WCHAR FileName[264]; // [rsp+1B0h] [rbp+B0h] BYREF

  v53 = a4;
  v48 = a3;
  hProcess = a2;
  v49 = a5;
  pbDebuggerPresent = 0;
  memset_0(v63, 0, 0x50u);
  hObject = 0;
  v62 = 0;
  v57 = 0;
  v10 = 0;
  v51 = 0;
  v60 = 0;
  ExceptionParam = 0;
  CallbackParam = 0;
  if ( !a2 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v8);
  v11 = *(_DWORD *)(a1 + 656);
  v12 = -1;
  v13 = &unk_18004FE4C;
  if ( (v11 & 2) != 0 )
  {
    TempFile = 1;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids);
LABEL_135:
    if ( (unsigned int)dword_180062070 > 5 )
    {
      v40 = *(_WORD **)(a1 + 624);
      v41 = *(_WORD **)(a1 + 8);
      LODWORD(v49) = TempFile;
      *(_QWORD *)&v56 = 0x1000000;
      if ( v40 )
      {
        v42 = -1;
        do
          ++v42;
        while ( v40[v42] );
        v43 = 2 * v42 + 2;
      }
      else
      {
        v40 = &unk_18004FE4C;
        v43 = 2;
      }
      v73 = v40;
      v74 = v43;
      v75 = 0;
      if ( v41 )
      {
        do
          ++v12;
        while ( v41[v12] );
        v44 = 2 * v12 + 2;
      }
      else
      {
        v41 = &unk_18004FE4C;
        v44 = 2;
      }
      v70 = v41;
      v71 = v44;
      v72 = 0;
      v68 = &v49;
      v69 = 4;
      v66 = &v56;
      v67 = 8;
      tlgWriteTransfer_EventWriteTransfer(&dword_180062070, &unk_180057CDA, 0, 0, 6, v65);
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_DSS(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)v7,
        v9,
        TempFile,
        *(_QWORD *)(a1 + 8),
        *(_QWORD *)(a1 + 624));
    goto LABEL_149;
  }
  if ( (v11 & 1) == 0 )
  {
    TempFile = -2147019873;
    goto LABEL_149;
  }
  if ( !*(_DWORD *)(a1 + 92) || !CheckRemoteDebuggerPresent(a2, &pbDebuggerPresent) || !pbDebuggerPresent )
  {
    hFile = (HANDLE)-1LL;
    if ( (*(_BYTE *)(a1 + 656) & 4) != 0 )
    {
      if ( *(_QWORD *)(a1 + 640) )
      {
        TempFile = MmsCreate(v63, v7, v9, v13);
        if ( TempFile < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 22;
LABEL_21:
            v17 = (unsigned int)TempFile;
LABEL_22:
            WPP_SF_d(v15[2], v16, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids, v17);
            goto LABEL_62;
          }
          goto LABEL_62;
        }
        hFile = v63;
        *((_QWORD *)&v57 + 1) = v63;
      }
      else
      {
        if ( !*(_QWORD *)(a1 + 648) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v8);
        TempFile = UtilGetTempFile(0, 0, (__int64)L".dmp", FileName, dwCreationDisposition, 0, 0, 0);
        if ( TempFile < 0 )
        {
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 23;
            goto LABEL_21;
          }
LABEL_62:
          if ( TempFile == -2147019873 )
            goto LABEL_149;
          goto LABEL_135;
        }
        FileW = (char *)CreateFileW(FileName, 0xC0010000, 0, 0, 2u, 0x4000100u, 0);
        hObject = FileW;
        if ( FileW == (char *)-1LL || FileW + 1 == (char *)1 )
        {
          LastError = GetLastError();
          TempFile = LastError;
          if ( LastError > 0 )
            TempFile = (unsigned __int16)LastError | 0x80070000;
          if ( TempFile >= 0 )
            TempFile = -2147467259;
          v15 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            v16 = 24;
            goto LABEL_21;
          }
          goto LABEL_62;
        }
        *((_QWORD *)&v57 + 1) = 0;
        hFile = FileW;
      }
    }
    v20 = UtilEnsureDirectory(*(const wchar_t **)(a1 + 48), v7);
    TempFile = v20;
    if ( v20 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_62;
      v16 = 25;
      goto LABEL_43;
    }
    v20 = UtilPruneFolder(*(const wchar_t **)(a1 + 48), (const wchar_t *)v7, *(_DWORD *)(a1 + 80) - 1);
    TempFile = v20;
    if ( v20 < 0 )
    {
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_62;
      v16 = 26;
      goto LABEL_43;
    }
    ProcessId = GetProcessId(a2);
    if ( !ProcessId )
    {
      v22 = GetLastError();
      v23 = v22 < 0;
      if ( v22 > 0 )
      {
        v22 = (unsigned __int16)v22 | 0x80070000;
        v23 = v22 < 0;
      }
      if ( !v23 )
        v22 = -2147467259;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          27,
          &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
          (unsigned int)v22);
    }
    UniqueDumpFile = CLocalDumpGenerator::CreateUniqueDumpFile(
                       *(_QWORD *)(a1 + 48),
                       *(_QWORD *)(a1 + 624),
                       ProcessId,
                       (*(_DWORD *)(a1 + 656) >> 2) & 1,
                       (__int64)&v51,
                       a1 + 8);
    TempFile = UniqueDumpFile;
    if ( UniqueDumpFile < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          28,
          &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
          (unsigned int)UniqueDumpFile);
      v10 = v51;
      goto LABEL_61;
    }
    if ( v53 && v49 )
    {
      *(_QWORD *)&v60 = v53;
      *((_QWORD *)&v60 + 1) = v49;
      ExceptionParam.ThreadId = v48;
      ExceptionParam.ExceptionPointers = (PEXCEPTION_POINTERS)&v60;
      ExceptionParam.ClientPointers = 0;
    }
    *(_QWORD *)&v57 = a1;
    CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CLocalDumpGenerator::static_MiniDumpCallback;
    CallbackParam.CallbackParam = &v57;
    v25 = *(_DWORD *)(a1 + 84);
    if ( v25 )
    {
      v26 = v25 - 1;
      if ( v26 )
      {
        if ( v26 == 1 )
          v27 = 6182;
        else
          v27 = 0;
      }
      else
      {
        v27 = 289;
      }
    }
    else
    {
      v27 = *(_DWORD *)(a1 + 88);
    }
    v28 = v27 | 0x20000;
    TempFile = 0;
    if ( (v27 & 2) == 0 )
      v28 = v27;
    if ( !v53 || (p_ExceptionParam = &ExceptionParam, !v49) )
      p_ExceptionParam = 0;
    v10 = v51;
    v30 = v51;
    if ( (*(_BYTE *)(a1 + 656) & 4) != 0 )
      v30 = hFile;
    v32 = MiniDumpWriteDump(hProcess, ProcessId, v30, v28, p_ExceptionParam, 0, &CallbackParam);
    if ( !v32 )
      TempFile = GetLastError();
    if ( (unsigned int)dword_180062070 > 5 )
    {
      LODWORD(v7) = 0;
      if ( (qword_180062080 & 0x400000000000LL) != 0 && (qword_180062088 & 0x400000000000LL) == qword_180062088 )
      {
        hProcess = *(HANDLE *)(a1 + 8);
        v48 = v28;
        v53 = &unk_18004FE4C;
        v59 = L"LocalDumpGenerator";
        LODWORD(v49) = TempFile;
        *(_QWORD *)&v56 = 0x1000000;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
          (unsigned int)&dword_180062070,
          (unsigned int)&unk_180057D2D,
          v9,
          v31,
          (__int64)&v56,
          (__int64)&v49,
          (__int64)&v59,
          (__int64)&v53,
          (__int64)&v48,
          (__int64)&hProcess);
      }
    }
    v33 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
        (unsigned int)TempFile,
        v28);
      v33 = WPP_GLOBAL_Control;
    }
    if ( !v32 )
    {
      if ( TempFile >= 0 )
        TempFile = -2147467259;
      goto LABEL_94;
    }
    if ( TempFile < 0 )
    {
LABEL_94:
      if ( v33 == (_BYTE *)&WPP_GLOBAL_Control || (v33[28] & 1) == 0 )
        goto LABEL_61;
      v34 = 30;
      v35 = (unsigned int)TempFile;
LABEL_97:
      WPP_SF_d(*((_QWORD *)v33 + 2), v34, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids, v35);
LABEL_61:
      v12 = -1;
      goto LABEL_62;
    }
    if ( (*(_BYTE *)(a1 + 656) & 4) != 0 )
    {
      if ( !*(_QWORD *)(a1 + 640) )
      {
        if ( !*(_QWORD *)(a1 + 648) )
        {
          MicrosoftTelemetryAssertTriggeredNoArgs(v33);
          v33 = WPP_GLOBAL_Control;
        }
        if ( !*(_QWORD *)(a1 + 640) )
        {
          v38 = hFile;
          v12 = -1;
          if ( hFile == (HANDLE)-1LL )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v33);
            v33 = WPP_GLOBAL_Control;
          }
          if ( !*(_QWORD *)(a1 + 648) )
          {
            MicrosoftTelemetryAssertTriggeredNoArgs(v33);
            v33 = WPP_GLOBAL_Control;
          }
          if ( v33 != (_BYTE *)&WPP_GLOBAL_Control && (v33[28] & 4) != 0 )
            WPP_SF_(*((_QWORD *)v33 + 2), 36, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids);
          v20 = (*(__int64 (__fastcall **)(HANDLE, HANDLE))(a1 + 648))(v38, v10);
          TempFile = v20;
          if ( v20 < 0 )
          {
            v15 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_62;
            v16 = 37;
LABEL_43:
            v17 = (unsigned int)v20;
            goto LABEL_22;
          }
LABEL_127:
          if ( (*(_BYTE *)(a1 + 656) & 8) != 0
            && !FlushFileBuffers(v10)
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v39 = GetLastError();
            if ( v39 > 0 )
              v39 = (unsigned __int16)v39 | 0x80070000;
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              38,
              &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids,
              (unsigned int)v39);
          }
          *(_DWORD *)(a1 + 656) |= 2u;
          TempFile = 0;
          goto LABEL_135;
        }
      }
      v56 = 0;
      *(_QWORD *)&v62 = off_18004C7C0;
      *((_QWORD *)&v62 + 1) = v10;
      v36 = v64;
      if ( v33 != (_BYTE *)&WPP_GLOBAL_Control && (v33[28] & 4) != 0 )
        WPP_SF_Dd(*((_QWORD *)v33 + 2), 33, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids, HIDWORD(v64), v64);
      v37 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD, _QWORD, _QWORD))(v63[0] + 40LL))(v63, 0, 0, 0);
      TempFile = v37;
      if ( v37 < 0 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_61;
        v34 = 34;
        goto LABEL_110;
      }
      v37 = (*(__int64 (__fastcall **)(_QWORD *, __int128 *, __int64))(a1 + 640))(v63, &v62, v36);
      TempFile = v37;
      if ( v37 < 0 )
      {
        v33 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_61;
        v34 = 35;
LABEL_110:
        v35 = (unsigned int)v37;
        goto LABEL_97;
      }
    }
    v12 = -1;
    goto LABEL_127;
  }
  TempFile = -2147019873;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, &WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids);
LABEL_149:
  MmsFree(v63);
  if ( TempFile < 0 && (unsigned __int64)v10 + 1 > 1 )
    UtilMarkFileForDelete(v10, v45);
  if ( (unsigned __int64)v10 + 1 > 1 )
    CloseHandle(v10);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  return (unsigned int)TempFile;
}

```

## disassembly

```asm
0x1800199f8  push    rbp
0x1800199fa  push    rbx
0x1800199fb  push    rsi
0x1800199fc  push    rdi
0x1800199fd  push    r12
0x1800199ff  push    r13
0x180019a01  push    r14
0x180019a03  lea     rbp, [rsp-2D0h]
0x180019a0b  sub     rsp, 3D0h
0x180019a12  mov     rax, cs:__security_cookie
0x180019a19  xor     rax, rsp
0x180019a1c  mov     [rbp+300h+var_40], rax
0x180019a23  mov     [rsp+400h+var_388], r9
0x180019a28  mov     [rsp+400h+var_3B0], r8d
0x180019a2d  mov     rbx, rdx
0x180019a30  mov     [rbp+300h+hProcess], rdx
0x180019a34  mov     r14, rcx
0x180019a37  mov     rax, [rbp+300h+arg_20]
0x180019a3e  mov     [rsp+400h+var_3A8], rax
0x180019a43  xor     edi, edi
0x180019a45  mov     [rsp+400h+pbDebuggerPresent], edi
0x180019a49  xor     edx, edx; Val
0x180019a4b  lea     r8d, [rdi+50h]; Size
0x180019a4f  lea     rcx, [rbp+300h+var_300]; void *
0x180019a53  call    memset_0
0x180019a58  mov     [rbp+300h+hObject], rdi
0x180019a5c  xorps   xmm0, xmm0
0x180019a5f  movups  [rbp+300h+var_318], xmm0
0x180019a63  xorps   xmm1, xmm1
0x180019a66  movups  [rbp+300h+var_360], xmm1
0x180019a6a  mov     r13d, edi
0x180019a6d  mov     [rsp+400h+var_398], rdi
0x180019a72  movups  [rbp+300h+var_338], xmm0
0x180019a76  movups  xmmword ptr [rbp+300h+ExceptionParam.ThreadId], xmm1
0x180019a7a  movups  xmmword ptr [rbp+300h+CallbackParam.CallbackRoutine], xmm0
0x180019a7e  test    rbx, rbx
0x180019a81  jnz     short loc_180019A88
0x180019a83  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019a88  mov     eax, [r14+290h]
0x180019a8f  or      r12, 0FFFFFFFFFFFFFFFFh
0x180019a93  lea     r9, unk_18004FE4C
0x180019a9a  lea     esi, [r12+3]
0x180019a9f  test    sil, al
0x180019aa2  jz      short loc_180019AE0
0x180019aa4  lea     edi, [rsi-1]
0x180019aa7  lea     rsi, WPP_GLOBAL_Control
0x180019aae  mov     rcx, cs:WPP_GLOBAL_Control
0x180019ab5  cmp     rcx, rsi
0x180019ab8  jz      loc_18001A21D
0x180019abe  test    byte ptr [rcx+1Ch], 4
0x180019ac2  jz      loc_18001A21D
0x180019ac8  lea     edx, [rdi+13h]
0x180019acb  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x180019ad2  mov     rcx, [rcx+10h]
0x180019ad6  call    WPP_SF_
0x180019adb  jmp     loc_18001A216
0x180019ae0  test    al, 1
0x180019ae2  jnz     short loc_180019AEE
0x180019ae4  mov     edi, 8007139Fh
0x180019ae9  jmp     loc_18001A333
0x180019aee  cmp     [r14+5Ch], edi
0x180019af2  jz      short loc_180019B4C
0x180019af4  lea     rdx, [rsp+400h+pbDebuggerPresent]; pbDebuggerPresent
0x180019af9  mov     rcx, rbx; hProcess
0x180019afc  call    cs:__imp_CheckRemoteDebuggerPresent
0x180019b02  test    eax, eax
0x180019b04  jz      short loc_180019B4C
0x180019b06  cmp     [rsp+400h+pbDebuggerPresent], edi
0x180019b0a  jz      short loc_180019B4C
0x180019b0c  mov     edi, 8007139Fh
0x180019b11  lea     rsi, WPP_GLOBAL_Control
0x180019b18  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b1f  cmp     rcx, rsi
0x180019b22  jz      loc_18001A333
0x180019b28  test    byte ptr [rcx+1Ch], 4
0x180019b2c  jz      loc_18001A333
0x180019b32  mov     edx, 15h
0x180019b37  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x180019b3e  mov     rcx, [rcx+10h]
0x180019b42  call    WPP_SF_
0x180019b47  jmp     loc_18001A333
0x180019b4c  mov     [rsp+400h+hFile], r12
0x180019b51  test    byte ptr [r14+290h], 4
0x180019b59  jz      loc_180019CBE
0x180019b5f  cmp     [r14+280h], rdi
0x180019b66  jz      short loc_180019BCB
0x180019b68  lea     rcx, [rbp+300h+var_300]
0x180019b6c  call    MmsCreate
0x180019b71  mov     edi, eax
0x180019b73  test    eax, eax
0x180019b75  jns     short loc_180019BB5
0x180019b77  lea     rsi, WPP_GLOBAL_Control
0x180019b7e  mov     rcx, cs:WPP_GLOBAL_Control
0x180019b85  cmp     rcx, rsi
0x180019b88  jz      loc_180019E04
0x180019b8e  test    byte ptr [rcx+1Ch], 1
0x180019b92  jz      loc_180019E04
0x180019b98  mov     edx, 16h
0x180019b9d  mov     r9d, edi
0x180019ba0  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x180019ba7  mov     rcx, [rcx+10h]
0x180019bab  call    WPP_SF_d
0x180019bb0  jmp     loc_180019E04
0x180019bb5  lea     rsi, [rbp+300h+var_300]
0x180019bb9  mov     [rsp+400h+hFile], rsi
0x180019bbe  lea     rax, [rbp+300h+var_300]
0x180019bc2  mov     qword ptr [rbp+300h+var_360+8], rax
0x180019bc6  jmp     loc_180019CBE
0x180019bcb  cmp     [r14+288h], rdi
0x180019bd2  jnz     short loc_180019BD9
0x180019bd4  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180019bd9  mov     dword ptr [rsp+400h+var_3C8], edi
0x180019bdd  mov     dword ptr [rsp+400h+hTemplateFile], edi
0x180019be1  mov     qword ptr [rsp+400h+dwFlagsAndAttributes], rdi
0x180019be6  lea     r9, [rbp+300h+FileName]
0x180019bed  lea     r8, aDmp_1; ".dmp"
0x180019bf4  xor     edx, edx
0x180019bf6  xor     ecx, ecx
0x180019bf8  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x180019bfd  mov     edi, eax
0x180019bff  xor     eax, eax
0x180019c01  test    edi, edi
0x180019c03  jns     short loc_180019C2E
0x180019c05  lea     rsi, WPP_GLOBAL_Control
0x180019c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c13  cmp     rcx, rsi
0x180019c16  jz      loc_180019E04
0x180019c1c  test    byte ptr [rcx+1Ch], 1
0x180019c20  jz      loc_180019E04
0x180019c26  lea     edx, [rax+17h]
0x180019c29  jmp     loc_180019B9D
0x180019c2e  mov     [rsp+400h+hTemplateFile], rax; hTemplateFile
0x180019c33  mov     [rsp+400h+dwFlagsAndAttributes], 4000100h; dwFlagsAndAttributes
0x180019c3b  mov     [rsp+400h+dwCreationDisposition], esi; dwCreationDisposition
0x180019c3f  xor     r9d, r9d; lpSecurityAttributes
0x180019c42  xor     r8d, r8d; dwShareMode
0x180019c45  mov     edx, 0C0010000h; dwDesiredAccess
0x180019c4a  lea     rcx, [rbp+300h+FileName]; lpFileName
0x180019c51  call    cs:__imp_CreateFileW
0x180019c57  mov     rcx, rax
0x180019c5a  mov     [rbp+300h+hObject], rax
0x180019c5e  inc     rax
0x180019c61  cmp     rax, 1
0x180019c65  ja      short loc_180019CB1
0x180019c67  call    cs:__imp_GetLastError
0x180019c6d  mov     edi, eax
0x180019c6f  test    eax, eax
0x180019c71  jle     short loc_180019C7C
0x180019c73  movzx   edi, ax
0x180019c76  or      edi, 80070000h
0x180019c7c  mov     eax, 80004005h
0x180019c81  test    edi, edi
0x180019c83  cmovns  edi, eax
0x180019c86  lea     rsi, WPP_GLOBAL_Control
0x180019c8d  mov     rcx, cs:WPP_GLOBAL_Control
0x180019c94  cmp     rcx, rsi
0x180019c97  jz      loc_180019E04
0x180019c9d  test    byte ptr [rcx+1Ch], 1
0x180019ca1  jz      loc_180019E04
0x180019ca7  mov     edx, 18h
0x180019cac  jmp     loc_180019B9D
0x180019cb1  mov     qword ptr [rbp+300h+var_360+8], 0
0x180019cb9  mov     [rsp+400h+hFile], rcx
0x180019cbe  mov     rcx, [r14+30h]; wchar_t *
0x180019cc2  call    ?UtilEnsureDirectory@@YAJPEB_WPEAU_SECURITY_ATTRIBUTES@@@Z; UtilEnsureDirectory(wchar_t const *,_SECURITY_ATTRIBUTES *)
0x180019cc7  mov     edi, eax
0x180019cc9  test    eax, eax
0x180019ccb  jns     short loc_180019CFB
0x180019ccd  lea     rsi, WPP_GLOBAL_Control
0x180019cd4  mov     rcx, cs:WPP_GLOBAL_Control
0x180019cdb  cmp     rcx, rsi
0x180019cde  jz      loc_180019E04
0x180019ce4  test    byte ptr [rcx+1Ch], 1
0x180019ce8  jz      loc_180019E04
0x180019cee  mov     edx, 19h
0x180019cf3  mov     r9d, eax
0x180019cf6  jmp     loc_180019BA0
0x180019cfb  mov     r8d, [r14+50h]
0x180019cff  dec     r8d; unsigned int
0x180019d02  mov     rcx, [r14+30h]; wchar_t *
0x180019d06  call    ?UtilPruneFolder@@YAJPEB_W0K@Z; UtilPruneFolder(wchar_t const *,wchar_t const *,ulong)
0x180019d0b  mov     edi, eax
0x180019d0d  test    eax, eax
0x180019d0f  jns     short loc_180019D39
0x180019d11  lea     rsi, WPP_GLOBAL_Control
0x180019d18  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d1f  cmp     rcx, rsi
0x180019d22  jz      loc_180019E04
0x180019d28  test    byte ptr [rcx+1Ch], 1
0x180019d2c  jz      loc_180019E04
0x180019d32  mov     edx, 1Ah
0x180019d37  jmp     short loc_180019CF3
0x180019d39  mov     rcx, rbx; Process
0x180019d3c  call    cs:__imp_GetProcessId
0x180019d42  mov     r12d, eax
0x180019d45  lea     rsi, WPP_GLOBAL_Control
0x180019d4c  mov     ebx, 80004005h
0x180019d51  test    eax, eax
0x180019d53  jnz     short loc_180019D96
0x180019d55  call    cs:__imp_GetLastError
0x180019d5b  test    eax, eax
0x180019d5d  jle     short loc_180019D69
0x180019d5f  movzx   eax, ax
0x180019d62  or      eax, 80070000h
0x180019d67  test    eax, eax
0x180019d69  cmovns  eax, ebx
0x180019d6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180019d73  cmp     rcx, rsi
0x180019d76  jz      short loc_180019D96
0x180019d78  test    byte ptr [rcx+1Ch], 2
0x180019d7c  jz      short loc_180019D96
0x180019d7e  mov     edx, 1Bh
0x180019d83  mov     r9d, eax
0x180019d86  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x180019d8d  mov     rcx, [rcx+10h]
0x180019d91  call    WPP_SF_d
0x180019d96  lea     rax, [r14+8]
0x180019d9a  mov     r9d, [r14+290h]
0x180019da1  shr     r9d, 2
0x180019da5  and     r9d, 1
0x180019da9  mov     qword ptr [rsp+400h+dwFlagsAndAttributes], rax
0x180019dae  lea     rax, [rsp+400h+var_398]
0x180019db3  mov     qword ptr [rsp+400h+dwCreationDisposition], rax
0x180019db8  mov     r8d, r12d
0x180019dbb  mov     rdx, [r14+270h]
0x180019dc2  mov     rcx, [r14+30h]
0x180019dc6  call    ?CreateUniqueDumpFile@CLocalDumpGenerator@@CAJPEB_W0KHPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CLocalDumpGenerator::CreateUniqueDumpFile(wchar_t const *,wchar_t const *,ulong,int,tlx::unique_any<tlx::file_handle_traits> *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x180019dcb  mov     edi, eax
0x180019dcd  xor     ebx, ebx
0x180019dcf  test    eax, eax
0x180019dd1  jns     short loc_180019E15
0x180019dd3  mov     rcx, cs:WPP_GLOBAL_Control
0x180019dda  cmp     rcx, rsi
0x180019ddd  jz      short loc_180019DFB
0x180019ddf  test    byte ptr [rcx+1Ch], 1
0x180019de3  jz      short loc_180019DFB
0x180019de5  lea     edx, [rbx+1Ch]
0x180019de8  mov     r9d, eax
0x180019deb  lea     r8, WPP_4fd2d0472bda38cad05aba6dffb91300_Traceguids
0x180019df2  mov     rcx, [rcx+10h]
0x180019df6  call    WPP_SF_d
0x180019dfb  mov     r13, [rsp+400h+var_398]
0x180019e00  or      r12, 0FFFFFFFFFFFFFFFFh
0x180019e04  cmp     edi, 8007139Fh
0x180019e0a  jz      loc_18001A333
0x180019e10  jmp     loc_18001A216
0x180019e15  mov     r8, [rsp+400h+var_388]
0x180019e1a  mov     rdx, [rsp+400h+var_3A8]
0x180019e1f  test    r8, r8
0x180019e22  jz      short loc_180019E43
0x180019e24  test    rdx, rdx
0x180019e27  jz      short loc_180019E43
0x180019e29  mov     qword ptr [rbp+300h+var_338], r8
0x180019e2d  mov     qword ptr [rbp+300h+var_338+8], rdx
0x180019e31  mov     eax, [rsp+400h+var_3B0]
0x180019e35  mov     [rbp+300h+ExceptionParam.ThreadId], eax
0x180019e38  lea     rax, [rbp+300h+var_338]
0x180019e3c  mov     [rbp+300h+ExceptionParam.ExceptionPointers], rax
0x180019e40  mov     [rbp+300h+ExceptionParam.ClientPointers], ebx
0x180019e43  mov     qword ptr [rbp+300h+var_360], r14
0x180019e47  lea     rax, ?static_MiniDumpCallback@CLocalDumpGenerator@@CAHPEAXQEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; CLocalDumpGenerator::static_MiniDumpCallback(void *,_MINIDUMP_CALLBACK_INPUT * const,_MINIDUMP_CALLBACK_OUTPUT *)
0x180019e4e  mov     [rbp+300h+CallbackParam.CallbackRoutine], rax
0x180019e52  lea     rax, [rbp+300h+var_360]
0x180019e56  mov     [rbp+300h+CallbackParam.CallbackParam], rax
0x180019e5a  mov     ecx, [r14+54h]
0x180019e5e  test    ecx, ecx
0x180019e60  jz      short loc_180019E7E
0x180019e62  sub     ecx, 1
0x180019e65  jz      short loc_180019E77
0x180019e67  cmp     ecx, 1
0x180019e6a  jz      short loc_180019E70
0x180019e6c  mov     ecx, ebx
0x180019e6e  jmp     short loc_180019E82
0x180019e70  mov     ecx, 1826h
0x180019e75  jmp     short loc_180019E82
0x180019e77  mov     ecx, 121h
0x180019e7c  jmp     short loc_180019E82
0x180019e7e  mov     ecx, [r14+58h]
0x180019e82  mov     ebx, ecx
0x180019e84  bts     ebx, 11h
0x180019e88  xor     edi, edi
0x180019e8a  test    cl, 2
0x180019e8d  cmovz   ebx, ecx
0x180019e90  test    r8, r8
0x180019e93  jz      short loc_180019E9E
0x180019e95  test    rdx, rdx
0x180019e98  lea     rax, [rbp+300h+ExceptionParam]
0x180019e9c  jnz     short loc_180019EA1
0x180019e9e  mov     rax, rdi
0x180019ea1  test    byte ptr [r14+290h], 4
0x180019ea9  mov     r13, [rsp+400h+var_398]
0x180019eae  mov     r8, r13
0x180019eb1  cmovnz  r8, [rsp+400h+hFile]; hFile
0x180019eb7  lea     rcx, [rbp+300h+CallbackParam]
0x180019ebb  mov     [rsp+400h+hTemplateFile], rcx; CallbackParam
0x180019ec0  mov     qword ptr [rsp+400h+dwFlagsAndAttributes], rdi; UserStreamParam
0x180019ec5  mov     qword ptr [rsp+400h+dwCreationDisposition], rax; ExceptionParam
0x180019eca  mov     r9d, ebx; DumpType
0x180019ecd  mov     edx, r12d; ProcessId
0x180019ed0  mov     rcx, [rbp+300h+hProcess]; hProcess
  ... truncated ...
```
