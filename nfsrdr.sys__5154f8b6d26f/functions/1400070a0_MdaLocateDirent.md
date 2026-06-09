# MdaLocateDirent

- ea: `0x1400070a0`
- end: `0x140008136`
- name: `MdaLocateDirent`
- size: `4246`
- prototype: `__int64 __fastcall(int, int, int, int, char, __int64, __int64, PUNICODE_STRING DestinationString, PUNICODE_STRING Name, __int64)`
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
  __int64 v19; // rdx
  __int64 v20; // r8
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rdx
  __int64 v24; // r8
  int appended; // r15d
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // rcx
  __int64 v30; // rdi
  __int64 v31; // rdx
  __int64 v32; // r8
  bool v33; // cf
  __int64 *v34; // r9
  __int64 *v35; // rcx
  __int64 v36; // rdx
  __int64 v37; // rax
  int v38; // r9d
  int DirectoryEntry; // eax
  int v40; // eax
  int v41; // r9d
  USHORT v42; // ax
  PWSTR Buffer; // rcx
  int v44; // eax
  __int64 v45; // rdx
  PDEVICE_OBJECT v46; // rcx
  int v47; // eax
  struct _UNICODE_STRING *v48; // rcx
  USHORT Length; // ax
  struct _UNICODE_STRING *v50; // rcx
  BOOLEAN IsNameInExpression; // al
  __int64 v52; // rdx
  __int64 v53; // r8
  unsigned int v54; // ebx
  PWSTR v55; // rax
  __int64 v56; // rax
  __int64 v57; // rax
  __int64 v58; // r8
  __int64 v59; // rdx
  __int64 v60; // rax
  PDEVICE_OBJECT v61; // rdx
  PDEVICE_OBJECT v62; // rcx
  __int64 v63; // r11
  __int64 v64; // rax
  __int64 v65; // rdx
  int v66; // ecx
  PDEVICE_OBJECT v67; // rax
  __int64 v68; // rdx
  __int64 v69; // r8
  PDEVICE_OBJECT v70; // rcx
  struct _KMUTANT *v71; // rcx
  __int64 v72; // rdx
  __int64 v73; // rdx
  __int64 v74; // r8
  __int64 v75; // r8
  int TargetAttributes; // eax
  __int64 v77; // rdx
  __int64 v78; // r8
  __int64 v79; // rcx
  __int64 v80; // rax
  PDEVICE_OBJECT v81; // rbx
  __int64 v82; // rdx
  __int64 v83; // r8
  struct _KMUTANT *Timer; // rcx
  PDEVICE_OBJECT v85; // rdi
  __int64 v86; // rdx
  __int64 v87; // r8
  __int64 v88; // [rsp+50h] [rbp-89h] BYREF
  __int64 v89; // [rsp+58h] [rbp-81h]
  __int64 *v90; // [rsp+60h] [rbp-79h]
  __int64 *v91; // [rsp+68h] [rbp-71h]
  ULONG BytesInUnicodeString[2]; // [rsp+70h] [rbp-69h] BYREF
  int v93; // [rsp+78h] [rbp-61h] BYREF
  PDEVICE_OBJECT v94[2]; // [rsp+80h] [rbp-59h] BYREF
  PCH CustomCPString[2]; // [rsp+90h] [rbp-49h] BYREF
  CHAR *v96; // [rsp+A0h] [rbp-39h] BYREF
  __int64 v97; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v98; // [rsp+B0h] [rbp-29h] BYREF
  __int64 v99; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v100; // [rsp+C0h] [rbp-19h]
  __int64 v101; // [rsp+C8h] [rbp-11h]
  UNICODE_STRING String2; // [rsp+D0h] [rbp-9h] BYREF
  struct _MRX_FCB_ *v104; // [rsp+128h] [rbp+4Fh]
  __int64 *v105; // [rsp+130h] [rbp+57h]
  int DestinationStringa; // [rsp+158h] [rbp+7Fh]
  unsigned int DestinationStringb; // [rsp+158h] [rbp+7Fh]

  v105 = a3;
  v104 = (struct _MRX_FCB_ *)a2;
  v10 = *(_QWORD *)(a2 + 80);
  v11 = 0;
  v12 = 0;
  v93 = 0;
  v13 = 0;
  v96 = 0;
  v14 = 0;
  v99 = 0;
  v98 = 0;
  LOBYTE(v88) = 0;
  v16 = a1;
  v97 = 0;
  *(_OWORD *)CustomCPString = 0;
  v89 = v10;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 53, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    LODWORD(a2) = (_DWORD)v104;
    v16 = a1;
    v10 = v89;
    a3 = v105;
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
        HacReference(v105[1]);
        HacAcquireLock(v105[1], v19, v20);
        *a6 = v105[1];
        KeReleaseMutex(*(PRKMUTEX *)(v105[1] + 40), 0);
        Name->Length = 0;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
          return 0;
        v22 = 54;
LABEL_19:
        WPP_SF_d(v21->AttachedDevice, v22, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
        return 0;
      }
    }
    else if ( DestinationString->Length == 4 && *(_DWORD *)DestinationString->Buffer == 3014702 )
    {
      HacReference(*v105);
      HacAcquireLock(*v105, v23, v24);
      *a6 = *v105;
      KeReleaseMutex(*(PRKMUTEX *)(*v105 + 40), 0);
      Name->Length = 0;
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
        return 0;
      v22 = 55;
      goto LABEL_19;
    }
    appended = RtlAppendUnicodeStringToString((PUNICODE_STRING)(a4 + 5), DestinationString);
    if ( appended >= 0 )
    {
      appended = CaseInsensitiveLookup(a1, (_DWORD)v104, (int)a4 + 40, v105[1], a5, (__int64)a6);
      if ( appended >= 0 )
      {
        HacAcquireLock(*a6, v27, v28);
        v29 = *a6;
        if ( *(_DWORD *)(*a6 + 128) == 5 && a7 )
        {
          v30 = v105[1];
          KeReleaseMutex(*(PRKMUTEX *)(v29 + 40), 0);
          appended = MdaFindTargetAttributes(a1, v104, *a6, a5, a7, &v88, a10);
          if ( appended >= 0 )
          {
            if ( (_BYTE)v88 )
            {
              HacDereference(v89, *a6);
              HacReference(v30);
              HacAcquireLock(v30, v31, v32);
              *a6 = v30;
              KeReleaseMutex(*(PRKMUTEX *)(v30 + 40), 0);
            }
          }
          else
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 56, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
            HacDereference(v89, *a6);
            *a6 = 0;
          }
        }
        else
        {
          KeReleaseMutex(*(PRKMUTEX *)(v29 + 40), 0);
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
  v33 = (a4[1] & 4) != 0;
  DestinationStringa = 0;
  v34 = &v98;
  v35 = &v97;
  v101 = *(_QWORD *)(*(_QWORD *)(v16 + 32) + 40LL);
  v100 = *(_QWORD *)(v16 + 40);
  if ( !v33 )
  {
    v34 = 0;
    v35 = 0;
  }
  v90 = v34;
  v91 = v35;
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
              v10 = v89;
              v34 = v90;
              v35 = v91;
            }
            v36 = *a4;
            if ( *a4 )
            {
              v12 = *(CHAR **)(v36 + 256);
              v37 = *(_QWORD *)(v36 + 72);
              v11 = *(_DWORD *)(v36 + 88);
              v96 = v12;
              v99 = v37;
              v93 = v11;
              if ( v35 )
              {
                *v35 = 0;
                v13 = v97;
              }
              if ( v34 )
              {
                *v34 = 0;
                v14 = v98;
              }
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 197, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
                v10 = v89;
              }
              v38 = 0;
            }
            else
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 )
              {
                WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 196, WPP_9f5d595fe98735cd2eac9181671fbbfa_Traceguids);
                v10 = v89;
              }
              v38 = -1073741811;
            }
            *((_DWORD *)a4 + 2) &= ~2u;
            DestinationStringb = v38;
          }
          else
          {
            DirectoryEntry = NfsReadDirectoryEntry(
                               v16,
                               a2,
                               a3[1],
                               (_DWORD)a4,
                               1,
                               (__int64)&v99,
                               (__int64)&v96,
                               (__int64)&v93,
                               (__int64)v35,
                               (__int64)v34);
            v10 = v89;
            v12 = v96;
            v38 = DirectoryEntry;
            v11 = v93;
            v13 = v97;
            v14 = v98;
            DestinationStringb = DirectoryEntry;
          }
          if ( v38 < 0 )
          {
            v54 = DestinationStringb;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
            {
              WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 59, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
            }
            if ( DestinationStringb != -2147483642 )
            {
              LOBYTE(v36) = 1;
              NfsReadDirectoryQuit(a4, v36);
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
            v54 = -1073741823;
            goto LABEL_161;
          }
          LOWORD(CustomCPString[0]) = v11;
          CustomCPString[1] = v12;
          v40 = *(_DWORD *)(v100 + 32);
          if ( (v40 & 0x14000) != 0 )
          {
            BytesInUnicodeString[0] = 0;
            DestinationStringa = LoadCodePageTable(v10, 0x3B5u, &KscTableInfo, &KscTableBase);
            v41 = DestinationStringa;
            if ( DestinationStringa >= 0 )
            {
              DestinationStringa = RtlCustomCPToUnicodeN(
                                     &KscTableInfo,
                                     DestinationString->Buffer,
                                     DestinationString->MaximumLength - 2,
                                     BytesInUnicodeString,
                                     CustomCPString[1],
                                     LOWORD(CustomCPString[0]));
              v41 = DestinationStringa;
              if ( DestinationStringa >= 0 )
              {
                v42 = BytesInUnicodeString[0];
                if ( BytesInUnicodeString[0] >= (unsigned __int64)DestinationString->MaximumLength - 2 )
                  v42 = DestinationString->MaximumLength - 2;
                Buffer = DestinationString->Buffer;
                DestinationString->Length = v42;
                Buffer[(unsigned __int64)v42 >> 1] = 0;
              }
            }
          }
          else
          {
            if ( (v40 & 0x8040) != 0 )
            {
              v44 = NfsConvertDbcsToUnicode(
                      v10,
                      (int)DestinationString,
                      (int)CustomCPString,
                      0,
                      &ShiftJisTableInfo,
                      (__int64)&ShiftJisTableBase,
                      932);
            }
            else if ( (v40 & 0x20000) != 0 )
            {
              v44 = NfsConvertDbcsToUnicode(
                      v10,
                      (int)DestinationString,
                      (int)CustomCPString,
                      0,
                      &Big5TableInfo,
                      (__int64)&Big5TableBase,
                      950);
            }
            else if ( (v40 & 0x2000) != 0 )
            {
              v44 = NfsConvertDbcsToUnicode(
                      v10,
                      (int)DestinationString,
                      (int)CustomCPString,
                      0,
                      &CnsTableInfo,
                      (__int64)&CnsTableBase,
                      20000);
            }
            else
            {
              v44 = (v40 & 0x40000) != 0
                  ? NfsConvertDbcsToUnicode(
                      v10,
                      (int)DestinationString,
                      (int)CustomCPString,
                      0,
                      &GBTableInfo,
                      (__int64)&GBTableBase,
                      936)
                  : RtlAnsiStringToUnicodeString(DestinationString, (PCANSI_STRING)CustomCPString, 0);
            }
            v41 = v44;
            DestinationStringa = v44;
          }
          if ( v41 >= 0 )
            break;
          LODWORD(v16) = a1;
          LODWORD(a2) = (_DWORD)v104;
          v10 = v89;
          a3 = v105;
          v35 = v91;
          *(_QWORD *)BytesInUnicodeString = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            v45 = 61;
LABEL_88:
            v46 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
            goto LABEL_89;
          }
LABEL_44:
          v34 = v90;
        }
        Name->Length = 0;
        v47 = *((_DWORD *)a4 + 2);
        if ( (v47 & 8) != 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          }
          goto LABEL_111;
        }
        v48 = (struct _UNICODE_STRING *)(a4 + 3);
        if ( (v47 & 1) != 0 )
          break;
        Length = v48->Length;
        LODWORD(a2) = (_DWORD)v104;
        LODWORD(v16) = a1;
        v10 = v89;
        a3 = v105;
        v34 = v90;
        v35 = v91;
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
      if ( FsRtlIsNameInExpression(v48, DestinationString, 1u, 0) )
        goto LABEL_111;
      LODWORD(a2) = (_DWORD)v104;
      LODWORD(v16) = a1;
      v10 = v89;
      a3 = v105;
      v34 = v90;
      v35 = v91;
      if ( Name->Length )
      {
        v50 = (struct _UNICODE_STRING *)(a4 + 3);
        if ( Name->Length == 4 && *(_DWORD *)Name->Buffer == 3014702 && v50->Length > 1u )
          Name->Length = 1;
        IsNameInExpression = FsRtlIsNameInExpression(v50, Name, 1u, 0);
        LODWORD(a2) = (_DWORD)v104;
        LODWORD(v16) = a1;
        v10 = v89;
        a3 = v105;
        v34 = v90;
        v35 = v91;
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
        HacReference(v105[1]);
        HacAcquireLock(v105[1], v52, v53);
        *a6 = v105[1];
        KeReleaseMutex(*(PRKMUTEX *)(v105[1] + 40), 0);
        v54 = 0;
        goto LABEL_161;
      }
    }
    else if ( DestinationString->Length == 4 )
    {
      v55 = DestinationString->Buffer;
      if ( *v55 == 46 && v55[1] == 46 )
      {
        HacReference(*v105);
        HacAcquireLock(*v105, v77, v78);
        v79 = *v105;
        *a6 = *v105;
        if ( (unsigned __int8)HacIsEntryFake(v79) && v14 )
        {
          v80 = *a6;
          *(_OWORD *)(v80 + 128) = *(_OWORD *)v14;
          *(_OWORD *)(v80 + 144) = *(_OWORD *)(v14 + 16);
          *(_OWORD *)(v80 + 160) = *(_OWORD *)(v14 + 32);
          *(_OWORD *)(v80 + 176) = *(_OWORD *)(v14 + 48);
          *(_OWORD *)(v80 + 192) = *(_OWORD *)(v14 + 64);
          *(_QWORD *)(v80 + 208) = *(_QWORD *)(v14 + 80);
        }
        KeReleaseMutex(*(PRKMUTEX *)(*v105 + 40), 0);
        v54 = 0;
        goto LABEL_161;
      }
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 65, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids, a4 + 5);
    if ( !v13 || !v14 )
      break;
    v56 = v101;
    *((_WORD *)a4 + 20) -= 2;
    v57 = HacAllocate(v89, *(_QWORD *)(v56 + 72), a4 + 5, DestinationString);
    *(_QWORD *)BytesInUnicodeString = v57;
    v59 = v57;
    if ( v57 )
    {
      *(_OWORD *)(v57 + 216) = *(_OWORD *)v13;
      *(_OWORD *)(v57 + 232) = *(_OWORD *)(v13 + 16);
      *(_OWORD *)(v57 + 248) = *(_OWORD *)(v13 + 32);
      *(_OWORD *)(v57 + 264) = *(_OWORD *)(v13 + 48);
      *(_DWORD *)(v57 + 280) = *(_DWORD *)(v13 + 64);
      *(_OWORD *)(v57 + 128) = *(_OWORD *)v14;
      *(_OWORD *)(v57 + 144) = *(_OWORD *)(v14 + 16);
      *(_OWORD *)(v57 + 160) = *(_OWORD *)(v14 + 32);
      *(_OWORD *)(v57 + 176) = *(_OWORD *)(v14 + 48);
      *(_OWORD *)(v57 + 192) = *(_OWORD *)(v14 + 64);
      *(_QWORD *)(v57 + 208) = *(_QWORD *)(v14 + 80);
      v60 = *a4;
      String2 = 0;
      *(_QWORD *)(v59 + 120) = *(_QWORD *)(v60 + 56);
      v94[0] = (PDEVICE_OBJECT)v105[1];
      HacAcquireLock(v59, v59, v58);
      v61 = v94[0];
      if ( v94[0] )
      {
        v62 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
        *(_DWORD *)(*(_QWORD *)BytesInUnicodeString + 104LL) = v94[0]->Queue.Wcb.CurrentIrp;
        HIDWORD(v62->Queue.Wcb.DeviceRoutine) = v61->Dpc.TargetInfoAsUlong;
        LODWORD(v62->Queue.Wcb.DeviceContext) = *((_DWORD *)&v61->Dpc.0 + 1);
      }
      else
      {
        MdaDissectNameTail(*(_QWORD *)BytesInUnicodeString + 64LL, &String2, v94);
        v64 = HacQueryAndReference(*(PRKMUTEX *)(v63 + 40), &String2);
        v65 = v64;
        if ( v64 )
        {
          v66 = *(_DWORD *)(v64 + 136);
          v67 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
          *(_DWORD *)(*(_QWORD *)BytesInUnicodeString + 104LL) = v66;
          HIDWORD(v67->Queue.Wcb.DeviceRoutine) = *(_DWORD *)(v65 + 200);
          LODWORD(v67->Queue.Wcb.DeviceContext) = *(_DWORD *)(v65 + 204);
          HacDereference(v89, v65);
        }
        v62 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
      }
      KeReleaseMutex((PRKMUTEX)v62->Timer, 0);
      HacInsertEntry(v89, *(_QWORD *)BytesInUnicodeString);
      HacAcquireLock(*(_QWORD *)BytesInUnicodeString, v68, v69);
      v70 = *(PDEVICE_OBJECT *)BytesInUnicodeString;
      if ( *(_DWORD *)(*(_QWORD *)BytesInUnicodeString + 128LL) == 5 && a7 )
      {
        v71 = *(struct _KMUTANT **)(*(_QWORD *)BytesInUnicodeString + 40LL);
        v94[0] = (PDEVICE_OBJECT)v105[1];
        KeReleaseMutex(v71, 0);
        DestinationStringa = MdaFindTargetAttributes(a1, v104, *(__int64 *)BytesInUnicodeString, a5, a7, &v88, a10);
        if ( DestinationStringa < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
          }
          v72 = *(_QWORD *)BytesInUnicodeString;
LABEL_42:
          HacDereference(v89, v72);
          *a6 = 0;
          goto LABEL_43;
        }
        if ( !(_BYTE)v88 )
        {
          v54 = DestinationStringa;
          *a6 = *(_QWORD *)BytesInUnicodeString;
          goto LABEL_161;
        }
        HacDereference(v89, *(_QWORD *)BytesInUnicodeString);
        v81 = v94[0];
        HacReference(v94[0]);
        HacAcquireLock(v81, v82, v83);
        *a6 = (__int64)v81;
        Timer = (struct _KMUTANT *)v81->Timer;
      }
      else
      {
        *a6 = *(_QWORD *)BytesInUnicodeString;
        Timer = (struct _KMUTANT *)v70->Timer;
      }
LABEL_159:
      KeReleaseMutex(Timer, 0);
LABEL_160:
      v54 = DestinationStringa;
      goto LABEL_161;
    }
    LODWORD(v16) = a1;
    LODWORD(a2) = (_DWORD)v104;
    v10 = v89;
    a3 = v105;
    v34 = v90;
    v35 = v91;
    *(_QWORD *)BytesInUnicodeString = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v45 = 66;
      goto LABEL_88;
    }
  }
  DestinationStringa = RtlAppendUnicodeStringToString((PUNICODE_STRING)(a4 + 5), DestinationString);
  if ( DestinationStringa < 0 )
  {
    LODWORD(v16) = a1;
    LODWORD(a2) = (_DWORD)v104;
    v10 = v89;
    a3 = v105;
    v35 = v91;
    v94[0] = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      v46 = v94[0];
      v45 = 68;
      goto LABEL_89;
    }
    goto LABEL_44;
  }
  DestinationStringa = NfsLookup(a1, (__int64)v104, (const UNICODE_STRING *)(a4 + 5), v105[1], a5, a6);
  if ( DestinationStringa < 0 )
  {
    LODWORD(v16) = a1;
    LODWORD(a2) = (_DWORD)v104;
    v10 = v89;
    a3 = v105;
    v35 = v91;
    v94[0] = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v46 = v94[0];
      v45 = 69;
LABEL_89:
      WPP_SF_d(v46->AttachedDevice, v45, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
LABEL_43:
      LODWORD(a2) = (_DWORD)v104;
      LODWORD(v16) = a1;
      v10 = v89;
      a3 = v105;
      v35 = v91;
      goto LABEL_44;
    }
    goto LABEL_44;
  }
  HacAcquireLock(*a6, v73, v74);
  v75 = *a6;
  if ( *(_DWORD *)(*a6 + 128) != 5 || !a7 )
  {
    Timer = *(struct _KMUTANT **)(v75 + 40);
    goto LABEL_159;
  }
  v94[0] = (PDEVICE_OBJECT)v105[1];
  KeReleaseMutex(*(PRKMUTEX *)(v75 + 40), 0);
  TargetAttributes = MdaFindTargetAttributes(a1, v104, *a6, a5, a7, &v88, a10);
  DestinationStringa = TargetAttributes;
  if ( TargetAttributes < 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 70, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    v72 = *a6;
    goto LABEL_42;
  }
  if ( (_BYTE)v88 )
  {
    HacDereference(v89, *a6);
    v85 = v94[0];
    HacReference(v94[0]);
    HacAcquireLock(v85, v86, v87);
    *a6 = (__int64)v85;
    Timer = (struct _KMUTANT *)v85->Timer;
    goto LABEL_159;
  }
  v54 = TargetAttributes;
LABEL_161:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 71, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 72, WPP_c4d8736813ae3e7b4796d167662a6148_Traceguids);
  }
  return v54;
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
