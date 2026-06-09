# CONFIG_CACHE::ProcessConfigPath(PATH *,ulong,CONFIG_FILE_LIST *,PARSE_ERROR_INFO *)

- ea: `0x180002b20`
- end: `0x18000342e`
- name: `?ProcessConfigPath@CONFIG_CACHE@@AEAAJPEAVPATH@@KPEAVCONFIG_FILE_LIST@@PEAVPARSE_ERROR_INFO@@@Z`
- size: `2318`
- prototype: `__int64 __fastcall(CONFIG_CACHE *__hidden this, struct PATH *, unsigned int, struct CONFIG_FILE_LIST *, struct PARSE_ERROR_INFO *)`
- caller_count: `7`
- callee_count: `21`
- tags: `registry_config, installer_update`

## callers

- `0x180001080`
- `0x180001350`
- `0x180001410`
- `0x180001f00`
- `0x180002b20`
- `0x18004e9fc`
- `0x18004ebb4`

## callees

- `0x1800011c0`
- `0x1800012c0`
- `0x180002b20`
- `0x180003440`
- `0x180003480`
- `0x180007e30`
- `0x1800169a0`
- `0x180017490`
- `0x18001a588`
- `0x18001a648`
- `0x18001b0f0`
- `0x18004bc68`
- `0x18004beac`
- `0x18004eda8`
- `0x180050654`
- `0x180050944`
- `0x180052c54`
- `0x180052fa0`
- `0x180053028`
- `0x180059bea`
- `0x180059c30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ef8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ed2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002ef8`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ee3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f09`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002ee3`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180002f09`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003007`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180003007`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800032a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003331`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003399`
- `iisutil!??1STRU@@QEAA@XZ` at `0x1800032a2`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003331`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003399`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000326a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800032ff`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000326a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x1800032ff`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800030b9`
- `iisutil!IsStringEqualOrdinalIgnoreCase` at `0x1800030b9`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003234`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180003234`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033b3`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033e9`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033b3`
- `iisutil!?ReadLock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033e9`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033c0`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003423`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x1800033c0`
- `iisutil!?ReadUnlock@CReaderWriterLock3@@QEAAXXZ` at `0x180003423`

## pseudocode

```c
__int64 __fastcall CONFIG_CACHE::ProcessConfigPath(
        CONFIG_CACHE *this,
        struct PATH *a2,
        unsigned int a3,
        struct CONFIG_FILE_LIST *a4,
        struct PARSE_ERROR_INFO *a5)
{
  struct _PATH_CACHE_NODE *v5; // r12
  char v7; // r13
  struct PATH *v8; // r15
  unsigned int v9; // eax
  struct PATH *v10; // rsi
  int v11; // r14d
  SIZE_T v12; // rdi
  size_t v13; // r8
  unsigned int v14; // ecx
  unsigned int v15; // r8d
  int v16; // ecx
  int v17; // r13d
  CONFIG_CACHE *v18; // rsi
  BOOL v19; // edi
  unsigned int v20; // eax
  __int64 v21; // rdi
  int DesiredManagedRuntimeVersion; // r14d
  CONFIG_CACHE *v23; // r10
  struct _PATH_CACHE_NODE *v24; // rsi
  int v25; // ecx
  __int64 v26; // r14
  unsigned int v27; // eax
  __int64 v28; // r13
  int v29; // r15d
  unsigned int v30; // edi
  __int64 v31; // rdi
  __int64 v32; // rsi
  __int64 j; // rdx
  __int64 v34; // r8
  unsigned int v36; // eax
  unsigned int v37; // eax
  unsigned int v38; // eax
  int v39; // r15d
  HANDLE ProcessHeap; // rax
  LPVOID v41; // rax
  SIZE_T v42; // rdi
  HANDLE v43; // rax
  LPVOID v44; // rax
  DWORD TickCount; // eax
  struct _PATH_CACHE_NODE *v46; // rdx
  unsigned int v47; // eax
  unsigned int *v48; // r8
  __int64 v49; // rsi
  unsigned int v50; // ecx
  const unsigned __int16 *v51; // r12
  unsigned int v52; // r14d
  int v53; // r15d
  __int64 *i; // rsi
  bool v55; // cc
  bool v56; // zf
  __int64 v57; // rcx
  unsigned int v58; // eax
  int v59; // eax
  const unsigned __int16 *Str; // rax
  int IsLoadedRuntimeVersionValidForSpecifiedVersion; // edi
  int IsLoadedRuntimeBitnessValid; // eax
  BOOL v63; // r15d
  int v64; // edi
  const unsigned __int16 *v65; // rax
  int v66; // eax
  int v68; // [rsp+48h] [rbp-B8h] BYREF
  int v69; // [rsp+4Ch] [rbp-B4h] BYREF
  PARSE_ERROR_INFO *v70; // [rsp+50h] [rbp-B0h]
  int File; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v72; // [rsp+5Ch] [rbp-A4h]
  struct _PATH_CACHE_NODE *v73; // [rsp+60h] [rbp-A0h] BYREF
  struct PATH *v74; // [rsp+68h] [rbp-98h]
  struct CONFIG_FILE *v75; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v76[56]; // [rsp+78h] [rbp-88h] BYREF
  __int128 v77; // [rsp+B0h] [rbp-50h] BYREF
  int v78; // [rsp+C0h] [rbp-40h]
  int v79; // [rsp+C4h] [rbp-3Ch]
  int v80; // [rsp+C8h] [rbp-38h]
  __int64 v81; // [rsp+CCh] [rbp-34h]
  int v82; // [rsp+D4h] [rbp-2Ch]
  unsigned int v83; // [rsp+D8h] [rbp-28h]
  _QWORD v84[4]; // [rsp+1A0h] [rbp+A0h] BYREF
  int v85; // [rsp+1C0h] [rbp+C0h]
  char v86; // [rsp+1C4h] [rbp+C4h] BYREF

  v5 = 0;
  v72 = a3;
  v74 = a2;
  v7 = a3;
  v8 = a2;
  v70 = a5;
  v73 = 0;
  if ( !a2 )
    return (unsigned int)-2147024809;
  v9 = *((_DWORD *)a2 + 6);
  if ( v9 == -1 )
    return (unsigned int)-2147024809;
  v10 = (CONFIG_CACHE *)((char *)this + 352);
  if ( this == (CONFIG_CACHE *)-352LL )
    return (unsigned int)-2147024809;
  v11 = *((_DWORD *)this + 205);
  v12 = 8LL * v9;
  *((_DWORD *)a4 + 4) = v9;
  if ( v9 > 0x10 )
  {
    ProcessHeap = GetProcessHeap();
    v41 = HeapAlloc(ProcessHeap, 8u, v12);
    *(_QWORD *)a4 = v41;
    if ( !v41 )
      return (unsigned int)-2147024888;
    v42 = 4LL * *((unsigned int *)a4 + 4);
    v43 = GetProcessHeap();
    v44 = HeapAlloc(v43, 8u, v42);
    if ( (*((_QWORD *)a4 + 1) = v44) == 0 )
      return (unsigned int)-2147024888;
  }
  else
  {
    *(_QWORD *)a4 = (char *)a4 + 48;
    memset_0((char *)a4 + 48, 0, 8LL * v9);
    v13 = 4LL * *((unsigned int *)a4 + 4);
    *((_QWORD *)a4 + 1) = (char *)a4 + 176;
    memset_0((char *)a4 + 176, 0, v13);
  }
  v14 = *((_DWORD *)a4 + 10) & 0xFFFFFFFE;
  *((_DWORD *)a4 + 10) = v14;
  v15 = *((_DWORD *)v10 + 6);
  if ( v15 == -1
    || (v58 = *((_DWORD *)v8 + 6), v58 == -1)
    || v15 > v58
    || (v59 = PATH::Equal(v10, v8, v15 - 1), v14 = *((_DWORD *)a4 + 10), !v59) )
  {
    *((_DWORD *)a4 + 5) = -1;
  }
  else
  {
    *((_DWORD *)a4 + 5) = *((_DWORD *)v10 + 6) - 1;
    if ( (v7 & 0x10) != 0 || (v14 & 8) == 0 )
      v14 |= 1u;
  }
  *((_DWORD *)a4 + 6) = 0;
  *((_DWORD *)a4 + 7) = -1;
  *((_DWORD *)a4 + 10) = v14 & 0xFFFFFFF9 ^ (2 * (_BYTE)v11) & 2;
  do
  {
    v16 = *((_DWORD *)v8 + 8);
    v17 = 0;
    v18 = this;
    v69 = 0;
    v19 = (v16 & 1) == 0
       && (v16 & 2) == 0
       && (unsigned int)(*((_DWORD *)this + 94) - 4) <= 0xFFFFFFFA
       && !*((_QWORD *)this + 99);
    v20 = *((_DWORD *)a4 + 5);
    if ( v20 != -1 && (*((_BYTE *)a4 + 40) & 1) == 0 && v20 < 2 && (v16 & 4) != 0 && *((_DWORD *)v8 + 6) > 3u || v19 )
    {
      v85 &= 0xFFFFFFF0;
      v78 = 0;
      v79 = -1;
      v83 = v83 & 0xFFFFFFF0 | 8;
      v77 = 0;
      v84[0] = &v86;
      v80 = 0;
      v81 = -1;
      v82 = -1;
      v75 = 0;
      v84[1] = 0;
      v84[2] = 0;
      v84[3] = -1;
      DesiredManagedRuntimeVersion = PATH::Parse((PATH *)v84, L"MACHINE/WEBROOT/APPHOST");
      if ( DesiredManagedRuntimeVersion >= 0 )
      {
        File = PATH_CACHE::GetFile(
                 (CONFIG_CACHE *)((char *)this + 24),
                 L"MACHINE/WEBROOT/APPHOST",
                 *((_DWORD *)this + 14),
                 &v75);
        DesiredManagedRuntimeVersion = File;
        if ( File >= 0 )
        {
          if ( v75 )
          {
            CONFIG_FILE::QueryInitialized(v75, &File, v70);
            DesiredManagedRuntimeVersion = File;
          }
          else
          {
            DesiredManagedRuntimeVersion = CONFIG_CACHE::ProcessConfigPath(
                                             this,
                                             (struct PATH *)v84,
                                             v72 | 0x10,
                                             (struct CONFIG_FILE_LIST *)&v77,
                                             v70);
          }
        }
      }
      PATH::Destroy((PATH *)v84);
      CONFIG_FILE_LIST::Destroy((CONFIG_FILE_LIST *)&v77);
      if ( DesiredManagedRuntimeVersion < 0 )
        goto LABEL_136;
      if ( v19 )
      {
        STRU::STRU((STRU *)v76);
        v68 = 0;
        DesiredManagedRuntimeVersion = CONFIG_CACHE::GetDesiredManagedRuntimeVersion(
                                         this,
                                         (struct STRU *)v76,
                                         &v68,
                                         v70);
        if ( DesiredManagedRuntimeVersion < 0 )
        {
          STRU::~STRU((STRU *)v76);
          return (unsigned int)DesiredManagedRuntimeVersion;
        }
        Str = STRU::QueryStr((STRU *)v76);
        IsLoadedRuntimeVersionValidForSpecifiedVersion = CONFIG_PATH_MAPPER::IsLoadedRuntimeVersionValidForSpecifiedVersion(
                                                           (CONFIG_CACHE *)((char *)this + 64),
                                                           Str);
        IsLoadedRuntimeBitnessValid = CONFIG_PATH_MAPPER::IsLoadedRuntimeBitnessValid(
                                        (CONFIG_CACHE *)((char *)this + 64),
                                        v68);
        DesiredManagedRuntimeVersion = IsLoadedRuntimeBitnessValid;
        v63 = IsLoadedRuntimeBitnessValid == 0;
        if ( !IsLoadedRuntimeVersionValidForSpecifiedVersion || !IsLoadedRuntimeBitnessValid )
        {
          CONFIG_CACHE::ReadUnlock(this);
          CONFIG_CACHE::WriteLock(this);
          if ( DesiredManagedRuntimeVersion )
            goto LABEL_134;
          v64 = v68;
          if ( !(unsigned int)CONFIG_PATH_MAPPER::IsLoadedRuntimeBitnessValid((CONFIG_CACHE *)((char *)this + 64), v68) )
            DesiredManagedRuntimeVersion = CONFIG_PATH_MAPPER::GetInstalledClrVersions(
                                             (CONFIG_CACHE *)((char *)this + 120),
                                             (CONFIG_CACHE *)((char *)this + 64),
                                             v64);
          if ( DesiredManagedRuntimeVersion >= 0 )
          {
LABEL_134:
            v65 = STRU::QueryStr((STRU *)v76);
            DesiredManagedRuntimeVersion = CONFIG_CACHE::SetManagedRuntimeVersion(this, v65, v63);
          }
          CONFIG_CACHE::WriteUnlock(this);
          CONFIG_CACHE::ReadLock(this);
          v17 = 1;
          STRU::~STRU((STRU *)v76);
          v8 = v74;
LABEL_136:
          v23 = this;
          goto LABEL_20;
        }
        STRU::~STRU((STRU *)v76);
        v8 = v74;
        v18 = this;
      }
    }
    LODWORD(v21) = *((_DWORD *)v8 + 6);
    DesiredManagedRuntimeVersion = 0;
    v5 = 0;
    while ( 1 )
    {
      if ( !(_DWORD)v21 )
      {
        v5 = 0;
        goto LABEL_18;
      }
      v47 = *((_DWORD *)v8 + 6);
      v21 = (unsigned int)(v21 - 1);
      if ( (unsigned int)v21 >= v47 )
        return (unsigned int)-2147024809;
      if ( *((_DWORD *)v8 + 7) != -1 || v47 == -1 )
        return (unsigned int)-2147024846;
      v48 = (unsigned int *)(*(_QWORD *)v8 + 8 * v21);
      *(_WORD *)(*((_QWORD *)v8 + 1) + 2LL * *v48) = 0;
      *((_DWORD *)v8 + 7) = v21;
      v49 = *((_QWORD *)v18 + 4);
      if ( v49 && (v50 = *((_DWORD *)this + 10)) != 0 )
      {
        v51 = (const unsigned __int16 *)*((_QWORD *)v8 + 1);
        v52 = v48[1];
        v53 = 0;
        for ( i = *(__int64 **)(v49 + 8LL * (v52 % v50)); i; i = (__int64 *)*i )
        {
          v55 = *((_DWORD *)i + 16) <= v52;
          if ( *((_DWORD *)i + 16) == v52 )
          {
            if ( IsStringEqualOrdinalIgnoreCase((const unsigned __int16 *)i[7], v51) )
            {
              v53 = 1;
              break;
            }
            v55 = *((_DWORD *)i + 16) <= v52;
          }
          if ( !v55 )
            break;
        }
        v5 = 0;
        DesiredManagedRuntimeVersion = 0;
        v56 = v53 == 0;
        v8 = v74;
        if ( !v56 )
          v5 = (struct _PATH_CACHE_NODE *)i;
      }
      else
      {
        DesiredManagedRuntimeVersion = -2147024809;
      }
      v57 = *((unsigned int *)v8 + 7);
      if ( (_DWORD)v57 != -1 )
      {
        if ( (_DWORD)v57 != *((_DWORD *)v8 + 6) - 1 )
          *(_WORD *)(*((_QWORD *)v8 + 1) + 2LL * *(unsigned int *)(*(_QWORD *)v8 + 8 * v57)) = 47;
        *((_DWORD *)v8 + 7) = -1;
      }
      if ( DesiredManagedRuntimeVersion < 0 )
        return (unsigned int)DesiredManagedRuntimeVersion;
      if ( v5 )
        break;
      v18 = this;
    }
    TickCount = GetTickCount();
    v46 = v5;
    do
    {
      if ( TickCount - *((_DWORD *)v46 + 17) > 0x2710 )
        *((_DWORD *)v46 + 17) = TickCount;
      v46 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v46 + 1);
    }
    while ( v46 );
    DesiredManagedRuntimeVersion = 0;
LABEL_18:
    v23 = this;
    if ( *((_DWORD *)this + 203)
      && v5
      && ((v66 = CONFIG_CACHE::PollForChanges(this, v8, v5, &v69, v70),
           v17 = v69,
           DesiredManagedRuntimeVersion = v66,
           v23 = this,
           v66 < 0)
       || v69) )
    {
      v5 = v73;
    }
    else
    {
      v73 = v5;
    }
LABEL_20:
    if ( DesiredManagedRuntimeVersion < 0 )
      return (unsigned int)DesiredManagedRuntimeVersion;
  }
  while ( v17 );
  v24 = v5;
  if ( v5 )
  {
    while ( 1 )
    {
      if ( ((v25 = *((_DWORD *)a4 + 10), v26 = *((unsigned int *)v24 + 20), (v25 & 2) == 0) || (unsigned int)v26 <= 2)
        && ((v27 = *((_DWORD *)a4 + 5), v27 == -1) || (_DWORD)v26 == v27 || (unsigned int)v26 < v27 || (v25 & 1) != 0) )
      {
        v28 = *((_QWORD *)v24 + 4);
      }
      else
      {
        v28 = 0;
      }
      if ( (unsigned int)v26 > *((_DWORD *)a4 + 4) )
        return (unsigned int)-2147024809;
      if ( *(_QWORD *)(*(_QWORD *)a4 + 8 * v26) )
        return (unsigned int)-2147024713;
      v29 = *((_DWORD *)v24 + 19);
      if ( v28 && ((v25 & 1) != 0 || (unsigned int)v26 <= *((_DWORD *)a4 + 5)) )
      {
        *(_QWORD *)(*(_QWORD *)a4 + 8 * v26) = v28;
        ++*((_DWORD *)a4 + 6);
        v36 = *((_DWORD *)a4 + 7);
        if ( v36 == -1 || (unsigned int)v26 > v36 )
          *((_DWORD *)a4 + 7) = v26;
        if ( (*(_BYTE *)(v28 + 272) & 1) == 0 )
        {
          CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v28 + 184));
          CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v28 + 184));
        }
        if ( *(_DWORD *)(v28 + 56) || *(_DWORD *)(v28 + 60) )
        {
          v37 = *((_DWORD *)a4 + 8);
          if ( v37 == -1 || (unsigned int)v26 > v37 )
            *((_DWORD *)a4 + 8) = v26;
        }
      }
      if ( (v29 & 0x10) != 0 )
      {
        v38 = *((_DWORD *)a4 + 9);
        if ( v38 == -1 || (unsigned int)v26 > v38 )
          *((_DWORD *)a4 + 9) = v26;
      }
      *(_DWORD *)(*((_QWORD *)a4 + 1) + 4 * v26) = v29;
      v24 = (struct _PATH_CACHE_NODE *)*((_QWORD *)v24 + 1);
      if ( !v24 )
      {
        v8 = v74;
        v23 = this;
        if ( v73 )
        {
          v30 = *((_DWORD *)v73 + 20) + 1;
          goto LABEL_33;
        }
        goto LABEL_146;
      }
    }
  }
  else
  {
LABEL_146:
    v30 = 0;
LABEL_33:
    while ( v30 < *((_DWORD *)v8 + 6) )
    {
      DesiredManagedRuntimeVersion = CONFIG_CACHE::CacheMiss(
                                       v23,
                                       (const unsigned __int16 **)v8,
                                       v30,
                                       v72,
                                       a4,
                                       &v73,
                                       v70);
      if ( DesiredManagedRuntimeVersion < 0 )
        return (unsigned int)DesiredManagedRuntimeVersion;
      v23 = this;
      ++v30;
    }
    DesiredManagedRuntimeVersion = 0;
    v31 = 0;
    if ( *((_DWORD *)a4 + 4) )
    {
      while ( 1 )
      {
        v32 = *(_QWORD *)(*(_QWORD *)a4 + 8 * v31);
        if ( v32 )
        {
          if ( (*(_BYTE *)(v32 + 272) & 1) != 0 )
          {
            v39 = 0;
          }
          else
          {
            CReaderWriterLock3::ReadLock((CReaderWriterLock3 *)(v32 + 184));
            v39 = 1;
          }
          DesiredManagedRuntimeVersion = *(_DWORD *)(v32 + 192);
          if ( DesiredManagedRuntimeVersion < 0 && v70 )
            PARSE_ERROR_INFO::CopyParseError(v70, (const struct PARSE_ERROR_INFO *)(v32 + 208));
          if ( v39 )
            CReaderWriterLock3::ReadUnlock((CReaderWriterLock3 *)(v32 + 184));
          if ( DesiredManagedRuntimeVersion < 0 )
            break;
        }
        v31 = (unsigned int)(v31 + 1);
        if ( (unsigned int)v31 >= *((_DWORD *)a4 + 4) )
          goto LABEL_37;
      }
    }
    else
    {
LABEL_37:
      for ( j = 0; (unsigned int)j < *((_DWORD *)a4 + 6); j = (unsigned int)(j + 1) )
      {
        v34 = *(_QWORD *)(*(_QWORD *)a4 + 8 * j);
        if ( v34 )
          _InterlockedIncrement((volatile signed __int32 *)(v34 + 36));
      }
      *((_DWORD *)a4 + 10) |= 4u;
    }
  }
  return (unsigned int)DesiredManagedRuntimeVersion;
}

```

## disassembly

```asm
0x180002b20  push    rbp
0x180002b22  push    rbx
0x180002b23  push    rsi
0x180002b24  push    rdi
0x180002b25  push    r12
0x180002b27  push    r13
0x180002b29  push    r14
0x180002b2b  push    r15
0x180002b2d  lea     rbp, [rsp-268h]
0x180002b35  sub     rsp, 368h
0x180002b3c  mov     rax, cs:__security_cookie
0x180002b43  xor     rax, rsp
0x180002b46  mov     [rbp+2A0h+var_50], rax
0x180002b4d  mov     rax, [rbp+2A0h+arg_20]
0x180002b54  xor     r12d, r12d
0x180002b57  mov     [rsp+3A0h+var_344], r8d
0x180002b5c  mov     rbx, r9
0x180002b5f  mov     [rsp+3A0h+var_338], rdx
0x180002b64  mov     r13d, r8d
0x180002b67  mov     [rsp+3A0h+var_360], rcx
0x180002b6c  mov     r15, rdx
0x180002b6f  mov     [rsp+3A0h+var_350], rax
0x180002b74  mov     [rsp+3A0h+var_340], r12
0x180002b79  test    rdx, rdx
0x180002b7c  jz      loc_180002EB0
0x180002b82  mov     eax, [rdx+18h]
0x180002b85  cmp     eax, 0FFFFFFFFh
0x180002b88  jz      loc_180002EB0
0x180002b8e  lea     rsi, [rcx+160h]
0x180002b95  test    rsi, rsi
0x180002b98  jz      loc_180002EB0
0x180002b9e  mov     r14d, [rcx+334h]
0x180002ba5  mov     edi, eax
0x180002ba7  shl     rdi, 3
0x180002bab  mov     [r9+10h], eax
0x180002baf  cmp     eax, 10h
0x180002bb2  ja      loc_180002ED2
0x180002bb8  lea     rcx, [r9+30h]; void *
0x180002bbc  mov     r8, rdi; Size
0x180002bbf  xor     edx, edx; Val
0x180002bc1  mov     [r9], rcx
0x180002bc4  call    memset_0
0x180002bc9  mov     r8d, [rbx+10h]
0x180002bcd  lea     rcx, [rbx+0B0h]; void *
0x180002bd4  shl     r8, 2; Size
0x180002bd8  xor     edx, edx; Val
0x180002bda  mov     [rbx+8], rcx
0x180002bde  call    memset_0
0x180002be3  mov     ecx, [rbx+28h]
0x180002be6  and     ecx, 0FFFFFFFEh
0x180002be9  mov     [rbx+28h], ecx
0x180002bec  mov     r8d, [rsi+18h]
0x180002bf0  cmp     r8d, 0FFFFFFFFh
0x180002bf4  jnz     loc_18000313C
0x180002bfa  mov     dword ptr [rbx+14h], 0FFFFFFFFh
0x180002c01  lea     eax, [r14+r14]
0x180002c05  mov     [rbx+18h], r12d
0x180002c09  and     eax, 2
0x180002c0c  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x180002c13  and     ecx, 0FFFFFFF9h
0x180002c16  xor     eax, ecx
0x180002c18  mov     [rbx+28h], eax
0x180002c1b  mov     ecx, [r15+20h]
0x180002c1f  xor     r13d, r13d
0x180002c22  mov     rsi, [rsp+3A0h+var_360]
0x180002c27  mov     r9d, 80070057h
0x180002c2d  mov     [rsp+3A0h+var_354], r13d
0x180002c32  test    cl, 1
0x180002c35  jnz     short loc_180002C4E
0x180002c37  test    cl, 2
0x180002c3a  jnz     short loc_180002C4E
0x180002c3c  mov     eax, [rsi+178h]
0x180002c42  sub     eax, 4
0x180002c45  cmp     eax, 0FFFFFFFAh
0x180002c48  jbe     loc_180002EBB
0x180002c4e  xor     edi, edi
0x180002c50  mov     eax, [rbx+14h]
0x180002c53  cmp     eax, 0FFFFFFFFh
0x180002c56  jnz     loc_18000318A
0x180002c5c  test    edi, edi
0x180002c5e  jnz     loc_180002F27
0x180002c64  mov     edi, [r15+18h]
0x180002c68  xor     r14d, r14d
0x180002c6b  xor     r12d, r12d
0x180002c6e  test    edi, edi
0x180002c70  jnz     loc_180003033
0x180002c76  xor     r12d, r12d
0x180002c79  mov     r10, [rsp+3A0h+var_360]
0x180002c7e  cmp     [r10+32Ch], r13d
0x180002c85  jnz     loc_18000334F
0x180002c8b  mov     [rsp+3A0h+var_340], r12
0x180002c90  test    r14d, r14d
0x180002c93  js      loc_180002D8F
0x180002c99  test    r13d, r13d
0x180002c9c  jnz     loc_180002C1B
0x180002ca2  mov     rsi, r12
0x180002ca5  test    r12, r12
0x180002ca8  jz      loc_1800033DB
0x180002cae  xchg    ax, ax
0x180002cb0  mov     ecx, [rbx+28h]
0x180002cb3  mov     r14d, [rsi+50h]
0x180002cb7  test    cl, 2
0x180002cba  jnz     loc_180002FF5
0x180002cc0  mov     eax, [rbx+14h]
0x180002cc3  cmp     eax, 0FFFFFFFFh
0x180002cc6  jnz     loc_180002FDB
0x180002ccc  mov     r13, [rsi+20h]
0x180002cd0  cmp     r14d, [rbx+10h]
0x180002cd4  ja      loc_180002EB0
0x180002cda  mov     rax, [rbx]
0x180002cdd  cmp     qword ptr [rax+r14*8], 0
0x180002ce2  jnz     loc_180002E62
0x180002ce8  mov     r15d, [rsi+4Ch]
0x180002cec  test    r13, r13
0x180002cef  jnz     loc_180002DB5
0x180002cf5  test    r15b, 10h
0x180002cf9  jnz     loc_180002E0B
0x180002cff  mov     rax, [rbx+8]
0x180002d03  mov     [rax+r14*4], r15d
0x180002d07  mov     rsi, [rsi+8]
0x180002d0b  test    rsi, rsi
0x180002d0e  jnz     short loc_180002CB0
0x180002d10  mov     r12, [rsp+3A0h+var_340]
0x180002d15  mov     r15, [rsp+3A0h+var_338]
0x180002d1a  mov     r10, [rsp+3A0h+var_360]
0x180002d1f  test    r12, r12
0x180002d22  jz      loc_1800033DB
0x180002d28  mov     edi, [r12+50h]
0x180002d2d  inc     edi
0x180002d2f  cmp     edi, [r15+18h]
0x180002d33  jb      loc_180002E6D
0x180002d39  xor     r14d, r14d
0x180002d3c  xor     edi, edi
0x180002d3e  cmp     [rbx+10h], edi
0x180002d41  jbe     short loc_180002D67
0x180002d43  nop     dword ptr [rax+00h]
0x180002d47  nop     word ptr [rax+rax+00000000h]
0x180002d50  mov     rax, [rbx]
0x180002d53  mov     rsi, [rax+rdi*8]
0x180002d57  test    rsi, rsi
0x180002d5a  jnz     loc_180002E2B
0x180002d60  inc     edi
0x180002d62  cmp     edi, [rbx+10h]
0x180002d65  jb      short loc_180002D50
0x180002d67  test    r14d, r14d
0x180002d6a  js      short loc_180002D8F
0x180002d6c  xor     edx, edx
0x180002d6e  cmp     [rbx+18h], edx
0x180002d71  jbe     short loc_180002D8B
0x180002d73  mov     rax, [rbx]
0x180002d76  mov     r8, [rax+rdx*8]
0x180002d7a  test    r8, r8
0x180002d7d  jz      short loc_180002D84
0x180002d7f  lock inc dword ptr [r8+24h]
0x180002d84  inc     edx
0x180002d86  cmp     edx, [rbx+18h]
0x180002d89  jb      short loc_180002D73
0x180002d8b  or      dword ptr [rbx+28h], 4
0x180002d8f  mov     eax, r14d
0x180002d92  mov     rcx, [rbp+2A0h+var_50]
0x180002d99  xor     rcx, rsp; StackCookie
0x180002d9c  call    __security_check_cookie
0x180002da1  add     rsp, 368h
0x180002da8  pop     r15
0x180002daa  pop     r14
0x180002dac  pop     r13
0x180002dae  pop     r12
0x180002db0  pop     rdi
0x180002db1  pop     rsi
0x180002db2  pop     rbx
0x180002db3  pop     rbp
0x180002db4  retn
0x180002db5  test    cl, 1
0x180002db8  jnz     short loc_180002DC4
0x180002dba  cmp     r14d, [rbx+14h]
0x180002dbe  ja      loc_180002CF5
0x180002dc4  mov     [rax+r14*8], r13
0x180002dc8  inc     dword ptr [rbx+18h]
0x180002dcb  mov     eax, [rbx+1Ch]
0x180002dce  cmp     eax, 0FFFFFFFFh
0x180002dd1  jz      short loc_180002E25
0x180002dd3  cmp     r14d, eax
0x180002dd6  ja      short loc_180002E25
0x180002dd8  test    byte ptr [r13+110h], 1
0x180002de0  jz      loc_1800033AC
0x180002de6  cmp     dword ptr [r13+38h], 0
0x180002deb  jz      loc_1800033CB
0x180002df1  mov     eax, [rbx+20h]
0x180002df4  cmp     eax, 0FFFFFFFFh
0x180002df7  jz      short loc_180002E02
0x180002df9  cmp     r14d, eax
0x180002dfc  jbe     loc_180002CF5
0x180002e02  mov     [rbx+20h], r14d
0x180002e06  jmp     loc_180002CF5
0x180002e0b  mov     eax, [rbx+24h]
0x180002e0e  cmp     eax, 0FFFFFFFFh
0x180002e11  jz      short loc_180002E1C
0x180002e13  cmp     r14d, eax
0x180002e16  jbe     loc_180002CFF
0x180002e1c  mov     [rbx+24h], r14d
0x180002e20  jmp     loc_180002CFF
0x180002e25  mov     [rbx+1Ch], r14d
0x180002e29  jmp     short loc_180002DD8
0x180002e2b  test    byte ptr [rsi+110h], 1
0x180002e32  jz      loc_1800033E2
0x180002e38  xor     r15d, r15d
0x180002e3b  mov     r14d, [rsi+0C0h]
0x180002e42  test    r14d, r14d
0x180002e45  js      loc_1800033FA
0x180002e4b  test    r15d, r15d
0x180002e4e  jnz     loc_18000341C
0x180002e54  test    r14d, r14d
0x180002e57  jns     loc_180002D60
0x180002e5d  jmp     loc_180002D8F
0x180002e62  mov     r14d, 800700B7h
0x180002e68  jmp     loc_180002D8F
0x180002e6d  mov     rax, [rsp+3A0h+var_350]
0x180002e72  mov     r8d, edi; unsigned int
0x180002e75  mov     r9d, [rsp+3A0h+var_344]; unsigned int
0x180002e7a  mov     rdx, r15; struct PATH *
0x180002e7d  mov     [rsp+3A0h+var_370], rax; struct PARSE_ERROR_INFO *
0x180002e82  mov     rcx, r10; this
0x180002e85  lea     rax, [rsp+3A0h+var_340]
0x180002e8a  mov     [rsp+3A0h+var_378], rax; struct _PATH_CACHE_NODE **
0x180002e8f  mov     [rsp+3A0h+var_380], rbx; struct CONFIG_FILE_LIST *
0x180002e94  call    ?CacheMiss@CONFIG_CACHE@@AEAAJPEAVPATH@@KKPEAVCONFIG_FILE_LIST@@PEAPEAU_PATH_CACHE_NODE@@PEAVPARSE_ERROR_INFO@@@Z; CONFIG_CACHE::CacheMiss(PATH *,ulong,ulong,CONFIG_FILE_LIST *,_PATH_CACHE_NODE * *,PARSE_ERROR_INFO *)
0x180002e99  mov     r14d, eax
0x180002e9c  test    eax, eax
0x180002e9e  js      loc_180002D8F
0x180002ea4  mov     r10, [rsp+3A0h+var_360]
0x180002ea9  inc     edi
0x180002eab  jmp     loc_180002D2F
0x180002eb0  mov     r14d, 80070057h
0x180002eb6  jmp     loc_180002D8F
0x180002ebb  cmp     [rsi+318h], r13
0x180002ec2  jnz     loc_180002C4E
0x180002ec8  mov     edi, 1
0x180002ecd  jmp     loc_180002C50
0x180002ed2  call    cs:__imp_GetProcessHeap
0x180002ed8  mov     r8, rdi; dwBytes
0x180002edb  mov     edx, 8; dwFlags
0x180002ee0  mov     rcx, rax; hHeap
0x180002ee3  call    cs:__imp_HeapAlloc
0x180002ee9  mov     [rbx], rax
0x180002eec  test    rax, rax
0x180002eef  jz      short loc_180002F1C
0x180002ef1  mov     edi, [rbx+10h]
0x180002ef4  shl     rdi, 2
0x180002ef8  call    cs:__imp_GetProcessHeap
0x180002efe  mov     r8, rdi; dwBytes
0x180002f01  mov     edx, 8; dwFlags
0x180002f06  mov     rcx, rax; hHeap
0x180002f09  call    cs:__imp_HeapAlloc
0x180002f0f  mov     [rbx+8], rax
0x180002f13  test    rax, rax
0x180002f16  jnz     loc_180002BE3
0x180002f1c  mov     r14d, 80070008h
0x180002f22  jmp     loc_180002D8F
0x180002f27  mov     eax, [rbp+2A0h+var_2C8]
0x180002f2a  lea     rdx, aMachineWebroot; "MACHINE/WEBROOT/APPHOST"
0x180002f31  and     [rbp+2A0h+var_1E0], 0FFFFFFF0h
0x180002f38  lea     rcx, [rbp+2A0h+var_200]; this
0x180002f3f  and     eax, 0FFFFFFF8h
0x180002f42  mov     [rbp+2A0h+var_2E0], r13d
0x180002f46  or      eax, 8
0x180002f49  mov     [rbp+2A0h+var_2DC], 0FFFFFFFFh
0x180002f50  mov     [rbp+2A0h+var_2C8], eax
0x180002f53  xorps   xmm0, xmm0
0x180002f56  lea     rax, [rbp+2A0h+var_1DC]
0x180002f5d  movdqa  [rbp+2A0h+var_2F0], xmm0
0x180002f62  mov     [rbp+2A0h+var_200], rax
0x180002f69  mov     [rbp+2A0h+var_2D8], r13d
0x180002f6d  mov     [rbp+2A0h+var_2D4], 0FFFFFFFFFFFFFFFFh
0x180002f75  mov     [rbp+2A0h+var_2CC], 0FFFFFFFFh
0x180002f7c  mov     [rsp+3A0h+var_330], r13
0x180002f81  mov     [rbp+2A0h+var_1F8], r13
0x180002f88  mov     [rbp+2A0h+var_1F0], r13
0x180002f8f  mov     [rbp+2A0h+var_1E8], 0FFFFFFFFFFFFFFFFh
0x180002f9a  call    ?Parse@PATH@@QEAAJPEBG@Z; PATH::Parse(ushort const *)
0x180002f9f  mov     r14d, eax
0x180002fa2  test    eax, eax
0x180002fa4  jns     loc_1800031B6
0x180002faa  lea     rcx, [rbp+2A0h+var_200]; this
0x180002fb1  call    ?Destroy@PATH@@QEAAXXZ; PATH::Destroy(void)
0x180002fb6  lea     rcx, [rbp+2A0h+var_2F0]; this
0x180002fba  call    ?Destroy@CONFIG_FILE_LIST@@AEAAXXZ; CONFIG_FILE_LIST::Destroy(void)
0x180002fbf  test    r14d, r14d
0x180002fc2  js      loc_18000333C
0x180002fc8  test    edi, edi
0x180002fca  jnz     loc_18000322F
0x180002fd0  mov     r9d, 80070057h
0x180002fd6  jmp     loc_180002C64
0x180002fdb  cmp     r14d, eax
0x180002fde  jz      loc_180002CCC
0x180002fe4  jb      loc_180002CCC
0x180002fea  test    cl, 1
0x180002fed  jnz     loc_180002CCC
0x180002ff3  jmp     short loc_180002FFF
0x180002ff5  cmp     r14d, 2
0x180002ff9  jbe     loc_180002CC0
  ... truncated ...
```
