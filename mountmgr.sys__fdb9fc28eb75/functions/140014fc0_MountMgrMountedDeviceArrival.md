# MountMgrMountedDeviceArrival

- ea: `0x140014fc0`
- end: `0x140015d42`
- name: `MountMgrMountedDeviceArrival`
- size: `3458`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `24`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x14000d9a0`
- `0x1400147a0`
- `0x140019980`

## callees

- `0x140001ae0`
- `0x140001b30`
- `0x140002400`
- `0x14000a510`
- `0x14000a640`
- `0x14000acd8`
- `0x14000b4a0`
- `0x14000c954`
- `0x14000ff00`
- `0x1400144a0`
- `0x140014fc0`
- `0x140017540`
- `0x140017a20`
- `0x140018890`
- `0x140018cd0`
- `0x140018da0`
- `0x140019140`
- `0x1400192f0`
- `0x1400195d0`
- `0x1400198b0`
- `0x140019ca0`
- `0x140019d90`
- `0x14001a2b0`
- `0x14001a790`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x1400151fa`
- `ntoskrnl!RtlCompareUnicodeString` at `0x1400151fa`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140015966`
- `ntoskrnl!RtlWriteRegistryValue` at `0x140015966`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015146`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015668`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015146`
- `ntoskrnl!RtlEqualUnicodeString` at `0x140015668`
- `ntoskrnl!ObIsDosDeviceLocallyMapped` at `0x140015543`
- `ntoskrnl!ObIsDosDeviceLocallyMapped` at `0x140015543`
- `ntoskrnl!KeReleaseMutex` at `0x14001517e`
- `ntoskrnl!KeReleaseMutex` at `0x140015298`
- `ntoskrnl!KeReleaseMutex` at `0x140015c29`
- `ntoskrnl!KeReleaseMutex` at `0x140015d19`
- `ntoskrnl!KeReleaseMutex` at `0x14001517e`
- `ntoskrnl!KeReleaseMutex` at `0x140015298`
- `ntoskrnl!KeReleaseMutex` at `0x140015c29`
- `ntoskrnl!KeReleaseMutex` at `0x140015d19`
- `ntoskrnl!KeSetEvent` at `0x140015b15`
- `ntoskrnl!KeSetEvent` at `0x140015b15`
- `ntoskrnl!ExAllocatePool2` at `0x140015013`
- `ntoskrnl!ExAllocatePool2` at `0x1400157bd`
- `ntoskrnl!ExAllocatePool2` at `0x140015990`
- `ntoskrnl!ExAllocatePool2` at `0x140015013`
- `ntoskrnl!ExAllocatePool2` at `0x1400157bd`
- `ntoskrnl!ExAllocatePool2` at `0x140015990`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001509d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400156b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015724`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400157df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400159dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c7f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001509d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152aa`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152bc`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400152df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400154be`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400156b8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015724`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400157df`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400159dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x140015c7f`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015122`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400151d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015cd8`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015122`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400151d6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140015cd8`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140015086`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x140015086`

## string_xrefs

- `0x140015940`: `\Registry\Machine\System\MountedDevices`

## pseudocode

```c
__int64 __fastcall MountMgrMountedDeviceArrival(__int64 a1, const UNICODE_STRING *a2, char a3)
{
  __int64 Pool2; // rax
  UNICODE_STRING *v7; // rbx
  unsigned int DeviceInformation; // esi
  _QWORD *v9; // rdi
  struct _UNICODE_STRING *v10; // r8
  _QWORD *v11; // rax
  __int64 v12; // r8
  void *v13; // rcx
  UNICODE_STRING *v14; // r14
  UNICODE_STRING *v15; // rdi
  UNICODE_STRING **v16; // rax
  __int64 v17; // r8
  __int64 v18; // rcx
  const UNICODE_STRING *v19; // r14
  int v20; // eax
  __int64 v21; // r8
  unsigned int IsDosDeviceLocallyMapped; // r12d
  unsigned int v23; // r13d
  __int64 v24; // r8
  __int64 v25; // r14
  struct _KMUTANT *v26; // rax
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // r8
  unsigned int v29; // ebp
  UNICODE_STRING *v30; // r14
  PWSTR Buffer; // rax
  WCHAR v32; // cx
  __int64 v33; // rcx
  __int64 v34; // rdx
  __int64 v35; // r8
  int v36; // edx
  int v37; // r8d
  __int64 v38; // r8
  __int64 v39; // r8
  bool v40; // si
  __int64 v41; // r8
  __int64 v42; // rdx
  __int64 v43; // r8
  __int64 v44; // r8
  __int64 v45; // rax
  _QWORD *v46; // rsi
  UNICODE_STRING v47; // xmm0
  _QWORD *v48; // rax
  _QWORD *v49; // rsi
  __int64 v50; // rax
  __int128 v51; // xmm0
  __int64 *v52; // rcx
  char v53; // cl
  UNICODE_STRING **v54; // r9
  UNICODE_STRING **v55; // rsi
  __int64 i; // rax
  unsigned int v57; // edx
  UNICODE_STRING *v58; // rax
  int v59; // eax
  unsigned __int8 v60; // di
  PDEVICE_OBJECT v61; // rcx
  __int64 v62; // rdx
  __int64 v63; // r8
  UNICODE_STRING *j; // rbx
  char v66; // [rsp+30h] [rbp-78h] BYREF
  char v67; // [rsp+31h] [rbp-77h]
  char v68; // [rsp+32h] [rbp-76h]
  PRKMUTEX Mutex; // [rsp+38h] [rbp-70h]
  PVOID P; // [rsp+40h] [rbp-68h] BYREF
  PCWSTR ValueName[2]; // [rsp+48h] [rbp-60h] BYREF
  UNICODE_STRING String2; // [rsp+58h] [rbp-50h] BYREF
  unsigned int v75; // [rsp+C8h] [rbp+20h] BYREF

  P = 0;
  v75 = 0;
  v66 = 0;
  String2 = 0;
  *(_OWORD *)ValueName = 0;
  Pool2 = ExAllocatePool2(256, 184, 1098149453);
  v7 = (UNICODE_STRING *)Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 170);
    return (unsigned int)-1073741670;
  }
  v9 = (_QWORD *)(Pool2 + 16);
  *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
  v10 = (struct _UNICODE_STRING *)(Pool2 + 64);
  *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
  v11 = (_QWORD *)(Pool2 + 32);
  v11[1] = v11;
  *v11 = v11;
  v7[3].Buffer = &v7[3].Length;
  *(_QWORD *)&v7[3].Length = v7 + 3;
  DeviceInformation = RtlDuplicateUnicodeString(1u, a2, v10);
  if ( (DeviceInformation & 0x80000000) != 0 )
  {
    ExFreePoolWithTag(v7, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 171, v12, DeviceInformation);
    return DeviceInformation;
  }
  HIBYTE(v7[8].Length) = a3;
  v7[9].Buffer = (PWSTR)a1;
  Mutex = (PRKMUTEX)(a1 + 56);
  DeviceInformation = QueryDeviceInformation(a2, v7);
  v13 = (void *)(a1 + 56);
  if ( (DeviceInformation & 0x80000000) == 0 )
  {
    KeWaitForSingleObject(v13, Executive, 0, 0, 0);
    v19 = *(const UNICODE_STRING **)(a1 + 16);
    if ( v19 != (const UNICODE_STRING *)(a1 + 16) )
    {
      while ( RtlCompareUnicodeString(v19 + 5, v7 + 5, 1u) )
      {
        v19 = *(const UNICODE_STRING **)&v19->Length;
        if ( v19 == (const UNICODE_STRING *)(a1 + 16) )
          goto LABEL_24;
      }
      KeReleaseMutex(Mutex, 0);
      ExFreePoolWithTag(*(PVOID *)&v7[6].Length, 0);
      ExFreePoolWithTag(v7[5].Buffer, 0);
      ExFreePoolWithTag(v7[4].Buffer, 0);
      ExFreePoolWithTag(v7, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 173, v24, DeviceInformation);
      }
      return 0;
    }
LABEL_24:
    *(_QWORD *)&v7[11].Length = ++*(_QWORD *)(a1 + 336);
    v20 = QuerySymbolicLinkNamesFromStorage(v18, v7, &P, &v75);
    IsDosDeviceLocallyMapped = v20;
    if ( v20 >= 0 )
    {
      v23 = v75;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 174, v21, (unsigned int)v20);
      }
      v23 = 0;
      P = 0;
      IsDosDeviceLocallyMapped = 0;
    }
    v25 = a1;
    v26 = (struct _KMUTANT *)RemoveSavedLinks(a1, *(_QWORD *)&v7[6].Length);
    v29 = 0;
    Mutex = v26;
    LOBYTE(v75) = 0;
    v68 = 0;
    v67 = 0;
    if ( v23 )
    {
      while ( 1 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 175, v28, 0);
        }
        v30 = (UNICODE_STRING *)((char *)P + 16 * v29);
        if ( (v30->Length == 96 || v30->Length == 98 && v30->Buffer[48] == 92)
          && (Buffer = v30->Buffer, *Buffer == 92)
          && ((v32 = Buffer[1], v32 == 63) || v32 == 92)
          && Buffer[2] == 63
          && Buffer[3] == 92
          && Buffer[4] == 86
          && Buffer[5] == 111
          && Buffer[6] == 108
          && Buffer[7] == 117
          && Buffer[8] == 109
          && Buffer[9] == 101
          && Buffer[10] == 123
          && Buffer[19] == 45
          && Buffer[24] == 45
          && Buffer[29] == 45
          && Buffer[34] == 45
          && Buffer[47] == 125 )
        {
          v67 = 1;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 176, v28, IsDosDeviceLocallyMapped);
          }
        }
        else if ( (unsigned __int8)IsDriveLetter((PCUNICODE_STRING)P + v29) )
        {
          if ( BYTE6(v7[7].Buffer) )
            goto LABEL_66;
          if ( (_BYTE)v75 )
          {
            DeleteFromLocalDatabase(v30, *(_QWORD *)&v7[6].Length);
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 177, v28, IsDosDeviceLocallyMapped);
            }
            goto LABEL_120;
          }
          v33 = (unsigned int)v30->Buffer[12] - 64;
          v66 = 0;
          IsDosDeviceLocallyMapped = ObIsDosDeviceLocallyMapped(v33, &v66);
          if ( (IsDosDeviceLocallyMapped & 0x80000000) == 0 )
          {
            if ( v66 )
            {
LABEL_66:
              ExFreePoolWithTag(v30->Buffer, 0);
              v30->Buffer = 0;
              v30->Length = 0;
              goto LABEL_120;
            }
          }
          else
          {
            v66 = 0;
            LOBYTE(IsDosDeviceLocallyMapped) = 0;
          }
          MountmgrSetDLStringCase(v30, v34, v35);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_SL(WPP_GLOBAL_Control->AttachedDevice, v36, v37, v30->Buffer, IsDosDeviceLocallyMapped);
          }
          LOBYTE(v75) = 1;
        }
        IsDosDeviceLocallyMapped = GlobalCreateSymbolicLink(v30, (__int128 *)&v7[5]);
        if ( (IsDosDeviceLocallyMapped & 0x80000000) == 0 )
          goto LABEL_105;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 179, v38, IsDosDeviceLocallyMapped);
        if ( Mutex && (unsigned __int8)RedirectSavedLink(Mutex, v30, &v7[5]) )
        {
LABEL_105:
          if ( (unsigned __int8)IsOffline(v30) )
          {
            v68 = 1;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 184, v44, IsDosDeviceLocallyMapped);
            }
          }
          v45 = ExAllocatePool2(258, 40, 1098149453);
          v46 = (_QWORD *)v45;
          if ( v45 )
          {
            v47 = *v30;
            *(_BYTE *)(v45 + 16) = 1;
            *(UNICODE_STRING *)(v45 + 24) = v47;
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 186, v28, IsDosDeviceLocallyMapped);
            }
            v48 = (_QWORD *)v9[1];
            if ( (_QWORD *)*v48 != v9 )
              goto LABEL_166;
            *v46 = v9;
            v46[1] = v48;
            *v48 = v46;
            v9[1] = v46;
          }
          else
          {
            GlobalDeleteSymbolicLink(v30);
            ExFreePoolWithTag(v30->Buffer, 0);
            v27 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 185);
            }
          }
          goto LABEL_120;
        }
        IsDosDeviceLocallyMapped = QueryDeviceName(v30, &String2);
        if ( (IsDosDeviceLocallyMapped & 0x80000000) == 0 )
        {
          v40 = RtlEqualUnicodeString(v7 + 5, &String2, 1u) != 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 181, v41, IsDosDeviceLocallyMapped);
          }
          ExFreePoolWithTag(String2.Buffer, 0);
          if ( v40 )
            goto LABEL_105;
        }
        else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 180, v39, IsDosDeviceLocallyMapped);
        }
        if ( (unsigned __int8)IsDriveLetter(v30) )
        {
          v42 = *(_QWORD *)&v7[6].Length;
          LOBYTE(v75) = 0;
          DeleteFromLocalDatabase(v30, v42);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 182, v43, IsDosDeviceLocallyMapped);
          }
        }
        ExFreePoolWithTag(v30->Buffer, 0);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 183, v28, IsDosDeviceLocallyMapped);
        }
LABEL_120:
        if ( ++v29 >= v23 )
        {
          v25 = a1;
          v26 = Mutex;
          break;
        }
      }
    }
    v49 = (_QWORD *)*v9;
    if ( (_QWORD *)*v9 != v9 )
    {
      do
      {
        SendLinkCreated(v27, v49 + 3);
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 187, v28, IsDosDeviceLocallyMapped);
        }
        v49 = (_QWORD *)*v49;
      }
      while ( v49 != v9 );
      v26 = Mutex;
    }
    if ( v26 )
      MountMgrFreeSavedLink(v26);
    if ( !v67 )
    {
      IsDosDeviceLocallyMapped = CreateNewVolumeName((PUNICODE_STRING)ValueName);
      if ( (IsDosDeviceLocallyMapped & 0x80000000) == 0 )
      {
        RtlWriteRegistryValue(
          0,
          L"\\Registry\\Machine\\System\\MountedDevices",
          ValueName[1],
          3u,
          (PVOID)(*(_QWORD *)&v7[6].Length + 2LL),
          **(unsigned __int16 **)&v7[6].Length);
        GlobalCreateSymbolicLink((const UNICODE_STRING *)ValueName, (__int128 *)&v7[5]);
        v50 = ExAllocatePool2(258, 40, 1098149453);
        if ( v50 )
        {
          v51 = *(_OWORD *)ValueName;
          *(_BYTE *)(v50 + 16) = 1;
          *(_OWORD *)(v50 + 24) = v51;
          v52 = (__int64 *)v9[1];
          if ( (_QWORD *)*v52 != v9 )
            goto LABEL_166;
          *(_QWORD *)v50 = v9;
          *(_QWORD *)(v50 + 8) = v52;
          *v52 = v50;
          v9[1] = v50;
          SendLinkCreated(v52, ValueName);
        }
        else
        {
          ExFreePoolWithTag((PVOID)ValueName[1], 0);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 189);
          }
        }
      }
      else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
             && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 188, v28, IsDosDeviceLocallyMapped);
      }
    }
    v53 = v75;
    if ( (_BYTE)v75 )
    {
      LOBYTE(v7[8].Length) = 0;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 190, v28, IsDosDeviceLocallyMapped);
      }
    }
    else
    {
      if ( ((__int64)v7[7].Buffer & 0x100) != 0 )
        goto LABEL_153;
      if ( !*(_BYTE *)(v25 + 192) && !BYTE4(v7[7].Buffer) || !*(_BYTE *)(v25 + 144) || HIBYTE(v7[7].Buffer) )
      {
LABEL_155:
        if ( !a3 )
        {
          RegisterForTargetDeviceNotification(v25, v7);
          v53 = v75;
        }
        v54 = *(UNICODE_STRING ***)(v25 + 24);
        v55 = (UNICODE_STRING **)(v25 + 16);
        if ( v54 != (UNICODE_STRING **)(v25 + 16) )
        {
LABEL_158:
          for ( i = 0; (unsigned int)i < 4; i = (unsigned int)(i + 1) )
          {
            v57 = *((_DWORD *)&v7[10].Length + i);
            if ( v57 < *((_DWORD *)v54 + i + 40) )
            {
              v54 = (UNICODE_STRING **)v54[1];
              if ( v54 != v55 )
                goto LABEL_158;
              break;
            }
            if ( v57 > *((_DWORD *)v54 + i + 40) )
              break;
          }
          v53 = v75;
        }
        v58 = *v54;
        if ( (UNICODE_STRING **)(*v54)->Buffer != v54 )
          goto LABEL_166;
        *(_QWORD *)&v7->Length = v58;
        v7->Buffer = (PWSTR)v54;
        v58->Buffer = &v7->Length;
        *v54 = v7;
        v59 = (int)v7[7].Buffer;
        if ( (v59 & 0x100) != 0 )
        {
          KeSetEvent((PRKEVENT)(v25 + 344), 0, 0);
          v60 = 1;
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_194;
          }
          v62 = 191;
        }
        else if ( (v59 & 0x200000) != 0 )
        {
          v60 = 1;
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_194;
          }
          v62 = 192;
        }
        else if ( v68 )
        {
          *((_BYTE *)&v7[8].MaximumLength + 3) = 1;
          v60 = 0;
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_194;
          }
          v62 = 193;
        }
        else if ( *(_BYTE *)(v25 + 192) || BYTE4(v7[7].Buffer) || v53 )
        {
          v60 = 1;
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_194;
          }
          v62 = 194;
        }
        else
        {
          v60 = 0;
          v61 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
            || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
          {
            goto LABEL_194;
          }
          v62 = 195;
        }
        WPP_SF_L(v61->AttachedDevice, v62, v28, 0);
LABEL_194:
        KeReleaseMutex((PRKMUTEX)(v25 + 56), 0);
        SendOnlineNotification(a2, v60);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 196, v63, 0);
        }
        if ( P )
          ExFreePoolWithTag(P, 0);
        if ( *(_BYTE *)(v25 + 144) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 197, v63, 0);
          }
          KeWaitForSingleObject((PVOID)(v25 + 56), Executive, 0, 0, 0);
          ReconcileThisDatabaseWithMaster((PVOID)v25);
          for ( j = *v55; j != (UNICODE_STRING *)v55; j = *(UNICODE_STRING **)&j->Length )
          {
            if ( *((_BYTE *)&j[8].MaximumLength + 2) )
              ReconcileThisDatabaseWithMaster((PVOID)v25);
          }
          KeReleaseMutex((PRKMUTEX)(v25 + 56), 0);
        }
        return 0;
      }
      if ( !(unsigned __int8)HasNoDriveLetterEntry(*(_QWORD *)&v7[6].Length) )
LABEL_153:
        CreateNewDriveLetterName(v7);
    }
    v53 = v75;
    goto LABEL_155;
  }
  KeWaitForSingleObject(v13, Executive, 0, 0, 0);
  v14 = *(UNICODE_STRING **)(a1 + 32);
  v15 = (UNICODE_STRING *)(a1 + 32);
  if ( v14 != (UNICODE_STRING *)(a1 + 32) )
  {
    while ( !RtlEqualUnicodeString(v7 + 4, v14 + 4, 1u) )
    {
      v14 = *(UNICODE_STRING **)&v14->Length;
      if ( v14 == v15 )
        goto LABEL_14;
    }
    MountMgrFreeDeadDeviceInfo(v7);
    goto LABEL_16;
  }
LABEL_14:
  v16 = *(UNICODE_STRING ***)(a1 + 40);
  if ( *v16 != v15 )
LABEL_166:
    __fastfail(3u);
  *(_QWORD *)&v7->Length = v15;
  v7->Buffer = (PWSTR)v16;
  *v16 = v7;
  *(_QWORD *)(a1 + 40) = v7;
LABEL_16:
  KeReleaseMutex((PRKMUTEX)(a1 + 56), 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_L(WPP_GLOBAL_Control->AttachedDevice, 172, v17, DeviceInformation);
  }
  return DeviceInformation;
}

```

## disassembly

```asm
0x140014fc0  mov     r11, rsp
0x140014fc3  mov     [r11+18h], rbx
0x140014fc7  mov     [r11+10h], rdx
0x140014fcb  mov     [r11+8], rcx
0x140014fcf  push    rbp
0x140014fd0  push    rsi
0x140014fd1  push    rdi
0x140014fd2  push    r12
0x140014fd4  push    r13
0x140014fd6  push    r14
0x140014fd8  push    r15
0x140014fda  sub     rsp, 70h
0x140014fde  xor     eax, eax
0x140014fe0  xorps   xmm0, xmm0
0x140014fe3  movzx   r15d, r8b
0x140014fe7  mov     [r11-68h], rax
0x140014feb  mov     r14, rdx
0x140014fee  mov     [r11+20h], eax
0x140014ff2  mov     r13, rcx
0x140014ff5  mov     [rsp+0A8h+var_78], al
0x140014ff9  mov     edx, 0B8h
0x140014ffe  mov     ecx, 100h
0x140015003  mov     r8d, 41746E4Dh
0x140015009  movups  xmmword ptr [rsp+0A8h+String2.Length], xmm0
0x14001500e  movups  xmmword ptr [rsp+0A8h+ValueName], xmm0
0x140015013  call    cs:__imp_ExAllocatePool2
0x14001501a  nop     dword ptr [rax+rax+00h]
0x14001501f  mov     rbx, rax
0x140015022  test    rax, rax
0x140015025  jnz     short loc_140015059
0x140015027  mov     rcx, cs:WPP_GLOBAL_Control
0x14001502e  lea     rax, WPP_GLOBAL_Control
0x140015035  cmp     rcx, rax
0x140015038  jz      short loc_14001504F
0x14001503a  mov     eax, [rcx+2Ch]
0x14001503d  test    al, 4
0x14001503f  jz      short loc_14001504F
0x140015041  mov     rcx, [rcx+18h]
0x140015045  mov     edx, 0AAh
0x14001504a  call    WPP_SF_
0x14001504f  mov     esi, 0C000009Ah
0x140015054  jmp     loc_140015D27
0x140015059  lea     rdi, [rax+10h]
0x14001505d  mov     rdx, r14; StringIn
0x140015060  mov     [rdi+8], rdi
0x140015064  lea     r8, [rbx+40h]; StringOut
0x140015068  mov     [rdi], rdi
0x14001506b  add     rax, 20h ; ' '
0x14001506f  mov     ecx, 1; Flags
0x140015074  mov     [rax+8], rax
0x140015078  mov     [rax], rax
0x14001507b  lea     rax, [rbx+30h]
0x14001507f  mov     [rax+8], rax
0x140015083  mov     [rax], rax
0x140015086  call    cs:__imp_RtlDuplicateUnicodeString
0x14001508d  nop     dword ptr [rax+rax+00h]
0x140015092  mov     esi, eax
0x140015094  test    eax, eax
0x140015096  jns     short loc_1400150E2
0x140015098  xor     edx, edx; Tag
0x14001509a  mov     rcx, rbx; P
0x14001509d  call    cs:__imp_ExFreePoolWithTag
0x1400150a4  nop     dword ptr [rax+rax+00h]
0x1400150a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400150b0  lea     rax, WPP_GLOBAL_Control
0x1400150b7  cmp     rcx, rax
0x1400150ba  jz      loc_140015D27
0x1400150c0  mov     edx, [rcx+2Ch]
0x1400150c3  test    dl, 1
0x1400150c6  jz      loc_140015D27
0x1400150cc  mov     rcx, [rcx+18h]
0x1400150d0  mov     edx, 0ABh
0x1400150d5  mov     r9d, esi
0x1400150d8  call    WPP_SF_L
0x1400150dd  jmp     loc_140015D27
0x1400150e2  mov     rdx, rbx
0x1400150e5  mov     [rbx+81h], r15b
0x1400150ec  mov     rcx, r14
0x1400150ef  mov     [rbx+98h], r13
0x1400150f6  call    QueryDeviceInformation
0x1400150fb  lea     r12, [r13+38h]
0x1400150ff  mov     [rsp+0A8h+Timeout], 0; Timeout
0x140015108  xor     r9d, r9d; Alertable
0x14001510b  mov     [rsp+0A8h+Mutex], r12
0x140015110  xor     r8d, r8d; WaitMode
0x140015113  xor     edx, edx; WaitReason
0x140015115  mov     esi, eax
0x140015117  mov     rcx, r12; Object
0x14001511a  test    eax, eax
0x14001511c  jns     loc_1400151D6
0x140015122  call    cs:__imp_KeWaitForSingleObject
0x140015129  nop     dword ptr [rax+rax+00h]
0x14001512e  mov     r14, [r13+20h]
0x140015132  lea     rdi, [r13+20h]
0x140015136  cmp     r14, rdi
0x140015139  jz      short loc_14001515E
0x14001513b  lea     rdx, [r14+40h]; String2
0x14001513f  mov     r8b, 1; CaseInSensitive
0x140015142  lea     rcx, [rbx+40h]; String1
0x140015146  call    cs:__imp_RtlEqualUnicodeString
0x14001514d  nop     dword ptr [rax+rax+00h]
0x140015152  test    al, al
0x140015154  jnz     short loc_1400151CC
0x140015156  mov     r14, [r14]
0x140015159  cmp     r14, rdi
0x14001515c  jnz     short loc_14001513B
0x14001515e  mov     rax, [rdi+8]
0x140015162  cmp     [rax], rdi
0x140015165  jnz     loc_140015AEB
0x14001516b  mov     [rbx], rdi
0x14001516e  mov     [rbx+8], rax
0x140015172  mov     [rax], rbx
0x140015175  mov     [rdi+8], rbx
0x140015179  xor     edx, edx; Wait
0x14001517b  mov     rcx, r12; Mutex
0x14001517e  call    cs:__imp_KeReleaseMutex
0x140015185  nop     dword ptr [rax+rax+00h]
0x14001518a  mov     rcx, cs:WPP_GLOBAL_Control
0x140015191  lea     rax, WPP_GLOBAL_Control
0x140015198  cmp     rcx, rax
0x14001519b  jz      loc_140015D27
0x1400151a1  mov     eax, [rcx+2Ch]
0x1400151a4  test    al, 1
0x1400151a6  jz      loc_140015D27
0x1400151ac  cmp     byte ptr [rcx+29h], 1
0x1400151b0  jb      loc_140015D27
0x1400151b6  mov     rcx, [rcx+18h]
0x1400151ba  mov     edx, 0ACh
0x1400151bf  mov     r9d, esi
0x1400151c2  call    WPP_SF_L
0x1400151c7  jmp     loc_140015D27
0x1400151cc  mov     rcx, rbx; P
0x1400151cf  call    MountMgrFreeDeadDeviceInfo
0x1400151d4  jmp     short loc_140015179
0x1400151d6  call    cs:__imp_KeWaitForSingleObject
0x1400151dd  nop     dword ptr [rax+rax+00h]
0x1400151e2  mov     r14, [r13+10h]
0x1400151e6  lea     r12, [r13+10h]
0x1400151ea  cmp     r14, r12
0x1400151ed  jz      short loc_140015216
0x1400151ef  lea     rcx, [r14+50h]; String1
0x1400151f3  mov     r8b, 1; CaseInSensitive
0x1400151f6  lea     rdx, [rbx+50h]; String2
0x1400151fa  call    cs:__imp_RtlCompareUnicodeString
0x140015201  nop     dword ptr [rax+rax+00h]
0x140015206  test    eax, eax
0x140015208  jz      loc_140015291
0x14001520e  mov     r14, [r14]
0x140015211  cmp     r14, r12
0x140015214  jnz     short loc_1400151EF
0x140015216  inc     qword ptr [r13+150h]
0x14001521d  lea     r9, [rsp+0A8h+arg_18]
0x140015225  mov     rax, [r13+150h]
0x14001522c  lea     r8, [rsp+0A8h+P]
0x140015231  mov     rdx, rbx
0x140015234  mov     [rbx+0B0h], rax
0x14001523b  call    QuerySymbolicLinkNamesFromStorage
0x140015240  lea     rsi, WPP_GLOBAL_Control
0x140015247  mov     r12d, eax
0x14001524a  test    eax, eax
0x14001524c  jns     loc_14001532D
0x140015252  mov     rcx, cs:WPP_GLOBAL_Control
0x140015259  cmp     rcx, rsi
0x14001525c  jz      short loc_14001527D
0x14001525e  mov     edx, [rcx+2Ch]
0x140015261  test    dl, 1
0x140015264  jz      short loc_14001527D
0x140015266  cmp     byte ptr [rcx+29h], 2
0x14001526a  jb      short loc_14001527D
0x14001526c  mov     rcx, [rcx+18h]
0x140015270  mov     edx, 0AEh
0x140015275  mov     r9d, eax
0x140015278  call    WPP_SF_L
0x14001527d  xor     r13d, r13d
0x140015280  mov     [rsp+0A8h+P], 0
0x140015289  xor     r12d, r12d
0x14001528c  jmp     loc_14001533F
0x140015291  mov     rcx, [rsp+0A8h+Mutex]; Mutex
0x140015296  xor     edx, edx; Wait
0x140015298  call    cs:__imp_KeReleaseMutex
0x14001529f  nop     dword ptr [rax+rax+00h]
0x1400152a4  mov     rcx, [rbx+60h]; P
0x1400152a8  xor     edx, edx; Tag
0x1400152aa  call    cs:__imp_ExFreePoolWithTag
0x1400152b1  nop     dword ptr [rax+rax+00h]
0x1400152b6  mov     rcx, [rbx+58h]; P
0x1400152ba  xor     edx, edx; Tag
0x1400152bc  call    cs:__imp_ExFreePoolWithTag
0x1400152c3  nop     dword ptr [rax+rax+00h]
0x1400152c8  mov     rcx, [rbx+48h]; P
0x1400152cc  xor     edx, edx; Tag
0x1400152ce  call    cs:__imp_ExFreePoolWithTag
0x1400152d5  nop     dword ptr [rax+rax+00h]
0x1400152da  xor     edx, edx; Tag
0x1400152dc  mov     rcx, rbx; P
0x1400152df  call    cs:__imp_ExFreePoolWithTag
0x1400152e6  nop     dword ptr [rax+rax+00h]
0x1400152eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400152f2  lea     rax, WPP_GLOBAL_Control
0x1400152f9  cmp     rcx, rax
0x1400152fc  jz      loc_140015D25
0x140015302  mov     eax, [rcx+2Ch]
0x140015305  test    al, 1
0x140015307  jz      loc_140015D25
0x14001530d  cmp     byte ptr [rcx+29h], 2
0x140015311  jb      loc_140015D25
0x140015317  mov     rcx, [rcx+18h]
0x14001531b  mov     edx, 0ADh
0x140015320  mov     r9d, esi
0x140015323  call    WPP_SF_L
0x140015328  jmp     loc_140015D25
0x14001532d  mov     rax, [rsp+0A8h+P]
0x140015332  mov     r13d, [rsp+0A8h+arg_18]
0x14001533a  mov     [rsp+0A8h+P], rax
0x14001533f  mov     r14, [rsp+0A8h+Context]
0x140015347  mov     rdx, [rbx+60h]
0x14001534b  mov     rcx, r14
0x14001534e  call    RemoveSavedLinks
0x140015353  xor     ebp, ebp
0x140015355  mov     [rsp+0A8h+Mutex], rax
0x14001535a  mov     byte ptr [rsp+0A8h+arg_18], 0
0x140015362  mov     [rsp+0A8h+var_76], 0
0x140015367  mov     [rsp+0A8h+var_77], 0
0x14001536c  test    r13d, r13d
0x14001536f  jz      loc_14001588C
0x140015375  mov     rcx, cs:WPP_GLOBAL_Control
0x14001537c  cmp     rcx, rsi
0x14001537f  jz      short loc_14001539F
0x140015381  mov     eax, [rcx+2Ch]
0x140015384  test    al, 1
0x140015386  jz      short loc_14001539F
0x140015388  cmp     byte ptr [rcx+29h], 2
0x14001538c  jb      short loc_14001539F
0x14001538e  mov     rcx, [rcx+18h]
0x140015392  mov     edx, 0AFh
0x140015397  xor     r9d, r9d
0x14001539a  call    WPP_SF_L
0x14001539f  mov     r14d, ebp
0x1400153a2  shl     r14, 4
0x1400153a6  add     r14, [rsp+0A8h+P]
0x1400153ab  movzx   eax, word ptr [r14]
0x1400153af  cmp     ax, 60h ; '`'
0x1400153b3  jz      short loc_1400153CE
0x1400153b5  cmp     ax, 62h ; 'b'
0x1400153b9  jnz     loc_1400154A2
0x1400153bf  mov     rax, [r14+8]
0x1400153c3  cmp     word ptr [rax+60h], 5Ch ; '\'
0x1400153c8  jnz     loc_1400154A2
0x1400153ce  mov     rax, [r14+8]
0x1400153d2  cmp     word ptr [rax], 5Ch ; '\'
0x1400153d6  jnz     loc_1400154A2
0x1400153dc  movzx   ecx, word ptr [rax+2]
0x1400153e0  cmp     cx, 3Fh ; '?'
0x1400153e4  jz      short loc_1400153F0
0x1400153e6  cmp     cx, 5Ch ; '\'
0x1400153ea  jnz     loc_1400154A2
0x1400153f0  cmp     word ptr [rax+4], 3Fh ; '?'
0x1400153f5  jnz     loc_1400154A2
0x1400153fb  cmp     word ptr [rax+6], 5Ch ; '\'
0x140015400  jnz     loc_1400154A2
0x140015406  cmp     word ptr [rax+8], 56h ; 'V'
0x14001540b  jnz     loc_1400154A2
0x140015411  cmp     word ptr [rax+0Ah], 6Fh ; 'o'
0x140015416  jnz     loc_1400154A2
0x14001541c  cmp     word ptr [rax+0Ch], 6Ch ; 'l'
0x140015421  jnz     short loc_1400154A2
0x140015423  cmp     word ptr [rax+0Eh], 75h ; 'u'
0x140015428  jnz     short loc_1400154A2
0x14001542a  cmp     word ptr [rax+10h], 6Dh ; 'm'
0x14001542f  jnz     short loc_1400154A2
0x140015431  cmp     word ptr [rax+12h], 65h ; 'e'
0x140015436  jnz     short loc_1400154A2
0x140015438  cmp     word ptr [rax+14h], 7Bh ; '{'
0x14001543d  jnz     short loc_1400154A2
0x14001543f  cmp     word ptr [rax+26h], 2Dh ; '-'
0x140015444  jnz     short loc_1400154A2
0x140015446  cmp     word ptr [rax+30h], 2Dh ; '-'
0x14001544b  jnz     short loc_1400154A2
0x14001544d  cmp     word ptr [rax+3Ah], 2Dh ; '-'
0x140015452  jnz     short loc_1400154A2
0x140015454  cmp     word ptr [rax+44h], 2Dh ; '-'
0x140015459  jnz     short loc_1400154A2
0x14001545b  cmp     word ptr [rax+5Eh], 7Dh ; '}'
0x140015460  jnz     short loc_1400154A2
0x140015462  mov     [rsp+0A8h+var_77], 1
0x140015467  mov     rcx, cs:WPP_GLOBAL_Control
0x14001546e  cmp     rcx, rsi
0x140015471  jz      loc_1400155A6
0x140015477  mov     eax, [rcx+2Ch]
0x14001547a  test    al, 1
0x14001547c  jz      loc_1400155A6
0x140015482  cmp     byte ptr [rcx+29h], 2
0x140015486  jb      loc_1400155A6
0x14001548c  mov     rcx, [rcx+18h]
0x140015490  mov     edx, 0B0h
0x140015495  mov     r9d, r12d
0x140015498  call    WPP_SF_L
0x14001549d  jmp     loc_1400155A6
0x1400154a2  mov     rcx, r14; String2
0x1400154a5  call    IsDriveLetter
  ... truncated ...
```
