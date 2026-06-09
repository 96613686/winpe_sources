# MdaLocateDirent

- ea: `0x1400070a0`
- end: `0x140008136`
- name: `MdaLocateDirent`
- size: `4246`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *, __int64 *, char, __int64 *, __int64, PUNICODE_STRING DestinationString, PUNICODE_STRING Name, _BYTE *)`
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x140005de0`

## callees

- `0x140003380`
- `0x140003440`
- `0x140003510`
- `0x140003bd0`
- `0x140004530`
- `0x140005c90`
- `0x1400070a0`
- `0x140008140`
- `0x140008a50`
- `0x140009380`
- `0x14000c370`
- `0x140013dc0`
- `0x140014970`
- `0x140014a90`
- `0x1400159cc`
- `0x1400159fc`
- `0x140015a40`
- `0x140018a7c`
- `0x14002c4c4`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x14000719d`
- `ntoskrnl!RtlCopyUnicodeString` at `0x14000719d`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400072b8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140007d42`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400072b8`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140007d42`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14000793e`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400079a6`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x14000793e`
- `ntoskrnl!FsRtlIsNameInExpression` at `0x1400079a6`
- `ntoskrnl!RtlCustomCPToUnicodeN` at `0x140007716`
- `ntoskrnl!RtlCustomCPToUnicodeN` at `0x140007716`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14000780e`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x14000780e`
- `ntoskrnl!KeReleaseMutex` at `0x1400071eb`
- `ntoskrnl!KeReleaseMutex` at `0x140007267`
- `ntoskrnl!KeReleaseMutex` at `0x14000733d`
- `ntoskrnl!KeReleaseMutex` at `0x1400073fe`
- `ntoskrnl!KeReleaseMutex` at `0x140007412`
- `ntoskrnl!KeReleaseMutex` at `0x140007a4a`
- `ntoskrnl!KeReleaseMutex` at `0x140007c63`
- `ntoskrnl!KeReleaseMutex` at `0x140007cb4`
- `ntoskrnl!KeReleaseMutex` at `0x140007e5c`
- `ntoskrnl!KeReleaseMutex` at `0x140007f6a`
- `ntoskrnl!KeReleaseMutex` at `0x140007fb4`
- `ntoskrnl!KeReleaseMutex` at `0x1400071eb`
- `ntoskrnl!KeReleaseMutex` at `0x140007267`
- `ntoskrnl!KeReleaseMutex` at `0x14000733d`
- `ntoskrnl!KeReleaseMutex` at `0x1400073fe`
- `ntoskrnl!KeReleaseMutex` at `0x140007412`
- `ntoskrnl!KeReleaseMutex` at `0x140007a4a`
- `ntoskrnl!KeReleaseMutex` at `0x140007c63`
- `ntoskrnl!KeReleaseMutex` at `0x140007cb4`
- `ntoskrnl!KeReleaseMutex` at `0x140007e5c`
- `ntoskrnl!KeReleaseMutex` at `0x140007f6a`
- `ntoskrnl!KeReleaseMutex` at `0x140007fb4`

## pseudocode

```c
__int64 __fastcall MdaLocateDirent(
        __int64 a1,
        __int64 a2,
        __int64 *a3,
        __int64 *a4,
        char a5,
        __int64 *a6,
        __int64 a7,
        PUNICODE_STRING DestinationString,
        PUNICODE_STRING Name,
        _BYTE *a10)
{
  __int64 v10; // r11
  int v11; // r12d
  CHAR *v12; // r15
  __int64 v13; // r13
  __int64 v14; // r14
  __int64 v16; // r10
  int v18; // ecx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  int appended; // r15d
  __int64 v23; // rcx
  __int64 v24; // rdi
  bool v25; // cf
  __int64 *v26; // r9
  __int64 *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // rax
  int v30; // r9d
  int DirectoryEntry; // eax
  int v32; // eax
  int v33; // r9d
  USHORT v34; // ax
  PWSTR Buffer; // rcx
  int v36; // eax
  __int64 v37; // rdx
  PDEVICE_OBJECT v38; // rcx
  int v39; // eax
  struct _UNICODE_STRING *v40; // rcx
  USHORT Length; // ax
  struct _UNICODE_STRING *v42; // rcx
  BOOLEAN IsNameInExpression; // al
  unsigned int v44; // ebx
  PWSTR v45; // rax
  __int64 v46; // rax
  struct _UNICODE_STRING *v47; // rax
  struct _UNICODE_STRING *v48; // rdx
  __int64 v49; // rax
  PDEVICE_OBJECT v50; // rdx
  PDEVICE_OBJECT v51; // rcx
  __int64 v52; // r11
  __int64 v53; // rax
  __int64 v54; // rdx
  int v55; // ecx
  PDEVICE_OBJECT v56; // rax
  PDEVICE_OBJECT v57; // rcx
  struct _KMUTANT *v58; // rcx
  __int64 v59; // rdx
  __int64 v60; // r8
  int TargetAttributes; // eax
  __int64 v62; // rcx
  __int64 v63; // rax
  PDEVICE_OBJECT v64; // rbx
  struct _KMUTANT *Timer; // rcx
  PDEVICE_OBJECT v66; // rdi
  __int64 v67; // [rsp+50h] [rbp-89h] BYREF
  __int64 v68; // [rsp+58h] [rbp-81h]
  __int64 *v69; // [rsp+60h] [rbp-79h]
  __int64 *v70; // [rsp+68h] [rbp-71h]
  ULONG BytesInUnicodeString[2]; // [rsp+70h] [rbp-69h] BYREF
  int v72; // [rsp+78h] [rbp-61h] BYREF
  PDEVICE_OBJECT v73[2]; // [rsp+80h] [rbp-59h] BYREF
  PCH CustomCPString[2]; // [rsp+90h] [rbp-49h] BYREF
  CHAR *v75; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v76; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v77; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v78; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v79; // [rsp+C0h] [rbp-19h]
  __int64 v80; // [rsp+C8h] [rbp-11h]
  UNICODE_STRING String2; // [rsp+D0h] [rbp-9h] BYREF
  struct _MRX_FCB_ *v83; // [rsp+128h] [rbp+4Fh]
  __int64 *v84; // [rsp+130h] [rbp+57h]
  int DestinationStringa; // [rsp+158h] [rbp+7Fh]
  unsigned int DestinationStringb; // [rsp+158h] [rbp+7Fh]

  v84 = a3;
  v83 = (struct _MRX_FCB_ *)a2;
  v10 = *(_QWORD *)(a2 + 80);
  v11 = 0;
  v12 = 0;
  v72 = 0;
  v13 = 0;
  v75 = 0;
  v14 = 0;
  v78 = 0;
  v77 = 0;
  LOBYTE(v67) = 0;
  v16 = a1;
  v76 = 0;
  *(_OWORD *)CustomCPString = 0;
  v68 = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    LODWORD(a2) = (_DWORD)v83;
    v16 = a1;
    v10 = v68;
    a3 = v84;
  }
  if ( !DestinationString || !DestinationString->Buffer || DestinationString->MaximumLength < 0x208u || !Name )
    return 3221225485LL;
  DestinationString->Length = 0;
  v18 = *((_DWORD *)a4 + 2);
  if ( (v18 & 1) == 0 )
  {
    *((_DWORD *)a4 + 2) = v18 | 0x10;
    RtlCopyUnicodeString(DestinationString, (PCUNICODE_STRING)(a4 + 3));
    if ( DestinationString->Length == 2 )
    {
      if ( *DestinationString->Buffer == 46 )
      {
        HacReference(v84[1]);
        HacAcquireLock(v84[1]);
        *a6 = v84[1];
        KeReleaseMutex(*(PRKMUTEX *)(v84[1] + 40), 0);
        Name->Length = 0;
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
          return 0;
        v20 = 54;
LABEL_19:
        WPP_SF_d(v19->AttachedDevice, v20, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
        return 0;
      }
    }
    else if ( DestinationString->Length == 4 && *(_DWORD *)DestinationString->Buffer == 3014702 )
    {
      HacReference(*v84);
      HacAcquireLock(*v84);
      *a6 = *v84;
      KeReleaseMutex(*(PRKMUTEX *)(*v84 + 40), 0);
      Name->Length = 0;
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
        return 0;
      v20 = 55;
      goto LABEL_19;
    }
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)(a4 + 5), DestinationString);
    if ( appended >= 0 )
    {
      appended = CaseInsensitiveLookup(a1, (_DWORD)v83, (int)a4 + 40, v84[1], a5, (__int64)a6);
      if ( appended >= 0 )
      {
        HacAcquireLock(*a6);
        v23 = *a6;
        if ( *(_DWORD *)(*a6 + 128) == 5 && a7 )
        {
          v24 = v84[1];
          KeReleaseMutex(*(PRKMUTEX *)(v23 + 40), 0);
          appended = MdaFindTargetAttributes(a1, v83, *a6, a5, a7, &v67, a10);
          if ( appended >= 0 )
          {
            if ( (_BYTE)v67 )
            {
              HacDereference(v68, *a6);
              HacReference(v24);
              HacAcquireLock(v24);
              *a6 = v24;
              KeReleaseMutex(*(PRKMUTEX *)(v24 + 40), 0);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
            HacDereference(v68, *a6);
            *a6 = 0;
          }
        }
        else
        {
          KeReleaseMutex(*(PRKMUTEX *)(v23 + 40), 0);
          Name->Length = 0;
          appended = 0;
          if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            return (unsigned int)appended;
          if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 57, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids, Name);
        }
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 58, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    return (unsigned int)appended;
  }
  v25 = (a4[1] & 4) != 0;
  DestinationStringa = 0;
  v26 = &v77;
  v27 = &v76;
  v80 = *(_QWORD *)(*(_QWORD *)(v16 + 32) + 40LL);
  v79 = *(_QWORD *)(v16 + 40);
  if ( !v25 )
  {
    v26 = 0;
    v27 = 0;
  }
  v69 = v26;
  v70 = v27;
  while ( 1 )
  {
    while ( 1 )
    {
      while ( 1 )
      {
        while ( 1 )
        {
          if ( *a10 )
            goto LABEL_160;
          DestinationString->Length = 0;
          *((_WORD *)a4 + 20) = *((_WORD *)a4 + 6);
          if ( (a4[1] & 2) != 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 195, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
              v10 = v68;
              v26 = v69;
              v27 = v70;
            }
            v28 = *a4;
            if ( *a4 )
            {
              v12 = *(CHAR **)(v28 + 256);
              v29 = *(_QWORD *)(v28 + 72);
              v11 = *(_DWORD *)(v28 + 88);
              v75 = v12;
              v78 = v29;
              v72 = v11;
              if ( v27 )
              {
                *v27 = 0;
                v13 = v76;
              }
              if ( v26 )
              {
                *v26 = 0;
                v14 = v77;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
                v10 = v68;
              }
              v30 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 196, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
                v10 = v68;
              }
              v30 = -1073741811;
            }
            *((_DWORD *)a4 + 2) &= ~2u;
            DestinationStringb = v30;
          }
          else
          {
            DirectoryEntry = NfsReadDirectoryEntry(
                               v16,
                               a2,
                               a3[1],
                               (_DWORD)a4,
                               1,
                               (__int64)&v78,
                               (__int64)&v75,
                               (__int64)&v72,
                               (__int64)v27,
                               (__int64)v26);
            v10 = v68;
            v12 = v75;
            v30 = DirectoryEntry;
            v11 = v72;
            v13 = v76;
            v14 = v77;
            DestinationStringb = DirectoryEntry;
          }
          if ( v30 < 0 )
          {
            v44 = DestinationStringb;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
            if ( DestinationStringb != -2147483642 )
            {
              LOBYTE(v28) = 1;
              NfsReadDirectoryQuit(a4, v28);
            }
            *((_DWORD *)a4 + 2) |= 0x10u;
            goto LABEL_161;
          }
          if ( !v11 || !v12 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 60, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
            *((_DWORD *)a4 + 2) |= 0x10u;
            v44 = -1073741823;
            goto LABEL_161;
          }
          LOWORD(CustomCPString[0]) = v11;
          CustomCPString[1] = v12;
          v32 = *(_DWORD *)(v79 + 32);
          if ( (v32 & 0x14000) != 0 )
          {
            BytesInUnicodeString[0] = 0;
            DestinationStringa = LoadCodePageTable(v10, 949, &KscTableInfo, &KscTableBase);
            v33 = DestinationStringa;
            if ( DestinationStringa >= 0 )
            {
              DestinationStringa = RtlCustomCPToUnicodeN(
                                     &KscTableInfo,
                                     DestinationString->Buffer,
                                     DestinationString->MaximumLength - 2,
                                     BytesInUnicodeString,
                                     CustomCPString[1],
                                     LOWORD(CustomCPString[0]));
              v33 = DestinationStringa;
              if ( DestinationStringa >= 0 )
              {
                v34 = BytesInUnicodeString[0];
                if ( BytesInUnicodeString[0] >= (unsigned __int64)DestinationString->MaximumLength - 2 )
                  v34 = DestinationString->MaximumLength - 2;
                Buffer = DestinationString->Buffer;
                DestinationString->Length = v34;
                Buffer[(unsigned __int64)v34 >> 1] = 0;
              }
            }
          }
          else
          {
            if ( (v32 & 0x8040) != 0 )
            {
              v36 = NfsConvertDbcsToUnicode(
                      v10,
                      (__int64)DestinationString,
                      (unsigned __int16 *)CustomCPString,
                      0,
                      &ShiftJisTableInfo,
                      (__int64)&ShiftJisTableBase,
                      0x3A4u);
            }
            else if ( (v32 & 0x20000) != 0 )
            {
              v36 = NfsConvertDbcsToUnicode(
                      v10,
                      (__int64)DestinationString,
                      (unsigned __int16 *)CustomCPString,
                      0,
                      &Big5TableInfo,
                      (__int64)&Big5TableBase,
                      0x3B6u);
            }
            else if ( (v32 & 0x2000) != 0 )
            {
              v36 = NfsConvertDbcsToUnicode(
                      v10,
                      (__int64)DestinationString,
                      (unsigned __int16 *)CustomCPString,
                      0,
                      &CnsTableInfo,
                      (__int64)&CnsTableBase,
                      0x4E20u);
            }
            else
            {
              v36 = (v32 & 0x40000) != 0
                  ? NfsConvertDbcsToUnicode(
                      v10,
                      (__int64)DestinationString,
                      (unsigned __int16 *)CustomCPString,
                      0,
                      &GBTableInfo,
                      (__int64)&GBTableBase,
                      0x3A8u)
                  : RtlAnsiStringToUnicodeString(DestinationString, (PCANSI_STRING)CustomCPString, 0);
            }
            v33 = v36;
            DestinationStringa = v36;
          }
          if ( v33 >= 0 )
            break;
          LODWORD(v16) = a1;
          LODWORD(a2) = (_DWORD)v83;
          v10 = v68;
          a3 = v84;
          v27 = v70;
          *(_QWORD *)BytesInUnicodeString = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            v37 = 61;
LABEL_88:
            v38 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
            goto LABEL_89;
          }
LABEL_44:
          v26 = v69;
        }
        Name->Length = 0;
        v39 = *((_DWORD *)a4 + 2);
        if ( (v39 & 8) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          }
          goto LABEL_111;
        }
        v40 = (struct _UNICODE_STRING *)(a4 + 3);
        if ( (v39 & 1) != 0 )
          break;
        Length = v40->Length;
        LODWORD(a2) = (_DWORD)v83;
        LODWORD(v16) = a1;
        v10 = v68;
        a3 = v84;
        v26 = v69;
        v27 = v70;
        if ( Length != DestinationString->Length && Length )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          }
          DestinationString->Length = 0;
          goto LABEL_43;
        }
      }
      if ( FsRtlIsNameInExpression(v40, DestinationString, 1u, 0) )
        goto LABEL_111;
      LODWORD(a2) = (_DWORD)v83;
      LODWORD(v16) = a1;
      v10 = v68;
      a3 = v84;
      v26 = v69;
      v27 = v70;
      if ( Name->Length )
      {
        v42 = (struct _UNICODE_STRING *)(a4 + 3);
        if ( Name->Length == 4 && *(_DWORD *)Name->Buffer == 3014702 && v42->Length > 1u )
          Name->Length = 1;
        IsNameInExpression = FsRtlIsNameInExpression(v42, Name, 1u, 0);
        LODWORD(a2) = (_DWORD)v83;
        LODWORD(v16) = a1;
        v10 = v68;
        a3 = v84;
        v26 = v69;
        v27 = v70;
        if ( IsNameInExpression )
          break;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 64, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids, Name);
LABEL_111:
    if ( DestinationString->Length == 2 )
    {
      if ( *DestinationString->Buffer == 46 )
      {
        HacReference(v84[1]);
        HacAcquireLock(v84[1]);
        *a6 = v84[1];
        KeReleaseMutex(*(PRKMUTEX *)(v84[1] + 40), 0);
        v44 = 0;
        goto LABEL_161;
      }
    }
    else if ( DestinationString->Length == 4 )
    {
      v45 = DestinationString->Buffer;
      if ( *v45 == 46 && v45[1] == 46 )
      {
        HacReference(*v84);
        HacAcquireLock(*v84);
        v62 = *v84;
        *a6 = *v84;
        if ( (unsigned __int8)HacIsEntryFake(v62) && v14 )
        {
          v63 = *a6;
          *(_OWORD *)(v63 + 128) = *(_OWORD *)v14;
          *(_OWORD *)(v63 + 144) = *(_OWORD *)(v14 + 16);
          *(_OWORD *)(v63 + 160) = *(_OWORD *)(v14 + 32);
          *(_OWORD *)(v63 + 176) = *(_OWORD *)(v14 + 48);
          *(_OWORD *)(v63 + 192) = *(_OWORD *)(v14 + 64);
          *(_QWORD *)(v63 + 208) = *(_QWORD *)(v14 + 80);
        }
        KeReleaseMutex(*(PRKMUTEX *)(*v84 + 40), 0);
        v44 = 0;
        goto LABEL_161;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids, a4 + 5);
    if ( !v13 || !v14 )
      break;
    v46 = v80;
    *((_WORD *)a4 + 20) -= 2;
    v47 = HacAllocate(v68, *(_QWORD *)(v46 + 72), (const UNICODE_STRING *)(a4 + 5), DestinationString);
    *(_QWORD *)BytesInUnicodeString = v47;
    v48 = v47;
    if ( v47 )
    {
      *(struct _UNICODE_STRING *)((char *)v47 + 216) = *(struct _UNICODE_STRING *)v13;
      *(struct _UNICODE_STRING *)((char *)v47 + 232) = *(struct _UNICODE_STRING *)(v13 + 16);
      *(struct _UNICODE_STRING *)((char *)v47 + 248) = *(struct _UNICODE_STRING *)(v13 + 32);
      *(struct _UNICODE_STRING *)((char *)v47 + 264) = *(struct _UNICODE_STRING *)(v13 + 48);
      LODWORD(v47[17].Buffer) = *(_DWORD *)(v13 + 64);
      v47[8] = *(struct _UNICODE_STRING *)v14;
      v47[9] = *(struct _UNICODE_STRING *)(v14 + 16);
      v47[10] = *(struct _UNICODE_STRING *)(v14 + 32);
      v47[11] = *(struct _UNICODE_STRING *)(v14 + 48);
      v47[12] = *(struct _UNICODE_STRING *)(v14 + 64);
      *(_QWORD *)&v47[13].Length = *(_QWORD *)(v14 + 80);
      v49 = *a4;
      String2 = 0;
      v48[7].Buffer = *(PWSTR *)(v49 + 56);
      v73[0] = (PDEVICE_OBJECT)v84[1];
      HacAcquireLock(v48);
      v50 = v73[0];
      if ( v73[0] )
      {
        v51 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
        *(_DWORD *)(*(_QWORD *)BytesInUnicodeString + 104LL) = v73[0]->Queue.Wcb.CurrentIrp;
        HIDWORD(v51->Queue.Wcb.DeviceRoutine) = v50->Dpc.TargetInfoAsUlong;
        LODWORD(v51->Queue.Wcb.DeviceContext) = *((_DWORD *)&v50->Dpc.0 + 1);
      }
      else
      {
        MdaDissectNameTail(*(_QWORD *)BytesInUnicodeString + 64LL, &String2, v73);
        v53 = HacQueryAndReference(*(PRKMUTEX *)(v52 + 40), &String2);
        v54 = v53;
        if ( v53 )
        {
          v55 = *(_DWORD *)(v53 + 136);
          v56 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
          *(_DWORD *)(*(_QWORD *)BytesInUnicodeString + 104LL) = v55;
          HIDWORD(v56->Queue.Wcb.DeviceRoutine) = *(_DWORD *)(v54 + 200);
          LODWORD(v56->Queue.Wcb.DeviceContext) = *(_DWORD *)(v54 + 204);
          HacDereference(v68, v54);
        }
        v51 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
      }
      KeReleaseMutex((PRKMUTEX)v51->Timer, 0);
      HacInsertEntry(v68, *(_QWORD *)BytesInUnicodeString);
      HacAcquireLock(*(_QWORD *)BytesInUnicodeString);
      v57 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
      if ( *(_DWORD *)(*(_QWORD *)BytesInUnicodeString + 128LL) == 5 && a7 )
      {
        v58 = *(struct _KMUTANT **)(*(_QWORD *)BytesInUnicodeString + 40LL);
        v73[0] = (PDEVICE_OBJECT)v84[1];
        KeReleaseMutex(v58, 0);
        DestinationStringa = MdaFindTargetAttributes(a1, v83, *(__int64 *)BytesInUnicodeString, a5, a7, &v67, a10);
        if ( DestinationStringa < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          }
          v59 = *(_QWORD *)BytesInUnicodeString;
LABEL_42:
          HacDereference(v68, v59);
          *a6 = 0;
          goto LABEL_43;
        }
        if ( !(_BYTE)v67 )
        {
          v44 = DestinationStringa;
          *a6 = *(_QWORD *)BytesInUnicodeString;
          goto LABEL_161;
        }
        HacDereference(v68, *(_QWORD *)BytesInUnicodeString);
        v64 = v73[0];
        HacReference(v73[0]);
        HacAcquireLock(v64);
        *a6 = (__int64)v64;
        Timer = (struct _KMUTANT *)v64->Timer;
      }
      else
      {
        *a6 = *(_QWORD *)BytesInUnicodeString;
        Timer = (struct _KMUTANT *)v57->Timer;
      }
LABEL_159:
      KeReleaseMutex(Timer, 0);
LABEL_160:
      v44 = DestinationStringa;
      goto LABEL_161;
    }
    LODWORD(v16) = a1;
    LODWORD(a2) = (_DWORD)v83;
    v10 = v68;
    a3 = v84;
    v26 = v69;
    v27 = v70;
    *(_QWORD *)BytesInUnicodeString = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v37 = 66;
      goto LABEL_88;
    }
  }
  DestinationStringa = RtlAppendUnicodeStringToString((PUNICODE_STRING)(a4 + 5), DestinationString);
  if ( DestinationStringa < 0 )
  {
    LODWORD(v16) = a1;
    LODWORD(a2) = (_DWORD)v83;
    v10 = v68;
    a3 = v84;
    v27 = v70;
    v73[0] = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v38 = v73[0];
      v37 = 68;
      goto LABEL_89;
    }
    goto LABEL_44;
  }
  DestinationStringa = NfsLookup(a1, (_DWORD)v83, (int)a4 + 40, v84[1], a5, (__int64)a6);
  if ( DestinationStringa < 0 )
  {
    LODWORD(v16) = a1;
    LODWORD(a2) = (_DWORD)v83;
    v10 = v68;
    a3 = v84;
    v27 = v70;
    v73[0] = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v38 = v73[0];
      v37 = 69;
LABEL_89:
      WPP_SF_d(v38->AttachedDevice, v37, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
LABEL_43:
      LODWORD(a2) = (_DWORD)v83;
      LODWORD(v16) = a1;
      v10 = v68;
      a3 = v84;
      v27 = v70;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  HacAcquireLock(*a6);
  v60 = *a6;
  if ( *(_DWORD *)(*a6 + 128) != 5 || !a7 )
  {
    Timer = *(struct _KMUTANT **)(v60 + 40);
    goto LABEL_159;
  }
  v73[0] = (PDEVICE_OBJECT)v84[1];
  KeReleaseMutex(*(PRKMUTEX *)(v60 + 40), 0);
  TargetAttributes = MdaFindTargetAttributes(a1, v83, *a6, a5, a7, &v67, a10);
  DestinationStringa = TargetAttributes;
  if ( TargetAttributes < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    v59 = *a6;
    goto LABEL_42;
  }
  if ( (_BYTE)v67 )
  {
    HacDereference(v68, *a6);
    v66 = v73[0];
    HacReference(v73[0]);
    HacAcquireLock(v66);
    *a6 = (__int64)v66;
    Timer = (struct _KMUTANT *)v66->Timer;
    goto LABEL_159;
  }
  v44 = TargetAttributes;
LABEL_161:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
  }
  return v44;
}

```

## disassembly

```asm
0x1400070a0  mov     [rsp-8+arg_10], r8
0x1400070a5  mov     [rsp-8+arg_8], rdx
0x1400070aa  mov     qword ptr [rsp-8+arg_0], rcx
0x1400070af  push    rbp
0x1400070b0  push    rbx
0x1400070b1  push    rsi
0x1400070b2  push    r12
0x1400070b4  push    r13
0x1400070b6  push    r14
0x1400070b8  push    r15
0x1400070ba  lea     rbp, [rsp-7]
0x1400070bf  sub     rsp, 0E0h
0x1400070c6  mov     r11, [rdx+50h]
0x1400070ca  xor     r12d, r12d
0x1400070cd  xor     r15d, r15d
0x1400070d0  mov     [rbp+37h+var_98], r12d
0x1400070d4  xor     r13d, r13d
0x1400070d7  mov     [rbp+37h+var_70], r15
0x1400070db  xor     r14d, r14d
0x1400070de  mov     [rbp+37h+var_58], r12
0x1400070e2  xorps   xmm0, xmm0
0x1400070e5  mov     [rbp+37h+var_60], r14
0x1400070e9  mov     rsi, r9
0x1400070ec  mov     byte ptr [rsp+110h+var_C0], r12b
0x1400070f1  mov     r10, rcx
0x1400070f4  mov     [rbp+37h+var_68], r13
0x1400070f8  movups  xmmword ptr [rbp+37h+var_80], xmm0
0x1400070fc  mov     [rsp+110h+var_B8], r11
0x140007101  mov     rcx, cs:WPP_GLOBAL_Control
0x140007108  lea     rax, WPP_GLOBAL_Control
0x14000710f  cmp     rcx, rax
0x140007112  jz      short loc_140007141
0x140007114  mov     eax, [rcx+2Ch]
0x140007117  test    al, 8
0x140007119  jz      short loc_140007141
0x14000711b  mov     rcx, [rcx+18h]
0x14000711f  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x140007126  mov     edx, 35h ; '5'
0x14000712b  call    WPP_SF_
0x140007130  mov     rdx, [rbp+37h+arg_8]
0x140007134  mov     r10, qword ptr [rbp+37h+arg_0]
0x140007138  mov     r11, [rsp+110h+var_B8]
0x14000713d  mov     r8, [rbp+37h+arg_10]
0x140007141  mov     rbx, [rbp+37h+DestinationString]
0x140007145  mov     [rsp+110h+arg_18], rdi
0x14000714d  test    rbx, rbx
0x140007150  jz      loc_140008115
0x140007156  cmp     [rbx+8], r12
0x14000715a  jz      loc_140008115
0x140007160  mov     eax, 208h
0x140007165  cmp     [rbx+2], ax
0x140007169  jb      loc_140008115
0x14000716f  mov     rdi, [rbp+37h+Name]
0x140007176  test    rdi, rdi
0x140007179  jz      loc_140008115
0x14000717f  xor     eax, eax
0x140007181  mov     [rbx], ax
0x140007184  mov     ecx, [rsi+8]
0x140007187  test    cl, 1
0x14000718a  jnz     loc_140007492
0x140007190  or      ecx, 10h
0x140007193  lea     rdx, [rsi+18h]; SourceString
0x140007197  mov     [rsi+8], ecx
0x14000719a  mov     rcx, rbx; DestinationString
0x14000719d  call    cs:__imp_RtlCopyUnicodeString
0x1400071a4  nop     dword ptr [rax+rax+00h]
0x1400071a9  movzx   eax, word ptr [rbx]
0x1400071ac  cmp     ax, 2
0x1400071b0  jnz     short loc_140007225
0x1400071b2  mov     rax, [rbx+8]
0x1400071b6  cmp     word ptr [rax], 2Eh ; '.'
0x1400071ba  jnz     loc_1400072B1
0x1400071c0  mov     rbx, [rbp+37h+arg_10]
0x1400071c4  mov     rcx, [rbx+8]
0x1400071c8  call    HacReference
0x1400071cd  mov     rcx, [rbx+8]
0x1400071d1  call    HacAcquireLock
0x1400071d6  mov     rcx, [rbx+8]
0x1400071da  xor     edx, edx; Wait
0x1400071dc  mov     rax, [rbp+37h+arg_28]
0x1400071e0  mov     [rax], rcx
0x1400071e3  mov     rcx, [rbx+8]
0x1400071e7  mov     rcx, [rcx+28h]; Mutex
0x1400071eb  call    cs:__imp_KeReleaseMutex
0x1400071f2  nop     dword ptr [rax+rax+00h]
0x1400071f7  xor     eax, eax
0x1400071f9  mov     [rdi], ax
0x1400071fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140007203  lea     rdx, WPP_GLOBAL_Control
0x14000720a  cmp     rcx, rdx
0x14000720d  jz      loc_1400072AA
0x140007213  mov     eax, [rcx+2Ch]
0x140007216  test    al, 8
0x140007218  jz      loc_1400072AA
0x14000721e  mov     edx, 36h ; '6'
0x140007223  jmp     short loc_140007297
0x140007225  cmp     ax, 4
0x140007229  jnz     loc_1400072B1
0x14000722f  mov     rax, [rbx+8]
0x140007233  cmp     word ptr [rax], 2Eh ; '.'
0x140007237  jnz     short loc_1400072B1
0x140007239  cmp     word ptr [rax+2], 2Eh ; '.'
0x14000723e  jnz     short loc_1400072B1
0x140007240  mov     rbx, [rbp+37h+arg_10]
0x140007244  mov     rcx, [rbx]
0x140007247  call    HacReference
0x14000724c  mov     rcx, [rbx]
0x14000724f  call    HacAcquireLock
0x140007254  mov     rcx, [rbx]
0x140007257  xor     edx, edx; Wait
0x140007259  mov     rax, [rbp+37h+arg_28]
0x14000725d  mov     [rax], rcx
0x140007260  mov     rcx, [rbx]
0x140007263  mov     rcx, [rcx+28h]; Mutex
0x140007267  call    cs:__imp_KeReleaseMutex
0x14000726e  nop     dword ptr [rax+rax+00h]
0x140007273  xor     eax, eax
0x140007275  mov     [rdi], ax
0x140007278  mov     rcx, cs:WPP_GLOBAL_Control
0x14000727f  lea     rdx, WPP_GLOBAL_Control
0x140007286  cmp     rcx, rdx
0x140007289  jz      short loc_1400072AA
0x14000728b  mov     eax, [rcx+2Ch]
0x14000728e  test    al, 8
0x140007290  jz      short loc_1400072AA
0x140007292  mov     edx, 37h ; '7'
0x140007297  mov     rcx, [rcx+18h]
0x14000729b  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x1400072a2  xor     r9d, r9d
0x1400072a5  call    WPP_SF_d
0x1400072aa  xor     eax, eax
0x1400072ac  jmp     loc_14000811A
0x1400072b1  mov     rdx, rbx; Source
0x1400072b4  lea     rcx, [rsi+28h]; Destination
0x1400072b8  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400072bf  nop     dword ptr [rax+rax+00h]
0x1400072c4  mov     r15d, eax
0x1400072c7  test    eax, eax
0x1400072c9  js      loc_140007458
0x1400072cf  mov     r14, [rbp+37h+arg_10]
0x1400072d3  lea     r8, [rsi+28h]
0x1400072d7  mov     r12, [rbp+37h+arg_28]
0x1400072db  mov     rbx, [rbp+37h+arg_8]
0x1400072df  mov     rsi, qword ptr [rbp+37h+arg_0]
0x1400072e3  mov     rdx, rbx
0x1400072e6  movzx   r13d, [rbp+37h+arg_20]
0x1400072eb  mov     rcx, rsi
0x1400072ee  mov     r9, [r14+8]
0x1400072f2  mov     qword ptr [rsp+110h+BytesInCustomCPString], r12
0x1400072f7  mov     byte ptr [rsp+110h+CustomCPString], r13b
0x1400072fc  call    CaseInsensitiveLookup
0x140007301  mov     r15d, eax
0x140007304  test    eax, eax
0x140007306  js      loc_140007458
0x14000730c  mov     rcx, [r12]
0x140007310  call    HacAcquireLock
0x140007315  mov     rcx, [r12]
0x140007319  cmp     dword ptr [rcx+80h], 5
0x140007320  jnz     loc_14000740C
0x140007326  mov     r15, [rbp+37h+arg_30]
0x14000732a  test    r15, r15
0x14000732d  jz      loc_14000740C
0x140007333  mov     rcx, [rcx+28h]; Mutex
0x140007337  xor     edx, edx; Wait
0x140007339  mov     rdi, [r14+8]
0x14000733d  call    cs:__imp_KeReleaseMutex
0x140007344  nop     dword ptr [rax+rax+00h]
0x140007349  mov     rax, [rbp+37h+arg_48]
0x140007350  movzx   r9d, r13b
0x140007354  mov     r8, [r12]
0x140007358  mov     rdx, rbx
0x14000735b  mov     [rsp+110h+var_E0], rax; __int64
0x140007360  mov     rcx, rsi; int
0x140007363  lea     rax, [rsp+110h+var_C0]
0x140007368  mov     qword ptr [rsp+110h+BytesInCustomCPString], rax; __int64
0x14000736d  mov     [rsp+110h+CustomCPString], r15; __int64
0x140007372  call    MdaFindTargetAttributes
0x140007377  mov     r15d, eax
0x14000737a  test    eax, eax
0x14000737c  jns     short loc_1400073CB
0x14000737e  mov     rcx, cs:WPP_GLOBAL_Control
0x140007385  lea     rdx, WPP_GLOBAL_Control
0x14000738c  cmp     rcx, rdx
0x14000738f  jz      short loc_1400073B0
0x140007391  mov     eax, [rcx+2Ch]
0x140007394  test    al, 1
0x140007396  jz      short loc_1400073B0
0x140007398  mov     rcx, [rcx+18h]
0x14000739c  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x1400073a3  mov     edx, 38h ; '8'
0x1400073a8  mov     r9d, r15d
0x1400073ab  call    WPP_SF_d
0x1400073b0  mov     rdx, [r12]
0x1400073b4  mov     rcx, [rsp+110h+var_B8]
0x1400073b9  call    HacDereference
0x1400073be  mov     qword ptr [r12], 0
0x1400073c6  jmp     loc_140007458
0x1400073cb  cmp     byte ptr [rsp+110h+var_C0], 0
0x1400073d0  jz      loc_140007458
0x1400073d6  mov     rdx, [r12]
0x1400073da  mov     rcx, [rsp+110h+var_B8]
0x1400073df  call    HacDereference
0x1400073e4  mov     rcx, rdi
0x1400073e7  call    HacReference
0x1400073ec  mov     rcx, rdi
0x1400073ef  call    HacAcquireLock
0x1400073f4  mov     [r12], rdi
0x1400073f8  xor     edx, edx; Wait
0x1400073fa  mov     rcx, [rdi+28h]; Mutex
0x1400073fe  call    cs:__imp_KeReleaseMutex
0x140007405  nop     dword ptr [rax+rax+00h]
0x14000740a  jmp     short loc_140007458
0x14000740c  mov     rcx, [rcx+28h]; Mutex
0x140007410  xor     edx, edx; Wait
0x140007412  call    cs:__imp_KeReleaseMutex
0x140007419  nop     dword ptr [rax+rax+00h]
0x14000741e  xor     eax, eax
0x140007420  mov     [rdi], ax
0x140007423  xor     r15d, r15d
0x140007426  mov     rcx, cs:WPP_GLOBAL_Control
0x14000742d  lea     rdx, WPP_GLOBAL_Control
0x140007434  cmp     rcx, rdx
0x140007437  jz      short loc_14000748A
0x140007439  mov     eax, [rcx+2Ch]
0x14000743c  test    al, 4
0x14000743e  jz      short loc_140007458
0x140007440  mov     rcx, [rcx+18h]
0x140007444  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x14000744b  mov     edx, 39h ; '9'
0x140007450  mov     r9, rdi
0x140007453  call    WPP_SF_Z
0x140007458  mov     rcx, cs:WPP_GLOBAL_Control
0x14000745f  lea     rax, WPP_GLOBAL_Control
0x140007466  cmp     rcx, rax
0x140007469  jz      short loc_14000748A
0x14000746b  mov     eax, [rcx+2Ch]
0x14000746e  test    al, 8
0x140007470  jz      short loc_14000748A
0x140007472  mov     rcx, [rcx+18h]
0x140007476  lea     r8, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids
0x14000747d  mov     edx, 3Ah ; ':'
0x140007482  mov     r9d, r15d
0x140007485  call    WPP_SF_d
0x14000748a  mov     eax, r15d
0x14000748d  jmp     loc_14000811A
0x140007492  mov     rax, [r10+20h]
0x140007496  xor     r9d, r9d
0x140007499  bt      ecx, 2
0x14000749d  mov     dword ptr [rbp+37h+DestinationString], r9d
0x1400074a1  lea     r9, [rbp+37h+var_60]
0x1400074a5  lea     rcx, [rbp+37h+var_68]
0x1400074a9  mov     rax, [rax+28h]
0x1400074ad  mov     [rbp+37h+var_48], rax
0x1400074b1  mov     rax, [r10+28h]
0x1400074b5  mov     [rbp+37h+var_50], rax
0x1400074b9  mov     rax, r12
0x1400074bc  cmovnb  r9, rax
0x1400074c0  cmovnb  rcx, rax
0x1400074c4  mov     [rbp+37h+var_B0], r9
0x1400074c8  mov     [rbp+37h+var_A8], rcx
0x1400074cc  jmp     short loc_140007500
0x1400074ce  mov     rcx, [rsp+110h+var_B8]
0x1400074d3  call    HacDereference
0x1400074d8  mov     rax, [rbp+37h+arg_28]
0x1400074dc  mov     qword ptr [rax], 0
0x1400074e3  mov     rdx, [rbp+37h+arg_8]
0x1400074e7  mov     r10, qword ptr [rbp+37h+arg_0]
0x1400074eb  mov     r11, [rsp+110h+var_B8]
0x1400074f0  mov     r8, [rbp+37h+arg_10]
0x1400074f4  mov     rcx, [rbp+37h+var_A8]
0x1400074f8  mov     r9, [rbp+37h+var_B0]
0x1400074fc  nop     dword ptr [rax+00h]
0x140007500  mov     rax, [rbp+37h+arg_48]
0x140007507  cmp     byte ptr [rax], 0
0x14000750a  jnz     loc_140007FC0
0x140007510  xor     eax, eax
0x140007512  mov     [rbx], ax
0x140007515  movzx   eax, word ptr [rsi+0Ch]
0x140007519  mov     [rsi+28h], ax
0x14000751d  mov     eax, [rsi+8]
0x140007520  test    al, 2
0x140007522  jz      loc_14000762C
0x140007528  mov     r10, cs:WPP_GLOBAL_Control
0x14000752f  lea     r8, WPP_GLOBAL_Control
0x140007536  cmp     r10, r8
0x140007539  jz      short loc_14000756C
0x14000753b  mov     eax, [r10+2Ch]
0x14000753f  test    al, 40h
0x140007541  jz      short loc_14000756C
0x140007543  mov     rcx, [r10+18h]
0x140007547  lea     r8, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids
0x14000754e  mov     edx, 0C3h
0x140007553  call    WPP_SF_
0x140007558  mov     r11, [rsp+110h+var_B8]
0x14000755d  lea     r8, WPP_GLOBAL_Control
0x140007564  mov     r9, [rbp+37h+var_B0]
0x140007568  mov     rcx, [rbp+37h+var_A8]
0x14000756c  mov     rdx, [rsi]
0x14000756f  test    rdx, rdx
0x140007572  jz      short loc_1400075E8
  ... truncated ...
```
