# CDiskScanner::ScrubVolume(_SCRUB_VOLUME_IDENTIFIER const *,ulong,uchar *,ulong *)

- ea: `0x18001ec84`
- end: `0x18001f86f`
- name: `?ScrubVolume@CDiskScanner@@IEAAJPEBU_SCRUB_VOLUME_IDENTIFIER@@KPEAEPEAK@Z`
- size: `3051`
- prototype: `__int64 __fastcall(CDiskScanner *this, const struct _SCRUB_VOLUME_IDENTIFIER *, int, unsigned __int8 *, unsigned int *)`
- caller_count: `3`
- callee_count: `25`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001c8c4`
- `0x18001ce8c`
- `0x18001ec84`

## callees

- `0x180001b78`
- `0x180001bc4`
- `0x1800032f8`
- `0x180006498`
- `0x180006688`
- `0x1800088a4`
- `0x18000893c`
- `0x180008c9c`
- `0x180008e48`
- `0x18000d118`
- `0x180012048`
- `0x180012158`
- `0x18001c024`
- `0x18001c044`
- `0x18001ec84`
- `0x18001fc04`
- `0x18001fcac`
- `0x18001fde0`
- `0x18001fed8`
- `0x1800200dc`
- `0x180020d90`
- `0x180021480`
- `0x180021db4`
- `0x180024b24`
- `0x180037620`

## import_xrefs

- `msvcrt!free` at `0x18001f114`
- `msvcrt!free` at `0x18001f1b2`
- `msvcrt!free` at `0x18001f28b`
- `msvcrt!free` at `0x18001f295`
- `msvcrt!free` at `0x18001f344`
- `msvcrt!free` at `0x18001f34e`
- `msvcrt!free` at `0x18001f114`
- `msvcrt!free` at `0x18001f1b2`
- `msvcrt!free` at `0x18001f28b`
- `msvcrt!free` at `0x18001f295`
- `msvcrt!free` at `0x18001f344`
- `msvcrt!free` at `0x18001f34e`
- `ntdll!RtlEqualUnicodeString` at `0x18001f022`
- `ntdll!RtlEqualUnicodeString` at `0x18001f36f`
- `ntdll!RtlEqualUnicodeString` at `0x18001f3a7`
- `ntdll!RtlEqualUnicodeString` at `0x18001f022`
- `ntdll!RtlEqualUnicodeString` at `0x18001f36f`
- `ntdll!RtlEqualUnicodeString` at `0x18001f3a7`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001ef49`
- `ntdll!NtQueryVolumeInformationFile` at `0x18001ef49`
- `ntdll!NtOpenFile` at `0x18001eebc`
- `ntdll!NtOpenFile` at `0x18001eebc`
- `KERNEL32!SetThreadPriority` at `0x18001f625`
- `KERNEL32!SetThreadPriority` at `0x18001f625`
- `KERNEL32!GetTickCount64` at `0x18001f5eb`
- `KERNEL32!GetTickCount64` at `0x18001f72d`
- `KERNEL32!GetTickCount64` at `0x18001f5eb`
- `KERNEL32!GetTickCount64` at `0x18001f72d`
- `KERNEL32!GetLastError` at `0x18001f639`
- `KERNEL32!GetLastError` at `0x18001f639`
- `KERNEL32!GetCurrentThread` at `0x18001f617`
- `KERNEL32!GetCurrentThread` at `0x18001f617`

## pseudocode

```c
__int64 __fastcall CDiskScanner::ScrubVolume(
        CDiskScanner *this,
        const struct _SCRUB_VOLUME_IDENTIFIER *a2,
        int a3,
        unsigned __int8 *a4,
        unsigned int *a5)
{
  unsigned int *v9; // r9
  __int64 v10; // rdx
  USHORT v11; // dx
  USHORT Length; // cx
  USHORT v13; // ax
  PVOID *v14; // r8
  struct _UNICODE_STRING *v15; // rbx
  struct _UNICODE_STRING *v16; // rcx
  NTSTATUS v17; // esi
  int v18; // esi
  _QWORD *v19; // rcx
  NTSTATUS v20; // esi
  int MdsPath; // eax
  void *v22; // rcx
  _DWORD *v23; // rbx
  unsigned int v24; // eax
  PVOID *v25; // rcx
  int v26; // edi
  BOOL v27; // ebx
  int v28; // r14d
  _DWORD *v29; // rdx
  PVOID *v30; // rcx
  int IsCsvVolumeByName; // eax
  char TickCount64; // r12
  __int64 v33; // rcx
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  void *v36; // rax
  CScrub *v37; // rbx
  char v38; // al
  void *v40; // [rsp+70h] [rbp-188h] BYREF
  const char *v41; // [rsp+78h] [rbp-180h] BYREF
  int v42; // [rsp+80h] [rbp-178h]
  void *Block; // [rsp+88h] [rbp-170h]
  struct _UNICODE_STRING *v44; // [rsp+90h] [rbp-168h] BYREF
  UNICODE_STRING String2; // [rsp+98h] [rbp-160h] BYREF
  struct _UNICODE_STRING v46; // [rsp+A8h] [rbp-150h] BYREF
  void *FileHandle; // [rsp+B8h] [rbp-140h] BYREF
  int v48; // [rsp+C0h] [rbp-138h]
  char v49; // [rsp+C4h] [rbp-134h]
  unsigned int v50; // [rsp+C8h] [rbp-130h] BYREF
  unsigned int *v51; // [rsp+D0h] [rbp-128h]
  struct _UNICODE_STRING v52; // [rsp+D8h] [rbp-120h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+E8h] [rbp-110h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+F8h] [rbp-100h] BYREF
  _OWORD v55[2]; // [rsp+130h] [rbp-C8h] BYREF
  __int128 v56; // [rsp+150h] [rbp-A8h]
  __int128 v57; // [rsp+160h] [rbp-98h]
  __int64 v58; // [rsp+170h] [rbp-88h]
  _OWORD FsInformation[3]; // [rsp+180h] [rbp-78h] BYREF

  v9 = a5;
  v51 = a5;
  v10 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v10 + 16) = "CDiskScanner::ScrubVolume";
  v41 = "CDiskScanner::ScrubVolume";
  v42 = 0;
  v11 = ++*(_WORD *)(v10 + 8);
  Length = GlobalIndentString.Length;
  v13 = GlobalIndentString.Length;
  if ( v11 < GlobalIndentString.Length )
    v13 = v11;
  v46.Length = v13;
  if ( v11 < GlobalIndentString.Length )
    Length = v11;
  v46.MaximumLength = Length;
  *(_DWORD *)(&v46.MaximumLength + 1) = 0;
  v46.Buffer = (PWSTR)off_180047060;
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CDiskScanner::ScrubVolume");
    v14 = (PVOID *)WPP_GLOBAL_Control;
    v9 = v51;
  }
  v15 = (struct _UNICODE_STRING *)*((_QWORD *)a2 + 4);
  Block = (void *)*((_QWORD *)a2 + 5);
  if ( a4 )
  {
    *a4 = 0;
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v9 )
  {
    *v9 = 0;
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
  v16 = v15;
  if ( (a3 & 0x10) != 0 )
    v16 = 0;
  v44 = v16;
  if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 4u )
    WPP_SF_DDZZZZ_guid_DDL(
      (TRACEHANDLE)v14[2],
      *(_DWORD *)(*(_QWORD *)a2 + 36LL),
      *((_QWORD *)a2 + 8),
      *((_QWORD *)a2 + 4),
      *((_QWORD *)a2 + 5),
      *((_QWORD *)a2 + 6),
      *(_QWORD *)a2 + 20LL,
      *(_DWORD *)(*(_QWORD *)a2 + 16LL),
      *(_DWORD *)(*(_QWORD *)a2 + 36LL),
      a3);
  IoStatusBlock = 0;
  FileHandle = 0;
  v48 = 0;
  v49 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = v15;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v17 = NtOpenFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 7u, 0x21u);
  if ( v17 < 0 )
  {
    v18 = v17 | 0x10000000;
    v42 = v18;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
LABEL_28:
      WPP_SF_DDZZd(v19[2], *(_DWORD *)(*(_QWORD *)a2 + 36LL), *((_QWORD *)a2 + 8), (__int64)v15, v18);
      goto LABEL_125;
    }
    goto LABEL_125;
  }
  memset(FsInformation, 0, 44);
  v20 = NtQueryVolumeInformationFile(FileHandle, &IoStatusBlock, FsInformation, 0x2Cu, FileFsAttributeInformation);
  if ( v20 < 0 )
  {
    v18 = v20 | 0x10000000;
    v42 = v18;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      goto LABEL_28;
    }
    goto LABEL_125;
  }
  if ( DWORD2(FsInformation[0]) > 0xFFFF || WORD4(FsInformation[0]) > 0x20u )
  {
    v18 = -1879048187;
LABEL_124:
    v42 = v18;
    goto LABEL_125;
  }
  String2.Length = WORD4(FsInformation[0]);
  String2.MaximumLength = WORD4(FsInformation[0]);
  *(_DWORD *)(&String2.MaximumLength + 1) = 0;
  String2.Buffer = (PWSTR)FsInformation + 6;
  v18 = 1;
  if ( RtlEqualUnicodeString(&CsvfsFileSystemName, &String2, 1u) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(*(_QWORD *)a2 + 36LL),
        *((_QWORD *)a2 + 8),
        (__int64)&String2);
    }
    Block = 0;
    LODWORD(v40) = 0;
    MdsPath = ((__int64 (__fastcall *)(HANDLE))CsvQueryMdsPath)(FileHandle);
    v18 = MdsPath;
    v42 = MdsPath;
    if ( MdsPath >= 0 )
    {
      v46 = 0;
      v23 = Block;
      v24 = *((_DWORD *)Block + 2);
      if ( v24 >= 0xFFFE )
      {
        LOWORD(v24) = -2;
        v46.MaximumLength = -2;
      }
      else
      {
        v46.MaximumLength = *((_DWORD *)Block + 2);
      }
      v46.Length = v24;
      v46.Buffer = (PWSTR)((char *)Block + 12);
      v52 = 0;
      v40 = 0;
      v18 = CopyUnicodeStringToBuffer(0, &v46, (struct _UNICODE_STRING *)&BackslashString, &v52, (PWSTR *)&v40);
      v42 = v18;
      if ( v18 >= 0 )
      {
        v25 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDZDDZ(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            *(_DWORD *)(*(_QWORD *)a2 + 36LL),
            *((_QWORD *)a2 + 8),
            *v23,
            v23[1],
            (__int64)&v52);
          v25 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( *v23 == v23[1] )
        {
          v55[0] = *(_OWORD *)a2;
          v55[1] = *((_OWORD *)a2 + 1);
          v56 = *((_OWORD *)a2 + 2);
          v57 = *((_OWORD *)a2 + 3);
          v58 = *((_QWORD *)a2 + 8);
          *(_QWORD *)&v56 = &v52;
          *((_QWORD *)&v56 + 1) = &v46;
          v44 = 0;
          v26 = CDiskScanner::ScrubVolume(this, (const struct _SCRUB_VOLUME_IDENTIFIER *)v55, a3 | 0x10000000u, a4, v51);
          v42 = v26;
          free(v40);
          free(v23);
          v18 = v26;
        }
        else
        {
          if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 1) != 0 && *((_BYTE *)v25 + 25) >= 4u )
            WPP_SF_DDZZ((TRACEHANDLE)v25[2], *(_DWORD *)(*(_QWORD *)a2 + 36LL), *((_QWORD *)a2 + 8), (__int64)&String2);
          v42 = 1;
          free(v40);
          free(v23);
          v18 = 1;
        }
        goto LABEL_125;
      }
      free(v40);
      v22 = v23;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DDZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          *(_DWORD *)(*(_QWORD *)a2 + 16LL),
          *(_DWORD *)(*(_QWORD *)a2 + 36LL),
          *((_QWORD *)a2 + 8),
          MdsPath);
      }
      v22 = Block;
    }
    free(v22);
    goto LABEL_125;
  }
  v27 = 0;
  if ( RtlEqualUnicodeString(&RefsFileSystemName, &String2, 1u) )
  {
    v28 = a3 | 0x20000000;
    v29 = (_DWORD *)*((_QWORD *)this + 10);
    if ( *v29 == 1 || *v29 == 3 )
    {
      v27 = 1;
      v28 |= 0xBu;
    }
  }
  else
  {
    if ( !RtlEqualUnicodeString(&NtfsFileSystemName, &String2, 1u) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(*(_QWORD *)a2 + 36LL),
          *((_QWORD *)a2 + 8),
          (__int64)&String2);
      }
      v42 = 1;
      if ( a4 )
        *a4 = 1;
      goto LABEL_125;
    }
    v28 = a3 | 0x40000000;
    v29 = (_DWORD *)*((_QWORD *)this + 10);
    v27 = *v29 == 1;
    if ( v29[2] == 1 )
      v27 = 0;
  }
  if ( (FsInformation[0] & 0x80000) == 0 )
    goto LABEL_76;
  if ( v29[2] != 1 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(*(_QWORD *)a2 + 36LL),
        *((_QWORD *)a2 + 8),
        (__int64)&String2);
    }
    goto LABEL_124;
  }
  v30 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *(_DWORD *)(*(_QWORD *)a2 + 36LL),
      *((_QWORD *)a2 + 8),
      (__int64)&String2);
LABEL_76:
    v30 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( !v27 )
  {
    if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 && *((_BYTE *)v30 + 25) >= 4u )
      WPP_SF_DDZZ((TRACEHANDLE)v30[2], *(_DWORD *)(*(_QWORD *)a2 + 36LL), *((_QWORD *)a2 + 8), (__int64)&String2);
    if ( a4 )
      *a4 = 1;
    goto LABEL_124;
  }
  if ( (v28 & 0x10000000) != 0 )
  {
    IsCsvVolumeByName = CsvIsCsvVolumeByName(a2, (struct _UNICODE_STRING *)Block);
    v18 = IsCsvVolumeByName;
    v42 = IsCsvVolumeByName;
    if ( IsCsvVolumeByName )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_DDZd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          71,
          (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          *(_DWORD *)(*(_QWORD *)a2 + 16LL),
          *(_DWORD *)(*(_QWORD *)a2 + 36LL),
          *((_QWORD *)a2 + 8),
          IsCsvVolumeByName);
      }
      goto LABEL_125;
    }
    v30 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v30 != &WPP_GLOBAL_Control && (*((_BYTE *)v30 + 28) & 1) != 0 && *((_BYTE *)v30 + 25) >= 4u )
    WPP_SF_DDZ(
      (unsigned int)v30[2],
      72,
      (unsigned int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
      *(_DWORD *)(*(_QWORD *)a2 + 16LL),
      *(_DWORD *)(*(_QWORD *)a2 + 36LL),
      *((_QWORD *)a2 + 8));
  TickCount64 = GetTickCount64();
  EventWriteVolumeScanStart(*((struct _SCRUB_ENVIRONMENT **)this + 10), a2);
  v33 = *((_QWORD *)this + 10);
  if ( *(_DWORD *)(v33 + 8) == 1 || (v28 & 0x20000000) != 0 && *(_BYTE *)(v33 + 5) )
  {
    LODWORD(v40) = -2147467259;
  }
  else
  {
    CurrentThread = GetCurrentThread();
    if ( SetThreadPriority(CurrentThread, 0x10000) )
    {
      LODWORD(v40) = 0;
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      LODWORD(v40) = LastError;
      if ( LastError != -2147024496
        && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          &WPP_11204aedcb833d82ae2b41202b2dd706_Traceguids,
          (unsigned int)LastError);
      }
    }
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    v36 = operator new(0x910u);
    Block = v36;
    if ( v36 )
      v37 = CScrub::CScrub((CScrub *)v36, *((struct _SCRUB_ENVIRONMENT **)this + 10), *((void **)this + 12));
    else
      v37 = 0;
    Block = v37;
    v44 = 0;
    v18 = CScrub::ScrubVolume(v37, a2, v28, &String2, v51);
    v42 = v18;
    ((void (__stdcall *)(CScrub *, int, unsigned __int8))CScrub::LogLastVolumeScrubResult)(v37, v18, 0);
    if ( v37 )
    {
      CScrub::~CScrub(v37);
      operator delete(v37);
    }
    CBackgroundThreadModeInStack::~CBackgroundThreadModeInStack((CBackgroundThreadModeInStack *)&v40);
    v38 = GetTickCount64();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZi(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        75,
        (int)&WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
        *(_DWORD *)(*(_QWORD *)a2 + 16LL),
        *(_DWORD *)(*(_QWORD *)a2 + 36LL),
        *((_QWORD *)a2 + 8),
        16 * (v38 - TickCount64));
    }
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &ATL::CAtlException `RTTI Type Descriptor', (ATL::CAtlException *)&v50) )
    {
      v42 = v50;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids, v50);
      }
      v18 = v50;
      __eh34_try_continuation(0, &ATL::CAtlException `RTTI Type Descriptor', &loc_18001F79F);
      goto LABEL_125;
    }
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v42 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          &WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids,
          2147942414LL);
      }
      v18 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_18001F7A8);
    }
  }
LABEL_125:
  CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
  CAutoClearVolumeCheckpoint::~CAutoClearVolumeCheckpoint((CAutoClearVolumeCheckpoint *)&v44);
  CHResultImp::~CHResultImp((CHResultImp *)&v41);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18001ec84  push    rbx
0x18001ec86  push    rsi
0x18001ec87  push    rdi
0x18001ec88  push    r12
0x18001ec8a  push    r13
0x18001ec8c  push    r14
0x18001ec8e  sub     rsp, 1C8h
0x18001ec95  mov     rax, cs:__security_cookie
0x18001ec9c  xor     rax, rsp
0x18001ec9f  mov     [rsp+1F8h+var_48], rax
0x18001eca7  mov     r12, r9
0x18001ecaa  mov     r14d, r8d
0x18001ecad  mov     rdi, rdx
0x18001ecb0  mov     r13, rcx
0x18001ecb3  mov     r9, [rsp+1F8h+arg_20]
0x18001ecbb  mov     [rsp+1F8h+var_128], r9
0x18001ecc3  mov     ecx, cs:_tls_index
0x18001ecc9  mov     rax, gs:58h
0x18001ecd2  mov     rdx, [rax+rcx*8]
0x18001ecd6  mov     eax, 10h
0x18001ecdb  lea     r11, aCdiskscannerSc; "CDiskScanner::ScrubVolume"
0x18001ece2  mov     [rax+rdx], r11
0x18001ece6  mov     [rsp+1F8h+var_180], r11
0x18001eceb  xor     esi, esi
0x18001eced  mov     [rsp+1F8h+var_178], esi
0x18001ecf4  mov     eax, 8
0x18001ecf9  lea     r10d, [rsi+1]
0x18001ecfd  add     [rax+rdx], r10w
0x18001ed02  movzx   edx, word ptr [rax+rdx]
0x18001ed06  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x18001ed0d  movzx   eax, cx
0x18001ed10  cmp     dx, cx
0x18001ed13  cmovb   ax, dx
0x18001ed17  mov     [rsp+1F8h+var_150.Length], ax
0x18001ed1f  cmovb   cx, dx
0x18001ed23  mov     [rsp+1F8h+var_150.MaximumLength], cx
0x18001ed2b  xor     eax, eax
0x18001ed2d  mov     dword ptr [rsp+1F8h+var_150+4], eax
0x18001ed34  mov     rax, cs:off_180047060; "                                       "...
0x18001ed3b  mov     [rsp+1F8h+var_150.Buffer], rax
0x18001ed43  lea     rdx, WPP_GLOBAL_Control
0x18001ed4a  mov     r8, cs:WPP_GLOBAL_Control
0x18001ed51  cmp     r8, rdx
0x18001ed54  jz      short loc_18001ED96
0x18001ed56  test    [r8+1Ch], r10b
0x18001ed5a  jz      short loc_18001ED96
0x18001ed5c  cmp     byte ptr [r8+19h], 5
0x18001ed61  jb      short loc_18001ED96
0x18001ed63  lea     edx, [rsi+0Dh]
0x18001ed66  mov     qword ptr [rsp+1F8h+ShareAccess], r11; __int64
0x18001ed6b  lea     r9, [rsp+1F8h+var_150]
0x18001ed73  mov     rcx, [r8+10h]; LoggerHandle
0x18001ed77  call    WPP_SF_aZs
0x18001ed7c  mov     r8, cs:WPP_GLOBAL_Control
0x18001ed83  mov     r9, [rsp+1F8h+var_128]
0x18001ed8b  lea     r10d, [rsi+1]
0x18001ed8f  lea     rdx, WPP_GLOBAL_Control
0x18001ed96  mov     rbx, [rdi+20h]
0x18001ed9a  mov     rax, [rdi+28h]
0x18001ed9e  mov     [rsp+1F8h+Block], rax
0x18001eda6  test    r12, r12
0x18001eda9  jz      short loc_18001EDB6
0x18001edab  mov     [r12], sil
0x18001edaf  mov     r8, cs:WPP_GLOBAL_Control
0x18001edb6  test    r9, r9
0x18001edb9  jz      short loc_18001EDC5
0x18001edbb  mov     [r9], esi
0x18001edbe  mov     r8, cs:WPP_GLOBAL_Control
0x18001edc5  test    r14b, 10h
0x18001edc9  mov     rcx, rbx
0x18001edcc  cmovnz  rcx, rsi
0x18001edd0  mov     [rsp+1F8h+var_168], rcx
0x18001edd8  cmp     r8, rdx
0x18001eddb  jz      short loc_18001EE3C
0x18001eddd  test    [r8+1Ch], r10b
0x18001ede1  jz      short loc_18001EE3C
0x18001ede3  cmp     byte ptr [r8+19h], 4
0x18001ede8  jb      short loc_18001EE3C
0x18001edea  mov     rax, [rdi]
0x18001eded  mov     ecx, [rax+24h]
0x18001edf0  mov     r9d, [rax+10h]
0x18001edf4  add     rax, 14h
0x18001edf8  mov     dword ptr [rsp+1F8h+var_198], r14d; char
0x18001edfd  mov     dword ptr [rsp+1F8h+var_1A0], ecx; char
0x18001ee01  mov     dword ptr [rsp+1F8h+var_1A8], r9d; char
0x18001ee06  mov     [rsp+1F8h+var_1B0], rax; __int64
0x18001ee0b  mov     rax, [rdi+30h]
0x18001ee0f  mov     [rsp+1F8h+var_1B8], rax; __int64
0x18001ee14  mov     rax, [rdi+28h]
0x18001ee18  mov     qword ptr [rsp+1F8h+var_1C0], rax; __int64
0x18001ee1d  mov     rax, [rdi+20h]
0x18001ee21  mov     qword ptr [rsp+1F8h+var_1C8], rax; __int64
0x18001ee26  mov     rax, [rdi+40h]
0x18001ee2a  mov     qword ptr [rsp+1F8h+OpenOptions], rax; __int64
0x18001ee2f  mov     [rsp+1F8h+ShareAccess], ecx; char
0x18001ee33  mov     rcx, [r8+10h]; LoggerHandle
0x18001ee37  call    WPP_SF_DDZZZZ_guid_DDL
0x18001ee3c  xorps   xmm0, xmm0
0x18001ee3f  movups  xmmword ptr [rsp+1F8h+IoStatusBlock], xmm0
0x18001ee47  mov     [rsp+1F8h+FileHandle], rsi
0x18001ee4f  mov     [rsp+1F8h+var_138], esi
0x18001ee56  mov     [rsp+1F8h+var_134], sil
0x18001ee5e  mov     qword ptr [rsp+1F8h+ObjectAttributes.Length], 30h ; '0'
0x18001ee6a  mov     [rsp+1F8h+ObjectAttributes.RootDirectory], rsi
0x18001ee72  mov     [rsp+1F8h+ObjectAttributes.ObjectName], rbx
0x18001ee7a  mov     qword ptr [rsp+1F8h+ObjectAttributes.Attributes], 40h ; '@'
0x18001ee86  movdqu  xmmword ptr [rsp+1F8h+ObjectAttributes.SecurityDescriptor], xmm0
0x18001ee8f  mov     [rsp+1F8h+OpenOptions], 21h ; '!'; OpenOptions
0x18001ee97  mov     [rsp+1F8h+ShareAccess], 7; ShareAccess
0x18001ee9f  lea     r9, [rsp+1F8h+IoStatusBlock]; IoStatusBlock
0x18001eea7  lea     r8, [rsp+1F8h+ObjectAttributes]; ObjectAttributes
0x18001eeaf  mov     edx, 100080h; DesiredAccess
0x18001eeb4  lea     rcx, [rsp+1F8h+FileHandle]; FileHandle
0x18001eebc  call    cs:__imp_NtOpenFile
0x18001eec2  mov     esi, eax
0x18001eec4  test    eax, eax
0x18001eec6  jns     short loc_18001EF08
0x18001eec8  bts     esi, 1Ch
0x18001eecc  mov     [rsp+1F8h+var_178], esi
0x18001eed3  mov     rcx, cs:WPP_GLOBAL_Control
0x18001eeda  lea     rdx, WPP_GLOBAL_Control
0x18001eee1  cmp     rcx, rdx
0x18001eee4  jz      loc_18001F826
0x18001eeea  test    byte ptr [rcx+1Ch], 1
0x18001eeee  jz      loc_18001F826
0x18001eef4  cmp     byte ptr [rcx+19h], 2
0x18001eef8  jb      loc_18001F826
0x18001eefe  mov     edx, 3Dh ; '='
0x18001ef03  jmp     loc_18001EF90
0x18001ef08  xorps   xmm0, xmm0
0x18001ef0b  movups  [rsp+1F8h+FsInformation], xmm0
0x18001ef13  movups  xmmword ptr [rsp+1F8h+var_68], xmm0
0x18001ef1b  movups  xmmword ptr [rsp+1F8h+var_68+0Ch], xmm0
0x18001ef23  mov     [rsp+1F8h+ShareAccess], 5; FsInformationClass
0x18001ef2b  mov     r9d, 2Ch ; ','; Length
0x18001ef31  lea     r8, [rsp+1F8h+FsInformation]; FsInformation
0x18001ef39  lea     rdx, [rsp+1F8h+IoStatusBlock]; IoStatusBlock
0x18001ef41  mov     rcx, [rsp+1F8h+FileHandle]; FileHandle
0x18001ef49  call    cs:__imp_NtQueryVolumeInformationFile
0x18001ef4f  mov     esi, eax
0x18001ef51  test    eax, eax
0x18001ef53  jns     short loc_18001EFC6
0x18001ef55  bts     esi, 1Ch
0x18001ef59  mov     [rsp+1F8h+var_178], esi
0x18001ef60  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ef67  lea     rdx, WPP_GLOBAL_Control
0x18001ef6e  cmp     rcx, rdx
0x18001ef71  jz      loc_18001F826
0x18001ef77  test    byte ptr [rcx+1Ch], 1
0x18001ef7b  jz      loc_18001F826
0x18001ef81  cmp     byte ptr [rcx+19h], 2
0x18001ef85  jb      loc_18001F826
0x18001ef8b  mov     edx, 3Eh ; '>'
0x18001ef90  mov     r9, [rdi]
0x18001ef93  mov     dword ptr [rsp+1F8h+var_1C0], esi; char
0x18001ef97  mov     qword ptr [rsp+1F8h+var_1C8], rbx; __int64
0x18001ef9c  mov     rax, [rdi+40h]
0x18001efa0  mov     qword ptr [rsp+1F8h+OpenOptions], rax; __int64
0x18001efa5  mov     eax, [r9+24h]
0x18001efa9  mov     [rsp+1F8h+ShareAccess], eax; char
0x18001efad  mov     r9d, [r9+10h]
0x18001efb1  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001efb8  mov     rcx, [rcx+10h]; LoggerHandle
0x18001efbc  call    WPP_SF_DDZZd
0x18001efc1  jmp     loc_18001F826
0x18001efc6  mov     eax, dword ptr [rsp+1F8h+FsInformation+8]
0x18001efcd  cmp     eax, 0FFFFh
0x18001efd2  ja      loc_18001F81A
0x18001efd8  cmp     ax, 20h ; ' '
0x18001efdc  ja      loc_18001F81A
0x18001efe2  mov     [rsp+1F8h+String2.Length], ax
0x18001efea  mov     [rsp+1F8h+String2.MaximumLength], ax
0x18001eff2  xor     eax, eax
0x18001eff4  mov     dword ptr [rsp+1F8h+String2+4], eax
0x18001effb  lea     rax, [rsp+1F8h+FsInformation+0Ch]
0x18001f003  mov     [rsp+1F8h+String2.Buffer], rax
0x18001f00b  mov     esi, 1
0x18001f010  mov     r8b, sil; CaseInsensitive
0x18001f013  lea     rdx, [rsp+1F8h+String2]; String2
0x18001f01b  lea     rcx, ?CsvfsFileSystemName@@3U_UNICODE_STRING@@B; String1
0x18001f022  call    cs:__imp_RtlEqualUnicodeString
0x18001f028  test    al, al
0x18001f02a  jz      loc_18001F35B
0x18001f030  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f037  lea     rbx, WPP_GLOBAL_Control
0x18001f03e  cmp     rcx, rbx
0x18001f041  jz      short loc_18001F087
0x18001f043  test    [rcx+1Ch], sil
0x18001f047  jz      short loc_18001F087
0x18001f049  cmp     byte ptr [rcx+19h], 4
0x18001f04d  jb      short loc_18001F087
0x18001f04f  mov     r9, [rdi]
0x18001f052  lea     edx, [rsi+3Eh]
0x18001f055  lea     rax, [rsp+1F8h+String2]
0x18001f05d  mov     qword ptr [rsp+1F8h+var_1C8], rax; __int64
0x18001f062  mov     rax, [rdi+40h]
0x18001f066  mov     qword ptr [rsp+1F8h+OpenOptions], rax; __int64
0x18001f06b  mov     eax, [r9+24h]
0x18001f06f  mov     [rsp+1F8h+ShareAccess], eax; char
0x18001f073  mov     r9d, [r9+10h]
0x18001f077  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001f07e  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f082  call    WPP_SF_DDZZ
0x18001f087  mov     [rsp+1F8h+Block], 0
0x18001f093  mov     dword ptr [rsp+1F8h+var_188], 0
0x18001f09b  lea     r8, [rsp+1F8h+var_188]
0x18001f0a0  lea     rdx, [rsp+1F8h+Block]
0x18001f0a8  mov     rcx, [rsp+1F8h+FileHandle]; Handle
0x18001f0b0  call    ?CsvQueryMdsPath@@YAJPEAXAEAV?$CHeapPtr@U_CSV_QUERY_MDS_PATH@@VCCRTAllocator@ATL@@@ATL@@AEAK@Z; CsvQueryMdsPath(void *,ATL::CHeapPtr<_CSV_QUERY_MDS_PATH,ATL::CCRTAllocator> &,ulong &)
0x18001f0b5  mov     esi, eax
0x18001f0b7  mov     [rsp+1F8h+var_178], eax
0x18001f0be  test    eax, eax
0x18001f0c0  jns     short loc_18001F11F
0x18001f0c2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f0c9  cmp     rcx, rbx
0x18001f0cc  jz      short loc_18001F10C
0x18001f0ce  test    byte ptr [rcx+1Ch], 1
0x18001f0d2  jz      short loc_18001F10C
0x18001f0d4  cmp     byte ptr [rcx+19h], 2
0x18001f0d8  jb      short loc_18001F10C
0x18001f0da  mov     r9, [rdi]
0x18001f0dd  mov     edx, 40h ; '@'
0x18001f0e2  mov     dword ptr [rsp+1F8h+var_1C8], eax
0x18001f0e6  mov     rax, [rdi+40h]
0x18001f0ea  mov     qword ptr [rsp+1F8h+OpenOptions], rax
0x18001f0ef  mov     eax, [r9+24h]
0x18001f0f3  mov     [rsp+1F8h+ShareAccess], eax
0x18001f0f7  mov     r9d, [r9+10h]
0x18001f0fb  lea     r8, WPP_0e4f52959e84311ee6e5571afd0bb0f5_Traceguids
0x18001f102  mov     rcx, [rcx+10h]
0x18001f106  call    WPP_SF_DDZd
0x18001f10b  nop
0x18001f10c  mov     rcx, [rsp+1F8h+Block]; Block
0x18001f114  call    cs:__imp_free
0x18001f11a  jmp     loc_18001F826
0x18001f11f  xorps   xmm0, xmm0
0x18001f122  movups  xmmword ptr [rsp+1F8h+var_150.Length], xmm0
0x18001f12a  mov     rbx, [rsp+1F8h+Block]
0x18001f132  mov     eax, [rbx+8]
0x18001f135  mov     ecx, 0FFFEh
0x18001f13a  cmp     eax, ecx
0x18001f13c  jnb     short loc_18001F148
0x18001f13e  mov     [rsp+1F8h+var_150.MaximumLength], ax
0x18001f146  jmp     short loc_18001F153
0x18001f148  movzx   eax, cx
0x18001f14b  mov     [rsp+1F8h+var_150.MaximumLength], cx
0x18001f153  mov     [rsp+1F8h+var_150.Length], ax
0x18001f15b  lea     rax, [rbx+0Ch]
0x18001f15f  mov     [rsp+1F8h+var_150.Buffer], rax
0x18001f167  movups  xmmword ptr [rsp+1F8h+var_120.Length], xmm0
0x18001f16f  mov     [rsp+1F8h+var_188], 0
0x18001f178  lea     rax, [rsp+1F8h+var_188]
0x18001f17d  mov     qword ptr [rsp+1F8h+ShareAccess], rax; __int64
0x18001f182  lea     r9, [rsp+1F8h+var_120]; struct _UNICODE_STRING *
0x18001f18a  lea     r8, ?BackslashString@@3U_UNICODE_STRING@@B; struct _UNICODE_STRING *
0x18001f191  lea     rdx, [rsp+1F8h+var_150]; struct _UNICODE_STRING *
0x18001f199  xor     ecx, ecx; struct _UNICODE_STRING *
0x18001f19b  call    ?CopyUnicodeStringToBuffer@@YAJPEBU_UNICODE_STRING@@00PEAU1@AEAV?$CHeapPtr@GVCCRTAllocator@ATL@@@ATL@@@Z; CopyUnicodeStringToBuffer(_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING const *,_UNICODE_STRING *,ATL::CHeapPtr<ushort,ATL::CCRTAllocator> &)
0x18001f1a0  mov     esi, eax
0x18001f1a2  mov     [rsp+1F8h+var_178], eax
0x18001f1a9  test    eax, eax
0x18001f1ab  jns     short loc_18001F1C1
0x18001f1ad  mov     rcx, [rsp+1F8h+var_188]; Block
0x18001f1b2  call    cs:__imp_free
0x18001f1b8  nop
0x18001f1b9  mov     rcx, rbx
0x18001f1bc  jmp     loc_18001F114
0x18001f1c1  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f1c8  lea     rdx, WPP_GLOBAL_Control
0x18001f1cf  cmp     rcx, rdx
0x18001f1d2  jz      short loc_18001F229
0x18001f1d4  test    byte ptr [rcx+1Ch], 1
0x18001f1d8  jz      short loc_18001F229
0x18001f1da  cmp     byte ptr [rcx+19h], 4
0x18001f1de  jb      short loc_18001F229
0x18001f1e0  mov     r9, [rdi]
0x18001f1e3  lea     rax, [rsp+1F8h+var_120]
0x18001f1eb  mov     [rsp+1F8h+var_1B8], rax; __int64
0x18001f1f0  mov     eax, [rbx+4]
0x18001f1f3  mov     dword ptr [rsp+1F8h+var_1C0], eax; char
0x18001f1f7  mov     eax, [rbx]
0x18001f1f9  mov     dword ptr [rsp+1F8h+var_1C8], eax; char
0x18001f1fd  mov     rax, [rdi+40h]
0x18001f201  mov     qword ptr [rsp+1F8h+OpenOptions], rax; __int64
0x18001f206  mov     eax, [r9+24h]
0x18001f20a  mov     [rsp+1F8h+ShareAccess], eax; char
0x18001f20e  mov     r9d, [r9+10h]
0x18001f212  mov     rcx, [rcx+10h]; LoggerHandle
0x18001f216  call    WPP_SF_DDZDDZ
0x18001f21b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f222  lea     rdx, WPP_GLOBAL_Control
0x18001f229  mov     eax, [rbx+4]
0x18001f22c  cmp     [rbx], eax
0x18001f22e  jz      short loc_18001F2A5
0x18001f230  cmp     rcx, rdx
0x18001f233  jz      short loc_18001F27B
0x18001f235  test    byte ptr [rcx+1Ch], 1
0x18001f239  jz      short loc_18001F27B
0x18001f23b  cmp     byte ptr [rcx+19h], 4
0x18001f23f  jb      short loc_18001F27B
  ... truncated ...
```
