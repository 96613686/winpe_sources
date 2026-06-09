# ExtSTAAssocCompletion(EXTSTA_VELAN *,_DOT11_ASSOCIATION_TYPE,DOT11_ASSOCIATION_COMPLETION_PARAMETERS * const,ulong,DOT11_CONNECTION_INFO *)

- ea: `0x14005e1fc`
- end: `0x14005f23a`
- name: `?ExtSTAAssocCompletion@@YAXPEAUEXTSTA_VELAN@@W4_DOT11_ASSOCIATION_TYPE@@QEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@KPEAUDOT11_CONNECTION_INFO@@@Z`
- size: `4158`
- prototype: `void __fastcall(__int64, unsigned int, __int64, unsigned int, struct DOT11_MAC_STATE_ENTRY *)`
- caller_count: `1`
- callee_count: `38`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140068960`

## callees

- `0x140001008`
- `0x14000185c`
- `0x14000ab78`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140018a0c`
- `0x14001a34c`
- `0x140020998`
- `0x140020e04`
- `0x140020f20`
- `0x140025704`
- `0x14002f44c`
- `0x140032690`
- `0x140038f9c`
- `0x14003a2a8`
- `0x140046610`
- `0x140047794`
- `0x140047e48`
- `0x140053f88`
- `0x14005e1fc`
- `0x14005f8f4`
- `0x14005fec4`
- `0x140060758`
- `0x1400648d8`
- `0x140064df4`
- `0x140064eb8`
- `0x140064f24`
- `0x140064f9c`
- `0x140067fc0`
- `0x1400680cc`
- `0x14007d1a8`
- `0x1400975c0`
- `0x140097684`
- `0x140097788`
- `0x14009bbb0`
- `0x14009bcc0`
- `0x14009bfc0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005eafb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005ed07`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005eafb`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005ed07`
- `ntoskrnl!ExAllocatePool2` at `0x14005eb19`
- `ntoskrnl!ExAllocatePool2` at `0x14005ed25`
- `ntoskrnl!ExAllocatePool2` at `0x14005eb19`
- `ntoskrnl!ExAllocatePool2` at `0x14005ed25`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005e3cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005eb5d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005ec7e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005f20e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005e3cb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005eb5d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005ec7e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005f20e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eb6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ec8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f1e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f222`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005eb6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005ec8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f1e8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f222`

## pseudocode

```c
void __fastcall ExtSTAAssocCompletion(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        struct DOT11_MAC_STATE_ENTRY *a5)
{
  struct DOT11_MAC_STATE_ENTRY *i; // rsi
  __int64 *pvAssocEntry; // r13
  bool v7; // zf
  int v8; // r15d
  unsigned int v11; // eax
  char v12; // cl
  enum _DOT11_CIPHER_ALGORITHM v13; // edx
  __int64 v14; // r15
  const void *v15; // r12
  struct DOT11_MAC_STATE_ENTRY **v16; // r14
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  __int64 *v19; // rax
  __int64 **v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // rdx
  int v26; // r8d
  int v27; // r9d
  unsigned int v28; // ecx
  int v29; // ecx
  unsigned int v30; // r8d
  unsigned int v31; // r9d
  const char *v32; // rax
  stringify *v33; // rcx
  const char *v34; // rax
  stringify *v35; // rcx
  enum _DOT11_CIPHER_ALGORITHM v36; // edx
  const char *v37; // rax
  stringify *v38; // rcx
  enum _DOT11_AUTH_ALGORITHM v39; // edx
  const char *v40; // rax
  __int64 v41; // rcx
  __int64 v42; // rdx
  __int64 v43; // rax
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  char *v47; // rdx
  const char *v48; // rax
  stringify *v49; // rcx
  const char *v50; // rax
  stringify *v51; // rcx
  enum _DOT11_CIPHER_ALGORITHM v52; // edx
  const char *v53; // rax
  stringify *v54; // rcx
  enum _DOT11_AUTH_ALGORITHM v55; // edx
  const char *v56; // rax
  __int64 v57; // rcx
  __int64 v58; // rdx
  struct _WFD_ROLE *v59; // rcx
  int v60; // eax
  PDEVICE_OBJECT v61; // rcx
  __int64 v62; // rdx
  _DEVICE_OBJECT *AttachedDevice; // rcx
  int v64; // eax
  PDEVICE_OBJECT v65; // rcx
  __int64 v66; // rdx
  _DEVICE_OBJECT *v67; // rcx
  int v68; // eax
  _DEVICE_OBJECT *v69; // rcx
  unsigned int v70; // eax
  unsigned int v71; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // r12
  _DWORD *v73; // rax
  char *v74; // r12
  __int64 v75; // rcx
  __int64 v76; // rcx
  void *v77; // rcx
  int v78; // ecx
  int v79; // ecx
  __int64 v80; // rcx
  __int64 v81; // rcx
  unsigned int v82; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // r12
  _DWORD *Pool2; // rax
  void *v85; // rcx
  int v86; // eax
  bool v87; // cf
  int v88; // eax
  unsigned int v89; // ecx
  int v90; // ecx
  __int64 v91; // rdx
  unsigned int v92; // ecx
  unsigned int v93; // ecx
  int IsEnabledDeviceUsageNoInline; // eax
  struct _DOT11_SSID *v95; // rdx
  int v96; // eax
  __int64 v97; // rax
  int v98; // eax
  struct _IRP *v99; // rdx
  PDEVICE_OBJECT v100; // rcx
  __int64 v101; // rdx
  unsigned __int8 v102[4]; // [rsp+A0h] [rbp-80h] BYREF
  size_t Size; // [rsp+A4h] [rbp-7Ch]
  __int128 v104; // [rsp+B0h] [rbp-70h] BYREF
  char v105; // [rsp+C0h] [rbp-60h] BYREF
  _BYTE v106[3]; // [rsp+C1h] [rbp-5Fh] BYREF
  unsigned int v107; // [rsp+C4h] [rbp-5Ch] BYREF
  int v108; // [rsp+C8h] [rbp-58h]
  unsigned int v109; // [rsp+CCh] [rbp-54h]
  unsigned int v110; // [rsp+D0h] [rbp-50h]
  int v111; // [rsp+D4h] [rbp-4Ch]
  int v112; // [rsp+D8h] [rbp-48h]
  __int128 *v113; // [rsp+E0h] [rbp-40h] BYREF
  __int64 v114; // [rsp+E8h] [rbp-38h] BYREF
  const char *v115; // [rsp+F0h] [rbp-30h] BYREF
  const char *v116; // [rsp+F8h] [rbp-28h] BYREF
  const char *v117; // [rsp+100h] [rbp-20h] BYREF
  int v118; // [rsp+108h] [rbp-18h] BYREF
  int v119; // [rsp+10Ch] [rbp-14h] BYREF
  int v120; // [rsp+110h] [rbp-10h] BYREF
  int v121; // [rsp+114h] [rbp-Ch] BYREF
  int v122; // [rsp+118h] [rbp-8h] BYREF
  int v123; // [rsp+11Ch] [rbp-4h] BYREF
  int v124; // [rsp+120h] [rbp+0h] BYREF
  int v125; // [rsp+124h] [rbp+4h]
  struct DOT11_MAC_STATE_ENTRY *v126; // [rsp+128h] [rbp+8h] BYREF
  __int128 v127; // [rsp+130h] [rbp+10h] BYREF
  __int128 v128; // [rsp+140h] [rbp+20h]
  __int64 v129; // [rsp+150h] [rbp+30h]
  __int128 v130; // [rsp+158h] [rbp+38h] BYREF
  __int16 v131; // [rsp+168h] [rbp+48h]
  _BYTE v132[128]; // [rsp+170h] [rbp+50h] BYREF

  i = 0;
  v126 = a5;
  pvAssocEntry = 0;
  LODWORD(Size) = a4;
  v7 = *(_BYTE *)(a1 + 1704) == 0;
  v129 = 0;
  v8 = -1073741823;
  v112 = 0;
  v110 = a2;
  v125 = v7;
  v111 = -1073741823;
  v102[0] = 0;
  v127 = 0;
  v128 = 0;
  if ( a4 < 4 || *(_BYTE *)a3 != 0x80 || (v11 = *(unsigned __int16 *)(a3 + 2), a4 < v11) )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    goto LABEL_20;
  }
  v12 = *(_BYTE *)(a3 + 1);
  v13 = DOT11_CIPHER_ALGO_WEP40;
  if ( v12 != 1 )
  {
    if ( v12 == 2 && v11 >= 0x60 )
    {
      v109 = 2;
      goto LABEL_10;
    }
LABEL_213:
    v100 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v101 = 23;
LABEL_212:
    WPP_SF_(v100->AttachedDevice, v101, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    return;
  }
  if ( v11 < 0x58 )
    goto LABEL_213;
  v109 = 1;
LABEL_10:
  v14 = *(_QWORD *)(a1 + 2616);
  v15 = (const void *)(a3 + 4);
  v16 = (struct DOT11_MAC_STATE_ENTRY **)(v14
                                        + 16
                                        * (((*(unsigned __int8 *)(a3 + 8) ^ *(unsigned __int8 *)(a3 + 9)) & 0x800000FF)
                                         + 10LL));
  for ( i = *v16;
        v16 != (struct DOT11_MAC_STATE_ENTRY **)i;
        i = (struct DOT11_MAC_STATE_ENTRY *)i->MacHashEntry.Linkage.Flink )
  {
    if ( !memcmp(i->MacHashEntry.MacKey, v15, 6u) )
      goto LABEL_15;
  }
  i = 0;
LABEL_15:
  if ( !i )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_19:
      v8 = -1073741823;
LABEL_20:
      if ( i )
      {
        i->pvAssocEntry = 0;
        if ( pvAssocEntry )
        {
          v19 = (__int64 *)*pvAssocEntry;
          if ( *(__int64 **)(*pvAssocEntry + 8) != pvAssocEntry
            || (v20 = (__int64 **)pvAssocEntry[1], *v20 != pvAssocEntry) )
          {
            __fastfail(3u);
          }
          *v20 = v19;
          v19[1] = (__int64)v20;
          v126 = (struct DOT11_MAC_STATE_ENTRY *)pvAssocEntry[2];
          Dot11DecObjCnt(&v126, v13);
          v21 = pvAssocEntry[6];
          if ( v21 )
          {
            v22 = v21 - 16;
            if ( *(_QWORD *)v22 )
              ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v22, (PVOID)v22);
            else
              ExFreePoolWithTag((PVOID)v22, *(_DWORD *)(v22 + 8));
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
    v18 = 24;
LABEL_18:
    WPP_SF_(v17->AttachedDevice, v18, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    goto LABEL_19;
  }
  pvAssocEntry = (__int64 *)i->pvAssocEntry;
  if ( !pvAssocEntry || *((_DWORD *)pvAssocEntry + 6) != 1 )
  {
    v100 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v101 = 25;
    goto LABEL_212;
  }
  --*(_DWORD *)(a1 + 328);
  v23 = *(_DWORD *)(a3 + 12);
  *((_QWORD *)&v127 + 1) = v15;
  LODWORD(v128) = v23;
  LODWORD(v127) = 37;
  if ( *(_QWORD *)(v14 + 5888) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    v24 = *(_QWORD *)(v14 + 5888);
  }
  else
  {
    if ( !*(_QWORD *)(v14 + 5872) )
      goto LABEL_38;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    v24 = *(_QWORD *)(v14 + 5872);
  }
  NwfUpcallMsg((PIO_CSQ)(*(_QWORD *)(v24 + 24) + 40LL), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v127);
LABEL_38:
  if ( (byte_1400B2803 & 2) != 0 )
    McTemplateK0pjb6q_EtwWriteTransfer(
      a3 + 4,
      (unsigned int)AssocComplete,
      *(_QWORD *)(a1 + 2616) + 4920,
      *(_QWORD *)(a1 + 2616),
      *(_QWORD *)(a1 + 2616) + 4920LL,
      a3 + 4,
      *(_DWORD *)(a3 + 12));
  ExtSTASnapshotDiagStats((struct EXTSTA_VELAN *)a1);
  v108 = 0;
  if ( v109 >= 2 )
    v108 = *(_DWORD *)(a3 + 92);
  v130 = 0;
  v131 = 0;
  MacAddrToLogString(a3 + 4, v25, &v130);
  if ( (unsigned int)dword_1400B1050 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1400B1050, 0x200000000000LL) )
  {
    v28 = *(_DWORD *)(a1 + 8);
    v118 = *(_DWORD *)(a1 + 344);
    v120 = v28 & 1;
    v119 = (v28 >> 1) & 1;
    v121 = *(_DWORD *)(a1 + 328);
    v122 = *(_DWORD *)(a1 + 1612);
    v123 = *(_DWORD *)(a3 + 40);
    v124 = *(_DWORD *)(a3 + 32);
    LODWORD(v113) = *(_DWORD *)(a3 + 24);
    v105 = *(_BYTE *)(a3 + 17);
    v106[0] = *(_BYTE *)(a3 + 16);
    LODWORD(v114) = v108;
    LODWORD(v115) = *(_DWORD *)(a3 + 60);
    LODWORD(v116) = *(_DWORD *)(a3 + 56);
    LODWORD(v117) = *(_DWORD *)(a3 + 52);
    v107 = *(_DWORD *)(a3 + 12);
    *(_QWORD *)&v104 = &v130;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v120,
      (unsigned int)&byte_1400A72A7,
      v26,
      v27,
      (__int64)&v104,
      (__int64)&v107,
      (__int64)&v117,
      (__int64)&v116,
      (__int64)&v115,
      (__int64)&v114,
      (__int64)v106,
      (__int64)&v105,
      (__int64)&v113,
      (__int64)&v124,
      (__int64)&v123,
      (__int64)&v122,
      (__int64)&v121,
      (__int64)&v120,
      (__int64)&v119,
      (__int64)&v118);
  }
  *(_DWORD *)(a1 + 404) = *(_DWORD *)(a3 + 12);
  *(_DWORD *)(a1 + 412) = v108;
  v29 = *(_DWORD *)(a3 + 12);
  v108 = v29;
  if ( ((v29 - 0x10000) & 0xFFFCFFFF) == 0 && v29 != 0x40000 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    *(_DWORD *)(a3 + 12) = 0;
    v108 = 0;
  }
  memset(v132, 0, sizeof(v132));
  if ( v108 )
  {
    if ( (unsigned int)dword_1400B1088 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400B1088, 4) )
    {
      v107 = *(unsigned __int8 *)(a3 + 16);
      if ( v110 )
      {
        if ( v110 == 1 )
        {
          v32 = "Ft";
        }
        else if ( v110 == 2 )
        {
          v32 = "PbssNotInDs";
        }
        else
        {
          v32 = "ToStringFailed";
        }
      }
      else
      {
        v32 = "General";
      }
      v33 = (stringify *)*(unsigned int *)(a3 + 60);
      *(_QWORD *)&v104 = v32;
      v34 = stringify::ToLogString(v33, v13);
      v35 = (stringify *)*(unsigned int *)(a3 + 56);
      v117 = v34;
      v37 = stringify::ToLogString(v35, v36);
      v38 = (stringify *)*(unsigned int *)(a3 + 52);
      v116 = v37;
      v40 = stringify::ToLogString(v38, v39);
      v41 = *(unsigned int *)(a3 + 12);
      v115 = v40;
      v43 = Dot11AssocStatusToLogString(v41, v42, v132);
      v47 = byte_1400A7213;
LABEL_71:
      v114 = v43;
      v113 = &v130;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v44,
        (_DWORD)v47,
        v45,
        v46,
        (__int64)&v113,
        (__int64)&v114,
        (__int64)&v115,
        (__int64)&v116,
        (__int64)&v117,
        (__int64)&v104,
        (__int64)&v107);
    }
  }
  else if ( (unsigned int)dword_1400B1088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400B1088, 4) )
  {
    v107 = *(unsigned __int8 *)(a3 + 16);
    if ( v110 )
    {
      if ( v110 == 1 )
      {
        v48 = "Ft";
      }
      else if ( v110 == 2 )
      {
        v48 = "PbssNotInDs";
      }
      else
      {
        v48 = "ToStringFailed";
      }
    }
    else
    {
      v48 = "General";
    }
    v49 = (stringify *)*(unsigned int *)(a3 + 60);
    *(_QWORD *)&v104 = v48;
    v50 = stringify::ToLogString(v49, v13);
    v51 = (stringify *)*(unsigned int *)(a3 + 56);
    v117 = v50;
    v53 = stringify::ToLogString(v51, v52);
    v54 = (stringify *)*(unsigned int *)(a3 + 52);
    v116 = v53;
    v56 = stringify::ToLogString(v54, v55);
    v57 = *(unsigned int *)(a3 + 12);
    v115 = v56;
    v43 = Dot11AssocStatusToLogString(v57, v58, v132);
    v47 = &byte_1400A717F;
    goto LABEL_71;
  }
  v59 = *(struct _WFD_ROLE **)(a1 + 2624);
  if ( v59 )
  {
    *(_BYTE *)(a1 + 408) = 0;
    if ( WFDRoleParseWFDStatusFromAssocCompletion(v59, (struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)a3, v102) >= 0 )
      *(_BYTE *)(a1 + 408) = v102[0];
  }
  v60 = *(_DWORD *)(a3 + 24);
  if ( v60 )
  {
    if ( *(_BYTE *)(a3 + 16) )
    {
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_82;
      v62 = 29;
    }
    else
    {
      v61 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_82;
      v62 = 30;
    }
    AttachedDevice = v61->AttachedDevice;
    v104 = 0;
    LOWORD(v104) = v60;
    *((_QWORD *)&v104 + 1) = a3 + *(unsigned int *)(a3 + 20);
    WPP_SF__HEX_(AttachedDevice, v62, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids, &v104);
  }
LABEL_82:
  v64 = *(_DWORD *)(a3 + 32);
  if ( v64 )
  {
    if ( *(_BYTE *)(a3 + 17) )
    {
      v65 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v66 = 31;
LABEL_88:
        v67 = v65->AttachedDevice;
        v104 = 0;
        LOWORD(v104) = v64;
        *((_QWORD *)&v104 + 1) = a3 + *(unsigned int *)(a3 + 28);
        WPP_SF__HEX_(v67, v66, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids, &v104);
      }
    }
    else
    {
      v65 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        v66 = 32;
        goto LABEL_88;
      }
    }
  }
  v68 = *(_DWORD *)(a3 + 40);
  if ( v68 && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    v69 = WPP_GLOBAL_Control->AttachedDevice;
    v104 = 0;
    LOWORD(v104) = v68;
    *((_QWORD *)&v104 + 1) = a3 + *(unsigned int *)(a3 + 36);
    WPP_SF__HEX_(v69, 33, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids, &v104);
  }
  if ( *(_DWORD *)(a3 + 12) )
  {
    if ( v109 < 2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d_MAC_L(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v30,
          *(_DWORD *)(*(_QWORD *)(v14 + 16) + 1708LL),
          a3 + 4);
    }
    else
    {
      v13 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d_MAC_Ld(
          WPP_GLOBAL_Control->AttachedDevice,
          (_DWORD)WPP_GLOBAL_Control,
          v30,
          *(_DWORD *)(*(_QWORD *)(v14 + 16) + 1708LL),
          a3 + 4);
    }
    if ( *(_DWORD *)(v14 + 5916) == 10 )
      OWEOnAssociationFailure((struct _VELAN *)v14, i, v30);
    goto LABEL_19;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d_MAC_d(WPP_GLOBAL_Control->AttachedDevice, v13, v30, *(_DWORD *)(*(_QWORD *)(v14 + 16) + 1708LL), a3 + 4);
  if ( *(_DWORD *)(a1 + 1612) != 1 )
  {
    v80 = pvAssocEntry[6];
    if ( v80 )
    {
      v81 = v80 - 16;
      if ( *(_QWORD *)v81 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v81, (PVOID)v81);
      else
        ExFreePoolWithTag((PVOID)v81, *(_DWORD *)(v81 + 8));
      pvAssocEntry[6] = 0;
    }
    if ( !*(_QWORD *)(v14 + 5888) )
      goto LABEL_158;
    v13 = (int)Size;
    pvAssocEntry[6] = 0;
    v82 = v13 + 16;
    if ( (unsigned int)v13 >= 0xFFFFFFF0 )
    {
LABEL_156:
      v85 = (void *)pvAssocEntry[6];
      if ( v85 )
      {
        memmove(v85, (const void *)a3, (unsigned int)v13);
        *((_DWORD *)pvAssocEntry + 11) = Size;
      }
LABEL_158:
      *(_DWORD *)(a1 + 1604) = *(_DWORD *)(a1 + 392);
      *(_WORD *)(a1 + 1608) = *(_WORD *)(a1 + 396);
      goto LABEL_159;
    }
    if ( v82 > 0x40 )
    {
      if ( v82 > 0x100 )
      {
        if ( v82 > 0x400 )
        {
          if ( v82 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (_DWORD *)ExAllocatePool2(64, v82, 895579251);
LABEL_154:
            v13 = (int)Size;
            if ( Pool2 )
            {
              *(_QWORD *)Pool2 = p_WaitListHead;
              Pool2[2] = 895579251;
              pvAssocEntry[6] = (__int64)(Pool2 + 4);
            }
            goto LABEL_156;
          }
          p_WaitListHead = &stru_1400B31C0;
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
    goto LABEL_154;
  }
  if ( (*(_DWORD *)(a1 + 8) & 3) == 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_19;
    v18 = 37;
    goto LABEL_18;
  }
  if ( !ExtSTACancelConnRoamingTimer((struct EXTSTA_VELAN *)a1) )
    goto LABEL_19;
  v70 = *(_DWORD *)(a3 + 84) >> 2;
  v112 = 1;
  v107 = v70;
  if ( v70 > 0xFFFF )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_19;
    v18 = 38;
    goto LABEL_18;
  }
  if ( v70 > *(_DWORD *)(a1 + 1688) )
  {
    v71 = 4 * v70 + 16;
    if ( v71 < 0x10 )
    {
LABEL_112:
      v8 = -1073741670;
      goto LABEL_20;
    }
    if ( v71 > 0x40 )
    {
      if ( v71 > 0x100 )
      {
        if ( v71 > 0x400 )
        {
          if ( v71 > 0x800 )
          {
            p_DeviceQueue = 0;
            v73 = (_DWORD *)ExAllocatePool2(64, v71, 912356467);
            goto LABEL_123;
          }
          p_DeviceQueue = &stru_1400B31C0;
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
    v73 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
LABEL_123:
    if ( !v73 )
      goto LABEL_112;
    *(_QWORD *)v73 = p_DeviceQueue;
    v74 = (char *)(v73 + 4);
    v73[2] = 912356467;
    v75 = *(_QWORD *)(a1 + 1696);
    v111 = 0;
    if ( v75 )
    {
      v76 = v75 - 16;
      if ( *(_QWORD *)v76 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v76, (PVOID)v76);
      else
        ExFreePoolWithTag((PVOID)v76, *(_DWORD *)(v76 + 8));
    }
    v70 = v107;
    *(_QWORD *)(a1 + 1696) = v74;
    *(_DWORD *)(a1 + 1688) = v70;
  }
  v77 = *(void **)(a1 + 1696);
  *(_DWORD *)(a1 + 1692) = v70;
  memmove(v77, (const void *)(a3 + *(unsigned int *)(a3 + 80)), 4LL * v70);
  if ( *(_DWORD *)(a1 + 332) )
    ExtSTADeleteAssociation(a1, a1 + 1604, qword_1400A3E78);
  *(_DWORD *)(a1 + 1604) = *(_DWORD *)(a3 + 4);
  *(_WORD *)(a1 + 1608) = *(_WORD *)(a3 + 8);
  *(_DWORD *)(a1 + 8) |= 4u;
  v78 = *(_DWORD *)(a1 + 344);
  *(_DWORD *)(a1 + 352) = *(_DWORD *)(a3 + 76);
  v79 = v78 - 1;
  if ( v79 )
  {
    if ( v79 == 1 && !*(_DWORD *)(a3 + 76) )
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
LABEL_159:
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
    ExtSTASetPacketFilterForAssocChange((struct EXTSTA_VELAN *)a1, 1, v125);
  v86 = *(_DWORD *)(a3 + 60);
  *(_DWORD *)(a1 + 1552) |= 1u;
  v87 = v109 < 2;
  *(_DWORD *)(a1 + 1656) = v86;
  *((_DWORD *)pvAssocEntry + 7) = *(_DWORD *)(a3 + 52);
  *((_DWORD *)pvAssocEntry + 8) = *(_DWORD *)(a3 + 56);
  *((_DWORD *)pvAssocEntry + 6) = 3;
  if ( v87 || (v88 = *(_DWORD *)(a3 + 88)) == 0 )
  {
    *(_DWORD *)(a1 + 1660) = 0;
  }
  else
  {
    *(_DWORD *)(a1 + 1660) = v88;
    if ( *(_DWORD *)(v14 + 5624) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
      v8 = v111;
      goto LABEL_20;
    }
  }
  ++i->uObjCnt;
  _InterlockedIncrement((volatile signed __int32 *)&i->uRefCnt);
  v89 = *((_DWORD *)i + 10) & 0xFFFFFFED | 2;
  *((_DWORD *)i + 10) = v89;
  if ( *(_QWORD *)(v14 + 5888) )
  {
    v90 = v89 | 4;
    *((_DWORD *)i + 10) = v90;
    if ( *(_QWORD *)(v14 + 5888) == *(_QWORD *)(v14 + 5880) )
    {
      *((_DWORD *)i + 10) = v90 ^ ((unsigned __int8)v90 ^ (unsigned __int8)(8 * *(_BYTE *)(a3 + 73))) & 8;
    }
    else
    {
      *(_BYTE *)(a3 + 73) = 0;
      *((_DWORD *)i + 10) &= ~8u;
      v91 = *(_QWORD *)(*(_QWORD *)(v14 + 5888) + 24LL);
      if ( *(_DWORD *)(v91 + 184) && !*(_DWORD *)(v91 + 168) )
        *((_DWORD *)i + 10) &= ~4u;
    }
  }
  else
  {
    *((_DWORD *)i + 10) = v89 & 0xFFFFFFF3;
  }
  v92 = *(_DWORD *)(v14 + 136);
  *(_DWORD *)(v14 + 136) = v92 + 1;
  i->uSessionId = v92;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF__MAC_ll(
      WPP_GLOBAL_Control->AttachedDevice,
      40,
      WPP_GLOBAL_Control,
      a3 + 4,
      (*((_DWORD *)i + 10) >> 2) & 1,
      (*((_DWORD *)i + 10) >> 3) & 1);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids, v110, 2);
  }
  v93 = v110;
  *(_DWORD *)(a1 + 2748) = 0;
  if ( v93 != 1 )
  {
    if ( *(_DWORD *)(a1 + 1612) == 1 )
    {
      if ( v93 == 2 )
        *(_DWORD *)(a1 + 2748) = 1;
      Dot11RsnaOnAssociate(v14, a1 + 1616, i, v93, a3, Size, v126);
    }
    if ( *(_DWORD *)(v14 + 5624) )
      SafeModeOnAssociate((struct _VELAN *)v14, i, (struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)a3, v31);
    DWORD2(v127) = *(_DWORD *)(a3 + 4);
    WORD6(v127) = *(_WORD *)(a3 + 8);
    LODWORD(v127) = 0;
    LODWORD(v128) = i->uSessionId;
    DWORD1(v128) = (*((_DWORD *)i + 10) >> 2) & 1;
    v96 = (*((_DWORD *)i + 10) >> 3) & 1;
    v129 = a3;
    *((_QWORD *)&v128 + 1) = __PAIR64__(Size, v96);
    if ( *(_QWORD *)(v14 + 5888) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
      v97 = *(_QWORD *)(v14 + 5888);
    }
    else
    {
      if ( !*(_QWORD *)(v14 + 5872) )
        goto LABEL_197;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
      v97 = *(_QWORD *)(v14 + 5872);
    }
    NwfUpcallMsg((PIO_CSQ)(*(_QWORD *)(v97 + 24) + 40LL), (const struct DOT11_AUTH_UPCALL_REQUEST *)&v127);
LABEL_197:
    if ( (*((_DWORD *)i + 10) & 0xC) != 4 )
    {
      ++*(_DWORD *)(a1 + 336);
      if ( *(_DWORD *)(a1 + 1612) == 1 )
      {
        v98 = *(_DWORD *)(a1 + 344);
        *(_DWORD *)(a1 + 348) = v98;
        if ( v98 != 1 )
          ExtSTAIndicateNetworkChange((struct EXTSTA_VELAN *)a1, (v98 != 2) + 1);
        *(_DWORD *)(a1 + 344) = 1;
      }
      else if ( *(_DWORD *)(a1 + 336) == 1 )
      {
        ExtSTAIndicateMediaStatus((struct EXTSTA_VELAN *)a1, 1);
      }
    }
    goto LABEL_204;
  }
  IsEnabledDeviceUsageNoInline = Feature_Bugfix_53850044__private_IsEnabledDeviceUsageNoInline();
  v95 = (struct _DOT11_SSID *)(a1 + 1616);
  if ( IsEnabledDeviceUsageNoInline )
    Dot11RsnaOnFTAssociationCompletion(
      (struct _VELAN *)v14,
      v95,
      i,
      Size,
      (struct DOT11_ASSOCIATION_COMPLETION_EX_PARAMETERS *)a3);
  else
    Dot11RsnaOnFTAssociation((struct _VELAN *)v14, v95, i, (struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)a3, Size);
LABEL_204:
  v8 = 0;
LABEL_205:
  if ( v112 )
  {
    v99 = *(struct _IRP **)(a1 + 16);
    *(_QWORD *)(a1 + 16) = 0;
    if ( v99 )
    {
      ExtSTACompleteConnection((struct EXTSTA_VELAN *)a1, v99, v8);
      if ( v8 < 0 )
        ExtSTATerminateConnection((struct EXTSTA_VELAN *)a1);
    }
  }
}

```

## disassembly

```asm
0x14005e1fc  push    rbp
0x14005e1fe  push    rbx
0x14005e1ff  push    rsi
0x14005e200  push    rdi
0x14005e201  push    r12
0x14005e203  push    r13
0x14005e205  push    r14
0x14005e207  push    r15
0x14005e209  lea     rbp, [rsp-0E8h]
0x14005e211  sub     rsp, 208h
0x14005e218  mov     rax, cs:__security_cookie
0x14005e21f  xor     rax, rsp
0x14005e222  mov     [rbp+120h+var_50], rax
0x14005e229  mov     rax, [rbp+120h+arg_20]
0x14005e230  xor     esi, esi
0x14005e232  mov     [rbp+120h+var_118], rax
0x14005e236  xor     r13d, r13d
0x14005e239  xor     eax, eax
0x14005e23b  mov     dword ptr [rbp+120h+Size], r9d
0x14005e23f  cmp     [rcx+6A8h], al
0x14005e245  xorps   xmm0, xmm0
0x14005e248  mov     [rbp+120h+var_F0], rax
0x14005e24c  mov     r15d, 0C0000001h
0x14005e252  mov     [rbp+120h+var_168], eax
0x14005e255  mov     rdi, r8
0x14005e258  setz    al
0x14005e25b  mov     [rbp+120h+var_170], edx
0x14005e25e  mov     [rbp+120h+var_11C], eax
0x14005e261  mov     rbx, rcx
0x14005e264  mov     [rbp+120h+var_16C], r15d
0x14005e268  mov     [rbp+120h+var_1A0], sil
0x14005e26c  movups  [rbp+120h+var_110], xmm0
0x14005e270  movups  [rbp+120h+var_100], xmm0
0x14005e274  cmp     r9d, 4
0x14005e278  jb      loc_14005F1B8
0x14005e27e  cmp     byte ptr [r8], 80h
0x14005e282  jnz     loc_14005F1B8
0x14005e288  movzx   eax, word ptr [r8+2]
0x14005e28d  cmp     r9d, eax
0x14005e290  jb      loc_14005F1B8
0x14005e296  mov     cl, [r8+1]
0x14005e29a  lea     edx, [rsi+1]
0x14005e29d  cmp     cl, dl
0x14005e29f  jnz     short loc_14005E2AF
0x14005e2a1  cmp     eax, 58h ; 'X'
0x14005e2a4  jb      loc_14005F19E
0x14005e2aa  mov     [rbp+120h+var_174], edx
0x14005e2ad  jmp     short loc_14005E2C8
0x14005e2af  cmp     cl, 2
0x14005e2b2  jnz     loc_14005F19E
0x14005e2b8  cmp     eax, 60h ; '`'
0x14005e2bb  jb      loc_14005F19E
0x14005e2c1  mov     [rbp+120h+var_174], 2
0x14005e2c8  mov     r15, [rbx+0A38h]
0x14005e2cf  lea     r12, [r8+4]
0x14005e2d3  movzx   ecx, byte ptr [r12+5]
0x14005e2d9  movzx   eax, byte ptr [r12+4]
0x14005e2df  xor     ecx, eax
0x14005e2e1  and     ecx, 800000FFh
0x14005e2e7  jge     short loc_14005E2F3
0x14005e2e9  sub     ecx, edx
0x14005e2eb  or      ecx, 0FFFFFF00h
0x14005e2f1  add     ecx, edx
0x14005e2f3  mov     r14d, ecx
0x14005e2f6  add     r14, 0Ah
0x14005e2fa  shl     r14, 4
0x14005e2fe  add     r14, r15
0x14005e301  mov     rsi, [r14]
0x14005e304  jmp     short loc_14005E31F
0x14005e306  lea     rcx, [rsi+10h]; Buf1
0x14005e30a  mov     r8d, 6; Size
0x14005e310  mov     rdx, r12; Buf2
0x14005e313  call    memcmp
0x14005e318  test    eax, eax
0x14005e31a  jz      short loc_14005E326
0x14005e31c  mov     rsi, [rsi]
0x14005e31f  cmp     r14, rsi
0x14005e322  jnz     short loc_14005E306
0x14005e324  xor     esi, esi
0x14005e326  test    rsi, rsi
0x14005e329  jnz     loc_14005E3DC
0x14005e32f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e336  lea     r14, WPP_GLOBAL_Control
0x14005e33d  cmp     rcx, r14
0x14005e340  jz      short loc_14005E355
0x14005e342  lea     edx, [rsi+18h]
0x14005e345  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005e34c  mov     rcx, [rcx+18h]
0x14005e350  call    WPP_SF_
0x14005e355  mov     r15d, 0C0000001h
0x14005e35b  test    rsi, rsi
0x14005e35e  jz      loc_14005F121
0x14005e364  mov     qword ptr [rsi+40h], 0
0x14005e36c  test    r13, r13
0x14005e36f  jz      loc_14005F121
0x14005e375  mov     rax, [r13+0]
0x14005e379  cmp     [rax+8], r13
0x14005e37d  jnz     loc_14005F233
0x14005e383  mov     rcx, [r13+8]
0x14005e387  cmp     [rcx], r13
0x14005e38a  jnz     loc_14005F233
0x14005e390  mov     [rcx], rax
0x14005e393  mov     [rax+8], rcx
0x14005e397  lea     rcx, [rbp+120h+var_118]; struct DOT11_MAC_STATE_ENTRY **
0x14005e39b  mov     rax, [r13+10h]
0x14005e39f  mov     [rbp+120h+var_118], rax
0x14005e3a3  call    ?Dot11DecObjCnt@@YAXPEAPEAUDOT11_MAC_STATE_ENTRY@@K@Z; Dot11DecObjCnt(DOT11_MAC_STATE_ENTRY * *,ulong)
0x14005e3a8  mov     rcx, [r13+30h]
0x14005e3ac  test    rcx, rcx
0x14005e3af  jz      loc_14005F1FC
0x14005e3b5  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14005e3b9  mov     rax, [rcx]
0x14005e3bc  test    rax, rax
0x14005e3bf  jz      loc_14005F1E5
0x14005e3c5  mov     rdx, rcx; Entry
0x14005e3c8  mov     rcx, rax; Lookaside
0x14005e3cb  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005e3d2  nop     dword ptr [rax+rax+00h]
0x14005e3d7  jmp     loc_14005F1F4
0x14005e3dc  mov     r13, [rsi+40h]
0x14005e3e0  test    r13, r13
0x14005e3e3  jz      loc_14005F174
0x14005e3e9  cmp     dword ptr [r13+18h], 1
0x14005e3ee  jnz     loc_14005F174
0x14005e3f4  dec     dword ptr [rbx+148h]
0x14005e3fa  lea     r14, WPP_GLOBAL_Control
0x14005e401  mov     eax, [rdi+0Ch]
0x14005e404  mov     qword ptr [rbp+120h+var_110+8], r12
0x14005e408  lea     r12, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005e40f  mov     dword ptr [rbp+120h+var_100], eax
0x14005e412  mov     dword ptr [rbp+120h+var_110], 25h ; '%'
0x14005e419  cmp     qword ptr [r15+1700h], 0
0x14005e421  jz      short loc_14005E449
0x14005e423  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e42a  cmp     rcx, r14
0x14005e42d  jz      short loc_14005E440
0x14005e42f  mov     rcx, [rcx+18h]
0x14005e433  mov     edx, 1Ah
0x14005e438  mov     r8, r12
0x14005e43b  call    WPP_SF_
0x14005e440  mov     rax, [r15+1700h]
0x14005e447  jmp     short loc_14005E477
0x14005e449  cmp     qword ptr [r15+16F0h], 0
0x14005e451  jz      short loc_14005E488
0x14005e453  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e45a  cmp     rcx, r14
0x14005e45d  jz      short loc_14005E470
0x14005e45f  mov     rcx, [rcx+18h]
0x14005e463  mov     edx, 1Bh
0x14005e468  mov     r8, r12
0x14005e46b  call    WPP_SF_
0x14005e470  mov     rax, [r15+16F0h]
0x14005e477  mov     rcx, [rax+18h]
0x14005e47b  lea     rdx, [rbp+120h+var_110]; struct DOT11_AUTH_UPCALL_REQUEST *
0x14005e47f  add     rcx, 28h ; '('; Csq
0x14005e483  call    ?NwfUpcallMsg@@YAJPEAUNWF_AUTH_UPCALL@@PEBUDOT11_AUTH_UPCALL_REQUEST@@@Z; NwfUpcallMsg(NWF_AUTH_UPCALL *,DOT11_AUTH_UPCALL_REQUEST const *)
0x14005e488  test    cs:byte_1400B2803, 2
0x14005e48f  jz      short loc_14005E4C0
0x14005e491  mov     r9, [rbx+0A38h]
0x14005e498  lea     rcx, [rdi+4]
0x14005e49c  mov     eax, [rdi+0Ch]
0x14005e49f  lea     rdx, AssocComplete
0x14005e4a6  mov     dword ptr [rsp+240h+var_210], eax
0x14005e4aa  mov     [rsp+240h+var_218], rcx
0x14005e4af  lea     r8, [r9+1338h]
0x14005e4b6  mov     [rsp+240h+var_220], r8
0x14005e4bb  call    McTemplateK0pjb6q_EtwWriteTransfer
0x14005e4c0  mov     rcx, rbx; struct EXTSTA_VELAN *
0x14005e4c3  call    ?ExtSTASnapshotDiagStats@@YAXPEAUEXTSTA_VELAN@@@Z; ExtSTASnapshotDiagStats(EXTSTA_VELAN *)
0x14005e4c8  cmp     [rbp+120h+var_174], 2
0x14005e4cc  mov     [rbp+120h+var_178], 0
0x14005e4d3  jb      short loc_14005E4DB
0x14005e4d5  mov     eax, [rdi+5Ch]
0x14005e4d8  mov     [rbp+120h+var_178], eax
0x14005e4db  xorps   xmm0, xmm0
0x14005e4de  lea     r8, [rbp+120h+var_E8]
0x14005e4e2  xor     eax, eax
0x14005e4e4  lea     rcx, [rdi+4]
0x14005e4e8  movups  [rbp+120h+var_E8], xmm0
0x14005e4ec  mov     [rbp+120h+var_D8], ax
0x14005e4f0  call    MacAddrToLogString
0x14005e4f5  mov     eax, cs:dword_1400B1050
0x14005e4fb  cmp     eax, 5
0x14005e4fe  jbe     loc_14005E63C
0x14005e504  mov     rdx, 200000000000h
0x14005e50e  lea     rcx, dword_1400B1050
0x14005e515  call    _tlgKeywordOn
0x14005e51a  test    al, al
0x14005e51c  jz      loc_14005E63C
0x14005e522  mov     eax, [rbx+158h]
0x14005e528  lea     rdx, byte_1400A72A7
0x14005e52f  mov     ecx, [rbx+8]
0x14005e532  mov     [rbp+120h+var_138], eax
0x14005e535  mov     eax, ecx
0x14005e537  shr     eax, 1
0x14005e539  and     ecx, 1
0x14005e53c  and     eax, 1
0x14005e53f  mov     [rbp+120h+var_130], ecx
0x14005e542  mov     [rbp+120h+var_134], eax
0x14005e545  mov     eax, [rbx+148h]
0x14005e54b  mov     [rbp+120h+var_12C], eax
0x14005e54e  mov     eax, [rbx+64Ch]
0x14005e554  mov     [rbp+120h+var_128], eax
0x14005e557  mov     eax, [rdi+28h]
0x14005e55a  mov     [rbp+120h+var_124], eax
0x14005e55d  mov     eax, [rdi+20h]
0x14005e560  mov     [rbp+120h+var_120], eax
0x14005e563  mov     eax, [rdi+18h]
0x14005e566  mov     dword ptr [rbp+120h+var_160], eax
0x14005e569  mov     al, [rdi+11h]
0x14005e56c  mov     [rbp+120h+var_180], al
0x14005e56f  mov     al, [rdi+10h]
0x14005e572  mov     [rbp+120h+var_17F], al
0x14005e575  mov     eax, [rbp+120h+var_178]
0x14005e578  mov     dword ptr [rbp+120h+var_158], eax
0x14005e57b  mov     eax, [rdi+3Ch]
0x14005e57e  mov     dword ptr [rbp+120h+var_150], eax
0x14005e581  mov     eax, [rdi+38h]
0x14005e584  mov     dword ptr [rbp+120h+var_148], eax
0x14005e587  mov     eax, [rdi+34h]
0x14005e58a  mov     dword ptr [rbp+120h+var_140], eax
0x14005e58d  mov     eax, [rdi+0Ch]
0x14005e590  mov     [rbp+120h+var_17C], eax
0x14005e593  lea     rax, [rbp+120h+var_E8]
0x14005e597  mov     qword ptr [rbp+120h+var_190], rax
0x14005e59b  lea     rax, [rbp+120h+var_138]
0x14005e59f  mov     [rsp+240h+var_1A8], rax
0x14005e5a7  lea     rax, [rbp+120h+var_134]
0x14005e5ab  mov     [rsp+240h+var_1B0], rax
0x14005e5b3  lea     rax, [rbp+120h+var_130]
0x14005e5b7  mov     [rsp+240h+var_1B8], rax
0x14005e5bf  lea     rax, [rbp+120h+var_12C]
0x14005e5c3  mov     [rsp+240h+var_1C0], rax
0x14005e5cb  lea     rax, [rbp+120h+var_128]
0x14005e5cf  mov     [rsp+240h+var_1C8], rax
0x14005e5d4  lea     rax, [rbp+120h+var_124]
0x14005e5d8  mov     [rsp+240h+var_1D0], rax
0x14005e5dd  lea     rax, [rbp+120h+var_120]
0x14005e5e1  mov     [rsp+240h+var_1D8], rax
0x14005e5e6  lea     rax, [rbp+120h+var_160]
0x14005e5ea  mov     [rsp+240h+var_1E0], rax
0x14005e5ef  lea     rax, [rbp+120h+var_180]
0x14005e5f3  mov     [rsp+240h+var_1E8], rax
0x14005e5f8  lea     rax, [rbp+120h+var_17F]
0x14005e5fc  mov     [rsp+240h+var_1F0], rax
0x14005e601  lea     rax, [rbp+120h+var_158]
0x14005e605  mov     [rsp+240h+var_1F8], rax
0x14005e60a  lea     rax, [rbp+120h+var_150]
0x14005e60e  mov     [rsp+240h+var_200], rax
0x14005e613  lea     rax, [rbp+120h+var_148]
0x14005e617  mov     [rsp+240h+var_208], rax
0x14005e61c  lea     rax, [rbp+120h+var_140]
0x14005e620  mov     [rsp+240h+var_210], rax
0x14005e625  lea     rax, [rbp+120h+var_17C]
0x14005e629  mov     [rsp+240h+var_218], rax
0x14005e62e  lea     rax, [rbp+120h+var_190]
0x14005e632  mov     [rsp+240h+var_220], rax
0x14005e637  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@U2@U?$_tlgWrapperByVal@$00@@U3@U2@U2@U2@U2@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4444AEBU?$_tlgWrapperByVal@$00@@544444444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x14005e63c  mov     eax, [rdi+0Ch]
0x14005e63f  mov     [rbx+194h], eax
0x14005e645  mov     eax, [rbp+120h+var_178]
0x14005e648  mov     [rbx+19Ch], eax
0x14005e64e  mov     ecx, [rdi+0Ch]
0x14005e651  mov     [rbp+120h+var_178], ecx
0x14005e654  lea     eax, [rcx-10000h]
0x14005e65a  test    eax, 0FFFCFFFFh
0x14005e65f  jnz     short loc_14005E694
0x14005e661  cmp     ecx, 40000h
0x14005e667  jz      short loc_14005E694
0x14005e669  mov     rcx, cs:WPP_GLOBAL_Control
0x14005e670  cmp     rcx, r14
0x14005e673  jz      short loc_14005E686
0x14005e675  mov     rcx, [rcx+18h]
0x14005e679  mov     edx, 1Ch
0x14005e67e  mov     r8, r12
0x14005e681  call    WPP_SF_
0x14005e686  mov     dword ptr [rdi+0Ch], 0
0x14005e68d  mov     [rbp+120h+var_178], 0
0x14005e694  xor     edx, edx; Val
0x14005e696  lea     rcx, [rbp+120h+var_D0]; void *
0x14005e69a  mov     r8d, 80h; Size
0x14005e6a0  call    memset
0x14005e6a5  cmp     [rbp+120h+var_178], 0
0x14005e6a9  mov     eax, cs:dword_1400B1088
0x14005e6af  jz      loc_14005E751
0x14005e6b5  cmp     eax, 2
0x14005e6b8  jbe     loc_14005E838
0x14005e6be  mov     edx, 4
0x14005e6c3  lea     rcx, dword_1400B1088
0x14005e6ca  call    _tlgKeywordOn
0x14005e6cf  test    al, al
0x14005e6d1  jz      loc_14005E838
0x14005e6d7  movzx   eax, byte ptr [rdi+10h]
0x14005e6db  mov     ecx, [rbp+120h+var_170]
0x14005e6de  mov     [rbp+120h+var_17C], eax
0x14005e6e1  test    ecx, ecx
0x14005e6e3  jz      short loc_14005E70A
0x14005e6e5  sub     ecx, 1
0x14005e6e8  jz      short loc_14005E701
0x14005e6ea  cmp     ecx, 1
  ... truncated ...
```
