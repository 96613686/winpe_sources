# CfConnectSyncRoot

- ea: `0x180004dd0`
- end: `0x180005b17`
- name: `CfConnectSyncRoot`
- size: `3399`
- prototype: `__int64 __fastcall(const WCHAR *, int *, __int64, int, char **)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180001aa0`
- `0x18000231e`
- `0x1800046bc`
- `0x180004dd0`
- `0x18000b478`
- `0x180010294`
- `0x1800112c0`
- `0x180012054`
- `0x180012c28`
- `0x18001d0ac`

## import_xrefs

- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800053b5`
- `api-ms-win-crt-string-l1-1-0!wcsnlen` at `0x1800053b5`
- `ntdll!RtlInitUnicodeString` at `0x180005123`
- `ntdll!RtlInitUnicodeString` at `0x180005123`
- `ntdll!NtCreateFile` at `0x180005193`
- `ntdll!NtCreateFile` at `0x180005193`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800054b9`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x1800054b9`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800054f8`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x1800054f8`
- `ntdll!RtlInitializeSRWLock` at `0x180004f49`
- `ntdll!RtlInitializeSRWLock` at `0x180004f6a`
- `ntdll!RtlInitializeSRWLock` at `0x180004f49`
- `ntdll!RtlInitializeSRWLock` at `0x180004f6a`
- `ntdll!RtlNtStatusToDosError` at `0x180004fa2`
- `ntdll!RtlNtStatusToDosError` at `0x1800051a1`
- `ntdll!RtlNtStatusToDosError` at `0x1800055dc`
- `ntdll!RtlNtStatusToDosError` at `0x180005666`
- `ntdll!RtlNtStatusToDosError` at `0x1800056f1`
- `ntdll!RtlNtStatusToDosError` at `0x180005789`
- `ntdll!RtlNtStatusToDosError` at `0x180005820`
- `ntdll!RtlNtStatusToDosError` at `0x1800058b5`
- `ntdll!RtlNtStatusToDosError` at `0x18000593f`
- `ntdll!RtlNtStatusToDosError` at `0x1800059d2`
- `ntdll!RtlNtStatusToDosError` at `0x180004fa2`
- `ntdll!RtlNtStatusToDosError` at `0x1800051a1`
- `ntdll!RtlNtStatusToDosError` at `0x1800055dc`
- `ntdll!RtlNtStatusToDosError` at `0x180005666`
- `ntdll!RtlNtStatusToDosError` at `0x1800056f1`
- `ntdll!RtlNtStatusToDosError` at `0x180005789`
- `ntdll!RtlNtStatusToDosError` at `0x180005820`
- `ntdll!RtlNtStatusToDosError` at `0x1800058b5`
- `ntdll!RtlNtStatusToDosError` at `0x18000593f`
- `ntdll!RtlNtStatusToDosError` at `0x1800059d2`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800054da`
- `ntdll!RtlInsertElementGenericTableAvl` at `0x1800054da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052c2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800052c2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000523c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000531e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000523c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800052ce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000531e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005380`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180004e78`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x180004e78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ef1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005515`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005aa6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ef1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004ff1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005011`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800053d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005515`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005aa6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005025`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000552d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180004f0b`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180005025`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800053e9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000552d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005005`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005aba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005005`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005aba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ade`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005ade`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180005205`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180005309`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180005205`
- `api-ms-win-core-file-l1-1-0!GetVolumePathNameW` at `0x180005309`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000536b`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000536b`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000522c`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x18000522c`
- `FLTLIB!FilterSendMessage` at `0x180005a2a`
- `FLTLIB!FilterSendMessage` at `0x180005a2a`

## string_xrefs

- `0x180005686`: `SetCldMsgCommand Failed`
- `0x180004fc2`: `CfpCreateFile Failed`
- `0x1800051c1`: `NtCreateFile Failed`
- `0x18000533e`: `GetVolumePathName Failed`
- `0x1800052ee`: `CfpGetVolumeNameFromPath Failed`

## pseudocode

```c
__int64 __fastcall CfConnectSyncRoot(const WCHAR *a1, int *a2, __int64 a3, int a4, char **a5)
{
  char *v7; // r14
  int v8; // esi
  _DWORD *v9; // rdi
  __int64 v10; // rcx
  int v11; // ebx
  const wchar_t *v12; // rdx
  int v13; // r12d
  HANDLE ProcessHeap; // rax
  __int64 v15; // rdx
  NTSTATUS File; // eax
  signed int v17; // eax
  _DWORD *v18; // r15
  unsigned int v19; // r13d
  HANDLE v20; // rax
  HANDLE v21; // rax
  int SyncRootInfoByHandle; // eax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rax
  int v26; // eax
  __int64 *v27; // r12
  NTSTATUS v28; // eax
  signed int v29; // eax
  _WORD *v30; // rbx
  __int64 v31; // r15
  __int64 v32; // rcx
  WCHAR *v33; // rdx
  _WORD *v34; // rax
  _WORD *v35; // rcx
  __int64 v36; // rcx
  signed int LastError; // eax
  signed int v38; // eax
  signed int v39; // eax
  size_t v40; // rax
  SIZE_T v41; // r15
  HANDLE v42; // rax
  void *v43; // rax
  int v44; // ecx
  int v45; // eax
  int v46; // ecx
  int v47; // eax
  int v48; // ecx
  int v49; // eax
  HANDLE v50; // rax
  NTSTATUS v51; // r15d
  NTSTATUS v52; // ecx
  __int64 v53; // rcx
  __int64 v54; // rax
  unsigned int v55; // ecx
  signed int v56; // eax
  NTSTATUS v57; // ecx
  __int64 v58; // rcx
  __int64 v59; // rax
  signed int v60; // eax
  NTSTATUS v61; // ecx
  __int64 v62; // rcx
  __int64 v63; // rax
  signed int v64; // eax
  NTSTATUS v65; // ecx
  __int64 v66; // rcx
  __int64 v67; // rdx
  __int64 v68; // rax
  signed int v69; // eax
  NTSTATUS v70; // ecx
  __int64 v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // rax
  signed int v74; // eax
  NTSTATUS v75; // ecx
  __int64 v76; // rcx
  __int64 v77; // rax
  signed int v78; // eax
  NTSTATUS v79; // ecx
  __int64 v80; // rcx
  __int64 v81; // rax
  signed int v82; // eax
  __int64 v83; // rcx
  __int64 v84; // rax
  signed int v85; // eax
  __int64 *v86; // rax
  HANDLE v87; // rax
  int v90; // [rsp+64h] [rbp-9Ch]
  DWORD BytesReturned; // [rsp+78h] [rbp-88h] BYREF
  char *Buffer; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int64 UnbiasedTime; // [rsp+88h] [rbp-78h] BYREF
  _DWORD *v95; // [rsp+90h] [rbp-70h]
  _DWORD *v96; // [rsp+98h] [rbp-68h]
  __int64 v97; // [rsp+A0h] [rbp-60h]
  char **v98; // [rsp+A8h] [rbp-58h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+E0h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F0h] [rbp-10h] BYREF
  char v102[8]; // [rsp+100h] [rbp+0h] BYREF
  const wchar_t *v103; // [rsp+108h] [rbp+8h]
  __int64 v104; // [rsp+110h] [rbp+10h]
  int v105; // [rsp+118h] [rbp+18h]
  char *v106; // [rsp+120h] [rbp+20h]
  int v107; // [rsp+128h] [rbp+28h]
  WCHAR RootPathName[264]; // [rsp+160h] [rbp+60h] BYREF
  WCHAR szVolumePathName[264]; // [rsp+370h] [rbp+270h] BYREF

  v97 = a3;
  v98 = a5;
  BytesReturned = 0;
  UnbiasedTime = 0;
  v96 = 0;
  v7 = 0;
  v95 = 0;
  memset(&ObjectAttributes, 0, 44);
  v8 = 0;
  v9 = 0;
  Buffer = 0;
  IoStatusBlock = 0;
  DestinationString = 0;
  memset_0(v102, 0, 0x58u);
  QueryUnbiasedInterruptTime(&UnbiasedTime);
  if ( !a1 || !a2 || (v11 = 0, !a5) )
    v11 = 87;
  if ( v11 )
    v11 |= 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"Invalid Parameter";
LABEL_9:
    v13 = a4;
    goto LABEL_197;
  }
  LOBYTE(v10) = 1;
  v11 = GlobalPortInit(v10);
  if ( v11 <= -1 )
  {
    v12 = L"GlobalPortInit Failed";
    goto LABEL_9;
  }
  v11 = AttachFilterToVolume(a1);
  if ( v11 <= -1 )
  {
    v12 = L"AttachFilterToVolume Failed";
    goto LABEL_9;
  }
  ProcessHeap = GetProcessHeap();
  v7 = (char *)HeapAlloc(ProcessHeap, 8u, 0x120u);
  v11 = v7 == 0 ? 8 : 0;
  if ( !v7 )
    v11 |= 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"newSyncRootData memory allocation Failed";
    goto LABEL_9;
  }
  RtlInitializeSRWLock(v7 + 144);
  *((_QWORD *)v7 + 20) = v7 + 152;
  *((_QWORD *)v7 + 19) = v7 + 152;
  RtlInitializeSRWLock(v7 + 168);
  *(_QWORD *)v7 = 1;
  File = CfpCreateFile(a1, v15, 0, 7);
  v17 = RtlNtStatusToDosError(File);
  v11 = v17;
  if ( v17 > 0 )
    v11 = (unsigned __int16)v17 | 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"CfpCreateFile Failed";
    goto LABEL_9;
  }
  v18 = 0;
  v90 = 0;
  while ( 1 )
  {
    if ( v18 )
    {
      v19 = v18[263] + 1056;
      v20 = GetProcessHeap();
      HeapFree(v20, 0, v18);
    }
    else
    {
      v19 = 1056;
    }
    v21 = GetProcessHeap();
    v18 = HeapAlloc(v21, 0, v19);
    v11 = v18 == 0 ? 8 : 0;
    if ( !v18 )
      v11 |= 0x80070000;
    if ( v11 < 0 )
    {
      v12 = L"syncRootStdInfo memory allocation Failed";
      goto LABEL_9;
    }
    SyncRootInfoByHandle = CfpGetSyncRootInfoByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0);
    v11 = SyncRootInfoByHandle;
    if ( SyncRootInfoByHandle != -2147024662 )
      break;
    if ( ++v90 >= 2 )
      goto LABEL_34;
  }
  if ( SyncRootInfoByHandle <= -1 )
  {
LABEL_34:
    v12 = L"CfpGetSyncRootInfoByHandle Failed";
    goto LABEL_9;
  }
  *((_QWORD *)v7 + 2) = v18;
  v96 = v18 + 7;
  v95 = v18 + 135;
  while ( 1 )
  {
    v26 = *a2;
    if ( *a2 == -1 )
      break;
    v23 = v26;
    v24 = *(_QWORD *)&v7[8 * v26 + 176];
    v11 = v24 != 0 ? 0x57 : 0;
    if ( v24 )
      v11 = (v24 != 0 ? 0x57 : 0) | 0x80070000;
    if ( v11 < 0 )
    {
      v12 = L"CallbackTable entry is NULL";
      goto LABEL_9;
    }
    v25 = *((_QWORD *)a2 + 1);
    a2 += 4;
    *(_QWORD *)&v7[8 * v23 + 176] = v25;
  }
  *((_QWORD *)v7 + 35) = v97;
  RtlInitUnicodeString(&DestinationString, &SourceString);
  v27 = (__int64 *)(v7 + 8);
  ObjectAttributes.RootDirectory = (HANDLE)-1LL;
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v28 = NtCreateFile((PHANDLE)v7 + 1, 0x100000u, &ObjectAttributes, &IoStatusBlock, 0, 0, 7u, 1u, 1u, 0, 0);
  v29 = RtlNtStatusToDosError(v28);
  v11 = v29;
  if ( v29 > 0 )
    v11 = (unsigned __int16)v29 | 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"NtCreateFile Failed";
    goto LABEL_9;
  }
  if ( !a1 || (v30 = v7 + 40, v7 == (char *)-40LL) )
  {
    SetLastError(0x57u);
  }
  else
  {
    *v30 = 0;
    if ( GetVolumePathNameW(a1, szVolumePathName, 0x104u) )
    {
      v31 = 50;
      if ( GetVolumeNameForVolumeMountPointW(szVolumePathName, (LPWSTR)v7 + 20, 0x32u) )
      {
LABEL_58:
        v36 = -1;
        do
          ++v36;
        while ( v30[v36] );
        if ( v30[v36 - 1] == 92 )
          v30[v36 - 1] = 0;
        v11 = 0;
        goto LABEL_66;
      }
      if ( GetLastError() == 4390 )
      {
        v32 = 2147483646;
        v33 = szVolumePathName;
        v34 = v7 + 40;
        do
        {
          if ( !v32 )
            break;
          if ( !*v33 )
            break;
          *v34++ = *v33++;
          --v32;
          --v31;
        }
        while ( v31 );
        v35 = v34 - 1;
        v27 = (__int64 *)(v7 + 8);
        if ( v31 )
          v35 = v34;
        *v35 = 0;
        goto LABEL_58;
      }
    }
  }
  LastError = GetLastError();
  v11 = LastError;
  if ( LastError > 0 )
    v11 = (unsigned __int16)LastError | 0x80070000;
LABEL_66:
  if ( v11 <= -1 )
  {
    v12 = L"CfpGetVolumeNameFromPath Failed";
    goto LABEL_9;
  }
  if ( GetVolumePathNameW(a1, RootPathName, 0x104u) )
  {
    v11 = 0;
  }
  else
  {
    v38 = GetLastError();
    v11 = v38;
    if ( v38 > 0 )
      v11 = (unsigned __int16)v38 | 0x80070000;
  }
  if ( v11 <= -1 )
  {
    v12 = L"GetVolumePathName Failed";
    goto LABEL_9;
  }
  if ( GetVolumeInformationW(RootPathName, 0, 0, (LPDWORD)v7 + 6, 0, 0, 0, 0) )
  {
    v11 = 0;
  }
  else
  {
    v39 = GetLastError();
    v11 = v39;
    if ( v39 > 0 )
      v11 = (unsigned __int16)v39 | 0x80070000;
  }
  if ( v11 <= -1 )
  {
    v12 = L"GetVolumeInformation Failed";
    goto LABEL_9;
  }
  v40 = wcsnlen(RootPathName, 0x104u);
  if ( v40 - 1 <= 0x102 )
  {
    v41 = 2 * v40;
    v42 = GetProcessHeap();
    v43 = HeapAlloc(v42, 8u, v41);
    *((_QWORD *)v7 + 4) = v43;
    v11 = v43 == 0 ? 8 : 0;
    if ( !v43 )
      v11 |= 0x80070000;
    if ( v11 <= -1 )
    {
      v12 = L"VolumeDosName memory allocation Failed";
      goto LABEL_9;
    }
    memcpy_0(v43, RootPathName, v41 - 2);
  }
  v44 = (*((_QWORD *)v7 + 27) != 0) | 2;
  if ( !*((_QWORD *)v7 + 28) )
    v44 = *((_QWORD *)v7 + 27) != 0;
  v45 = v44 | 8;
  if ( !*((_QWORD *)v7 + 30) )
    v45 = v44;
  v46 = v45 | 0x20;
  if ( !*((_QWORD *)v7 + 32) )
    v46 = v45;
  v47 = v46 | 0x80;
  if ( !*((_QWORD *)v7 + 34) )
    v47 = v46;
  v48 = v47 | 4;
  if ( !*((_QWORD *)v7 + 29) )
    v48 = v47;
  v49 = v48 | 0x10;
  if ( !*((_QWORD *)v7 + 31) )
    v49 = v48;
  v8 = v49 | 0x40;
  if ( !*((_QWORD *)v7 + 33) )
    v8 = v49;
  RtlAcquireSRWLockExclusive(&qword_18002ACF8);
  Buffer = v7;
  if ( !RtlInsertElementGenericTableAvl(&stru_18002AC90, &Buffer, 8u, 0) )
    v11 = -2147024888;
  RtlReleaseSRWLockExclusive(&qword_18002ACF8);
  if ( v11 <= -1 )
  {
    v12 = L"RtlInsertElementGenericTableAvl Failed";
    goto LABEL_9;
  }
  v50 = GetProcessHeap();
  v9 = HeapAlloc(v50, 8u, 0xF4u);
  v11 = v9 == 0 ? 8 : 0;
  if ( !v9 )
    v11 |= 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"CldCmdConnectSyncRoot memory allocation failed";
    goto LABEL_9;
  }
  *(_QWORD *)v9 = 1886219331;
  v9[2] = 200;
  v9[3] = 1507328;
  memset_0(v9 + 4, 0, 0xB8u);
  v51 = -1073741811;
  if ( *((_WORD *)v9 + 7) )
  {
    v53 = (unsigned int)v9[2];
    if ( ((v53 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= 0xF4 )
    {
      v55 = (v53 + 3) & 0xFFFFFFFC;
      v54 = v55;
      v9[2] = v55;
      v9[5] = v55;
      v52 = 0;
      v9[4] = 65543;
      *((_BYTE *)v9 + v54) = 1;
      ++v9[2];
    }
    else
    {
      v52 = -1073741789;
    }
  }
  else
  {
    v52 = -1073741811;
  }
  v56 = RtlNtStatusToDosError(v52);
  v11 = v56;
  if ( v56 > 0 )
    v11 = (unsigned __int16)v56 | 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"SetVersion Failed";
    goto LABEL_9;
  }
  if ( *((_WORD *)v9 + 7) > 1u )
  {
    v58 = (unsigned int)v9[2];
    if ( ((v58 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 2 <= 0xF4 )
    {
      v59 = ((_DWORD)v58 + 3) & 0xFFFFFFFC;
      v9[2] = v59;
      if ( *((_WORD *)v9 + 12) )
        *((_WORD *)v9 + 6) |= 1u;
      v9[6] = 131080;
      v57 = 0;
      v9[7] = v59;
      *(_WORD *)((char *)v9 + v59) = 4;
      v9[2] += 2;
    }
    else
    {
      v57 = -1073741789;
    }
  }
  else
  {
    v57 = -1073741811;
  }
  v60 = RtlNtStatusToDosError(v57);
  v11 = v60;
  if ( v60 > 0 )
    v11 = (unsigned __int16)v60 | 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"SetCldMsgCommand Failed";
    goto LABEL_9;
  }
  if ( *((_WORD *)v9 + 7) > 4u )
  {
    v62 = (unsigned int)v9[2];
    if ( ((v62 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF4 )
    {
      v63 = ((_DWORD)v62 + 3) & 0xFFFFFFFC;
      v9[2] = v63;
      if ( *((_WORD *)v9 + 24) )
        *((_WORD *)v9 + 6) |= 1u;
      v9[12] = 524294;
      v61 = 0;
      v9[13] = v63;
      *(_QWORD *)((char *)v9 + v63) = v7;
      v9[2] += 8;
    }
    else
    {
      v61 = -1073741789;
    }
  }
  else
  {
    v61 = -1073741811;
  }
  v64 = RtlNtStatusToDosError(v61);
  v11 = v64;
  if ( v64 > 0 )
    v11 = (unsigned __int16)v64 | 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"SetCldDsMsgSyncRootKey Failed";
    goto LABEL_9;
  }
  if ( *((_WORD *)v9 + 7) > 2u )
  {
    v66 = (unsigned int)v9[2];
    if ( ((v66 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF4 )
    {
      v67 = *v27;
      v68 = ((_DWORD)v66 + 3) & 0xFFFFFFFC;
      v9[2] = v68;
      if ( *((_WORD *)v9 + 16) )
        *((_WORD *)v9 + 6) |= 1u;
      v9[8] = 524299;
      v9[9] = v68;
      v65 = 0;
      *(_QWORD *)((char *)v9 + v68) = v67;
      v9[2] += 8;
    }
    else
    {
      v65 = -1073741789;
    }
  }
  else
  {
    v65 = -1073741811;
  }
  v69 = RtlNtStatusToDosError(v65);
  v11 = v69;
  if ( v69 > 0 )
    v11 = (unsigned __int16)v69 | 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"SetCldDsMsgSyncRoot Failed";
    goto LABEL_9;
  }
  if ( *((_WORD *)v9 + 7) > 0x16u )
  {
    v71 = (unsigned int)v9[2];
    if ( ((v71 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= 0xF4 )
    {
      v72 = **((_QWORD **)v7 + 2);
      v73 = ((_DWORD)v71 + 3) & 0xFFFFFFFC;
      v9[2] = v73;
      if ( *((_WORD *)v9 + 96) )
        *((_WORD *)v9 + 6) |= 1u;
      v9[48] = 524294;
      v70 = 0;
      v9[49] = v73;
      *(_QWORD *)((char *)v9 + v73) = v72;
      v9[2] += 8;
    }
    else
    {
      v70 = -1073741789;
    }
  }
  else
  {
    v70 = -1073741811;
  }
  v74 = RtlNtStatusToDosError(v70);
  v11 = v74;
  if ( v74 > 0 )
    v11 = (unsigned __int16)v74 | 0x80070000;
  if ( v11 <= -1 )
  {
    v12 = L"SetCldDsMsgSyncRootFileId Failed";
    goto LABEL_9;
  }
  if ( *((_WORD *)v9 + 7) > 5u )
  {
    v76 = (unsigned int)v9[2];
    if ( ((v76 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xF4 )
    {
      v77 = ((_DWORD)v76 + 3) & 0xFFFFFFFC;
      v9[2] = v77;
      if ( *((_WORD *)v9 + 28) )
        *((_WORD *)v9 + 6) |= 1u;
      v13 = a4;
      v75 = 0;
      v9[14] = 262154;
      v9[15] = v77;
      *(_DWORD *)((char *)v9 + v77) = a4;
      v9[2] += 4;
      goto LABEL_169;
    }
    v75 = -1073741789;
  }
  else
  {
    v75 = -1073741811;
  }
  v13 = a4;
LABEL_169:
  v78 = RtlNtStatusToDosError(v75);
  v11 = v78;
  if ( v78 > 0 )
    v11 = (unsigned __int16)v78 | 0x80070000;
  if ( v11 > -1 )
  {
    if ( *((_WORD *)v9 + 7) > 0xDu )
    {
      v80 = (unsigned int)v9[2];
      if ( ((v80 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xF4 )
      {
        v81 = ((_DWORD)v80 + 3) & 0xFFFFFFFC;
        v9[2] = v81;
        if ( *((_WORD *)v9 + 60) )
          *((_WORD *)v9 + 6) |= 1u;
        v9[30] = 262154;
        v79 = 0;
        v9[31] = v81;
        *(_DWORD *)((char *)v9 + v81) = v8;
        v9[2] += 4;
      }
      else
      {
        v79 = -1073741789;
      }
    }
    else
    {
      v79 = -1073741811;
    }
    v82 = RtlNtStatusToDosError(v79);
    v11 = v82;
    if ( v82 > 0 )
      v11 = (unsigned __int16)v82 | 0x80070000;
    if ( v11 > -1 )
    {
      if ( *((_WORD *)v9 + 7) > 0xEu )
      {
        v83 = (unsigned int)v9[2];
        if ( ((v83 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 4 <= 0xF4 )
        {
          v84 = ((_DWORD)v83 + 3) & 0xFFFFFFFC;
          v9[2] = v84;
          if ( *((_WORD *)v9 + 64) )
            *((_WORD *)v9 + 6) |= 1u;
          v9[32] = 262154;
          v51 = 0;
          v9[33] = v84;
          *(_DWORD *)((char *)v9 + v84) = 0;
          v9[2] += 4;
        }
        else
        {
          v51 = -1073741789;
        }
      }
      v85 = RtlNtStatusToDosError(v51);
      v11 = v85;
      if ( v85 > 0 )
        v11 = (unsigned __int16)v85 | 0x80070000;
      if ( v11 > -1 )
      {
        v9[1] = 0;
        *((_WORD *)v9 + 6) &= ~2u;
        v11 = FilterSendMessage(hPort, v9, 0xF4u, 0, 0, &BytesReturned);
        if ( v11 > -1 )
        {
          v12 = 0;
          v106 = v7;
          *v98 = v7;
          v86 = (__int64 *)*((_QWORD *)v7 + 2);
          v7 = 0;
          v104 = *v86;
        }
        else
        {
          v12 = L"FilterSendMessage Failed";
        }
      }
      else
      {
        v12 = L"SetCldDsMsgGlobalCallbackFlags Failed";
      }
    }
    else
    {
      v12 = L"SetCldDsMsgCallbackFlags Failed";
    }
  }
  else
  {
    v12 = L"SetCldDsMsgFlags Failed";
  }
LABEL_197:
  v103 = v12;
  v105 = v13;
  v107 = v8;
  TlmLogApiReliability(11, 0, (_DWORD)a1, (_DWORD)v96, (__int64)v95, UnbiasedTime, (__int64)v102, v11);
  if ( v9 )
  {
    v87 = GetProcessHeap();
    HeapFree(v87, 0, v9);
  }
  if ( v7 )
    CfpFreeSyncRoot(v7);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180004dd0  mov     [rsp-8+arg_10], rbx
0x180004dd5  push    rbp
0x180004dd6  push    rsi
0x180004dd7  push    rdi
0x180004dd8  push    r12
0x180004dda  push    r13
0x180004ddc  push    r14
0x180004dde  push    r15
0x180004de0  lea     rbp, [rsp-490h]
0x180004de8  sub     rsp, 590h
0x180004def  mov     rax, cs:__security_cookie
0x180004df6  xor     rax, rsp
0x180004df9  mov     [rbp+4C0h+var_40], rax
0x180004e00  mov     r15, [rbp+4C0h+arg_20]
0x180004e07  xor     r13d, r13d
0x180004e0a  xorps   xmm0, xmm0
0x180004e0d  mov     [rbp+4C0h+var_520], r8
0x180004e11  mov     r12, rdx
0x180004e14  mov     [rsp+5C0h+lpszFileName], rcx
0x180004e19  mov     rbx, rcx
0x180004e1c  mov     [rsp+5C0h+var_560], r9d
0x180004e21  xorps   xmm1, xmm1
0x180004e24  mov     [rbp+4C0h+var_518], r15
0x180004e28  movups  xmmword ptr [rbp+4C0h+ObjectAttributes.ObjectName], xmm0
0x180004e2c  lea     r8d, [r13+58h]; Size
0x180004e30  mov     [rsp+5C0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180004e39  xor     eax, eax
0x180004e3b  mov     [rsp+5C0h+BytesReturned], r13d
0x180004e40  xor     edx, edx; Val
0x180004e42  mov     [rbp+4C0h+UnbiasedTime], r13
0x180004e46  lea     rcx, [rbp+4C0h+var_4C0]; void *
0x180004e4a  mov     [rbp+4C0h+var_528], r13
0x180004e4e  mov     r14d, r13d
0x180004e51  mov     [rbp+4C0h+var_530], r13
0x180004e55  movups  xmmword ptr [rbp+4C0h+ObjectAttributes.Length], xmm0
0x180004e59  mov     esi, r13d
0x180004e5c  mov     edi, r13d
0x180004e5f  movups  xmmword ptr [rbp+4C0h+ObjectAttributes+1Ch], xmm0
0x180004e63  mov     [rbp+4C0h+Buffer], r13
0x180004e67  movups  xmmword ptr [rbp+4C0h+IoStatusBlock], xmm0
0x180004e6b  movups  xmmword ptr [rbp+4C0h+DestinationString.Length], xmm1
0x180004e6f  call    memset_0
0x180004e74  lea     rcx, [rbp+4C0h+UnbiasedTime]; UnbiasedTime
0x180004e78  call    cs:__imp_QueryUnbiasedInterruptTime
0x180004e7f  nop     dword ptr [rax+rax+00h]
0x180004e84  test    rbx, rbx
0x180004e87  jz      short loc_180004E96
0x180004e89  test    r12, r12
0x180004e8c  jz      short loc_180004E96
0x180004e8e  mov     ebx, r13d
0x180004e91  test    r15, r15
0x180004e94  jnz     short loc_180004E9B
0x180004e96  mov     ebx, 57h ; 'W'
0x180004e9b  mov     eax, ebx
0x180004e9d  or      eax, 80070000h
0x180004ea2  test    ebx, ebx
0x180004ea4  cmovnz  ebx, eax
0x180004ea7  cmp     ebx, 0FFFFFFFFh
0x180004eaa  jg      short loc_180004EBD
0x180004eac  lea     rdx, aInvalidParamet; "Invalid Parameter"
0x180004eb3  mov     r12d, [rsp+5C0h+var_560]
0x180004eb8  jmp     loc_180005A62
0x180004ebd  mov     cl, 1
0x180004ebf  call    GlobalPortInit
0x180004ec4  mov     ebx, eax
0x180004ec6  cmp     eax, 0FFFFFFFFh
0x180004ec9  jg      short loc_180004ED4
0x180004ecb  lea     rdx, aGlobalportinit; "GlobalPortInit Failed"
0x180004ed2  jmp     short loc_180004EB3
0x180004ed4  mov     r15, [rsp+5C0h+lpszFileName]
0x180004ed9  mov     rcx, r15
0x180004edc  call    AttachFilterToVolume
0x180004ee1  mov     ebx, eax
0x180004ee3  cmp     eax, 0FFFFFFFFh
0x180004ee6  jg      short loc_180004EF1
0x180004ee8  lea     rdx, aAttachfilterto; "AttachFilterToVolume Failed"
0x180004eef  jmp     short loc_180004EB3
0x180004ef1  call    cs:__imp_GetProcessHeap
0x180004ef8  nop     dword ptr [rax+rax+00h]
0x180004efd  mov     edx, 8; dwFlags
0x180004f02  mov     r8d, 120h; dwBytes
0x180004f08  mov     rcx, rax; hHeap
0x180004f0b  call    cs:__imp_HeapAlloc
0x180004f12  nop     dword ptr [rax+rax+00h]
0x180004f17  mov     r14, rax
0x180004f1a  neg     rax
0x180004f1d  sbb     ebx, ebx
0x180004f1f  not     ebx
0x180004f21  and     ebx, 8
0x180004f24  mov     eax, ebx
0x180004f26  or      eax, 80070000h
0x180004f2b  test    r14, r14
0x180004f2e  cmovz   ebx, eax
0x180004f31  cmp     ebx, 0FFFFFFFFh
0x180004f34  jg      short loc_180004F42
0x180004f36  lea     rdx, aNewsyncrootdat; "newSyncRootData memory allocation Faile"...
0x180004f3d  jmp     loc_180004EB3
0x180004f42  lea     rcx, [r14+90h]
0x180004f49  call    cs:__imp_RtlInitializeSRWLock
0x180004f50  nop     dword ptr [rax+rax+00h]
0x180004f55  lea     rax, [r14+98h]
0x180004f5c  lea     rcx, [r14+0A8h]
0x180004f63  mov     [rax+8], rax
0x180004f67  mov     [rax], rax
0x180004f6a  call    cs:__imp_RtlInitializeSRWLock
0x180004f71  nop     dword ptr [rax+rax+00h]
0x180004f76  lea     rax, [rsp+5C0h+hObject]
0x180004f7b  mov     qword ptr [r14], 1
0x180004f82  mov     qword ptr [rsp+5C0h+CreateDisposition], rax
0x180004f87  mov     r9d, 7
0x180004f8d  xor     r8d, r8d
0x180004f90  mov     [rsp+5C0h+FileAttributes], 21h ; '!'
0x180004f98  mov     rcx, r15
0x180004f9b  call    CfpCreateFile
0x180004fa0  mov     ecx, eax; Status
0x180004fa2  call    cs:__imp_RtlNtStatusToDosError
0x180004fa9  nop     dword ptr [rax+rax+00h]
0x180004fae  mov     ebx, eax
0x180004fb0  test    eax, eax
0x180004fb2  jle     short loc_180004FBD
0x180004fb4  movzx   ebx, ax
0x180004fb7  or      ebx, 80070000h
0x180004fbd  cmp     ebx, 0FFFFFFFFh
0x180004fc0  jg      short loc_180004FCE
0x180004fc2  lea     rdx, aCfpcreatefileF; "CfpCreateFile Failed"
0x180004fc9  jmp     loc_180004EB3
0x180004fce  mov     r15, r13
0x180004fd1  mov     [rsp+5C0h+var_55C], r13d
0x180004fd6  test    r15, r15
0x180004fd9  jnz     short loc_180004FE3
0x180004fdb  mov     r13d, 420h
0x180004fe1  jmp     short loc_180005011
0x180004fe3  mov     r13d, [r15+41Ch]
0x180004fea  add     r13d, 420h
0x180004ff1  call    cs:__imp_GetProcessHeap
0x180004ff8  nop     dword ptr [rax+rax+00h]
0x180004ffd  mov     r8, r15; lpMem
0x180005000  xor     edx, edx; dwFlags
0x180005002  mov     rcx, rax; hHeap
0x180005005  call    cs:__imp_HeapFree
0x18000500c  nop     dword ptr [rax+rax+00h]
0x180005011  call    cs:__imp_GetProcessHeap
0x180005018  nop     dword ptr [rax+rax+00h]
0x18000501d  mov     r8d, r13d; dwBytes
0x180005020  xor     edx, edx; dwFlags
0x180005022  mov     rcx, rax; hHeap
0x180005025  call    cs:__imp_HeapAlloc
0x18000502c  nop     dword ptr [rax+rax+00h]
0x180005031  mov     r15, rax
0x180005034  neg     rax
0x180005037  sbb     ebx, ebx
0x180005039  not     ebx
0x18000503b  and     ebx, 8
0x18000503e  mov     eax, ebx
0x180005040  or      eax, 80070000h
0x180005045  test    r15, r15
0x180005048  cmovz   ebx, eax
0x18000504b  test    ebx, ebx
0x18000504d  jz      short loc_180005051
0x18000504f  js      short loc_18000508D
0x180005051  mov     rcx, [rsp+5C0h+hObject]; hFile
0x180005056  mov     r9d, r13d
0x180005059  mov     r13d, 1
0x18000505f  mov     [rsp+5C0h+AllocationSize], rsi; __int64
0x180005064  mov     edx, r13d
0x180005067  mov     r8, r15
0x18000506a  call    CfpGetSyncRootInfoByHandle
0x18000506f  mov     ebx, eax
0x180005071  cmp     eax, 800700EAh
0x180005076  jnz     short loc_180005099
0x180005078  mov     eax, [rsp+5C0h+var_55C]
0x18000507c  add     eax, r13d
0x18000507f  mov     [rsp+5C0h+var_55C], eax
0x180005083  cmp     eax, 2
0x180005086  jge     short loc_18000509E
0x180005088  jmp     loc_180004FD6
0x18000508d  lea     rdx, aSyncrootstdinf; "syncRootStdInfo memory allocation Faile"...
0x180005094  jmp     loc_180004EB3
0x180005099  cmp     eax, 0FFFFFFFFh
0x18000509c  jg      short loc_1800050AA
0x18000509e  lea     rdx, aCfpgetsyncroot; "CfpGetSyncRootInfoByHandle Failed"
0x1800050a5  jmp     loc_180004EB3
0x1800050aa  lea     rax, [r15+1Ch]
0x1800050ae  mov     [r14+10h], r15
0x1800050b2  mov     [rbp+4C0h+var_528], rax
0x1800050b6  xor     r13d, r13d
0x1800050b9  lea     rax, [r15+21Ch]
0x1800050c0  mov     [rbp+4C0h+var_530], rax
0x1800050c4  jmp     short loc_180005104
0x1800050c6  movsxd  rdx, eax
0x1800050c9  mov     rcx, [r14+rdx*8+0B0h]
0x1800050d1  mov     rax, rcx
0x1800050d4  neg     rax
0x1800050d7  sbb     ebx, ebx
0x1800050d9  and     ebx, 57h
0x1800050dc  mov     eax, ebx
0x1800050de  or      eax, 80070000h
0x1800050e3  test    rcx, rcx
0x1800050e6  cmovnz  ebx, eax
0x1800050e9  test    ebx, ebx
0x1800050eb  jz      short loc_1800050F3
0x1800050ed  js      loc_1800051CD
0x1800050f3  mov     rax, [r12+8]
0x1800050f8  add     r12, 10h
0x1800050fc  mov     [r14+rdx*8+0B0h], rax
0x180005104  mov     eax, [r12]
0x180005108  cmp     eax, 0FFFFFFFFh
0x18000510b  jnz     short loc_1800050C6
0x18000510d  mov     rax, [rbp+4C0h+var_520]
0x180005111  lea     rdx, SourceString; SourceString
0x180005118  lea     rcx, [rbp+4C0h+DestinationString]; DestinationString
0x18000511c  mov     [r14+118h], rax
0x180005123  call    cs:__imp_RtlInitUnicodeString
0x18000512a  nop     dword ptr [rax+rax+00h]
0x18000512f  mov     rax, [rsp+5C0h+hObject]
0x180005134  lea     r12, [r14+8]
0x180005138  mov     [rsp+5C0h+EaLength], r13d; EaLength
0x18000513d  lea     r9, [rbp+4C0h+IoStatusBlock]; IoStatusBlock
0x180005141  mov     [rsp+5C0h+EaBuffer], r13; EaBuffer
0x180005146  lea     r8, [rbp+4C0h+ObjectAttributes]; ObjectAttributes
0x18000514a  mov     [rbp+4C0h+ObjectAttributes.RootDirectory], rax
0x18000514e  xorps   xmm0, xmm0
0x180005151  lea     rax, [rbp+4C0h+DestinationString]
0x180005155  mov     [rbp+4C0h+ObjectAttributes.Length], 30h ; '0'
0x18000515c  mov     [rbp+4C0h+ObjectAttributes.ObjectName], rax
0x180005160  mov     edx, 100000h; DesiredAccess
0x180005165  mov     eax, 1
0x18000516a  mov     [rbp+4C0h+ObjectAttributes.Attributes], 40h ; '@'
0x180005171  mov     [rsp+5C0h+CreateOptions], eax; CreateOptions
0x180005175  mov     rcx, r12; FileHandle
0x180005178  mov     [rsp+5C0h+CreateDisposition], eax; CreateDisposition
0x18000517c  mov     [rsp+5C0h+ShareAccess], 7; ShareAccess
0x180005184  mov     [rsp+5C0h+FileAttributes], r13d; FileAttributes
0x180005189  mov     [rsp+5C0h+AllocationSize], r13; AllocationSize
0x18000518e  movdqu  xmmword ptr [rbp+4C0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180005193  call    cs:__imp_NtCreateFile
0x18000519a  nop     dword ptr [rax+rax+00h]
0x18000519f  mov     ecx, eax; Status
0x1800051a1  call    cs:__imp_RtlNtStatusToDosError
0x1800051a8  nop     dword ptr [rax+rax+00h]
0x1800051ad  mov     ebx, eax
0x1800051af  test    eax, eax
0x1800051b1  jle     short loc_1800051BC
0x1800051b3  movzx   ebx, ax
0x1800051b6  or      ebx, 80070000h
0x1800051bc  cmp     ebx, 0FFFFFFFFh
0x1800051bf  jg      short loc_1800051D9
0x1800051c1  lea     rdx, aNtcreatefileFa; "NtCreateFile Failed"
0x1800051c8  jmp     loc_180004EB3
0x1800051cd  lea     rdx, aCallbacktableE; "CallbackTable entry is NULL"
0x1800051d4  jmp     loc_180004EB3
0x1800051d9  mov     rcx, [rsp+5C0h+lpszFileName]; lpszFileName
0x1800051de  test    rcx, rcx
0x1800051e1  jz      loc_1800052BD
0x1800051e7  lea     rbx, [r14+28h]
0x1800051eb  test    rbx, rbx
0x1800051ee  jz      loc_1800052BD
0x1800051f4  mov     r8d, 104h; cchBufferLength
0x1800051fa  mov     [rbx], r13w
0x1800051fe  lea     rdx, [rbp+4C0h+szVolumePathName]; lpszVolumePathName
0x180005205  call    cs:__imp_GetVolumePathNameW
0x18000520c  nop     dword ptr [rax+rax+00h]
0x180005211  test    eax, eax
0x180005213  jz      loc_1800052CE
0x180005219  mov     r15d, 32h ; '2'
0x18000521f  lea     rcx, [rbp+4C0h+szVolumePathName]; lpszVolumeMountPoint
0x180005226  mov     r8d, r15d; cchBufferLength
0x180005229  mov     rdx, rbx; lpszVolumeName
0x18000522c  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180005233  nop     dword ptr [rax+rax+00h]
0x180005238  test    eax, eax
0x18000523a  jnz     short loc_18000529C
0x18000523c  call    cs:__imp_GetLastError
0x180005243  nop     dword ptr [rax+rax+00h]
0x180005248  cmp     eax, 1126h
0x18000524d  jnz     short loc_1800052CE
0x18000524f  mov     ecx, 7FFFFFFEh
0x180005254  lea     rdx, [rbp+4C0h+szVolumePathName]
0x18000525b  mov     rax, rbx
0x18000525e  lea     r12d, [r15-30h]
0x180005262  test    rcx, rcx
0x180005265  jz      short loc_180005289
0x180005267  movzx   r8d, word ptr [rdx]
0x18000526b  test    r8w, r8w
0x18000526f  jz      short loc_180005289
0x180005271  mov     [rax], r8w
0x180005275  add     rdx, r12
0x180005278  mov     r8d, 1
0x18000527e  add     rax, r12
0x180005281  sub     rcx, r8
0x180005284  sub     r15, r8
0x180005287  jnz     short loc_180005262
0x180005289  test    r15, r15
0x18000528c  lea     rcx, [rax-2]
0x180005290  lea     r12, [r14+8]
0x180005294  cmovnz  rcx, rax
0x180005298  mov     [rcx], r13w
0x18000529c  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800052a0  inc     rcx
0x1800052a3  cmp     [rbx+rcx*2], r13w
  ... truncated ...
```
