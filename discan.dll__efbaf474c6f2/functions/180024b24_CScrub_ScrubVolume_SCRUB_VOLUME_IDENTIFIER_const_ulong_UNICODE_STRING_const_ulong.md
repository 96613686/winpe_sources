# CScrub::ScrubVolume(_SCRUB_VOLUME_IDENTIFIER const *,ulong,_UNICODE_STRING const *,ulong *)

- ea: `0x180024b24`
- end: `0x180026ee6`
- name: `?ScrubVolume@CScrub@@QEAAJPEBU_SCRUB_VOLUME_IDENTIFIER@@KPEBU_UNICODE_STRING@@PEAK@Z`
- size: `9154`
- prototype: `__int64 __fastcall(CScrub *this, const struct _SCRUB_VOLUME_IDENTIFIER *, int, struct _UNICODE_STRING *, unsigned int *)`
- caller_count: `1`
- callee_count: `40`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001ec84`

## callees

- `0x180003180`
- `0x1800032f8`
- `0x180006688`
- `0x180006b80`
- `0x1800088a4`
- `0x180009088`
- `0x18000ece0`
- `0x18001018c`
- `0x180012048`
- `0x180012158`
- `0x1800136c0`
- `0x1800137d4`
- `0x1800177c4`
- `0x180018ed8`
- `0x18001c024`
- `0x18001fc04`
- `0x18001fde0`
- `0x1800200dc`
- `0x180021aac`
- `0x180024280`
- `0x180024b24`
- `0x180026eec`
- `0x180027184`
- `0x1800273d8`
- `0x1800277e0`
- `0x1800299f0`
- `0x18002b6b0`
- `0x18002b778`
- `0x18002bb08`
- `0x18002c960`
- `0x18002ca98`
- `0x18002e168`
- `0x18002e55c`
- `0x18002eabc`
- `0x18002eddc`
- `0x18002f040`
- `0x180030c08`
- `0x180030fc0`
- `0x1800375ee`
- `0x180037620`

## import_xrefs

- `ntdll!NtClearEvent` at `0x180024e0c`
- `ntdll!NtClearEvent` at `0x180025034`
- `ntdll!NtClearEvent` at `0x180024e0c`
- `ntdll!NtClearEvent` at `0x180025034`
- `ntdll!NtSetEvent` at `0x180026183`
- `ntdll!NtSetEvent` at `0x1800262fa`
- `ntdll!NtSetEvent` at `0x180026183`
- `ntdll!NtSetEvent` at `0x1800262fa`
- `ntdll!NtWaitForSingleObject` at `0x1800265a9`
- `ntdll!NtWaitForSingleObject` at `0x1800265ca`
- `ntdll!NtWaitForSingleObject` at `0x1800265a9`
- `ntdll!NtWaitForSingleObject` at `0x1800265ca`
- `ntdll!NtOpenFile` at `0x180024eda`
- `ntdll!NtOpenFile` at `0x180024eda`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800265fa`
- `KERNEL32!QueryPerformanceFrequency` at `0x1800265fa`
- `KERNEL32!GetTickCount64` at `0x180025054`
- `KERNEL32!GetTickCount64` at `0x180025054`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180024e59`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180024e82`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800261ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026322`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800263ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026452`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180024e59`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180024e82`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800261ab`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026322`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1800263ec`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x180026452`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180024e1c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180024e70`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800260fc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002627a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180024e1c`
- `KERNEL32!AcquireSRWLockExclusive` at `0x180024e70`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1800260fc`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18002627a`
- `KERNEL32!CreateThreadpoolWork` at `0x180025ab9`
- `KERNEL32!CreateThreadpoolWork` at `0x180025c4c`
- `KERNEL32!CreateThreadpoolWork` at `0x180025ab9`
- `KERNEL32!CreateThreadpoolWork` at `0x180025c4c`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180025fb6`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180026044`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180025fb6`
- `KERNEL32!WaitForThreadpoolWorkCallbacks` at `0x180026044`
- `KERNEL32!SubmitThreadpoolWork` at `0x180025f6f`
- `KERNEL32!SubmitThreadpoolWork` at `0x180025f6f`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180024fa8`
- `api-ms-win-devices-config-l1-1-1!CM_Register_Notification` at `0x180024fa8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180024fb8`
- `api-ms-win-devices-config-l1-1-1!CM_MapCrToWin32Err` at `0x180024fb8`

## pseudocode

```c
__int64 __fastcall CScrub::ScrubVolume(
        CScrub *this,
        const struct _SCRUB_VOLUME_IDENTIFIER *a2,
        int a3,
        struct _UNICODE_STRING *a4,
        unsigned int *a5)
{
  __int64 v8; // rdx
  USHORT v9; // dx
  USHORT Length; // cx
  USHORT v11; // ax
  struct _UNICODE_STRING *v12; // rbx
  __int64 v13; // rsi
  struct _UNICODE_STRING *v14; // r13
  int v15; // r12d
  struct _UNICODE_STRING *v16; // rcx
  unsigned int i; // edx
  __int64 v18; // rcx
  PVOID *v19; // rcx
  _QWORD *v20; // rdx
  _SCRUB_DIRECTORY_ENTRY *v21; // rcx
  __int64 v22; // rax
  RTL_SRWLOCK *v23; // rsi
  NTSTATUS v24; // r14d
  int started; // r14d
  void *v26; // r14
  CONFIGRET v27; // eax
  signed int v28; // eax
  unsigned int v29; // ecx
  unsigned int j; // r8d
  int k; // r8d
  PVOID *v32; // r14
  __int64 v33; // rax
  USHORT v34; // cx
  const struct _UNICODE_STRING *v35; // r9
  _QWORD *v36; // rcx
  int v37; // edx
  _QWORD *v38; // r13
  unsigned int m; // r14d
  unsigned int n; // r14d
  __int64 v41; // rdx
  struct _UNICODE_STRING *v42; // rcx
  unsigned int v43; // r14d
  __int64 v44; // r12
  PTP_WORK ThreadpoolWork; // rax
  CScrub **v46; // r8
  CScrub *v47; // rcx
  _QWORD *v48; // rcx
  int v49; // edx
  unsigned int v50; // r14d
  struct _SCRUB_ENVIRONMENT **v51; // r12
  __int64 v52; // r12
  PTP_WORK v53; // rax
  CScrub **v54; // r8
  CScrub *v55; // rcx
  int v56; // r8d
  PVOID *v57; // rcx
  _QWORD **v58; // r12
  _QWORD **v59; // r13
  unsigned int v60; // ebx
  unsigned int v61; // ebx
  int v62; // r8d
  unsigned int ii; // ebx
  unsigned int v64; // ebx
  _QWORD *jj; // rax
  int v66; // r8d
  unsigned int kk; // ebx
  unsigned int v68; // ebx
  _QWORD *mm; // rax
  int v70; // r14d
  int v72; // edi
  int v73; // r8d
  unsigned int nn; // ebx
  __int64 v75; // r10
  __int64 v76; // r8
  struct _SCRUB_THREAD_CONTEXT *v77; // rdx
  unsigned int i1; // ebx
  __int64 v79; // r10
  __int64 v80; // r8
  struct _SCRUB_THREAD_CONTEXT *v81; // rdx
  __int64 v82; // rbx
  PVOID *v83; // r10
  int ParityExtentRecordCount; // eax
  struct _UNICODE_STRING v85; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v86; // [rsp+70h] [rbp-90h] BYREF
  const char *v87; // [rsp+78h] [rbp-88h] BYREF
  int v88; // [rsp+80h] [rbp-80h]
  int v89; // [rsp+88h] [rbp-78h]
  __int64 v90; // [rsp+90h] [rbp-70h] BYREF
  int v91; // [rsp+98h] [rbp-68h]
  char v92; // [rsp+9Ch] [rbp-64h]
  struct _UNICODE_STRING *v93; // [rsp+A0h] [rbp-60h] BYREF
  struct _SCRUB_ENVIRONMENT **v94; // [rsp+A8h] [rbp-58h]
  struct _UNICODE_STRING *v95; // [rsp+B0h] [rbp-50h] BYREF
  LARGE_INTEGER Frequency; // [rsp+B8h] [rbp-48h] BYREF
  _QWORD v97[2]; // [rsp+C0h] [rbp-40h] BYREF
  void *FileHandle; // [rsp+D0h] [rbp-30h] BYREF
  int v99; // [rsp+D8h] [rbp-28h]
  char v100; // [rsp+DCh] [rbp-24h]
  __int64 v101; // [rsp+E0h] [rbp-20h] BYREF
  struct _UNICODE_STRING v102; // [rsp+E8h] [rbp-18h] BYREF
  struct _UNICODE_STRING v103; // [rsp+F8h] [rbp-8h] BYREF
  struct _UNICODE_STRING *v104; // [rsp+108h] [rbp+8h]
  unsigned int *v105; // [rsp+110h] [rbp+10h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+118h] [rbp+18h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+148h] [rbp+48h] BYREF
  _DWORD v108[4]; // [rsp+160h] [rbp+60h] BYREF
  void *v109; // [rsp+170h] [rbp+70h]

  v104 = a4;
  v89 = a3;
  v105 = a5;
  v8 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + (unsigned int)tls_index);
  *(_QWORD *)(v8 + 16) = "CScrub::ScrubVolume";
  v87 = "CScrub::ScrubVolume";
  v88 = 0;
  v9 = ++*(_WORD *)(v8 + 8);
  Length = GlobalIndentString.Length;
  v11 = GlobalIndentString.Length;
  if ( v9 < GlobalIndentString.Length )
    v11 = v9;
  LOWORD(v97[0]) = v11;
  if ( v9 < GlobalIndentString.Length )
    Length = v9;
  WORD1(v97[0]) = Length;
  HIDWORD(v97[0]) = 0;
  v97[1] = off_180047060;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_aZs(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)"CScrub::ScrubVolume");
  }
  v12 = (struct _UNICODE_STRING *)*((_QWORD *)a2 + 4);
  v13 = *((_QWORD *)a2 + 6);
  v14 = (struct _UNICODE_STRING *)*((_QWORD *)a2 + 7);
  v95 = v14;
  if ( a5 )
    *a5 = 0;
  *(_QWORD *)this = a2;
  *((_BYTE *)this + 1497) = 1;
  v15 = a3 & 0x10;
  v16 = v12;
  if ( (a3 & 0x10) != 0 )
    v16 = 0;
  v93 = v16;
  *((_DWORD *)this + 315) = a3;
  *((_DWORD *)this + 378) = 0;
  for ( i = 0; i < *((_DWORD *)this + 335); ++i )
  {
    v18 = 35024LL * i;
    *(_BYTE *)(v18 + *((_QWORD *)this + 177) + 24) = 0;
    *(_QWORD *)(v18 + *((_QWORD *)this + 177) + 34488) = 0;
  }
  v19 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)v12);
      v19 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v19 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
      {
        WPP_SF_DDZZ(
          (TRACEHANDLE)v19[2],
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          v13);
        v19 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v19 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
        {
          WPP_SF_DDZZ(
            (TRACEHANDLE)v19[2],
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            (__int64)v14);
          v19 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v19 != &WPP_GLOBAL_Control && (*((_BYTE *)v19 + 28) & 1) != 0 && *((_BYTE *)v19 + 25) >= 4u )
          WPP_SF_DDZL(
            (unsigned int)v19[2],
            i,
            1,
            *(_DWORD *)(**(_QWORD **)this + 16LL),
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            a3);
      }
    }
  }
  NtClearEvent(*((HANDLE *)this + 152));
  AcquireSRWLockExclusive((PSRWLOCK)this + 181);
  while ( 1 )
  {
    v20 = (_QWORD *)((char *)this + 1432);
    v21 = (_SCRUB_DIRECTORY_ENTRY *)*((_QWORD *)this + 179);
    if ( v21 == (CScrub *)((char *)this + 1432) )
      break;
    if ( *((_QWORD **)v21 + 1) != v20
      || (v22 = *(_QWORD *)v21, *(_SCRUB_DIRECTORY_ENTRY **)(*(_QWORD *)v21 + 8LL) != v21) )
    {
      __fastfail(3u);
    }
    *v20 = v22;
    *(_QWORD *)(v22 + 8) = v20;
    _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'(v21, (unsigned int)v20);
  }
  ReleaseSRWLockExclusive((PSRWLOCK)this + 181);
  v97[0] = 0;
  v23 = (RTL_SRWLOCK *)((char *)this + 1472);
  AcquireSRWLockExclusive((PSRWLOCK)this + 184);
  CScrub::_DrainFileQueue(this);
  ReleaseSRWLockExclusive((PSRWLOCK)this + 184);
  v101 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 64;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = v12;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  IoStatusBlock = 0;
  FileHandle = 0;
  v99 = 0;
  v100 = 0;
  v24 = NtOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 7u, 0);
  if ( v24 < 0 )
  {
    started = v24 | 0x10000000;
    v88 = started;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDZZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)v12,
        started);
    }
LABEL_299:
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)&v101);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)v97);
    CAutoClearVolumeCheckpoint::~CAutoClearVolumeCheckpoint((CAutoClearVolumeCheckpoint *)&v93);
    CHResultImp::~CHResultImp((CHResultImp *)&v87);
    return (unsigned int)started;
  }
  v26 = FileHandle;
  *((_QWORD *)this + 3) = FileHandle;
  memset_0(v108, 0, 0x1A0u);
  v108[0] = 416;
  v108[2] = 1;
  v109 = v26;
  v90 = 0;
  v91 = 0;
  v92 = 0;
  v27 = CM_Register_Notification(v108, this, &CScrub::_VolumeNotifyCallback, &v90);
  if ( v27 )
  {
    v28 = CM_MapCrToWin32Err(v27, 0xDu);
    v29 = v28;
    if ( v28 > 0 )
      v29 = (unsigned __int16)v28 | 0x80070000;
    v88 = v29;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v29);
    }
    CHandleT<void *,NtHandleTrait>::Detach(&v90);
  }
  NtClearEvent(*((HANDLE *)this + 154));
  v86 = *((_QWORD *)this + 154);
  v103 = 0;
  v102 = 0;
  *((_QWORD *)this + 166) = GetTickCount64();
  for ( j = 0; j < *((_DWORD *)this + 335); ++j )
    *(_QWORD *)(35024LL * j + *((_QWORD *)this + 177) + 1656) = *((_QWORD *)this + 166);
  for ( k = 0; (unsigned int)k < *((_DWORD *)this + 343); ++k )
    *(_QWORD *)(35024LL * (unsigned int)k + *((_QWORD *)this + 178) + 1656) = *((_QWORD *)this + 166);
  if ( v15 )
  {
    v32 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      goto LABEL_74;
    }
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)this + 16LL),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL));
  }
  else
  {
    v88 = CScrubCheckpoint::Initialize(
            (CScrub *)((char *)this + 1264),
            *(struct _UNICODE_STRING **)(*(_QWORD *)this + 32LL),
            FileHandle,
            0);
    if ( v88 >= 0 )
    {
      v85 = 0;
      v33 = *((_QWORD *)this + 163);
      v34 = *(_WORD *)(v33 + 280);
      v85.MaximumLength = v34;
      v85.Length = v34;
      if ( v34 )
        v85.Buffer = (PWSTR)(v33 + 288);
      else
        v85.Buffer = 0;
      v32 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          (__int64)&v85);
        v32 = (PVOID *)WPP_GLOBAL_Control;
        v34 = v85.Length;
      }
      if ( !v34 )
        goto LABEL_74;
      k = ParseCheckpointPath(&v85, &v103, &v102);
      v88 = k;
      if ( k >= 0 || v32 == &WPP_GLOBAL_Control || (*((_BYTE *)v32 + 28) & 1) == 0 || *((_BYTE *)v32 + 25) < 2u )
        goto LABEL_74;
      WPP_SF_DDZd(
        (unsigned int)v32[2],
        17,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        k);
    }
  }
  v32 = (PVOID *)WPP_GLOBAL_Control;
LABEL_74:
  v89 &= 0x40u;
  if ( v89 )
  {
    started = CScrubJetNameTable::SetupSystemVolumeInformation(v12);
    v88 = started;
    if ( started < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v37 = 19;
      goto LABEL_80;
    }
    started = CScrubJetNameTable::SetupNames(
                (CScrub *)((char *)this + 32),
                *(const struct _UNICODE_STRING **)(*(_QWORD *)this + 32LL),
                *(const struct _GUID **)(*(_QWORD *)this + 24LL),
                v35);
    v88 = started;
    if ( started < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v37 = 20;
      goto LABEL_80;
    }
    started = CScrubJetInstance::StartJetInstance(
                (CScrub *)((char *)this + 64),
                *((const unsigned __int16 **)this + 4),
                DiscanJetBaseName,
                *((const unsigned __int16 **)this + 5),
                *((const unsigned __int16 **)this + 5),
                *((const unsigned __int16 **)this + 7));
    v88 = started;
    if ( started < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v37 = 21;
      goto LABEL_80;
    }
    started = CScrubDatabase::OpenJetDatabase(
                (CScrub *)((char *)this + 80),
                *((_QWORD *)this + 9),
                *((const unsigned __int16 **)this + 6));
    v88 = started;
    if ( started < 0 )
    {
      v36 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_81;
      }
      v37 = 22;
LABEL_80:
      WPP_SF_DDZd(
        v36[2],
        v37,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        started);
      goto LABEL_81;
    }
    v32 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v32 != &WPP_GLOBAL_Control )
  {
    v38 = (_QWORD *)*((_QWORD *)this + 163);
    if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
    {
      WPP_SF_DDZZ(
        (TRACEHANDLE)v32[2],
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)&v103);
      v32 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v32 != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
      {
        WPP_SF_DDZZ(
          (TRACEHANDLE)v32[2],
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          (__int64)&v102);
        v32 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v32 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
        {
          WPP_SF_DDZi(
            (unsigned int)v32[2],
            25,
            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
            *(_DWORD *)(**(_QWORD **)this + 16LL),
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            v38[2]);
          v32 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v32 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
          {
            WPP_SF_DDZi(
              (unsigned int)v32[2],
              26,
              (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
              *(_DWORD *)(**(_QWORD **)this + 16LL),
              *(_DWORD *)(**(_QWORD **)this + 36LL),
              *(_QWORD *)(*(_QWORD *)this + 64LL),
              v38[3]);
            v32 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v32 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
            {
              WPP_SF_DDZi(
                (unsigned int)v32[2],
                27,
                (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                *(_DWORD *)(**(_QWORD **)this + 16LL),
                *(_DWORD *)(**(_QWORD **)this + 36LL),
                *(_QWORD *)(*(_QWORD *)this + 64LL),
                v38[4]);
              v32 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v32 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
              {
                WPP_SF_DDZI(
                  (unsigned int)v32[2],
                  28,
                  k,
                  *(_DWORD *)(**(_QWORD **)this + 16LL),
                  *(_DWORD *)(**(_QWORD **)this + 36LL),
                  *(_QWORD *)(*(_QWORD *)this + 64LL),
                  v38[5]);
                v32 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v32 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
                {
                  WPP_SF_DDZI(
                    (unsigned int)v32[2],
                    29,
                    k,
                    *(_DWORD *)(**(_QWORD **)this + 16LL),
                    *(_DWORD *)(**(_QWORD **)this + 36LL),
                    *(_QWORD *)(*(_QWORD *)this + 64LL),
                    v38[6]);
                  v32 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v32 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
                  {
                    WPP_SF_DDZI(
                      (unsigned int)v32[2],
                      30,
                      k,
                      *(_DWORD *)(**(_QWORD **)this + 16LL),
                      *(_DWORD *)(**(_QWORD **)this + 36LL),
                      *(_QWORD *)(*(_QWORD *)this + 64LL),
                      v38[7]);
                    v32 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v32 != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
                    {
                      WPP_SF_DDZI(
                        (unsigned int)v32[2],
                        31,
                        k,
                        *(_DWORD *)(**(_QWORD **)this + 16LL),
                        *(_DWORD *)(**(_QWORD **)this + 36LL),
                        *(_QWORD *)(*(_QWORD *)this + 64LL),
                        v38[8]);
                      v32 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v32 != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
                      {
                        WPP_SF_DDZI(
                          (unsigned int)v32[2],
                          32,
                          k,
                          *(_DWORD *)(**(_QWORD **)this + 16LL),
                          *(_DWORD *)(**(_QWORD **)this + 36LL),
                          *(_QWORD *)(*(_QWORD *)this + 64LL),
                          v38[9]);
                        v32 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v32 != &WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
                        {
                          WPP_SF_DDZi(
                            (unsigned int)v32[2],
                            33,
                            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                            *(_DWORD *)(**(_QWORD **)this + 16LL),
                            *(_DWORD *)(**(_QWORD **)this + 36LL),
                            *(_QWORD *)(*(_QWORD *)this + 64LL),
                            v38[10]);
                          v32 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v32 != &WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
                          {
                            WPP_SF_DDZi(
                              (unsigned int)v32[2],
                              34,
                              (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                              *(_DWORD *)(**(_QWORD **)this + 16LL),
                              *(_DWORD *)(**(_QWORD **)this + 36LL),
                              *(_QWORD *)(*(_QWORD *)this + 64LL),
                              v38[11]);
                            v32 = (PVOID *)WPP_GLOBAL_Control;
                          }
                          if ( v32 != &WPP_GLOBAL_Control )
                          {
                            if ( (*((_BYTE *)v32 + 28) & 1) != 0 && *((_BYTE *)v32 + 25) >= 4u )
                            {
                              WPP_SF_DDZi(
                                (unsigned int)v32[2],
                                35,
                                (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                                *(_DWORD *)(**(_QWORD **)this + 16LL),
                                *(_DWORD *)(**(_QWORD **)this + 36LL),
                                *(_QWORD *)(*(_QWORD *)this + 64LL),
                                v38[12]);
                              v32 = (PVOID *)WPP_GLOBAL_Control;
                            }
                            if ( v32 != &WPP_GLOBAL_Control
                              && (*((_BYTE *)v32 + 28) & 1) != 0
                              && *((_BYTE *)v32 + 25) >= 4u )
                            {
                              WPP_SF_DDZi(
                                (unsigned int)v32[2],
                                36,
                                (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                                *(_DWORD *)(**(_QWORD **)this + 16LL),
                                *(_DWORD *)(**(_QWORD **)this + 36LL),
                                *(_QWORD *)(*(_QWORD *)this + 64LL),
                                v38[13]);
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  for ( m = 0; m < *((_DWORD *)this + 335); ++m )
    memset_0((void *)(*((_QWORD *)this + 177) + 1480LL + 35024LL * m), 0, 0xB0u);
  for ( n = 0; n < *((_DWORD *)this + 343); ++n )
    memset_0((void *)(*((_QWORD *)this + 178) + 1480LL + 35024LL * n), 0, 0xB0u);
  *(struct _UNICODE_STRING *)(*((_QWORD *)this + 177) + 34464LL) = v103;
  v41 = *((_QWORD *)this + 177);
  if ( *(_WORD *)(v41 + 34464) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        (__int64)&v103,
        (__int64)&v102);
      v41 = *((_QWORD *)this + 177);
    }
    v42 = &v102;
    if ( !v102.Length )
      v42 = 0;
    *(_QWORD *)(v41 + 34480) = v42;
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)this + 16LL),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL));
  }
  v43 = 0;
  v94 = (struct _SCRUB_ENVIRONMENT **)((char *)this + 8);
  while ( v43 < *((_DWORD *)this + 335) )
  {
    v44 = 35024LL * v43;
    *(_DWORD *)(*((_QWORD *)this + 177) + v44 + 36) = 0;
    *(_DWORD *)(v44 + *((_QWORD *)this + 177) + 40) = 0;
    *(_DWORD *)(v44 + *((_QWORD *)this + 177) + 32) = 0;
    *(_QWORD *)(v44 + *((_QWORD *)this + 177) + 48) = 0;
    *(_QWORD *)(v44 + *((_QWORD *)this + 177) + 56) = 0;
    *(_WORD *)(v44 + *((_QWORD *)this + 177) + 34496) = 0;
    *(_QWORD *)(v44 + *((_QWORD *)this + 177) + 64) = this;
    v94 = (struct _SCRUB_ENVIRONMENT **)((char *)this + 8);
    ThreadpoolWork = CreateThreadpoolWork(
                       CScrub::_ScrubDirectoryQueue,
                       (PVOID)(v44 + *((_QWORD *)this + 177)),
                       *(PTP_CALLBACK_ENVIRON *)(*((_QWORD *)this + 1) + 72LL));
    *(_QWORD *)&v85.Length = ThreadpoolWork;
    LODWORD(v85.Buffer) = 0;
    BYTE4(v85.Buffer) = 0;
    if ( !ThreadpoolWork )
    {
      started = ATL::AtlHresultFromLastError();
      v88 = started;
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v49 = 39;
        goto LABEL_181;
      }
      goto LABEL_182;
    }
    *(_QWORD *)&v85.Length = 0;
    *(_QWORD *)(*((_QWORD *)this + 175) + 16LL * v43) = ThreadpoolWork;
    *(_QWORD *)(v44 + *((_QWORD *)this + 177) + 16) = *(_QWORD *)(*((_QWORD *)this + 175) + 16LL * v43);
    if ( v43 )
    {
      v46 = (CScrub **)*((_QWORD *)this + 170);
      if ( *v46 != (CScrub *)((char *)this + 1352) )
LABEL_188:
        __fastfail(3u);
      v47 = (CScrub *)(v44 + *((_QWORD *)this + 177));
      *(_QWORD *)v47 = (char *)this + 1352;
      *((_QWORD *)v47 + 1) = v46;
      *v46 = v47;
      *((_QWORD *)this + 170) = v47;
    }
    CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(&v85);
    ++v43;
  }
  v50 = 0;
  v51 = v94;
  while ( v50 < *((_DWORD *)this + 343) )
  {
    v52 = 35024LL * v50;
    *(_DWORD *)(v52 + *((_QWORD *)this + 178) + 36) = 0;
    *(_DWORD *)(v52 + *((_QWORD *)this + 178) + 40) = 0;
    *(_DWORD *)(v52 + *((_QWORD *)this + 178) + 32) = 0;
    *(_QWORD *)(v52 + *((_QWORD *)this + 178) + 48) = 0;
    *(_QWORD *)(v52 + *((_QWORD *)this + 178) + 56) = 0;
    *(_WORD *)(v52 + *((_QWORD *)this + 178) + 34496) = 0;
    *(_QWORD *)(v52 + *((_QWORD *)this + 178) + 64) = this;
    v53 = CreateThreadpoolWork(
            CScrub::_ScrubFileQueue,
            (PVOID)(v52 + *((_QWORD *)this + 178)),
            *((PTP_CALLBACK_ENVIRON *)*v94 + 9));
    *(_QWORD *)&v85.Length = v53;
    LODWORD(v85.Buffer) = 0;
    BYTE4(v85.Buffer) = 0;
    if ( !v53 )
    {
      started = ATL::AtlHresultFromLastError();
      v88 = started;
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v49 = 40;
LABEL_181:
        WPP_SF_DDZd(
          v48[2],
          v49,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          *(_DWORD *)(**(_QWORD **)this + 16LL),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          started);
      }
LABEL_182:
      CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(&v85);
LABEL_81:
      CAutoSetEvent::~CAutoSetEvent((CAutoSetEvent *)&v86);
      CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>::~CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>(&v90);
      goto LABEL_299;
    }
    *(_QWORD *)&v85.Length = 0;
    *(_QWORD *)(*((_QWORD *)this + 176) + 16LL * v50) = v53;
    *(_QWORD *)(v52 + *((_QWORD *)this + 178) + 16) = *(_QWORD *)(*((_QWORD *)this + 176) + 16LL * v50);
    v54 = (CScrub **)*((_QWORD *)this + 174);
    if ( *v54 != (CScrub *)((char *)this + 1384) )
      goto LABEL_188;
    v55 = (CScrub *)(v52 + *((_QWORD *)this + 178));
    *(_QWORD *)v55 = (char *)this + 1384;
    *((_QWORD *)v55 + 1) = v54;
    *v54 = v55;
    *((_QWORD *)this + 174) = v55;
    CHandleT<_TP_WORK *,ThreadPoolWorkTrait>::~CHandleT<_TP_WORK *,ThreadPoolWorkTrait>(&v85);
    ++v50;
    v51 = (struct _SCRUB_ENVIRONMENT **)((char *)this + 8);
    v94 = (struct _SCRUB_ENVIRONMENT **)((char *)this + 8);
  }
  if ( !*(_WORD *)(*((_QWORD *)this + 177) + 34464LL) )
  {
    v56 = CScrub::ScrubVolumeDasd(this, *(const struct _UNICODE_STRING **)(*(_QWORD *)this + 40LL));
    v88 = v56;
    if ( v56 == -805306102 )
    {
      v93 = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZ(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          41,
          (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
          *(_DWORD *)(**(_QWORD **)this + 16LL),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL));
      }
      goto LABEL_298;
    }
    if ( v56 < 0
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        42,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v56);
    }
  }
  started = CScrub::ScrubRootDirectory(this, v12, v95);
  v88 = started;
  if ( started == -805306102 )
  {
    v57 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        *((_QWORD *)this + 177) + 34496LL);
      v57 = (PVOID *)WPP_GLOBAL_Control;
    }
    v93 = 0;
    if ( v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 4u )
    {
      WPP_SF_DDZ(
        (unsigned int)v57[2],
        44,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL));
      v57 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( *((_DWORD *)*v51 + 2) != 1 )
      goto LABEL_81;
  }
  else
  {
    v57 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( started < 0 && v57 != &WPP_GLOBAL_Control && (*((_BYTE *)v57 + 28) & 1) != 0 && *((_BYTE *)v57 + 25) >= 2u )
    WPP_SF_DDZd(
      (unsigned int)v57[2],
      45,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)this + 16LL),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL),
      started);
  if ( *((_DWORD *)*v51 + 2) != 1 )
  {
    CScrub::_ScrubDirectoryQueue(0, *((PVOID *)this + 177), 0);
    goto LABEL_302;
  }
  SubmitThreadpoolWork(**((PTP_WORK **)this + 175));
  v58 = (_QWORD **)((char *)this + 1352);
  v59 = (_QWORD **)((char *)this + 1384);
  while ( 1 )
  {
    v60 = 0;
    if ( *((_DWORD *)this + 335) )
    {
      do
      {
        WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(*((_QWORD *)this + 175) + 16LL * v60), 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            46,
            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
            *(_DWORD *)(**(_QWORD **)this + 16LL),
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            v60);
        }
        ++v60;
      }
      while ( v60 < *((_DWORD *)this + 335) );
      v23 = (RTL_SRWLOCK *)((char *)this + 1472);
    }
    v61 = 0;
    if ( *((_DWORD *)this + 343) )
    {
      do
      {
        WaitForThreadpoolWorkCallbacks(*(PTP_WORK *)(*((_QWORD *)this + 176) + 16LL * v61), 0);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_DDZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            47,
            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
            *(_DWORD *)(**(_QWORD **)this + 16LL),
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            v61);
        }
        ++v61;
      }
      while ( v61 < *((_DWORD *)this + 343) );
      v59 = (_QWORD **)((char *)this + 1384);
    }
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        48,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL));
    }
    AcquireSRWLockExclusive((PSRWLOCK)this + 181);
    if ( *((CScrub **)this + 179) == (CScrub *)((char *)this + 1432) )
      break;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL));
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 181);
    v95 = 0;
LABEL_288:
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)&v95);
  }
  v62 = *((_DWORD *)this + 336);
  if ( v62 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        50,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v62);
    }
    for ( ii = 0; ii < *((_DWORD *)this + 336); ++ii )
      NtSetEvent(*((HANDLE *)this + 146), 0);
  }
  v64 = 0;
  for ( jj = *v58; jj != v58; jj = (_QWORD *)*jj )
    ++v64;
  ReleaseSRWLockExclusive((PSRWLOCK)this + 181);
  v95 = 0;
  if ( v64 < *((_DWORD *)this + 335) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        51,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v64);
    }
    goto LABEL_288;
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      52,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)this + 16LL),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL));
  }
  AcquireSRWLockExclusive(v23);
  if ( *((CScrub **)this + 182) != (CScrub *)((char *)this + 1456) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        53,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL));
    }
    ReleaseSRWLockExclusive(v23);
    *(_QWORD *)&v85.Length = 0;
    goto LABEL_282;
  }
  v66 = *((_DWORD *)this + 344);
  if ( v66 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v66);
    }
    for ( kk = 0; kk < *((_DWORD *)this + 344); ++kk )
      NtSetEvent(*((HANDLE *)this + 148), 0);
  }
  v68 = 0;
  for ( mm = *v59; mm != v59; mm = (_QWORD *)*mm )
    ++v68;
  ReleaseSRWLockExclusive(v23);
  *(_QWORD *)&v85.Length = 0;
  if ( v68 < *((_DWORD *)this + 343) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL),
        v68);
    }
LABEL_282:
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)&v85);
    goto LABEL_288;
  }
  v70 = v88;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      56,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)this + 16LL),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL));
  }
  CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)&v85);
  CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)&v95);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_DDZ(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      57,
      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
      *(_DWORD *)(**(_QWORD **)this + 16LL),
      *(_DWORD *)(**(_QWORD **)this + 36LL),
      *(_QWORD *)(*(_QWORD *)this + 64LL));
  }
  if ( v70 == -805306102 )
  {
LABEL_298:
    CAutoSetEvent::~CAutoSetEvent((CAutoSetEvent *)&v86);
    CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>::~CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>(&v90);
    started = -805306102;
    goto LABEL_299;
  }
  v51 = v94;
LABEL_302:
  if ( NtWaitForSingleObject(*((HANDLE *)this + 2), 0, &LiZero)
    && NtWaitForSingleObject(*((HANDLE *)this + 152), 0, &LiZero) )
  {
    *((_BYTE *)this + 1497) = 0;
    CScrubCheckpoint::UpdatePercentComplete((CScrub *)((char *)this + 1264), 0x64u);
    v72 = 0;
    Frequency.QuadPart = !QueryPerformanceFrequency(&Frequency);
    for ( nn = 0; nn < *((_DWORD *)this + 335); ++nn )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v75 = 35024LL * nn;
        v76 = *((_QWORD *)this + 177);
        WPP_SF_DDZddddll(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          59,
          v76,
          *(_DWORD *)(**(_QWORD **)this + 16LL),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          nn,
          *(_DWORD *)(v75 + v76 + 40),
          *(_DWORD *)(v75 + v76 + 36),
          *(_DWORD *)(v75 + v76 + 32),
          *(_DWORD *)(v75 + v76 + 48),
          1000LL * *(_QWORD *)(v75 + v76 + 56) / Frequency.QuadPart);
      }
      v77 = (struct _SCRUB_THREAD_CONTEXT *)(*((_QWORD *)this + 177) + 35024LL * nn);
      v72 += *((_DWORD *)v77 + 10);
      CScrub::_Checkpoint(this, v77, 0, 0, 1u);
    }
    for ( i1 = 0; i1 < *((_DWORD *)this + 343); ++i1 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v79 = 35024LL * i1;
        v80 = *((_QWORD *)this + 178);
        WPP_SF_DDZddddll(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          60,
          v80,
          *(_DWORD *)(**(_QWORD **)this + 16LL),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          i1,
          *(_DWORD *)(v79 + v80 + 40),
          *(_DWORD *)(v79 + v80 + 36),
          *(_DWORD *)(v79 + v80 + 32),
          *(_DWORD *)(v79 + v80 + 48),
          1000LL * *(_QWORD *)(v79 + v80 + 56) / Frequency.QuadPart);
      }
      v81 = (struct _SCRUB_THREAD_CONTEXT *)(*((_QWORD *)this + 178) + 35024LL * i1);
      v72 += *((_DWORD *)v81 + 10);
      CScrub::_Checkpoint(this, v81, 0, 0, 1u);
    }
    v82 = *((_QWORD *)this + 163);
    v83 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
    {
      if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_DDZdddl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          *((_DWORD *)this + 335),
          *(_QWORD *)this,
          *(_DWORD *)(**(_QWORD **)this + 16LL),
          *(_DWORD *)(**(_QWORD **)this + 36LL),
          *(_QWORD *)(*(_QWORD *)this + 64LL),
          v72,
          *((_DWORD *)this + 335),
          *((_DWORD *)this + 343),
          *(_DWORD *)(v82 + 16));
        v83 = (PVOID *)WPP_GLOBAL_Control;
      }
      if ( v83 != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
        {
          WPP_SF_DDZZ(
            (TRACEHANDLE)v83[2],
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            (__int64)&v103);
          v83 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v83 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
          {
            WPP_SF_DDZZ(
              (TRACEHANDLE)v83[2],
              *(_DWORD *)(**(_QWORD **)this + 36LL),
              *(_QWORD *)(*(_QWORD *)this + 64LL),
              (__int64)&v102);
            v83 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v83 != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
            {
              WPP_SF_DDZi(
                (unsigned int)v83[2],
                64,
                (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                *(_DWORD *)(**(_QWORD **)this + 16LL),
                *(_DWORD *)(**(_QWORD **)this + 36LL),
                *(_QWORD *)(*(_QWORD *)this + 64LL),
                *(_QWORD *)(v82 + 16));
              v83 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v83 != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
              {
                WPP_SF_DDZi(
                  (unsigned int)v83[2],
                  65,
                  (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                  *(_DWORD *)(**(_QWORD **)this + 16LL),
                  *(_DWORD *)(**(_QWORD **)this + 36LL),
                  *(_QWORD *)(*(_QWORD *)this + 64LL),
                  *(_QWORD *)(v82 + 24));
                v83 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v83 != &WPP_GLOBAL_Control )
              {
                if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                {
                  WPP_SF_DDZi(
                    (unsigned int)v83[2],
                    66,
                    (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                    *(_DWORD *)(**(_QWORD **)this + 16LL),
                    *(_DWORD *)(**(_QWORD **)this + 36LL),
                    *(_QWORD *)(*(_QWORD *)this + 64LL),
                    *(_QWORD *)(v82 + 32));
                  v83 = (PVOID *)WPP_GLOBAL_Control;
                }
                if ( v83 != &WPP_GLOBAL_Control )
                {
                  if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                  {
                    WPP_SF_DDZI(
                      (unsigned int)v83[2],
                      67,
                      v73,
                      *(_DWORD *)(**(_QWORD **)this + 16LL),
                      *(_DWORD *)(**(_QWORD **)this + 36LL),
                      *(_QWORD *)(*(_QWORD *)this + 64LL),
                      *(_QWORD *)(v82 + 40));
                    v83 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( v83 != &WPP_GLOBAL_Control )
                  {
                    if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                    {
                      WPP_SF_DDZI(
                        (unsigned int)v83[2],
                        68,
                        v73,
                        *(_DWORD *)(**(_QWORD **)this + 16LL),
                        *(_DWORD *)(**(_QWORD **)this + 36LL),
                        *(_QWORD *)(*(_QWORD *)this + 64LL),
                        *(_QWORD *)(v82 + 48));
                      v83 = (PVOID *)WPP_GLOBAL_Control;
                    }
                    if ( v83 != &WPP_GLOBAL_Control )
                    {
                      if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                      {
                        WPP_SF_DDZI(
                          (unsigned int)v83[2],
                          69,
                          v73,
                          *(_DWORD *)(**(_QWORD **)this + 16LL),
                          *(_DWORD *)(**(_QWORD **)this + 36LL),
                          *(_QWORD *)(*(_QWORD *)this + 64LL),
                          *(_QWORD *)(v82 + 56));
                        v83 = (PVOID *)WPP_GLOBAL_Control;
                      }
                      if ( v83 != &WPP_GLOBAL_Control )
                      {
                        if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                        {
                          WPP_SF_DDZI(
                            (unsigned int)v83[2],
                            70,
                            v73,
                            *(_DWORD *)(**(_QWORD **)this + 16LL),
                            *(_DWORD *)(**(_QWORD **)this + 36LL),
                            *(_QWORD *)(*(_QWORD *)this + 64LL),
                            *(_QWORD *)(v82 + 64));
                          v83 = (PVOID *)WPP_GLOBAL_Control;
                        }
                        if ( v83 != &WPP_GLOBAL_Control )
                        {
                          if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                          {
                            WPP_SF_DDZI(
                              (unsigned int)v83[2],
                              71,
                              v73,
                              *(_DWORD *)(**(_QWORD **)this + 16LL),
                              *(_DWORD *)(**(_QWORD **)this + 36LL),
                              *(_QWORD *)(*(_QWORD *)this + 64LL),
                              *(_QWORD *)(v82 + 72));
                            v83 = (PVOID *)WPP_GLOBAL_Control;
                          }
                          if ( v83 != &WPP_GLOBAL_Control )
                          {
                            if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                            {
                              WPP_SF_DDZi(
                                (unsigned int)v83[2],
                                72,
                                (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                                *(_DWORD *)(**(_QWORD **)this + 16LL),
                                *(_DWORD *)(**(_QWORD **)this + 36LL),
                                *(_QWORD *)(*(_QWORD *)this + 64LL),
                                *(_QWORD *)(v82 + 80));
                              v83 = (PVOID *)WPP_GLOBAL_Control;
                            }
                            if ( v83 != &WPP_GLOBAL_Control )
                            {
                              if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                              {
                                WPP_SF_DDZi(
                                  (unsigned int)v83[2],
                                  73,
                                  (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                                  *(_DWORD *)(**(_QWORD **)this + 16LL),
                                  *(_DWORD *)(**(_QWORD **)this + 36LL),
                                  *(_QWORD *)(*(_QWORD *)this + 64LL),
                                  *(_QWORD *)(v82 + 88));
                                v83 = (PVOID *)WPP_GLOBAL_Control;
                              }
                              if ( v83 != &WPP_GLOBAL_Control )
                              {
                                if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                                {
                                  WPP_SF_DDZi(
                                    (unsigned int)v83[2],
                                    74,
                                    (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                                    *(_DWORD *)(**(_QWORD **)this + 16LL),
                                    *(_DWORD *)(**(_QWORD **)this + 36LL),
                                    *(_QWORD *)(*(_QWORD *)this + 64LL),
                                    *(_QWORD *)(v82 + 96));
                                  v83 = (PVOID *)WPP_GLOBAL_Control;
                                }
                                if ( v83 != &WPP_GLOBAL_Control )
                                {
                                  if ( (*((_BYTE *)v83 + 28) & 1) != 0 && *((_BYTE *)v83 + 25) >= 4u )
                                  {
                                    WPP_SF_DDZi(
                                      (unsigned int)v83[2],
                                      75,
                                      (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
                                      *(_DWORD *)(**(_QWORD **)this + 16LL),
                                      *(_DWORD *)(**(_QWORD **)this + 36LL),
                                      *(_QWORD *)(*(_QWORD *)this + 64LL),
                                      *(_QWORD *)(v82 + 104));
                                    v83 = (PVOID *)WPP_GLOBAL_Control;
                                  }
                                  if ( v83 != &WPP_GLOBAL_Control
                                    && (*((_BYTE *)v83 + 28) & 1) != 0
                                    && *((_BYTE *)v83 + 25) >= 4u )
                                  {
                                    WPP_SF_DDZI(
                                      (unsigned int)v83[2],
                                      76,
                                      v73,
                                      *(_DWORD *)(**(_QWORD **)this + 16LL),
                                      *(_DWORD *)(**(_QWORD **)this + 36LL),
                                      *(_QWORD *)(*(_QWORD *)this + 64LL),
                                      *((_QWORD *)this + 186));
                                  }
                                }
                              }
                            }
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
    SqmScrubResult(
      *(const struct _SCRUB_VOLUME_IDENTIFIER **)this,
      0,
      *v51,
      *(const struct _GUID **)(*(_QWORD *)this + 24LL),
      v104,
      *(_QWORD *)(v82 + 16),
      *(_QWORD *)(v82 + 24),
      *(_QWORD *)(v82 + 32),
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)this + 16LL) + 16LL),
      *(_QWORD *)(v82 + 40),
      *(_QWORD *)(v82 + 48));
    if ( v89 )
    {
      if ( v105 )
      {
        ParityExtentRecordCount = CScrubDatabase::GetParityExtentRecordCount((CScrub *)((char *)this + 80), v105);
        if ( ParityExtentRecordCount < 0
          && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_DDZd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            77,
            (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
            *(_DWORD *)(**(_QWORD **)this + 16LL),
            *(_DWORD *)(**(_QWORD **)this + 36LL),
            *(_QWORD *)(*(_QWORD *)this + 64LL),
            ParityExtentRecordCount);
        }
      }
      CScrubDatabase::CloseJetDatabase((CScrub *)((char *)this + 80));
      CScrubJetInstance::StopJetInstance((CScrub *)((char *)this + 64));
    }
    v88 = 0;
    CAutoSetEvent::~CAutoSetEvent((CAutoSetEvent *)&v86);
    CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>::~CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>(&v90);
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)&v101);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)v97);
    CAutoClearVolumeCheckpoint::~CAutoClearVolumeCheckpoint((CAutoClearVolumeCheckpoint *)&v93);
    CHResultImp::~CHResultImp((CHResultImp *)&v87);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDZ(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        58,
        (unsigned int)&WPP_efaeeb0993ed33c3273434515202503b_Traceguids,
        *(_DWORD *)(**(_QWORD **)this + 16LL),
        *(_DWORD *)(**(_QWORD **)this + 36LL),
        *(_QWORD *)(*(_QWORD *)this + 64LL));
    }
    v93 = 0;
    CAutoSetEvent::~CAutoSetEvent((CAutoSetEvent *)&v86);
    CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>::~CHandleT<HCMNOTIFICATION__ *,CCmNotificationHandleTrait>(&v90);
    CHandleT<void *,NtHandleTrait>::~CHandleT<void *,NtHandleTrait>(&FileHandle);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)&v101);
    CAutoSrwExclusiveLock::~CAutoSrwExclusiveLock((CAutoSrwExclusiveLock *)v97);
    CAutoClearVolumeCheckpoint::~CAutoClearVolumeCheckpoint((CAutoClearVolumeCheckpoint *)&v93);
    CHResultImp::~CHResultImp((CHResultImp *)&v87);
    return 3489661194LL;
  }
}

```

## disassembly

```asm
0x180024b24  mov     [rsp-8+arg_10], rbx
0x180024b29  push    rbp
0x180024b2a  push    rsi
0x180024b2b  push    rdi
0x180024b2c  push    r12
0x180024b2e  push    r13
0x180024b30  push    r14
0x180024b32  push    r15
0x180024b34  lea     rbp, [rsp-210h]
0x180024b3c  sub     rsp, 310h
0x180024b43  mov     rax, cs:__security_cookie
0x180024b4a  xor     rax, rsp
0x180024b4d  mov     [rbp+240h+var_40], rax
0x180024b54  mov     [rbp+240h+var_238], r9
0x180024b58  mov     r14d, r8d
0x180024b5b  mov     [rbp+240h+var_2B8], r8d
0x180024b5f  mov     rdi, rdx
0x180024b62  mov     r15, rcx
0x180024b65  mov     r12, [rbp+240h+arg_20]
0x180024b6c  mov     [rbp+240h+var_230], r12
0x180024b70  mov     r9d, cs:_tls_index
0x180024b77  mov     rax, gs:58h
0x180024b80  mov     rdx, [rax+r9*8]
0x180024b84  mov     eax, 10h
0x180024b89  lea     r11, aCscrubScrubvol; "CScrub::ScrubVolume"
0x180024b90  mov     [rax+rdx], r11
0x180024b94  mov     [rsp+340h+var_2C8], r11
0x180024b99  xor     r10d, r10d
0x180024b9c  mov     [rbp+240h+var_2C0], r10d
0x180024ba0  mov     eax, 8
0x180024ba5  lea     r8d, [r10+1]
0x180024ba9  add     [rax+rdx], r8w
0x180024bae  movzx   edx, word ptr [rax+rdx]
0x180024bb2  movzx   ecx, cs:?GlobalIndentString@@3U_STRING@@A; _STRING GlobalIndentString
0x180024bb9  movzx   eax, cx
0x180024bbc  cmp     dx, cx
0x180024bbf  cmovb   ax, dx
0x180024bc3  mov     word ptr [rbp+240h+var_280], ax
0x180024bc7  cmovb   cx, dx
0x180024bcb  mov     word ptr [rbp+240h+var_280+2], cx
0x180024bcf  xor     eax, eax
0x180024bd1  mov     dword ptr [rbp+240h+var_280+4], eax
0x180024bd4  mov     rax, cs:off_180047060; "                                       "...
0x180024bdb  mov     [rbp+240h+var_278], rax
0x180024bdf  lea     r9, WPP_GLOBAL_Control
0x180024be6  mov     rcx, cs:WPP_GLOBAL_Control
0x180024bed  cmp     rcx, r9
0x180024bf0  jz      short loc_180024C24
0x180024bf2  test    [rcx+1Ch], r8b
0x180024bf6  jz      short loc_180024C24
0x180024bf8  cmp     byte ptr [rcx+19h], 5
0x180024bfc  jb      short loc_180024C24
0x180024bfe  lea     edx, [r10+0Dh]
0x180024c02  mov     qword ptr [rsp+340h+ShareAccess], r11; __int64
0x180024c07  lea     r9, [rbp+240h+var_280]
0x180024c0b  mov     rcx, [rcx+10h]; LoggerHandle
0x180024c0f  call    WPP_SF_aZs
0x180024c14  mov     r8d, 1
0x180024c1a  lea     r9, WPP_GLOBAL_Control
0x180024c21  xor     r10d, r10d
0x180024c24  mov     rbx, [rdi+20h]
0x180024c28  mov     rsi, [rdi+30h]
0x180024c2c  mov     r13, [rdi+38h]
0x180024c30  mov     [rbp+240h+var_290], r13
0x180024c34  test    r12, r12
0x180024c37  jz      short loc_180024C3D
0x180024c39  mov     [r12], r10d
0x180024c3d  mov     [r15], rdi
0x180024c40  mov     [r15+5D9h], r8b
0x180024c47  mov     r12d, r14d
0x180024c4a  and     r12d, 10h
0x180024c4e  mov     rcx, rbx
0x180024c51  cmovnz  rcx, r10
0x180024c55  mov     [rbp+240h+var_2A0], rcx
0x180024c59  mov     [r15+4ECh], r14d
0x180024c60  mov     [r15+5E8h], r10d
0x180024c67  mov     edx, r10d
0x180024c6a  mov     eax, [r15+53Ch]
0x180024c71  test    eax, eax
0x180024c73  jz      short loc_180024CA7
0x180024c75  mov     eax, edx
0x180024c77  imul    rcx, rax, 88D0h
0x180024c7e  mov     rax, [r15+588h]
0x180024c85  mov     [rcx+rax+18h], r10b
0x180024c8a  mov     rax, [r15+588h]
0x180024c91  mov     [rcx+rax+86B8h], r10
0x180024c99  add     edx, r8d
0x180024c9c  mov     eax, [r15+53Ch]
0x180024ca3  cmp     edx, eax
0x180024ca5  jb      short loc_180024C75
0x180024ca7  mov     dil, 4
0x180024caa  mov     rcx, cs:WPP_GLOBAL_Control
0x180024cb1  cmp     rcx, r9
0x180024cb4  jz      loc_180024E05
0x180024cba  test    [rcx+1Ch], r8b
0x180024cbe  jz      short loc_180024D0F
0x180024cc0  cmp     [rcx+19h], dil
0x180024cc4  jb      short loc_180024D0F
0x180024cc6  mov     rax, [r15]
0x180024cc9  mov     r9, [rax]
0x180024ccc  mov     edx, 0Ah
0x180024cd1  mov     qword ptr [rsp+340h+var_310], rbx; __int64
0x180024cd6  mov     rax, [rax+40h]
0x180024cda  mov     qword ptr [rsp+340h+OpenOptions], rax; __int64
0x180024cdf  mov     eax, [r9+24h]
0x180024ce3  mov     [rsp+340h+ShareAccess], eax; char
0x180024ce7  mov     r9d, [r9+10h]
0x180024ceb  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180024cf2  mov     rcx, [rcx+10h]; LoggerHandle
0x180024cf6  call    WPP_SF_DDZZ
0x180024cfb  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d02  mov     r8d, 1
0x180024d08  lea     r9, WPP_GLOBAL_Control
0x180024d0f  cmp     rcx, r9
0x180024d12  jz      loc_180024E05
0x180024d18  test    [rcx+1Ch], r8b
0x180024d1c  jz      short loc_180024D6D
0x180024d1e  cmp     [rcx+19h], dil
0x180024d22  jb      short loc_180024D6D
0x180024d24  mov     rax, [r15]
0x180024d27  mov     r9, [rax]
0x180024d2a  mov     edx, 0Bh
0x180024d2f  mov     qword ptr [rsp+340h+var_310], rsi; __int64
0x180024d34  mov     rax, [rax+40h]
0x180024d38  mov     qword ptr [rsp+340h+OpenOptions], rax; __int64
0x180024d3d  mov     eax, [r9+24h]
0x180024d41  mov     [rsp+340h+ShareAccess], eax; char
0x180024d45  mov     r9d, [r9+10h]
0x180024d49  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180024d50  mov     rcx, [rcx+10h]; LoggerHandle
0x180024d54  call    WPP_SF_DDZZ
0x180024d59  mov     rcx, cs:WPP_GLOBAL_Control
0x180024d60  mov     r8d, 1
0x180024d66  lea     r9, WPP_GLOBAL_Control
0x180024d6d  cmp     rcx, r9
0x180024d70  jz      loc_180024E05
0x180024d76  test    [rcx+1Ch], r8b
0x180024d7a  jz      short loc_180024DCB
0x180024d7c  cmp     [rcx+19h], dil
0x180024d80  jb      short loc_180024DCB
0x180024d82  mov     rax, [r15]
0x180024d85  mov     r9, [rax]
0x180024d88  mov     edx, 0Ch
0x180024d8d  mov     qword ptr [rsp+340h+var_310], r13; __int64
0x180024d92  mov     rax, [rax+40h]
0x180024d96  mov     qword ptr [rsp+340h+OpenOptions], rax; __int64
0x180024d9b  mov     eax, [r9+24h]
0x180024d9f  mov     [rsp+340h+ShareAccess], eax; char
0x180024da3  mov     r9d, [r9+10h]
0x180024da7  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180024dae  mov     rcx, [rcx+10h]; LoggerHandle
0x180024db2  call    WPP_SF_DDZZ
0x180024db7  mov     rcx, cs:WPP_GLOBAL_Control
0x180024dbe  mov     r8d, 1
0x180024dc4  lea     r9, WPP_GLOBAL_Control
0x180024dcb  cmp     rcx, r9
0x180024dce  jz      short loc_180024E05
0x180024dd0  test    [rcx+1Ch], r8b
0x180024dd4  jz      short loc_180024E05
0x180024dd6  cmp     [rcx+19h], dil
0x180024dda  jb      short loc_180024E05
0x180024ddc  mov     rax, [r15]
0x180024ddf  mov     r9, [rax]
0x180024de2  mov     dword ptr [rsp+340h+var_310], r14d
0x180024de7  mov     rax, [rax+40h]
0x180024deb  mov     qword ptr [rsp+340h+OpenOptions], rax
0x180024df0  mov     eax, [r9+24h]
0x180024df4  mov     [rsp+340h+ShareAccess], eax
0x180024df8  mov     r9d, [r9+10h]
0x180024dfc  mov     rcx, [rcx+10h]
0x180024e00  call    WPP_SF_DDZL
0x180024e05  mov     rcx, [r15+4C0h]; EventHandle
0x180024e0c  call    cs:__imp_NtClearEvent
0x180024e12  lea     rdi, [r15+5A8h]
0x180024e19  mov     rcx, rdi; SRWLock
0x180024e1c  call    cs:__imp_AcquireSRWLockExclusive
0x180024e22  nop
0x180024e23  lea     rdx, [r15+598h]; unsigned int
0x180024e2a  mov     rcx, [rdx]; this
0x180024e2d  cmp     rcx, rdx
0x180024e30  jz      short loc_180024E56
0x180024e32  cmp     [rcx+8], rdx
0x180024e36  jnz     short loc_180024E4F
0x180024e38  mov     rax, [rcx]
0x180024e3b  cmp     [rax+8], rcx
0x180024e3f  jnz     short loc_180024E4F
0x180024e41  mov     [rdx], rax
0x180024e44  mov     [rax+8], rdx
0x180024e48  call    ??_G_SCRUB_DIRECTORY_ENTRY@@QEAAPEAXI@Z; _SCRUB_DIRECTORY_ENTRY::`scalar deleting destructor'(uint)
0x180024e4d  jmp     short loc_180024E23
0x180024e4f  mov     ecx, 3
0x180024e54  int     29h; Win8: RtlFailFast(ecx)
0x180024e56  mov     rcx, rdi; SRWLock
0x180024e59  call    cs:__imp_ReleaseSRWLockExclusive
0x180024e5f  xor     r13d, r13d
0x180024e62  mov     [rbp+240h+var_280], r13
0x180024e66  lea     rsi, [r15+5C0h]
0x180024e6d  mov     rcx, rsi; SRWLock
0x180024e70  call    cs:__imp_AcquireSRWLockExclusive
0x180024e76  nop
0x180024e77  mov     rcx, r15; this
0x180024e7a  call    ?_DrainFileQueue@CScrub@@AEAAXXZ; CScrub::_DrainFileQueue(void)
0x180024e7f  mov     rcx, rsi; SRWLock
0x180024e82  call    cs:__imp_ReleaseSRWLockExclusive
0x180024e88  mov     [rbp+240h+var_260], r13
0x180024e8c  mov     qword ptr [rbp+240h+ObjectAttributes.Length], 30h ; '0'
0x180024e94  mov     qword ptr [rbp+240h+ObjectAttributes.Attributes], 40h ; '@'
0x180024e9c  mov     [rbp+240h+ObjectAttributes.RootDirectory], r13
0x180024ea0  mov     [rbp+240h+ObjectAttributes.ObjectName], rbx
0x180024ea4  xorps   xmm0, xmm0
0x180024ea7  movdqu  xmmword ptr [rbp+240h+ObjectAttributes.SecurityDescriptor], xmm0
0x180024eac  movups  xmmword ptr [rbp+240h+IoStatusBlock], xmm0
0x180024eb0  mov     [rbp+240h+FileHandle], r13
0x180024eb4  mov     [rbp+240h+var_268], r13d
0x180024eb8  mov     [rbp+240h+var_264], r13b
0x180024ebc  mov     [rsp+340h+OpenOptions], r13d; OpenOptions
0x180024ec1  mov     [rsp+340h+ShareAccess], 7; ShareAccess
0x180024ec9  lea     r9, [rbp+240h+IoStatusBlock]; IoStatusBlock
0x180024ecd  lea     r8, [rbp+240h+ObjectAttributes]; ObjectAttributes
0x180024ed1  mov     edx, 80h; DesiredAccess
0x180024ed6  lea     rcx, [rbp+240h+FileHandle]; FileHandle
0x180024eda  call    cs:__imp_NtOpenFile
0x180024ee0  mov     r14d, eax
0x180024ee3  test    eax, eax
0x180024ee5  jns     short loc_180024F59
0x180024ee7  bts     r14d, 1Ch
0x180024eec  mov     [rbp+240h+var_2C0], r14d
0x180024ef0  mov     rcx, cs:WPP_GLOBAL_Control
0x180024ef7  lea     rax, WPP_GLOBAL_Control
0x180024efe  cmp     rcx, rax
0x180024f01  jz      loc_180026544
0x180024f07  test    byte ptr [rcx+1Ch], 1
0x180024f0b  jz      loc_180026544
0x180024f11  cmp     byte ptr [rcx+19h], 2
0x180024f15  jb      loc_180026544
0x180024f1b  mov     rax, [r15]
0x180024f1e  mov     r9, [rax]
0x180024f21  lea     edx, [r13+0Eh]
0x180024f25  mov     dword ptr [rsp+340h+var_308], r14d; char
0x180024f2a  mov     qword ptr [rsp+340h+var_310], rbx; __int64
0x180024f2f  mov     rax, [rax+40h]
0x180024f33  mov     qword ptr [rsp+340h+OpenOptions], rax; __int64
0x180024f38  mov     eax, [r9+24h]
0x180024f3c  mov     [rsp+340h+ShareAccess], eax; char
0x180024f40  mov     r9d, [r9+10h]
0x180024f44  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x180024f4b  mov     rcx, [rcx+10h]; LoggerHandle
0x180024f4f  call    WPP_SF_DDZZd
0x180024f54  jmp     loc_180026544
0x180024f59  mov     r14, [rbp+240h+FileHandle]
0x180024f5d  mov     [r15+18h], r14
0x180024f61  mov     r13d, 1A0h
0x180024f67  mov     r8d, r13d; Size
0x180024f6a  xor     edx, edx; Val
0x180024f6c  lea     rcx, [rbp+240h+var_1E0]; void *
0x180024f70  call    memset_0
0x180024f75  mov     [rbp+240h+var_1E0], r13d
0x180024f79  mov     r13d, 1
0x180024f7f  mov     [rbp+240h+var_1D8], r13d
0x180024f83  mov     [rbp+240h+var_1D0], r14
0x180024f87  xor     r14d, r14d
0x180024f8a  mov     [rbp+240h+var_2B0], r14
0x180024f8e  mov     [rbp+240h+var_2A8], r14d
0x180024f92  mov     [rbp+240h+var_2A4], r14b
0x180024f96  lea     r9, [rbp+240h+var_2B0]
0x180024f9a  lea     r8, ?_VolumeNotifyCallback@CScrub@@CAKPEAUHCMNOTIFICATION__@@PEAXW4_CM_NOTIFY_ACTION@@PEAU_CM_NOTIFY_EVENT_DATA@@K@Z; CScrub::_VolumeNotifyCallback(HCMNOTIFICATION__ *,void *,_CM_NOTIFY_ACTION,_CM_NOTIFY_EVENT_DATA *,ulong)
0x180024fa1  mov     rdx, r15
0x180024fa4  lea     rcx, [rbp+240h+var_1E0]
0x180024fa8  call    cs:__imp_CM_Register_Notification
0x180024fae  test    eax, eax
0x180024fb0  jz      short loc_18002502D
0x180024fb2  lea     edx, [r13+0Ch]; DefaultErr
0x180024fb6  mov     ecx, eax; CmReturnCode
0x180024fb8  call    cs:__imp_CM_MapCrToWin32Err
0x180024fbe  mov     ecx, eax
0x180024fc0  test    eax, eax
0x180024fc2  jle     short loc_180024FCD
0x180024fc4  movzx   ecx, ax
0x180024fc7  or      ecx, 80070000h
0x180024fcd  mov     [rbp+240h+var_2C0], ecx
0x180024fd0  mov     r10, cs:WPP_GLOBAL_Control
0x180024fd7  lea     rax, WPP_GLOBAL_Control
0x180024fde  cmp     r10, rax
0x180024fe1  jz      short loc_180025024
0x180024fe3  test    [r10+1Ch], r13b
0x180024fe7  jz      short loc_180025024
0x180024fe9  cmp     byte ptr [r10+19h], 2
0x180024fee  jb      short loc_180025024
0x180024ff0  mov     rax, [r15]
0x180024ff3  mov     r9, [rax]
0x180024ff6  mov     edx, 0Fh
0x180024ffb  mov     dword ptr [rsp+340h+var_310], ecx
0x180024fff  mov     rax, [rax+40h]
0x180025003  mov     qword ptr [rsp+340h+OpenOptions], rax
0x180025008  mov     eax, [r9+24h]
0x18002500c  mov     [rsp+340h+ShareAccess], eax
0x180025010  mov     r9d, [r9+10h]
0x180025014  lea     r8, WPP_efaeeb0993ed33c3273434515202503b_Traceguids
0x18002501b  mov     rcx, [r10+10h]
0x18002501f  call    WPP_SF_DDZd
  ... truncated ...
```
