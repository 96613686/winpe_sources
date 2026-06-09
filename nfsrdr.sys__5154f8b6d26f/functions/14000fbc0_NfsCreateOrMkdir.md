# NfsCreateOrMkdir

- ea: `0x14000fbc0`
- end: `0x140010860`
- name: `NfsCreateOrMkdir`
- size: `3232`
- prototype: ``
- caller_count: `1`
- callee_count: `34`
- tags: `installer_update`

## callers

- `0x1400316d0`

## callees

- `0x140001f10`
- `0x140003440`
- `0x140003510`
- `0x140003bd0`
- `0x140005c90`
- `0x140008140`
- `0x140009380`
- `0x14000c370`
- `0x14000cdb8`
- `0x14000d99c`
- `0x14000d9f0`
- `0x14000fa80`
- `0x14000fb40`
- `0x14000fbc0`
- `0x140010870`
- `0x140011960`
- `0x140011f84`
- `0x140012024`
- `0x140013ac0`
- `0x1400145f0`
- `0x1400146a0`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x1400173f8`
- `0x14001837c`
- `0x1400200d0`
- `0x1400204c0`
- `0x140022220`
- `0x14002ba4c`
- `0x14002bb40`
- `0x14002bf9c`
- `0x14002c764`
- `0x14002ddac`

## import_xrefs

- `ntoskrnl!KeReleaseMutex` at `0x1400101a3`
- `ntoskrnl!KeReleaseMutex` at `0x14001049f`
- `ntoskrnl!KeReleaseMutex` at `0x1400104dc`
- `ntoskrnl!KeReleaseMutex` at `0x1400106c6`
- `ntoskrnl!KeReleaseMutex` at `0x1400101a3`
- `ntoskrnl!KeReleaseMutex` at `0x14001049f`
- `ntoskrnl!KeReleaseMutex` at `0x1400104dc`
- `ntoskrnl!KeReleaseMutex` at `0x1400106c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400107ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010804`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400107ea`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010804`
- `ntoskrnl!ExAllocatePool2` at `0x14000fce8`
- `ntoskrnl!ExAllocatePool2` at `0x14000fdb3`
- `ntoskrnl!ExAllocatePool2` at `0x14000fce8`
- `ntoskrnl!ExAllocatePool2` at `0x14000fdb3`
- `rpcxdr!OncRpcDestroy` at `0x1400107c0`
- `rpcxdr!OncRpcDestroy` at `0x1400107d4`
- `rpcxdr!OncRpcDestroy` at `0x1400107c0`
- `rpcxdr!OncRpcDestroy` at `0x1400107d4`

## pseudocode

```c
__int64 __fastcall NfsCreateOrMkdir(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        const UNICODE_STRING *a5,
        __int64 a6,
        char a7,
        char a8,
        _WORD *a9,
        __int64 *a10)
{
  __int64 v10; // rbx
  __int64 v12; // r15
  __int64 v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rax
  int v17; // r13d
  __int64 v18; // r14
  __int64 v19; // rsi
  void *v20; // rdi
  int v21; // ebx
  __int64 Pool2; // rax
  int v23; // edx
  void *v24; // rax
  PDEVICE_OBJECT v25; // rcx
  __int64 v26; // rdx
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  int v29; // eax
  int Length; // esi
  int v31; // ebx
  int v32; // eax
  PCHAR Buffer; // r8
  unsigned __int16 v34; // cx
  int v35; // esi
  __int64 v36; // r15
  CHAR v37; // r10
  CHAR v38; // dl
  PCHAR v39; // r8
  unsigned __int16 v40; // cx
  int v41; // ebx
  __int64 v42; // r15
  CHAR v43; // r9
  CHAR v44; // dl
  __int64 v45; // r14
  __int64 v46; // rdx
  __int64 v47; // r8
  __int64 v48; // r8
  unsigned int v49; // r9d
  __int64 v50; // rcx
  __int64 v51; // r9
  int v52; // edx
  unsigned int v53; // r9d
  __int64 v54; // rcx
  PDEVICE_OBJECT v55; // rcx
  __int64 v56; // rdx
  unsigned int v57; // r9d
  __int64 v58; // rcx
  __int64 v59; // r12
  __int64 v60; // rax
  __int64 v61; // r14
  unsigned int v62; // ebx
  struct _DEVICE_OBJECT *v63; // rdx
  __int64 v64; // rdx
  int v65; // ebx
  __int64 v66; // r8
  __int64 v67; // rdx
  __int64 v68; // r8
  struct _UNICODE_STRING *v69; // rbx
  __int64 v70; // r8
  int v71; // r14d
  __int64 v72; // r8
  unsigned __int8 v73; // al
  __int64 *v74; // r14
  __int64 v75; // rdx
  __int64 v76; // r8
  __int64 v77; // r8
  __int64 v79; // [rsp+58h] [rbp-69h] BYREF
  _QWORD v80[2]; // [rsp+60h] [rbp-61h] BYREF
  STRING DestinationString; // [rsp+70h] [rbp-51h] BYREF
  STRING SourceString; // [rsp+80h] [rbp-41h] BYREF
  UNICODE_STRING v83; // [rsp+90h] [rbp-31h] BYREF
  __int64 v84; // [rsp+A0h] [rbp-21h]
  PVOID P; // [rsp+A8h] [rbp-19h]
  __int64 v86; // [rsp+B0h] [rbp-11h]
  __int64 v87; // [rsp+B8h] [rbp-9h]

  v10 = *(_QWORD *)(a2 + 80);
  v84 = v10;
  v79 = 0;
  v12 = a4;
  *(_QWORD *)&v83.Length = 0;
  v83.Buffer = 0;
  v80[0] = 0;
  v80[1] = 0;
  *(_QWORD *)&SourceString.Length = 0;
  SourceString.Buffer = 0;
  *(_QWORD *)&DestinationString.Length = 0;
  DestinationString.Buffer = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 74, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  *a10 = 0;
  v14 = *(_QWORD *)(a1 + 32);
  v15 = *(_QWORD *)(*(_QWORD *)(v14 + 32) + 32LL);
  v16 = *(_QWORD *)(v14 + 40);
  v86 = v15;
  v87 = v16;
  v17 = *(_DWORD *)(v15 + 88);
  if ( !v16 )
    return 3221225662LL;
  if ( !v15 )
    return 3221225662LL;
  v18 = *(_QWORD *)(a1 + 40);
  if ( !v18 )
    return 3221225662LL;
  P = 0;
  v19 = 0;
  if ( !(unsigned __int8)HacIsEntryFake(v12) )
  {
    MdaDissectNameTail(a5, v80, &v83);
    Pool2 = ExAllocatePool2(258, 1024, 844260942);
    v80[0] = Pool2;
    v20 = (void *)Pool2;
    if ( !Pool2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 75, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        v20 = (void *)v80[0];
      }
      v21 = -1073741670;
      goto LABEL_178;
    }
    *(_DWORD *)&SourceString.Length = 0x1000000;
    SourceString.Buffer = (PCHAR)(Pool2 + 512);
    v21 = NfsConvertUnicodeToAnsi(v10, &SourceString, &v83);
    if ( a3 == 5 )
    {
      if ( !a9 || !*a9 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 77, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        v21 = -1073741811;
        goto LABEL_177;
      }
      DestinationString.Length = (*a9 >> 1) + 1;
      DestinationString.MaximumLength = DestinationString.Length;
      v24 = (void *)ExAllocatePool2(258, DestinationString.Length, 844260942);
      P = v24;
      if ( !v24 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_23;
        v26 = 76;
LABEL_22:
        WPP_SF_(v25->AttachedDevice, v26, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_23:
        v21 = -1073741670;
LABEL_177:
        v20 = (void *)v80[0];
        goto LABEL_178;
      }
      DestinationString.Buffer = (PCHAR)v24;
      v21 = NfsConvertUnicodeToAnsi(v84, &DestinationString, a9);
    }
    if ( v21 < 0 )
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
        goto LABEL_177;
      v28 = 78;
      goto LABEL_29;
    }
    v29 = *(_DWORD *)(v18 + 32);
    if ( (v29 & 0x40) != 0 )
    {
      DsSjisToEuc(&SourceString, &SourceString);
      if ( a3 == 5 )
      {
        DsSjisToEuc(&DestinationString, &DestinationString);
        goto LABEL_37;
      }
      goto LABEL_83;
    }
    if ( (v29 & 0x4000) != 0 )
    {
      if ( SourceString.Length )
      {
        Buffer = SourceString.Buffer;
        if ( SourceString.Buffer )
        {
          v34 = 0;
          v35 = SourceString.Length - 1;
          if ( v35 > 0 )
          {
            v36 = 0x3FFFFFF03FFFFFFLL;
            while ( 1 )
            {
              v37 = Buffer[v34];
              if ( (unsigned __int8)(v37 + 127) <= 0x1Fu )
              {
                LOBYTE(v23) = Buffer[v34 + 1];
                if ( (unsigned __int8)(v23 - 65) <= 0x39u )
                {
                  if ( _bittest64(&v36, (unsigned int)(v23 - 65)) )
                    break;
                }
                if ( (unsigned __int8)(v23 + 127) <= 0x1Fu || (unsigned __int8)(v23 + 95) <= 0x5Du )
                  break;
              }
              if ( (unsigned __int8)(v37 + 95) <= 0x5Du )
              {
                v38 = Buffer[v34 + 1];
                if ( (unsigned __int8)(v38 - 65) <= 0x19u
                  || (unsigned __int8)(v38 - 97) <= 0x19u
                  || (unsigned __int8)(v38 + 127) <= 0x1Fu )
                {
                  break;
                }
              }
              if ( (unsigned __int8)(v37 + 127) <= 0x7Du )
                goto LABEL_57;
LABEL_58:
              if ( ++v34 >= v35 )
              {
                v12 = a4;
                goto LABEL_60;
              }
            }
            *(_WORD *)&Buffer[v34] = 16191;
LABEL_57:
            ++v34;
            goto LABEL_58;
          }
        }
      }
LABEL_60:
      if ( a3 == 5 )
      {
        if ( DestinationString.Length )
        {
          v39 = DestinationString.Buffer;
          if ( DestinationString.Buffer )
          {
            v40 = 0;
            v41 = DestinationString.Length - 1;
            if ( v41 > 0 )
            {
              v42 = 0x3FFFFFF03FFFFFFLL;
              while ( 1 )
              {
                v43 = v39[v40];
                if ( (unsigned __int8)(v43 + 127) <= 0x1Fu )
                {
                  LOBYTE(v23) = v39[v40 + 1];
                  if ( (unsigned __int8)(v23 - 65) <= 0x39u )
                  {
                    if ( _bittest64(&v42, (unsigned int)(v23 - 65)) )
                      break;
                  }
                  if ( (unsigned __int8)(v23 + 127) <= 0x1Fu || (unsigned __int8)(v23 + 95) <= 0x5Du )
                    break;
                }
                if ( (unsigned __int8)(v43 + 95) <= 0x5Du )
                {
                  v44 = v39[v40 + 1];
                  if ( (unsigned __int8)(v44 - 65) <= 0x19u
                    || (unsigned __int8)(v44 - 97) <= 0x19u
                    || (unsigned __int8)(v44 + 127) <= 0x1Fu )
                  {
                    v39[v40 + 1] = 63;
                    v39[v40] = 63;
                    goto LABEL_77;
                  }
                }
                if ( (unsigned __int8)(v43 + 127) <= 0x7Du )
                  goto LABEL_77;
LABEL_78:
                if ( ++v40 >= v41 )
                {
                  v12 = a4;
                  goto LABEL_37;
                }
              }
              *(_WORD *)&v39[v40] = 16191;
LABEL_77:
              ++v40;
              goto LABEL_78;
            }
          }
        }
      }
    }
    else if ( (v29 & 0x2000) != 0 )
    {
      DsCnsToEuc(SourceString.Buffer, SourceString.Length, SourceString.Buffer, &SourceString);
      if ( a3 == 5 )
      {
        DsEucToCns(DestinationString.Buffer, DestinationString.Length, DestinationString.Buffer, &DestinationString);
        goto LABEL_37;
      }
    }
LABEL_83:
    Length = 0;
    if ( a3 == 1 )
    {
      v31 = (v17 != 3) + 8;
      goto LABEL_91;
    }
    if ( a3 == 2 )
    {
      v31 = 9;
      v32 = 14;
LABEL_38:
      if ( v17 != 3 )
        v31 = v32;
      goto LABEL_91;
    }
    if ( a3 != 5 )
    {
      v31 = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 79, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_91:
      v45 = v86;
      v19 = NfsRdrBuildCall(
              v86 + 116,
              *(_DWORD *)(v86 + 80),
              *(_DWORD *)(v86 + 84),
              *(_DWORD *)(v86 + 88),
              v31,
              SourceString.Length + (-SourceString.Length & 3) + (-Length & 3u) + Length + 136,
              a1);
      if ( !v19 )
      {
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_23;
        v26 = 80;
        goto LABEL_22;
      }
      HacAcquireLock(v12, v46, v47);
      LOBYTE(v48) = v17 == 3;
      XdrEncodeNfsFileHandleUnsafe(v19, v12 + 216, v48);
      KeReleaseMutex(*(PRKMUTEX *)(v12 + 40), 0);
      XdrEncodeIntUnsafe(v19, SourceString.Length);
      XdrEncodeOpaqueUnsafe(v50, v49);
      if ( v17 == 3 )
      {
        if ( a3 == 1 )
          XdrEncodeIntUnsafe(v19, 0);
      }
      else if ( a3 == 5 )
      {
        XdrEncodeIntUnsafe(v19, DestinationString.Length);
        XdrEncodeOpaqueUnsafe(v58, v57);
        if ( *(int *)(v19 + 264) < 0 )
        {
          v55 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_176;
          }
          v56 = 81;
          goto LABEL_175;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_dd(
          WPP_GLOBAL_Control->AttachedDevice,
          82,
          WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids,
          *(unsigned int *)(a6 + 12),
          *(_DWORD *)(a6 + 20));
      }
      LOBYTE(v51) = v17 == 3;
      XdrEncodeNfsSetAttributes(v19, a3, a6, v51);
      if ( *(int *)(v19 + 264) < 0 )
      {
        v55 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_176;
        v56 = 83;
        goto LABEL_175;
      }
      if ( v17 == 3 && a3 == 5 )
      {
        XdrEncodeIntUnsafe(v19, DestinationString.Length);
        XdrEncodeOpaqueUnsafe(v54, v53);
        if ( *(int *)(v19 + 264) < 0 )
        {
          v55 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          {
            goto LABEL_176;
          }
          v56 = 84;
LABEL_175:
          WPP_SF_(v55->AttachedDevice, v56, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
LABEL_176:
          v21 = *(_DWORD *)(v19 + 264);
          goto LABEL_177;
        }
      }
      v59 = v84;
      v60 = v45 + 72;
      v61 = a1;
      v21 = NfsSendWaitReply(v84, v52, a1, a2, *(_QWORD *)(a1 + 40), v60, v19, (__int64)&v79, 2);
      if ( v21 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_177;
        v28 = 85;
        goto LABEL_29;
      }
      v21 = OncRpcMapRpcStatusToNtStatus(v79);
      if ( v21 < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
          goto LABEL_177;
        v28 = 86;
LABEL_29:
        WPP_SF_d(v27->AttachedDevice, v28, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        goto LABEL_177;
      }
      v62 = XdrDecodeInt(v79);
      if ( *(int *)(v79 + 264) < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        v21 = *(_DWORD *)(v79 + 264);
        goto LABEL_177;
      }
      if ( v62 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 88, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        v21 = MapNFSStatusToNtStatus(v62);
        if ( v21 == -1073741816 )
        {
          if ( WPP_GLOBAL_Control != v63 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 89, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids, v12 + 64);
          HacOrphanStaleEntry(v59, v12);
        }
      }
      else
      {
        if ( v17 == 3 )
        {
          v65 = (unsigned __int8)XdrDecodeBool(v79);
        }
        else
        {
          v65 = 1;
          HacInvalidateAttributes(v12);
        }
        HacAcquireLock(v12, v64, v66);
        DeleteDirCache(v59, v12);
        KeReleaseMutex(*(PRKMUTEX *)(v12 + 40), 0);
        if ( v65 )
        {
          HacAcquireLock(v12, v67, v68);
          v69 = HacAllocate(v59, *(_QWORD *)(v87 + 72), (const UNICODE_STRING *)(v12 + 64), &v83);
          KeReleaseMutex(*(PRKMUTEX *)(v12 + 40), 0);
          if ( !v69 )
          {
            v25 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0 )
            {
              goto LABEL_23;
            }
            v26 = 90;
            goto LABEL_22;
          }
          LOBYTE(v70) = v17 == 3;
          LODWORD(v69[13].Buffer) = 32;
          v71 = 1;
          XdrDecodeNfsFileHandle(v79, &v69[13].Buffer, v70);
          if ( v17 != 3 || (v73 = XdrDecodeBool(v79), (v71 = v73) != 0) )
          {
            LOBYTE(v72) = v17 == 3;
            XdrDecodeNfsFileAttributes(v79, &v69[8], v72);
          }
          if ( *(int *)(v79 + 264) >= 0 && v71 )
          {
            HacUpdateTimeStamp(v69);
            HacInsertEntry(v59, (__int64)v69);
            v74 = a10;
            *a10 = (__int64)v69;
            v21 = 0;
LABEL_157:
            if ( v17 == 3 )
            {
              if ( (unsigned __int8)XdrDecodeBool(v79) )
                XdrDecodeSkipBytes(v79, 24);
              if ( (unsigned __int8)XdrDecodeBool(v79) )
              {
                HacAcquireLock(v12, v75, v76);
                LOBYTE(v77) = v17 == 3;
                XdrDecodeNfsFileAttributes(v79, v12 + 128, v77);
                KeReleaseMutex(*(PRKMUTEX *)(v12 + 40), 0);
                if ( *(int *)(v79 + 264) >= 0 )
                  HacUpdateTimeStamp(v12);
              }
            }
            if ( v21 >= 0 )
            {
              HacCaptureParentInfo(v59, *v74, v12);
              v21 = 0;
            }
            else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                   && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
            }
            goto LABEL_177;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
          }
          HacDereference(v59, v69);
          HacInvalidateAttributes(v12);
          v61 = a1;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        v21 = CaseInsensitiveLookup(v61, a2, a5, v12, a8, a10);
        if ( v21 < 0
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
        }
      }
      v74 = a10;
      goto LABEL_157;
    }
LABEL_37:
    Length = DestinationString.Length;
    v31 = 10;
    v32 = 13;
    goto LABEL_38;
  }
  v20 = 0;
  v21 = -1073741790;
LABEL_178:
  if ( v79 )
    OncRpcDestroy(v79);
  if ( v19 )
    OncRpcDestroy(v19);
  if ( v20 )
    ExFreePoolWithTag(v20, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x14000fbc0  mov     rax, rsp
0x14000fbc3  mov     [rax+18h], rbx
0x14000fbc7  mov     [rax+20h], r9
0x14000fbcb  mov     [rax+10h], rdx
0x14000fbcf  mov     [rax+8], rcx
0x14000fbd3  push    rbp
0x14000fbd4  push    rsi
0x14000fbd5  push    rdi
0x14000fbd6  push    r12
0x14000fbd8  push    r13
0x14000fbda  push    r14
0x14000fbdc  push    r15
0x14000fbde  lea     rbp, [rax-3Fh]
0x14000fbe2  sub     rsp, 0C0h
0x14000fbe9  mov     rbx, [rdx+50h]
0x14000fbed  mov     r12d, r8d
0x14000fbf0  xor     r8d, r8d
0x14000fbf3  mov     [rbp+37h+var_58], rbx
0x14000fbf7  mov     [rbp+37h+var_A0], r8
0x14000fbfb  mov     r15, r9
0x14000fbfe  mov     [rbp+37h+var_68], r8
0x14000fc02  mov     rdi, rcx
0x14000fc05  mov     [rbp+37h+var_60], r8
0x14000fc09  mov     [rbp+37h+var_98], r8
0x14000fc0d  mov     [rbp+37h+var_90], r8
0x14000fc11  mov     qword ptr [rbp+37h+SourceString.Length], r8
0x14000fc15  mov     [rbp+37h+SourceString.Buffer], r8
0x14000fc19  mov     qword ptr [rbp+37h+DestinationString.Length], r8
0x14000fc1d  mov     [rbp+37h+DestinationString.Buffer], r8
0x14000fc21  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fc28  lea     rax, WPP_GLOBAL_Control
0x14000fc2f  cmp     rcx, rax
0x14000fc32  jz      short loc_14000FC52
0x14000fc34  mov     eax, [rcx+2Ch]
0x14000fc37  test    al, 40h
0x14000fc39  jz      short loc_14000FC52
0x14000fc3b  mov     rcx, [rcx+18h]
0x14000fc3f  lea     edx, [r8+4Ah]
0x14000fc43  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000fc4a  call    WPP_SF_
0x14000fc4f  xor     r8d, r8d
0x14000fc52  mov     rax, [rbp+37h+arg_48]
0x14000fc59  mov     [rax], r8
0x14000fc5c  mov     rcx, [rdi+20h]
0x14000fc60  mov     rax, [rcx+20h]
0x14000fc64  mov     rdx, [rax+20h]
0x14000fc68  mov     rax, [rcx+28h]
0x14000fc6c  mov     [rbp+37h+var_48], rdx
0x14000fc70  mov     [rbp+37h+var_40], rax
0x14000fc74  mov     r13d, [rdx+58h]
0x14000fc78  cmp     r13d, 3
0x14000fc7c  setz    [rbp+37h+arg_30]
0x14000fc80  test    rax, rax
0x14000fc83  jz      loc_14001083F
0x14000fc89  test    rdx, rdx
0x14000fc8c  jz      loc_14001083F
0x14000fc92  mov     r14, [rdi+28h]
0x14000fc96  test    r14, r14
0x14000fc99  jz      loc_14001083F
0x14000fc9f  mov     rcx, r15
0x14000fca2  mov     [rbp+37h+P], r8
0x14000fca6  mov     rsi, r8
0x14000fca9  call    HacIsEntryFake
0x14000fcae  xor     ecx, ecx
0x14000fcb0  test    al, al
0x14000fcb2  jz      short loc_14000FCC7
0x14000fcb4  mov     edi, ecx
0x14000fcb6  lea     r14, WPP_GLOBAL_Control
0x14000fcbd  mov     ebx, 0C0000022h
0x14000fcc2  jmp     loc_1400107B7
0x14000fcc7  mov     rcx, [rbp+37h+arg_20]
0x14000fccb  lea     r8, [rbp+37h+var_68]
0x14000fccf  lea     rdx, [rbp+37h+var_98]
0x14000fcd3  call    MdaDissectNameTail
0x14000fcd8  mov     edx, 400h
0x14000fcdd  mov     ecx, 102h
0x14000fce2  mov     r8d, 3252664Eh
0x14000fce8  call    cs:__imp_ExAllocatePool2
0x14000fcef  nop     dword ptr [rax+rax+00h]
0x14000fcf4  mov     [rbp+37h+var_98], rax
0x14000fcf8  mov     rdi, rax
0x14000fcfb  test    rax, rax
0x14000fcfe  jnz     short loc_14000FD41
0x14000fd00  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fd07  lea     r14, WPP_GLOBAL_Control
0x14000fd0e  cmp     rcx, r14
0x14000fd11  jz      short loc_14000FD37
0x14000fd13  mov     eax, [rcx+2Ch]
0x14000fd16  mov     edi, 1
0x14000fd1b  test    dil, al
0x14000fd1e  jz      short loc_14000FD33
0x14000fd20  mov     rcx, [rcx+18h]
0x14000fd24  lea     edx, [rdi+4Ah]
0x14000fd27  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000fd2e  call    WPP_SF_
0x14000fd33  mov     rdi, [rbp+37h+var_98]
0x14000fd37  mov     ebx, 0C000009Ah
0x14000fd3c  jmp     loc_1400107B7
0x14000fd41  add     rax, 200h
0x14000fd47  mov     dword ptr [rbp+37h+SourceString.Length], 1000000h
0x14000fd4e  mov     [rbp+37h+SourceString.Buffer], rax
0x14000fd52  lea     r8, [rbp+37h+var_68]
0x14000fd56  mov     eax, [r14+20h]
0x14000fd5a  lea     rdx, [rbp+37h+SourceString]
0x14000fd5e  mov     rcx, rbx
0x14000fd61  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14000fd65  call    NfsConvertUnicodeToAnsi
0x14000fd6a  mov     ebx, eax
0x14000fd6c  mov     edi, 1
0x14000fd71  cmp     r12d, 5
0x14000fd75  jnz     loc_14000FE1E
0x14000fd7b  mov     rbx, [rbp+37h+arg_40]
0x14000fd82  test    rbx, rbx
0x14000fd85  jz      loc_14000FE62
0x14000fd8b  movzx   eax, word ptr [rbx]
0x14000fd8e  test    ax, ax
0x14000fd91  jz      loc_14000FE62
0x14000fd97  shr     ax, 1
0x14000fd9a  mov     ecx, 102h
0x14000fd9f  add     ax, di
0x14000fda2  mov     r8d, 3252664Eh
0x14000fda8  movzx   edx, ax
0x14000fdab  mov     [rbp+37h+DestinationString.Length], dx
0x14000fdaf  mov     [rbp+37h+DestinationString.MaximumLength], dx
0x14000fdb3  call    cs:__imp_ExAllocatePool2
0x14000fdba  nop     dword ptr [rax+rax+00h]
0x14000fdbf  mov     [rbp+37h+P], rax
0x14000fdc3  test    rax, rax
0x14000fdc6  jnz     short loc_14000FE00
0x14000fdc8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fdcf  lea     r14, WPP_GLOBAL_Control
0x14000fdd6  cmp     rcx, r14
0x14000fdd9  jz      short loc_14000FDF6
0x14000fddb  mov     eax, [rcx+2Ch]
0x14000fdde  test    dil, al
0x14000fde1  jz      short loc_14000FDF6
0x14000fde3  lea     edx, [rdi+4Bh]
0x14000fde6  mov     rcx, [rcx+18h]
0x14000fdea  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000fdf1  call    WPP_SF_
0x14000fdf6  mov     ebx, 0C000009Ah
0x14000fdfb  jmp     loc_1400107B3
0x14000fe00  mov     rcx, [rbp+37h+var_58]
0x14000fe04  lea     rdx, [rbp+37h+DestinationString]
0x14000fe08  mov     [rbp+37h+DestinationString.Buffer], rax
0x14000fe0c  mov     r8, rbx
0x14000fe0f  mov     eax, [r14+20h]
0x14000fe13  mov     dword ptr [rsp+0F0h+var_D0], eax
0x14000fe17  call    NfsConvertUnicodeToAnsi
0x14000fe1c  mov     ebx, eax
0x14000fe1e  test    ebx, ebx
0x14000fe20  jns     short loc_14000FE9C
0x14000fe22  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe29  lea     r14, WPP_GLOBAL_Control
0x14000fe30  cmp     rcx, r14
0x14000fe33  jz      loc_1400107B3
0x14000fe39  mov     eax, [rcx+2Ch]
0x14000fe3c  test    dil, al
0x14000fe3f  jz      loc_1400107B3
0x14000fe45  mov     edx, 4Eh ; 'N'
0x14000fe4a  mov     rcx, [rcx+18h]
0x14000fe4e  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000fe55  mov     r9d, ebx
0x14000fe58  call    WPP_SF_d
0x14000fe5d  jmp     loc_1400107B3
0x14000fe62  mov     rcx, cs:WPP_GLOBAL_Control
0x14000fe69  lea     r14, WPP_GLOBAL_Control
0x14000fe70  cmp     rcx, r14
0x14000fe73  jz      short loc_14000FE92
0x14000fe75  mov     eax, [rcx+2Ch]
0x14000fe78  test    dil, al
0x14000fe7b  jz      short loc_14000FE92
0x14000fe7d  mov     rcx, [rcx+18h]
0x14000fe81  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000fe88  mov     edx, 4Dh ; 'M'
0x14000fe8d  call    WPP_SF_
0x14000fe92  mov     ebx, 0C000000Dh
0x14000fe97  jmp     loc_1400107B3
0x14000fe9c  mov     eax, [r14+20h]
0x14000fea0  test    al, 40h
0x14000fea2  jz      short loc_14000FEE0
0x14000fea4  lea     rdx, [rbp+37h+SourceString]; DestinationString
0x14000fea8  lea     rcx, [rbp+37h+SourceString]; SourceString
0x14000feac  call    DsSjisToEuc
0x14000feb1  cmp     r12d, 5
0x14000feb5  jnz     loc_14001009E
0x14000febb  lea     rdx, [rbp+37h+DestinationString]; DestinationString
0x14000febf  lea     rcx, [rbp+37h+DestinationString]; SourceString
0x14000fec3  call    DsSjisToEuc
0x14000fec8  movzx   esi, [rbp+37h+DestinationString.Length]
0x14000fecc  mov     ebx, 0Ah
0x14000fed1  lea     eax, [rbx+3]
0x14000fed4  cmp     r13d, 3
0x14000fed8  cmovnz  ebx, eax
0x14000fedb  jmp     loc_140010107
0x14000fee0  bt      eax, 0Eh
0x14000fee4  jnb     loc_140010065
0x14000feea  xor     r14d, r14d
0x14000feed  cmp     r14w, [rbp+37h+SourceString.Length]
0x14000fef2  jz      loc_14000FF96
0x14000fef8  mov     r8, [rbp+37h+SourceString.Buffer]
0x14000fefc  test    r8, r8
0x14000feff  jz      loc_14000FF96
0x14000ff05  movzx   esi, [rbp+37h+SourceString.Length]
0x14000ff09  mov     ecx, r14d
0x14000ff0c  dec     esi
0x14000ff0e  test    esi, esi
0x14000ff10  jle     loc_14000FF96
0x14000ff16  mov     r15, 3FFFFFF03FFFFFFh
0x14000ff20  movzx   r11d, cx
0x14000ff24  mov     r10b, [r11+r8]
0x14000ff28  lea     ebx, [r10+7Fh]
0x14000ff2c  cmp     bl, 1Fh
0x14000ff2f  ja      short loc_14000FF5B
0x14000ff31  mov     dl, [r11+r8+1]
0x14000ff36  lea     eax, [rdx-41h]
0x14000ff39  cmp     al, 39h ; '9'
0x14000ff3b  ja      short loc_14000FF43
0x14000ff3d  bt      r15, rax
0x14000ff41  jb      short loc_14000FF52
0x14000ff43  lea     eax, [rdx+7Fh]
0x14000ff46  cmp     al, 1Fh
0x14000ff48  jbe     short loc_14000FF52
0x14000ff4a  add     dl, 5Fh ; '_'
0x14000ff4d  cmp     dl, 5Dh ; ']'
0x14000ff50  ja      short loc_14000FF5B
0x14000ff52  mov     word ptr [r11+r8], 3F3Fh
0x14000ff59  jmp     short loc_14000FF85
0x14000ff5b  add     r10b, 5Fh ; '_'
0x14000ff5f  cmp     r10b, 5Dh ; ']'
0x14000ff63  ja      short loc_14000FF80
0x14000ff65  mov     dl, [r11+r8+1]
0x14000ff6a  lea     eax, [rdx-41h]
0x14000ff6d  cmp     al, 19h
0x14000ff6f  jbe     short loc_14000FF52
0x14000ff71  lea     eax, [rdx-61h]
0x14000ff74  cmp     al, 19h
0x14000ff76  jbe     short loc_14000FF52
0x14000ff78  add     dl, 7Fh
0x14000ff7b  cmp     dl, 1Fh
0x14000ff7e  jbe     short loc_14000FF52
0x14000ff80  cmp     bl, 7Dh ; '}'
0x14000ff83  ja      short loc_14000FF88
0x14000ff85  add     cx, di
0x14000ff88  add     cx, di
0x14000ff8b  movzx   eax, cx
0x14000ff8e  cmp     eax, esi
0x14000ff90  jl      short loc_14000FF20
0x14000ff92  mov     r15, [rbp+37h+arg_18]
0x14000ff96  cmp     r12d, 5
0x14000ff9a  jnz     loc_1400100A1
0x14000ffa0  cmp     r14w, [rbp+37h+DestinationString.Length]
0x14000ffa5  jz      loc_1400100A1
0x14000ffab  mov     r8, [rbp+37h+DestinationString.Buffer]
0x14000ffaf  test    r8, r8
0x14000ffb2  jz      loc_1400100A1
0x14000ffb8  movzx   ebx, [rbp+37h+DestinationString.Length]
0x14000ffbc  mov     ecx, r14d
0x14000ffbf  dec     ebx
0x14000ffc1  test    ebx, ebx
0x14000ffc3  jle     loc_1400100A1
0x14000ffc9  mov     r15, 3FFFFFF03FFFFFFh
0x14000ffd3  movzx   r10d, cx
0x14000ffd7  mov     r9b, [r8+r10]
0x14000ffdb  lea     eax, [r9+7Fh]
0x14000ffdf  cmp     al, 1Fh
0x14000ffe1  ja      short loc_14001000D
0x14000ffe3  mov     dl, [r8+r10+1]
0x14000ffe8  lea     eax, [rdx-41h]
0x14000ffeb  cmp     al, 39h ; '9'
0x14000ffed  ja      short loc_14000FFF5
0x14000ffef  bt      r15, rax
0x14000fff3  jb      short loc_140010004
0x14000fff5  lea     eax, [rdx+7Fh]
0x14000fff8  cmp     al, 1Fh
0x14000fffa  jbe     short loc_140010004
0x14000fffc  add     dl, 5Fh ; '_'
0x14000ffff  cmp     dl, 5Dh ; ']'
0x140010002  ja      short loc_14001000D
0x140010004  mov     word ptr [r8+r10], 3F3Fh
0x14001000b  jmp     short loc_14001004B
0x14001000d  lea     eax, [r9+5Fh]
0x140010011  cmp     al, 5Dh ; ']'
0x140010013  ja      short loc_140010041
0x140010015  movzx   r11d, cx
0x140010019  mov     dl, [r11+r8+1]
0x14001001e  lea     eax, [rdx-41h]
0x140010021  cmp     al, 19h
0x140010023  jbe     short loc_140010034
0x140010025  lea     eax, [rdx-61h]
0x140010028  cmp     al, 19h
0x14001002a  jbe     short loc_140010034
0x14001002c  add     dl, 7Fh
0x14001002f  cmp     dl, 1Fh
0x140010032  ja      short loc_140010041
0x140010034  mov     byte ptr [r11+r8+1], 3Fh ; '?'
0x14001003a  mov     byte ptr [r8+r10], 3Fh ; '?'
0x14001003f  jmp     short loc_14001004B
0x140010041  add     r9b, 7Fh
0x140010045  cmp     r9b, 7Dh ; '}'
  ... truncated ...
```
