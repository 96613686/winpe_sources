# ExtSTAAssocStart(EXTSTA_VELAN *,DOT11_ASSOCIATION_START_PARAMETERS *,ulong)

- ea: `0x14005f348`
- end: `0x14005f8eb`
- name: `?ExtSTAAssocStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_ASSOCIATION_START_PARAMETERS@@K@Z`
- size: `1443`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, struct DOT11_ASSOCIATION_START_PARAMETERS *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140068960`

## callees

- `0x140001b18`
- `0x14000aaf8`
- `0x14000d21c`
- `0x14000d2b0`
- `0x140020e04`
- `0x140020f20`
- `0x140036ca0`
- `0x140054aa8`
- `0x14005f348`
- `0x140060814`
- `0x140063fa0`
- `0x1400692fc`
- `0x14009bbb0`
- `0x14009c4e0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005f60d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005f60d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005f66e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005f81c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005f66e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005f81c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f738`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f82d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f738`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005f82d`

## pseudocode

```c
void __fastcall ExtSTAAssocStart(struct EXTSTA_VELAN *a1, struct DOT11_ASSOCIATION_START_PARAMETERS *a2, int a3)
{
  UCHAR *MacAddr; // r12
  _VELAN *pGenVElan; // r13
  char *pvAssocEntry; // r14
  int v8; // ecx
  unsigned int v9; // ecx
  struct DOT11_MAC_STATE_ENTRY **v10; // r15
  struct DOT11_MAC_STATE_ENTRY *i; // rsi
  PDEVICE_OBJECT v12; // rcx
  __int64 v13; // rdx
  int v14; // eax
  unsigned __int64 v15; // rdx
  int AssocMgr; // eax
  __int64 v17; // rdx
  __int64 v18; // rax
  int v19; // r8d
  int v20; // r9d
  unsigned int uSSIDLength; // ecx
  _DWORD *v22; // rax
  PNPAGED_LOOKASIDE_LIST *v23; // r15
  unsigned int uMaxNumPendingAssocAuth; // eax
  __int64 uNumPendingAssoc; // r9
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  _LIST_ENTRY *Blink; // rdx
  __int64 v29; // rcx
  __int64 v30; // rcx
  unsigned __int64 v31; // [rsp+40h] [rbp-29h] BYREF
  struct DOT11_MAC_STATE_ENTRY *v32; // [rsp+48h] [rbp-21h] BYREF
  _GUID *p_gDeviceId; // [rsp+50h] [rbp-19h] BYREF
  unsigned __int8 *ucSSID; // [rsp+58h] [rbp-11h] BYREF
  __int16 v35; // [rsp+60h] [rbp-9h]
  __int128 v36; // [rsp+68h] [rbp-1h] BYREF
  __int16 v37; // [rsp+78h] [rbp+Fh]

  if ( a3 != 56
    || a2->Header.Type != 0x80
    || a2->Header.Revision != 1
    || a2->Header.Size != 56
    || (MacAddr = a2->MacAddr, (a2->MacAddr[0] & 1) != 0)
    || a2->SSID.uSSIDLength > 0x20 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v13 = 13;
    goto LABEL_76;
  }
  pGenVElan = a1->pGenVElan;
  pvAssocEntry = 0;
  v8 = a2->MacAddr[5];
  v31 = MEMORY[0xFFFFF78000000014];
  v9 = (a2->MacAddr[4] ^ v8) % 256;
  v10 = (struct DOT11_MAC_STATE_ENTRY **)&pGenVElan->MacStateTable.Hash.Buckets[v9];
  for ( i = *v10;
        v10 != (struct DOT11_MAC_STATE_ENTRY **)i;
        i = (struct DOT11_MAC_STATE_ENTRY *)i->MacHashEntry.Linkage.Flink )
  {
    if ( !memcmp(i->MacHashEntry.MacKey, MacAddr, 6u) )
      goto LABEL_12;
  }
  i = 0;
LABEL_12:
  v32 = i;
  if ( i && (pvAssocEntry = (char *)i->pvAssocEntry) != 0 )
  {
    if ( *((_DWORD *)pvAssocEntry + 6) == 1 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      v13 = 14;
LABEL_76:
      WPP_SF_(v12->AttachedDevice, v13, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
      return;
    }
    v14 = *((_DWORD *)i + 10);
    v15 = v31;
    if ( (v14 & 0x10) != 0 )
    {
      if ( v31 < i->ullPortAuthFailedTimeoutTime )
        return;
      *((_DWORD *)i + 10) = v14 & 0xFFFFFFEF;
      --a1->AssocMgr.uNumAuthFailedPort;
    }
  }
  else
  {
    v15 = v31;
  }
  if ( a1->RoD.CurrentBSSType != dot11_BSS_type_infrastructure )
  {
    if ( a1->AssocMgr.uNumAuthFailedPort < a1->AssocMgr.uAuthFailedPortThreshold
      || (ExtSTARecycleAuthFailedPort(a1, v15),
          uMaxNumPendingAssocAuth = a1->AssocMgr.uAuthFailedPortThreshold,
          uNumPendingAssoc = a1->AssocMgr.uNumAuthFailedPort,
          (unsigned int)uNumPendingAssoc < uMaxNumPendingAssocAuth) )
    {
      uMaxNumPendingAssocAuth = a1->AssocMgr.uMaxNumPendingAssocAuth;
      uNumPendingAssoc = a1->AssocMgr.uNumPendingAssoc;
      if ( (unsigned int)uNumPendingAssoc < uMaxNumPendingAssocAuth )
        goto LABEL_29;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      v27 = 18;
    }
    else
    {
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        return;
      v27 = 17;
    }
    WPP_SF_Dd(
      v26->AttachedDevice,
      v27,
      WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids,
      uNumPendingAssoc,
      uMaxNumPendingAssocAuth);
    return;
  }
  AssocMgr = (int)a1->AssocMgr;
  if ( (AssocMgr & 3) == 0 )
    return;
  if ( a1->AssocMgr.uNumPendingAssoc || (AssocMgr & 4) != 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v13 = 15;
    goto LABEL_76;
  }
  if ( !a2->SSID.uSSIDLength )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      return;
    v13 = 16;
    goto LABEL_76;
  }
  *(_OWORD *)&a1->AssocMgr.InterimSSID.uSSIDLength = *(_OWORD *)&a2->SSID.uSSIDLength;
  *(_OWORD *)&a1->AssocMgr.InterimSSID.ucSSID[12] = *(_OWORD *)&a2->SSID.ucSSID[12];
  *(_DWORD *)&a1->AssocMgr.InterimSSID.ucSSID[28] = *(_DWORD *)&a2->SSID.ucSSID[28];
LABEL_29:
  if ( (byte_1400B2803 & 2) != 0 )
    McTemplateK0pjb6_EtwWriteTransfer(
      v9,
      (unsigned int)AssocStart,
      &a1->pGenVElan->gDeviceId,
      a1->pGenVElan,
      (__int64)&a1->pGenVElan->gDeviceId,
      (__int64)MacAddr);
  v37 = 0;
  v36 = 0;
  if ( (unsigned int)dword_1400B1088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400B1088, 4) )
  {
    v18 = MacAddrToLogString(MacAddr, v17, &v36);
    uSSIDLength = a2->SSID.uSSIDLength;
    v31 = v18;
    if ( uSSIDLength > 0xFFFF )
      uSSIDLength = 0xFFFF;
    v35 = uSSIDLength;
    ucSSID = a2->SSID.ucSSID;
    p_gDeviceId = &a1->pGenVElan->gDeviceId;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapSz<char>>(
      uSSIDLength,
      (unsigned int)byte_1400A73F5,
      v19,
      v20,
      (__int64)&p_gDeviceId,
      (__int64)&ucSSID,
      (__int64)&v31);
  }
  if ( pvAssocEntry )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d_MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        21,
        (unsigned int)WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids,
        pGenVElan->pAdapt->IfIndex,
        (__int64)MacAddr);
    v29 = *((_QWORD *)pvAssocEntry + 6);
    if ( v29 )
    {
      v30 = v29 - 16;
      if ( *(_QWORD *)v30 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v30, (PVOID)v30);
      else
        ExFreePoolWithTag((PVOID)v30, *(_DWORD *)(v30 + 8));
      *((_QWORD *)pvAssocEntry + 6) = 0;
    }
    --a1->AssocMgr.uNumAssoc;
    ExtSTADeleteDataPort(a1, i);
LABEL_70:
    if ( pGenVElan->FIPSContext.bSafeMode && pGenVElan->FIPSContext.bSafeMode80211nSupported )
      pGenVElan->FIPSContext.bSafeMode80211nActive = 1;
    *((_DWORD *)pvAssocEntry + 6) = 1;
    a1->RoD.uLinkQuality = -1;
    ExtSTAPowerMgmtOnAssocStart(a1, (struct EXTSTA_ASSOC_ENTRY *)pvAssocEntry);
    ++a1->AssocMgr.uNumPendingAssoc;
    return;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d_MAC_(
      WPP_GLOBAL_Control->AttachedDevice,
      19,
      (unsigned int)WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids,
      pGenVElan->pAdapt->IfIndex,
      (__int64)MacAddr);
  v22 = ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  v23 = (PNPAGED_LOOKASIDE_LIST *)v22;
  if ( v22 )
  {
    *(_QWORD *)v22 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    pvAssocEntry = (char *)(v22 + 4);
    v22[2] = 895579251;
    *((_QWORD *)v22 + 8) = 0;
    if ( !i )
    {
      if ( (unsigned int)Dot11AddMacState(&pGenVElan->MacStateTable, (const unsigned __int8 (*)[6])MacAddr, &v32) )
      {
        if ( *v23 )
          ExFreeToNPagedLookasideList(*v23, v23);
        else
          ExFreePoolWithTag(v23, *((_DWORD *)v23 + 2));
        return;
      }
      i = v32;
    }
    *(_DWORD *)a1->AssocMgr.LastAttemptedBSSID = *(_DWORD *)MacAddr;
    *(_WORD *)&a1->AssocMgr.LastAttemptedBSSID[4] = *((_WORD *)MacAddr + 2);
    if ( i->pvAssocEntry && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids);
    ++i->uObjCnt;
    _InterlockedIncrement((volatile signed __int32 *)&i->uRefCnt);
    *((_QWORD *)pvAssocEntry + 2) = i;
    i->pvAssocEntry = pvAssocEntry;
    Blink = a1->AssocMgr.AssocList.Blink;
    if ( Blink->Flink != &a1->AssocMgr.AssocList )
      __fastfail(3u);
    *(_QWORD *)pvAssocEntry = &a1->AssocMgr.AssocList;
    *((_QWORD *)pvAssocEntry + 1) = Blink;
    Blink->Flink = (_LIST_ENTRY *)pvAssocEntry;
    a1->AssocMgr.AssocList.Blink = (_LIST_ENTRY *)pvAssocEntry;
    goto LABEL_70;
  }
}

```

## disassembly

```asm
0x14005f348  mov     [rsp-8+arg_10], rbx
0x14005f34d  push    rbp
0x14005f34e  push    rsi
0x14005f34f  push    rdi
0x14005f350  push    r12
0x14005f352  push    r13
0x14005f354  push    r14
0x14005f356  push    r15
0x14005f358  lea     rbp, [rsp-27h]
0x14005f35d  sub     rsp, 90h
0x14005f364  mov     rax, cs:__security_cookie
0x14005f36b  xor     rax, rsp
0x14005f36e  mov     [rbp+57h+var_40], rax
0x14005f372  mov     eax, 38h ; '8'
0x14005f377  mov     rbx, rdx
0x14005f37a  mov     rdi, rcx
0x14005f37d  cmp     r8d, eax
0x14005f380  jnz     loc_14005F89B
0x14005f386  cmp     byte ptr [rdx], 80h
0x14005f389  jnz     loc_14005F89B
0x14005f38f  cmp     byte ptr [rdx+1], 1
0x14005f393  jnz     loc_14005F89B
0x14005f399  cmp     ax, [rdx+2]
0x14005f39d  jnz     loc_14005F89B
0x14005f3a3  lea     r12, [rdx+4]
0x14005f3a7  test    byte ptr [r12], 1
0x14005f3ac  jnz     loc_14005F89B
0x14005f3b2  cmp     dword ptr [rdx+0Ch], 20h ; ' '
0x14005f3b6  ja      loc_14005F89B
0x14005f3bc  mov     r13, [rcx+0A38h]
0x14005f3c3  mov     rax, 0FFFFF78000000014h
0x14005f3cd  xor     r14d, r14d
0x14005f3d0  mov     rax, [rax]
0x14005f3d3  movzx   ecx, byte ptr [r12+5]
0x14005f3d9  mov     [rbp+57h+var_80], rax
0x14005f3dd  movzx   eax, byte ptr [r12+4]
0x14005f3e3  xor     ecx, eax
0x14005f3e5  and     ecx, 800000FFh
0x14005f3eb  jge     short loc_14005F3F7
0x14005f3ed  dec     ecx
0x14005f3ef  or      ecx, 0FFFFFF00h
0x14005f3f5  inc     ecx
0x14005f3f7  mov     r15d, ecx
0x14005f3fa  shl     r15, 4
0x14005f3fe  add     r15, 0A0h
0x14005f405  add     r15, r13
0x14005f408  mov     rsi, [r15]
0x14005f40b  jmp     short loc_14005F426
0x14005f40d  lea     rcx, [rsi+10h]; Buf1
0x14005f411  mov     r8d, 6; Size
0x14005f417  mov     rdx, r12; Buf2
0x14005f41a  call    memcmp
0x14005f41f  test    eax, eax
0x14005f421  jz      short loc_14005F42D
0x14005f423  mov     rsi, [rsi]
0x14005f426  cmp     r15, rsi
0x14005f429  jnz     short loc_14005F40D
0x14005f42b  xor     esi, esi
0x14005f42d  or      r15d, 0FFFFFFFFh
0x14005f431  mov     [rbp+57h+var_78], rsi
0x14005f435  test    rsi, rsi
0x14005f438  jz      short loc_14005F48F
0x14005f43a  mov     r14, [rsi+40h]
0x14005f43e  test    r14, r14
0x14005f441  jz      short loc_14005F48F
0x14005f443  cmp     dword ptr [r14+18h], 1
0x14005f448  jnz     short loc_14005F46B
0x14005f44a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f451  lea     rbx, WPP_GLOBAL_Control
0x14005f458  cmp     rcx, rbx
0x14005f45b  jz      loc_14005F8C3
0x14005f461  mov     edx, 0Eh
0x14005f466  jmp     loc_14005F8B3
0x14005f46b  mov     eax, [rsi+28h]
0x14005f46e  mov     rdx, [rbp+57h+var_80]
0x14005f472  test    al, 10h
0x14005f474  jz      short loc_14005F493
0x14005f476  cmp     rdx, [rsi+38h]
0x14005f47a  jb      loc_14005F8C3
0x14005f480  and     eax, 0FFFFFFEFh
0x14005f483  mov     [rsi+28h], eax
0x14005f486  add     [rdi+154h], r15d
0x14005f48d  jmp     short loc_14005F493
0x14005f48f  mov     rdx, [rbp+57h+var_80]
0x14005f493  cmp     dword ptr [rdi+64Ch], 1
0x14005f49a  jnz     loc_14005F6A0
0x14005f4a0  mov     eax, [rdi+8]
0x14005f4a3  test    al, 3
0x14005f4a5  jz      loc_14005F8C3
0x14005f4ab  cmp     dword ptr [rdi+148h], 0
0x14005f4b2  jnz     loc_14005F67F
0x14005f4b8  test    al, 4
0x14005f4ba  jnz     loc_14005F67F
0x14005f4c0  cmp     dword ptr [rbx+0Ch], 0
0x14005f4c4  jnz     short loc_14005F4E7
0x14005f4c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f4cd  lea     rbx, WPP_GLOBAL_Control
0x14005f4d4  cmp     rcx, rbx
0x14005f4d7  jz      loc_14005F8C3
0x14005f4dd  mov     edx, 10h
0x14005f4e2  jmp     loc_14005F8B3
0x14005f4e7  movups  xmm0, xmmword ptr [rbx+0Ch]
0x14005f4eb  movups  xmmword ptr [rdi+164h], xmm0
0x14005f4f2  movups  xmm1, xmmword ptr [rbx+1Ch]
0x14005f4f6  movups  xmmword ptr [rdi+174h], xmm1
0x14005f4fd  mov     eax, [rbx+2Ch]
0x14005f500  mov     [rdi+184h], eax
0x14005f506  test    cs:byte_1400B2803, 2
0x14005f50d  jz      short loc_14005F533
0x14005f50f  mov     r9, [rdi+0A38h]
0x14005f516  lea     rdx, AssocStart
0x14005f51d  mov     [rsp+0C0h+var_98], r12
0x14005f522  lea     r8, [r9+1338h]
0x14005f529  mov     [rsp+0C0h+var_A0], r8
0x14005f52e  call    McTemplateK0pjb6_EtwWriteTransfer
0x14005f533  xor     eax, eax
0x14005f535  xorps   xmm0, xmm0
0x14005f538  mov     [rbp+57h+var_48], ax
0x14005f53c  mov     eax, cs:dword_1400B1088
0x14005f542  movups  [rbp+57h+var_58], xmm0
0x14005f546  cmp     eax, 4
0x14005f549  jbe     short loc_14005F5C3
0x14005f54b  mov     edx, 4
0x14005f550  lea     rcx, dword_1400B1088
0x14005f557  call    _tlgKeywordOn
0x14005f55c  test    al, al
0x14005f55e  jz      short loc_14005F5C3
0x14005f560  lea     r8, [rbp+57h+var_58]
0x14005f564  mov     rcx, r12
0x14005f567  call    MacAddrToLogString
0x14005f56c  mov     ecx, [rbx+0Ch]
0x14005f56f  mov     [rbp+57h+var_80], rax
0x14005f573  mov     eax, 0FFFFh
0x14005f578  cmp     ecx, eax
0x14005f57a  jbe     short loc_14005F57F
0x14005f57c  movzx   ecx, ax
0x14005f57f  lea     rax, [rbx+10h]
0x14005f583  mov     [rbp+57h+var_60], cx
0x14005f587  mov     [rbp+57h+var_68], rax
0x14005f58b  lea     rdx, byte_1400A73F5
0x14005f592  mov     rax, [rdi+0A38h]
0x14005f599  add     rax, 1338h
0x14005f59f  mov     [rbp+57h+var_70], rax
0x14005f5a3  lea     rax, [rbp+57h+var_80]
0x14005f5a7  mov     [rsp+0C0h+var_90], rax
0x14005f5ac  lea     rax, [rbp+57h+var_68]
0x14005f5b0  mov     [rsp+0C0h+var_98], rax
0x14005f5b5  lea     rax, [rbp+57h+var_70]
0x14005f5b9  mov     [rsp+0C0h+var_A0], rax
0x14005f5be  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &)
0x14005f5c3  test    r14, r14
0x14005f5c6  jnz     loc_14005F7C9
0x14005f5cc  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f5d3  lea     rbx, WPP_GLOBAL_Control
0x14005f5da  cmp     rcx, rbx
0x14005f5dd  jz      short loc_14005F603
0x14005f5df  mov     r9, [r13+10h]
0x14005f5e3  lea     edx, [r14+13h]
0x14005f5e7  mov     rcx, [rcx+18h]
0x14005f5eb  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005f5f2  mov     [rsp+0C0h+var_A0], r12
0x14005f5f7  mov     r9d, [r9+6ACh]
0x14005f5fe  call    WPP_SF_d_MAC_
0x14005f603  lea     r14, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14005f60a  mov     rcx, r14; Lookaside
0x14005f60d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005f614  nop     dword ptr [rax+rax+00h]
0x14005f619  mov     r15, rax
0x14005f61c  test    rax, rax
0x14005f61f  jz      loc_14005F8C3
0x14005f625  mov     [rax], r14
0x14005f628  lea     r14, [rax+10h]
0x14005f62c  mov     dword ptr [rax+8], 35617473h
0x14005f633  mov     qword ptr [r14+30h], 0
0x14005f63b  test    rsi, rsi
0x14005f63e  jnz     loc_14005F74D
0x14005f644  lea     r8, [rbp+57h+var_78]; struct DOT11_MAC_STATE_ENTRY **
0x14005f648  mov     rdx, r12; unsigned __int8 (*)[6]
0x14005f64b  lea     rcx, [r13+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x14005f652  call    ?Dot11AddMacState@@YAHPEAUDOT11_MAC_STATE_MODULE@@PEAY05$$CBEPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11AddMacState(DOT11_MAC_STATE_MODULE *,uchar const (*)[6],DOT11_MAC_STATE_ENTRY * *)
0x14005f657  test    eax, eax
0x14005f659  jz      loc_14005F749
0x14005f65f  mov     rcx, [r15]; Lookaside
0x14005f662  test    rcx, rcx
0x14005f665  jz      loc_14005F731
0x14005f66b  mov     rdx, r15; Entry
0x14005f66e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005f675  nop     dword ptr [rax+rax+00h]
0x14005f67a  jmp     loc_14005F8C3
0x14005f67f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f686  lea     rbx, WPP_GLOBAL_Control
0x14005f68d  cmp     rcx, rbx
0x14005f690  jz      loc_14005F8C3
0x14005f696  mov     edx, 0Fh
0x14005f69b  jmp     loc_14005F8B3
0x14005f6a0  mov     eax, [rdi+318h]
0x14005f6a6  cmp     [rdi+154h], eax
0x14005f6ac  jb      short loc_14005F6FD
0x14005f6ae  mov     rcx, rdi
0x14005f6b1  call    ExtSTARecycleAuthFailedPort
0x14005f6b6  mov     eax, [rdi+318h]
0x14005f6bc  mov     r9d, [rdi+154h]
0x14005f6c3  cmp     r9d, eax
0x14005f6c6  jb      short loc_14005F6FD
0x14005f6c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f6cf  lea     rbx, WPP_GLOBAL_Control
0x14005f6d6  cmp     rcx, rbx
0x14005f6d9  jz      loc_14005F8C3
0x14005f6df  mov     edx, 11h
0x14005f6e4  mov     rcx, [rcx+18h]
0x14005f6e8  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005f6ef  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14005f6f3  call    WPP_SF_Dd
0x14005f6f8  jmp     loc_14005F8C3
0x14005f6fd  mov     eax, [rdi+314h]
0x14005f703  mov     r9d, [rdi+148h]
0x14005f70a  cmp     r9d, eax
0x14005f70d  jb      loc_14005F506
0x14005f713  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f71a  lea     rbx, WPP_GLOBAL_Control
0x14005f721  cmp     rcx, rbx
0x14005f724  jz      loc_14005F8C3
0x14005f72a  mov     edx, 12h
0x14005f72f  jmp     short loc_14005F6E4
0x14005f731  mov     edx, [r15+8]; Tag
0x14005f735  mov     rcx, r15; P
0x14005f738  call    cs:__imp_ExFreePoolWithTag
0x14005f73f  nop     dword ptr [rax+rax+00h]
0x14005f744  jmp     loc_14005F8C3
0x14005f749  mov     rsi, [rbp+57h+var_78]
0x14005f74d  mov     eax, [r12]
0x14005f751  mov     [rdi+18Eh], eax
0x14005f757  movzx   eax, word ptr [r12+4]
0x14005f75d  mov     [rdi+192h], ax
0x14005f764  cmp     qword ptr [rsi+40h], 0
0x14005f769  jz      short loc_14005F78C
0x14005f76b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f772  cmp     rcx, rbx
0x14005f775  jz      short loc_14005F78C
0x14005f777  mov     rcx, [rcx+18h]
0x14005f77b  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005f782  mov     edx, 14h
0x14005f787  call    WPP_SF_
0x14005f78c  inc     dword ptr [rsi+20h]
0x14005f78f  lock inc dword ptr [rsi+24h]
0x14005f793  mov     [r14+10h], rsi
0x14005f797  lea     rax, [rdi+1A0h]
0x14005f79e  mov     [rsi+40h], r14
0x14005f7a2  mov     rdx, [rax+8]
0x14005f7a6  cmp     [rdx], rax
0x14005f7a9  jz      short loc_14005F7B2
0x14005f7ab  mov     ecx, 3
0x14005f7b0  int     29h; Win8: RtlFailFast(ecx)
0x14005f7b2  mov     [r14], rax
0x14005f7b5  or      r15d, 0FFFFFFFFh
0x14005f7b9  mov     [r14+8], rdx
0x14005f7bd  mov     [rdx], r14
0x14005f7c0  mov     [rax+8], r14
0x14005f7c4  jmp     loc_14005F85A
0x14005f7c9  mov     rcx, cs:WPP_GLOBAL_Control
0x14005f7d0  lea     rbx, WPP_GLOBAL_Control
0x14005f7d7  cmp     rcx, rbx
0x14005f7da  jz      short loc_14005F801
0x14005f7dc  mov     r9, [r13+10h]
0x14005f7e0  lea     r8, WPP_c6bb31eb4526364bf8c57723d56b61c7_Traceguids
0x14005f7e7  mov     rcx, [rcx+18h]
0x14005f7eb  mov     edx, 15h
0x14005f7f0  mov     [rsp+0C0h+var_A0], r12
0x14005f7f5  mov     r9d, [r9+6ACh]
0x14005f7fc  call    WPP_SF_d_MAC_
0x14005f801  mov     rcx, [r14+30h]
0x14005f805  test    rcx, rcx
0x14005f808  jz      short loc_14005F841
0x14005f80a  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14005f80e  mov     rax, [rcx]
0x14005f811  test    rax, rax
0x14005f814  jz      short loc_14005F82A
0x14005f816  mov     rdx, rcx; Entry
0x14005f819  mov     rcx, rax; Lookaside
0x14005f81c  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005f823  nop     dword ptr [rax+rax+00h]
0x14005f828  jmp     short loc_14005F839
0x14005f82a  mov     edx, [rcx+8]; Tag
0x14005f82d  call    cs:__imp_ExFreePoolWithTag
0x14005f834  nop     dword ptr [rax+rax+00h]
0x14005f839  mov     qword ptr [r14+30h], 0
0x14005f841  add     [rdi+14Ch], r15d
0x14005f848  lea     r8, qword_1400A3E78
0x14005f84f  mov     rdx, rsi; struct DOT11_MAC_STATE_ENTRY *
0x14005f852  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14005f855  call    ExtSTADeleteDataPort
0x14005f85a  cmp     dword ptr [r13+15F8h], 0
0x14005f862  jz      short loc_14005F879
0x14005f864  cmp     dword ptr [r13+1600h], 0
0x14005f86c  jz      short loc_14005F879
0x14005f86e  mov     dword ptr [r13+15FCh], 1
0x14005f879  mov     dword ptr [r14+18h], 1
0x14005f881  mov     rdx, r14; struct EXTSTA_ASSOC_ENTRY *
0x14005f884  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14005f887  mov     [rdi+674h], r15d
  ... truncated ...
```
