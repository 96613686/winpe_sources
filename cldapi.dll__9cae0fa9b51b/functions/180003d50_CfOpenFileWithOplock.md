# CfOpenFileWithOplock

- ea: `0x180003d50`
- end: `0x18000465d`
- name: `CfOpenFileWithOplock`
- size: `2317`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callees

- `0x180001078`
- `0x180001aa0`
- `0x18000231e`
- `0x180003d50`
- `0x1800046bc`
- `0x180004804`
- `0x180012c28`

## import_xrefs

- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800041a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004476`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800041a9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180004476`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800041e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800044a3`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800041e2`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800044a3`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000448e`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x18000448e`
- `ntdll!RtlInitializeSRWLock` at `0x180003e62`
- `ntdll!RtlInitializeSRWLock` at `0x180003e62`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180003e91`
- `ntdll!RtlInitializeGenericTableAvl` at `0x180003e91`
- `ntdll!RtlNtStatusToDosError` at `0x180003fef`
- `ntdll!RtlNtStatusToDosError` at `0x180003fef`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800041cc`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800041cc`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004022`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x180004022`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003ec5`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180003ec5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180003f1b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180003f1b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ed9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003f2f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004037`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800040ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004261`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800042bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800043b1`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003ddb`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180003ddb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004067`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000460e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004067`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004141`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000460e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000407f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004159`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000407f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004624`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004624`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800040d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004241`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800040d3`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180004241`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180003dff`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800042aa`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x180003dff`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x1800042aa`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004371`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180004371`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000444b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044d7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003e4f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003f5e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000444b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044d7`

## string_xrefs

- `0x180003e33`: `CreateIoCompletionPort For IOCP failed`
- `0x180003f4f`: `TerminateThread for OplockCompletionWorker failed`
- `0x180003ef9`: `CreateThread for OplockCompletionWorker failed`
- `0x18000400f`: `Failed to open file with reparse point and oplock`
- `0x18000405b`: `ResumeThread for OplockCompletionWorker failed`
- `0x18000420e`: `Failed to insert element into OplockCompletionKeyTable`
- `0x18000418a`: `Failed to allocate completion context`
- `0x18000428e`: `Failed to create overlapped event`
- `0x1800044f2`: `CfOpenFileWithOplock`

## pseudocode

```c
__int64 __fastcall CfOpenFileWithOplock(const WCHAR *a1, int a2, _QWORD *a3)
{
  signed int v3; // edi
  __int64 v4; // r15
  unsigned int v5; // esi
  unsigned int v6; // r14d
  unsigned int v7; // r12d
  unsigned __int64 v8; // rbx
  HANDLE IoCompletionPort; // r13
  signed int LastError; // eax
  const wchar_t *v11; // rdx
  HANDLE Thread; // r13
  signed int v13; // eax
  signed int v14; // eax
  char v15; // dl
  int v16; // r13d
  unsigned int v17; // eax
  NTSTATUS v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  HANDLE ProcessHeap; // rax
  HANDLE EventW; // rax
  signed int v23; // eax
  HANDLE v24; // rax
  char *v25; // rax
  PVOID inserted; // rbx
  _QWORD **v27; // rbx
  HANDLE **v28; // r8
  signed int v29; // eax
  signed int v30; // eax
  __int64 v31; // rcx
  signed int v32; // eax
  BOOLEAN v33; // bl
  _QWORD **v34; // rax
  _QWORD *v35; // rcx
  const WCHAR *v36; // rax
  int v37; // ecx
  HANDLE v38; // rax
  _QWORD **Buffer; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int8 NewElement[8]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v42; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v43; // [rsp+68h] [rbp-98h] BYREF
  __int64 v44; // [rsp+70h] [rbp-90h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-88h] BYREF
  _QWORD *v46; // [rsp+80h] [rbp-80h] BYREF
  const WCHAR *v47; // [rsp+88h] [rbp-78h] BYREF
  DWORD BytesReturned; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v50; // [rsp+A0h] [rbp-60h] BYREF
  char v51[8]; // [rsp+B0h] [rbp-50h] BYREF
  const wchar_t *v52; // [rsp+B8h] [rbp-48h]
  const WCHAR *v53; // [rsp+C0h] [rbp-40h]
  unsigned int v54; // [rsp+C8h] [rbp-38h]
  int v55; // [rsp+CCh] [rbp-34h]
  int v56; // [rsp+D0h] [rbp-30h]
  unsigned int v57; // [rsp+D4h] [rbp-2Ch]
  char *v58; // [rsp+D8h] [rbp-28h]
  _QWORD *v59; // [rsp+E0h] [rbp-20h]
  __int64 v60; // [rsp+E8h] [rbp-18h]
  int v61; // [rsp+F0h] [rbp-10h]
  __int64 v62; // [rsp+F8h] [rbp-8h]
  char *v63; // [rsp+100h] [rbp+0h]
  __int64 InBuffer; // [rsp+110h] [rbp+10h] BYREF
  int v65; // [rsp+118h] [rbp+18h]
  char v66[32]; // [rsp+120h] [rbp+20h] BYREF
  const wchar_t *v67; // [rsp+140h] [rbp+40h]
  __int64 v68; // [rsp+148h] [rbp+48h]
  unsigned __int64 *v69; // [rsp+150h] [rbp+50h]
  __int64 v70; // [rsp+158h] [rbp+58h]
  _QWORD **v71; // [rsp+160h] [rbp+60h]
  __int64 v72; // [rsp+168h] [rbp+68h]
  const WCHAR *v73; // [rsp+170h] [rbp+70h]
  int v74; // [rsp+178h] [rbp+78h]
  int v75; // [rsp+17Ch] [rbp+7Ch]
  const WCHAR **v76; // [rsp+180h] [rbp+80h]
  __int64 v77; // [rsp+188h] [rbp+88h]
  _QWORD *v78; // [rsp+190h] [rbp+90h]
  __int64 v79; // [rsp+198h] [rbp+98h]
  __int64 *v80; // [rsp+1A0h] [rbp+A0h]
  __int64 v81; // [rsp+1A8h] [rbp+A8h]
  __int64 *v82; // [rsp+1B0h] [rbp+B0h]
  __int64 v83; // [rsp+1B8h] [rbp+B8h]

  v3 = 0;
  v46 = a3;
  v4 = -1;
  LODWORD(v44) = a2;
  v47 = a1;
  hObject = (HANDLE)-1LL;
  LODWORD(v43) = 129;
  InBuffer = 0;
  v5 = 0x200000;
  v65 = 0;
  v6 = 7;
  Buffer = 0;
  v7 = 1;
  NewElement[0] = 0;
  v8 = 0;
  BytesReturned = 0;
  UnbiasedTime = 0;
  memset_0(v51, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( !CompletionPort )
  {
    IoCompletionPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
    if ( !IoCompletionPort )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v3 <= -1 )
    {
      v11 = L"CreateIoCompletionPort For IOCP failed";
      goto LABEL_80;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&CompletionPort, (signed __int64)IoCompletionPort, 0) )
      CloseHandle(IoCompletionPort);
    RtlInitializeSRWLock(&qword_18002AC88);
    v3 = 0;
    RtlInitializeGenericTableAvl(
      &stru_18002AC20,
      CfpOplockCompletionKeyTableCompare,
      CfpOplockCompletionKeyTableAllocate,
      CfpSyncRootTableFree,
      0);
  }
  if ( !hThread )
  {
    Thread = CreateThread(0, 0, CfpOplockCompletionWorker, 0, 4u, 0);
    if ( !Thread )
    {
      v13 = GetLastError();
      v3 = v13;
      if ( v13 > 0 )
        v3 = (unsigned __int16)v13 | 0x80070000;
    }
    if ( v3 <= -1 )
    {
      v11 = L"CreateThread for OplockCompletionWorker failed";
      goto LABEL_80;
    }
    if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hThread, (signed __int64)Thread, 0) )
    {
      if ( TerminateThread(Thread, 0) )
      {
        v3 = 0;
      }
      else
      {
        v14 = GetLastError();
        v3 = v14;
        if ( v14 > 0 )
          v3 = (unsigned __int16)v14 | 0x80070000;
      }
      if ( v3 <= -1 )
      {
        v11 = L"TerminateThread for OplockCompletionWorker failed";
        goto LABEL_80;
      }
      CloseHandle(Thread);
    }
    else
    {
      if ( ResumeThread(hThread) == -1 )
      {
        v20 = GetLastError();
        v3 = v20;
        if ( v20 > 0 )
          v3 = (unsigned __int16)v20 | 0x80070000;
      }
      else
      {
        v3 = 0;
      }
      if ( v3 <= -1 )
      {
        v11 = L"ResumeThread for OplockCompletionWorker failed";
        goto LABEL_80;
      }
    }
  }
  v15 = v44;
  v5 = ~((_DWORD)v44 << 13) & 0x10000 | 0x200000;
  LODWORD(v44) = v44 & 1;
  v16 = 2 * (unsigned __int8)v44 + 1;
  v6 = (_BYTE)v44 == 0 ? 7 : 0;
  v17 = (v15 & 2) != 0 ? 387 : 129;
  if ( (v15 & 4) != 0 )
    v17 |= 0x10000u;
  LODWORD(v43) = v17;
  v53 = v47;
  v54 = v17;
  v55 = (_BYTE)v44 == 0 ? 7 : 0;
  v57 = v5;
  v56 = 2 * (unsigned __int8)v44 + 1;
  v18 = CfpCreateFile(v47, &hObject, v17, v6);
  v19 = RtlNtStatusToDosError(v18);
  v3 = v19;
  if ( v19 > 0 )
    v3 = (unsigned __int16)v19 | 0x80070000;
  if ( v3 > -1 )
  {
    ProcessHeap = GetProcessHeap();
    v8 = (unsigned __int64)HeapAlloc(ProcessHeap, 8u, 0x20u);
    v42 = (_QWORD *)v8;
    v3 = v8 == 0 ? 8 : 0;
    if ( !v8 )
      v3 |= 0x80070000;
    if ( v3 > -1 )
    {
      v50 = (unsigned __int64)hObject;
      v59 = (_QWORD *)v8;
      EventW = CreateEventW(0, 1, 0, 0);
      *(_QWORD *)(v8 + 8) = EventW;
      if ( EventW )
      {
        v3 = 0;
      }
      else
      {
        v23 = GetLastError();
        v3 = v23;
        if ( v23 > 0 )
          v3 = (unsigned __int16)v23 | 0x80070000;
      }
      if ( v3 >= 0 )
      {
        *(_QWORD *)v8 = v50;
        *(_BYTE *)(v8 + 28) = v44;
        *(_QWORD *)(v8 + 16) = 1;
        *(_DWORD *)(v8 + 24) = 1;
      }
      if ( v3 > -1 )
      {
        hObject = (HANDLE)-1LL;
        if ( (v5 & 0x10000) == 0 )
        {
          v11 = 0;
          *v46 = v8 | 1;
          v8 = 0;
          goto LABEL_79;
        }
        v24 = GetProcessHeap();
        v25 = (char *)HeapAlloc(v24, 8u, 0x40u);
        Buffer = (_QWORD **)v25;
        v3 = v25 == 0 ? 8 : 0;
        if ( !v25 )
          v3 |= 0x80070000;
        if ( v3 > -1 )
        {
          v63 = v25;
          v58 = v25 + 8;
          RtlAcquireSRWLockExclusive(&qword_18002AC88);
          inserted = RtlInsertElementGenericTableAvl(&stru_18002AC20, &Buffer, 8u, NewElement);
          RtlReleaseSRWLockExclusive(&qword_18002AC88);
          v3 = inserted == 0 ? 8 : 0;
          if ( !inserted )
            v3 |= 0x80070000;
          if ( v3 > -1 )
          {
            *Buffer = v42;
            v27 = Buffer;
            v42 = 0;
            v27[4] = CreateEventW(0, 1, 0, 0);
            v28 = (HANDLE **)Buffer;
            if ( Buffer[4] )
            {
              v3 = 0;
            }
            else
            {
              v29 = GetLastError();
              v28 = (HANDLE **)Buffer;
              v3 = v29;
              if ( v29 > 0 )
                v3 = (unsigned __int16)v29 | 0x80070000;
            }
            if ( v3 > -1 )
            {
              if ( CreateIoCompletionPort(**v28, CompletionPort, (ULONG_PTR)v28, 0) )
              {
                v3 = 0;
              }
              else
              {
                v30 = GetLastError();
                v3 = v30;
                if ( v30 > 0 )
                  v3 = (unsigned __int16)v30 | 0x80070000;
              }
              if ( v3 > -1 )
              {
                LODWORD(InBuffer) = 786433;
                HIDWORD(InBuffer) = v16;
                v65 = 1;
                *((_DWORD *)*Buffer + 6) = 2;
                v59 = *Buffer;
                v62 = **Buffer;
                v61 = *((_DWORD *)*Buffer + 6);
                v60 = (*Buffer)[2];
                if ( DeviceIoControl(
                       (HANDLE)**Buffer,
                       0x90240u,
                       &InBuffer,
                       0xCu,
                       Buffer + 5,
                       0x18u,
                       &BytesReturned,
                       (LPOVERLAPPED)(Buffer + 1)) )
                {
                  v3 = -2147467259;
                  v11 = L"DeviceIoControl returned an unexpected success";
                }
                else
                {
                  if ( GetLastError() == 997 )
                  {
                    v11 = 0;
                    v8 = 0;
                    v31 = (unsigned __int64)*Buffer | 1;
                    Buffer = 0;
                    *v46 = v31;
                    goto LABEL_79;
                  }
                  v32 = GetLastError();
                  v3 = v32;
                  if ( v32 > 0 )
                    v3 = (unsigned __int16)v32 | 0x80070000;
                  v11 = L"DeviceIoControl failed to request oplock";
                }
                *((_DWORD *)*Buffer + 6) = 1;
                v61 = *((_DWORD *)*Buffer + 6);
              }
              else
              {
                v11 = L"Failed to associate handle with IOCP";
              }
            }
            else
            {
              v11 = L"Failed to create overlapped event";
            }
          }
          else
          {
            v11 = L"Failed to insert element into OplockCompletionKeyTable";
          }
          v8 = (unsigned __int64)v42;
        }
        else
        {
          v11 = L"Failed to allocate completion context";
        }
      }
      else
      {
        v11 = L"Failed to initialize protected handle structure";
      }
    }
    else
    {
      v11 = L"Failed to allocate protected handle structure";
    }
  }
  else
  {
    v11 = L"Failed to open file with reparse point and oplock";
  }
LABEL_79:
  v7 = v16;
LABEL_80:
  v52 = v11;
  TlmLogApiReliability(34, 0, 0, 0, 0, UnbiasedTime, (__int64)v51, v3);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v8 )
    CfpDrainProtectedHandle(v8);
  if ( Buffer )
  {
    RtlAcquireSRWLockExclusive(&qword_18002AC88);
    v33 = RtlDeleteElementGenericTableAvl(&stru_18002AC20, &Buffer);
    RtlReleaseSRWLockExclusive(&qword_18002AC88);
    if ( v33 )
    {
      v34 = Buffer;
      if ( *Buffer )
      {
        CfpDrainProtectedHandle(*Buffer);
        v34 = Buffer;
      }
      v35 = v34[4];
      if ( v35 )
        CloseHandle(v35);
      if ( (unsigned int)dword_18002A1A0 > 4 )
      {
        v68 = 42;
        v67 = L"CfOpenFileWithOplock";
        v50 = UnbiasedTime;
        v69 = &v50;
        v46 = Buffer;
        v71 = &v46;
        v36 = v47;
        v70 = 8;
        v72 = 8;
        if ( v47 )
        {
          do
            ++v4;
          while ( v47[v4] );
          v37 = 2 * v4 + 2;
        }
        else
        {
          v36 = &SourceString;
          v37 = 2;
        }
        v73 = v36;
        v47 = (const WCHAR *)(unsigned int)v43;
        v74 = v37;
        v76 = &v47;
        v42 = (_QWORD *)v6;
        v78 = &v42;
        v44 = v7;
        v80 = &v44;
        v43 = v5;
        v82 = &v43;
        v75 = 0;
        v77 = 8;
        v79 = 8;
        v81 = 8;
        v83 = 8;
        tlgWriteTransfer_EventWriteTransfer(&dword_18002A1A0, byte_180023771, 0, 0, 10, v66);
      }
      v38 = GetProcessHeap();
      HeapFree(v38, 0, Buffer);
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180003d50  mov     [rsp-8+arg_8], rbx
0x180003d55  push    rbp
0x180003d56  push    rsi
0x180003d57  push    rdi
0x180003d58  push    r12
0x180003d5a  push    r13
0x180003d5c  push    r14
0x180003d5e  push    r15
0x180003d60  lea     rbp, [rsp-0D0h]
0x180003d68  sub     rsp, 1D0h
0x180003d6f  mov     rax, cs:__security_cookie
0x180003d76  xor     rax, rsp
0x180003d79  mov     [rbp+100h+var_40], rax
0x180003d80  xor     edi, edi
0x180003d82  mov     [rbp+100h+var_180], r8
0x180003d86  or      r15, 0FFFFFFFFFFFFFFFFh
0x180003d8a  mov     dword ptr [rsp+200h+var_190], edx
0x180003d8e  xor     eax, eax
0x180003d90  mov     [rbp+100h+var_178], rcx
0x180003d94  xor     edx, edx; Val
0x180003d96  mov     [rsp+200h+hObject], r15
0x180003d9b  lea     rcx, [rbp+100h+var_150]; void *
0x180003d9f  mov     dword ptr [rsp+200h+var_198], 81h
0x180003da7  lea     r8d, [r15+59h]; Size
0x180003dab  mov     [rbp+100h+InBuffer], rax
0x180003daf  mov     esi, 200000h
0x180003db4  mov     [rbp+100h+var_E8], eax
0x180003db7  lea     r14d, [r15+8]
0x180003dbb  mov     [rsp+200h+Buffer], rdi
0x180003dc0  lea     r12d, [r15+2]
0x180003dc4  mov     [rsp+200h+NewElement], dil
0x180003dc9  mov     ebx, edi
0x180003dcb  mov     [rbp+100h+BytesReturned], edi
0x180003dce  mov     [rbp+100h+UnbiasedTime], rdi
0x180003dd2  call    memset_0
0x180003dd7  lea     rcx, [rbp+100h+UnbiasedTime]; UnbiasedTime
0x180003ddb  call    cs:__imp_QueryUnbiasedInterruptTime
0x180003de2  nop     dword ptr [rax+rax+00h]
0x180003de7  cmp     cs:CompletionPort, rdi
0x180003dee  jnz     loc_180003E9D
0x180003df4  xor     r9d, r9d; NumberOfConcurrentThreads
0x180003df7  xor     r8d, r8d; CompletionKey
0x180003dfa  xor     edx, edx; ExistingCompletionPort
0x180003dfc  mov     rcx, r15; FileHandle
0x180003dff  call    cs:__imp_CreateIoCompletionPort
0x180003e06  nop     dword ptr [rax+rax+00h]
0x180003e0b  mov     r13, rax
0x180003e0e  test    rax, rax
0x180003e11  jnz     short loc_180003E2E
0x180003e13  call    cs:__imp_GetLastError
0x180003e1a  nop     dword ptr [rax+rax+00h]
0x180003e1f  mov     edi, eax
0x180003e21  test    eax, eax
0x180003e23  jle     short loc_180003E2E
0x180003e25  movzx   edi, ax
0x180003e28  or      edi, 80070000h
0x180003e2e  cmp     edi, r15d
0x180003e31  jg      short loc_180003E3F
0x180003e33  lea     rdx, aCreateiocomple; "CreateIoCompletionPort For IOCP failed"
0x180003e3a  jmp     loc_18000440D
0x180003e3f  xor     eax, eax
0x180003e41  lock cmpxchg cs:CompletionPort, r13
0x180003e4a  jz      short loc_180003E5B
0x180003e4c  mov     rcx, r13; hObject
0x180003e4f  call    cs:__imp_CloseHandle
0x180003e56  nop     dword ptr [rax+rax+00h]
0x180003e5b  lea     rcx, qword_18002AC88
0x180003e62  call    cs:__imp_RtlInitializeSRWLock
0x180003e69  nop     dword ptr [rax+rax+00h]
0x180003e6e  xor     edi, edi
0x180003e70  lea     r9, CfpSyncRootTableFree; FreeRoutine
0x180003e77  lea     r8, CfpOplockCompletionKeyTableAllocate; AllocateRoutine
0x180003e7e  mov     [rsp+200h+TableContext], rdi; TableContext
0x180003e83  lea     rdx, CfpOplockCompletionKeyTableCompare; CompareRoutine
0x180003e8a  lea     rcx, stru_18002AC20; Table
0x180003e91  call    cs:__imp_RtlInitializeGenericTableAvl
0x180003e98  nop     dword ptr [rax+rax+00h]
0x180003e9d  cmp     cs:hThread, rdi
0x180003ea4  jnz     loc_180003F6A
0x180003eaa  mov     [rsp+200h+lpThreadId], rdi; lpThreadId
0x180003eaf  lea     r8, CfpOplockCompletionWorker; lpStartAddress
0x180003eb6  xor     r9d, r9d; lpParameter
0x180003eb9  mov     dword ptr [rsp+200h+TableContext], 4; dwCreationFlags
0x180003ec1  xor     edx, edx; dwStackSize
0x180003ec3  xor     ecx, ecx; lpThreadAttributes
0x180003ec5  call    cs:__imp_CreateThread
0x180003ecc  nop     dword ptr [rax+rax+00h]
0x180003ed1  mov     r13, rax
0x180003ed4  test    rax, rax
0x180003ed7  jnz     short loc_180003EF4
0x180003ed9  call    cs:__imp_GetLastError
0x180003ee0  nop     dword ptr [rax+rax+00h]
0x180003ee5  mov     edi, eax
0x180003ee7  test    eax, eax
0x180003ee9  jle     short loc_180003EF4
0x180003eeb  movzx   edi, ax
0x180003eee  or      edi, 80070000h
0x180003ef4  cmp     edi, r15d
0x180003ef7  jg      short loc_180003F05
0x180003ef9  lea     rdx, aCreatethreadFo; "CreateThread for OplockCompletionWorker"...
0x180003f00  jmp     loc_18000440D
0x180003f05  xor     eax, eax
0x180003f07  lock cmpxchg cs:hThread, r13
0x180003f10  jz      loc_18000401B
0x180003f16  xor     edx, edx; dwExitCode
0x180003f18  mov     rcx, r13; hThread
0x180003f1b  call    cs:__imp_TerminateThread
0x180003f22  nop     dword ptr [rax+rax+00h]
0x180003f27  test    eax, eax
0x180003f29  jz      short loc_180003F2F
0x180003f2b  xor     edi, edi
0x180003f2d  jmp     short loc_180003F4A
0x180003f2f  call    cs:__imp_GetLastError
0x180003f36  nop     dword ptr [rax+rax+00h]
0x180003f3b  mov     edi, eax
0x180003f3d  test    eax, eax
0x180003f3f  jle     short loc_180003F4A
0x180003f41  movzx   edi, ax
0x180003f44  or      edi, 80070000h
0x180003f4a  cmp     edi, r15d
0x180003f4d  jg      short loc_180003F5B
0x180003f4f  lea     rdx, aTerminatethrea; "TerminateThread for OplockCompletionWor"...
0x180003f56  jmp     loc_18000440D
0x180003f5b  mov     rcx, r13; hObject
0x180003f5e  call    cs:__imp_CloseHandle
0x180003f65  nop     dword ptr [rax+rax+00h]
0x180003f6a  mov     edx, dword ptr [rsp+200h+var_190]
0x180003f6e  mov     r8d, 10000h
0x180003f74  mov     eax, edx
0x180003f76  shl     eax, 0Dh
0x180003f79  not     eax
0x180003f7b  and     eax, r8d
0x180003f7e  or      esi, eax
0x180003f80  mov     eax, edx
0x180003f82  and     eax, r12d
0x180003f85  mov     dword ptr [rsp+200h+var_190], eax
0x180003f89  movzx   eax, al
0x180003f8c  lea     r13d, ds:1[rax*2]
0x180003f94  neg     al
0x180003f96  sbb     eax, eax
0x180003f98  not     eax
0x180003f9a  and     r14d, eax
0x180003f9d  mov     eax, edx
0x180003f9f  and     al, 2
0x180003fa1  neg     al
0x180003fa3  mov     eax, 81h
0x180003fa8  sbb     ecx, ecx
0x180003faa  and     ecx, 102h
0x180003fb0  add     eax, ecx
0x180003fb2  test    dl, 4
0x180003fb5  jz      short loc_180003FBA
0x180003fb7  or      eax, r8d
0x180003fba  mov     rcx, [rbp+100h+var_178]
0x180003fbe  lea     rdx, [rsp+200h+hObject]
0x180003fc3  mov     [rsp+200h+lpOverlapped], rdx
0x180003fc8  mov     r9d, r14d
0x180003fcb  mov     r8d, eax
0x180003fce  mov     dword ptr [rsp+200h+lpThreadId], esi
0x180003fd2  mov     dword ptr [rsp+200h+var_198], eax
0x180003fd6  mov     [rbp+100h+var_140], rcx
0x180003fda  mov     [rbp+100h+var_138], eax
0x180003fdd  mov     [rbp+100h+var_134], r14d
0x180003fe1  mov     [rbp+100h+var_12C], esi
0x180003fe4  mov     [rbp+100h+var_130], r13d
0x180003fe8  call    CfpCreateFile
0x180003fed  mov     ecx, eax; Status
0x180003fef  call    cs:__imp_RtlNtStatusToDosError
0x180003ff6  nop     dword ptr [rax+rax+00h]
0x180003ffb  mov     edi, eax
0x180003ffd  test    eax, eax
0x180003fff  jle     short loc_18000400A
0x180004001  movzx   edi, ax
0x180004004  or      edi, 80070000h
0x18000400a  cmp     edi, r15d
0x18000400d  jg      short loc_180004067
0x18000400f  lea     rdx, aFailedToOpenFi; "Failed to open file with reparse point "...
0x180004016  jmp     loc_18000440A
0x18000401b  mov     rcx, cs:hThread; hThread
0x180004022  call    cs:__imp_ResumeThread
0x180004029  nop     dword ptr [rax+rax+00h]
0x18000402e  cmp     eax, 0FFFFFFFFh
0x180004031  jz      short loc_180004037
0x180004033  xor     edi, edi
0x180004035  jmp     short loc_180004052
0x180004037  call    cs:__imp_GetLastError
0x18000403e  nop     dword ptr [rax+rax+00h]
0x180004043  mov     edi, eax
0x180004045  test    eax, eax
0x180004047  jle     short loc_180004052
0x180004049  movzx   edi, ax
0x18000404c  or      edi, 80070000h
0x180004052  cmp     edi, r15d
0x180004055  jg      loc_180003F6A
0x18000405b  lea     rdx, aResumethreadFo; "ResumeThread for OplockCompletionWorker"...
0x180004062  jmp     loc_18000440D
0x180004067  call    cs:__imp_GetProcessHeap
0x18000406e  nop     dword ptr [rax+rax+00h]
0x180004073  mov     edx, 8; dwFlags
0x180004078  mov     rcx, rax; hHeap
0x18000407b  lea     r8d, [rdx+18h]; dwBytes
0x18000407f  call    cs:__imp_HeapAlloc
0x180004086  nop     dword ptr [rax+rax+00h]
0x18000408b  mov     rbx, rax
0x18000408e  mov     [rsp+200h+var_1A0], rax
0x180004093  neg     rax
0x180004096  sbb     edi, edi
0x180004098  not     edi
0x18000409a  and     edi, 8
0x18000409d  mov     eax, edi
0x18000409f  or      eax, 80070000h
0x1800040a4  test    rbx, rbx
0x1800040a7  cmovz   edi, eax
0x1800040aa  cmp     edi, r15d
0x1800040ad  jg      short loc_1800040BB
0x1800040af  lea     rdx, aFailedToAlloca_0; "Failed to allocate protected handle str"...
0x1800040b6  jmp     loc_18000440A
0x1800040bb  mov     rax, [rsp+200h+hObject]
0x1800040c0  xor     r9d, r9d; lpName
0x1800040c3  xor     r8d, r8d; bInitialState
0x1800040c6  mov     [rbp+100h+var_160], rax
0x1800040ca  mov     edx, r12d; bManualReset
0x1800040cd  mov     [rbp+100h+var_120], rbx
0x1800040d1  xor     ecx, ecx; lpEventAttributes
0x1800040d3  call    cs:__imp_CreateEventW
0x1800040da  nop     dword ptr [rax+rax+00h]
0x1800040df  mov     [rbx+8], rax
0x1800040e3  test    rax, rax
0x1800040e6  jz      short loc_1800040EC
0x1800040e8  xor     edi, edi
0x1800040ea  jmp     short loc_180004107
0x1800040ec  call    cs:__imp_GetLastError
0x1800040f3  nop     dword ptr [rax+rax+00h]
0x1800040f8  mov     edi, eax
0x1800040fa  test    eax, eax
0x1800040fc  jle     short loc_180004107
0x1800040fe  movzx   edi, ax
0x180004101  or      edi, 80070000h
0x180004107  test    edi, edi
0x180004109  js      short loc_180004121
0x18000410b  mov     rax, [rbp+100h+var_160]
0x18000410f  mov     [rbx], rax
0x180004112  mov     eax, dword ptr [rsp+200h+var_190]
0x180004116  mov     [rbx+1Ch], al
0x180004119  mov     [rbx+10h], r12
0x18000411d  mov     [rbx+18h], r12d
0x180004121  cmp     edi, r15d
0x180004124  jg      short loc_180004132
0x180004126  lea     rdx, aFailedToInitia; "Failed to initialize protected handle s"...
0x18000412d  jmp     loc_18000440A
0x180004132  mov     [rsp+200h+hObject], r15
0x180004137  bt      esi, 10h
0x18000413b  jnb     loc_1800043FC
0x180004141  call    cs:__imp_GetProcessHeap
0x180004148  nop     dword ptr [rax+rax+00h]
0x18000414d  mov     edx, 8; dwFlags
0x180004152  mov     rcx, rax; hHeap
0x180004155  lea     r8d, [rdx+38h]; dwBytes
0x180004159  call    cs:__imp_HeapAlloc
0x180004160  nop     dword ptr [rax+rax+00h]
0x180004165  mov     rcx, rax
0x180004168  mov     [rsp+200h+Buffer], rax
0x18000416d  neg     rcx
0x180004170  sbb     edi, edi
0x180004172  not     edi
0x180004174  and     edi, 8
0x180004177  mov     ecx, edi
0x180004179  or      ecx, 80070000h
0x18000417f  test    rax, rax
0x180004182  cmovz   edi, ecx
0x180004185  cmp     edi, r15d
0x180004188  jg      short loc_180004196
0x18000418a  lea     rdx, aFailedToAlloca; "Failed to allocate completion context"
0x180004191  jmp     loc_18000440A
0x180004196  mov     [rbp+100h+var_100], rax
0x18000419a  lea     rcx, qword_18002AC88
0x1800041a1  add     rax, 8
0x1800041a5  mov     [rbp+100h+var_128], rax
0x1800041a9  call    cs:__imp_RtlAcquireSRWLockExclusive
0x1800041b0  nop     dword ptr [rax+rax+00h]
0x1800041b5  lea     r9, [rsp+200h+NewElement]; NewElement
0x1800041ba  mov     r8d, 8; BufferSize
0x1800041c0  lea     rdx, [rsp+200h+Buffer]; Buffer
0x1800041c5  lea     rcx, stru_18002AC20; Table
0x1800041cc  call    cs:__imp_RtlInsertElementGenericTableAvl
0x1800041d3  nop     dword ptr [rax+rax+00h]
0x1800041d8  lea     rcx, qword_18002AC88
0x1800041df  mov     rbx, rax
0x1800041e2  call    cs:__imp_RtlReleaseSRWLockExclusive
0x1800041e9  nop     dword ptr [rax+rax+00h]
0x1800041ee  mov     rcx, rbx
0x1800041f1  neg     rcx
0x1800041f4  sbb     edi, edi
0x1800041f6  not     edi
0x1800041f8  and     edi, 8
0x1800041fb  mov     ecx, edi
0x1800041fd  or      ecx, 80070000h
0x180004203  test    rbx, rbx
0x180004206  cmovz   edi, ecx
0x180004209  cmp     edi, r15d
0x18000420c  jg      short loc_18000421F
  ... truncated ...
```
