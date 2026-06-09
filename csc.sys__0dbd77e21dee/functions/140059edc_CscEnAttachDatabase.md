# CscEnAttachDatabase

- ea: `0x140059edc`
- end: `0x14005adb4`
- name: `CscEnAttachDatabase`
- size: `3800`
- prototype: `__int64 __fastcall(_QWORD *, BOOL *, const UNICODE_STRING *, int, char, __int64, __int64, __int64)`
- caller_count: `2`
- callee_count: `37`
- tags: `file_ops, authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140015b28`
- `0x140046e48`

## callees

- `0x14000a64c`
- `0x14000b9d0`
- `0x14000ccc0`
- `0x14000d744`
- `0x14000dc9c`
- `0x140011d18`
- `0x14001266c`
- `0x1400140a4`
- `0x140015a84`
- `0x1400173e8`
- `0x140017e0c`
- `0x140017ebc`
- `0x140017f10`
- `0x140018388`
- `0x1400185f4`
- `0x140018df4`
- `0x140018fd0`
- `0x1400192ec`
- `0x140024894`
- `0x1400248e4`
- `0x1400269c4`
- `0x1400273fc`
- `0x140029cf0`
- `0x14002a780`
- `0x14002a864`
- `0x14002b7a8`
- `0x14002b814`
- `0x14002f010`
- `0x14002f440`
- `0x140046584`
- `0x1400487a8`
- `0x140049f48`
- `0x140059edc`
- `0x14005c004`
- `0x14006d870`
- `0x14008a4ac`
- `0x14008df70`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14005a0eb`
- `ntoskrnl!ExAllocatePool2` at `0x14005a179`
- `ntoskrnl!ExAllocatePool2` at `0x14005a1d4`
- `ntoskrnl!ExAllocatePool2` at `0x14005a0eb`
- `ntoskrnl!ExAllocatePool2` at `0x14005a179`
- `ntoskrnl!ExAllocatePool2` at `0x14005a1d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a1ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a209`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a1ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a209`
- `ntoskrnl!ZwClose` at `0x14005a40e`
- `ntoskrnl!ZwClose` at `0x14005aa59`
- `ntoskrnl!ZwClose` at `0x14005a40e`
- `ntoskrnl!ZwClose` at `0x14005aa59`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005a194`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005a1ef`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005a194`
- `ntoskrnl!ExInitializeResourceLite` at `0x14005a1ef`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14005a247`
- `ntoskrnl!RtlDuplicateUnicodeString` at `0x14005a247`

## string_xrefs

- `0x140059f46`: `sm.temp`

## pseudocode

```c
__int64 __fastcall CscEnAttachDatabase(
        _QWORD *a1,
        BOOL *a2,
        const UNICODE_STRING *a3,
        int a4,
        char a5,
        __int64 a6,
        __int64 a7,
        __int64 a8)
{
  int v8; // esi
  int v10; // r8d
  struct _LIST_ENTRY *v11; // r14
  _DWORD *v12; // rdi
  int v13; // ebx
  int TunnelCache; // ebx
  BOOL v15; // r15d
  char v16; // r12
  _DWORD *Pool2; // rax
  int v18; // edx
  unsigned int v19; // ecx
  int v20; // r9d
  int v21; // r8d
  int v22; // eax
  struct _ERESOURCE *v23; // rax
  struct _ERESOURCE *v24; // r15
  struct _ERESOURCE *v25; // rax
  struct _ERESOURCE *v26; // r15
  struct _LIST_ENTRY *v27; // r15
  struct _LIST_ENTRY **v28; // r13
  __int64 v29; // rdx
  int DiskSpaceInformationPoster; // eax
  __int64 v31; // rdx
  char v32; // r11
  __int64 v33; // rax
  __int64 v34; // rdx
  __int64 v35; // r14
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // r10
  __int64 v39; // rcx
  __int64 v40; // r8
  PCUNICODE_STRING v41; // rax
  __int128 v42; // xmm0
  int FullEaBuffer; // eax
  unsigned __int64 *v44; // r15
  __int64 v45; // rdx
  __int64 v46; // rcx
  __int64 v47; // r8
  __int64 v48; // r9
  struct _LIST_ENTRY *v49; // rax
  _QWORD *v50; // r13
  __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // rax
  int v54; // eax
  __int64 v55; // r8
  __int16 Flink_high; // ax
  __int64 v57; // rax
  __int64 v58; // rcx
  __int64 v59; // r8
  UUID *v60; // rcx
  int v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rdx
  _QWORD *v64; // r15
  __int64 v65; // r9
  char v67; // [rsp+71h] [rbp-8Fh]
  char v68; // [rsp+71h] [rbp-8Fh]
  int v69; // [rsp+74h] [rbp-8Ch]
  char v70; // [rsp+78h] [rbp-88h]
  char v71; // [rsp+79h] [rbp-87h] BYREF
  char v72; // [rsp+7Ah] [rbp-86h] BYREF
  char v73; // [rsp+7Bh] [rbp-85h] BYREF
  char v74[4]; // [rsp+7Ch] [rbp-84h] BYREF
  struct _LIST_ENTRY *v75; // [rsp+80h] [rbp-80h] BYREF
  int v76; // [rsp+88h] [rbp-78h] BYREF
  int v77; // [rsp+8Ch] [rbp-74h]
  int v78; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v79; // [rsp+94h] [rbp-6Ch] BYREF
  struct _LIST_ENTRY v80; // [rsp+98h] [rbp-68h] BYREF
  PCUNICODE_STRING StringIn; // [rsp+A8h] [rbp-58h] BYREF
  struct _LIST_ENTRY v82; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v83; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v84; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v85; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v86; // [rsp+E8h] [rbp-18h] BYREF
  struct _LIST_ENTRY v87; // [rsp+F8h] [rbp-8h] BYREF
  const wchar_t *v88; // [rsp+108h] [rbp+8h]
  _QWORD v89[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v90[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v91[2]; // [rsp+130h] [rbp+30h] BYREF
  struct _LIST_ENTRY v92; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v93; // [rsp+150h] [rbp+50h]
  BOOL *v94; // [rsp+158h] [rbp+58h]
  struct _UNICODE_STRING UnicodeString; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v96[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 Flink; // [rsp+180h] [rbp+80h]
  __int128 v98; // [rsp+190h] [rbp+90h]
  __int64 v99; // [rsp+1A0h] [rbp+A0h]
  _OWORD v100[6]; // [rsp+1B0h] [rbp+B0h] BYREF
  _OWORD v101[2]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v102; // [rsp+230h] [rbp+130h]
  __int64 v103; // [rsp+240h] [rbp+140h]
  _OWORD v104[8]; // [rsp+250h] [rbp+150h] BYREF
  __int64 *v105[6]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v106; // [rsp+300h] [rbp+200h] BYREF
  char v107; // [rsp+330h] [rbp+230h] BYREF

  v92.Blink = (struct _LIST_ENTRY *)L"namespace";
  StringIn = a3;
  v89[1] = L"pq";
  v8 = (int)a3;
  v94 = a2;
  v91[1] = L"sm";
  v93 = a1;
  v90[1] = L"sm.temp";
  v69 = 0;
  v88 = L"temp";
  v80.Blink = 0;
  v70 = 0;
  UnicodeString = 0;
  v82.Flink = 0;
  v87.Flink = 0;
  v80.Flink = 0;
  v92.Flink = (struct _LIST_ENTRY *)1310738;
  v89[0] = 393220;
  v91[0] = 393220;
  v90[0] = 1048590;
  v87.Blink = (struct _LIST_ENTRY *)655368;
  memset(v100, 0, 0x58u);
  memset(v104, 0, sizeof(v104));
  v75 = 0;
  v103 = 0;
  v76 = 0;
  *((_QWORD *)&v85 + 1) = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Database";
  v11 = 0;
  v72 = 0;
  *((_QWORD *)&v84 + 1) = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.EpochEa";
  v12 = 0;
  v71 = 0;
  *((_QWORD *)&v86 + 1) = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.DatabaseEx1";
  memset(v101, 0, sizeof(v101));
  v74[0] = 0;
  v73 = 0;
  v102 = 0;
  v83 = 0;
  *(_QWORD *)&v85 = 3276849;
  *(_QWORD *)&v84 = 3211312;
  v79 = 0;
  v78 = 0;
  v82.Blink = 0;
  *(_QWORD *)&v86 = 3473460;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Zd(WPP_GLOBAL_Control->AttachedDevice, 24, v10, v8, a4);
  if ( a4 )
  {
    v13 = a4 - 1;
    if ( !v13 )
    {
      v67 = 0;
      v77 = 1;
      goto LABEL_12;
    }
    if ( v13 != 1 )
    {
LABEL_7:
      TunnelCache = -1073741811;
      v15 = 0;
      v16 = 0;
      goto LABEL_42;
    }
  }
  else
  {
    v70 = 1;
  }
  if ( !*(_DWORD *)a6 )
    goto LABEL_7;
  v77 = 3;
  v67 = 1;
LABEL_12:
  Pool2 = (_DWORD *)ExAllocatePool2(256, 352, 658535235);
  v83 = Pool2;
  v12 = Pool2;
  if ( !Pool2 )
  {
    TunnelCache = -1073741670;
    goto LABEL_121;
  }
  *Pool2 = 23124486;
  CscDiffTransferGetDiffTransferHandleAllocationInformation(&v79, &v78);
  v18 = v78;
  v19 = v79;
  v20 = v78 - 1;
  v21 = ~(v78 - 1);
  v22 = v21 & (v78 + 511);
  v12[87] = v22;
  v12[86] = v19 + v22;
  if ( !v18 || (v18 & v20) != 0 || (v21 & v19) != v19 || v19 + v22 <= v19 )
  {
LABEL_122:
    TunnelCache = -1073740768;
    goto LABEL_123;
  }
  v23 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 574649155);
  v24 = v23;
  if ( !v23 )
  {
    TunnelCache = -1073741670;
    goto LABEL_120;
  }
  TunnelCache = ExInitializeResourceLite(v23);
  if ( TunnelCache < 0 )
  {
    ExFreePoolWithTag(v24, 0x22407343u);
LABEL_120:
    *((_QWORD *)v12 + 15) = 0;
    goto LABEL_121;
  }
  *((_QWORD *)v12 + 15) = v24;
  v25 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 574649155);
  v26 = v25;
  if ( !v25 )
  {
    TunnelCache = -1073741670;
    goto LABEL_118;
  }
  TunnelCache = ExInitializeResourceLite(v25);
  if ( TunnelCache < 0 )
  {
    ExFreePoolWithTag(v26, 0x22407343u);
LABEL_118:
    *((_QWORD *)v12 + 1) = 0;
LABEL_121:
    v15 = 0;
    v16 = 0;
    goto LABEL_42;
  }
  *((_QWORD *)v12 + 1) = v26;
  TunnelCache = CscStTuCreateTunnelCache(v12 + 10);
  if ( TunnelCache < 0 )
    goto LABEL_121;
  v27 = (struct _LIST_ENTRY *)StringIn;
  TunnelCache = RtlDuplicateUnicodeString(0, StringIn, (PUNICODE_STRING)(v12 + 18));
  if ( TunnelCache < 0 )
    goto LABEL_121;
  TunnelCache = CscEnpCreateVersionString(v12 + 22);
  if ( TunnelCache < 0 )
    goto LABEL_121;
  v28 = (struct _LIST_ENTRY **)(v12 + 6);
  TunnelCache = CscSeCreateSecurityDescriptor(v12 + 6);
  if ( TunnelCache < 0 )
  {
    v15 = 0;
LABEL_28:
    v16 = 0;
    goto LABEL_42;
  }
  TunnelCache = CscStorepLowIoCreateFilePoster(&v82, 0, v27, -2146435072, 0, 0, 3, v77, 33, 0, 0, *v28, &v80);
  v15 = 0;
  if ( TunnelCache < 0 )
    goto LABEL_28;
  v15 = v80.Flink == (struct _LIST_ENTRY *)2;
  v69 = v15;
  if ( !v67 )
    goto LABEL_52;
  DiskSpaceInformationPoster = CscStorepLowIoGetDiskSpaceInformationPoster(v82.Flink, v29, &v82.Blink);
  v32 = 0;
  TunnelCache = DiskSpaceInformationPoster;
  if ( DiskSpaceInformationPoster < 0 )
  {
LABEL_32:
    v16 = v32;
    goto LABEL_42;
  }
  LOBYTE(v31) = *(_BYTE *)a6;
  v33 = CscStPercentify(v82.Blink, v31);
  LOBYTE(v34) = *(_BYTE *)(a6 + 4);
  v35 = v33;
  StringIn = (PCUNICODE_STRING)CscStPercentify(v33, v34);
  v82.Blink = (struct _LIST_ENTRY *)CscStPercentify(v36, (unsigned __int8)(100 - *(_BYTE *)(a6 + 8)));
  if ( !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(v37, v38, v82.Blink) )
  {
    TunnelCache = -1073741811;
    goto LABEL_32;
  }
  if ( !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(v39, v40, v40) )
  {
    TunnelCache = -1073741811;
    goto LABEL_32;
  }
  TunnelCache = CscStUtGenerateGuid((UUID *)(v12 + 66));
  if ( TunnelCache >= 0 )
  {
    TunnelCache = CscStUtGenerateGuid((UUID *)(v12 + 81));
    if ( TunnelCache >= 0 )
    {
      v41 = StringIn;
      *((_QWORD *)v12 + 19) = v35;
      *((_QWORD *)v12 + 20) = v41;
      *((_QWORD *)v12 + 21) = v82.Blink;
      memset((char *)v100 + 8, 0, 0x50u);
      memset((char *)v104 + 8, 0, 0x78u);
      *(_QWORD *)&v104[0] = 0x58005002000006LL;
      *(_QWORD *)&v100[0] = 0x58005002000006LL;
      v100[1] = *(_OWORD *)(v12 + 38);
      *((_QWORD *)&v104[0] + 1) = *((_QWORD *)v12 + 21);
      v42 = *(_OWORD *)(v12 + 66);
      v103 = 0;
      v101[0] = 0x38001002000006uLL;
      v101[1] = 0;
      v100[4] = v42;
      v102 = 0;
      *(_OWORD *)((char *)v101 + 8) = *(_OWORD *)(v12 + 81);
      CscEaInitializeFullEntry((unsigned int)v105, (unsigned int)&v85, (unsigned int)v100, 88, 0);
      CscEaInitializeFullEntry((unsigned int)&v106, (unsigned int)&v86, (unsigned int)v104, 128, (__int64)v105);
      CscEaInitializeFullEntry((unsigned int)&v107, (unsigned int)&v84, (unsigned int)v101, 56, (__int64)v105);
      FullEaBuffer = CscEaCreateFullEaBuffer(v105, (__int64 *)&v75, (unsigned int *)&v76);
      v11 = v75;
      TunnelCache = FullEaBuffer;
      if ( FullEaBuffer >= 0 )
      {
        while ( 1 )
        {
LABEL_52:
          v44 = (unsigned __int64 *)(v12 + 4);
          TunnelCache = CscStorepLowIoCreateFilePoster(
                          (struct _LIST_ENTRY *)v12 + 1,
                          v82.Flink,
                          (struct _LIST_ENTRY *)(v12 + 22),
                          -2146435072,
                          0,
                          0,
                          3,
                          v77,
                          33,
                          v11,
                          v76,
                          *v28,
                          &v80);
          if ( TunnelCache < 0 )
          {
            v16 = 0;
            goto LABEL_124;
          }
          if ( !v70 )
            break;
          TunnelCache = CscStOrphanerGenerateTemporaryFileName(v46, v45, v47, &UnicodeString);
          if ( TunnelCache < 0 )
            goto LABEL_51;
          v49 = (struct _LIST_ENTRY *)*v44;
          *v44 = 0;
          LOBYTE(v48) = 1;
          v80.Blink = v49;
          TunnelCache = CscStorepLowIoRenameFilePoster(v49, v82.Flink, &UnicodeString, v48);
          if ( TunnelCache < 0 )
            goto LABEL_51;
          v70 = 0;
        }
        v68 = 0;
        if ( v80.Flink != (struct _LIST_ENTRY *)1 )
        {
          if ( v80.Flink != (struct _LIST_ENTRY *)2 )
            goto LABEL_122;
          v69 = 3;
          goto LABEL_62;
        }
        if ( v11 )
          CscEaFreeFullEaBuffer((void **)&v75);
        v52 = CscEaReadVariableSizeEa(*v44, &v85, (__int64 *)&v75, &v76);
        v11 = v75;
        TunnelCache = v52;
        if ( v52 < 0 )
          goto LABEL_123;
        if ( HIWORD(v75->Flink) != 88 )
        {
          TunnelCache = -1073741596;
          goto LABEL_123;
        }
        v53 = BYTE5(v75->Flink);
        v100[0] = *(_OWORD *)((char *)&v75->Blink + v53 + 1);
        v100[1] = *(struct _LIST_ENTRY *)((char *)v75 + v53 + 25);
        v100[2] = *(struct _LIST_ENTRY *)((char *)v75 + v53 + 41);
        v100[3] = *(struct _LIST_ENTRY *)((char *)v75 + v53 + 57);
        v100[4] = *(struct _LIST_ENTRY *)((char *)v75 + v53 + 73);
        *(_QWORD *)&v100[5] = *(struct _LIST_ENTRY **)((char *)&v75[5].Blink + v53 + 1);
        CscEaFreeFullEaBuffer((void **)&v75);
        TunnelCache = CscEnpCheckEaVersion(v100, 5767248);
        if ( TunnelCache < 0 )
        {
          v11 = v75;
          goto LABEL_123;
        }
        v54 = CscEaReadVariableSizeEa(*v44, &v86, (__int64 *)&v75, &v76);
        v11 = v75;
        TunnelCache = v54;
        if ( v54 < 0 )
          goto LABEL_123;
        Flink_high = HIWORD(v75->Flink);
        if ( Flink_high )
        {
          if ( Flink_high != 128 )
          {
            TunnelCache = -1073741596;
            goto LABEL_123;
          }
          v57 = BYTE5(v75->Flink);
          LOBYTE(v55) = 1;
          v104[0] = *(_OWORD *)((char *)&v75->Blink + v57 + 1);
          v104[1] = *(struct _LIST_ENTRY *)((char *)v75 + v57 + 25);
          v104[2] = *(struct _LIST_ENTRY *)((char *)v75 + v57 + 41);
          v104[3] = *(struct _LIST_ENTRY *)((char *)v75 + v57 + 57);
          v104[4] = *(struct _LIST_ENTRY *)((char *)v75 + v57 + 73);
          v104[5] = *(struct _LIST_ENTRY *)((char *)v75 + v57 + 89);
          v104[6] = *(struct _LIST_ENTRY *)((char *)v75 + v57 + 105);
          v104[7] = *(struct _LIST_ENTRY *)((char *)v75 + v57 + 121);
        }
        else
        {
          LOBYTE(v55) = 0;
        }
        if ( !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(*(_QWORD *)&v100[1], *((_QWORD *)&v100[1] + 1), v55) )
        {
          TunnelCache = -1073741596;
          goto LABEL_123;
        }
        if ( (_BYTE)v59 && !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(v58, *((_QWORD *)&v104[0] + 1), v59) )
        {
          TunnelCache = -1073741596;
          goto LABEL_123;
        }
        v60 = (UUID *)(v12 + 66);
        v12[36] = DWORD2(v100[0]);
        *(_OWORD *)(v12 + 38) = v100[1];
        *((_OWORD *)v12 + 12) = v100[2];
        *(_OWORD *)(v12 + 66) = v100[4];
        v12[80] = v100[5];
        if ( (_BYTE)v59 )
        {
          *((_QWORD *)v12 + 21) = *((_QWORD *)&v104[0] + 1);
          *((_QWORD *)v12 + 26) = *(_QWORD *)&v104[1];
        }
        v61 = v12[36];
        if ( (v61 & 0x10) != 0 )
        {
          v12[36] = v61 & 0xFFFFFFEF;
          *v60 = 0;
        }
        v62 = *(_QWORD *)&v60->Data1;
        v84 = 0;
        if ( !v62 )
          v62 = *((_QWORD *)v12 + 34) - *((_QWORD *)&v84 + 1);
        if ( v62 )
        {
          if ( (v12[36] & 8) != 0 )
          {
            *(_OWORD *)(v12 + 54) = v100[3];
            v68 = 1;
            if ( (_BYTE)v59 )
              *((_QWORD *)v12 + 29) = *((_QWORD *)&v104[1] + 1);
          }
        }
        else
        {
          *((_BYTE *)v12 + 128) |= 1u;
          TunnelCache = CscStUtGenerateGuid(v60);
          if ( TunnelCache < 0 )
            goto LABEL_123;
        }
        TunnelCache = CscEnpReadEpochEa(v12);
        if ( TunnelCache < 0 )
        {
LABEL_123:
          v16 = 0;
          goto LABEL_124;
        }
LABEL_62:
        v50 = v12 + 16;
        *((_BYTE *)v12 + 128) = v12[32] & 0xF9 | (2 * (a5 & 3));
        *((_QWORD *)v12 + 23) = (unsigned __int64)*(unsigned int *)(a6 + 32) << 10;
        v12[36] |= 0x80u;
        TunnelCache = CscStOrphanerOpen(v12 + 16, v45, *v44, &v87.Blink, *((_QWORD *)v12 + 3));
        if ( TunnelCache < 0 )
          goto LABEL_51;
        if ( v80.Blink )
        {
          TunnelCache = CscStOrphanerAddTemporaryFile(*v50, v80.Blink);
          if ( TunnelCache < 0 )
          {
LABEL_98:
            v16 = 0;
            goto LABEL_124;
          }
          ZwClose(v80.Blink);
          v80.Blink = 0;
        }
        TunnelCache = CscPqOpen(v12 + 12, v51, *v44, v89, *((_QWORD *)v12 + 3), &v72, &v71);
        if ( TunnelCache < 0 )
          goto LABEL_98;
        TunnelCache = CscSidMapOpen(v12 + 14, v63, *v44, v91, v90, v74, &v73);
        if ( TunnelCache < 0 )
          goto LABEL_98;
        TunnelCache = CscEnpCheckUpdateEpoch(v12);
        if ( TunnelCache < 0 )
          goto LABEL_98;
        CscStOrphanerDeleteContents(*v50, v12 + 81);
        TunnelCache = CscStorepLowIoCreateFilePoster(
                        &v87,
                        (struct _LIST_ENTRY *)*v44,
                        &v92,
                        -2146435072,
                        0,
                        0,
                        3,
                        3,
                        33,
                        0,
                        0,
                        *((struct _LIST_ENTRY **)v12 + 3),
                        &v80);
        if ( TunnelCache < 0 )
          goto LABEL_123;
        v64 = v12 + 8;
        v99 = 0;
        v96[0] = 0;
        v96[1] = v12;
        Flink = (unsigned __int64)v87.Flink;
        v98 = 0;
        TunnelCache = CscEnpCreateEntry(v12 + 8, 0, v96);
        if ( TunnelCache < 0 )
          goto LABEL_123;
        *((_QWORD *)v12 + 13) = a7;
        *((_QWORD *)v12 + 14) = a8;
        *((_BYTE *)v12 + 177) = *(_BYTE *)(a6 + 8);
        *((_BYTE *)v12 + 178) = *(_BYTE *)(a6 + 12);
        *((_BYTE *)v12 + 176) = *(_BYTE *)(a6 + 16);
        TunnelCache = CscEnpQuotaInitializeEvictionThreshold(*((_QWORD *)v12 + 19), v12 + 44, v12 + 60);
        if ( TunnelCache < 0 )
          goto LABEL_123;
        v12[70] = *(_DWORD *)(a6 + 20);
        v12[72] = *(_DWORD *)(a6 + 28);
        v12[71] = *(_DWORD *)(a6 + 24);
        if ( (v12[36] & 0x20) != 0 )
          v12[76] = v12[72];
        *((_QWORD *)v12 + 21) = *((_QWORD *)v12 + 20);
        CscEnEvictSetEvictionTimeout(*(unsigned int *)(a6 + 20));
        if ( *((_QWORD *)v12 + 24) )
        {
          TunnelCache = CscEnEvictStartEvictionThreads(*v64);
          if ( TunnelCache < 0 )
            goto LABEL_123;
          v16 = 1;
        }
        else
        {
          v16 = 0;
        }
        if ( (v12[32] & 1) != 0 || v68 )
          TunnelCache = CscEnpAsyncRecoverDatabase(*v64);
      }
      else
      {
LABEL_51:
        v16 = 0;
      }
LABEL_124:
      if ( v11 )
        CscEaFreeFullEaBuffer((void **)&v75);
    }
    else
    {
      v16 = 0;
    }
    v15 = v69;
  }
  else
  {
    v16 = 0;
  }
LABEL_42:
  CscStUtFreeUniqueName(&UnicodeString);
  if ( TunnelCache < 0 )
  {
    if ( v80.Blink )
      ZwClose(v80.Blink);
    if ( v12 )
    {
      if ( v16 )
        CscEnEvictShutdown();
      if ( *((_QWORD *)v12 + 4) )
      {
        StringIn = (PCUNICODE_STRING)*((_QWORD *)v12 + 4);
        CscEnDereferenceEntry(&StringIn);
        v12 = 0;
      }
      else
      {
        CscEnpDestroyNamespace(&v83);
        v12 = v83;
      }
    }
  }
  if ( v94 )
    *v94 = v15;
  if ( v12 )
    v65 = *((_QWORD *)v12 + 4);
  else
    v65 = 0;
  *v93 = v65;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qDD(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_2d57263f6f6237979220aa59cf47311d_Traceguids);
  return (unsigned int)TunnelCache;
}

```

## disassembly

```asm
0x140059edc  mov     [rsp-8+arg_18], rbx
0x140059ee1  push    rbp
0x140059ee2  push    rsi
0x140059ee3  push    rdi
0x140059ee4  push    r12
0x140059ee6  push    r13
0x140059ee8  push    r14
0x140059eea  push    r15
0x140059eec  lea     rbp, [rsp-270h]
0x140059ef4  sub     rsp, 370h
0x140059efb  mov     rax, cs:__security_cookie
0x140059f02  xor     rax, rsp
0x140059f05  mov     [rbp+2A0h+var_40], rax
0x140059f0c  mov     r12, [rbp+2A0h+arg_28]
0x140059f13  lea     rax, aNamespace
0x140059f1a  xor     r13d, r13d
0x140059f1d  mov     [rbp+2A0h+var_258], rax
0x140059f21  lea     rax, aPq
0x140059f28  mov     [rbp+2A0h+StringIn], r8
0x140059f2c  mov     [rbp+2A0h+var_288], rax
0x140059f30  mov     rsi, r8
0x140059f33  lea     rax, aSm
0x140059f3a  mov     [rbp+2A0h+var_248], rdx
0x140059f3e  mov     [rbp+2A0h+var_268], rax
0x140059f42  lea     r8d, [r13+58h]; Size
0x140059f46  lea     rax, aSmTemp
0x140059f4d  mov     [rbp+2A0h+var_250], rcx
0x140059f51  mov     [rbp+2A0h+var_278], rax
0x140059f55  lea     rcx, [rbp+2A0h+var_1F0]; void *
0x140059f5c  lea     rax, aTemp_0
0x140059f63  mov     [rsp+3A0h+var_32C], r13d
0x140059f68  xorps   xmm0, xmm0
0x140059f6b  mov     [rbp+2A0h+var_298], rax
0x140059f6f  xor     edx, edx; Val
0x140059f71  mov     [rbp+2A0h+Handle], r13
0x140059f75  mov     ebx, r9d
0x140059f78  mov     [rsp+3A0h+var_328], r13b
0x140059f7d  movups  xmmword ptr [rbp+2A0h+UnicodeString.Length], xmm0
0x140059f81  mov     [rbp+2A0h+var_2F0], r13
0x140059f85  mov     [rbp+2A0h+var_2A8], r13
0x140059f89  mov     [rbp+2A0h+var_308], r13
0x140059f8d  mov     [rbp+2A0h+var_260], 140012h
0x140059f95  mov     [rbp+2A0h+var_290], 60004h
0x140059f9d  mov     [rbp+2A0h+var_270], 60004h
0x140059fa5  mov     [rbp+2A0h+var_280], 10000Eh
0x140059fad  mov     [rbp+2A0h+var_2A0], 0A0008h
0x140059fb5  call    memset
0x140059fba  xor     edx, edx; Val
0x140059fbc  lea     rcx, [rbp+2A0h+var_150]; void *
0x140059fc3  mov     r8d, 80h; Size
0x140059fc9  call    memset
0x140059fce  xor     eax, eax
0x140059fd0  mov     [rbp+2A0h+var_320], r13
0x140059fd4  mov     [rbp+2A0h+var_160], rax
0x140059fdb  xorps   xmm0, xmm0
0x140059fde  lea     rax, aC8a05bc03fa849_0
0x140059fe5  mov     [rbp+2A0h+var_318], r13d
0x140059fe9  mov     [rbp+2A0h+var_2C0], rax
0x140059fed  mov     r14d, r13d
0x140059ff0  lea     rax, aC8a05bc03fa849_1
0x140059ff7  mov     [rsp+3A0h+var_326], r13b
0x140059ffc  mov     qword ptr [rbp+2A0h+var_2D8+8], rax
0x14005a000  mov     edi, r13d
0x14005a003  lea     rax, aC8a05bc03fa849_2
0x14005a00a  mov     [rsp+3A0h+var_327], r13b
0x14005a00f  mov     [rbp+2A0h+var_2B0], rax
0x14005a013  movups  [rbp+2A0h+var_190], xmm0
0x14005a01a  mov     [rsp+3A0h+var_324], r13b
0x14005a01f  movups  [rbp+2A0h+var_180], xmm0
0x14005a026  mov     [rsp+3A0h+var_325], r13b
0x14005a02b  movups  [rbp+2A0h+var_170], xmm0
0x14005a032  mov     [rbp+2A0h+var_2E0], r13
0x14005a036  mov     [rbp+2A0h+var_2C8], 320031h
0x14005a03e  mov     qword ptr [rbp+2A0h+var_2D8], 310030h
0x14005a046  mov     [rbp+2A0h+var_30C], r13d
0x14005a04a  mov     [rbp+2A0h+var_310], r13d
0x14005a04e  mov     [rsp+3A0h+var_330], r13b
0x14005a053  mov     [rbp+2A0h+var_2E8], r13
0x14005a057  mov     [rbp+2A0h+var_2B8], 350034h
0x14005a05f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005a066  lea     rax, WPP_GLOBAL_Control
0x14005a06d  cmp     rcx, rax
0x14005a070  jz      short loc_14005A08F
0x14005a072  test    dword ptr [rcx+2Ch], 40000h
0x14005a079  jz      short loc_14005A08F
0x14005a07b  mov     rcx, [rcx+18h]
0x14005a07f  lea     edx, [r13+18h]
0x14005a083  mov     r9, rsi
0x14005a086  mov     dword ptr [rsp+3A0h+var_380], ebx
0x14005a08a  call    WPP_SF_Zd
0x14005a08f  mov     esi, 1
0x14005a094  test    ebx, ebx
0x14005a096  jz      short loc_14005A0BF
0x14005a098  sub     ebx, esi
0x14005a09a  jz      short loc_14005A0B5
0x14005a09c  cmp     ebx, esi
0x14005a09e  jz      short loc_14005A0C4
0x14005a0a0  mov     esi, 725h
0x14005a0a5  mov     ebx, 0C000000Dh
0x14005a0aa  mov     r15d, edi
0x14005a0ad  mov     r12b, dil
0x14005a0b0  jmp     loc_14005A3F1
0x14005a0b5  mov     [rsp+3A0h+var_32F], r13b
0x14005a0ba  mov     [rbp+2A0h+var_314], esi
0x14005a0bd  jmp     short loc_14005A0DD
0x14005a0bf  mov     [rsp+3A0h+var_328], sil
0x14005a0c4  cmp     [r12], r13d
0x14005a0c8  jnz     short loc_14005A0D1
0x14005a0ca  mov     esi, 72Eh
0x14005a0cf  jmp     short loc_14005A0A5
0x14005a0d1  mov     [rbp+2A0h+var_314], 3
0x14005a0d8  mov     [rsp+3A0h+var_32F], sil
0x14005a0dd  mov     edx, 160h
0x14005a0e2  mov     r8d, 27407343h
0x14005a0e8  lea     ecx, [rdx-60h]
0x14005a0eb  call    cs:__imp_ExAllocatePool2
0x14005a0f2  nop     dword ptr [rax+rax+00h]
0x14005a0f7  mov     [rbp+2A0h+var_2E0], rax
0x14005a0fb  mov     rdi, rax
0x14005a0fe  test    rax, rax
0x14005a101  jz      loc_14005AD14
0x14005a107  lea     rdx, [rbp+2A0h+var_310]
0x14005a10b  mov     dword ptr [rax], 160DA06h
0x14005a111  lea     rcx, [rbp+2A0h+var_30C]
0x14005a115  call    CscDiffTransferGetDiffTransferHandleAllocationInformation
0x14005a11a  mov     edx, [rbp+2A0h+var_310]
0x14005a11d  mov     ecx, [rbp+2A0h+var_30C]
0x14005a120  lea     r9d, [rdx-1]
0x14005a124  mov     r8d, r9d
0x14005a127  lea     eax, [rdx+1FFh]
0x14005a12d  not     r8d
0x14005a130  and     eax, r8d
0x14005a133  mov     [rdi+15Ch], eax
0x14005a139  lea     r10d, [rcx+rax]
0x14005a13d  mov     [rdi+158h], r10d
0x14005a144  test    edx, edx
0x14005a146  jz      loc_14005ACF0
0x14005a14c  test    r9d, edx
0x14005a14f  jnz     loc_14005ACF0
0x14005a155  mov     eax, ecx
0x14005a157  and     eax, r8d
0x14005a15a  cmp     eax, ecx
0x14005a15c  jnz     loc_14005ACF0
0x14005a162  cmp     r10d, ecx
0x14005a165  jbe     loc_14005ACF0
0x14005a16b  mov     edx, 68h ; 'h'
0x14005a170  mov     r8d, 22407343h
0x14005a176  lea     ecx, [rdx-26h]
0x14005a179  call    cs:__imp_ExAllocatePool2
0x14005a180  nop     dword ptr [rax+rax+00h]
0x14005a185  mov     r15, rax
0x14005a188  test    rax, rax
0x14005a18b  jz      loc_14005ACD7
0x14005a191  mov     rcx, rax; Resource
0x14005a194  call    cs:__imp_ExInitializeResourceLite
0x14005a19b  nop     dword ptr [rax+rax+00h]
0x14005a1a0  mov     ebx, eax
0x14005a1a2  test    eax, eax
0x14005a1a4  jns     short loc_14005A1C2
0x14005a1a6  mov     edx, 22407343h; Tag
0x14005a1ab  mov     rcx, r15; P
0x14005a1ae  call    cs:__imp_ExFreePoolWithTag
0x14005a1b5  nop     dword ptr [rax+rax+00h]
0x14005a1ba  xor     r15d, r15d
0x14005a1bd  jmp     loc_14005ACDC
0x14005a1c2  mov     edx, 68h ; 'h'
0x14005a1c7  mov     [rdi+78h], r15
0x14005a1cb  mov     r8d, 22407343h
0x14005a1d1  lea     ecx, [rdx-26h]
0x14005a1d4  call    cs:__imp_ExAllocatePool2
0x14005a1db  nop     dword ptr [rax+rax+00h]
0x14005a1e0  mov     r15, rax
0x14005a1e3  test    rax, rax
0x14005a1e6  jz      loc_14005ACC7
0x14005a1ec  mov     rcx, rax; Resource
0x14005a1ef  call    cs:__imp_ExInitializeResourceLite
0x14005a1f6  nop     dword ptr [rax+rax+00h]
0x14005a1fb  mov     ebx, eax
0x14005a1fd  test    eax, eax
0x14005a1ff  jns     short loc_14005A21D
0x14005a201  mov     edx, 22407343h; Tag
0x14005a206  mov     rcx, r15; P
0x14005a209  call    cs:__imp_ExFreePoolWithTag
0x14005a210  nop     dword ptr [rax+rax+00h]
0x14005a215  xor     r15d, r15d
0x14005a218  jmp     loc_14005ACCC
0x14005a21d  lea     rcx, [rdi+28h]
0x14005a221  mov     [rdi+8], r15
0x14005a225  call    CscStTuCreateTunnelCache
0x14005a22a  mov     ebx, eax
0x14005a22c  test    eax, eax
0x14005a22e  jns     short loc_14005A23A
0x14005a230  mov     esi, 762h
0x14005a235  jmp     loc_14005ACE5
0x14005a23a  mov     r15, [rbp+2A0h+StringIn]
0x14005a23e  lea     r8, [rdi+48h]; StringOut
0x14005a242  mov     rdx, r15; StringIn
0x14005a245  xor     ecx, ecx; Flags
0x14005a247  call    cs:__imp_RtlDuplicateUnicodeString
0x14005a24e  nop     dword ptr [rax+rax+00h]
0x14005a253  mov     ebx, eax
0x14005a255  test    eax, eax
0x14005a257  jns     short loc_14005A263
0x14005a259  mov     esi, 76Bh
0x14005a25e  jmp     loc_14005ACE5
0x14005a263  lea     rcx, [rdi+58h]
0x14005a267  call    CscEnpCreateVersionString
0x14005a26c  mov     ebx, eax
0x14005a26e  test    eax, eax
0x14005a270  jns     short loc_14005A27C
0x14005a272  mov     esi, 76Eh
0x14005a277  jmp     loc_14005ACE5
0x14005a27c  lea     r13, [rdi+18h]
0x14005a280  mov     rcx, r13
0x14005a283  call    CscSeCreateSecurityDescriptor
0x14005a288  xor     ecx, ecx
0x14005a28a  mov     ebx, eax
0x14005a28c  test    eax, eax
0x14005a28e  jns     short loc_14005A2A3
0x14005a290  mov     esi, 77Ah
0x14005a295  mov     r15d, ecx
0x14005a298  mov     r12b, cl
0x14005a29b  xor     r13d, r13d
0x14005a29e  jmp     loc_14005A3F1
0x14005a2a3  lea     rax, [rbp+2A0h+var_308]
0x14005a2a7  mov     r9d, 80100000h
0x14005a2ad  mov     [rsp+3A0h+var_340], rax
0x14005a2b2  mov     r8, r15
0x14005a2b5  mov     rax, [r13+0]
0x14005a2b9  xor     edx, edx
0x14005a2bb  mov     [rsp+3A0h+var_348], rax
0x14005a2c0  mov     eax, [rbp+2A0h+var_314]
0x14005a2c3  mov     [rsp+3A0h+var_350], ecx
0x14005a2c7  mov     [rsp+3A0h+var_358], rcx
0x14005a2cc  mov     [rsp+3A0h+var_360], 21h ; '!'
0x14005a2d4  mov     [rsp+3A0h+var_368], eax
0x14005a2d8  mov     dword ptr [rsp+3A0h+var_370], 3
0x14005a2e0  mov     dword ptr [rsp+3A0h+var_378], ecx
0x14005a2e4  mov     [rsp+3A0h+var_380], rcx
0x14005a2e9  lea     rcx, [rbp+2A0h+var_2F0]
0x14005a2ed  call    CscStorepLowIoCreateFilePoster
0x14005a2f2  xor     ecx, ecx
0x14005a2f4  mov     ebx, eax
0x14005a2f6  mov     r15d, ecx
0x14005a2f9  test    eax, eax
0x14005a2fb  jns     short loc_14005A304
0x14005a2fd  mov     esi, 792h
0x14005a302  jmp     short loc_14005A298
0x14005a304  cmp     [rbp+2A0h+var_308], 2
0x14005a309  cmovz   r15d, esi
0x14005a30d  mov     [rsp+3A0h+var_32C], r15d
0x14005a312  cmp     [rsp+3A0h+var_32F], cl
0x14005a316  jz      loc_14005A5CA
0x14005a31c  mov     rcx, [rbp+2A0h+var_2F0]
0x14005a320  lea     r8, [rbp+2A0h+var_2E8]
0x14005a324  call    CscStorepLowIoGetDiskSpaceInformationPoster
0x14005a329  xor     r11d, r11d
0x14005a32c  mov     ebx, eax
0x14005a32e  test    eax, eax
0x14005a330  jns     short loc_14005A33F
0x14005a332  mov     esi, 7AFh
0x14005a337  mov     r12b, r11b
0x14005a33a  jmp     loc_14005A29B
0x14005a33f  mov     dl, [r12]
0x14005a343  mov     rcx, [rbp+2A0h+var_2E8]
0x14005a347  call    CscStPercentify
0x14005a34c  mov     dl, [r12+4]
0x14005a351  mov     rcx, rax
0x14005a354  mov     r14, rax
0x14005a357  call    CscStPercentify
0x14005a35c  mov     edx, 64h ; 'd'
0x14005a361  mov     [rbp+2A0h+StringIn], rax
0x14005a365  sub     dl, [r12+8]
0x14005a36a  mov     r10, rax
0x14005a36d  call    CscStPercentify
0x14005a372  mov     rdx, r10
0x14005a375  mov     [rbp+2A0h+var_2E8], rax
0x14005a379  mov     r8, rax
0x14005a37c  call    CscEnpIsValidDatabaseSizeSetting
0x14005a381  test    al, al
0x14005a383  jnz     short loc_14005A391
0x14005a385  mov     ebx, 0C000000Dh
0x14005a38a  mov     esi, 7C2h
0x14005a38f  jmp     short loc_14005A337
0x14005a391  mov     rdx, r8
0x14005a394  call    CscEnpIsValidDatabaseSizeSetting
0x14005a399  test    al, al
0x14005a39b  jnz     short loc_14005A3A9
0x14005a39d  mov     ebx, 0C000000Dh
0x14005a3a2  mov     esi, 7C9h
0x14005a3a7  jmp     short loc_14005A337
0x14005a3a9  lea     rcx, [rdi+108h]; Uuid
0x14005a3b0  call    CscStUtGenerateGuid
0x14005a3b5  mov     ebx, eax
0x14005a3b7  test    eax, eax
0x14005a3b9  jns     short loc_14005A3CA
0x14005a3bb  mov     r12b, [rsp+3A0h+var_330]
0x14005a3c0  mov     esi, 7D3h
0x14005a3c5  jmp     loc_14005A29B
0x14005a3ca  lea     r15, [rdi+144h]
  ... truncated ...
```
