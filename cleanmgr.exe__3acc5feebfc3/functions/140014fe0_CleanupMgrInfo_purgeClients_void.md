# CleanupMgrInfo::purgeClients(void)

- ea: `0x140014fe0`
- end: `0x140015fc2`
- name: `?purgeClients@CleanupMgrInfo@@QEAAHXZ`
- size: `4066`
- prototype: `__int64 __fastcall(CleanupMgrInfo *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config`

## callers

- `0x140009d34`

## callees

- `0x1400019bc`
- `0x140001cb8`
- `0x1400029a0`
- `0x140003390`
- `0x140005fa0`
- `0x140005fe4`
- `0x14000e15c`
- `0x14000ee64`
- `0x14000f254`
- `0x14000f87c`
- `0x14000f904`
- `0x140010a00`
- `0x140010be4`
- `0x140011fe4`
- `0x140014fe0`
- `0x140018010`

## import_xrefs

- `USER32!PostMessageW` at `0x1400154b8`
- `USER32!PostMessageW` at `0x1400155cc`
- `USER32!PostMessageW` at `0x1400154b8`
- `USER32!PostMessageW` at `0x1400155cc`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140015182`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140015182`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400151ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015f65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400151ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140015f65`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001519e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140015f58`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14001519e`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140015f58`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140015151`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140015151`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140015116`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001525a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400154f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140015527`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001590e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140015116`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001525a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1400154f8`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140015527`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x14001590e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140015132`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001545a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140015657`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140015132`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x14001545a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTime` at `0x140015657`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001522f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001524d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001522f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x14001524d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015cbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015f2f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015cbf`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140015f2f`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400151d2`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400152a6`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400155df`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x140015924`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400151d2`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400152a6`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x1400155df`
- `api-ms-win-core-file-l1-1-0!GetDiskFreeSpaceExW` at `0x140015924`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400158df`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1400158df`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14001546b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140015668`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x14001546b`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x140015668`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x1400151e2`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x1400152b6`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x1400155ef`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x140015934`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x1400151e2`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x1400152b6`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x1400155ef`
- `api-ms-win-storage-reserve-l1-1-0!QueryStorageReserveEx` at `0x140015934`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x140015206`
- `ext-ms-win-storage-sense-l1-2-0!GetStoragePolicySettings` at `0x140015206`

## pseudocode

```c
__int64 __fastcall CleanupMgrInfo::purgeClients(CleanupMgrInfo *this)
{
  double v2; // xmm8_8
  unsigned int *v3; // rsi
  HANDLE EventW; // rax
  HANDLE Thread; // rax
  bool v6; // r13
  char *v7; // rbx
  __int64 *v8; // r12
  int v9; // r14d
  __int64 v10; // r12
  __int64 v11; // rsi
  __int64 v12; // rax
  unsigned __int16 *v13; // rbx
  __int64 v14; // rax
  unsigned __int64 v15; // rdx
  ULONGLONG v16; // rbx
  int v17; // ecx
  _DWORD *v18; // r8
  ULONGLONG v19; // r14
  const unsigned __int16 *v20; // r8
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  int v24; // eax
  int v25; // eax
  struct _GUID *v26; // rdx
  CleanupMgrTelemetry::ClientPurge *v27; // rcx
  __int64 v28; // rbx
  double v29; // xmm0_8
  double v30; // xmm0_8
  unsigned __int64 v31; // rax
  __int64 v32; // r11
  __int64 v33; // r14
  double v34; // xmm6_8
  unsigned __int64 v35; // r12
  unsigned __int16 *v36; // rbx
  ULONGLONG v37; // rbx
  __int64 v38; // rbx
  double v39; // xmm6_8
  double v40; // xmm6_8
  unsigned int v41; // r13d
  __int64 v42; // rsi
  __int64 *v43; // r14
  const struct _tlgProvider_t *v44; // rax
  int v45; // r8d
  int v46; // r9d
  unsigned int v47; // r14d
  const struct _tlgProvider_t *v48; // rax
  int v49; // r8d
  int v50; // r9d
  void *v51; // rcx
  unsigned __int16 v53; // [rsp+50h] [rbp-128h]
  unsigned __int16 v54; // [rsp+60h] [rbp-118h]
  int v55; // [rsp+F8h] [rbp-80h] BYREF
  int v56; // [rsp+FCh] [rbp-7Ch] BYREF
  unsigned int v57; // [rsp+100h] [rbp-78h] BYREF
  unsigned int v58; // [rsp+104h] [rbp-74h] BYREF
  int v59; // [rsp+108h] [rbp-70h] BYREF
  unsigned int v60; // [rsp+10Ch] [rbp-6Ch]
  unsigned int v61; // [rsp+110h] [rbp-68h]
  unsigned int v62; // [rsp+114h] [rbp-64h]
  unsigned int v63; // [rsp+118h] [rbp-60h]
  unsigned int v64; // [rsp+11Ch] [rbp-5Ch]
  unsigned int v65; // [rsp+120h] [rbp-58h]
  union _ULARGE_INTEGER TotalNumberOfBytes; // [rsp+128h] [rbp-50h] BYREF
  unsigned __int64 v67; // [rsp+130h] [rbp-48h] BYREF
  unsigned int v68; // [rsp+138h] [rbp-40h] BYREF
  __int64 *v69; // [rsp+140h] [rbp-38h] BYREF
  HLOCAL hMem; // [rsp+148h] [rbp-30h] BYREF
  double v71; // [rsp+150h] [rbp-28h] BYREF
  __int64 v72; // [rsp+158h] [rbp-20h] BYREF
  __int64 v73; // [rsp+160h] [rbp-18h] BYREF
  __int64 v74; // [rsp+168h] [rbp-10h] BYREF
  unsigned __int64 v75; // [rsp+170h] [rbp-8h] BYREF
  struct _FILETIME FileTime; // [rsp+178h] [rbp+0h] BYREF
  unsigned int v77; // [rsp+180h] [rbp+8h]
  ULONGLONG TickCount64; // [rsp+188h] [rbp+10h] BYREF
  union _ULARGE_INTEGER v79; // [rsp+190h] [rbp+18h] BYREF
  union _ULARGE_INTEGER TotalNumberOfFreeBytes; // [rsp+198h] [rbp+20h] BYREF
  union _ULARGE_INTEGER v81; // [rsp+1A0h] [rbp+28h] BYREF
  union _ULARGE_INTEGER v82; // [rsp+1A8h] [rbp+30h] BYREF
  __int64 v83; // [rsp+1B0h] [rbp+38h] BYREF
  double v84; // [rsp+1B8h] [rbp+40h] BYREF
  union _ULARGE_INTEGER v85; // [rsp+1C0h] [rbp+48h] BYREF
  union _ULARGE_INTEGER v86; // [rsp+1C8h] [rbp+50h] BYREF
  union _ULARGE_INTEGER v87; // [rsp+1D0h] [rbp+58h] BYREF
  union _ULARGE_INTEGER v88; // [rsp+1D8h] [rbp+60h] BYREF
  double v89; // [rsp+1E0h] [rbp+68h] BYREF
  __int64 v90; // [rsp+1E8h] [rbp+70h] BYREF
  __int64 *v91; // [rsp+1F0h] [rbp+78h] BYREF
  int v92; // [rsp+1F8h] [rbp+80h]
  void *v93; // [rsp+200h] [rbp+88h] BYREF
  int v94; // [rsp+208h] [rbp+90h]
  void *v95; // [rsp+210h] [rbp+98h] BYREF
  int v96; // [rsp+218h] [rbp+A0h]
  __int64 *v97; // [rsp+220h] [rbp+A8h] BYREF
  int v98; // [rsp+228h] [rbp+B0h]
  _SYSTEMTIME SystemTime; // [rsp+230h] [rbp+B8h] BYREF
  _BYTE v100[336]; // [rsp+248h] [rbp+D0h] BYREF
  _QWORD v101[42]; // [rsp+398h] [rbp+220h] BYREF
  __int64 v102[12]; // [rsp+4E8h] [rbp+370h] BYREF
  unsigned __int16 v103[4]; // [rsp+548h] [rbp+3D0h] BYREF
  __int64 v104; // [rsp+550h] [rbp+3D8h]
  __int64 v105; // [rsp+558h] [rbp+3E0h]
  __int64 v106; // [rsp+560h] [rbp+3E8h]
  __int64 v107[12]; // [rsp+5A8h] [rbp+430h] BYREF
  __int64 v108[12]; // [rsp+608h] [rbp+490h] BYREF
  unsigned __int16 lParam[256]; // [rsp+668h] [rbp+4F0h] BYREF

  SystemTime = 0;
  v81.QuadPart = 0;
  v82.QuadPart = 0;
  TotalNumberOfFreeBytes.QuadPart = 0;
  v79.QuadPart = 0;
  TotalNumberOfBytes.QuadPart = 0;
  v2 = 0.0;
  v71 = 0.0;
  v55 = 0;
  v59 = 0;
  v77 = 1;
  v60 = 0;
  v65 = 0;
  v64 = 0;
  v63 = 0;
  v62 = 0;
  v61 = 0;
  v57 = 0;
  v58 = 0;
  v74 = 0;
  v73 = 0;
  v72 = 0;
  lParam[0] = 0;
  *((_QWORD *)this + 215) = 0;
  *((_DWORD *)this + 443) = 0;
  *((_QWORD *)this + 211) = 0;
  memset_0(v103, -1, 0x60u);
  memset_0(v102, -1, sizeof(v102));
  memset_0(v108, -1, sizeof(v108));
  memset_0(v107, -1, sizeof(v107));
  wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v101,
    "PurgeClients");
  v101[0] = &CleanupMgrTelemetry::PurgeClients::`vftable';
  cleanmgrBeforeCleanMgrPurgeActivityTick = GetTickCount64();
  CleanupMgrInfo::calculateSpaceToPurge(this);
  GetSystemTime(&SystemTime);
  v3 = (unsigned int *)((char *)this + 1632);
  if ( (*((_DWORD *)this + 408) & 0x1220) == 0 )
  {
    EventW = CreateEventW(0, 0, 0, 0);
    *((_QWORD *)this + 213) = EventW;
    if ( EventW )
    {
      Thread = CreateThread(0, 0, PurgeAbortThread, this, 0, (LPDWORD)this + 428);
      *((_QWORD *)this + 211) = Thread;
      if ( Thread )
        WaitForSingleObject(*((HANDLE *)this + 213), 0xFFFFFFFF);
      CloseHandle(*((HANDLE *)this + 213));
    }
  }
  if ( *((_QWORD *)this + 219) )
    qword_140021680 = (__int64)this;
  GetDiskFreeSpaceExW((LPCWSTR)this + 8, 0, &TotalNumberOfBytes, &TotalNumberOfFreeBytes);
  QueryStorageReserveEx((char *)this + 16, v108);
  v6 = 0;
  if ( (*v3 & 0xA00) == 0xA00 )
  {
    v56 = 1;
    if ( (int)GetStoragePolicySettings(2, 0, &v56) >= 0 )
      v6 = v56 == 0;
  }
  v7 = (char *)LocalAlloc(0x40u, 176LL * *((int *)this + 434));
  hMem = v7;
  v8 = (__int64 *)LocalAlloc(0x40u, 272LL * *((int *)this + 434));
  v69 = v8;
  TickCount64 = GetTickCount64();
  v9 = 0;
  v56 = 0;
  if ( *((int *)this + 434) <= 0 )
    goto LABEL_73;
  while ( 2 )
  {
    FileTime = 0;
    v67 = 0;
    GetDiskFreeSpaceExW((LPCWSTR)this + 8, 0, &TotalNumberOfBytes, &v81);
    QueryStorageReserveEx((char *)this + 16, v103);
    v10 = v9;
    v11 = 616LL * v9;
    v12 = *((_QWORD *)this + 218);
    CleanupMgrTelemetry::ClientPurge::ClientPurge(
      (unsigned int)v100,
      v11 + v12 + 604,
      v11 + v12 + 40,
      v11 + v12 + 608,
      v11 + v12 + 604,
      v11 + v12 + 600,
      (__int64)this + 16,
      (__int64)this + 1632,
      (__int64)this + 1648);
    if ( v7 )
    {
      v13 = (unsigned __int16 *)&v7[176 * v9];
      StringCchPrintfW(v13, 0x50u, L"%-*s");
      *((_DWORD *)v13 + 40) = *(_DWORD *)(*((_QWORD *)this + 218) + v11 + 608);
      *((_DWORD *)v13 + 41) = *(_DWORD *)(*((_QWORD *)this + 218) + v11 + 604);
      *((_DWORD *)v13 + 42) = *(_DWORD *)(*((_QWORD *)this + 218) + v11 + 600);
      *((_DWORD *)v13 + 43) = v9;
    }
    v14 = *((_QWORD *)this + 218);
    v15 = *(_QWORD *)(v11 + v14 + 592);
    v75 = v15;
    v16 = 0;
    if ( !v15 )
      ++v62;
    v17 = *(_DWORD *)(v11 + v14 + 604);
    if ( v17 == 1 )
      ++v61;
    v18 = (_DWORD *)((char *)this + 1632);
    if ( (*((_DWORD *)this + 408) & 0x200) != 0 )
    {
      if ( !*(_DWORD *)(v11 + v14 + 608)
        || !v15
        || (*v18 & 0x400) == 0 && !*((_DWORD *)this + 410) && (*(_BYTE *)(v11 + v14 + 612) & 2) != 0
        || (*v18 & 0x800) != 0 && v6 )
      {
        goto LABEL_26;
      }
    }
    else if ( !*(_DWORD *)(v11 + v14 + 600) || !v17 )
    {
LABEL_26:
      ++v57;
      goto LABEL_27;
    }
    v19 = 0;
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, &FileTime);
    v20 = *(const unsigned __int16 **)(*((_QWORD *)this + 218) + v11 + 568);
    if ( v20 )
    {
      StringCchCopyW(lParam, 0x100u, v20);
      if ( (*((_DWORD *)this + 408) & 0x1220) == 0 )
        PostMessageW(*((HWND *)this + 212), 0x402u, 0, (LPARAM)lParam);
    }
    *((_QWORD *)this + 216) = 0;
    v21 = v11 + *((_QWORD *)this + 218);
    if ( *(_QWORD *)(v21 + 24) && *((_QWORD *)this + 219) )
    {
      ++v58;
      if ( v21 )
        qword_140021678 = v21;
      v19 = GetTickCount64();
      v22 = *(_QWORD *)(*((_QWORD *)this + 218) + v11 + 24);
      v55 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, _QWORD))(*(_QWORD *)v22 + 40LL))(
              v22,
              v75,
              *((_QWORD *)this + 220));
      v16 = GetTickCount64();
      if ( v55 < 0 )
      {
        ++v64;
        *((_DWORD *)this + 407) = 2;
      }
      v23 = *(_QWORD *)(*((_QWORD *)this + 218) + v11 + 24);
      v24 = (*(__int64 (__fastcall **)(__int64, unsigned __int64 *, _QWORD))(*(_QWORD *)v23 + 32LL))(
              v23,
              &v67,
              *((_QWORD *)this + 220));
      v59 = v24;
      if ( v24 < 0 )
      {
        ++v63;
        *((_DWORD *)this + 407) = 2;
      }
      if ( v55 >= 0 && v24 >= 0 )
        ++v65;
    }
    *((_QWORD *)this + 215) += *(_QWORD *)(*((_QWORD *)this + 218) + 616 * v10 + 592);
    *((_QWORD *)this + 216) = 0;
    if ( (*((_DWORD *)this + 408) & 0x1220) == 0 )
      PostMessageW(*((HWND *)this + 212), 0x401u, 0, 0);
    GetDiskFreeSpaceExW((LPCWSTR)this + 8, 0, &TotalNumberOfBytes, &v82);
    QueryStorageReserveEx((char *)this + 16, v102);
    v25 = 1;
    while ( 1 )
    {
      while ( v25 == 1 )
      {
        v74 = v104 - v102[1];
LABEL_54:
        ++v25;
      }
      if ( v25 == 2 )
      {
        v73 = v105 - v102[2];
        goto LABEL_54;
      }
      if ( v25 == 3 )
        break;
      if ( (unsigned int)++v25 >= 4 )
        goto LABEL_57;
    }
    v72 = v106 - v102[3];
LABEL_57:
    GetSystemTime(&SystemTime);
    SystemTimeToFileTime(&SystemTime, &FileTime);
    v28 = v16 - v19;
    if ( v28 < 0 )
      v29 = (double)(int)(v28 & 1 | ((unsigned __int64)v28 >> 1))
          + (double)(int)(v28 & 1 | ((unsigned __int64)v28 >> 1));
    else
      v29 = (double)(int)v28;
    v30 = v29 / 1000.0;
    v31 = 0;
    if ( v30 >= 9.223372036854776e18 )
    {
      v30 = v30 - 9.223372036854776e18;
      if ( v30 < 9.223372036854776e18 )
      {
        v27 = (CleanupMgrTelemetry::ClientPurge *)0x8000000000000000LL;
        v31 = 0x8000000000000000uLL;
      }
    }
    v32 = *((_QWORD *)this + 218);
    v33 = v31 + (unsigned int)(int)v30;
    if ( v33 < 0 )
    {
      v27 = (CleanupMgrTelemetry::ClientPurge *)(v33 & 1 | ((unsigned __int64)v33 >> 1));
      v34 = (double)(int)v27 + (double)(int)v27;
    }
    else
    {
      v34 = (double)(int)v33;
    }
    LOBYTE(v26) = *(_DWORD *)(v11 + v32 + 608) != 0;
    LOBYTE(v27) = *((_DWORD *)this + 443) != 0;
    v35 = v75;
    CleanupMgrTelemetry::ClientPurge::Stop(
      v27,
      v26,
      (const unsigned __int16 *)(v11 + v32 + 40),
      *(_DWORD *)(v11 + v32 + 588),
      v34,
      v67,
      v75,
      v81.QuadPart,
      v82.QuadPart,
      (__int64 *)v103,
      v102,
      v54,
      (bool)v27,
      (bool)v26,
      *(_DWORD *)(v11 + v32 + 604) != 0,
      *(_DWORD *)(v11 + v32 + 600) != 0,
      v55,
      v59,
      (const unsigned __int16 *)this + 8,
      *((_DWORD *)this + 408),
      *((_DWORD *)this + 412) != 0);
    if ( v69 )
    {
      v36 = (unsigned __int16 *)&v69[34 * v60];
      StringCchPrintfW(v36, 0x50u, L"%-*s");
      *((_OWORD *)v36 + 10) = *(_OWORD *)(v11 + *((_QWORD *)this + 218) + 8);
      *((_QWORD *)v36 + 22) = v74;
      *((_QWORD *)v36 + 23) = v73;
      *((_QWORD *)v36 + 24) = v72;
      *((_QWORD *)v36 + 25) = v33;
      *((_QWORD *)v36 + 26) = v67;
      *((_QWORD *)v36 + 27) = v35;
      *((union _ULARGE_INTEGER *)v36 + 28) = v81;
      *((union _ULARGE_INTEGER *)v36 + 29) = v82;
      *((_DWORD *)v36 + 62) = *(_DWORD *)(v11 + *((_QWORD *)this + 218) + 608);
      *((_DWORD *)v36 + 63) = *(_DWORD *)(v11 + *((_QWORD *)this + 218) + 604);
      *((_DWORD *)v36 + 64) = *(_DWORD *)(v11 + *((_QWORD *)this + 218) + 600);
      *((_DWORD *)v36 + 65) = v55;
      *((_DWORD *)v36 + 66) = v59;
      v9 = v56;
      *((_DWORD *)v36 + 67) = v56;
    }
    else
    {
      v9 = v56;
    }
    v2 = v2 + v34;
    v71 = v2;
    ++v60;
    if ( *((_DWORD *)this + 443) == 1 )
    {
      *((_DWORD *)this + 407) = 4;
      v77 = 0;
      CleanupMgrTelemetry::ClientPurge::~ClientPurge((CleanupMgrTelemetry::ClientPurge *)v100);
    }
    else
    {
      Sleep(0x3E8u);
LABEL_27:
      CleanupMgrTelemetry::ClientPurge::~ClientPurge((CleanupMgrTelemetry::ClientPurge *)v100);
      v56 = ++v9;
      if ( v9 < *((_DWORD *)this + 434) )
      {
        v7 = (char *)hMem;
        continue;
      }
    }
    break;
  }
  v3 = (unsigned int *)((char *)this + 1632);
  v8 = v69;
LABEL_73:
  v37 = GetTickCount64();
  GetDiskFreeSpaceExW((LPCWSTR)this + 8, 0, &TotalNumberOfBytes, &v79);
  QueryStorageReserveEx((char *)this + 16, v107);
  v38 = v37 - TickCount64;
  if ( v38 < 0 )
    v39 = (double)(int)(v38 & 1 | ((unsigned __int64)v38 >> 1)) + (double)(int)(v38 & 1 | ((unsigned __int64)v38 >> 1));
  else
    v39 = (double)(int)v38;
  v40 = v39 / 1000.0;
  v41 = v57;
  CleanupMgrTelemetry::PurgeClients::Stop(
    (CleanupMgrTelemetry::PurgeClients *)*((int *)this + 434),
    *((_DWORD *)qword_14001AA40 + *((int *)this + 406)),
    *((unsigned int *)this + 402),
    *((_QWORD *)this + 215),
    TotalNumberOfBytes.QuadPart,
    TotalNumberOfFreeBytes.QuadPart,
    v79.QuadPart,
    v108,
    v107,
    v53,
    *((_DWORD *)this + 443) != 0,
    v40,
    *((int *)this + 434),
    v60,
    v58,
    v65,
    v64,
    v63,
    v62,
    v61,
    v57,
    (const unsigned __int16 *)this + 8,
    *v3,
    *((_DWORD *)this + 412) != 0);
  v42 = *(_QWORD *)&v71;
  v43 = (__int64 *)hMem;
  if ( hMem )
  {
    LOWORD(v55) = *((_WORD *)this + 868);
    v44 = g_hProvider::Provider();
    if ( *(_DWORD *)v44 && (unsigned __int8)tlgKeywordOn(v44, 0x400000000000LL, v44) )
    {
      v91 = v43;
      v92 = 176 * (unsigned __int16)v55;
      v93 = &v55;
      v94 = 2;
      v95 = v107;
      LOWORD(v96) = 12;
      v97 = v108;
      LOWORD(v98) = 12;
      v83 = v42;
      v84 = v40;
      v56 = v41;
      v59 = v61;
      v57 = v62;
      v68 = v63;
      LODWORD(TickCount64) = v64;
      LODWORD(hMem) = v65;
      LODWORD(v71) = v58;
      LODWORD(v72) = v60;
      LODWORD(v73) = *((_DWORD *)this + 434);
      LODWORD(v74) = *((_DWORD *)this + 443);
      v85 = v79;
      v86 = TotalNumberOfFreeBytes;
      v87 = TotalNumberOfBytes;
      v88 = *(union _ULARGE_INTEGER *)((char *)this + 1720);
      LODWORD(v75) = *((_DWORD *)this + 402);
      FileTime.dwLowDateTime = *((_DWORD *)qword_14001AA40 + *((int *)this + 406));
      LODWORD(v69) = *((_DWORD *)this + 412);
      LODWORD(v67) = *((_DWORD *)this + 408);
      *(_QWORD *)&v89 = (char *)this + 16;
      v90 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapperArray<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v45,
        (unsigned int)&dword_14001B68C,
        v45,
        v46,
        (__int64)&v90,
        (__int64)&v89,
        (__int64)&v67,
        (__int64)&v69,
        (__int64)&FileTime,
        (__int64)&v75,
        (__int64)&v88,
        (__int64)&v87,
        (__int64)&v86,
        (__int64)&v85,
        (__int64)&v74,
        (__int64)&v73,
        (__int64)&v72,
        (__int64)&v71,
        (__int64)&hMem,
        (__int64)&TickCount64,
        (__int64)&v68,
        (__int64)&v57,
        (__int64)&v59,
        (__int64)&v56,
        (__int64)&v84,
        (__int64)&v83,
        (__int64)&v97,
        (__int64)&v95,
        (__int64)&v93,
        (__int64)&v91);
    }
    LocalFree(v43);
  }
  if ( v8 )
  {
    v47 = v60;
    LOWORD(v55) = v60;
    v48 = g_hProvider::Provider();
    if ( *(_DWORD *)v48 && (unsigned __int8)tlgKeywordOn(v48, 0x400000000000LL, v48) )
    {
      v97 = v8;
      v98 = 272 * (unsigned __int16)v55;
      v95 = &v55;
      v96 = 2;
      v93 = v107;
      LOWORD(v94) = 12;
      v91 = v108;
      LOWORD(v92) = 12;
      v90 = v42;
      v89 = v40;
      LODWORD(v67) = v41;
      LODWORD(v69) = v61;
      FileTime.dwLowDateTime = v62;
      LODWORD(v75) = v63;
      LODWORD(v74) = v64;
      LODWORD(v73) = v65;
      LODWORD(v72) = v58;
      LODWORD(v71) = v47;
      LODWORD(hMem) = *((_DWORD *)this + 434);
      LODWORD(TickCount64) = *((_DWORD *)this + 443);
      v88 = v79;
      v87 = TotalNumberOfFreeBytes;
      v86 = TotalNumberOfBytes;
      v85 = *(union _ULARGE_INTEGER *)((char *)this + 1720);
      v68 = *((_DWORD *)this + 402);
      v56 = *((_DWORD *)qword_14001AA40 + *((int *)this + 406));
      v59 = *((_DWORD *)this + 412);
      v58 = *((_DWORD *)this + 408);
      *(_QWORD *)&v84 = (char *)this + 16;
      v83 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperArray<8>,_tlgWrapperArray<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
        v49,
        (unsigned int)&unk_14001B378,
        v49,
        v50,
        (__int64)&v83,
        (__int64)&v84,
        (__int64)&v58,
        (__int64)&v59,
        (__int64)&v56,
        (__int64)&v68,
        (__int64)&v85,
        (__int64)&v86,
        (__int64)&v87,
        (__int64)&v88,
        (__int64)&TickCount64,
        (__int64)&hMem,
        (__int64)&v71,
        (__int64)&v72,
        (__int64)&v73,
        (__int64)&v74,
        (__int64)&v75,
        (__int64)&FileTime,
        (__int64)&v69,
        (__int64)&v67,
        (__int64)&v89,
        (__int64)&v90,
        (__int64)&v91,
        (__int64)&v93,
        (__int64)&v95,
        (__int64)&v97);
    }
    LocalFree(v8);
  }
  if ( !*((_DWORD *)this + 443) )
  {
    *((_DWORD *)this + 443) = 1;
    v51 = (void *)*((_QWORD *)this + 211);
    if ( v51 )
    {
      WaitForSingleObject(v51, 0xFFFFFFFF);
      CloseHandle(*((HANDLE *)this + 211));
      *((_QWORD *)this + 211) = 0;
    }
    *((_DWORD *)this + 443) = 0;
  }
  CleanupMgrTelemetry::PurgeClients::~PurgeClients((CleanupMgrTelemetry::PurgeClients *)v101);
  return v77;
}

```

## disassembly

```asm
0x140014fe0  mov     rax, rsp
0x140014fe3  push    rbp
0x140014fe4  push    rbx
0x140014fe5  push    rsi
0x140014fe6  push    rdi
0x140014fe7  push    r12
0x140014fe9  push    r13
0x140014feb  push    r14
0x140014fed  push    r15
0x140014fef  lea     rbp, [rax-788h]
0x140014ff6  sub     rsp, 8B8h
0x140014ffd  movaps  xmmword ptr [rax-58h], xmm6
0x140015001  movaps  xmmword ptr [rax-68h], xmm7
0x140015005  movaps  xmmword ptr [rax-78h], xmm8
0x14001500a  movaps  xmmword ptr [rax-88h], xmm9
0x140015012  mov     rax, cs:__security_cookie
0x140015019  xor     rax, rsp
0x14001501c  mov     [rbp+780h+var_90], rax
0x140015023  mov     rdi, rcx
0x140015026  xorps   xmm0, xmm0
0x140015029  movups  xmmword ptr [rbp+780h+SystemTime.wYear], xmm0
0x140015030  xor     r14d, r14d
0x140015033  mov     qword ptr [rbp+780h+var_758], r14
0x140015037  mov     qword ptr [rbp+780h+var_750], r14
0x14001503b  mov     qword ptr [rbp+780h+TotalNumberOfFreeBytes], r14
0x14001503f  mov     qword ptr [rbp+780h+var_768], r14
0x140015043  mov     qword ptr [rbp+780h+TotalNumberOfBytes], r14
0x140015047  xorps   xmm8, xmm8
0x14001504b  movsd   [rbp+780h+var_7A8], xmm8
0x140015051  mov     [rbp+780h+var_800], r14d
0x140015055  mov     [rbp+780h+var_7F0], r14d
0x140015059  lea     r12d, [r14+1]
0x14001505d  mov     [rbp+780h+var_778], r12d
0x140015061  mov     [rbp+780h+var_7EC], r14d
0x140015065  mov     [rbp+780h+var_7D8], r14d
0x140015069  mov     [rbp+780h+var_7DC], r14d
0x14001506d  mov     [rbp+780h+var_7E0], r14d
0x140015071  mov     [rbp+780h+var_7E4], r14d
0x140015075  mov     [rbp+780h+var_7E8], r14d
0x140015079  mov     [rbp+780h+var_7F8], r14d
0x14001507d  mov     [rbp+780h+var_7F4], r14d
0x140015081  mov     [rbp+780h+var_790], r14
0x140015085  mov     [rbp+780h+var_798], r14
0x140015089  mov     [rbp+780h+var_7A0], r14
0x14001508d  mov     [rbp+780h+lParam], r14w
0x140015095  mov     [rcx+6B8h], r14
0x14001509c  mov     [rcx+6ECh], r14d
0x1400150a3  mov     [rcx+698h], r14
0x1400150aa  lea     esi, [r14+60h]
0x1400150ae  mov     r8d, esi; Size
0x1400150b1  or      ebx, 0FFFFFFFFh
0x1400150b4  mov     edx, ebx; Val
0x1400150b6  lea     rcx, [rbp+780h+var_3B0]; void *
0x1400150bd  call    memset_0
0x1400150c2  mov     r8d, esi; Size
0x1400150c5  mov     edx, ebx; Val
0x1400150c7  lea     rcx, [rbp+780h+var_410]; void *
0x1400150ce  call    memset_0
0x1400150d3  mov     r8d, esi; Size
0x1400150d6  mov     edx, ebx; Val
0x1400150d8  lea     rcx, [rbp+780h+var_2F0]; void *
0x1400150df  call    memset_0
0x1400150e4  mov     r8d, esi; Size
0x1400150e7  mov     edx, ebx; Val
0x1400150e9  lea     rcx, [rbp+780h+var_350]; void *
0x1400150f0  call    memset_0
0x1400150f5  lea     rdx, aPurgeclients; "PurgeClients"
0x1400150fc  lea     rcx, [rbp+780h+var_560]
0x140015103  call    ??0?$ActivityBase@Vg_hProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<g_hProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140015108  lea     rax, ??_7PurgeClients@CleanupMgrTelemetry@@6B@; const CleanupMgrTelemetry::PurgeClients::`vftable'
0x14001510f  mov     [rbp+780h+var_560], rax
0x140015116  call    cs:__imp_GetTickCount64
0x14001511c  mov     cs:?cleanmgrBeforeCleanMgrPurgeActivityTick@@3_KA, rax; unsigned __int64 cleanmgrBeforeCleanMgrPurgeActivityTick
0x140015123  mov     rcx, rdi; this
0x140015126  call    ?calculateSpaceToPurge@CleanupMgrInfo@@IEAAXXZ; CleanupMgrInfo::calculateSpaceToPurge(void)
0x14001512b  lea     rcx, [rbp+780h+SystemTime]; lpSystemTime
0x140015132  call    cs:__imp_GetSystemTime
0x140015138  lea     rsi, [rdi+660h]
0x14001513f  test    dword ptr [rsi], 1220h
0x140015145  jnz     short loc_1400151B1
0x140015147  xor     r9d, r9d; lpName
0x14001514a  xor     r8d, r8d; bInitialState
0x14001514d  xor     edx, edx; bManualReset
0x14001514f  xor     ecx, ecx; lpEventAttributes
0x140015151  call    cs:__imp_CreateEventW
0x140015157  mov     [rdi+6A8h], rax
0x14001515e  test    rax, rax
0x140015161  jz      short loc_1400151B1
0x140015163  lea     rax, [rdi+6B0h]
0x14001516a  mov     [rsp+8F0h+lpThreadId], rax; lpThreadId
0x14001516f  mov     [rsp+8F0h+dwCreationFlags], r14d; dwCreationFlags
0x140015174  mov     r9, rdi; lpParameter
0x140015177  lea     r8, ?PurgeAbortThread@@YAKPEAVCleanupMgrInfo@@@Z; lpStartAddress
0x14001517e  xor     edx, edx; dwStackSize
0x140015180  xor     ecx, ecx; lpThreadAttributes
0x140015182  call    cs:__imp_CreateThread
0x140015188  mov     [rdi+698h], rax
0x14001518f  test    rax, rax
0x140015192  jz      short loc_1400151A4
0x140015194  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140015197  mov     rcx, [rdi+6A8h]; hHandle
0x14001519e  call    cs:__imp_WaitForSingleObject
0x1400151a4  mov     rcx, [rdi+6A8h]; hObject
0x1400151ab  call    cs:__imp_CloseHandle
0x1400151b1  cmp     [rdi+6D8h], r14
0x1400151b8  jz      short loc_1400151C1
0x1400151ba  mov     cs:qword_140021680, rdi
0x1400151c1  lea     r15, [rdi+10h]
0x1400151c5  lea     r9, [rbp+780h+TotalNumberOfFreeBytes]; lpTotalNumberOfFreeBytes
0x1400151c9  lea     r8, [rbp+780h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1400151cd  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1400151cf  mov     rcx, r15; lpDirectoryName
0x1400151d2  call    cs:__imp_GetDiskFreeSpaceExW
0x1400151d8  lea     rdx, [rbp+780h+var_2F0]
0x1400151df  mov     rcx, r15
0x1400151e2  call    cs:__imp_QueryStorageReserveEx
0x1400151e8  movzx   r13d, r14b
0x1400151ec  mov     eax, [rsi]
0x1400151ee  mov     ecx, 0A00h
0x1400151f3  and     eax, ecx
0x1400151f5  cmp     eax, ecx
0x1400151f7  jnz     short loc_140015218
0x1400151f9  mov     [rbp+780h+var_7FC], r12d
0x1400151fd  lea     r8, [rbp+780h+var_7FC]
0x140015201  xor     edx, edx
0x140015203  lea     ecx, [rdx+2]
0x140015206  call    cs:__imp_GetStoragePolicySettings
0x14001520c  test    eax, eax
0x14001520e  js      short loc_140015218
0x140015210  cmp     [rbp+780h+var_7FC], r14d
0x140015214  cmovz   r13d, r12d
0x140015218  movsxd  rax, dword ptr [rdi+6C8h]
0x14001521f  imul    rdx, rax, 0B0h; uBytes
0x140015226  mov     r14d, 40h ; '@'
0x14001522c  mov     ecx, r14d; uFlags
0x14001522f  call    cs:__imp_LocalAlloc
0x140015235  mov     rbx, rax
0x140015238  mov     [rbp+780h+hMem], rax
0x14001523c  movsxd  rax, dword ptr [rdi+6C8h]
0x140015243  imul    rdx, rax, 110h; uBytes
0x14001524a  mov     ecx, r14d; uFlags
0x14001524d  call    cs:__imp_LocalAlloc
0x140015253  mov     r12, rax
0x140015256  mov     [rbp+780h+var_7B8], rax
0x14001525a  call    cs:__imp_GetTickCount64
0x140015260  mov     [rbp+780h+var_770], rax
0x140015264  xor     r14d, r14d
0x140015267  mov     [rbp+780h+var_7FC], r14d
0x14001526b  movsd   xmm9, cs:__real@408f400000000000
0x140015274  cmp     [rdi+6C8h], r14d
0x14001527b  jle     loc_14001590E
0x140015281  movsd   xmm7, cs:__real@43e0000000000000
0x140015289  mov     qword ptr [rbp+780h+FileTime.dwLowDateTime], 0
0x140015291  mov     [rbp+780h+var_7C8], 0
0x140015299  lea     r9, [rbp+780h+var_758]; lpTotalNumberOfFreeBytes
0x14001529d  lea     r8, [rbp+780h+TotalNumberOfBytes]; lpTotalNumberOfBytes
0x1400152a1  xor     edx, edx; lpFreeBytesAvailableToCaller
0x1400152a3  mov     rcx, r15; lpDirectoryName
0x1400152a6  call    cs:__imp_GetDiskFreeSpaceExW
0x1400152ac  lea     rdx, [rbp+780h+var_3B0]
0x1400152b3  mov     rcx, r15
0x1400152b6  call    cs:__imp_QueryStorageReserveEx
0x1400152bc  movsxd  r12, r14d
0x1400152bf  imul    rsi, r12, 268h
0x1400152c6  mov     rax, [rdi+6D0h]
0x1400152cd  lea     rcx, [rax+258h]
0x1400152d4  add     rcx, rsi
0x1400152d7  lea     rdx, [rax+25Ch]
0x1400152de  add     rdx, rsi
0x1400152e1  lea     r9, [rax+260h]
0x1400152e8  add     r9, rsi
0x1400152eb  lea     r8, [rax+28h]
0x1400152ef  add     r8, rsi
0x1400152f2  lea     rax, [rdi+670h]
0x1400152f9  mov     [rsp+8F0h+var_8B0], rax
0x1400152fe  lea     rax, [rdi+660h]
0x140015305  mov     [rsp+8F0h+var_8B8], rax
0x14001530a  mov     [rsp+8F0h+var_8C0], r15
0x14001530f  mov     [rsp+8F0h+lpThreadId], rcx
0x140015314  mov     qword ptr [rsp+8F0h+dwCreationFlags], rdx
0x140015319  lea     rcx, [rbp+780h+var_6B0]
0x140015320  call    ??$?0AEAY0BAE@GAEAHAEAHAEAHAEAY0BAE@GAEAKAEAH@ClientPurge@CleanupMgrTelemetry@@AEAA@U?$integral_constant@D$0A@@wistd@@AEAY0BAE@GAEAH221AEAK2@Z; CleanupMgrTelemetry::ClientPurge::ClientPurge(wistd::integral_constant<char,0>,ushort (&)[260],int &,int &,int &,ushort (&)[260],ulong &,int &)
0x140015325  nop
0x140015326  test    rbx, rbx
0x140015329  jz      short loc_1400153A4
0x14001532b  imul    rax, r12, 0B0h
0x140015332  add     rbx, rax
0x140015335  mov     rcx, [rdi+6D0h]
0x14001533c  add     rcx, 28h ; '('
0x140015340  add     rcx, rsi
0x140015343  mov     qword ptr [rsp+8F0h+dwCreationFlags], rcx
0x140015348  mov     r9d, 4Fh ; 'O'
0x14001534e  lea     r8, aS; "%-*s"
0x140015355  lea     edx, [r9+1]; unsigned __int64
0x140015359  mov     rcx, rbx; unsigned __int16 *
0x14001535c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140015361  mov     rax, [rdi+6D0h]
0x140015368  mov     ecx, [rax+rsi+260h]
0x14001536f  mov     [rbx+0A0h], ecx
0x140015375  mov     rax, [rdi+6D0h]
0x14001537c  mov     ecx, [rax+rsi+25Ch]
0x140015383  mov     [rbx+0A4h], ecx
0x140015389  mov     rax, [rdi+6D0h]
0x140015390  mov     ecx, [rax+rsi+258h]
0x140015397  mov     [rbx+0A8h], ecx
0x14001539d  mov     [rbx+0ACh], r14d
0x1400153a4  mov     rax, [rdi+6D0h]
0x1400153ab  mov     rdx, [rsi+rax+250h]
0x1400153b3  mov     [rbp+780h+var_788], rdx
0x1400153b7  xor     ebx, ebx
0x1400153b9  test    rdx, rdx
0x1400153bc  jnz     short loc_1400153C1
0x1400153be  inc     [rbp+780h+var_7E4]
0x1400153c1  mov     ecx, [rsi+rax+25Ch]
0x1400153c8  cmp     ecx, 1
0x1400153cb  jnz     short loc_1400153D0
0x1400153cd  inc     [rbp+780h+var_7E8]
0x1400153d0  lea     r8, [rdi+660h]
0x1400153d7  test    dword ptr [r8], 200h
0x1400153de  jz      short loc_140015443
0x1400153e0  cmp     [rsi+rax+260h], ebx
0x1400153e7  jz      short loc_140015417
0x1400153e9  test    rdx, rdx
0x1400153ec  jz      short loc_140015417
0x1400153ee  test    dword ptr [r8], 400h
0x1400153f5  jnz     short loc_140015409
0x1400153f7  cmp     [rdi+668h], ebx
0x1400153fd  jnz     short loc_140015409
0x1400153ff  test    byte ptr [rsi+rax+264h], 2
0x140015407  jnz     short loc_140015417
0x140015409  test    dword ptr [r8], 800h
0x140015410  jz      short loc_140015450
0x140015412  test    r13b, r13b
0x140015415  jz      short loc_140015450
0x140015417  inc     [rbp+780h+var_7F8]
0x14001541a  lea     rcx, [rbp+780h+var_6B0]; this
0x140015421  call    ??1ClientPurge@CleanupMgrTelemetry@@QEAA@XZ; CleanupMgrTelemetry::ClientPurge::~ClientPurge(void)
0x140015426  inc     r14d
0x140015429  mov     [rbp+780h+var_7FC], r14d
0x14001542d  cmp     r14d, [rdi+6C8h]
0x140015434  jge     loc_140015903
0x14001543a  mov     rbx, [rbp+780h+hMem]
0x14001543e  jmp     loc_140015289
0x140015443  cmp     [rsi+rax+258h], ebx
0x14001544a  jz      short loc_140015417
0x14001544c  test    ecx, ecx
0x14001544e  jz      short loc_140015417
0x140015450  mov     r14, rbx
0x140015453  lea     rcx, [rbp+780h+SystemTime]; lpSystemTime
0x14001545a  call    cs:__imp_GetSystemTime
0x140015460  lea     rdx, [rbp+780h+FileTime]; lpFileTime
0x140015464  lea     rcx, [rbp+780h+SystemTime]; lpSystemTime
0x14001546b  call    cs:__imp_SystemTimeToFileTime
0x140015471  mov     rax, [rdi+6D0h]
0x140015478  mov     r8, [rax+rsi+238h]; unsigned __int16 *
0x140015480  test    r8, r8
0x140015483  jz      short loc_1400154BE
0x140015485  mov     edx, 100h; unsigned __int64
0x14001548a  lea     rcx, [rbp+780h+lParam]; unsigned __int16 *
0x140015491  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x140015496  test    dword ptr [rdi+660h], 1220h
0x1400154a0  jnz     short loc_1400154BE
0x1400154a2  lea     r9, [rbp+780h+lParam]; lParam
0x1400154a9  xor     r8d, r8d; wParam
0x1400154ac  mov     edx, 402h; Msg
0x1400154b1  mov     rcx, [rdi+6A0h]; hWnd
0x1400154b8  call    cs:__imp_PostMessageW
0x1400154be  xor     r8d, r8d
0x1400154c1  mov     [rdi+6C0h], r8
0x1400154c8  mov     rcx, [rdi+6D0h]
0x1400154cf  add     rcx, rsi
0x1400154d2  cmp     [rcx+18h], r8
0x1400154d6  jz      loc_14001558A
0x1400154dc  cmp     [rdi+6D8h], r8
0x1400154e3  jz      loc_14001558A
0x1400154e9  inc     [rbp+780h+var_7F4]
0x1400154ec  test    rcx, rcx
0x1400154ef  jz      short loc_1400154F8
0x1400154f1  mov     cs:qword_140021678, rcx
0x1400154f8  call    cs:__imp_GetTickCount64
0x1400154fe  mov     r14, rax
0x140015501  mov     rax, [rdi+6D0h]
0x140015508  mov     rcx, [rax+rsi+18h]
0x14001550d  mov     rax, [rcx]
0x140015510  mov     r8, [rdi+6E0h]
0x140015517  mov     rdx, [rbp+780h+var_788]
0x14001551b  mov     rax, [rax+28h]
0x14001551f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015524  mov     [rbp+780h+var_800], eax
0x140015527  call    cs:__imp_GetTickCount64
0x14001552d  mov     rbx, rax
0x140015530  cmp     [rbp+780h+var_800], 0
0x140015534  jge     short loc_140015543
0x140015536  inc     [rbp+780h+var_7DC]
0x140015539  mov     dword ptr [rdi+65Ch], 2
0x140015543  mov     rcx, [rdi+6D0h]
0x14001554a  mov     rcx, [rcx+rsi+18h]
0x14001554f  mov     rdx, [rcx]
0x140015552  mov     rax, [rdx+20h]
0x140015556  mov     r8, [rdi+6E0h]
  ... truncated ...
```
