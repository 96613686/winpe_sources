# KernelDumpTargetInfo::DumpWritePhysicalMemoryToFile(void *,DUMP_WRITE_ARGS *,void *,int)

- ea: `0x1800e770c`
- end: `0x1800e83b3`
- name: `?DumpWritePhysicalMemoryToFile@KernelDumpTargetInfo@@QEAAJPEAXPEAUDUMP_WRITE_ARGS@@0H@Z`
- size: `3239`
- prototype: `__int64 __fastcall(KernelDumpTargetInfo *__hidden this, void *, struct DUMP_WRITE_ARGS *, void *, int)`
- caller_count: `5`
- callee_count: `14`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180215508`
- `0x18021a580`
- `0x18021a980`
- `0x18021adb0`
- `0x18021b080`

## callees

- `0x180071a60`
- `0x1800727b8`
- `0x1800793cc`
- `0x1800797ec`
- `0x18008534c`
- `0x1800954c4`
- `0x18009599c`
- `0x180096320`
- `0x180098468`
- `0x1800b94c4`
- `0x1800e770c`
- `0x1800e8b30`
- `0x18038605c`
- `0x1804f4010`

## import_xrefs

- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800e7862`
- `api-ms-win-crt-heap-l1-1-0!malloc` at `0x1800e7862`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e8373`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1800e8373`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e77f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e780c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7d2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e77f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e780c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7caf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7cbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800e7d2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8364`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800e8364`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e7d00`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x1800e7d00`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800e7c9e`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x1800e7c9e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e77d5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800e77d5`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800e79ba`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800e7f36`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800e79ba`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x1800e7f36`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e7759`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e79ca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e7f46`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e7759`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e79ca`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800e7f46`

## string_xrefs

- `0x1800e783e`: `Unable to open physical memory file '%s' - %s\n    "%s"\n`
- `0x1800e7969`: `Restarting %d page block reads at physical address 0x%I64X.\n`
- `0x1800e7dd1`: `Failed reading 0x%X bytes at physical address 0x%I64X, %s.\n`
- `0x1800e7e48`: `Page read at physical address 0x%I64X failed with %s, writing a page filled with 0xdeadfeed in its place.\n`
- `0x1800e834b`: `Wrote %d %s of 0xdeadfeed into this dump file for memory that could not be\nread successfully by the kernel memory manager.  The kernel memory manager can\nnot read pages that have a held page lock, are on the failed memory page list,\nor which have been hot removed from the system.\n`

## pseudocode

```c
__int64 __fastcall KernelDumpTargetInfo::DumpWritePhysicalMemoryToFile(
        KernelDumpTargetInfo *this,
        void *a2,
        struct DUMP_WRITE_ARGS *a3,
        _QWORD *a4,
        int a5)
{
  HANDLE v5; // r15
  __int64 v6; // rsi
  __int64 v9; // r12
  const WCHAR *v10; // rcx
  void *v11; // r13
  int *v12; // r8
  unsigned __int16 **v13; // r9
  unsigned int v14; // ebx
  signed int v15; // eax
  const unsigned __int16 *v16; // rdi
  unsigned __int16 *v17; // rax
  int v18; // ecx
  unsigned __int64 v19; // rdx
  char *v20; // r14
  char *v21; // r11
  unsigned int v22; // ebx
  unsigned int v23; // eax
  unsigned int v24; // r10d
  unsigned int *v25; // rdi
  __int64 v26; // r9
  unsigned __int64 v27; // r13
  unsigned __int64 v28; // r15
  __int64 v29; // r9
  __int64 v30; // r11
  __int64 v31; // rdx
  unsigned __int64 v32; // rcx
  unsigned __int64 v33; // r14
  __int64 v34; // rdx
  unsigned int v35; // edi
  LONGLONG v36; // rax
  LONGLONG v37; // rdx
  __int64 v38; // rcx
  LARGE_INTEGER v39; // rcx
  __int64 v40; // rdi
  LARGE_INTEGER v41; // rcx
  unsigned __int64 v42; // rax
  unsigned __int64 v43; // r9
  _DWORD *v44; // rdi
  unsigned __int64 v45; // rcx
  HANDLE v46; // rbx
  signed int LastError; // eax
  __int64 v48; // r9
  unsigned __int16 *v49; // rax
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // r8
  __int64 v53; // r9
  unsigned __int16 *v54; // rax
  unsigned __int64 v55; // rdx
  void *v56; // r8
  LARGE_INTEGER v57; // r14
  unsigned __int64 v58; // rsi
  double v59; // xmm1_8
  LARGE_INTEGER v60; // rdi
  LARGE_INTEGER v61; // rdi
  LARGE_INTEGER v62; // rdi
  LARGE_INTEGER v63; // rcx
  unsigned __int64 v64; // rdi
  double v65; // xmm1_8
  const wchar_t *v66; // r8
  __int64 v67; // rdx
  __int64 v68; // rcx
  __int64 v69; // r8
  __int64 v70; // r9
  DWORD dwCreationDisposition[2]; // [rsp+28h] [rbp-81h]
  int hTemplateFile; // [rsp+38h] [rbp-71h]
  LARGE_INTEGER PerformanceCount; // [rsp+48h] [rbp-61h] BYREF
  LPVOID lpBuffer; // [rsp+50h] [rbp-59h]
  HANDLE hFile; // [rsp+58h] [rbp-51h]
  unsigned int v77; // [rsp+60h] [rbp-49h]
  unsigned int v78; // [rsp+64h] [rbp-45h]
  LARGE_INTEGER Frequency; // [rsp+68h] [rbp-41h] BYREF
  LARGE_INTEGER v80; // [rsp+70h] [rbp-39h] BYREF
  unsigned int v81; // [rsp+78h] [rbp-31h]
  unsigned int v82; // [rsp+7Ch] [rbp-2Dh]
  LONG DistanceToMoveHigh; // [rsp+80h] [rbp-29h] BYREF
  unsigned int v84; // [rsp+84h] [rbp-25h]
  unsigned __int64 v85; // [rsp+88h] [rbp-21h]
  unsigned __int64 v86; // [rsp+90h] [rbp-19h]
  char *v87; // [rsp+98h] [rbp-11h]
  char *v88; // [rsp+A0h] [rbp-9h]
  LARGE_INTEGER v89; // [rsp+A8h] [rbp-1h]
  KernelDumpTargetInfo *NumberOfBytesRead; // [rsp+108h] [rbp+5Fh] BYREF
  void *v91; // [rsp+110h] [rbp+67h]
  unsigned int v92; // [rsp+118h] [rbp+6Fh]

  v91 = a2;
  NumberOfBytesRead = this;
  v5 = 0;
  Frequency.QuadPart = 0;
  PerformanceCount.QuadPart = 0;
  v6 = 0;
  hFile = 0;
  v80.QuadPart = 0;
  v78 = 0;
  QueryPerformanceCounter(&PerformanceCount);
  v89 = PerformanceCount;
  if ( g_Target && *((_DWORD *)g_Target + 1026) == 1 && !*((_DWORD *)g_Target + 1027) )
  {
    v9 = *((_QWORD *)g_Target + 530);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 72LL))(v9);
  }
  else
  {
    v9 = 0;
  }
  v10 = (const WCHAR *)*((_QWORD *)a3 + 10);
  if ( !v10
    || (hFile = CreateFileW(v10, 0x80000000, 1u, 0, 3u, 0x80u, 0),
        (((unsigned __int64)hFile + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0) )
  {
    lpBuffer = malloc((unsigned int)(32 * *((_DWORD *)g_Machine + 8)));
    v11 = lpBuffer;
    if ( !lpBuffer )
    {
      ErrOut(L"Unable to allocate page buffer\n");
      v14 = -2147024882;
LABEL_98:
      v5 = hFile;
      goto LABEL_99;
    }
    v18 = a5;
    v81 = 0;
    if ( a5 )
    {
      v19 = a4[1];
      v20 = (char *)(a4 + 2);
      v87 = (char *)(a4 + 2);
    }
    else
    {
      v19 = *((unsigned int *)a4 + 1);
      v20 = 0;
      v87 = 0;
    }
    v86 = v19;
    v21 = 0;
    v22 = 0;
    if ( !a5 )
      v21 = (char *)(a4 + 1);
    v77 = 0;
    v23 = *(_DWORD *)a4;
    v24 = 0;
    v25 = (unsigned int *)g_Machine;
    v88 = v21;
    v84 = v23;
LABEL_21:
    v82 = v24;
    if ( v24 >= v23 )
    {
      v14 = 0;
LABEL_97:
      v11 = lpBuffer;
      goto LABEL_98;
    }
    if ( v18 )
    {
      v27 = MachineInfo::SwapEnd64((MachineInfo *)v25, *(_QWORD *)&v20[16 * v24 + 8]);
      v28 = v25[8] * MachineInfo::SwapEnd64((MachineInfo *)v25, *(_QWORD *)&v20[8 * v26]);
    }
    else
    {
      v27 = MachineInfo::SwapEnd32((MachineInfo *)v25, *(_DWORD *)&v21[8 * v24 + 4]);
      v28 = v25[8] * (unsigned __int64)MachineInfo::SwapEnd32((MachineInfo *)v25, *(_DWORD *)(v30 + 8 * v29));
    }
    v31 = 0;
    v32 = 0;
    v92 = 0;
    v85 = 0;
    LODWORD(v33) = 32;
    while ( 1 )
    {
      if ( !v27 )
      {
        v18 = a5;
        v24 = v82 + 1;
        v21 = v88;
        v20 = v87;
        v23 = v84;
        goto LABEL_21;
      }
      if ( v27 == v32 && (_DWORD)v31 )
      {
        v92 = 0;
        v85 = 0;
        LODWORD(v33) = v31;
        VerbOut(L"Restarting %d page block reads at physical address 0x%I64X.\n", v31, v28);
        v25 = (unsigned int *)g_Machine;
      }
      if ( v27 < (unsigned int)v33 )
        LODWORD(v33) = v27;
      if ( CheckUserInterruptInternal(0) )
      {
        ErrOut(L"--Interrupt\n");
        v14 = -805306054;
        goto LABEL_97;
      }
      if ( 100 * v6 / v86 == v22 )
      {
        QueryPerformanceFrequency(&Frequency);
        QueryPerformanceCounter(&v80);
        PerformanceCount.QuadPart = (v80.QuadPart - PerformanceCount.QuadPart) * (100 - v22) / ++Frequency.QuadPart;
        dprintf(L"%d%% written.", v22);
        v35 = v22 - v81;
        if ( v22 == v81 )
        {
          dprintf(L"\n", v34);
        }
        else
        {
          v36 = PerformanceCount.QuadPart / v35;
          v37 = PerformanceCount.QuadPart % v35;
          PerformanceCount.QuadPart = v36;
          v38 = v36;
          if ( v36 >= 86400 )
          {
            dprintf(L" %I64d day", v36 / 86400);
            v39 = PerformanceCount;
            if ( PerformanceCount.QuadPart >= 172800 )
            {
              dprintf(L"s");
              v39 = PerformanceCount;
            }
            v37 = v39.QuadPart / -86400;
            v38 = v39.QuadPart % -86400;
            PerformanceCount.QuadPart = v38;
          }
          v40 = v38;
          if ( v38 >= 3600 )
          {
            dprintf(L" %I64d hr", v38 / 3600);
            v41 = PerformanceCount;
            if ( PerformanceCount.QuadPart >= 7200 )
            {
              dprintf(L"s");
              v41 = PerformanceCount;
            }
            v37 = v41.QuadPart / -3600;
            v38 = v41.QuadPart % -3600;
            PerformanceCount.QuadPart = v38;
            v40 = v38;
          }
          if ( v40 >= 60 )
          {
            dprintf(L" %I64d min", v40 / 60);
            v37 = ((unsigned __int64)(((unsigned __int128)(PerformanceCount.QuadPart * (__int128)0x7777777777777777LL) >> 64)
                                    - PerformanceCount.QuadPart) >> 63)
                + ((__int64)(((unsigned __int128)(PerformanceCount.QuadPart * (__int128)0x7777777777777777LL) >> 64)
                           - PerformanceCount.QuadPart) >> 5);
            v38 = 60 * v37 + PerformanceCount.QuadPart;
            PerformanceCount.QuadPart = v38;
            v40 = v38;
          }
          if ( v40 > 0 )
            dprintf(L" %I64d sec", v38);
          dprintf(L" remaining.\n", v37);
        }
        PerformanceCount = v80;
        v81 = v22;
        FlushCallbacks();
        if ( !hFile && (!v9 || !*(_BYTE *)(v9 + 36)) )
        {
          v25 = (unsigned int *)g_Machine;
          v77 = v22 + 1;
          LODWORD(NumberOfBytesRead) = 0;
          goto LABEL_53;
        }
        v25 = (unsigned int *)g_Machine;
        v77 = v22 + 5;
      }
      v46 = hFile;
      LODWORD(NumberOfBytesRead) = 0;
      if ( hFile )
      {
        DistanceToMoveHigh = HIDWORD(v28);
        if ( SetFilePointer(hFile, v28, &DistanceToMoveHigh, 0) == -1 && GetLastError()
          || !ReadFile(v46, lpBuffer, *((_DWORD *)g_Machine + 8) * v33, (LPDWORD)&NumberOfBytesRead, 0) )
        {
          if ( !GetLastError() )
          {
            v14 = -2147467259;
LABEL_66:
            v44 = lpBuffer;
            goto LABEL_79;
          }
          LastError = GetLastError();
          v14 = LastError;
          if ( LastError > 0 )
            v14 = (unsigned __int16)LastError | 0x80070000;
LABEL_73:
          if ( !v14 )
            goto LABEL_91;
          goto LABEL_66;
        }
        v45 = (unsigned int)(*((_DWORD *)g_Machine + 8) * v33);
        if ( (unsigned int)NumberOfBytesRead >= (unsigned int)v45 )
        {
          v14 = 0;
          goto LABEL_73;
        }
        v44 = lpBuffer;
        goto LABEL_78;
      }
LABEL_53:
      if ( !v9 || !*(_BYTE *)(v9 + 36) || (v42 = *(_QWORD *)(v9 + 40), v28 >= v42) )
      {
        v48 = v25[8];
        LODWORD(v33) = 1;
        v44 = lpBuffer;
        LOBYTE(hTemplateFile) = 0;
        dwCreationDisposition[0] = 0;
        v14 = (*(__int64 (__fastcall **)(TargetInfo *, unsigned __int64, LPVOID, __int64, DWORD *, KernelDumpTargetInfo **, int))(*(_QWORD *)g_Target + 312LL))(
                g_Target,
                v28,
                lpBuffer,
                v48,
                *(DWORD **)dwCreationDisposition,
                &NumberOfBytesRead,
                hTemplateFile);
        if ( v14 )
          goto LABEL_79;
        v45 = *((unsigned int *)g_Machine + 8);
LABEL_77:
        if ( (unsigned int)NumberOfBytesRead >= (unsigned int)v45 )
          goto LABEL_91;
LABEL_78:
        v14 = -2147024866;
        goto LABEL_79;
      }
      v43 = v25[8];
      if ( v28 + (unsigned int)v33 * v25[8] > v42 )
        v33 = (v42 - v28) / v43;
      v44 = lpBuffer;
      v14 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, LPVOID, _QWORD, KernelDumpTargetInfo **))(*(_QWORD *)v9 + 64LL))(
              v9,
              v28,
              lpBuffer,
              (unsigned int)(v33 * v43),
              &NumberOfBytesRead);
      if ( !v14 )
      {
        v45 = (unsigned int)(*((_DWORD *)g_Machine + 8) * v33);
        goto LABEL_77;
      }
LABEL_79:
      v49 = FormatStatusCode(v14);
      VerbOut(
        L"Failed reading 0x%X bytes at physical address 0x%I64X, %s.\n",
        (unsigned int)(*((_DWORD *)g_Machine + 8) * v33),
        v28,
        v49);
      if ( v14 == 10060 )
        goto LABEL_97;
      if ( (unsigned int)v33 > 1 )
      {
        v25 = (unsigned int *)g_Machine;
        v31 = (unsigned int)v33;
        v32 = v27 - (unsigned int)v33;
        v92 = v33;
        v85 = v32;
        ++v27;
        LODWORD(v33) = 1;
        goto LABEL_93;
      }
      ++v78;
      FeatureUsageTracker::FeatureUsed(L"KernelDump", L"FixupMissingPage", 1u);
      if ( (_DWORD)v33 != 1 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v51, v50, v52, v53);
      v54 = FormatStatusCode(v14);
      VerbOut(
        L"Page read at physical address 0x%I64X failed with %s, writing a page filled with 0xdeadfeed in its place.\n",
        v28,
        v54);
      v55 = (unsigned __int64)*((unsigned int *)g_Machine + 8) >> 2;
      if ( v55 )
      {
        if ( ((unsigned __int8)v44 & 4) == 0 )
        {
          v56 = v44;
LABEL_89:
          memset64(v56, 0xDEADFEEDDEADFEEDuLL, v55 >> 1);
          v45 = 0;
          if ( (v55 & 1) != 0 )
            *((_DWORD *)v56 + v55 - 1) = -559022355;
          goto LABEL_91;
        }
        *v44 = -559022355;
        if ( --v55 )
        {
          v56 = v44 + 1;
          goto LABEL_89;
        }
      }
LABEL_91:
      v14 = DumpTargetInfo::DumpWriteFile((DumpTargetInfo *)v45, v91, lpBuffer, *((_DWORD *)g_Machine + 8) * v33);
      if ( v14 )
        goto LABEL_97;
      v25 = (unsigned int *)g_Machine;
      v32 = v85;
      v31 = v92;
      v28 += (unsigned int)(*((_DWORD *)g_Machine + 8) * v33);
      v6 += (unsigned int)v33;
LABEL_93:
      v22 = v77;
      v27 -= (unsigned int)v33;
    }
  }
  v11 = 0;
  if ( GetLastError() )
  {
    v15 = GetLastError();
    v14 = v15;
    if ( v15 > 0 )
      v14 = (unsigned __int16)v15 | 0x80070000;
  }
  else
  {
    v14 = -2147467259;
  }
  v16 = FormatAnyStatus(v14, 0, v12, v13);
  v17 = FormatStatusCode(v14);
  ErrOut(L"Unable to open physical memory file '%s' - %s\n    \"%s\"\n", *((_QWORD *)a3 + 10), v17, v16);
LABEL_99:
  QueryPerformanceFrequency(&Frequency);
  QueryPerformanceCounter(&v80);
  v57 = v89;
  ++Frequency.QuadPart;
  v58 = v6 << 12;
  PerformanceCount.QuadPart = (v80.QuadPart - v89.QuadPart) / Frequency.QuadPart;
  dprintf(L"Wrote", (v80.QuadPart - v89.QuadPart) % Frequency.QuadPart);
  if ( v58 <= 0x10000000000LL )
  {
    if ( v58 <= 0x40000000 )
    {
      if ( v58 <= 0x100000 )
      {
        if ( v58 > 0x400 )
          dprintf(L" %.1f KB", (double)(int)v58 * 0.0009765625 + 0.05);
      }
      else
      {
        dprintf(L" %.1f MB", (double)(int)v58 * 0.00000095367431640625 + 0.05);
      }
    }
    else
    {
      dprintf(L" %.1f GB", (double)(int)v58 * 9.313225746154785e-10 + 0.05);
    }
  }
  else
  {
    if ( (v58 & 0x8000000000000000uLL) != 0LL )
      v59 = (double)(int)(v58 & 1 | (v58 >> 1)) + (double)(int)(v58 & 1 | (v58 >> 1));
    else
      v59 = (double)(int)v58;
    dprintf(L" %.1f TB", v59 * 9.094947017729282e-13 + 0.05);
  }
  dprintf(L" in");
  v60 = PerformanceCount;
  if ( PerformanceCount.QuadPart >= 86400 )
  {
    dprintf(L" %I64d day", PerformanceCount.QuadPart / 86400);
    v61 = PerformanceCount;
    if ( PerformanceCount.QuadPart >= 172800 )
    {
      dprintf(L"s");
      v61 = PerformanceCount;
    }
    v60.QuadPart = v61.QuadPart % -86400;
    PerformanceCount = v60;
  }
  if ( v60.QuadPart >= 3600 )
  {
    dprintf(L" %I64d hr", v60.QuadPart / 3600);
    v62 = PerformanceCount;
    if ( PerformanceCount.QuadPart >= 7200 )
    {
      dprintf(L"s");
      v62 = PerformanceCount;
    }
    v60.QuadPart = v62.QuadPart % -3600;
    PerformanceCount = v60;
  }
  if ( v60.QuadPart >= 60 )
  {
    dprintf(
      L" %I64d min",
      v60.QuadPart / 60
    + ((unsigned __int64)(v60.QuadPart
                        + ((unsigned __int128)(v60.QuadPart * (__int128)(__int64)0x8888888888888889uLL) >> 64)) >> 63));
    v60.QuadPart = 60
                 * (((unsigned __int64)(((unsigned __int128)(PerformanceCount.QuadPart * (__int128)0x7777777777777777LL) >> 64)
                                      - PerformanceCount.QuadPart) >> 63)
                  + ((__int64)(((unsigned __int128)(PerformanceCount.QuadPart * (__int128)0x7777777777777777LL) >> 64)
                             - PerformanceCount.QuadPart) >> 5))
                 + PerformanceCount.QuadPart;
    PerformanceCount = v60;
  }
  if ( v60.QuadPart > 0 )
    dprintf(L" %I64d sec", v60.QuadPart);
  dprintf(L".\n");
  PerformanceCount.QuadPart = (v80.QuadPart - v57.QuadPart) / Frequency.QuadPart;
  v63 = PerformanceCount;
  if ( !PerformanceCount.QuadPart )
  {
    PerformanceCount.QuadPart = 1;
    v63.QuadPart = 1;
  }
  v64 = v58 / v63.QuadPart;
  dprintf(L"The average transfer rate was", v58 % v63.QuadPart);
  if ( v64 <= 0x40000000 )
  {
    if ( v64 <= 0x100000 )
    {
      if ( v64 > 0x400 )
        dprintf(L" %.1f KB", (double)(int)v64 * 0.0009765625 + 0.05);
    }
    else
    {
      dprintf(L" %.1f MB", (double)(int)v64 * 0.00000095367431640625 + 0.05);
    }
  }
  else
  {
    if ( (v64 & 0x8000000000000000uLL) != 0LL )
      v65 = (double)(int)(v64 & 1 | (v64 >> 1)) + (double)(int)(v64 & 1 | (v64 >> 1));
    else
      v65 = (double)(int)v64;
    dprintf(L" %.1f GB", v65 * 9.313225746154785e-10 + 0.05);
  }
  dprintf(L"/s.\n");
  if ( v78 )
  {
    v66 = L"page";
    if ( v78 != 1 )
      v66 = L"pages";
    dprintf(
      L"Wrote %d %s of 0xdeadfeed into this dump file for memory that could not be\n"
       "read successfully by the kernel memory manager.  The kernel memory manager can\n"
       "not read pages that have a held page lock, are on the failed memory page list,\n"
       "or which have been hot removed from the system.\n",
      v78,
      v66);
  }
  FlushCallbacks();
  if ( v5 )
    CloseHandle(v5);
  free(v11);
  if ( v14 && v14 != -805306054 )
    MicrosoftTelemetryAssertTriggeredNoArgs(v68, v67, v69, v70);
  return v14;
}

```

## disassembly

```asm
0x1800e770c  mov     rax, rsp
0x1800e770f  mov     [rax+20h], rbx
0x1800e7713  mov     [rax+10h], rdx
0x1800e7717  mov     [rax+8], rcx
0x1800e771b  push    rbp
0x1800e771c  push    rsi
0x1800e771d  push    rdi
0x1800e771e  push    r12
0x1800e7720  push    r13
0x1800e7722  push    r14
0x1800e7724  push    r15
0x1800e7726  lea     rbp, [rax-57h]
0x1800e772a  sub     rsp, 0C0h
0x1800e7731  xor     r15d, r15d
0x1800e7734  movaps  xmmword ptr [rax-48h], xmm6
0x1800e7738  lea     rcx, [rbp+4Fh+PerformanceCount]; lpPerformanceCount
0x1800e773c  mov     qword ptr [rbp+4Fh+Frequency], r15
0x1800e7740  mov     qword ptr [rbp+4Fh+PerformanceCount], r15
0x1800e7744  mov     esi, r15d
0x1800e7747  mov     [rbp+4Fh+hFile], r15
0x1800e774b  mov     rdi, r9
0x1800e774e  mov     qword ptr [rbp+4Fh+var_88], r15
0x1800e7752  mov     r14, r8
0x1800e7755  mov     [rbp+4Fh+var_94], r15d
0x1800e7759  call    cs:__imp_QueryPerformanceCounter
0x1800e7760  nop     dword ptr [rax+rax+00h]
0x1800e7765  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e7769  mov     [rbp+4Fh+var_50], rax
0x1800e776d  mov     rax, cs:?g_Target@@3PEAVTargetInfo@@EA; TargetInfo * g_Target
0x1800e7774  test    rax, rax
0x1800e7777  jz      short loc_1800E77A4
0x1800e7779  cmp     dword ptr [rax+1008h], 1
0x1800e7780  jnz     short loc_1800E77A4
0x1800e7782  cmp     [rax+100Ch], r15d
0x1800e7789  jnz     short loc_1800E77A4
0x1800e778b  mov     r12, [rax+1090h]
0x1800e7792  mov     rcx, r12
0x1800e7795  mov     rax, [r12]
0x1800e7799  mov     rax, [rax+48h]
0x1800e779d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e77a2  jmp     short loc_1800E77A7
0x1800e77a4  mov     r12, r15
0x1800e77a7  mov     rcx, [r14+50h]; lpFileName
0x1800e77ab  test    rcx, rcx
0x1800e77ae  jz      loc_1800E7855
0x1800e77b4  xor     r9d, r9d; lpSecurityAttributes
0x1800e77b7  mov     qword ptr [rsp+0F0h+hTemplateFile], r15; hTemplateFile
0x1800e77bc  mov     [rsp+0F0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800e77c4  mov     edx, 80000000h; dwDesiredAccess
0x1800e77c9  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800e77d1  lea     r8d, [r9+1]; dwShareMode
0x1800e77d5  call    cs:__imp_CreateFileW
0x1800e77dc  nop     dword ptr [rax+rax+00h]
0x1800e77e1  mov     [rbp+4Fh+hFile], rax
0x1800e77e5  lea     rcx, [rax+1]
0x1800e77e9  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800e77f0  jnz     short loc_1800E7855
0x1800e77f2  mov     r13, r15
0x1800e77f5  call    cs:__imp_GetLastError
0x1800e77fc  nop     dword ptr [rax+rax+00h]
0x1800e7801  test    eax, eax
0x1800e7803  jnz     short loc_1800E780C
0x1800e7805  mov     ebx, 80004005h
0x1800e780a  jmp     short loc_1800E7827
0x1800e780c  call    cs:__imp_GetLastError
0x1800e7813  nop     dword ptr [rax+rax+00h]
0x1800e7818  mov     ebx, eax
0x1800e781a  test    eax, eax
0x1800e781c  jle     short loc_1800E7827
0x1800e781e  movzx   ebx, ax
0x1800e7821  or      ebx, 80070000h
0x1800e7827  xor     edx, edx; Arguments
0x1800e7829  mov     ecx, ebx; dwMessageId
0x1800e782b  call    ?FormatAnyStatus@@YAPEBGJPEAXPEAHPEAPEAG@Z; FormatAnyStatus(long,void *,int *,ushort * *)
0x1800e7830  mov     ecx, ebx; int
0x1800e7832  mov     rdi, rax
0x1800e7835  call    ?FormatStatusCode@@YAPEAGJ@Z; FormatStatusCode(long)
0x1800e783a  mov     rdx, [r14+50h]
0x1800e783e  lea     rcx, aUnableToOpenPh; "Unable to open physical memory file '%s"...
0x1800e7845  mov     r9, rdi
0x1800e7848  mov     r8, rax
0x1800e784b  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e7850  jmp     loc_1800E7F32
0x1800e7855  mov     rax, cs:?g_Machine@@3PEAVMachineInfo@@EA; MachineInfo * g_Machine
0x1800e785c  mov     ecx, [rax+20h]
0x1800e785f  shl     ecx, 5; Size
0x1800e7862  call    cs:__imp_malloc
0x1800e7869  nop     dword ptr [rax+rax+00h]
0x1800e786e  mov     [rbp+4Fh+lpBuffer], rax
0x1800e7872  mov     r13, rax
0x1800e7875  test    rax, rax
0x1800e7878  jnz     short loc_1800E7890
0x1800e787a  lea     rcx, aUnableToAlloca_4; "Unable to allocate page buffer\n"
0x1800e7881  call    ?ErrOut@@YAXPEBGZZ; ErrOut(ushort const *,...)
0x1800e7886  mov     ebx, 8007000Eh
0x1800e788b  jmp     loc_1800E7F2E
0x1800e7890  mov     ecx, [rbp+4Fh+arg_20]
0x1800e7893  lea     rax, [rdi+8]
0x1800e7897  mov     [rbp+4Fh+var_80], r15d
0x1800e789b  test    ecx, ecx
0x1800e789d  jz      short loc_1800E78AC
0x1800e789f  mov     rdx, [rax]
0x1800e78a2  lea     r14, [rdi+10h]
0x1800e78a6  mov     [rbp+4Fh+var_60], r14
0x1800e78aa  jmp     short loc_1800E78B6
0x1800e78ac  mov     edx, [rdi+4]
0x1800e78af  mov     r14, r15
0x1800e78b2  mov     [rbp+4Fh+var_60], r15
0x1800e78b6  test    ecx, ecx
0x1800e78b8  mov     [rbp+4Fh+var_68], rdx
0x1800e78bc  mov     r11, r15
0x1800e78bf  mov     ebx, r15d
0x1800e78c2  cmovz   r11, rax
0x1800e78c6  mov     [rbp+4Fh+var_98], ebx
0x1800e78c9  mov     eax, [rdi]
0x1800e78cb  mov     r10d, r15d
0x1800e78ce  mov     rdi, cs:?g_Machine@@3PEAVMachineInfo@@EA; MachineInfo * g_Machine
0x1800e78d5  mov     [rbp+4Fh+var_58], r11
0x1800e78d9  mov     [rbp+4Fh+var_74], eax
0x1800e78dc  mov     [rbp+4Fh+var_7C], r10d
0x1800e78e0  cmp     r10d, eax
0x1800e78e3  jnb     loc_1800E7F27
0x1800e78e9  test    ecx, ecx
0x1800e78eb  mov     r9d, r10d
0x1800e78ee  mov     rcx, rdi; this
0x1800e78f1  jz      short loc_1800E791B
0x1800e78f3  add     r9, r9
0x1800e78f6  mov     rdx, [r14+r9*8+8]; unsigned __int64
0x1800e78fb  call    ?SwapEnd64@MachineInfo@@QEAA_K_K@Z; MachineInfo::SwapEnd64(unsigned __int64)
0x1800e7900  mov     rdx, [r14+r9*8]; unsigned __int64
0x1800e7904  mov     rcx, rdi; this
0x1800e7907  mov     r13, rax
0x1800e790a  call    ?SwapEnd64@MachineInfo@@QEAA_K_K@Z; MachineInfo::SwapEnd64(unsigned __int64)
0x1800e790f  mov     ecx, [rdi+20h]
0x1800e7912  mov     r15, rax
0x1800e7915  imul    r15, rcx
0x1800e7919  jmp     short loc_1800E793E
0x1800e791b  mov     edx, [r11+r9*8+4]; unsigned int
0x1800e7920  call    ?SwapEnd32@MachineInfo@@QEAAKK@Z; MachineInfo::SwapEnd32(ulong)
0x1800e7925  mov     edx, [r11+r9*8]; unsigned int
0x1800e7929  mov     rcx, rdi; this
0x1800e792c  mov     r13d, eax
0x1800e792f  call    ?SwapEnd32@MachineInfo@@QEAAKK@Z; MachineInfo::SwapEnd32(ulong)
0x1800e7934  mov     r15d, eax
0x1800e7937  mov     eax, [rdi+20h]
0x1800e793a  imul    r15, rax
0x1800e793e  xor     edx, edx
0x1800e7940  xor     ecx, ecx
0x1800e7942  mov     [rbp+4Fh+arg_10], edx
0x1800e7945  mov     [rbp+4Fh+var_70], rcx
0x1800e7949  lea     r14d, [rdx+20h]
0x1800e794d  test    r13, r13
0x1800e7950  jz      loc_1800E7EF7
0x1800e7956  cmp     r13, rcx
0x1800e7959  jnz     short loc_1800E7987
0x1800e795b  test    edx, edx
0x1800e795d  jz      short loc_1800E7987
0x1800e795f  mov     r8, r15
0x1800e7962  mov     [rbp+4Fh+arg_10], 0
0x1800e7969  lea     rcx, aRestartingDPag; "Restarting %d page block reads at physi"...
0x1800e7970  mov     [rbp+4Fh+var_70], 0
0x1800e7978  mov     r14d, edx
0x1800e797b  call    ?VerbOut@@YAXPEBGZZ; VerbOut(ushort const *,...)
0x1800e7980  mov     rdi, cs:?g_Machine@@3PEAVMachineInfo@@EA; MachineInfo * g_Machine
0x1800e7987  mov     eax, r14d
0x1800e798a  cmp     r13, rax
0x1800e798d  jnb     short loc_1800E7992
0x1800e798f  mov     r14d, r13d
0x1800e7992  xor     ecx, ecx; unsigned __int8
0x1800e7994  call    ?CheckUserInterruptInternal@@YAKE@Z; CheckUserInterruptInternal(uchar)
0x1800e7999  test    eax, eax
0x1800e799b  jnz     loc_1800E7F14
0x1800e79a1  imul    rax, rsi, 64h ; 'd'
0x1800e79a5  xor     edx, edx
0x1800e79a7  mov     ecx, ebx
0x1800e79a9  div     [rbp+4Fh+var_68]
0x1800e79ad  cmp     rax, rcx
0x1800e79b0  jnz     loc_1800E7C73
0x1800e79b6  lea     rcx, [rbp+4Fh+Frequency]; lpFrequency
0x1800e79ba  call    cs:__imp_QueryPerformanceFrequency
0x1800e79c1  nop     dword ptr [rax+rax+00h]
0x1800e79c6  lea     rcx, [rbp+4Fh+var_88]; lpPerformanceCount
0x1800e79ca  call    cs:__imp_QueryPerformanceCounter
0x1800e79d1  nop     dword ptr [rax+rax+00h]
0x1800e79d6  mov     rcx, qword ptr [rbp+4Fh+Frequency]
0x1800e79da  mov     eax, 64h ; 'd'
0x1800e79df  mov     rdx, qword ptr [rbp+4Fh+var_88]
0x1800e79e3  sub     eax, ebx
0x1800e79e5  sub     rdx, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e79e9  inc     rcx
0x1800e79ec  imul    rax, rdx
0x1800e79f0  mov     qword ptr [rbp+4Fh+Frequency], rcx
0x1800e79f4  mov     edi, ebx
0x1800e79f6  cqo
0x1800e79f8  idiv    rcx
0x1800e79fb  mov     edx, ebx
0x1800e79fd  lea     rcx, aDWritten; "%d%% written."
0x1800e7a04  mov     qword ptr [rbp+4Fh+PerformanceCount], rax
0x1800e7a08  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7a0d  sub     edi, [rbp+4Fh+var_80]
0x1800e7a10  jz      loc_1800E7B96
0x1800e7a16  mov     rax, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e7a1a  mov     ecx, edi
0x1800e7a1c  cqo
0x1800e7a1e  idiv    rcx
0x1800e7a21  mov     qword ptr [rbp+4Fh+PerformanceCount], rax
0x1800e7a25  mov     rcx, rax
0x1800e7a28  cmp     rax, 15180h
0x1800e7a2e  jl      short loc_1800E7A9D
0x1800e7a30  mov     rax, 1845C8A0CE512957h
0x1800e7a3a  imul    rcx
0x1800e7a3d  lea     rcx, aI64dDay; " %I64d day"
0x1800e7a44  sar     rdx, 0Dh
0x1800e7a48  mov     rax, rdx
0x1800e7a4b  shr     rax, 3Fh
0x1800e7a4f  add     rdx, rax
0x1800e7a52  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7a57  mov     rcx, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e7a5b  cmp     rcx, 2A300h
0x1800e7a62  jl      short loc_1800E7A74
0x1800e7a64  lea     rcx, aS_28; "s"
0x1800e7a6b  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7a70  mov     rcx, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e7a74  mov     rax, 0E7BA375F31AED6A9h
0x1800e7a7e  imul    rcx
0x1800e7a81  sar     rdx, 0Dh
0x1800e7a85  mov     rax, rdx
0x1800e7a88  shr     rax, 3Fh
0x1800e7a8c  add     rdx, rax
0x1800e7a8f  imul    rax, rdx, 15180h
0x1800e7a96  add     rcx, rax
0x1800e7a99  mov     qword ptr [rbp+4Fh+PerformanceCount], rcx
0x1800e7a9d  mov     rdi, rcx
0x1800e7aa0  cmp     rcx, 0E10h
0x1800e7aa7  jl      short loc_1800E7B19
0x1800e7aa9  mov     rax, 48D159E26AF37C05h
0x1800e7ab3  lea     rcx, aI64dHr; " %I64d hr"
0x1800e7aba  imul    rdi
0x1800e7abd  sar     rdx, 0Ah
0x1800e7ac1  mov     rax, rdx
0x1800e7ac4  shr     rax, 3Fh
0x1800e7ac8  add     rdx, rax
0x1800e7acb  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7ad0  mov     rcx, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e7ad4  cmp     rcx, 1C20h
0x1800e7adb  jl      short loc_1800E7AED
0x1800e7add  lea     rcx, aS_28; "s"
0x1800e7ae4  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7ae9  mov     rcx, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e7aed  mov     rax, 0B72EA61D950C83FBh
0x1800e7af7  imul    rcx
0x1800e7afa  sar     rdx, 0Ah
0x1800e7afe  mov     rax, rdx
0x1800e7b01  shr     rax, 3Fh
0x1800e7b05  add     rdx, rax
0x1800e7b08  imul    rax, rdx, 0E10h
0x1800e7b0f  add     rcx, rax
0x1800e7b12  mov     qword ptr [rbp+4Fh+PerformanceCount], rcx
0x1800e7b16  mov     rdi, rcx
0x1800e7b19  cmp     rdi, 3Ch ; '<'
0x1800e7b1d  jl      short loc_1800E7B79
0x1800e7b1f  mov     rax, 8888888888888889h
0x1800e7b29  lea     rcx, aI64dMin; " %I64d min"
0x1800e7b30  imul    rdi
0x1800e7b33  add     rdx, rdi
0x1800e7b36  sar     rdx, 5
0x1800e7b3a  mov     rax, rdx
0x1800e7b3d  shr     rax, 3Fh
0x1800e7b41  add     rdx, rax
0x1800e7b44  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7b49  mov     rcx, qword ptr [rbp+4Fh+PerformanceCount]
0x1800e7b4d  mov     rax, 7777777777777777h
0x1800e7b57  imul    rcx
0x1800e7b5a  sub     rdx, rcx
0x1800e7b5d  sar     rdx, 5
0x1800e7b61  mov     rax, rdx
0x1800e7b64  shr     rax, 3Fh
0x1800e7b68  add     rdx, rax
0x1800e7b6b  imul    rax, rdx, 3Ch ; '<'
0x1800e7b6f  add     rcx, rax
0x1800e7b72  mov     qword ptr [rbp+4Fh+PerformanceCount], rcx
0x1800e7b76  mov     rdi, rcx
0x1800e7b79  test    rdi, rdi
0x1800e7b7c  jle     short loc_1800E7B8D
0x1800e7b7e  mov     rdx, rcx
0x1800e7b81  lea     rcx, aI64dSec; " %I64d sec"
0x1800e7b88  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7b8d  lea     rcx, aRemaining; " remaining.\n"
0x1800e7b94  jmp     short loc_1800E7B9D
0x1800e7b96  lea     rcx, asc_1805BAA38; "\n"
0x1800e7b9d  call    ?dprintf@@YAXPEBGZZ; dprintf(ushort const *,...)
0x1800e7ba2  mov     rax, qword ptr [rbp+4Fh+var_88]
0x1800e7ba6  mov     qword ptr [rbp+4Fh+PerformanceCount], rax
0x1800e7baa  mov     [rbp+4Fh+var_80], ebx
0x1800e7bad  call    ?FlushCallbacks@@YAXXZ; FlushCallbacks(void)
0x1800e7bb2  cmp     [rbp+4Fh+hFile], 0
0x1800e7bb7  jnz     loc_1800E7C66
0x1800e7bbd  test    r12, r12
0x1800e7bc0  jz      short loc_1800E7BCE
0x1800e7bc2  cmp     byte ptr [r12+24h], 0
  ... truncated ...
```
