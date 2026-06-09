# ExtSTAAssocCompletion(EXTSTA_VELAN *,_DOT11_ASSOCIATION_TYPE,DOT11_ASSOCIATION_COMPLETION_PARAMETERS * const,ulong,DOT11_CONNECTION_INFO *)

- ea: `0x14005c9dc`
- end: `0x14005d9fd`
- name: `?ExtSTAAssocCompletion@@YAXPEAUEXTSTA_VELAN@@W4_DOT11_ASSOCIATION_TYPE@@QEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@KPEAUDOT11_CONNECTION_INFO@@@Z`
- size: `4129`
- prototype: ``
- caller_count: `1`
- callee_count: `36`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140067130`

## callees

- `0x140001008`
- `0x14000185c`
- `0x14000ab88`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140018a0c`
- `0x14001a34c`
- `0x140020998`
- `0x140020e04`
- `0x140020f20`
- `0x140025480`
- `0x14002f1bc`
- `0x140032470`
- `0x140038d7c`
- `0x14003a088`
- `0x140045a90`
- `0x140046bf0`
- `0x14005c9dc`
- `0x14005e0c4`
- `0x14005e694`
- `0x14005ef28`
- `0x1400630a8`
- `0x1400635c4`
- `0x140063688`
- `0x1400636f4`
- `0x14006376c`
- `0x140066790`
- `0x14006689c`
- `0x14007b978`
- `0x140095de0`
- `0x140095ea4`
- `0x140095fa8`
- `0x14009a3d0`
- `0x14009a4c0`
- `0x14009a7c0`
- `0x14009ace0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005d318`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005d51f`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005d318`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005d51f`
- `ntoskrnl!ExAllocatePool2` at `0x14005d335`
- `ntoskrnl!ExAllocatePool2` at `0x14005d53c`
- `ntoskrnl!ExAllocatePool2` at `0x14005d335`
- `ntoskrnl!ExAllocatePool2` at `0x14005d53c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d1d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d372`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d494`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d9d1`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d1d0`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d372`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d494`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005d9d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d383`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d4a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d9a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d9e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d383`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d4a5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d9a9`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005d9e5`

## pseudocode

```c
void __fastcall ExtSTAAssocCompletion(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        struct DOT11_MAC_STATE_ENTRY *a5)
{
  struct DOT11_MAC_STATE_ENTRY *Flink; // rsi
  __int64 *pvAssocEntry; // r12
  bool v7; // zf
  int v10; // r15d
  unsigned int v11; // eax
  char v12; // cl
  __int64 v13; // r13
  const void *v14; // rdx
  struct DOT11_MAC_STATE_ENTRY **v15; // r14
  PDEVICE_OBJECT v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // rdx
  int v22; // r8d
  int v23; // r9d
  unsigned int v24; // ecx
  int v25; // ecx
  unsigned int v26; // r8d
  __int64 v27; // r9
  const char *v28; // rax
  stringify *v29; // rcx
  const char *v30; // rax
  stringify *v31; // rcx
  enum _DOT11_CIPHER_ALGORITHM v32; // edx
  const char *v33; // rax
  stringify *v34; // rcx
  enum _DOT11_AUTH_ALGORITHM v35; // edx
  const char *v36; // rax
  __int64 v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  char *v43; // rdx
  const char *v44; // rax
  stringify *v45; // rcx
  const char *v46; // rax
  stringify *v47; // rcx
  enum _DOT11_CIPHER_ALGORITHM v48; // edx
  const char *v49; // rax
  stringify *v50; // rcx
  enum _DOT11_AUTH_ALGORITHM v51; // edx
  const char *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rdx
  struct _WFD_ROLE *v55; // rcx
  int v56; // eax
  PDEVICE_OBJECT v57; // rcx
  __int64 v58; // rdx
  _DEVICE_OBJECT *AttachedDevice; // rcx
  int v60; // eax
  PDEVICE_OBJECT v61; // rcx
  __int64 v62; // rdx
  _DEVICE_OBJECT *v63; // rcx
  int v64; // eax
  _DEVICE_OBJECT *v65; // rcx
  __int64 *v66; // rax
  __int64 **v67; // rcx
  __int64 v68; // rcx
  __int64 v69; // rcx
  PDEVICE_OBJECT v70; // rcx
  __int64 v71; // rdx
  __int64 v72; // r9
  unsigned int v73; // eax
  unsigned int v74; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r15
  _DWORD *v76; // rax
  char *v77; // r15
  __int64 v78; // rcx
  __int64 v79; // rcx
  void *v80; // rcx
  int v81; // ecx
  int v82; // ecx
  __int64 v83; // rcx
  __int64 v84; // rcx
  unsigned int v85; // edx
  unsigned int v86; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // r15
  _DWORD *Pool2; // rax
  void *v89; // rcx
  int v90; // eax
  bool v91; // cf
  int v92; // ecx
  unsigned int v93; // ecx
  int v94; // ecx
  __int64 v95; // rdx
  unsigned int v96; // ecx
  unsigned int v97; // ecx
  int v98; // eax
  __int64 v99; // rax
  int v100; // eax
  struct _IRP *v101; // rdx
  PDEVICE_OBJECT v102; // rcx
  __int64 v103; // rdx
  unsigned __int8 v104[16]; // [rsp+A0h] [rbp-80h] BYREF
  __int128 v105; // [rsp+B0h] [rbp-70h] BYREF
  char v106; // [rsp+C0h] [rbp-60h] BYREF
  char v107[3]; // [rsp+C1h] [rbp-5Fh] BYREF
  unsigned int Size; // [rsp+C4h] [rbp-5Ch]
  unsigned int Size_4; // [rsp+C8h] [rbp-58h] BYREF
  unsigned int v110; // [rsp+CCh] [rbp-54h]
  int v111; // [rsp+D0h] [rbp-50h]
  unsigned int v112; // [rsp+D4h] [rbp-4Ch]
  int v113; // [rsp+D8h] [rbp-48h]
  __int128 *v114; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v115; // [rsp+E8h] [rbp-38h] BYREF
  const char *v116; // [rsp+F0h] [rbp-30h] BYREF
  const char *v117; // [rsp+F8h] [rbp-28h] BYREF
  const char *v118; // [rsp+100h] [rbp-20h] BYREF
  int v119; // [rsp+108h] [rbp-18h] BYREF
  int v120; // [rsp+10Ch] [rbp-14h] BYREF
  int v121; // [rsp+110h] [rbp-10h] BYREF
  int v122; // [rsp+114h] [rbp-Ch] BYREF
  int v123; // [rsp+118h] [rbp-8h] BYREF
  int v124; // [rsp+11Ch] [rbp-4h] BYREF
  int v125; // [rsp+120h] [rbp+0h] BYREF
  int v126; // [rsp+124h] [rbp+4h]
  struct DOT11_MAC_STATE_ENTRY *v127; // [rsp+128h] [rbp+8h] BYREF
  __int128 v128; // [rsp+130h] [rbp+10h] BYREF
  __int128 v129; // [rsp+140h] [rbp+20h]
  __int64 v130; // [rsp+150h] [rbp+30h]
  __int128 v131; // [rsp+158h] [rbp+38h] BYREF
  __int16 v132; // [rsp+168h] [rbp+48h]
  _BYTE v133[128]; // [rsp+170h] [rbp+50h] BYREF

  Flink = 0;
  v127 = a5;
  pvAssocEntry = 0;
  Size = a4;
  v7 = *(_BYTE *)(a1 + 1704) == 0;
  v130 = 0;
  v113 = 0;
  v112 = a2;
  v126 = v7;
  v10 = -1073741823;
  v104[0] = 0;
  v128 = 0;
  v129 = 0;
  if ( a4 < 4 || *(_BYTE *)a3 != 0x80 || (v11 = *(unsigned __int16 *)(a3 + 2), a4 < v11) )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v17 = 22;
    goto LABEL_18;
  }
  v12 = *(_BYTE *)(a3 + 1);
  if ( v12 == 1 )
  {
    if ( v11 >= 0x58 )
    {
      v110 = 1;
      goto LABEL_10;
    }
LABEL_213:
    v102 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v103 = 23;
LABEL_212:
    WPP_SF_(v102->AttachedDevice, v103, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    return;
  }
  if ( v12 != 2 || v11 < 0x60 )
    goto LABEL_213;
  v110 = 2;
LABEL_10:
  v13 = *(_QWORD *)(a1 + 2616);
  v14 = (const void *)(a3 + 4);
  v15 = (struct DOT11_MAC_STATE_ENTRY **)(v13
                                        + 16
                                        * (((*(unsigned __int8 *)(a3 + 8) ^ *(unsigned __int8 *)(a3 + 9)) & 0x800000FF)
                                         + 10LL));
  Flink = *v15;
  if ( v15 == (struct DOT11_MAC_STATE_ENTRY **)*v15 )
  {
LABEL_14:
    Flink = 0;
  }
  else
  {
    while ( memcmp(Flink->MacHashEntry.MacKey, v14, 6u) )
    {
      Flink = (struct DOT11_MAC_STATE_ENTRY *)Flink->MacHashEntry.Linkage.Flink;
      if ( v15 == (struct DOT11_MAC_STATE_ENTRY **)Flink )
        goto LABEL_14;
      v14 = (const void *)(a3 + 4);
    }
  }
  if ( !Flink )
  {
    v16 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_93:
      if ( Flink )
      {
        Flink->pvAssocEntry = 0;
        if ( pvAssocEntry )
        {
          v66 = (__int64 *)*pvAssocEntry;
          if ( *(__int64 **)(*pvAssocEntry + 8) != pvAssocEntry
            || (v67 = (__int64 **)pvAssocEntry[1], *v67 != pvAssocEntry) )
          {
            __fastfail(3u);
          }
          *v67 = v66;
          v66[1] = (__int64)v67;
          v127 = (struct DOT11_MAC_STATE_ENTRY *)pvAssocEntry[2];
          Dot11DecObjCnt(&v127, (unsigned int)v14);
          v68 = pvAssocEntry[6];
          if ( v68 )
          {
            v69 = v68 - 16;
            if ( *(_QWORD *)v69 )
              ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v69, (PVOID)v69);
            else
              ExFreePoolWithTag((PVOID)v69, *(_DWORD *)(v69 + 8));
            pvAssocEntry[6] = 0;
          }
          if ( *(pvAssocEntry - 2) )
            ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)*(pvAssocEntry - 2), pvAssocEntry - 2);
          else
            ExFreePoolWithTag(pvAssocEntry - 2, *((_DWORD *)pvAssocEntry - 2));
        }
      }
      goto LABEL_205;
    }
    v17 = 24;
LABEL_18:
    WPP_SF_(v16->AttachedDevice, v17, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    goto LABEL_93;
  }
  pvAssocEntry = (__int64 *)Flink->pvAssocEntry;
  if ( !pvAssocEntry || *((_DWORD *)pvAssocEntry + 6) != 1 )
  {
    v102 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v103 = 25;
    goto LABEL_212;
  }
  --*(_DWORD *)(a1 + 328);
  v18 = a3 + 4;
  v19 = *(_DWORD *)(a3 + 12);
  *((_QWORD *)&v128 + 1) = a3 + 4;
  LODWORD(v129) = v19;
  LODWORD(v128) = 37;
  if ( *(_QWORD *)(v13 + 5888) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    v20 = *(_QWORD *)(v13 + 5888);
  }
  else
  {
    if ( !*(_QWORD *)(v13 + 5872) )
      goto LABEL_30;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    v20 = *(_QWORD *)(v13 + 5872);
  }
  NwfUpcallMsg((PIO_CSQ)(*(_QWORD *)(v20 + 24) + 40LL), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v128);
  v18 = a3 + 4;
LABEL_30:
  if ( (byte_1400AF803 & 2) != 0 )
    McTemplateK0pjb6q_EtwWriteTransfer(
      v18,
      (unsigned int)AssocComplete,
      *(_QWORD *)(a1 + 2616) + 4920,
      *(_QWORD *)(a1 + 2616),
      *(_QWORD *)(a1 + 2616) + 4920LL,
      v18,
      *(_DWORD *)(a3 + 12));
  ExtSTASnapshotDiagStats((struct EXTSTA_VELAN *)a1);
  v111 = 0;
  if ( v110 >= 2 )
    v111 = *(_DWORD *)(a3 + 92);
  v131 = 0;
  v132 = 0;
  MacAddrToLogString(a3 + 4, v21, &v131);
  if ( (unsigned int)dword_1400AE050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400AE050, 0x200000000000LL) )
  {
    v24 = *(_DWORD *)(a1 + 8);
    v119 = *(_DWORD *)(a1 + 344);
    v121 = v24 & 1;
    v120 = (v24 >> 1) & 1;
    v122 = *(_DWORD *)(a1 + 328);
    v123 = *(_DWORD *)(a1 + 1612);
    v124 = *(_DWORD *)(a3 + 40);
    v125 = *(_DWORD *)(a3 + 32);
    LODWORD(v114) = *(_DWORD *)(a3 + 24);
    v106 = *(_BYTE *)(a3 + 17);
    v107[0] = *(_BYTE *)(a3 + 16);
    LODWORD(v115) = v111;
    LODWORD(v116) = *(_DWORD *)(a3 + 60);
    LODWORD(v117) = *(_DWORD *)(a3 + 56);
    LODWORD(v118) = *(_DWORD *)(a3 + 52);
    Size_4 = *(_DWORD *)(a3 + 12);
    *(_QWORD *)&v105 = &v131;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v121,
      (unsigned int)&byte_1400A51A7,
      v22,
      v23,
      (__int64)&v105,
      (__int64)&Size_4,
      (__int64)&v118,
      (__int64)&v117,
      (__int64)&v116,
      (__int64)&v115,
      (__int64)v107,
      (__int64)&v106,
      (__int64)&v114,
      (__int64)&v125,
      (__int64)&v124,
      (__int64)&v123,
      (__int64)&v122,
      (__int64)&v121,
      (__int64)&v120,
      (__int64)&v119);
  }
  *(_DWORD *)(a1 + 404) = *(_DWORD *)(a3 + 12);
  *(_DWORD *)(a1 + 412) = v111;
  v25 = *(_DWORD *)(a3 + 12);
  v111 = v25;
  if ( ((v25 - 0x10000) & 0xFFFCFFFF) == 0 && v25 != 0x40000 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    *(_DWORD *)(a3 + 12) = 0;
    v111 = 0;
  }
  memset(v133, 0, sizeof(v133));
  if ( v111 )
  {
    if ( (unsigned int)dword_1400AE088 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400AE088, 4) )
    {
      Size_4 = *(unsigned __int8 *)(a3 + 16);
      if ( v112 )
      {
        if ( v112 == 1 )
        {
          v28 = "Ft";
        }
        else if ( v112 == 2 )
        {
          v28 = "PbssNotInDs";
        }
        else
        {
          v28 = "ToStringFailed";
        }
      }
      else
      {
        v28 = "General";
      }
      v29 = (stringify *)*(unsigned int *)(a3 + 60);
      *(_QWORD *)&v105 = v28;
      v30 = stringify::ToLogString(v29, (enum _DOT11_CIPHER_ALGORITHM)v14);
      v31 = (stringify *)*(unsigned int *)(a3 + 56);
      v118 = v30;
      v33 = stringify::ToLogString(v31, v32);
      v34 = (stringify *)*(unsigned int *)(a3 + 52);
      v117 = v33;
      v36 = stringify::ToLogString(v34, v35);
      v37 = *(unsigned int *)(a3 + 12);
      v116 = v36;
      v39 = Dot11AssocStatusToLogString(v37, v38, v133);
      v43 = byte_1400A5113;
LABEL_63:
      v115 = v39;
      v114 = &v131;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v40,
        (_DWORD)v43,
        v41,
        v42,
        (__int64)&v114,
        (__int64)&v115,
        (__int64)&v116,
        (__int64)&v117,
        (__int64)&v118,
        (__int64)&v105,
        (__int64)&Size_4);
    }
  }
  else if ( (unsigned int)dword_1400AE088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400AE088, 4) )
  {
    Size_4 = *(unsigned __int8 *)(a3 + 16);
    if ( v112 )
    {
      if ( v112 == 1 )
      {
        v44 = "Ft";
      }
      else if ( v112 == 2 )
      {
        v44 = "PbssNotInDs";
      }
      else
      {
        v44 = "ToStringFailed";
      }
    }
    else
    {
      v44 = "General";
    }
    v45 = (stringify *)*(unsigned int *)(a3 + 60);
    *(_QWORD *)&v105 = v44;
    v46 = stringify::ToLogString(v45, (enum _DOT11_CIPHER_ALGORITHM)v14);
    v47 = (stringify *)*(unsigned int *)(a3 + 56);
    v118 = v46;
    v49 = stringify::ToLogString(v47, v48);
    v50 = (stringify *)*(unsigned int *)(a3 + 52);
    v117 = v49;
    v52 = stringify::ToLogString(v50, v51);
    v53 = *(unsigned int *)(a3 + 12);
    v116 = v52;
    v39 = Dot11AssocStatusToLogString(v53, v54, v133);
    v43 = &byte_1400A507F;
    goto LABEL_63;
  }
  v55 = *(struct _WFD_ROLE **)(a1 + 2624);
  if ( v55 )
  {
    *(_BYTE *)(a1 + 408) = 0;
    if ( WFDRoleParseWFDStatusFromAssocCompletion(v55, (struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)a3, v104) >= 0 )
      *(_BYTE *)(a1 + 408) = v104[0];
  }
  v56 = *(_DWORD *)(a3 + 24);
  if ( v56 )
  {
    if ( *(_BYTE *)(a3 + 16) )
    {
      v57 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_74;
      v58 = 29;
    }
    else
    {
      v57 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_74;
      v58 = 30;
    }
    AttachedDevice = v57->AttachedDevice;
    v105 = 0;
    LOWORD(v105) = v56;
    *((_QWORD *)&v105 + 1) = a3 + *(unsigned int *)(a3 + 20);
    WPP_SF__HEX_(AttachedDevice, v58, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids, &v105);
  }
LABEL_74:
  v60 = *(_DWORD *)(a3 + 32);
  if ( v60 )
  {
    if ( *(_BYTE *)(a3 + 17) )
    {
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v62 = 31;
LABEL_80:
        v63 = v61->AttachedDevice;
        v105 = 0;
        LOWORD(v105) = v60;
        *((_QWORD *)&v105 + 1) = a3 + *(unsigned int *)(a3 + 28);
        WPP_SF__HEX_(v63, v62, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids, &v105);
      }
    }
    else
    {
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v62 = 32;
        goto LABEL_80;
      }
    }
  }
  v64 = *(_DWORD *)(a3 + 40);
  if ( v64 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v65 = WPP_GLOBAL_Control->AttachedDevice;
    v105 = 0;
    LOWORD(v105) = v64;
    *((_QWORD *)&v105 + 1) = a3 + *(unsigned int *)(a3 + 36);
    WPP_SF__HEX_(v65, 33, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids, &v105);
  }
  if ( *(_DWORD *)(a3 + 12) )
  {
    if ( v110 < 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d_MAC_L(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)v14,
          v26,
          *(_DWORD *)(*(_QWORD *)(v13 + 16) + 1708LL),
          a3 + 4);
    }
    else
    {
      LODWORD(v14) = (_DWORD)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d_MAC_Ld(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)WPP_GLOBAL_Control,
          v26,
          *(_DWORD *)(*(_QWORD *)(v13 + 16) + 1708LL),
          a3 + 4);
    }
    if ( *(_DWORD *)(v13 + 5916) == 10 )
      OWEOnAssociationFailure((struct _VELAN *)v13, Flink, v26);
    goto LABEL_92;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d_MAC_d(
      WPP_GLOBAL_Control->AttachedDevice,
      (_DWORD)v14,
      v26,
      *(_DWORD *)(*(_QWORD *)(v13 + 16) + 1708LL),
      a3 + 4);
  if ( v110 >= 2 && *(_DWORD *)(a3 + 88) && *(_DWORD *)(v13 + 5624) )
  {
    v70 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_92:
      v10 = -1073741823;
      goto LABEL_93;
    }
    v71 = 37;
LABEL_107:
    WPP_SF_(v70->AttachedDevice, v71, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
    goto LABEL_92;
  }
  if ( *(_DWORD *)(a1 + 1612) != 1 )
  {
    v83 = pvAssocEntry[6];
    if ( v83 )
    {
      v84 = v83 - 16;
      if ( *(_QWORD *)v84 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v84, (PVOID)v84);
      else
        ExFreePoolWithTag((PVOID)v84, *(_DWORD *)(v84 + 8));
      pvAssocEntry[6] = 0;
    }
    if ( !*(_QWORD *)(v13 + 5888) )
      goto LABEL_164;
    v85 = Size;
    pvAssocEntry[6] = 0;
    v86 = v85 + 16;
    if ( v85 >= 0xFFFFFFF0 )
    {
LABEL_162:
      v89 = (void *)pvAssocEntry[6];
      if ( v89 )
      {
        memmove(v89, (const void *)a3, v85);
        *((_DWORD *)pvAssocEntry + 11) = Size;
      }
LABEL_164:
      *(_DWORD *)(a1 + 1604) = *(_DWORD *)(a1 + 392);
      *(_WORD *)(a1 + 1608) = *(_WORD *)(a1 + 396);
      goto LABEL_165;
    }
    if ( v86 > 0x40 )
    {
      if ( v86 > 0x100 )
      {
        if ( v86 > 0x400 )
        {
          if ( v86 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v86, 895579251, v27);
LABEL_160:
            v85 = Size;
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[2] = 895579251;
              pvAssocEntry[6] = (__int64)(Pool2 + 4);
            }
            goto LABEL_162;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
      else
      {
        p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_160;
  }
  if ( (*(_DWORD *)(a1 + 8) & 3) == 0 )
  {
    v70 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_92;
    v71 = 38;
    goto LABEL_107;
  }
  if ( !ExtSTACancelConnRoamingTimer((struct EXTSTA_VELAN *)a1) )
    goto LABEL_92;
  v73 = *(_DWORD *)(a3 + 84) >> 2;
  v113 = 1;
  Size_4 = v73;
  if ( v73 > 0xFFFF )
  {
    v70 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_92;
    v71 = 39;
    goto LABEL_107;
  }
  if ( v73 > *(_DWORD *)(a1 + 1688) )
  {
    v74 = 4 * v73 + 16;
    if ( v74 < 0x10 )
    {
LABEL_118:
      v10 = -1073741670;
      goto LABEL_93;
    }
    if ( v74 > 0x40 )
    {
      if ( v74 > 0x100 )
      {
        if ( v74 > 0x400 )
        {
          if ( v74 > 0x800 )
          {
            p_DeviceQueue = 0;
            v76 = (_DWORD *)ExAllocatePool2(64, v74, 912356467, v72);
            goto LABEL_129;
          }
          p_DeviceQueue = &stru_1400B0180;
        }
        else
        {
          p_DeviceQueue = &Lookaside;
        }
      }
      else
      {
        p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
      }
    }
    else
    {
      p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    v76 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_129:
    if ( !v76 )
      goto LABEL_118;
    *(_QWORD *)v76 = p_DeviceQueue;
    v77 = (char *)(v76 + 4);
    v76[2] = 912356467;
    v78 = *(_QWORD *)(a1 + 1696);
    if ( v78 )
    {
      v79 = v78 - 16;
      if ( *(_QWORD *)v79 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v79, (PVOID)v79);
      else
        ExFreePoolWithTag((PVOID)v79, *(_DWORD *)(v79 + 8));
    }
    v73 = Size_4;
    *(_QWORD *)(a1 + 1696) = v77;
    *(_DWORD *)(a1 + 1688) = v73;
  }
  v80 = *(void **)(a1 + 1696);
  *(_DWORD *)(a1 + 1692) = v73;
  memmove(v80, (const void *)(a3 + *(unsigned int *)(a3 + 80)), 4LL * v73);
  if ( *(_DWORD *)(a1 + 332) )
    ExtSTADeleteAssociation(a1, a1 + 1604, qword_1400A1D38);
  *(_DWORD *)(a1 + 1604) = *(_DWORD *)(a3 + 4);
  *(_WORD *)(a1 + 1608) = *(_WORD *)(a3 + 8);
  *(_DWORD *)(a1 + 8) |= 4u;
  v81 = *(_DWORD *)(a1 + 344);
  *(_DWORD *)(a1 + 352) = *(_DWORD *)(a3 + 76);
  v82 = v81 - 1;
  if ( v82 )
  {
    if ( v82 == 1 && !*(_DWORD *)(a3 + 76) )
      *(_DWORD *)(a1 + 344) = 0;
  }
  else
  {
    *(_DWORD *)(a1 + 344) = *(_DWORD *)(a3 + 76);
  }
  PtRequestAdapterAsync(
    *(struct _ADAPT **)(*(_QWORD *)(a1 + 2616) + 16LL),
    0,
    0xE020183u,
    *(void **)(a1 + 1680),
    *(_DWORD *)(a1 + 1668));
  *(_DWORD *)(a1 + 1552) ^= ((unsigned __int8)*(_DWORD *)(a1 + 1552) ^ (unsigned __int8)(4 * *(_BYTE *)(a3 + 72))) & 4;
LABEL_165:
  *(_OWORD *)(a1 + 1616) = *(_OWORD *)(a1 + 356);
  *(_OWORD *)(a1 + 1632) = *(_OWORD *)(a1 + 372);
  *(_DWORD *)(a1 + 1648) = *(_DWORD *)(a1 + 388);
  *((_DWORD *)pvAssocEntry + 9) = *(_DWORD *)(a1 + 1604);
  *((_WORD *)pvAssocEntry + 20) = *(_WORD *)(a1 + 1608);
  _InterlockedExchange((volatile __int32 *)(a1 + 804), 0);
  _InterlockedExchange((volatile __int32 *)(a1 + 800), 0);
  *(_QWORD *)(a1 + 808) = 0;
  _InterlockedExchange((volatile __int32 *)(a1 + 820), 0);
  if ( ++*(_DWORD *)(a1 + 332) == 1 )
    ExtSTASetPacketFilterForAssocChange((struct EXTSTA_VELAN *)a1, 1, v126);
  v90 = *(_DWORD *)(a3 + 60);
  *(_DWORD *)(a1 + 1552) |= 1u;
  v91 = v110 < 2;
  *(_DWORD *)(a1 + 1656) = v90;
  *((_DWORD *)pvAssocEntry + 7) = *(_DWORD *)(a3 + 52);
  *((_DWORD *)pvAssocEntry + 8) = *(_DWORD *)(a3 + 56);
  *((_DWORD *)pvAssocEntry + 6) = 3;
  if ( v91 || (v92 = *(_DWORD *)(a3 + 88)) == 0 )
    v92 = 0;
  *(_DWORD *)(a1 + 1660) = v92;
  ++Flink->uObjCnt;
  _InterlockedIncrement((volatile signed __int32 *)&Flink->uRefCnt);
  v93 = *((_DWORD *)Flink + 10) & 0xFFFFFFED | 2;
  *((_DWORD *)Flink + 10) = v93;
  if ( *(_QWORD *)(v13 + 5888) )
  {
    v94 = v93 | 4;
    *((_DWORD *)Flink + 10) = v94;
    if ( *(_QWORD *)(v13 + 5888) == *(_QWORD *)(v13 + 5880) )
    {
      *((_DWORD *)Flink + 10) = v94 ^ ((unsigned __int8)v94 ^ (unsigned __int8)(8 * *(_BYTE *)(a3 + 73))) & 8;
    }
    else
    {
      *(_BYTE *)(a3 + 73) = 0;
      *((_DWORD *)Flink + 10) &= ~8u;
      v95 = *(_QWORD *)(*(_QWORD *)(v13 + 5888) + 24LL);
      if ( *(_DWORD *)(v95 + 184) && !*(_DWORD *)(v95 + 168) )
        *((_DWORD *)Flink + 10) &= ~4u;
    }
  }
  else
  {
    *((_DWORD *)Flink + 10) = v93 & 0xFFFFFFF3;
  }
  v96 = *(_DWORD *)(v13 + 136);
  *(_DWORD *)(v13 + 136) = v96 + 1;
  Flink->uSessionId = v96;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF__MAC_ll(
      WPP_GLOBAL_Control->AttachedDevice,
      41,
      WPP_GLOBAL_Control,
      a3 + 4,
      (*((_DWORD *)Flink + 10) >> 2) & 1,
      (*((_DWORD *)Flink + 10) >> 3) & 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids, v112, 2);
  }
  v97 = v112;
  *(_DWORD *)(a1 + 2748) = 0;
  if ( v97 != 1 )
  {
    if ( *(_DWORD *)(a1 + 1612) == 1 )
    {
      if ( v97 == 2 )
        *(_DWORD *)(a1 + 2748) = 1;
      Dot11RsnaOnAssociate(
        (_QWORD *)v13,
        (struct _DOT11_SSID *)(a1 + 1616),
        Flink,
        v97,
        (struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)a3,
        Size,
        v127);
    }
    if ( *(_DWORD *)(v13 + 5624) )
      SafeModeOnAssociate((struct _VELAN *)v13, Flink, (struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)a3, v27);
    DWORD2(v128) = *(_DWORD *)(a3 + 4);
    WORD6(v128) = *(_WORD *)(a3 + 8);
    LODWORD(v128) = 0;
    LODWORD(v129) = Flink->uSessionId;
    DWORD1(v129) = (*((_DWORD *)Flink + 10) >> 2) & 1;
    v98 = (*((_DWORD *)Flink + 10) >> 3) & 1;
    v130 = a3;
    *((_QWORD *)&v129 + 1) = __PAIR64__(Size, v98);
    if ( *(_QWORD *)(v13 + 5888) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
      v99 = *(_QWORD *)(v13 + 5888);
    }
    else
    {
      if ( !*(_QWORD *)(v13 + 5872) )
        goto LABEL_197;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 44, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
      v99 = *(_QWORD *)(v13 + 5872);
    }
    NwfUpcallMsg((PIO_CSQ)(*(_QWORD *)(v99 + 24) + 40LL), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v128);
LABEL_197:
    if ( (*((_DWORD *)Flink + 10) & 0xC) != 4 )
    {
      ++*(_DWORD *)(a1 + 336);
      if ( *(_DWORD *)(a1 + 1612) == 1 )
      {
        v100 = *(_DWORD *)(a1 + 344);
        *(_DWORD *)(a1 + 348) = v100;
        if ( v100 != 1 )
          ExtSTAIndicateNetworkChange((struct EXTSTA_VELAN *)a1, (v100 != 2) + 1);
        *(_DWORD *)(a1 + 344) = 1;
      }
      else if ( *(_DWORD *)(a1 + 336) == 1 )
      {
        ExtSTAIndicateMediaStatus((struct EXTSTA_VELAN *)a1, 1);
      }
    }
    goto LABEL_204;
  }
  Dot11RsnaOnFTAssociationCompletion(
    (struct _VELAN *)v13,
    (struct _DOT11_SSID *)(a1 + 1616),
    Flink,
    Size,
    (struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)a3);
LABEL_204:
  v10 = 0;
LABEL_205:
  if ( v113 )
  {
    v101 = *(struct _IRP **)(a1 + 16);
    *(_QWORD *)(a1 + 16) = 0;
    if ( v101 )
    {
      ExtSTACompleteConnection((struct EXTSTA_VELAN *)a1, v101, v10);
      if ( v10 < 0 )
        ExtSTATerminateConnection((struct EXTSTA_VELAN *)a1);
    }
  }
}

```

## disassembly

```asm
0x14005c9dc  push    rbp
0x14005c9de  push    rbx
0x14005c9df  push    rsi
0x14005c9e0  push    rdi
0x14005c9e1  push    r12
0x14005c9e3  push    r13
0x14005c9e5  push    r14
0x14005c9e7  push    r15
0x14005c9e9  lea     rbp, [rsp-0E8h]
0x14005c9f1  sub     rsp, 208h
0x14005c9f8  mov     rax, cs:__security_cookie
0x14005c9ff  xor     rax, rsp
0x14005ca02  mov     [rbp+120h+var_50], rax
0x14005ca09  mov     rax, [rbp+120h+arg_20]
0x14005ca10  xor     esi, esi
0x14005ca12  mov     [rbp+120h+var_118], rax
0x14005ca16  xor     r12d, r12d
0x14005ca19  xor     eax, eax
0x14005ca1b  mov     dword ptr [rbp+120h+Size], r9d
0x14005ca1f  cmp     [rcx+6A8h], al
0x14005ca25  xorps   xmm0, xmm0
0x14005ca28  mov     [rbp+120h+var_F0], rax
0x14005ca2c  mov     rdi, r8
0x14005ca2f  mov     [rbp+120h+var_168], eax
0x14005ca32  mov     rbx, rcx
0x14005ca35  setz    al
0x14005ca38  mov     [rbp+120h+var_16C], edx
0x14005ca3b  mov     [rbp+120h+var_11C], eax
0x14005ca3e  mov     r15d, 0C0000001h
0x14005ca44  mov     [rbp+120h+var_1A0], sil
0x14005ca48  movups  [rbp+120h+var_110], xmm0
0x14005ca4c  movups  [rbp+120h+var_100], xmm0
0x14005ca50  cmp     r9d, 4
0x14005ca54  jb      loc_14005D989
0x14005ca5a  cmp     byte ptr [r8], 80h
0x14005ca5e  jnz     loc_14005D989
0x14005ca64  movzx   eax, word ptr [r8+2]
0x14005ca69  cmp     r9d, eax
0x14005ca6c  jb      loc_14005D989
0x14005ca72  mov     cl, [r8+1]
0x14005ca76  lea     r8d, [rsi+1]
0x14005ca7a  cmp     cl, r8b
0x14005ca7d  jnz     short loc_14005CA8E
0x14005ca7f  cmp     eax, 58h ; 'X'
0x14005ca82  jb      loc_14005D96F
0x14005ca88  mov     [rbp+120h+var_174], r8d
0x14005ca8c  jmp     short loc_14005CAA7
0x14005ca8e  cmp     cl, 2
0x14005ca91  jnz     loc_14005D96F
0x14005ca97  cmp     eax, 60h ; '`'
0x14005ca9a  jb      loc_14005D96F
0x14005caa0  mov     [rbp+120h+var_174], 2
0x14005caa7  mov     r13, [rbx+0A38h]
0x14005caae  lea     rdx, [rdi+4]; Buf2
0x14005cab2  movzx   ecx, byte ptr [rdx+5]
0x14005cab6  movzx   eax, byte ptr [rdx+4]
0x14005caba  xor     ecx, eax
0x14005cabc  and     ecx, 800000FFh
0x14005cac2  jge     short loc_14005CAD0
0x14005cac4  sub     ecx, r8d
0x14005cac7  or      ecx, 0FFFFFF00h
0x14005cacd  add     ecx, r8d
0x14005cad0  mov     r14d, ecx
0x14005cad3  add     r14, 0Ah
0x14005cad7  shl     r14, 4
0x14005cadb  add     r14, r13
0x14005cade  mov     rsi, [r14]
0x14005cae1  cmp     r14, rsi
0x14005cae4  jz      short loc_14005CB07
0x14005cae6  lea     rcx, [rsi+10h]; Buf1
0x14005caea  mov     r8d, 6; Size
0x14005caf0  call    memcmp
0x14005caf5  test    eax, eax
0x14005caf7  jz      short loc_14005CB09
0x14005caf9  mov     rsi, [rsi]
0x14005cafc  cmp     r14, rsi
0x14005caff  jz      short loc_14005CB07
0x14005cb01  lea     rdx, [rdi+4]
0x14005cb05  jmp     short loc_14005CAE6
0x14005cb07  xor     esi, esi
0x14005cb09  test    rsi, rsi
0x14005cb0c  jnz     short loc_14005CB3D
0x14005cb0e  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb15  lea     r14, WPP_GLOBAL_Control
0x14005cb1c  cmp     rcx, r14
0x14005cb1f  jz      loc_14005D15D
0x14005cb25  lea     edx, [rsi+18h]
0x14005cb28  mov     rcx, [rcx+18h]
0x14005cb2c  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005cb33  call    WPP_SF_
0x14005cb38  jmp     loc_14005D15D
0x14005cb3d  mov     r12, [rsi+40h]
0x14005cb41  test    r12, r12
0x14005cb44  jz      loc_14005D945
0x14005cb4a  cmp     dword ptr [r12+18h], 1
0x14005cb50  jnz     loc_14005D945
0x14005cb56  dec     dword ptr [rbx+148h]
0x14005cb5c  lea     rcx, [rdi+4]
0x14005cb60  mov     eax, [rdi+0Ch]
0x14005cb63  lea     r14, WPP_GLOBAL_Control
0x14005cb6a  mov     qword ptr [rbp+120h+var_110+8], rcx
0x14005cb6e  lea     r15, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005cb75  mov     dword ptr [rbp+120h+var_100], eax
0x14005cb78  mov     dword ptr [rbp+120h+var_110], 25h ; '%'
0x14005cb7f  cmp     qword ptr [r13+1700h], 0
0x14005cb87  jz      short loc_14005CBAF
0x14005cb89  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cb90  cmp     rcx, r14
0x14005cb93  jz      short loc_14005CBA6
0x14005cb95  mov     rcx, [rcx+18h]
0x14005cb99  mov     edx, 1Ah
0x14005cb9e  mov     r8, r15
0x14005cba1  call    WPP_SF_
0x14005cba6  mov     rax, [r13+1700h]
0x14005cbad  jmp     short loc_14005CBDD
0x14005cbaf  cmp     qword ptr [r13+16F0h], 0
0x14005cbb7  jz      short loc_14005CBF2
0x14005cbb9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cbc0  cmp     rcx, r14
0x14005cbc3  jz      short loc_14005CBD6
0x14005cbc5  mov     rcx, [rcx+18h]
0x14005cbc9  mov     edx, 1Bh
0x14005cbce  mov     r8, r15
0x14005cbd1  call    WPP_SF_
0x14005cbd6  mov     rax, [r13+16F0h]
0x14005cbdd  mov     rcx, [rax+18h]
0x14005cbe1  lea     rdx, [rbp+120h+var_110]; struct DOT11_AUTH_UPCALL_REQUEST *
0x14005cbe5  add     rcx, 28h ; '('; Csq
0x14005cbe9  call    ?NwfUpcallMsg@@YAJPEAUNWF_AUTH_UPCALL@@PEBUDOT11_AUTH_UPCALL_REQUEST@@@Z; NwfUpcallMsg(NWF_AUTH_UPCALL *,DOT11_AUTH_UPCALL_REQUEST const *)
0x14005cbee  lea     rcx, [rdi+4]
0x14005cbf2  test    cs:byte_1400AF803, 2
0x14005cbf9  jz      short loc_14005CC26
0x14005cbfb  mov     r9, [rbx+0A38h]
0x14005cc02  lea     rdx, AssocComplete
0x14005cc09  mov     eax, [rdi+0Ch]
0x14005cc0c  mov     dword ptr [rsp+240h+var_210], eax
0x14005cc10  mov     [rsp+240h+var_218], rcx
0x14005cc15  lea     r8, [r9+1338h]
0x14005cc1c  mov     [rsp+240h+var_220], r8
0x14005cc21  call    McTemplateK0pjb6q_EtwWriteTransfer
0x14005cc26  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14005cc29  call    ?ExtSTASnapshotDiagStats@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTASnapshotDiagStats(EXTSTA_VELAN *)
0x14005cc2e  cmp     [rbp+120h+var_174], 2
0x14005cc32  mov     [rbp+120h+var_170], 0
0x14005cc39  jb      short loc_14005CC41
0x14005cc3b  mov     eax, [rdi+5Ch]
0x14005cc3e  mov     [rbp+120h+var_170], eax
0x14005cc41  xorps   xmm0, xmm0
0x14005cc44  lea     r8, [rbp+120h+var_E8]
0x14005cc48  xor     eax, eax
0x14005cc4a  lea     rcx, [rdi+4]
0x14005cc4e  movups  [rbp+120h+var_E8], xmm0
0x14005cc52  mov     [rbp+120h+var_D8], ax
0x14005cc56  call    MacAddrToLogString
0x14005cc5b  mov     eax, cs:dword_1400AE050
0x14005cc61  cmp     eax, 5
0x14005cc64  jbe     loc_14005CDA2
0x14005cc6a  mov     rdx, 200000000000h
0x14005cc74  lea     rcx, dword_1400AE050
0x14005cc7b  call    _tlgKeywordOn
0x14005cc80  test    al, al
0x14005cc82  jz      loc_14005CDA2
0x14005cc88  mov     eax, [rbx+158h]
0x14005cc8e  lea     rdx, byte_1400A51A7
0x14005cc95  mov     ecx, [rbx+8]
0x14005cc98  mov     [rbp+120h+var_138], eax
0x14005cc9b  mov     eax, ecx
0x14005cc9d  shr     eax, 1
0x14005cc9f  and     ecx, 1
0x14005cca2  and     eax, 1
0x14005cca5  mov     [rbp+120h+var_130], ecx
0x14005cca8  mov     [rbp+120h+var_134], eax
0x14005ccab  mov     eax, [rbx+148h]
0x14005ccb1  mov     [rbp+120h+var_12C], eax
0x14005ccb4  mov     eax, [rbx+64Ch]
0x14005ccba  mov     [rbp+120h+var_128], eax
0x14005ccbd  mov     eax, [rdi+28h]
0x14005ccc0  mov     [rbp+120h+var_124], eax
0x14005ccc3  mov     eax, [rdi+20h]
0x14005ccc6  mov     [rbp+120h+var_120], eax
0x14005ccc9  mov     eax, [rdi+18h]
0x14005cccc  mov     dword ptr [rbp+120h+var_160], eax
0x14005cccf  mov     al, [rdi+11h]
0x14005ccd2  mov     [rbp+120h+var_180], al
0x14005ccd5  mov     al, [rdi+10h]
0x14005ccd8  mov     [rbp+120h+var_17F], al
0x14005ccdb  mov     eax, [rbp+120h+var_170]
0x14005ccde  mov     dword ptr [rbp+120h+var_158], eax
0x14005cce1  mov     eax, [rdi+3Ch]
0x14005cce4  mov     dword ptr [rbp+120h+var_150], eax
0x14005cce7  mov     eax, [rdi+38h]
0x14005ccea  mov     dword ptr [rbp+120h+var_148], eax
0x14005cced  mov     eax, [rdi+34h]
0x14005ccf0  mov     dword ptr [rbp+120h+var_140], eax
0x14005ccf3  mov     eax, [rdi+0Ch]
0x14005ccf6  mov     dword ptr [rbp+120h+Size+4], eax
0x14005ccf9  lea     rax, [rbp+120h+var_E8]
0x14005ccfd  mov     qword ptr [rbp+120h+var_190], rax
0x14005cd01  lea     rax, [rbp+120h+var_138]
0x14005cd05  mov     [rsp+240h+var_1A8], rax
0x14005cd0d  lea     rax, [rbp+120h+var_134]
0x14005cd11  mov     [rsp+240h+var_1B0], rax
0x14005cd19  lea     rax, [rbp+120h+var_130]
0x14005cd1d  mov     [rsp+240h+var_1B8], rax
0x14005cd25  lea     rax, [rbp+120h+var_12C]
0x14005cd29  mov     [rsp+240h+var_1C0], rax
0x14005cd31  lea     rax, [rbp+120h+var_128]
0x14005cd35  mov     [rsp+240h+var_1C8], rax
0x14005cd3a  lea     rax, [rbp+120h+var_124]
0x14005cd3e  mov     [rsp+240h+var_1D0], rax
0x14005cd43  lea     rax, [rbp+120h+var_120]
0x14005cd47  mov     [rsp+240h+var_1D8], rax
0x14005cd4c  lea     rax, [rbp+120h+var_160]
0x14005cd50  mov     [rsp+240h+var_1E0], rax
0x14005cd55  lea     rax, [rbp+120h+var_180]
0x14005cd59  mov     [rsp+240h+var_1E8], rax
0x14005cd5e  lea     rax, [rbp+120h+var_17F]
0x14005cd62  mov     [rsp+240h+var_1F0], rax
0x14005cd67  lea     rax, [rbp+120h+var_158]
0x14005cd6b  mov     [rsp+240h+var_1F8], rax
0x14005cd70  lea     rax, [rbp+120h+var_150]
0x14005cd74  mov     [rsp+240h+var_200], rax
0x14005cd79  lea     rax, [rbp+120h+var_148]
0x14005cd7d  mov     [rsp+240h+var_208], rax
0x14005cd82  lea     rax, [rbp+120h+var_140]
0x14005cd86  mov     [rsp+240h+var_210], rax
0x14005cd8b  lea     rax, [rbp+120h+Size+4]
0x14005cd8f  mov     [rsp+240h+var_218], rax
0x14005cd94  lea     rax, [rbp+120h+var_190]
0x14005cd98  mov     [rsp+240h+var_220], rax
0x14005cd9d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U?$_tlgWrapperByVal@$00@@U3@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapperByVal@$00@@544444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005cda2  mov     eax, [rdi+0Ch]
0x14005cda5  mov     [rbx+194h], eax
0x14005cdab  mov     eax, [rbp+120h+var_170]
0x14005cdae  mov     [rbx+19Ch], eax
0x14005cdb4  mov     ecx, [rdi+0Ch]
0x14005cdb7  mov     [rbp+120h+var_170], ecx
0x14005cdba  lea     eax, [rcx-10000h]
0x14005cdc0  test    eax, 0FFFCFFFFh
0x14005cdc5  jnz     short loc_14005CDFA
0x14005cdc7  cmp     ecx, 40000h
0x14005cdcd  jz      short loc_14005CDFA
0x14005cdcf  mov     rcx, cs:WPP_GLOBAL_Control
0x14005cdd6  cmp     rcx, r14
0x14005cdd9  jz      short loc_14005CDEC
0x14005cddb  mov     rcx, [rcx+18h]
0x14005cddf  mov     edx, 1Ch
0x14005cde4  mov     r8, r15
0x14005cde7  call    WPP_SF_
0x14005cdec  mov     dword ptr [rdi+0Ch], 0
0x14005cdf3  mov     [rbp+120h+var_170], 0
0x14005cdfa  xor     edx, edx; Val
0x14005cdfc  lea     rcx, [rbp+120h+var_D0]; void *
0x14005ce00  mov     r8d, 80h; Size
0x14005ce06  call    memset
0x14005ce0b  cmp     [rbp+120h+var_170], 0
0x14005ce0f  mov     eax, cs:dword_1400AE088
0x14005ce15  jz      loc_14005CEB7
0x14005ce1b  cmp     eax, 2
0x14005ce1e  jbe     loc_14005CF9E
0x14005ce24  mov     edx, 4
0x14005ce29  lea     rcx, dword_1400AE088
0x14005ce30  call    _tlgKeywordOn
0x14005ce35  test    al, al
0x14005ce37  jz      loc_14005CF9E
0x14005ce3d  movzx   eax, byte ptr [rdi+10h]
0x14005ce41  mov     ecx, [rbp+120h+var_16C]
0x14005ce44  mov     dword ptr [rbp+120h+Size+4], eax
0x14005ce47  test    ecx, ecx
0x14005ce49  jz      short loc_14005CE70
0x14005ce4b  sub     ecx, 1
0x14005ce4e  jz      short loc_14005CE67
0x14005ce50  cmp     ecx, 1
0x14005ce53  jz      short loc_14005CE5E
0x14005ce55  lea     rax, aTostringfailed; "ToStringFailed"
0x14005ce5c  jmp     short loc_14005CE77
0x14005ce5e  lea     rax, aPbssnotinds; "PbssNotInDs"
0x14005ce65  jmp     short loc_14005CE77
0x14005ce67  lea     rax, aFt; "Ft"
0x14005ce6e  jmp     short loc_14005CE77
0x14005ce70  lea     rax, aGeneral; "General"
0x14005ce77  mov     ecx, [rdi+3Ch]; this
0x14005ce7a  mov     qword ptr [rbp+120h+var_190], rax
0x14005ce7e  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x14005ce83  mov     ecx, [rdi+38h]; this
0x14005ce86  mov     [rbp+120h+var_140], rax
0x14005ce8a  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_CIPHER_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_CIPHER_ALGORITHM)
0x14005ce8f  mov     ecx, [rdi+34h]; this
0x14005ce92  mov     [rbp+120h+var_148], rax
0x14005ce96  call    ?ToLogString@stringify@@YAPEBDW4_DOT11_AUTH_ALGORITHM@@@Z; stringify::ToLogString(_DOT11_AUTH_ALGORITHM)
0x14005ce9b  mov     ecx, [rdi+0Ch]
0x14005ce9e  lea     r8, [rbp+120h+var_D0]
0x14005cea2  mov     [rbp+120h+var_150], rax
0x14005cea6  call    Dot11AssocStatusToLogString
0x14005ceab  lea     rdx, byte_1400A5113
0x14005ceb2  jmp     loc_14005CF4E
0x14005ceb7  cmp     eax, 4
0x14005ceba  jbe     loc_14005CF9E
0x14005cec0  mov     edx, 4
0x14005cec5  lea     rcx, dword_1400AE088
  ... truncated ...
```
