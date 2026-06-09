# PuCleanDisk(PU_CLEAN_DISK_PARAMETERS *,void (*)(void *,ushort))

- ea: `0x18019bf0c`
- end: `0x18019c5e5`
- name: `?PuCleanDisk@@YAJPEAUPU_CLEAN_DISK_PARAMETERS@@P6AXPEAXG@Z@Z`
- size: `1753`
- prototype: `__int64 __fastcall(struct PU_CLEAN_DISK_PARAMETERS *, void (*)(void *, unsigned __int16))`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180114208`

## callees

- `0x180006350`
- `0x180007221`
- `0x18000d47c`
- `0x1800298d0`
- `0x18019a4a4`
- `0x18019bf0c`
- `0x18019cd40`
- `0x18019e8c4`
- `0x18019eac4`
- `0x18019f324`
- `0x18019f3c8`
- `0x18019f474`
- `0x18019f540`
- `0x18019f6f0`
- `0x1801a13a0`
- `0x1801a5fb4`
- `0x1801a9494`
- `0x1801a984c`
- `0x1801a9ab8`
- `0x1801a9c44`
- `0x1801aa148`
- `0x1801aaa3c`
- `0x1801aaa64`
- `0x1801aafdc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c2c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c527`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c0bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c1a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c2ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c2c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c329`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c4be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18019c527`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c4b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18019c4b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c592`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18019c592`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019bf76`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019c1da`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019bf76`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x18019c1da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019c5b6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18019c5b6`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c29e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c319`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c456`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c513`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c29e`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c319`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c456`
- `api-ms-win-core-io-l1-1-0!DeviceIoControl` at `0x18019c513`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c18e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18019c18e`

## string_xrefs

- `0x18019c1ca`: `CreateFile`
- `0x18019bfe7`: `Disk is read only`
- `0x18019c37f`: `DeleteBands`
- `0x18019c348`: `PuUpdateDisk`
- `0x18019c2e3`: `PuDeleteDriveLayout`

## pseudocode

```c
__int64 __fastcall PuCleanDisk(struct PU_CLEAN_DISK_PARAMETERS *a1, void (*a2)(void *, unsigned __int16))
{
  struct PU_CLEAN_DISK_PARAMETERS *v2; // r15
  __int64 v3; // rsi
  unsigned __int8 *v4; // r12
  const WCHAR *v5; // r14
  __int64 FileW; // r13
  int v7; // ebx
  int v8; // edi
  int v9; // eax
  signed int v10; // ebx
  const char *v11; // rdi
  signed int LastError; // eax
  __int64 v13; // r8
  BOOL v14; // r15d
  _QWORD *v15; // rax
  signed int v16; // eax
  int v17; // ecx
  DWORD v18; // eax
  signed int v19; // eax
  signed int v20; // eax
  int v21; // eax
  DWORD v22; // r14d
  __int64 v23; // rax
  signed int v24; // eax
  DWORD v25; // eax
  signed int v26; // eax
  signed int v27; // eax
  HANDLE ProcessHeap; // rax
  unsigned int v29; // edx
  void (*dwFlagsAndAttributes)(void *, unsigned __int16); // [rsp+28h] [rbp-B1h]
  DWORD v32; // [rsp+40h] [rbp-99h] BYREF
  unsigned int v33; // [rsp+48h] [rbp-91h] BYREF
  DWORD BytesReturned; // [rsp+4Ch] [rbp-8Dh] BYREF
  struct PU_CLEAN_DISK_PARAMETERS *v35; // [rsp+50h] [rbp-89h]
  unsigned __int8 *v36; // [rsp+58h] [rbp-81h] BYREF
  int v37; // [rsp+60h] [rbp-79h]
  LARGE_INTEGER PerformanceCount; // [rsp+68h] [rbp-71h] BYREF
  LARGE_INTEGER v39; // [rsp+70h] [rbp-69h] BYREF
  __int64 v40; // [rsp+78h] [rbp-61h]
  _QWORD Buf2[2]; // [rsp+80h] [rbp-59h] BYREF
  _BYTE Buf1[16]; // [rsp+90h] [rbp-49h] BYREF
  _BYTE v43[16]; // [rsp+A0h] [rbp-39h] BYREF
  const char *v44; // [rsp+B0h] [rbp-29h]
  __int64 v45; // [rsp+B8h] [rbp-21h]
  DWORD *v46; // [rsp+C0h] [rbp-19h]
  __int64 v47; // [rsp+C8h] [rbp-11h]
  unsigned __int8 **v48; // [rsp+D0h] [rbp-9h]
  __int64 v49; // [rsp+D8h] [rbp-1h]

  v2 = a1;
  v3 = *((_QWORD *)a1 + 1);
  v4 = 0;
  v5 = *(const WCHAR **)a1;
  FileW = -1;
  v7 = *((_DWORD *)a1 + 5);
  v8 = *((_DWORD *)a1 + 4);
  v32 = *((_DWORD *)a1 + 6);
  v9 = *((_DWORD *)a1 + 12);
  v35 = a1;
  v37 = v9;
  v33 = 0;
  v36 = 0;
  PU_TIMER::PU_TIMER((PU_TIMER *)&PerformanceCount);
  QueryPerformanceCounter(&PerformanceCount);
  if ( !*(_DWORD *)(v3 + 324) )
  {
    v10 = -2147220987;
    v11 = "Media is not present";
    goto LABEL_43;
  }
  if ( !*(_DWORD *)(v3 + 320) && *(_DWORD *)(v3 + 220) == 2 )
  {
    v10 = -2147220989;
    v11 = "Disk is not initialized";
    goto LABEL_43;
  }
  if ( *(_DWORD *)(v3 + 264) )
  {
    v10 = -2147220988;
    v11 = "Disk is offline";
    goto LABEL_43;
  }
  if ( *(_DWORD *)(v3 + 272) )
  {
    v10 = -2147220986;
    v11 = "Disk is read only";
    goto LABEL_43;
  }
  if ( !v7 && (unsigned int)PuDiskContainsOemPartition((struct PU_DISK_PROPERTIES *)v3) )
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
    if ( (unsigned int)PuDiskContainsDataPartition((struct PU_DISK_PROPERTIES *)v3) )
    {
      v10 = -2147220968;
      v11 = "Disk has one more or data partitions";
      goto LABEL_43;
    }
    if ( (unsigned int)PuDiskContainsEspPartition((struct PU_DISK_PROPERTIES *)v3) )
    {
      v10 = -2147220967;
      v11 = "Disk has an ESP partition";
      goto LABEL_43;
    }
  }
  if ( !*(_DWORD *)(v3 + 276)
    && !*(_DWORD *)(v3 + 280)
    && !*(_DWORD *)(v3 + 284)
    && !*(_DWORD *)(v3 + 288)
    && !*(_DWORD *)(v3 + 304) )
  {
    v10 = PuValidateOperation(*(_QWORD *)v2, 1);
    if ( v10 < 0 )
    {
      v11 = "PuValidateOperation";
      goto LABEL_43;
    }
    if ( !(unsigned int)PuGetDeviceNamesForRegions((struct PU_DISK_PROPERTIES *)v3) )
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
    if ( (unsigned int)PuDiskBacksBootPartition((struct PU_DISK_PROPERTIES *)v3) )
    {
      v10 = -2147220967;
      v11 = "Disk has a boot volume";
      goto LABEL_43;
    }
    PuDeleteAccessPathsForRegions((struct PU_DISK_PROPERTIES *)v3);
    PuDismountRegions((struct PU_DISK_PROPERTIES *)v3);
    CRtlList::Begin(v3 + 336, Buf1);
    v14 = *(_DWORD *)(v3 + 320)
       && (v15 = *(_QWORD **)(v13 + 8), Buf2[1] = v13, Buf2[0] = *v15, memcmp_0(Buf1, Buf2, 0x10u))
       && *((_QWORD *)CRtlListIter::GetEntryPointer((CRtlListIter *)Buf1) + 1) == 0;
    FileW = (__int64)CreateFileW(v5, 0xC0000000, 3u, 0, 3u, 0, 0);
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
        v2 = v35;
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
    if ( *(_DWORD *)(v3 + 316) )
    {
      if ( (unsigned int)PuPerformBandManagement((struct PU_DISK_PROPERTIES *)v3) )
      {
        v10 = DeleteBands(v5, 0, *(_QWORD *)(v3 + 136));
        if ( v10 < 0 )
        {
          v11 = "DeleteBands";
          goto LABEL_42;
        }
      }
    }
    if ( v37 )
    {
      v32 = 0;
      v21 = DeviceIoControl((HANDLE)FileW, 0x2D9640u, 0, 0, 0, 0, &v32, 0);
    }
    else
    {
      if ( !(unsigned int)PuCreateZeroBuffer(&v36, &v33) )
      {
        v4 = v36;
        goto LABEL_75;
      }
      v4 = v36;
      if ( !v32 )
      {
        v22 = v33;
        PuZeroFirstOrLastOneMB((HANDLE)FileW, (struct PU_DISK_PROPERTIES *)v3, 1, v36, v33);
        v23 = *(_QWORD *)(v3 + 32) - *(_QWORD *)&GUID_DEVCLASS_SMRDISK.Data1;
        if ( !v23 )
          v23 = *(_QWORD *)(v3 + 40) - *(_QWORD *)GUID_DEVCLASS_SMRDISK.Data4;
        if ( v23 )
          PuZeroFirstOrLastOneMB((HANDLE)FileW, (struct PU_DISK_PROPERTIES *)v3, 0, v4, v22);
LABEL_75:
        if ( *(_DWORD *)(v3 + 320) && !v14 )
        {
          if ( !(unsigned int)PuCreateDisk((HANDLE)FileW, (enum _PARTITION_STYLE)*(_DWORD *)(v3 + 220)) )
            goto LABEL_80;
          v25 = PuWriteBootCode((HANDLE)FileW, (struct PU_DISK_PROPERTIES *)v3);
          if ( v25 )
          {
            SetLastError(v25);
LABEL_80:
            v26 = GetLastError();
            v10 = v26;
            if ( v26 > 0 )
              v10 = (unsigned __int16)v26 | 0x80070000;
          }
        }
        v32 = 0;
        if ( !DeviceIoControl((HANDLE)FileW, 0x70140u, 0, 0, 0, 0, &v32, 0) )
        {
          v27 = GetLastError();
          v10 = v27;
          if ( v27 > 0 )
            v10 = (unsigned __int16)v27 | 0x80070000;
        }
        goto LABEL_42;
      }
      v21 = PuZeroEntireDisk(
              (HANDLE)FileW,
              (struct PU_DISK_PROPERTIES *)v3,
              v36,
              v33,
              (void **)v35,
              dwFlagsAndAttributes);
    }
    if ( !v21 )
    {
      v24 = GetLastError();
      v10 = v24;
      if ( v24 > 0 )
        v10 = (unsigned __int16)v24 | 0x80070000;
    }
    goto LABEL_75;
  }
  v10 = -2147220967;
  v11 = "Disk has a system partition";
LABEL_43:
  QueryPerformanceCounter(&v39);
  if ( v10 < 0 )
  {
    if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 1) != 0 )
      McTemplateU0sqsd_EventWriteTransfer(
        v17,
        (unsigned int)CleanDiskFailed,
        (unsigned int)"PuCleanDisk",
        *(_DWORD *)(v3 + 60),
        (__int64)v11,
        v10);
  }
  else if ( (Microsoft_Windows_StorageManagement_PartUtilEnableBits & 2) != 0 )
  {
    v44 = "PuCleanDisk";
    v45 = 12;
    v47 = 4;
    v36 = (unsigned __int8 *)(1000000 * (v39.QuadPart - PerformanceCount.QuadPart) / v40);
    v32 = *(_DWORD *)(v3 + 60);
    v46 = &v32;
    v48 = &v36;
    v49 = 8;
    McGenEventWrite_EventWriteTransfer(PartUtilProvider_Context, CleanDiskSucceeded, "PuCleanDisk", 4, v43);
  }
  *((_DWORD *)v2 + 7) = 0;
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    PmHeapFree(ProcessHeap, v29, v4);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18019bf0c  push    rbp
0x18019bf0e  push    rbx
0x18019bf0f  push    rsi
0x18019bf10  push    rdi
0x18019bf11  push    r12
0x18019bf13  push    r13
0x18019bf15  push    r14
0x18019bf17  push    r15
0x18019bf19  lea     rbp, [rsp-1Fh]
0x18019bf1e  sub     rsp, 0F8h
0x18019bf25  mov     rax, cs:__security_cookie
0x18019bf2c  xor     rax, rsp
0x18019bf2f  mov     [rbp+57h+var_50], rax
0x18019bf33  mov     eax, [rcx+18h]
0x18019bf36  mov     r15, rcx
0x18019bf39  mov     rsi, [rcx+8]
0x18019bf3d  xor     r12d, r12d
0x18019bf40  mov     r14, [rcx]
0x18019bf43  or      r13, 0FFFFFFFFFFFFFFFFh
0x18019bf47  mov     ebx, [rcx+14h]
0x18019bf4a  mov     edi, [rcx+10h]
0x18019bf4d  mov     [rsp+130h+var_F0], eax
0x18019bf51  mov     eax, [rcx+30h]
0x18019bf54  mov     [rsp+130h+var_E0], rcx
0x18019bf59  lea     rcx, [rbp+57h+PerformanceCount]; this
0x18019bf5d  mov     [rbp+57h+var_D0], eax
0x18019bf60  mov     [rsp+130h+var_E8], 0
0x18019bf68  mov     [rsp+130h+var_D8], r12
0x18019bf6d  call    ??0PU_TIMER@@QEAA@XZ; PU_TIMER::PU_TIMER(void)
0x18019bf72  lea     rcx, [rbp+57h+PerformanceCount]; lpPerformanceCount
0x18019bf76  call    cs:__imp_QueryPerformanceCounter
0x18019bf7d  nop     dword ptr [rax+rax+00h]
0x18019bf82  cmp     [rsi+144h], r12d
0x18019bf89  jnz     short loc_18019BF9C
0x18019bf8b  mov     ebx, 80040205h
0x18019bf90  lea     rdi, aMediaIsNotPres; "Media is not present"
0x18019bf97  jmp     loc_18019C1D6
0x18019bf9c  cmp     [rsi+140h], r12d
0x18019bfa3  jnz     short loc_18019BFBF
0x18019bfa5  cmp     dword ptr [rsi+0DCh], 2
0x18019bfac  jnz     short loc_18019BFBF
0x18019bfae  mov     ebx, 80040203h
0x18019bfb3  lea     rdi, aDiskIsNotIniti; "Disk is not initialized"
0x18019bfba  jmp     loc_18019C1D6
0x18019bfbf  cmp     [rsi+108h], r12d
0x18019bfc6  jz      short loc_18019BFD9
0x18019bfc8  mov     ebx, 80040204h
0x18019bfcd  lea     rdi, aDiskIsOffline; "Disk is offline"
0x18019bfd4  jmp     loc_18019C1D6
0x18019bfd9  cmp     [rsi+110h], r12d
0x18019bfe0  jz      short loc_18019BFF3
0x18019bfe2  mov     ebx, 80040206h
0x18019bfe7  lea     rdi, aDiskIsReadOnly; "Disk is read only"
0x18019bfee  jmp     loc_18019C1D6
0x18019bff3  test    ebx, ebx
0x18019bff5  jnz     short loc_18019C014
0x18019bff7  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019bffa  call    ?PuDiskContainsOemPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskContainsOemPartition(PU_DISK_PROPERTIES *)
0x18019bfff  test    eax, eax
0x18019c001  jz      short loc_18019C014
0x18019c003  mov     ebx, 80040217h
0x18019c008  lea     rdi, aDiskContainsAn; "Disk contains an OEM partition"
0x18019c00f  jmp     loc_18019C1D6
0x18019c014  test    edi, edi
0x18019c016  jnz     short loc_18019C054
0x18019c018  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019c01b  call    ?PuDiskContainsDataPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskContainsDataPartition(PU_DISK_PROPERTIES *)
0x18019c020  xor     edi, edi
0x18019c022  test    eax, eax
0x18019c024  jz      short loc_18019C037
0x18019c026  mov     ebx, 80040218h
0x18019c02b  lea     rdi, aDiskHasOneMore; "Disk has one more or data partitions"
0x18019c032  jmp     loc_18019C1D6
0x18019c037  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019c03a  call    ?PuDiskContainsEspPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskContainsEspPartition(PU_DISK_PROPERTIES *)
0x18019c03f  test    eax, eax
0x18019c041  jz      short loc_18019C056
0x18019c043  mov     ebx, 80040219h
0x18019c048  lea     rdi, aDiskHasAnEspPa; "Disk has an ESP partition"
0x18019c04f  jmp     loc_18019C1D6
0x18019c054  xor     edi, edi
0x18019c056  cmp     [rsi+114h], edi
0x18019c05c  jnz     loc_18019C54B
0x18019c062  cmp     [rsi+118h], edi
0x18019c068  jnz     loc_18019C54B
0x18019c06e  cmp     [rsi+11Ch], edi
0x18019c074  jnz     loc_18019C54B
0x18019c07a  cmp     [rsi+120h], edi
0x18019c080  jnz     loc_18019C54B
0x18019c086  cmp     [rsi+130h], edi
0x18019c08c  jnz     loc_18019C54B
0x18019c092  mov     rcx, [r15]
0x18019c095  mov     edx, 1
0x18019c09a  call    ?PuValidateOperation@@YAJPEBGW4PM_OPERATION@@@Z; PuValidateOperation(ushort const *,PM_OPERATION)
0x18019c09f  mov     ebx, eax
0x18019c0a1  test    eax, eax
0x18019c0a3  jns     short loc_18019C0B1
0x18019c0a5  lea     rdi, aPuvalidateoper; "PuValidateOperation"
0x18019c0ac  jmp     loc_18019C1D6
0x18019c0b1  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019c0b4  call    ?PuGetDeviceNamesForRegions@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuGetDeviceNamesForRegions(PU_DISK_PROPERTIES *)
0x18019c0b9  test    eax, eax
0x18019c0bb  jnz     short loc_18019C0E8
0x18019c0bd  call    cs:__imp_GetLastError
0x18019c0c4  nop     dword ptr [rax+rax+00h]
0x18019c0c9  mov     ebx, eax
0x18019c0cb  test    eax, eax
0x18019c0cd  jle     short loc_18019C0D8
0x18019c0cf  movzx   ebx, ax
0x18019c0d2  or      ebx, 80070000h
0x18019c0d8  test    ebx, ebx
0x18019c0da  jns     short loc_18019C0E8
0x18019c0dc  lea     rdi, aPugetdevicenam; "PuGetDeviceNamesForRegions"
0x18019c0e3  jmp     loc_18019C1D6
0x18019c0e8  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019c0eb  call    ?PuDiskBacksBootPartition@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuDiskBacksBootPartition(PU_DISK_PROPERTIES *)
0x18019c0f0  test    eax, eax
0x18019c0f2  jz      short loc_18019C105
0x18019c0f4  mov     ebx, 80040219h
0x18019c0f9  lea     rdi, aDiskHasABootVo; "Disk has a boot volume"
0x18019c100  jmp     loc_18019C1D6
0x18019c105  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019c108  call    ?PuDeleteAccessPathsForRegions@@YAXPEAVPU_DISK_PROPERTIES@@@Z; PuDeleteAccessPathsForRegions(PU_DISK_PROPERTIES *)
0x18019c10d  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019c110  call    ?PuDismountRegions@@YAXPEAVPU_DISK_PROPERTIES@@@Z; PuDismountRegions(PU_DISK_PROPERTIES *)
0x18019c115  lea     r8, [rsi+150h]
0x18019c11c  mov     rcx, r8
0x18019c11f  lea     rdx, [rbp+57h+Buf1]
0x18019c123  call    ?Begin@CRtlList@@QEAA?AVCRtlListIter@@XZ; CRtlList::Begin(void)
0x18019c128  cmp     [rsi+140h], edi
0x18019c12e  jnz     short loc_18019C135
0x18019c130  mov     r15d, edi
0x18019c133  jmp     short loc_18019C16F
0x18019c135  mov     rax, [r8+8]
0x18019c139  lea     rdx, [rbp+57h+Buf2]; Buf2
0x18019c13d  mov     [rbp+57h+var_A8], r8
0x18019c141  mov     r8d, 10h; Size
0x18019c147  mov     rcx, [rax]
0x18019c14a  mov     [rbp+57h+Buf2], rcx
0x18019c14e  lea     rcx, [rbp+57h+Buf1]; Buf1
0x18019c152  call    memcmp_0
0x18019c157  test    eax, eax
0x18019c159  jz      short loc_18019C130
0x18019c15b  lea     rcx, [rbp+57h+Buf1]; this
0x18019c15f  call    ?GetEntryPointer@CRtlListIter@@QEAAPEAXXZ; CRtlListIter::GetEntryPointer(void)
0x18019c164  mov     r15d, edi
0x18019c167  cmp     [rax+8], rdi
0x18019c16b  setz    r15b
0x18019c16f  mov     [rsp+130h+hTemplateFile], rdi; hTemplateFile
0x18019c174  mov     r8d, 3; dwShareMode
0x18019c17a  mov     dword ptr [rsp+130h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18019c17e  xor     r9d, r9d; lpSecurityAttributes
0x18019c181  mov     edx, 0C0000000h; dwDesiredAccess
0x18019c186  mov     [rsp+130h+dwCreationDisposition], r8d; dwCreationDisposition
0x18019c18b  mov     rcx, r14; lpFileName
0x18019c18e  call    cs:__imp_CreateFileW
0x18019c195  nop     dword ptr [rax+rax+00h]
0x18019c19a  mov     r13, rax
0x18019c19d  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18019c1a1  jnz     loc_18019C274
0x18019c1a7  call    cs:__imp_GetLastError
0x18019c1ae  nop     dword ptr [rax+rax+00h]
0x18019c1b3  mov     ebx, eax
0x18019c1b5  test    eax, eax
0x18019c1b7  jle     short loc_18019C1C2
0x18019c1b9  movzx   ebx, ax
0x18019c1bc  or      ebx, 80070000h
0x18019c1c2  test    ebx, ebx
0x18019c1c4  jns     loc_18019C274
0x18019c1ca  lea     rdi, aCreatefile; "CreateFile"
0x18019c1d1  mov     r15, [rsp+130h+var_E0]
0x18019c1d6  lea     rcx, [rbp+57h+var_C0]; lpPerformanceCount
0x18019c1da  call    cs:__imp_QueryPerformanceCounter
0x18019c1e1  nop     dword ptr [rax+rax+00h]
0x18019c1e6  test    ebx, ebx
0x18019c1e8  js      loc_18019C55C
0x18019c1ee  test    cs:Microsoft_Windows_StorageManagement_PartUtilEnableBits, 2
0x18019c1f5  jz      loc_18019C585
0x18019c1fb  mov     rax, qword ptr [rbp+57h+var_C0]
0x18019c1ff  lea     r8, aPucleandisk; "PuCleanDisk"
0x18019c206  sub     rax, qword ptr [rbp+57h+PerformanceCount]
0x18019c20a  lea     rcx, PartUtilProvider_Context
0x18019c211  imul    rax, 0F4240h
0x18019c218  mov     r9d, 4
0x18019c21e  mov     [rbp+57h+var_80], r8
0x18019c222  cqo
0x18019c224  mov     [rbp+57h+var_78], 0Ch
0x18019c22c  idiv    [rbp+57h+var_B8]
0x18019c230  lea     rdx, CleanDiskSucceeded
0x18019c237  mov     [rbp+57h+var_68], r9
0x18019c23b  mov     [rsp+130h+var_D8], rax
0x18019c240  mov     eax, [rsi+3Ch]
0x18019c243  mov     [rsp+130h+var_F0], eax
0x18019c247  lea     rax, [rsp+130h+var_F0]
0x18019c24c  mov     [rbp+57h+var_70], rax
0x18019c250  lea     rax, [rsp+130h+var_D8]
0x18019c255  mov     [rbp+57h+var_60], rax
0x18019c259  lea     rax, [rbp+57h+var_90]
0x18019c25d  mov     qword ptr [rsp+130h+dwCreationDisposition], rax
0x18019c262  mov     [rbp+57h+var_58], 8
0x18019c26a  call    McGenEventWrite_EventWriteTransfer
0x18019c26f  jmp     loc_18019C585
0x18019c274  mov     [rsp+130h+lpOverlapped], rdi; lpOverlapped
0x18019c279  lea     rax, [rsp+130h+BytesReturned]
0x18019c27e  mov     [rsp+130h+hTemplateFile], rax; lpBytesReturned
0x18019c283  xor     r9d, r9d; nInBufferSize
0x18019c286  mov     dword ptr [rsp+130h+dwFlagsAndAttributes], edi; nOutBufferSize
0x18019c28a  xor     r8d, r8d; lpInBuffer
0x18019c28d  mov     edx, 7C100h; dwIoControlCode
0x18019c292  mov     qword ptr [rsp+130h+dwCreationDisposition], rdi; lpOutBuffer
0x18019c297  mov     rcx, r13; hDevice
0x18019c29a  mov     [rsp+130h+BytesReturned], edi
0x18019c29e  call    cs:__imp_DeviceIoControl
0x18019c2a5  nop     dword ptr [rax+rax+00h]
0x18019c2aa  test    eax, eax
0x18019c2ac  jnz     short loc_18019C2EF
0x18019c2ae  call    cs:__imp_GetLastError
0x18019c2b5  nop     dword ptr [rax+rax+00h]
0x18019c2ba  test    r15d, r15d
0x18019c2bd  jz      short loc_18019C2C4
0x18019c2bf  cmp     eax, 1Fh
0x18019c2c2  jz      short loc_18019C2EF
0x18019c2c4  call    cs:__imp_GetLastError
0x18019c2cb  nop     dword ptr [rax+rax+00h]
0x18019c2d0  mov     ebx, eax
0x18019c2d2  test    eax, eax
0x18019c2d4  jle     short loc_18019C2DF
0x18019c2d6  movzx   ebx, ax
0x18019c2d9  or      ebx, 80070000h
0x18019c2df  test    ebx, ebx
0x18019c2e1  jns     short loc_18019C2EF
0x18019c2e3  lea     rdi, aPudeletedrivel; "PuDeleteDriveLayout"
0x18019c2ea  jmp     loc_18019C1D1
0x18019c2ef  mov     [rsp+130h+lpOverlapped], rdi; lpOverlapped
0x18019c2f4  lea     rax, [rsp+130h+BytesReturned]
0x18019c2f9  mov     [rsp+130h+hTemplateFile], rax; lpBytesReturned
0x18019c2fe  xor     r9d, r9d; nInBufferSize
0x18019c301  mov     dword ptr [rsp+130h+dwFlagsAndAttributes], edi; void (*)(void *, unsigned __int16)
0x18019c305  xor     r8d, r8d; lpInBuffer
0x18019c308  mov     edx, 70140h; dwIoControlCode
0x18019c30d  mov     qword ptr [rsp+130h+dwCreationDisposition], rdi; lpOutBuffer
0x18019c312  mov     rcx, r13; hDevice
0x18019c315  mov     [rsp+130h+BytesReturned], edi
0x18019c319  call    cs:__imp_DeviceIoControl
0x18019c320  nop     dword ptr [rax+rax+00h]
0x18019c325  test    eax, eax
0x18019c327  jnz     short loc_18019C354
0x18019c329  call    cs:__imp_GetLastError
0x18019c330  nop     dword ptr [rax+rax+00h]
0x18019c335  mov     ebx, eax
0x18019c337  test    eax, eax
0x18019c339  jle     short loc_18019C344
0x18019c33b  movzx   ebx, ax
0x18019c33e  or      ebx, 80070000h
0x18019c344  test    ebx, ebx
0x18019c346  jns     short loc_18019C354
0x18019c348  lea     rdi, aPuupdatedisk; "PuUpdateDisk"
0x18019c34f  jmp     loc_18019C1D1
0x18019c354  cmp     [rsi+13Ch], edi
0x18019c35a  jz      short loc_18019C38B
0x18019c35c  mov     rcx, rsi; struct PU_DISK_PROPERTIES *
0x18019c35f  call    ?PuPerformBandManagement@@YAHPEAVPU_DISK_PROPERTIES@@@Z; PuPerformBandManagement(PU_DISK_PROPERTIES *)
0x18019c364  test    eax, eax
0x18019c366  jz      short loc_18019C38B
0x18019c368  mov     r8, [rsi+88h]; unsigned __int64
0x18019c36f  xor     edx, edx; unsigned __int64
0x18019c371  mov     rcx, r14; unsigned __int16 *
0x18019c374  call    ?DeleteBands@@YAJPEBG_K1@Z; DeleteBands(ushort const *,unsigned __int64,unsigned __int64)
0x18019c379  mov     ebx, eax
0x18019c37b  test    eax, eax
0x18019c37d  jns     short loc_18019C38B
0x18019c37f  lea     rdi, aDeletebands; "DeleteBands"
0x18019c386  jmp     loc_18019C1D1
0x18019c38b  cmp     [rbp+57h+var_D0], r12d
0x18019c38f  jnz     loc_18019C42A
0x18019c395  lea     rdx, [rsp+130h+var_E8]; unsigned int *
0x18019c39a  lea     rcx, [rsp+130h+var_D8]; unsigned __int8 **
0x18019c39f  call    ?PuCreateZeroBuffer@@YAHPEAPEAEPEAK@Z; PuCreateZeroBuffer(uchar * *,ulong *)
0x18019c3a4  test    eax, eax
0x18019c3a6  jz      short loc_18019C423
0x18019c3a8  cmp     [rsp+130h+var_F0], r12d
0x18019c3ad  mov     rdx, rsi; struct PU_DISK_PROPERTIES *
0x18019c3b0  mov     r12, [rsp+130h+var_D8]
0x18019c3b5  mov     rcx, r13; hFile
0x18019c3b8  jz      short loc_18019C3D6
0x18019c3ba  mov     rax, [rsp+130h+var_E0]
0x18019c3bf  mov     r8, r12; unsigned __int8 *
0x18019c3c2  mov     r9d, [rsp+130h+var_E8]; unsigned int
0x18019c3c7  mov     qword ptr [rsp+130h+dwCreationDisposition], rax; struct PU_CLEAN_DISK_PARAMETERS *
0x18019c3cc  call    ?PuZeroEntireDisk@@YAHPEAXPEAVPU_DISK_PROPERTIES@@PEAEKPEAUPU_CLEAN_DISK_PARAMETERS@@P6AX0G@Z@Z; PuZeroEntireDisk(void *,PU_DISK_PROPERTIES *,uchar *,ulong,PU_CLEAN_DISK_PARAMETERS *,void (*)(void *,ushort))
0x18019c3d1  jmp     loc_18019C462
0x18019c3d6  mov     r14d, [rsp+130h+var_E8]
0x18019c3db  mov     r9, r12; unsigned __int8 *
0x18019c3de  mov     r8d, 1; int
0x18019c3e4  mov     [rsp+130h+dwCreationDisposition], r14d; unsigned int
0x18019c3e9  call    ?PuZeroFirstOrLastOneMB@@YAHPEAXPEAVPU_DISK_PROPERTIES@@HPEAEK@Z; PuZeroFirstOrLastOneMB(void *,PU_DISK_PROPERTIES *,int,uchar *,ulong)
0x18019c3ee  mov     rax, [rsi+20h]
0x18019c3f2  sub     rax, qword ptr cs:GUID_DEVCLASS_SMRDISK.Data1
0x18019c3f9  jnz     short loc_18019C406
0x18019c3fb  mov     rax, [rsi+28h]
  ... truncated ...
```
