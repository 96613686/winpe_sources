# PuCleanDisk(PU_CLEAN_DISK_PARAMETERS *,void (*)(void *,ushort))

- ea: `0x1801973a0`
- end: `0x180197a50`
- name: `?PuCleanDisk@@YAJPEAUPU_CLEAN_DISK_PARAMETERS@@P6AXPEAXG@Z@Z`
- size: `1712`
- prototype: `__int64 __fastcall(struct PU_CLEAN_DISK_PARAMETERS *, void (*)(void *, unsigned __int16))`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1801105e0`

## callees

- `0x180006290`
- `0x180007141`
- `0x18000d49c`
- `0x180195a90`
- `0x1801973a0`
- `0x180198120`
- `0x180199db0`
- `0x18019a5ec`
- `0x18019a690`
- `0x18019a73c`
- `0x18019a808`
- `0x18019a9b4`
- `0x18019c540`
- `0x1801a0df0`
- `0x1801a401c`
- `0x1801a4388`
- `0x1801a45b8`
- `0x1801a472c`
- `0x1801a4bf0`
- `0x1801a54bc`
- `0x1801a54e4`
- `0x1801a59f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801978f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019793e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019799b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197543`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197621`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197717`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197727`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180197780`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801978f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019793e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019799b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801978a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180197938`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801978a6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180197938`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197a15`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180197a15`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801977f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197a02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1801977f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180197a02`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180197813`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180197813`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180197401`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019764e`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180197401`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019764e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180197a28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180197a28`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019770d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180197776`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801978e8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019798d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019770d`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x180197776`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x1801978e8`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019798d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019760e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019760e`

## string_xrefs

- `0x18019763e`: `CreateFile`
- `0x180197799`: `PuUpdateDisk`
- `0x180197740`: `PuDeleteDriveLayout`
- `0x18019746c`: `Disk is read only`
- `0x1801977d0`: `DeleteBands`

## pseudocode

```c
__int64 __fastcall PuCleanDisk(struct PU_CLEAN_DISK_PARAMETERS *a1, void (*a2)(void *, unsigned __int16))
{
  DWORD v2; // eax
  struct PU_CLEAN_DISK_PARAMETERS *v3; // r12
  __int64 v4; // rsi
  __int64 FileW; // r13
  const WCHAR *v6; // r14
  int v7; // ebx
  int v8; // edi
  int v9; // r15d
  signed int v10; // ebx
  const char *v11; // rdi
  signed int LastError; // eax
  __int64 v13; // r8
  BOOL v14; // r12d
  _QWORD *v15; // rax
  signed int v16; // eax
  int v17; // ecx
  DWORD v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  DWORD v21; // r15d
  HANDLE ProcessHeap; // rax
  void *v23; // r14
  DWORD v24; // ecx
  int v25; // eax
  __int64 v26; // rax
  signed int v27; // eax
  DWORD v28; // eax
  signed int v29; // eax
  signed int v30; // eax
  void *v31; // rdi
  HANDLE v32; // rax
  void (*dwFlagsAndAttributes)(void *, unsigned __int16); // [rsp+28h] [rbp-B1h]
  DWORD v35; // [rsp+40h] [rbp-99h] BYREF
  struct PU_CLEAN_DISK_PARAMETERS *v36; // [rsp+48h] [rbp-91h] BYREF
  DWORD BytesReturned; // [rsp+50h] [rbp-89h] BYREF
  LPVOID lpMem; // [rsp+58h] [rbp-81h]
  LARGE_INTEGER PerformanceCount; // [rsp+60h] [rbp-79h] BYREF
  LARGE_INTEGER v40; // [rsp+68h] [rbp-71h] BYREF
  __int64 v41; // [rsp+70h] [rbp-69h]
  _QWORD Buf2[2]; // [rsp+80h] [rbp-59h] BYREF
  _BYTE Buf1[16]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v44[16]; // [rsp+A0h] [rbp-39h] BYREF
  const char *v45; // [rsp+B0h] [rbp-29h]
  __int64 v46; // [rsp+B8h] [rbp-21h]
  DWORD *v47; // [rsp+C0h] [rbp-19h]
  __int64 v48; // [rsp+C8h] [rbp-11h]
  struct PU_CLEAN_DISK_PARAMETERS **v49; // [rsp+D0h] [rbp-9h]
  __int64 v50; // [rsp+D8h] [rbp-1h]

  v2 = *((_DWORD *)a1 + 6);
  v3 = a1;
  v4 = *((_QWORD *)a1 + 1);
  FileW = -1;
  v6 = *(const WCHAR **)a1;
  v7 = *((_DWORD *)a1 + 5);
  v8 = *((_DWORD *)a1 + 4);
  v9 = *((_DWORD *)a1 + 12);
  v36 = a1;
  v35 = v2;
  lpMem = 0;
  PU_TIMER::PU_TIMER((PU_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( !*(_DWORD *)(v4 + 324) )
  {
    v10 = -2147220987;
    v11 = "Media is not present";
    goto LABEL_43;
  }
  if ( !*(_DWORD *)(v4 + 320) && *(_DWORD *)(v4 + 220) == 2 )
  {
    v10 = -2147220989;
    v11 = "Disk is not initialized";
    goto LABEL_43;
  }
  if ( *(_DWORD *)(v4 + 264) )
  {
    v10 = -2147220988;
    v11 = "Disk is offline";
    goto LABEL_43;
  }
  if ( *(_DWORD *)(v4 + 272) )
  {
    v10 = -2147220986;
    v11 = "Disk is read only";
    goto LABEL_43;
  }
  if ( !v7 && (unsigned int)PuDiskContainsOemPartition((struct PU_DISK_PROPERTIES *)v4) )
  {
    v10 = -2147220969;
    v11 = "Disk contains an OEM partition";
    goto LABEL_43;
  }
  if ( v8 )
  {
    v11 = 0;
  }
  else
  {
    v11 = 0;
    if ( (unsigned int)PuDiskContainsDataPartition((struct PU_DISK_PROPERTIES *)v4) )
    {
      v10 = -2147220968;
      v11 = "Disk has one more or data partitions";
      goto LABEL_43;
    }
    if ( (unsigned int)PuDiskContainsEspPartition((struct PU_DISK_PROPERTIES *)v4) )
    {
      v10 = -2147220967;
      v11 = "Disk has an ESP partition";
      goto LABEL_43;
    }
  }
  if ( !*(_DWORD *)(v4 + 276)
    && !*(_DWORD *)(v4 + 280)
    && !*(_DWORD *)(v4 + 284)
    && !*(_DWORD *)(v4 + 288)
    && !*(_DWORD *)(v4 + 304) )
  {
    v10 = PuValidateOperation(*(_QWORD *)v3, 1);
    if ( v10 < 0 )
    {
      v11 = "PuValidateOperation";
      goto LABEL_43;
    }
    if ( !(unsigned int)PuGetDeviceNamesForRegions((struct PU_DISK_PROPERTIES *)v4) )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      if ( v10 < 0 )
      {
        v11 = "PuGetDeviceNamesForRegions";
        goto LABEL_43;
      }
    }
    if ( (unsigned int)PuDiskBacksBootPartition((struct PU_DISK_PROPERTIES *)v4) )
    {
      v10 = -2147220967;
      v11 = "Disk has a boot volume";
      goto LABEL_43;
    }
    PuDeleteAccessPathsForRegions((struct PU_DISK_PROPERTIES *)v4);
    PuDismountRegions((struct PU_DISK_PROPERTIES *)v4);
    CRtlList::Begin(v4 + 336, Buf1);
    v14 = *(_DWORD *)(v4 + 320)
       && (v15 = *(_QWORD **)(v13 + 8), Buf2[1] = v13, Buf2[0] = *v15, memcmp_0(Buf1, Buf2, 0x10u))
       && *((_QWORD *)CRtlListIter::GetEntryPointer((CRtlListIter *)Buf1) + 1) == 0;
    FileW = (__int64)CreateFileW(v6, 0xC0000000, 3u, 0, 3u, 0, 0);
    if ( FileW == -1 )
    {
      v16 = GetLastError();
      v10 = v16;
      if ( v16 > 0 )
        v10 = (unsigned __int16)v16 | 0x80070000;
      if ( v10 < 0 )
      {
        v11 = "CreateFile";
LABEL_42:
        v3 = v36;
        goto LABEL_43;
      }
    }
    BytesReturned = 0;
    if ( !DeviceIoControl((HANDLE)FileW, 0x7C100u, 0, 0, 0, 0, &BytesReturned, 0) )
    {
      v18 = GetLastError();
      if ( !v14 || v18 != 31 )
      {
        v19 = GetLastError();
        v10 = v19;
        if ( v19 > 0 )
          v10 = (unsigned __int16)v19 | 0x80070000;
        if ( v10 < 0 )
        {
          v11 = "PuDeleteDriveLayout";
          goto LABEL_42;
        }
      }
    }
    BytesReturned = 0;
    if ( !DeviceIoControl((HANDLE)FileW, 0x70140u, 0, 0, 0, 0, &BytesReturned, 0) )
    {
      v20 = GetLastError();
      v10 = v20;
      if ( v20 > 0 )
        v10 = (unsigned __int16)v20 | 0x80070000;
      if ( v10 < 0 )
      {
        v11 = "PuUpdateDisk";
        goto LABEL_42;
      }
    }
    if ( *(_DWORD *)(v4 + 316) )
    {
      if ( (unsigned int)PuPerformBandManagement((struct PU_DISK_PROPERTIES *)v4) )
      {
        v10 = DeleteBands(v6, 0, *(_QWORD *)(v4 + 136));
        if ( v10 < 0 )
        {
          v11 = "DeleteBands";
          goto LABEL_42;
        }
      }
    }
    if ( v9 )
    {
      v35 = 0;
      v25 = DeviceIoControl((HANDLE)FileW, 0x2D9640u, 0, 0, 0, 0, &v35, 0);
LABEL_79:
      if ( !v25 )
      {
        v27 = GetLastError();
        v10 = v27;
        if ( v27 > 0 )
          v10 = (unsigned __int16)v27 | 0x80070000;
      }
    }
    else
    {
      v21 = 0x100000;
      do
      {
        if ( v21 < 0x200 )
        {
          SetLastError(8u);
          goto LABEL_82;
        }
        ProcessHeap = GetProcessHeap();
        if ( ProcessHeap )
          v23 = HeapAlloc(ProcessHeap, 8u, v21);
        else
          v23 = 0;
        v24 = v21 >> 1;
        if ( v23 )
          v24 = v21;
        v21 = v24;
      }
      while ( !v23 );
      lpMem = v23;
      if ( v35 )
      {
        v25 = PuZeroEntireDisk(
                (HANDLE)FileW,
                (struct PU_DISK_PROPERTIES *)v4,
                (unsigned __int8 *)v23,
                v24,
                (void **)v36,
                dwFlagsAndAttributes);
        goto LABEL_79;
      }
      PuZeroFirstOrLastOneMB((HANDLE)FileW, (struct PU_DISK_PROPERTIES *)v4, 1, (unsigned __int8 *)v23, v24);
      v26 = *(_QWORD *)(v4 + 32) - *(_QWORD *)&GUID_DEVCLASS_SMRDISK.Data1;
      if ( !v26 )
        v26 = *(_QWORD *)(v4 + 40) - *(_QWORD *)GUID_DEVCLASS_SMRDISK.Data4;
      if ( v26 )
        PuZeroFirstOrLastOneMB((HANDLE)FileW, (struct PU_DISK_PROPERTIES *)v4, 0, (unsigned __int8 *)v23, v21);
    }
LABEL_82:
    if ( *(_DWORD *)(v4 + 320) && !v14 )
    {
      if ( !(unsigned int)PuCreateDisk((HANDLE)FileW, (enum _PARTITION_STYLE)*(_DWORD *)(v4 + 220)) )
        goto LABEL_87;
      v28 = PuWriteBootCode((HANDLE)FileW, (struct PU_DISK_PROPERTIES *)v4);
      if ( v28 )
      {
        SetLastError(v28);
LABEL_87:
        v29 = GetLastError();
        v10 = v29;
        if ( v29 > 0 )
          v10 = (unsigned __int16)v29 | 0x80070000;
      }
    }
    v35 = 0;
    if ( !DeviceIoControl((HANDLE)FileW, 0x70140u, 0, 0, 0, 0, &v35, 0) )
    {
      v30 = GetLastError();
      v10 = v30;
      if ( v30 > 0 )
        v10 = (unsigned __int16)v30 | 0x80070000;
    }
    goto LABEL_42;
  }
  v10 = -2147220967;
  v11 = "Disk has a system partition";
LABEL_43:
  QueryPerformanceCounter(&v40);
  if ( v10 < 0 )
  {
    if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 1) != 0 )
      McTemplateU0sqsd_EventWriteTransfer(
        v17,
        (unsigned int)CleanDiskFailed,
        (unsigned int)"PuCleanDisk",
        *(_DWORD *)(v4 + 60),
        (__int64)v11,
        v10);
  }
  else if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 2) != 0 )
  {
    v45 = "PuCleanDisk";
    v46 = 12;
    v48 = 4;
    v36 = (struct PU_CLEAN_DISK_PARAMETERS *)(1000000 * (v40.QuadPart - PerformanceCount.QuadPart) / v41);
    v35 = *(_DWORD *)(v4 + 60);
    v47 = &v35;
    v49 = &v36;
    v50 = 8;
    McGenEventWrite_EventWriteTransfer(PartUtilProvider_Context, CleanDiskSucceeded, "PuCleanDisk", 4, v44);
  }
  v31 = lpMem;
  *((_DWORD *)v3 + 7) = 0;
  if ( v31 )
  {
    v32 = GetProcessHeap();
    if ( v32 )
      HeapFree(v32, 0, v31);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x1801973a0  push    rbp
0x1801973a2  push    rbx
0x1801973a3  push    rsi
0x1801973a4  push    rdi
0x1801973a5  push    r12
0x1801973a7  push    r13
0x1801973a9  push    r14
0x1801973ab  push    r15
0x1801973ad  lea     rbp, [rsp-1Fh]
0x1801973b2  sub     rsp, 0F8h
0x1801973b9  mov     rax, cs:__security_cookie
0x1801973c0  xor     rax, rsp
0x1801973c3  mov     [rbp+57h+var_50], rax
0x1801973c7  mov     eax, [rcx+18h]
0x1801973ca  mov     r12, rcx
0x1801973cd  mov     rsi, [rcx+8]
0x1801973d1  or      r13, 0FFFFFFFFFFFFFFFFh
0x1801973d5  mov     r14, [rcx]
0x1801973d8  mov     ebx, [rcx+14h]
0x1801973db  mov     edi, [rcx+10h]
0x1801973de  mov     r15d, [rcx+30h]
0x1801973e2  mov     [rsp+130h+var_E8], rcx
0x1801973e7  lea     rcx, [rbp+57h+PerformanceCount]; this
0x1801973eb  mov     [rsp+130h+var_F0], eax
0x1801973ef  mov     [rsp+130h+lpMem], 0
0x1801973f8  call    ??0PU_TIMER@@QEAA@XZ; PU_TIMER::PU_TIMER(void)
0x1801973fd  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x180197401  call    cs:__imp_QueryPerformanceCounter
0x180197407  cmp     dword ptr [rsi+144h], 0
0x18019740e  jnz     short loc_180197421
0x180197410  mov     ebx, 80040205h
0x180197415  lea     rdi, aMediaIsNotPres; "Media is not present"
0x18019741c  jmp     loc_18019764A
0x180197421  cmp     dword ptr [rsi+140h], 0
0x180197428  jnz     short loc_180197444
0x18019742a  cmp     dword ptr [rsi+0DCh], 2
0x180197431  jnz     short loc_180197444
0x180197433  mov     ebx, 80040203h
0x180197438  lea     rdi, aDiskIsNotIniti; "Disk is not initialized"
0x18019743f  jmp     loc_18019764A
0x180197444  cmp     dword ptr [rsi+108h], 0
0x18019744b  jz      short loc_18019745E
0x18019744d  mov     ebx, 80040204h
0x180197452  lea     rdi, aDiskIsOffline; "Disk is offline"
0x180197459  jmp     loc_18019764A
0x18019745e  cmp     dword ptr [rsi+110h], 0
0x180197465  jz      short loc_180197478
0x180197467  mov     ebx, 80040206h
0x18019746c  lea     rdi, aDiskIsReadOnly; "Disk is read only"
0x180197473  jmp     loc_18019764A
0x180197478  test    ebx, ebx
0x18019747a  jnz     short loc_180197499
0x18019747c  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019747f  call    ?PuDiskContainsOemPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskContainsOemPartition(PU_DISK_PROPERTIES *)
0x180197484  test    eax, eax
0x180197486  jz      short loc_180197499
0x180197488  mov     ebx, 80040217h
0x18019748d  lea     rdi, aDiskContainsAn; "Disk contains an OEM partition"
0x180197494  jmp     loc_18019764A
0x180197499  test    edi, edi
0x18019749b  jnz     short loc_1801974D9
0x18019749d  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x1801974a0  call    ?PuDiskContainsDataPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskContainsDataPartition(PU_DISK_PROPERTIES *)
0x1801974a5  xor     edi, edi
0x1801974a7  test    eax, eax
0x1801974a9  jz      short loc_1801974BC
0x1801974ab  mov     ebx, 80040218h
0x1801974b0  lea     rdi, aDiskHasOneMore; "Disk has one more or data partitions"
0x1801974b7  jmp     loc_18019764A
0x1801974bc  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x1801974bf  call    ?PuDiskContainsEspPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskContainsEspPartition(PU_DISK_PROPERTIES *)
0x1801974c4  test    eax, eax
0x1801974c6  jz      short loc_1801974DB
0x1801974c8  mov     ebx, 80040219h
0x1801974cd  lea     rdi, aDiskHasAnEspPa; "Disk has an ESP partition"
0x1801974d4  jmp     loc_18019764A
0x1801974d9  xor     edi, edi
0x1801974db  cmp     [rsi+114h], edi
0x1801974e1  jnz     loc_1801979B9
0x1801974e7  cmp     [rsi+118h], edi
0x1801974ed  jnz     loc_1801979B9
0x1801974f3  cmp     [rsi+11Ch], edi
0x1801974f9  jnz     loc_1801979B9
0x1801974ff  cmp     [rsi+120h], edi
0x180197505  jnz     loc_1801979B9
0x18019750b  cmp     [rsi+130h], edi
0x180197511  jnz     loc_1801979B9
0x180197517  mov     rcx, [r12]
0x18019751b  mov     edx, 1
0x180197520  call    ?PuValidateOperation@@YAJPEBGW4PM_OPERATION@@@Z; PuValidateOperation(ushort const *,PM_OPERATION)
0x180197525  mov     ebx, eax
0x180197527  test    eax, eax
0x180197529  jns     short loc_180197537
0x18019752b  lea     rdi, aPuvalidateoper; "PuValidateOperation"
0x180197532  jmp     loc_18019764A
0x180197537  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019753a  call    ?PuGetDeviceNamesForRegions@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuGetDeviceNamesForRegions(PU_DISK_PROPERTIES *)
0x18019753f  test    eax, eax
0x180197541  jnz     short loc_180197568
0x180197543  call    cs:__imp_GetLastError
0x180197549  mov     ebx, eax
0x18019754b  test    eax, eax
0x18019754d  jle     short loc_180197558
0x18019754f  movzx   ebx, ax
0x180197552  or      ebx, 80070000h
0x180197558  test    ebx, ebx
0x18019755a  jns     short loc_180197568
0x18019755c  lea     rdi, aPugetdevicenam; "PuGetDeviceNamesForRegions"
0x180197563  jmp     loc_18019764A
0x180197568  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019756b  call    ?PuDiskBacksBootPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskBacksBootPartition(PU_DISK_PROPERTIES *)
0x180197570  test    eax, eax
0x180197572  jz      short loc_180197585
0x180197574  mov     ebx, 80040219h
0x180197579  lea     rdi, aDiskHasABootVo; "Disk has a boot volume"
0x180197580  jmp     loc_18019764A
0x180197585  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x180197588  call    ?PuDeleteAccessPathsForRegions@@YAXPEAVPU_DISK_PROPERTIES@@@Z; PuDeleteAccessPathsForRegions(PU_DISK_PROPERTIES *)
0x18019758d  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x180197590  call    ?PuDismountRegions@@YAXPEAVPU_DISK_PROPERTIES@@@Z; PuDismountRegions(PU_DISK_PROPERTIES *)
0x180197595  lea     r8, [rsi+150h]
0x18019759c  mov     rcx, r8
0x18019759f  lea     rdx, [rbp+57h+Buf1]
0x1801975a3  call    ?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x1801975a8  cmp     [rsi+140h], edi
0x1801975ae  jnz     short loc_1801975B5
0x1801975b0  mov     r12d, edi
0x1801975b3  jmp     short loc_1801975EF
0x1801975b5  mov     rax, [r8+8]
0x1801975b9  lea     rdx, [rbp+57h+Buf2]; Buf2
0x1801975bd  mov     [rbp+57h+var_A8], r8
0x1801975c1  mov     r8d, 10h; Size
0x1801975c7  mov     rcx, [rax]
0x1801975ca  mov     [rbp+57h+Buf2], rcx
0x1801975ce  lea     rcx, [rbp+57h+Buf1]; Buf1
0x1801975d2  call    memcmp_0
0x1801975d7  test    eax, eax
0x1801975d9  jz      short loc_1801975B0
0x1801975db  lea     rcx, [rbp+57h+Buf1]; this
0x1801975df  call    ?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x1801975e4  mov     r12d, edi
0x1801975e7  cmp     [rax+8], rdi
0x1801975eb  setz    r12b
0x1801975ef  mov     [rsp+130h+hTemplateFile], rdi; hTemplateFile
0x1801975f4  mov     r8d, 3; dwShareMode
0x1801975fa  mov     dword ptr [rsp+130h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1801975fe  xor     r9d, r9d; lpSecurityAttributes
0x180197601  mov     edx, 0C0000000h; dwDesiredAccess
0x180197606  mov     [rsp+130h+dwCreationDisposition], r8d; dwCreationDisposition
0x18019760b  mov     rcx, r14; lpFileName
0x18019760e  call    cs:__imp_CreateFileW
0x180197614  mov     r13, rax
0x180197617  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019761b  jnz     loc_1801976E3
0x180197621  call    cs:__imp_GetLastError
0x180197627  mov     ebx, eax
0x180197629  test    eax, eax
0x18019762b  jle     short loc_180197636
0x18019762d  movzx   ebx, ax
0x180197630  or      ebx, 80070000h
0x180197636  test    ebx, ebx
0x180197638  jns     loc_1801976E3
0x18019763e  lea     rdi, aCreatefile; "CreateFile"
0x180197645  mov     r12, [rsp+130h+var_E8]
0x18019764a  lea     rcx, [rbp+57h+var_C8]; lpPerformanceCount
0x18019764e  call    cs:__imp_QueryPerformanceCounter
0x180197654  xor     r14d, r14d
0x180197657  test    ebx, ebx
0x180197659  js      loc_1801979CA
0x18019765f  test    cs:Microsoft_Windows_StorageManagement_PartUtilEnableBits, 2
0x180197666  jz      loc_1801979F3
0x18019766c  mov     rax, qword ptr [rbp+57h+var_C8]
0x180197670  lea     r8, aPucleandisk; "PuCleanDisk"
0x180197677  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x18019767b  lea     r9d, [r14+4]
0x18019767f  imul    rax, 0F4240h
0x180197686  lea     rcx, PartUtilProvider_Context
0x18019768d  mov     [rbp+57h+var_80], r8
0x180197691  cqo
0x180197693  mov     [rbp+57h+var_78], 0Ch
0x18019769b  idiv    [rbp+57h+var_C0]
0x18019769f  lea     rdx, CleanDiskSucceeded
0x1801976a6  mov     [rbp+57h+var_68], r9
0x1801976aa  mov     [rsp+130h+var_E8], rax
0x1801976af  mov     eax, [rsi+3Ch]
0x1801976b2  mov     [rsp+130h+var_F0], eax
0x1801976b6  lea     rax, [rsp+130h+var_F0]
0x1801976bb  mov     [rbp+57h+var_70], rax
0x1801976bf  lea     rax, [rsp+130h+var_E8]
0x1801976c4  mov     [rbp+57h+var_60], rax
0x1801976c8  lea     rax, [rbp+57h+var_90]
0x1801976cc  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x1801976d1  mov     [rbp+57h+var_58], 8
0x1801976d9  call    McGenEventWrite_EventWriteTransfer
0x1801976de  jmp     loc_1801979F3
0x1801976e3  mov     [rsp+130h+lpOverlapped], rdi; lpOverlapped
0x1801976e8  lea     rax, [rsp+130h+BytesReturned]
0x1801976ed  mov     [rsp+130h+hTemplateFile], rax; lpBytesReturned
0x1801976f2  xor     r9d, r9d; nInBufferSize
0x1801976f5  mov     dword ptr [rsp+130h+dwFlagsAndAttributes], edi; nOutBufferSize
0x1801976f9  xor     r8d, r8d; lpInBuffer
0x1801976fc  mov     edx, 7C100h; dwIoControlCode
0x180197701  mov     qword ptr [rsp+130h+dwCreationDisposition], rdi; lpOutBuffer
0x180197706  mov     rcx, r13; hDevice
0x180197709  mov     [rsp+130h+BytesReturned], edi
0x18019770d  call    cs:__imp_DeviceIoControl
0x180197713  test    eax, eax
0x180197715  jnz     short loc_18019774C
0x180197717  call    cs:__imp_GetLastError
0x18019771d  test    r12d, r12d
0x180197720  jz      short loc_180197727
0x180197722  cmp     eax, 1Fh
0x180197725  jz      short loc_18019774C
0x180197727  call    cs:__imp_GetLastError
0x18019772d  mov     ebx, eax
0x18019772f  test    eax, eax
0x180197731  jle     short loc_18019773C
0x180197733  movzx   ebx, ax
0x180197736  or      ebx, 80070000h
0x18019773c  test    ebx, ebx
0x18019773e  jns     short loc_18019774C
0x180197740  lea     rdi, aPudeletedrivel; "PuDeleteDriveLayout"
0x180197747  jmp     loc_180197645
0x18019774c  mov     [rsp+130h+lpOverlapped], rdi; lpOverlapped
0x180197751  lea     rax, [rsp+130h+BytesReturned]
0x180197756  mov     [rsp+130h+hTemplateFile], rax; lpBytesReturned
0x18019775b  xor     r9d, r9d; nInBufferSize
0x18019775e  mov     dword ptr [rsp+130h+dwFlagsAndAttributes], edi; void (*)(void *, unsigned __int16)
0x180197762  xor     r8d, r8d; lpInBuffer
0x180197765  mov     edx, 70140h; dwIoControlCode
0x18019776a  mov     qword ptr [rsp+130h+dwCreationDisposition], rdi; lpOutBuffer
0x18019776f  mov     rcx, r13; hDevice
0x180197772  mov     [rsp+130h+BytesReturned], edi
0x180197776  call    cs:__imp_DeviceIoControl
0x18019777c  test    eax, eax
0x18019777e  jnz     short loc_1801977A5
0x180197780  call    cs:__imp_GetLastError
0x180197786  mov     ebx, eax
0x180197788  test    eax, eax
0x18019778a  jle     short loc_180197795
0x18019778c  movzx   ebx, ax
0x18019778f  or      ebx, 80070000h
0x180197795  test    ebx, ebx
0x180197797  jns     short loc_1801977A5
0x180197799  lea     rdi, aPuupdatedisk; "PuUpdateDisk"
0x1801977a0  jmp     loc_180197645
0x1801977a5  cmp     [rsi+13Ch], edi
0x1801977ab  jz      short loc_1801977DC
0x1801977ad  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x1801977b0  call    ?PuPerformBandManagement@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuPerformBandManagement(PU_DISK_PROPERTIES *)
0x1801977b5  test    eax, eax
0x1801977b7  jz      short loc_1801977DC
0x1801977b9  mov     r8, [rsi+88h]; unsigned __int64
0x1801977c0  xor     edx, edx; unsigned __int64
0x1801977c2  mov     rcx, r14; unsigned __int16 *
0x1801977c5  call    ?DeleteBands@@YAJPEBG_K1@Z; DeleteBands(ushort const *,unsigned __int64,unsigned __int64)
0x1801977ca  mov     ebx, eax
0x1801977cc  test    eax, eax
0x1801977ce  jns     short loc_1801977DC
0x1801977d0  lea     rdi, aDeletebands; "DeleteBands"
0x1801977d7  jmp     loc_180197645
0x1801977dc  test    r15d, r15d
0x1801977df  jnz     loc_1801978AE
0x1801977e5  mov     r15d, 100000h
0x1801977eb  cmp     r15d, 200h
0x1801977f2  jb      loc_1801978A1
0x1801977f8  call    cs:__imp_GetProcessHeap
0x1801977fe  test    rax, rax
0x180197801  jnz     short loc_180197808
0x180197803  xor     r14d, r14d
0x180197806  jmp     short loc_18019781C
0x180197808  mov     r8d, r15d; dwBytes
0x18019780b  mov     edx, 8; dwFlags
0x180197810  mov     rcx, rax; hHeap
0x180197813  call    cs:__imp_HeapAlloc
0x180197819  mov     r14, rax
0x18019781c  mov     ecx, r15d
0x18019781f  shr     ecx, 1
0x180197821  test    r14, r14
0x180197824  cmovnz  ecx, r15d
0x180197828  mov     r15d, ecx
0x18019782b  jz      short loc_1801977EB
0x18019782d  cmp     [rsp+130h+var_F0], 0
0x180197832  mov     rdx, rsi; struct PU_DISK_PROPERTIES *
0x180197835  mov     [rsp+130h+lpMem], r14
0x18019783a  mov     rcx, r13; hFile
0x18019783d  jz      short loc_180197859
0x18019783f  mov     rax, [rsp+130h+var_E8]
0x180197844  mov     r9d, r15d; unsigned int
0x180197847  mov     r8, r14; unsigned __int8 *
0x18019784a  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; struct PU_CLEAN_DISK_PARAMETERS *
0x18019784f  call    ?PuZeroEntireDisk@@YAHPEAXPEAVPU_DISK_PROPERTIES@@PEAEKPEAUPU_CLEAN_DISK_PARAMETERS@@P6AX0G@Z@Z; PuZeroEntireDisk(void *,PU_DISK_PROPERTIES *,uchar *,ulong,PU_CLEAN_DISK_PARAMETERS *,void (*)(void *,ushort))
0x180197854  jmp     loc_1801978EE
0x180197859  mov     r9, r14; unsigned __int8 *
0x18019785c  mov     [rsp+130h+dwCreationDisposition], r15d; unsigned int
0x180197861  mov     r8d, 1; int
0x180197867  call    ?PuZeroFirstOrLastOneMB@@YAHPEAXPEAVPU_DISK_PROPERTIES@@HPEAEK@Z; PuZeroFirstOrLastOneMB(void *,PU_DISK_PROPERTIES *,int,uchar *,ulong)
0x18019786c  mov     rax, [rsi+20h]
0x180197870  sub     rax, qword ptr cs:GUID_DEVCLASS_SMRDISK.Data1
0x180197877  jnz     short loc_180197884
  ... truncated ...
```
