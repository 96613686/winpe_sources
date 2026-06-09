# CldiPortProcessServiceCommands

- ea: `0x14003baf0`
- end: `0x14003d021`
- name: `CldiPortProcessServiceCommands`
- size: `5425`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x140039300`

## callees

- `0x140003c50`
- `0x14000c12c`
- `0x14000d908`
- `0x14000d95c`
- `0x14000e888`
- `0x140011c0c`
- `0x140012c54`
- `0x1400131d4`
- `0x1400168cc`
- `0x14001e280`
- `0x140035184`
- `0x140035584`
- `0x140037a1c`
- `0x140038cc0`
- `0x14003baf0`
- `0x14003d9b0`
- `0x140050280`
- `0x1400560c8`
- `0x1400561cc`
- `0x14005f550`
- `0x14007a5bc`
- `0x14007e61c`
- `0x14007f2ec`
- `0x1400827b4`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x14003c230`
- `ntoskrnl!RtlComputeCrc32` at `0x14003c230`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003beb1`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x14003beb1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003cd4e`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14003cd4e`
- `ntoskrnl!IoFileObjectType` at `0x14003be91`
- `ntoskrnl!ObfDereferenceObject` at `0x14003cff7`
- `ntoskrnl!ObfDereferenceObject` at `0x14003cff7`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14003cf01`
- `ntoskrnl!RtlDeleteElementGenericTableAvl` at `0x14003cf01`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cfa3`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003cfa3`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003ccde`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cd75`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cd8c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cf27`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003ccde`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cd75`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cd8c`
- `ntoskrnl!IoGetCurrentProcess` at `0x14003cf27`
- `FLTMGR!FltAttachVolumeAtAltitude` at `0x14003bf95`
- `FLTMGR!FltAttachVolumeAtAltitude` at `0x14003bf95`
- `FLTMGR!FltReleasePushLockEx` at `0x14003bd4a`
- `FLTMGR!FltReleasePushLockEx` at `0x14003cc76`
- `FLTMGR!FltReleasePushLockEx` at `0x14003cf12`
- `FLTMGR!FltReleasePushLockEx` at `0x14003cf4d`
- `FLTMGR!FltReleasePushLockEx` at `0x14003bd4a`
- `FLTMGR!FltReleasePushLockEx` at `0x14003cc76`
- `FLTMGR!FltReleasePushLockEx` at `0x14003cf12`
- `FLTMGR!FltReleasePushLockEx` at `0x14003cf4d`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14003bd2a`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x14003bd2a`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003cba1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003cc50`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003ce75`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003ceea`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003cba1`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003cc50`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003ce75`
- `FLTMGR!FltAcquirePushLockExclusiveEx` at `0x14003ceea`
- `FLTMGR!FltGetInstanceContext` at `0x14003c02f`
- `FLTMGR!FltGetInstanceContext` at `0x14003c02f`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14003bfc5`
- `FLTMGR!FltGetVolumeInstanceFromName` at `0x14003bfc5`
- `FLTMGR!FltObjectDereference` at `0x14003cfcd`
- `FLTMGR!FltObjectDereference` at `0x14003cfe2`
- `FLTMGR!FltObjectDereference` at `0x14003cfcd`
- `FLTMGR!FltObjectDereference` at `0x14003cfe2`
- `FLTMGR!FltReleaseContext` at `0x14003cfb8`
- `FLTMGR!FltReleaseContext` at `0x14003cfb8`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14003bf11`
- `FLTMGR!FltGetVolumeFromFileObject` at `0x14003bf11`

## string_xrefs

- `0x14003cd61`: `ConnectingPortContext's SyncProvider is already set`

## pseudocode

```c
__int64 __fastcall CldiPortProcessServiceCommands(__int64 a1, __int16 a2, __int64 a3, unsigned int a4)
{
  void *v7; // r12
  __int64 v8; // rax
  unsigned int v9; // r8d
  unsigned __int16 v10; // r9
  unsigned __int64 v11; // rdx
  unsigned int v12; // eax
  __int64 v13; // rdi
  PDEVICE_OBJECT v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  __int64 v17; // rax
  unsigned int v18; // r8d
  unsigned __int16 v19; // r9
  unsigned __int64 v20; // rdx
  unsigned int v21; // eax
  __int64 v22; // rsi
  __int64 v23; // rax
  unsigned int v24; // r8d
  unsigned __int16 v25; // r9
  unsigned __int64 v26; // rdx
  unsigned int v27; // ecx
  PDEVICE_OBJECT v28; // rcx
  __int64 v29; // rdx
  void *v30; // r9
  __int64 v31; // rdx
  unsigned int v32; // r12d
  bool v33; // cf
  __int64 v34; // r15
  unsigned int v35; // r13d
  __int64 v36; // rax
  unsigned int v37; // r8d
  unsigned __int16 v38; // r9
  unsigned __int64 v39; // rdx
  unsigned int v40; // ecx
  unsigned __int64 v41; // rdx
  __int64 v42; // r9
  unsigned __int64 v43; // rbx
  unsigned int i; // r10d
  unsigned int v45; // eax
  unsigned __int64 v46; // rcx
  unsigned int v47; // eax
  unsigned int v48; // eax
  __int64 v49; // rcx
  unsigned int v50; // r8d
  unsigned __int16 v51; // r9
  unsigned __int64 v52; // rdx
  unsigned int v53; // ecx
  __int64 v54; // rcx
  unsigned int v55; // r8d
  unsigned __int16 v56; // r9
  unsigned __int64 v57; // rdx
  unsigned int v58; // eax
  int v59; // r9d
  int v60; // r11d
  __int64 v61; // rax
  unsigned int v62; // r8d
  unsigned __int16 v63; // r10
  unsigned __int64 v64; // rdx
  unsigned int v65; // ecx
  __int64 v66; // rax
  unsigned int v67; // r8d
  unsigned __int16 v68; // r9
  unsigned __int64 v69; // rdx
  unsigned int v70; // eax
  __int64 v71; // rdx
  unsigned int v72; // r15d
  __int64 v73; // rax
  unsigned int v74; // r8d
  unsigned __int16 v75; // r9
  unsigned __int64 v76; // rdx
  unsigned int v77; // eax
  __int64 v78; // rax
  unsigned int v79; // r8d
  unsigned __int16 v80; // r9
  unsigned __int64 v81; // rdx
  unsigned int v82; // eax
  __int64 v83; // rax
  unsigned int v84; // r8d
  unsigned __int16 v85; // r9
  unsigned __int64 v86; // rdx
  unsigned int v87; // eax
  __int64 v88; // rcx
  unsigned int v89; // r8d
  unsigned __int16 v90; // r9
  unsigned __int64 v91; // rdx
  unsigned int v92; // eax
  __int64 v93; // rsi
  PDEVICE_OBJECT v94; // rcx
  __int64 v95; // rdx
  void *v96; // r9
  struct _KPROCESS **v97; // rsi
  struct _KPROCESS *v98; // rbx
  int v99; // edx
  int v100; // r8d
  unsigned int CurrentProcessId; // eax
  __int64 v102; // rcx
  struct _KPROCESS *CurrentProcess; // rax
  PEPROCESS v104; // rax
  int v105; // eax
  __int64 v106; // rcx
  unsigned int v107; // r8d
  unsigned __int16 v108; // r9
  unsigned __int64 v109; // rdx
  unsigned int v110; // eax
  __int64 v111; // rbx
  PEPROCESS v113; // rax
  PVOID *Object; // [rsp+28h] [rbp-89h]
  __int64 Buffer; // [rsp+58h] [rbp-59h] BYREF
  PVOID v117; // [rsp+60h] [rbp-51h] BYREF
  PFLT_CONTEXT Context; // [rsp+68h] [rbp-49h] BYREF
  int v119; // [rsp+70h] [rbp-41h]
  int v120; // [rsp+74h] [rbp-3Dh]
  void *v121; // [rsp+78h] [rbp-39h]
  PFLT_VOLUME RetVolume; // [rsp+80h] [rbp-31h] BYREF
  __int64 v123; // [rsp+88h] [rbp-29h] BYREF
  __int64 v124; // [rsp+90h] [rbp-21h]
  PFLT_INSTANCE RetInstance; // [rsp+98h] [rbp-19h] BYREF
  __int64 v126; // [rsp+A0h] [rbp-11h]
  UNICODE_STRING InstanceName; // [rsp+A8h] [rbp-9h] BYREF
  UNICODE_STRING Altitude; // [rsp+B8h] [rbp+7h] BYREF
  PVOID P[2]; // [rsp+C8h] [rbp+17h] BYREF
  int v131; // [rsp+120h] [rbp+6Fh]

  *(_QWORD *)&InstanceName.Length = 917516;
  v121 = 0;
  InstanceName.Buffer = L"CldFlt";
  Altitude.Buffer = L"180451";
  v117 = 0;
  RetVolume = 0;
  RetInstance = 0;
  Context = 0;
  v124 = 0;
  v7 = 0;
  Buffer = 0;
  *(_QWORD *)&Altitude.Length = 917516;
  *(_OWORD *)P = 0;
  if ( a2 != 6 )
  {
    if ( a4 >= 0x18
      && (v23 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v23 > 2u)
      && (v24 = *(_DWORD *)(a3 + 8), v24 >= 0x28)
      && (v25 = *(_WORD *)(a3 + 32), v25 < 0x12u)
      && ((v26 = *(unsigned int *)(a3 + 36), !(_DWORD)v26) || v26 >= 8 * v23 + 16 && (unsigned int)v26 <= v24)
      && (v27 = *(unsigned __int16 *)(a3 + 34), v27 <= v24)
      && v27 + (unsigned int)v26 >= (unsigned int)v26
      && v27 + (unsigned int)v26 <= v24
      && v25 == 11
      && v27 == 8 )
    {
      v7 = *(void **)(v26 + a3);
      LODWORD(v13) = 0;
      v121 = v7;
    }
    else
    {
      LODWORD(v13) = -1073741275;
    }
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( (int)v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 14;
        goto LABEL_21;
      }
      goto LABEL_389;
    }
    LODWORD(v13) = ObReferenceObjectByHandle(v7, 0, (POBJECT_TYPE)IoFileObjectType, 1, &v117, 0);
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( (int)v13 < 0 )
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 15;
        goto LABEL_21;
      }
      goto LABEL_389;
    }
    LODWORD(v13) = FltGetVolumeFromFileObject(Globals, (PFILE_OBJECT)v117, &RetVolume);
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( (int)v13 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_389;
      }
      v29 = 16;
LABEL_79:
      v30 = v7;
LABEL_80:
      LODWORD(Object) = v13;
      WPP_SF_qd(v28->AttachedDevice, v29, WPP_452df49304b034ad87c0baec305776b3_Traceguids, v30, Object);
      goto LABEL_389;
    }
    v13 = (unsigned int)FltAttachVolumeAtAltitude(Globals, RetVolume, &Altitude, &InstanceName, &RetInstance);
    HsmDbgBreakOnStatus(v13);
    if ( (_DWORD)v13 == -1071906798 )
    {
      LODWORD(v13) = FltGetVolumeInstanceFromName(Globals, RetVolume, &InstanceName, &RetInstance);
      HsmDbgBreakOnStatus((unsigned int)v13);
    }
    else
    {
      TlmWriteFilterAttachEvent((unsigned int)v13, &Altitude, &InstanceName, RetVolume);
    }
    if ( (int)v13 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_389;
      }
      v29 = 17;
      goto LABEL_79;
    }
    LODWORD(v13) = FltGetInstanceContext(RetInstance, &Context);
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( (int)v13 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_389;
      }
      v29 = 18;
      goto LABEL_79;
    }
    v13 = (unsigned int)HsmpAccessCheck((__int64)Context, (struct _FILE_OBJECT *)v117, 2u);
    HsmDbgBreakOnStatus(v13);
    if ( (int)v13 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_389;
      }
      v29 = 19;
      goto LABEL_79;
    }
    switch ( a2 )
    {
      case 1:
        goto LABEL_389;
      case 2:
        LODWORD(v13) = 0;
        v32 = 3;
        v33 = a4 < 0x18;
        v34 = 0;
        v35 = 0;
        if ( v33 )
        {
          LODWORD(v13) = -1073741275;
        }
        else
        {
          v36 = *(unsigned __int16 *)(a3 + 14);
          if ( (unsigned __int16)v36 <= 3u
            || (v37 = *(_DWORD *)(a3 + 8), v37 < 0x30)
            || (v38 = *(_WORD *)(a3 + 40), v38 >= 0x12u)
            || (v39 = *(unsigned int *)(a3 + 44), (_DWORD)v39) && (v39 < 8 * v36 + 16 || (unsigned int)v39 > v37)
            || (v40 = *(unsigned __int16 *)(a3 + 42), v40 > v37)
            || v40 + (unsigned int)v39 < (unsigned int)v39
            || v40 + (unsigned int)v39 > v37
            || v38 != 17 )
          {
            LODWORD(v13) = -1073741275;
          }
          else
          {
            if ( (_DWORD)v39 && (_WORD)v40 )
              v34 = a3 + v39;
            v35 = *(unsigned __int16 *)(a3 + 42);
          }
          if ( (int)v13 < 0 )
            v35 = 0;
        }
        HsmDbgBreakOnStatus((unsigned int)v13);
        if ( (int)v13 < 0 )
        {
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v15 = 20;
            goto LABEL_21;
          }
          goto LABEL_389;
        }
        if ( !v34 )
        {
          LODWORD(v13) = -1073688821;
          v14 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v15 = 21;
            v16 = 3221278475LL;
            goto LABEL_22;
          }
          goto LABEL_389;
        }
        if ( v35 < 0x18 )
        {
          v32 = 0;
          goto LABEL_178;
        }
        if ( *(_DWORD *)v34 != 1850307155 )
        {
          v32 = 1;
          goto LABEL_178;
        }
        if ( (*(_BYTE *)(v34 + 12) & 2) != 0 )
        {
          v32 = 2;
          if ( *(_DWORD *)(v34 + 4) != RtlComputeCrc32(0, (PUCHAR)(v34 + 8), v35 - 8) )
            goto LABEL_178;
          v32 = 3;
        }
        v41 = *(unsigned int *)(v34 + 8);
        if ( v35 >= (unsigned int)v41 )
        {
          v42 = *(unsigned __int16 *)(v34 + 14);
          if ( (_WORD)v42 )
          {
            v43 = 8 * v42 + 16;
            if ( v43 < v41 )
            {
              v32 = 0x10000;
              for ( i = 0; ; ++i )
              {
                v45 = *(unsigned __int16 *)(v34 + 14);
                if ( (unsigned __int16)v42 >= 9u )
                  v45 = 9;
                if ( i >= v45 )
                  break;
                if ( *(_WORD *)(v34 + 8LL * i + 16) >= 0x12u )
                  goto LABEL_178;
                v46 = *(unsigned int *)(v34 + 8LL * i + 20);
                if ( (_DWORD)v46 )
                {
                  if ( v46 < v43 )
                    goto LABEL_178;
                }
                if ( (unsigned int)v46 > (unsigned int)v41 )
                  goto LABEL_178;
                v47 = *(unsigned __int16 *)(v34 + 8LL * i + 18);
                if ( v47 > (unsigned int)v41 )
                  goto LABEL_178;
                v48 = v46 + v47;
                if ( v48 < (unsigned int)v46 || v48 > (unsigned int)v41 )
                  goto LABEL_178;
                ++v32;
              }
              v49 = *(unsigned __int16 *)(v34 + 14);
              if ( (unsigned __int16)v49 > 7u
                && (v50 = *(_DWORD *)(v34 + 8), (unsigned int)v41 >= 0x50)
                && (v51 = *(_WORD *)(v34 + 72), v51 < 0x12u)
                && ((v52 = *(unsigned int *)(v34 + 76), !(_DWORD)v52) || v52 >= 8 * v49 + 16 && (unsigned int)v52 <= v50)
                && (v53 = *(unsigned __int16 *)(v34 + 74), v53 <= v50)
                && v53 + (unsigned int)v52 >= (unsigned int)v52
                && v53 + (unsigned int)v52 <= v50
                && v51 == 16
                && (_WORD)v53 == 16 )
              {
                memmove((void *)(a1 + 264), (const void *)(v34 + v52), *(unsigned __int16 *)(v34 + 74));
                LODWORD(v13) = 0;
              }
              else
              {
                LODWORD(v13) = -1073741275;
              }
              HsmDbgBreakOnStatus((unsigned int)v13);
              if ( (int)v13 < 0 )
              {
                v14 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  v15 = 23;
                  goto LABEL_21;
                }
                goto LABEL_389;
              }
              LODWORD(v13) = HsmCldPersistSyncRootInfo(Context, v117, v34, v35);
              HsmDbgBreakOnStatus((unsigned int)v13);
              if ( (int)v13 >= 0 )
                goto LABEL_389;
              v28 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_389;
              }
              v29 = 24;
              goto LABEL_173;
            }
            v32 = 5;
          }
          else
          {
            v32 = 4;
          }
        }
LABEL_178:
        LODWORD(v13) = -1073741811;
        HsmDbgBreakOnStatus(3221225485LL);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            22,
            WPP_452df49304b034ad87c0baec305776b3_Traceguids,
            v32,
            -1073741811);
        }
        goto LABEL_389;
      case 3:
        LODWORD(v13) = HsmCldDeleteSyncRootInfo(Context, v117);
        HsmDbgBreakOnStatus((unsigned int)v13);
        if ( (int)v13 >= 0 )
          goto LABEL_389;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 25;
        goto LABEL_79;
    }
    v126 = *((_QWORD *)Context + 2);
    if ( a2 == 7 )
    {
      LODWORD(v13) = HsmiQueryFullFilePath(*((_QWORD *)Context + 4), v31, v117, 257, P);
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 >= 0 )
      {
        if ( a4 >= 0x18
          && (v54 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v54 > 0x16u)
          && (v55 = *(_DWORD *)(a3 + 8), v55 >= 0xC8)
          && (v56 = *(_WORD *)(a3 + 192), v56 < 0x12u)
          && ((v57 = *(unsigned int *)(a3 + 196), LODWORD(v13) = 0, !(_DWORD)v57)
           || v57 >= 8 * v54 + 16 && (unsigned int)v57 <= v55)
          && (v58 = *(unsigned __int16 *)(a3 + 194), v58 <= v55)
          && v58 + (unsigned int)v57 >= (unsigned int)v57
          && v58 + (unsigned int)v57 <= v55
          && v56 == 6
          && v58 == 8 )
        {
          v124 = *(_QWORD *)(v57 + a3);
        }
        else
        {
          LODWORD(v13) = -1073741275;
        }
        HsmDbgBreakOnStatus((unsigned int)v13);
        if ( (int)v13 >= 0 )
        {
          v59 = 0;
          v60 = 0;
          if ( a4 >= 0x18 )
          {
            v61 = *(unsigned __int16 *)(a3 + 14);
            if ( (unsigned __int16)v61 > 9u )
            {
              v62 = *(_DWORD *)(a3 + 8);
              if ( v62 >= 0x60 )
              {
                v63 = *(_WORD *)(a3 + 88);
                if ( v63 < 0x12u )
                {
                  v64 = *(unsigned int *)(a3 + 92);
                  if ( !(_DWORD)v64 || v64 >= 8 * v61 + 16 && (unsigned int)v64 <= v62 )
                  {
                    v65 = *(unsigned __int16 *)(a3 + 90);
                    if ( v65 <= v62
                      && v65 + (unsigned int)v64 >= (unsigned int)v64
                      && v65 + (unsigned int)v64 <= v62
                      && v63 == 17 )
                    {
                      if ( (_DWORD)v64 && (_WORD)v65 )
                        v59 = a3 + v64;
                      v60 = *(unsigned __int16 *)(a3 + 90);
                    }
                  }
                }
              }
            }
          }
          LODWORD(v13) = CldSyncReportSyncStatusOnRoot(v126, v124, (unsigned int)P, v59, v60);
          HsmDbgBreakOnStatus((unsigned int)v13);
          if ( (int)v13 >= 0 )
            goto LABEL_389;
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_389;
          }
          v29 = 28;
        }
        else
        {
          v28 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_389;
          }
          v29 = 27;
        }
      }
      else
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 26;
      }
      goto LABEL_79;
    }
    if ( a4 >= 0x18
      && (v66 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v66 > 4u)
      && (v67 = *(_DWORD *)(a3 + 8), v67 >= 0x38)
      && (v68 = *(_WORD *)(a3 + 48), v68 < 0x12u)
      && ((v69 = *(unsigned int *)(a3 + 52), LODWORD(v13) = 0, !(_DWORD)v69)
       || v69 >= 8 * v66 + 16 && (unsigned int)v69 <= v67)
      && (v70 = *(unsigned __int16 *)(a3 + 50), v70 <= v67)
      && v70 + (unsigned int)v69 >= (unsigned int)v69
      && v70 + (unsigned int)v69 <= v67
      && v68 == 6
      && v70 == 8 )
    {
      Buffer = *(_QWORD *)(v69 + a3);
    }
    else
    {
      LODWORD(v13) = -1073741275;
    }
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( (int)v13 < 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_389;
      }
      v29 = 29;
      goto LABEL_79;
    }
    if ( a2 == 4 )
    {
      v123 = 0;
      v119 = 0;
      v131 = 0;
      v120 = 0;
      v13 = (unsigned int)HsmpCheckLegacyFilterAbsence();
      HsmDbgBreakOnStatus(v13);
      if ( (int)v13 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 30;
        goto LABEL_79;
      }
      LODWORD(v13) = HsmiQueryFullFilePath(*((_QWORD *)Context + 4), v71, v117, 257, P);
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 31;
        goto LABEL_79;
      }
      v72 = a4;
      if ( a4 >= 0x18 )
      {
        v73 = *(unsigned __int16 *)(a3 + 14);
        if ( (unsigned __int16)v73 > 5u
          && (v74 = *(_DWORD *)(a3 + 8), v74 >= 0x40)
          && (v75 = *(_WORD *)(a3 + 56), v75 < 0x12u)
          && ((v76 = *(unsigned int *)(a3 + 60), LODWORD(v13) = 0, !(_DWORD)v76)
           || v76 >= 8 * v73 + 16 && (unsigned int)v76 <= v74)
          && (v77 = *(unsigned __int16 *)(a3 + 58), v77 <= v74)
          && v77 + (unsigned int)v76 >= (unsigned int)v76
          && v77 + (unsigned int)v76 <= v74
          && v75 == 10
          && (_WORD)v77 == 4 )
        {
          v119 = *(_DWORD *)(v76 + a3);
        }
        else
        {
          LODWORD(v13) = -1073741275;
        }
        v7 = v121;
      }
      else
      {
        LODWORD(v13) = -1073741275;
      }
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 32;
        goto LABEL_79;
      }
      if ( a4 >= 0x18
        && (v78 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v78 > 0xEu)
        && (v79 = *(_DWORD *)(a3 + 8), v79 >= 0x88)
        && (v80 = *(_WORD *)(a3 + 128), v80 < 0x12u)
        && ((v81 = *(unsigned int *)(a3 + 132), LODWORD(v13) = 0, !(_DWORD)v81)
         || v81 >= 8 * v78 + 16 && (unsigned int)v81 <= v79)
        && (v82 = *(unsigned __int16 *)(a3 + 130), v82 <= v79)
        && v82 + (unsigned int)v81 >= (unsigned int)v81
        && v82 + (unsigned int)v81 <= v79
        && v80 == 10
        && (_WORD)v82 == 4 )
      {
        v120 = *(_DWORD *)(v81 + a3);
      }
      else
      {
        LODWORD(v13) = -1073741275;
      }
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 33;
        goto LABEL_79;
      }
      if ( a4 >= 0x18 )
      {
        v83 = *(unsigned __int16 *)(a3 + 14);
        if ( (unsigned __int16)v83 > 0xDu
          && (v84 = *(_DWORD *)(a3 + 8), v84 >= 0x80)
          && (v85 = *(_WORD *)(a3 + 120), v85 < 0x12u)
          && ((v86 = *(unsigned int *)(a3 + 124), LODWORD(v13) = 0, !(_DWORD)v86)
           || v86 >= 8 * v83 + 16 && (unsigned int)v86 <= v84)
          && (v87 = *(unsigned __int16 *)(a3 + 122), v87 <= v84)
          && v87 + (unsigned int)v86 >= (unsigned int)v86
          && v87 + (unsigned int)v86 <= v84
          && v85 == 10
          && (_WORD)v87 == 4 )
        {
          v131 = *(_DWORD *)(v86 + a3);
        }
        else
        {
          LODWORD(v13) = -1073741275;
        }
        v72 = a4;
      }
      else
      {
        LODWORD(v13) = -1073741275;
      }
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 34;
        goto LABEL_79;
      }
      if ( v72 >= 0x18
        && (v88 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v88 > 0x16u)
        && (v89 = *(_DWORD *)(a3 + 8), v89 >= 0xC8)
        && (v90 = *(_WORD *)(a3 + 192), v90 < 0x12u)
        && ((v91 = *(unsigned int *)(a3 + 196), LODWORD(v13) = 0, !(_DWORD)v91)
         || v91 >= 8 * v88 + 16 && (unsigned int)v91 <= v89)
        && (v92 = *(unsigned __int16 *)(a3 + 194), v92 <= v89)
        && v92 + (unsigned int)v91 >= (unsigned int)v91
        && v92 + (unsigned int)v91 <= v89
        && v90 == 6
        && v92 == 8 )
      {
        v124 = *(_QWORD *)(v91 + a3);
      }
      else
      {
        LODWORD(v13) = -1073741275;
      }
      HsmDbgBreakOnStatus((unsigned int)v13);
      if ( (int)v13 < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 35;
        goto LABEL_79;
      }
      FltAcquirePushLockExclusiveEx(&qword_1400286A8, 0);
      v93 = v124;
      v13 = (unsigned int)CldSyncConnectRoot(v126, a1, v124, (unsigned int)P, v119, v131, Buffer, (__int64)&v123);
      HsmDbgBreakOnStatus(v13);
      if ( (int)v13 < 0 )
      {
        v94 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_383;
        }
        v95 = 37;
        goto LABEL_348;
      }
      FltAcquirePushLockExclusiveEx(a1 + 144, 0);
      LODWORD(v13) = CldiPortInsertSyncRootNoLock(a1, v123, Buffer, v93);
      FltReleasePushLockEx(a1 + 144, 0);
      if ( (int)v13 >= 0 )
      {
        v97 = (struct _KPROCESS **)(a1 + 104);
        if ( !*(_QWORD *)(a1 + 104) || (v98 = *v97, v98 == IoGetCurrentProcess()) )
        {
          CurrentProcess = IoGetCurrentProcess();
          CldCaptureProcessInfo(CurrentProcess, a1 + 104);
          v104 = IoGetCurrentProcess();
          HsmOsSetProcessAsSyncProvider(v104);
          v105 = v120;
          ++*(_DWORD *)(a1 + 140);
          *(_DWORD *)(a1 + 260) = v105;
        }
        else
        {
          LODWORD(v13) = -1073688808;
          HsmDbgBreakOnStatus(3221278488LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qiqDZd(
              WPP_GLOBAL_Control->AttachedDevice,
              v99,
              v100,
              a1,
              (char)v7,
              (char)*v97,
              *(_DWORD *)(a1 + 128),
              *(_QWORD *)(a1 + 112));
          }
          CurrentProcessId = (unsigned int)PsGetCurrentProcessId();
          MicrosoftTelemetryAssertTriggeredArgsMsgKM(
            v102,
            *(unsigned int *)(a1 + 128),
            CurrentProcessId,
            "ConnectingPortContext's SyncProvider is already set");
        }
        goto LABEL_383;
      }
      CldSyncDisconnectRootByObject(v123, 3221225474LL);
      v94 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v95 = 38;
LABEL_348:
        v96 = v7;
LABEL_349:
        LODWORD(Object) = v13;
        WPP_SF_qd(v94->AttachedDevice, v95, WPP_452df49304b034ad87c0baec305776b3_Traceguids, v96, Object);
      }
    }
    else
    {
      if ( a2 != 5 )
      {
        LODWORD(v13) = -1073741808;
        HsmDbgBreakOnStatus(3221225488LL);
        goto LABEL_389;
      }
      if ( a4 < 0x18
        || (v106 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v106 <= 0x16u)
        || (v107 = *(_DWORD *)(a3 + 8), v107 < 0xC8)
        || (v108 = *(_WORD *)(a3 + 192), v108 >= 0x12u)
        || (v109 = *(unsigned int *)(a3 + 196), (_DWORD)v109) && (v109 < 8 * v106 + 16 || (unsigned int)v109 > v107)
        || (v110 = *(unsigned __int16 *)(a3 + 194), v110 > v107)
        || v110 + (unsigned int)v109 < (unsigned int)v109
        || v110 + (unsigned int)v109 > v107
        || v108 != 6
        || v110 != 8 )
      {
        LODWORD(v13) = -1073741275;
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_389;
        }
        v29 = 40;
LABEL_173:
        v30 = v121;
        goto LABEL_80;
      }
      v111 = *(_QWORD *)(v109 + a3);
      FltAcquirePushLockExclusiveEx(&qword_1400286A8, 0);
      v123 = 0;
      v13 = (unsigned int)CldSyncDisconnectRoot(v126, v111, Buffer, &v123);
      HsmDbgBreakOnStatus(v13);
      if ( (int)v13 >= 0 )
      {
        FltAcquirePushLockExclusiveEx(a1 + 144, 0);
        RtlDeleteElementGenericTableAvl((PRTL_AVL_TABLE)(a1 + 152), &Buffer);
        FltReleasePushLockEx(a1 + 144, 0);
        if ( (*(_DWORD *)(a1 + 140))-- == 1 )
        {
          v113 = IoGetCurrentProcess();
          HsmOsClearProcessAsSyncProvider(v113);
          CldReleaseProcessInfo(a1 + 104);
        }
        goto LABEL_383;
      }
      v94 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v96 = v121;
        v95 = 41;
        goto LABEL_349;
      }
    }
LABEL_383:
    FltReleasePushLockEx(&qword_1400286A8, 0);
    goto LABEL_389;
  }
  if ( a4 >= 0x18
    && (v8 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v8 > 4u)
    && (v9 = *(_DWORD *)(a3 + 8), v9 >= 0x38)
    && (v10 = *(_WORD *)(a3 + 48), v10 < 0x12u)
    && ((v11 = *(unsigned int *)(a3 + 52), !(_DWORD)v11) || v11 >= 8 * v8 + 16 && (unsigned int)v11 <= v9)
    && (v12 = *(unsigned __int16 *)(a3 + 50), v12 <= v9)
    && v12 + (unsigned int)v11 >= (unsigned int)v11
    && v12 + (unsigned int)v11 <= v9
    && v10 == 6
    && v12 == 8 )
  {
    LODWORD(v13) = 0;
    Buffer = *(_QWORD *)(v11 + a3);
  }
  else
  {
    LODWORD(v13) = -1073741275;
  }
  HsmDbgBreakOnStatus((unsigned int)v13);
  if ( (int)v13 >= 0 )
  {
    if ( a4 >= 0x18
      && (v17 = *(unsigned __int16 *)(a3 + 14), (unsigned __int16)v17 > 0xDu)
      && (v18 = *(_DWORD *)(a3 + 8), v18 >= 0x80)
      && (v19 = *(_WORD *)(a3 + 120), v19 < 0x12u)
      && ((v20 = *(unsigned int *)(a3 + 124), LODWORD(v13) = 0, !(_DWORD)v20)
       || v20 >= 8 * v17 + 16 && (unsigned int)v20 <= v18)
      && (v21 = *(unsigned __int16 *)(a3 + 122), v21 <= v18)
      && v21 + (unsigned int)v20 >= (unsigned int)v20
      && v21 + (unsigned int)v20 <= v18
      && v19 == 10
      && (_WORD)v21 == 4 )
    {
      LODWORD(v7) = *(_DWORD *)(v20 + a3);
    }
    else
    {
      LODWORD(v13) = -1073741275;
    }
    HsmDbgBreakOnStatus((unsigned int)v13);
    if ( (int)v13 >= 0 )
    {
      if ( Buffer )
      {
        FltAcquirePushLockSharedEx(a1 + 144, 0);
        v22 = CldiPortLookupSyncRootNoLock(a1, Buffer);
        FltReleasePushLockEx(a1 + 144, 0);
        if ( v22 )
        {
          *(_DWORD *)(v22 + 48) = (_DWORD)v7;
        }
        else
        {
          LODWORD(v13) = -1073688821;
          HsmDbgBreakOnStatus(3221278475LL);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_qd(
              WPP_GLOBAL_Control->AttachedDevice,
              13,
              WPP_452df49304b034ad87c0baec305776b3_Traceguids,
              a1,
              -1073688821);
          }
        }
      }
      else
      {
        *(_DWORD *)(a1 + 136) = (_DWORD)v7;
      }
    }
    else
    {
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v15 = 12;
        goto LABEL_21;
      }
    }
  }
  else
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v15 = 11;
LABEL_21:
      v16 = (unsigned int)v13;
LABEL_22:
      WPP_SF_d(v14->AttachedDevice, v15, WPP_452df49304b034ad87c0baec305776b3_Traceguids, v16);
    }
  }
LABEL_389:
  if ( P[1] )
    ExFreePoolWithTag(P[1], 0x73557348u);
  if ( Context )
    FltReleaseContext(Context);
  if ( RetInstance )
    FltObjectDereference(RetInstance);
  if ( RetVolume )
    FltObjectDereference(RetVolume);
  if ( v117 )
    ObfDereferenceObject(v117);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x14003baf0  mov     rax, rsp
0x14003baf3  mov     [rax+18h], rbx
0x14003baf7  mov     [rax+20h], r9d
0x14003bafb  mov     [rax+8], rcx
0x14003baff  push    rbp
0x14003bb00  push    rsi
0x14003bb01  push    rdi
0x14003bb02  push    r12
0x14003bb04  push    r13
0x14003bb06  push    r14
0x14003bb08  push    r15
0x14003bb0a  lea     rbp, [rax-5Fh]
0x14003bb0e  sub     rsp, 0D0h
0x14003bb15  xor     r10d, r10d
0x14003bb18  mov     qword ptr [rbp+57h+InstanceName.Length], 0E000Ch
0x14003bb20  mov     [rbp+57h+var_90], r10
0x14003bb24  lea     rax, aCldflt; "CldFlt"
0x14003bb2b  mov     [rbp+57h+InstanceName.Buffer], rax
0x14003bb2f  lea     rax, a180451; "180451"
0x14003bb36  mov     [rbp+57h+Altitude.Buffer], rax
0x14003bb3a  xorps   xmm0, xmm0
0x14003bb3d  mov     [rbp+57h+var_A8], r10
0x14003bb41  lea     ecx, [r10+12h]
0x14003bb45  mov     [rbp+57h+RetVolume], r10
0x14003bb49  mov     r13d, r9d
0x14003bb4c  mov     [rbp+57h+RetInstance], r10
0x14003bb50  mov     rbx, r8
0x14003bb53  mov     [rbp+57h+Context], r10
0x14003bb57  movzx   r15d, dx
0x14003bb5b  mov     [rbp+57h+var_78], r10
0x14003bb5f  mov     r12d, r10d
0x14003bb62  mov     [rbp+57h+Buffer], r10
0x14003bb66  mov     esi, 0C0000225h
0x14003bb6b  mov     qword ptr [rbp+57h+Altitude.Length], 0E000Ch
0x14003bb73  movups  xmmword ptr [rbp+57h+P], xmm0
0x14003bb77  cmp     dx, 6
0x14003bb7b  jnz     loc_14003BDD3
0x14003bb81  cmp     [rbp+57h+arg_18], 18h
0x14003bb85  lea     r13d, [r10+4]
0x14003bb89  jb      short loc_14003BBF2
0x14003bb8b  movzx   eax, word ptr [r8+0Eh]
0x14003bb90  cmp     r13w, ax
0x14003bb94  jnb     short loc_14003BBF2
0x14003bb96  mov     r8d, [r8+8]
0x14003bb9a  cmp     r8d, 38h ; '8'
0x14003bb9e  jb      short loc_14003BBF2
0x14003bba0  movzx   r9d, word ptr [rbx+30h]
0x14003bba5  cmp     r9w, cx
0x14003bba9  jnb     short loc_14003BBF2
0x14003bbab  mov     edx, [rbx+34h]
0x14003bbae  test    edx, edx
0x14003bbb0  jz      short loc_14003BBC4
0x14003bbb2  lea     rcx, ds:10h[rax*8]
0x14003bbba  cmp     rdx, rcx
0x14003bbbd  jb      short loc_14003BBF2
0x14003bbbf  cmp     edx, r8d
0x14003bbc2  ja      short loc_14003BBF2
0x14003bbc4  movzx   eax, word ptr [rbx+32h]
0x14003bbc8  cmp     eax, r8d
0x14003bbcb  ja      short loc_14003BBF2
0x14003bbcd  lea     ecx, [rax+rdx]
0x14003bbd0  cmp     ecx, edx
0x14003bbd2  jb      short loc_14003BBF2
0x14003bbd4  cmp     ecx, r8d
0x14003bbd7  ja      short loc_14003BBF2
0x14003bbd9  cmp     r9w, 6
0x14003bbde  jnz     short loc_14003BBF2
0x14003bbe0  cmp     eax, 8
0x14003bbe3  jnz     short loc_14003BBF2
0x14003bbe5  mov     rcx, [rdx+rbx]
0x14003bbe9  mov     edi, r10d
0x14003bbec  mov     [rbp+57h+Buffer], rcx
0x14003bbf0  jmp     short loc_14003BBF4
0x14003bbf2  mov     edi, esi
0x14003bbf4  mov     ecx, edi
0x14003bbf6  call    HsmDbgBreakOnStatus
0x14003bbfb  test    edi, edi
0x14003bbfd  jns     short loc_14003BC4F
0x14003bbff  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bc06  lea     rax, WPP_GLOBAL_Control
0x14003bc0d  cmp     rcx, rax
0x14003bc10  jz      loc_14003CF95
0x14003bc16  test    dword ptr [rcx+2Ch], 100h
0x14003bc1d  jz      loc_14003CF95
0x14003bc23  mov     r14d, 2
0x14003bc29  cmp     [rcx+29h], r14b
0x14003bc2d  jb      loc_14003CF95
0x14003bc33  lea     edx, [r14+9]
0x14003bc37  mov     r9d, edi
0x14003bc3a  mov     rcx, [rcx+18h]
0x14003bc3e  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x14003bc45  call    WPP_SF_d
0x14003bc4a  jmp     loc_14003CF95
0x14003bc4f  cmp     [rbp+57h+arg_18], 18h
0x14003bc53  mov     r15d, 0Dh
0x14003bc59  jb      short loc_14003BCC4
0x14003bc5b  movzx   eax, word ptr [rbx+0Eh]
0x14003bc5f  cmp     r15w, ax
0x14003bc63  jnb     short loc_14003BCC4
0x14003bc65  mov     r8d, [rbx+8]
0x14003bc69  cmp     r8d, 80h
0x14003bc70  jb      short loc_14003BCC4
0x14003bc72  movzx   r9d, word ptr [rbx+78h]
0x14003bc77  lea     ecx, [r15+5]
0x14003bc7b  cmp     r9w, cx
0x14003bc7f  jnb     short loc_14003BCC4
0x14003bc81  mov     edx, [rbx+7Ch]
0x14003bc84  xor     edi, edi
0x14003bc86  test    edx, edx
0x14003bc88  jz      short loc_14003BC9C
0x14003bc8a  lea     rcx, ds:10h[rax*8]
0x14003bc92  cmp     rdx, rcx
0x14003bc95  jb      short loc_14003BCC4
0x14003bc97  cmp     edx, r8d
0x14003bc9a  ja      short loc_14003BCC4
0x14003bc9c  movzx   eax, word ptr [rbx+7Ah]
0x14003bca0  cmp     eax, r8d
0x14003bca3  ja      short loc_14003BCC4
0x14003bca5  lea     ecx, [rax+rdx]
0x14003bca8  cmp     ecx, edx
0x14003bcaa  jb      short loc_14003BCC4
0x14003bcac  cmp     ecx, r8d
0x14003bcaf  ja      short loc_14003BCC4
0x14003bcb1  cmp     r9w, 0Ah
0x14003bcb6  jnz     short loc_14003BCC4
0x14003bcb8  cmp     ax, r13w
0x14003bcbc  jnz     short loc_14003BCC4
0x14003bcbe  mov     r12d, [rdx+rbx]
0x14003bcc2  jmp     short loc_14003BCC6
0x14003bcc4  mov     edi, esi
0x14003bcc6  mov     ecx, edi
0x14003bcc8  call    HsmDbgBreakOnStatus
0x14003bccd  xor     ecx, ecx
0x14003bccf  test    edi, edi
0x14003bcd1  jns     short loc_14003BD10
0x14003bcd3  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bcda  lea     rax, WPP_GLOBAL_Control
0x14003bce1  cmp     rcx, rax
0x14003bce4  jz      loc_14003CF95
0x14003bcea  test    dword ptr [rcx+2Ch], 100h
0x14003bcf1  jz      loc_14003CF95
0x14003bcf7  mov     r14d, 2
0x14003bcfd  cmp     [rcx+29h], r14b
0x14003bd01  jb      loc_14003CF95
0x14003bd07  lea     edx, [r14+0Ah]
0x14003bd0b  jmp     loc_14003BC37
0x14003bd10  cmp     [rbp+57h+Buffer], rcx
0x14003bd14  jz      loc_14003BDC3
0x14003bd1a  mov     r13, [rbp+57h+arg_0]
0x14003bd1e  xor     edx, edx
0x14003bd20  lea     rbx, [r13+90h]
0x14003bd27  mov     rcx, rbx
0x14003bd2a  call    cs:__imp_FltAcquirePushLockSharedEx
0x14003bd31  nop     dword ptr [rax+rax+00h]
0x14003bd36  mov     rdx, [rbp+57h+Buffer]
0x14003bd3a  mov     rcx, r13
0x14003bd3d  call    CldiPortLookupSyncRootNoLock
0x14003bd42  xor     edx, edx
0x14003bd44  mov     rcx, rbx
0x14003bd47  mov     rsi, rax
0x14003bd4a  call    cs:__imp_FltReleasePushLockEx
0x14003bd51  nop     dword ptr [rax+rax+00h]
0x14003bd56  test    rsi, rsi
0x14003bd59  jnz     short loc_14003BDBA
0x14003bd5b  mov     ebx, 0C000CF0Bh
0x14003bd60  mov     ecx, ebx
0x14003bd62  mov     edi, ebx
0x14003bd64  call    HsmDbgBreakOnStatus
0x14003bd69  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bd70  lea     rax, WPP_GLOBAL_Control
0x14003bd77  cmp     rcx, rax
0x14003bd7a  jz      loc_14003CF95
0x14003bd80  test    dword ptr [rcx+2Ch], 100h
0x14003bd87  jz      loc_14003CF95
0x14003bd8d  lea     r14d, [rsi+2]
0x14003bd91  cmp     [rcx+29h], r14b
0x14003bd95  jb      loc_14003CF95
0x14003bd9b  mov     rcx, [rcx+18h]
0x14003bd9f  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x14003bda6  mov     edx, r15d
0x14003bda9  mov     dword ptr [rsp+100h+Object], ebx
0x14003bdad  mov     r9, r13
0x14003bdb0  call    WPP_SF_qd
0x14003bdb5  jmp     loc_14003CF95
0x14003bdba  mov     [rsi+30h], r12d
0x14003bdbe  jmp     loc_14003CF95
0x14003bdc3  mov     rcx, [rbp+57h+arg_0]
0x14003bdc7  mov     [rcx+88h], r12d
0x14003bdce  jmp     loc_14003CF95
0x14003bdd3  mov     r14d, 2
0x14003bdd9  cmp     r13d, 18h
0x14003bddd  jb      short loc_14003BE4A
0x14003bddf  movzx   eax, word ptr [r8+0Eh]
0x14003bde4  cmp     r14w, ax
0x14003bde8  jnb     short loc_14003BE4A
0x14003bdea  mov     r8d, [r8+8]
0x14003bdee  cmp     r8d, 28h ; '('
0x14003bdf2  jb      short loc_14003BE4A
0x14003bdf4  movzx   r9d, word ptr [rbx+20h]
0x14003bdf9  cmp     r9w, cx
0x14003bdfd  jnb     short loc_14003BE4A
0x14003bdff  mov     edx, [rbx+24h]
0x14003be02  test    edx, edx
0x14003be04  jz      short loc_14003BE18
0x14003be06  lea     rcx, ds:10h[rax*8]
0x14003be0e  cmp     rdx, rcx
0x14003be11  jb      short loc_14003BE4A
0x14003be13  cmp     edx, r8d
0x14003be16  ja      short loc_14003BE4A
0x14003be18  movzx   ecx, word ptr [rbx+22h]
0x14003be1c  cmp     ecx, r8d
0x14003be1f  ja      short loc_14003BE4A
0x14003be21  lea     eax, [rcx+rdx]
0x14003be24  cmp     eax, edx
0x14003be26  jb      short loc_14003BE4A
0x14003be28  cmp     eax, r8d
0x14003be2b  ja      short loc_14003BE4A
0x14003be2d  mov     eax, 0Bh
0x14003be32  cmp     r9w, ax
0x14003be36  jnz     short loc_14003BE4A
0x14003be38  cmp     ecx, 8
0x14003be3b  jnz     short loc_14003BE4A
0x14003be3d  mov     r12, [rdx+rbx]
0x14003be41  mov     edi, r10d
0x14003be44  mov     [rbp+57h+var_90], r12
0x14003be48  jmp     short loc_14003BE4C
0x14003be4a  mov     edi, esi
0x14003be4c  mov     ecx, edi
0x14003be4e  call    HsmDbgBreakOnStatus
0x14003be53  xor     eax, eax
0x14003be55  test    edi, edi
0x14003be57  jns     short loc_14003BE91
0x14003be59  mov     rcx, cs:WPP_GLOBAL_Control
0x14003be60  lea     rax, WPP_GLOBAL_Control
0x14003be67  cmp     rcx, rax
0x14003be6a  jz      loc_14003CF95
0x14003be70  test    dword ptr [rcx+2Ch], 100h
0x14003be77  jz      loc_14003CF95
0x14003be7d  cmp     [rcx+29h], r14b
0x14003be81  jb      loc_14003CF95
0x14003be87  mov     edx, 0Eh
0x14003be8c  jmp     loc_14003BC37
0x14003be91  mov     r8, cs:__imp_IoFileObjectType
0x14003be98  mov     r9b, 1; AccessMode
0x14003be9b  mov     [rsp+100h+HandleInformation], rax; HandleInformation
0x14003bea0  xor     edx, edx; DesiredAccess
0x14003bea2  lea     rax, [rbp+57h+var_A8]
0x14003bea6  mov     rcx, r12; Handle
0x14003bea9  mov     [rsp+100h+Object], rax; Object
0x14003beae  mov     r8, [r8]; ObjectType
0x14003beb1  call    cs:__imp_ObReferenceObjectByHandle
0x14003beb8  nop     dword ptr [rax+rax+00h]
0x14003bebd  mov     ecx, eax
0x14003bebf  mov     edi, eax
0x14003bec1  call    HsmDbgBreakOnStatus
0x14003bec6  test    edi, edi
0x14003bec8  jns     short loc_14003BF02
0x14003beca  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bed1  lea     rax, WPP_GLOBAL_Control
0x14003bed8  cmp     rcx, rax
0x14003bedb  jz      loc_14003CF95
0x14003bee1  test    dword ptr [rcx+2Ch], 100h
0x14003bee8  jz      loc_14003CF95
0x14003beee  cmp     [rcx+29h], r14b
0x14003bef2  jb      loc_14003CF95
0x14003bef8  mov     edx, 0Fh
0x14003befd  jmp     loc_14003BC37
0x14003bf02  mov     rdx, [rbp+57h+var_A8]; FileObject
0x14003bf06  lea     r8, [rbp+57h+RetVolume]; RetVolume
0x14003bf0a  mov     rcx, cs:Globals; Filter
0x14003bf11  call    cs:__imp_FltGetVolumeFromFileObject
0x14003bf18  nop     dword ptr [rax+rax+00h]
0x14003bf1d  mov     ecx, eax
0x14003bf1f  mov     edi, eax
0x14003bf21  call    HsmDbgBreakOnStatus
0x14003bf26  test    edi, edi
0x14003bf28  jns     short loc_14003BF79
0x14003bf2a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003bf31  lea     rax, WPP_GLOBAL_Control
0x14003bf38  cmp     rcx, rax
0x14003bf3b  jz      loc_14003CF95
0x14003bf41  test    dword ptr [rcx+2Ch], 100h
0x14003bf48  jz      loc_14003CF95
0x14003bf4e  cmp     [rcx+29h], r14b
0x14003bf52  jb      loc_14003CF95
0x14003bf58  mov     edx, 10h
0x14003bf5d  mov     r9, r12
0x14003bf60  mov     rcx, [rcx+18h]
0x14003bf64  lea     r8, WPP_452df49304b034ad87c0baec305776b3_Traceguids
0x14003bf6b  mov     dword ptr [rsp+100h+Object], edi
0x14003bf6f  call    WPP_SF_qd
0x14003bf74  jmp     loc_14003CF95
0x14003bf79  mov     rdx, [rbp+57h+RetVolume]; Volume
0x14003bf7d  lea     rax, [rbp+57h+RetInstance]
0x14003bf81  mov     rcx, cs:Globals; Filter
0x14003bf88  lea     r9, [rbp+57h+InstanceName]; InstanceName
0x14003bf8c  lea     r8, [rbp+57h+Altitude]; Altitude
0x14003bf90  mov     [rsp+100h+Object], rax; RetInstance
0x14003bf95  call    cs:__imp_FltAttachVolumeAtAltitude
0x14003bf9c  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
