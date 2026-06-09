# CscEnAttachDatabase

- ea: `0x140059edc`
- end: `0x14005adb4`
- name: `CscEnAttachDatabase`
- size: `3800`
- prototype: ``
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
  __int64 v11; // r9
  struct _LIST_ENTRY *v12; // r14
  __int64 v13; // rdi
  int v14; // ebx
  int v15; // esi
  int TunnelCache; // ebx
  BOOL v17; // r15d
  char v18; // r12
  _DWORD *Pool2; // rax
  int v20; // edx
  unsigned int v21; // ecx
  __int64 v22; // r9
  int v23; // r8d
  int v24; // eax
  struct _ERESOURCE *v25; // rax
  struct _ERESOURCE *v26; // r15
  __int64 v27; // r9
  struct _ERESOURCE *v28; // rax
  struct _ERESOURCE *v29; // r15
  struct _LIST_ENTRY *v30; // r15
  struct _LIST_ENTRY **v31; // r13
  __int64 v32; // rdx
  int DiskSpaceInformationPoster; // eax
  __int64 v34; // rdx
  char v35; // r11
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // r14
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // r10
  __int64 v42; // rcx
  __int64 v43; // r8
  PCUNICODE_STRING v44; // rax
  __int128 v45; // xmm0
  int v46; // eax
  unsigned __int64 *v47; // r15
  __int64 v48; // rdx
  __int64 v49; // rcx
  __int64 v50; // r8
  struct _LIST_ENTRY *v51; // rax
  _QWORD *v52; // r13
  __int64 v53; // rdx
  int v54; // eax
  __int64 v55; // rax
  int v56; // eax
  __int64 v57; // r8
  __int16 v58; // ax
  __int64 v59; // rax
  __int64 v60; // rcx
  __int64 v61; // r8
  UUID *v62; // rcx
  int v63; // eax
  __int64 v64; // rdx
  __int64 v65; // rdx
  _QWORD *v66; // r15
  __int64 v67; // r9
  char v69; // [rsp+71h] [rbp-8Fh]
  char v70; // [rsp+71h] [rbp-8Fh]
  int v71; // [rsp+74h] [rbp-8Ch]
  char v72; // [rsp+78h] [rbp-88h]
  char v73; // [rsp+79h] [rbp-87h] BYREF
  char v74; // [rsp+7Ah] [rbp-86h] BYREF
  char v75; // [rsp+7Bh] [rbp-85h] BYREF
  char v76[4]; // [rsp+7Ch] [rbp-84h] BYREF
  __int64 v77; // [rsp+80h] [rbp-80h] BYREF
  int v78; // [rsp+88h] [rbp-78h] BYREF
  int v79; // [rsp+8Ch] [rbp-74h]
  int v80; // [rsp+90h] [rbp-70h] BYREF
  unsigned int v81; // [rsp+94h] [rbp-6Ch] BYREF
  struct _LIST_ENTRY v82; // [rsp+98h] [rbp-68h] BYREF
  PCUNICODE_STRING StringIn; // [rsp+A8h] [rbp-58h] BYREF
  struct _LIST_ENTRY v84; // [rsp+B0h] [rbp-50h] BYREF
  _DWORD *v85; // [rsp+C0h] [rbp-40h] BYREF
  __int128 v86; // [rsp+C8h] [rbp-38h] BYREF
  __int128 v87; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v88; // [rsp+E8h] [rbp-18h] BYREF
  struct _LIST_ENTRY v89; // [rsp+F8h] [rbp-8h] BYREF
  const wchar_t *v90; // [rsp+108h] [rbp+8h]
  _QWORD v91[2]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v92[2]; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v93[2]; // [rsp+130h] [rbp+30h] BYREF
  struct _LIST_ENTRY v94; // [rsp+140h] [rbp+40h] BYREF
  _QWORD *v95; // [rsp+150h] [rbp+50h]
  BOOL *v96; // [rsp+158h] [rbp+58h]
  struct _UNICODE_STRING UnicodeString; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v98[2]; // [rsp+170h] [rbp+70h] BYREF
  __int128 Flink; // [rsp+180h] [rbp+80h]
  __int128 v100; // [rsp+190h] [rbp+90h]
  __int64 v101; // [rsp+1A0h] [rbp+A0h]
  _OWORD v102[6]; // [rsp+1B0h] [rbp+B0h] BYREF
  _OWORD v103[2]; // [rsp+210h] [rbp+110h] BYREF
  __int128 v104; // [rsp+230h] [rbp+130h]
  __int64 v105; // [rsp+240h] [rbp+140h]
  _OWORD v106[8]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v107[48]; // [rsp+2D0h] [rbp+1D0h] BYREF
  char v108; // [rsp+300h] [rbp+200h] BYREF
  char v109; // [rsp+330h] [rbp+230h] BYREF

  v94.Blink = (struct _LIST_ENTRY *)L"namespace";
  StringIn = a3;
  v91[1] = L"pq";
  v8 = (int)a3;
  v96 = a2;
  v93[1] = L"sm";
  v95 = a1;
  v92[1] = L"sm.temp";
  v71 = 0;
  v90 = L"temp";
  v82.Blink = 0;
  v72 = 0;
  UnicodeString = 0;
  v84.Flink = 0;
  v89.Flink = 0;
  v82.Flink = 0;
  v94.Flink = (struct _LIST_ENTRY *)1310738;
  v91[0] = 393220;
  v93[0] = 393220;
  v92[0] = 1048590;
  v89.Blink = (struct _LIST_ENTRY *)655368;
  memset(v102, 0, 0x58u);
  memset(v106, 0, sizeof(v106));
  v77 = 0;
  v105 = 0;
  v78 = 0;
  *((_QWORD *)&v87 + 1) = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.Database";
  v12 = 0;
  v74 = 0;
  *((_QWORD *)&v86 + 1) = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.EpochEa";
  v13 = 0;
  v73 = 0;
  *((_QWORD *)&v88 + 1) = "c8a05bc0-3fa8-49e9-8148-61ee14a67687.Csc.DatabaseEx1";
  memset(v103, 0, sizeof(v103));
  v76[0] = 0;
  v75 = 0;
  v104 = 0;
  v85 = 0;
  *(_QWORD *)&v87 = 3276849;
  *(_QWORD *)&v86 = 3211312;
  v81 = 0;
  v80 = 0;
  v84.Blink = 0;
  *(_QWORD *)&v88 = 3473460;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_Zd(WPP_GLOBAL_Control->AttachedDevice, 24, v10, v8, a4);
  if ( a4 )
  {
    v14 = a4 - 1;
    if ( !v14 )
    {
      v69 = 0;
      v79 = 1;
      goto LABEL_14;
    }
    if ( v14 != 1 )
    {
      v15 = 1829;
LABEL_8:
      TunnelCache = -1073741811;
      v17 = 0;
      v18 = 0;
      goto LABEL_49;
    }
  }
  else
  {
    v72 = 1;
  }
  if ( !*(_DWORD *)a6 )
  {
    v15 = 1838;
    goto LABEL_8;
  }
  v79 = 3;
  v69 = 1;
LABEL_14:
  Pool2 = (_DWORD *)ExAllocatePool2(256, 352, 658535235, v11);
  v85 = Pool2;
  v13 = (__int64)Pool2;
  if ( !Pool2 )
  {
    TunnelCache = -1073741670;
    v15 = 1851;
    goto LABEL_141;
  }
  *Pool2 = 23124486;
  CscDiffTransferGetDiffTransferHandleAllocationInformation(&v81, &v80);
  v20 = v80;
  v21 = v81;
  v22 = (unsigned int)(v80 - 1);
  v23 = ~(v80 - 1);
  v24 = v23 & (v80 + 511);
  *(_DWORD *)(v13 + 348) = v24;
  *(_DWORD *)(v13 + 344) = v21 + v24;
  if ( !v20 || (v20 & (unsigned int)v22) != 0 || (v23 & v21) != v21 || v21 + v24 <= v21 )
  {
    v15 = 1868;
LABEL_143:
    TunnelCache = -1073740768;
LABEL_144:
    v18 = 0;
    goto LABEL_145;
  }
  v25 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 574649155, v22);
  v26 = v25;
  if ( !v25 )
  {
    TunnelCache = -1073741670;
    goto LABEL_140;
  }
  TunnelCache = ExInitializeResourceLite(v25);
  if ( TunnelCache < 0 )
  {
    ExFreePoolWithTag(v26, 0x22407343u);
LABEL_140:
    *(_QWORD *)(v13 + 120) = 0;
    v15 = 1876;
    goto LABEL_141;
  }
  *(_QWORD *)(v13 + 120) = v26;
  v28 = (struct _ERESOURCE *)ExAllocatePool2(66, 104, 574649155, v27);
  v29 = v28;
  if ( !v28 )
  {
    TunnelCache = -1073741670;
    goto LABEL_138;
  }
  TunnelCache = ExInitializeResourceLite(v28);
  if ( TunnelCache < 0 )
  {
    ExFreePoolWithTag(v29, 0x22407343u);
LABEL_138:
    *(_QWORD *)(v13 + 8) = 0;
    v15 = 1883;
    goto LABEL_141;
  }
  *(_QWORD *)(v13 + 8) = v29;
  TunnelCache = CscStTuCreateTunnelCache(v13 + 40);
  if ( TunnelCache >= 0 )
  {
    v30 = (struct _LIST_ENTRY *)StringIn;
    TunnelCache = RtlDuplicateUnicodeString(0, StringIn, (PUNICODE_STRING)(v13 + 72));
    if ( TunnelCache < 0 )
    {
      v15 = 1899;
      goto LABEL_141;
    }
    TunnelCache = CscEnpCreateVersionString(v13 + 88);
    if ( TunnelCache < 0 )
    {
      v15 = 1902;
      goto LABEL_141;
    }
    v31 = (struct _LIST_ENTRY **)(v13 + 24);
    TunnelCache = CscSeCreateSecurityDescriptor((_QWORD *)(v13 + 24));
    if ( TunnelCache < 0 )
    {
      v15 = 1914;
      v17 = 0;
LABEL_33:
      v18 = 0;
      goto LABEL_49;
    }
    TunnelCache = CscStorepLowIoCreateFilePoster(&v84, 0, v30, -2146435072, 0, 0, 3, v79, 33, 0, 0, *v31, &v82);
    v17 = 0;
    if ( TunnelCache < 0 )
    {
      v15 = 1938;
      goto LABEL_33;
    }
    v17 = v82.Flink == (struct _LIST_ENTRY *)2;
    v71 = v17;
    if ( !v69 )
      goto LABEL_60;
    DiskSpaceInformationPoster = CscStorepLowIoGetDiskSpaceInformationPoster(v84.Flink, v32, &v84.Blink);
    v35 = 0;
    TunnelCache = DiskSpaceInformationPoster;
    if ( DiskSpaceInformationPoster < 0 )
    {
      v15 = 1967;
LABEL_39:
      v18 = v35;
      goto LABEL_49;
    }
    LOBYTE(v34) = *(_BYTE *)a6;
    v36 = CscStPercentify(v84.Blink, v34);
    LOBYTE(v37) = *(_BYTE *)(a6 + 4);
    v38 = v36;
    StringIn = (PCUNICODE_STRING)CscStPercentify(v36, v37);
    v84.Blink = (struct _LIST_ENTRY *)CscStPercentify(v39, (unsigned __int8)(100 - *(_BYTE *)(a6 + 8)));
    if ( !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(v40, v41, v84.Blink) )
    {
      TunnelCache = -1073741811;
      v15 = 1986;
      goto LABEL_39;
    }
    if ( !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(v42, v43, v43) )
    {
      TunnelCache = -1073741811;
      v15 = 1993;
      goto LABEL_39;
    }
    TunnelCache = CscStUtGenerateGuid((UUID *)(v13 + 264));
    if ( TunnelCache < 0 )
    {
      v18 = 0;
      v15 = 2003;
      goto LABEL_49;
    }
    TunnelCache = CscStUtGenerateGuid((UUID *)(v13 + 324));
    if ( TunnelCache < 0 )
    {
      v18 = 0;
      v15 = 2007;
LABEL_48:
      v17 = v71;
      goto LABEL_49;
    }
    v44 = StringIn;
    *(_QWORD *)(v13 + 152) = v38;
    *(_QWORD *)(v13 + 160) = v44;
    *(_QWORD *)(v13 + 168) = v84.Blink;
    memset((char *)v102 + 8, 0, 0x50u);
    memset((char *)v106 + 8, 0, 0x78u);
    *(_QWORD *)&v106[0] = 0x58005002000006LL;
    *(_QWORD *)&v102[0] = 0x58005002000006LL;
    v102[1] = *(_OWORD *)(v13 + 152);
    *((_QWORD *)&v106[0] + 1) = *(_QWORD *)(v13 + 168);
    v45 = *(_OWORD *)(v13 + 264);
    v105 = 0;
    v103[0] = 0x38001002000006uLL;
    v103[1] = 0;
    v102[4] = v45;
    v104 = 0;
    *(_OWORD *)((char *)v103 + 8) = *(_OWORD *)(v13 + 324);
    CscEaInitializeFullEntry((unsigned int)v107, (unsigned int)&v87, (unsigned int)v102, 88, 0);
    CscEaInitializeFullEntry((unsigned int)&v108, (unsigned int)&v88, (unsigned int)v106, 128, (__int64)v107);
    CscEaInitializeFullEntry((unsigned int)&v109, (unsigned int)&v86, (unsigned int)v103, 56, (__int64)v107);
    v46 = CscEaCreateFullEaBuffer(v107, &v77, &v78);
    v12 = (struct _LIST_ENTRY *)v77;
    TunnelCache = v46;
    if ( v46 >= 0 )
    {
      while ( 1 )
      {
LABEL_60:
        v47 = (unsigned __int64 *)(v13 + 16);
        TunnelCache = CscStorepLowIoCreateFilePoster(
                        (struct _LIST_ENTRY *)(v13 + 16),
                        v84.Flink,
                        (struct _LIST_ENTRY *)(v13 + 88),
                        -2146435072,
                        0,
                        0,
                        3,
                        v79,
                        33,
                        v12,
                        v78,
                        *v31,
                        &v82);
        if ( TunnelCache < 0 )
        {
          v15 = 2092;
          v18 = 0;
          goto LABEL_145;
        }
        if ( !v72 )
          break;
        TunnelCache = CscStOrphanerGenerateTemporaryFileName(v49, v48, v50, &UnicodeString);
        if ( TunnelCache < 0 )
        {
          v15 = 2107;
          goto LABEL_59;
        }
        v51 = (struct _LIST_ENTRY *)*v47;
        *v47 = 0;
        v82.Blink = v51;
        TunnelCache = CscStorepLowIoRenameFilePoster((__int64)v51, (__int64)v84.Flink, (__int64)&UnicodeString, 1);
        if ( TunnelCache < 0 )
        {
          v15 = 2116;
          goto LABEL_59;
        }
        v72 = 0;
      }
      v70 = 0;
      if ( v82.Flink == (struct _LIST_ENTRY *)1 )
      {
        if ( v12 )
          CscEaFreeFullEaBuffer(&v77);
        v54 = CscEaReadVariableSizeEa(*v47, &v87, &v77, &v78);
        v12 = (struct _LIST_ENTRY *)v77;
        TunnelCache = v54;
        if ( v54 < 0 )
        {
          v15 = 2145;
          goto LABEL_144;
        }
        if ( *(_WORD *)(v77 + 6) != 88 )
        {
          TunnelCache = -1073741596;
          v15 = 2150;
          goto LABEL_144;
        }
        v55 = *(unsigned __int8 *)(v77 + 5);
        v102[0] = *(_OWORD *)(v55 + v77 + 9);
        v102[1] = *(_OWORD *)(v55 + v77 + 25);
        v102[2] = *(_OWORD *)(v55 + v77 + 41);
        v102[3] = *(_OWORD *)(v55 + v77 + 57);
        v102[4] = *(_OWORD *)(v55 + v77 + 73);
        *(_QWORD *)&v102[5] = *(_QWORD *)(v55 + v77 + 89);
        CscEaFreeFullEaBuffer(&v77);
        TunnelCache = CscEnpCheckEaVersion(v102, 5767248);
        if ( TunnelCache < 0 )
        {
          v12 = (struct _LIST_ENTRY *)v77;
          v15 = 2162;
          goto LABEL_144;
        }
        v56 = CscEaReadVariableSizeEa(*v47, &v88, &v77, &v78);
        v12 = (struct _LIST_ENTRY *)v77;
        TunnelCache = v56;
        if ( v56 < 0 )
        {
          v15 = 2169;
          goto LABEL_144;
        }
        v58 = *(_WORD *)(v77 + 6);
        if ( v58 )
        {
          if ( v58 != 128 )
          {
            TunnelCache = -1073741596;
            v15 = 2187;
            goto LABEL_144;
          }
          v59 = *(unsigned __int8 *)(v77 + 5);
          LOBYTE(v57) = 1;
          v106[0] = *(_OWORD *)(v59 + v77 + 9);
          v106[1] = *(_OWORD *)(v59 + v77 + 25);
          v106[2] = *(_OWORD *)(v59 + v77 + 41);
          v106[3] = *(_OWORD *)(v59 + v77 + 57);
          v106[4] = *(_OWORD *)(v59 + v77 + 73);
          v106[5] = *(_OWORD *)(v59 + v77 + 89);
          v106[6] = *(_OWORD *)(v59 + v77 + 105);
          v106[7] = *(_OWORD *)(v59 + v77 + 121);
        }
        else
        {
          LOBYTE(v57) = 0;
        }
        if ( !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(*(_QWORD *)&v102[1], *((_QWORD *)&v102[1] + 1), v57) )
        {
          TunnelCache = -1073741596;
          v15 = 2201;
          goto LABEL_144;
        }
        if ( (_BYTE)v61 && !(unsigned __int8)CscEnpIsValidDatabaseSizeSetting(v60, *((_QWORD *)&v106[0] + 1), v61) )
        {
          TunnelCache = -1073741596;
          v15 = 2210;
          goto LABEL_144;
        }
        v62 = (UUID *)(v13 + 264);
        *(_DWORD *)(v13 + 144) = DWORD2(v102[0]);
        *(_OWORD *)(v13 + 152) = v102[1];
        *(_OWORD *)(v13 + 192) = v102[2];
        *(_OWORD *)(v13 + 264) = v102[4];
        *(_DWORD *)(v13 + 320) = v102[5];
        if ( (_BYTE)v61 )
        {
          *(_QWORD *)(v13 + 168) = *((_QWORD *)&v106[0] + 1);
          *(_QWORD *)(v13 + 208) = *(_QWORD *)&v106[1];
        }
        v63 = *(_DWORD *)(v13 + 144);
        if ( (v63 & 0x10) != 0 )
        {
          *(_DWORD *)(v13 + 144) = v63 & 0xFFFFFFEF;
          *v62 = 0;
        }
        v64 = *(_QWORD *)&v62->Data1;
        v86 = 0;
        if ( !v64 )
          v64 = *(_QWORD *)(v13 + 272) - *((_QWORD *)&v86 + 1);
        if ( v64 )
        {
          if ( (*(_DWORD *)(v13 + 144) & 8) != 0 )
          {
            *(_OWORD *)(v13 + 216) = v102[3];
            v70 = 1;
            if ( (_BYTE)v61 )
              *(_QWORD *)(v13 + 232) = *((_QWORD *)&v106[1] + 1);
          }
        }
        else
        {
          *(_BYTE *)(v13 + 128) |= 1u;
          TunnelCache = CscStUtGenerateGuid(v62);
          if ( TunnelCache < 0 )
          {
            v15 = 2263;
            goto LABEL_144;
          }
        }
        TunnelCache = CscEnpReadEpochEa(v13);
        if ( TunnelCache < 0 )
        {
          v15 = 2281;
          goto LABEL_144;
        }
      }
      else
      {
        if ( v82.Flink != (struct _LIST_ENTRY *)2 )
        {
          v15 = 2293;
          goto LABEL_143;
        }
        v71 = 3;
      }
      v52 = (_QWORD *)(v13 + 64);
      *(_BYTE *)(v13 + 128) = *(_BYTE *)(v13 + 128) & 0xF9 | (2 * (a5 & 3));
      *(_QWORD *)(v13 + 184) = (unsigned __int64)*(unsigned int *)(a6 + 32) << 10;
      *(_DWORD *)(v13 + 144) |= 0x80u;
      TunnelCache = CscStOrphanerOpen(v13 + 64, v48, *v47, &v89.Blink, *(_QWORD *)(v13 + 24));
      if ( TunnelCache < 0 )
      {
        v15 = 2333;
        goto LABEL_59;
      }
      if ( v82.Blink )
      {
        TunnelCache = CscStOrphanerAddTemporaryFile(*v52, v82.Blink);
        if ( TunnelCache < 0 )
        {
          v15 = 2345;
LABEL_110:
          v18 = 0;
          goto LABEL_145;
        }
        ZwClose(v82.Blink);
        v82.Blink = 0;
      }
      TunnelCache = CscPqOpen(v13 + 48, v53, *v47, v91, *(_QWORD *)(v13 + 24), &v74, &v73);
      if ( TunnelCache < 0 )
      {
        v15 = 2362;
        goto LABEL_110;
      }
      TunnelCache = CscSidMapOpen(v13 + 56, v65, *v47, v93, v92, v76, &v75);
      if ( TunnelCache < 0 )
      {
        v15 = 2375;
        goto LABEL_110;
      }
      TunnelCache = CscEnpCheckUpdateEpoch(v13);
      if ( TunnelCache < 0 )
      {
        v15 = 2382;
        goto LABEL_110;
      }
      CscStOrphanerDeleteContents(*v52, v13 + 324);
      TunnelCache = CscStorepLowIoCreateFilePoster(
                      &v89,
                      (struct _LIST_ENTRY *)*v47,
                      &v94,
                      -2146435072,
                      0,
                      0,
                      3,
                      3,
                      33,
                      0,
                      0,
                      *(struct _LIST_ENTRY **)(v13 + 24),
                      &v82);
      if ( TunnelCache < 0 )
      {
        v15 = 2416;
        goto LABEL_144;
      }
      v66 = (_QWORD *)(v13 + 32);
      v101 = 0;
      v98[0] = 0;
      v98[1] = v13;
      Flink = (unsigned __int64)v89.Flink;
      v100 = 0;
      TunnelCache = CscEnpCreateEntry(v13 + 32, 0, v98);
      if ( TunnelCache < 0 )
      {
        v15 = 2430;
        goto LABEL_144;
      }
      *(_QWORD *)(v13 + 104) = a7;
      *(_QWORD *)(v13 + 112) = a8;
      *(_BYTE *)(v13 + 177) = *(_BYTE *)(a6 + 8);
      *(_BYTE *)(v13 + 178) = *(_BYTE *)(a6 + 12);
      *(_BYTE *)(v13 + 176) = *(_BYTE *)(a6 + 16);
      TunnelCache = CscEnpQuotaInitializeEvictionThreshold(*(_QWORD *)(v13 + 152), v13 + 176, v13 + 240);
      if ( TunnelCache < 0 )
      {
        v15 = 2446;
        goto LABEL_144;
      }
      *(_DWORD *)(v13 + 280) = *(_DWORD *)(a6 + 20);
      *(_DWORD *)(v13 + 288) = *(_DWORD *)(a6 + 28);
      *(_DWORD *)(v13 + 284) = *(_DWORD *)(a6 + 24);
      if ( (*(_DWORD *)(v13 + 144) & 0x20) != 0 )
        *(_DWORD *)(v13 + 304) = *(_DWORD *)(v13 + 288);
      *(_QWORD *)(v13 + 168) = *(_QWORD *)(v13 + 160);
      CscEnEvictSetEvictionTimeout(*(unsigned int *)(a6 + 20));
      if ( *(_QWORD *)(v13 + 192) )
      {
        TunnelCache = CscEnEvictStartEvictionThreads(*v66);
        if ( TunnelCache < 0 )
        {
          v15 = 2487;
          goto LABEL_144;
        }
        v18 = 1;
      }
      else
      {
        v18 = 0;
      }
      if ( ((*(_BYTE *)(v13 + 128) & 1) != 0 || v70)
        && (TunnelCache = CscEnpAsyncRecoverDatabase(*v66), TunnelCache < 0) )
      {
        v15 = 2500;
      }
      else
      {
        v15 = 0;
      }
    }
    else
    {
      v15 = 2064;
LABEL_59:
      v18 = 0;
    }
LABEL_145:
    if ( v12 )
      CscEaFreeFullEaBuffer(&v77);
    goto LABEL_48;
  }
  v15 = 1890;
LABEL_141:
  v17 = 0;
  v18 = 0;
LABEL_49:
  CscStUtFreeUniqueName(&UnicodeString);
  if ( TunnelCache < 0 )
  {
    if ( v82.Blink )
      ZwClose(v82.Blink);
    if ( v13 )
    {
      if ( v18 )
        CscEnEvictShutdown();
      if ( *(_QWORD *)(v13 + 32) )
      {
        StringIn = *(PCUNICODE_STRING *)(v13 + 32);
        CscEnDereferenceEntry(&StringIn);
        v13 = 0;
      }
      else
      {
        CscEnpDestroyNamespace((__int64 *)&v85);
        v13 = (__int64)v85;
      }
    }
  }
  if ( v96 )
    *v96 = v17;
  if ( v13 )
    v67 = *(_QWORD *)(v13 + 32);
  else
    v67 = 0;
  *v95 = v67;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000) != 0 )
    WPP_SF_qDD(
      WPP_GLOBAL_Control->AttachedDevice,
      25,
      WPP_2d57263f6f6237979220aa59cf47311d_Traceguids,
      v67,
      TunnelCache,
      v15);
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
