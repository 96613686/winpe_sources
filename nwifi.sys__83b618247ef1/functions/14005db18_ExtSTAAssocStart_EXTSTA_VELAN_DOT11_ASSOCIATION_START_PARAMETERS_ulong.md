# ExtSTAAssocStart(EXTSTA_VELAN *,DOT11_ASSOCIATION_START_PARAMETERS *,ulong)

- ea: `0x14005db18`
- end: `0x14005e0bb`
- name: `?ExtSTAAssocStart@@YAXPEAUEXTSTA_VELAN@@PEAUDOT11_ASSOCIATION_START_PARAMETERS@@K@Z`
- size: `1443`
- prototype: `void __fastcall(struct EXTSTA_VELAN *, struct DOT11_ASSOCIATION_START_PARAMETERS *, unsigned int)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x140067130`

## callees

- `0x140001b18`
- `0x14000ab08`
- `0x14000d22c`
- `0x14000d2c0`
- `0x140020e04`
- `0x140020f20`
- `0x140036a80`
- `0x140053288`
- `0x14005db18`
- `0x14005efe4`
- `0x140062770`
- `0x140067acc`
- `0x14009a3d0`
- `0x14009ace0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005dddd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14005dddd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005de3e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005dfec`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005de3e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14005dfec`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005df08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005dffd`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005df08`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005dffd`

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
      WPP_SF_(v12->AttachedDevice, v13, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
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
      WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
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
  if ( (byte_1400AF803 & 2) != 0 )
    McTemplateK0pjb6_EtwWriteTransfer(
      v9,
      (unsigned int)AssocStart,
      &a1->pGenVElan->gDeviceId,
      a1->pGenVElan,
      (__int64)&a1->pGenVElan->gDeviceId,
      (__int64)MacAddr);
  v37 = 0;
  v36 = 0;
  if ( (unsigned int)dword_1400AE088 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1400AE088, 4) )
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
      (unsigned int)byte_1400A52F5,
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
        (unsigned int)WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
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
      (unsigned int)WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids,
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
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids);
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
0x14005db18  mov     [rsp-8+arg_10], rbx
0x14005db1d  push    rbp
0x14005db1e  push    rsi
0x14005db1f  push    rdi
0x14005db20  push    r12
0x14005db22  push    r13
0x14005db24  push    r14
0x14005db26  push    r15
0x14005db28  lea     rbp, [rsp-27h]
0x14005db2d  sub     rsp, 90h
0x14005db34  mov     rax, cs:__security_cookie
0x14005db3b  xor     rax, rsp
0x14005db3e  mov     [rbp+57h+var_40], rax
0x14005db42  mov     eax, 38h ; '8'
0x14005db47  mov     rbx, rdx
0x14005db4a  mov     rdi, rcx
0x14005db4d  cmp     r8d, eax
0x14005db50  jnz     loc_14005E06B
0x14005db56  cmp     byte ptr [rdx], 80h
0x14005db59  jnz     loc_14005E06B
0x14005db5f  cmp     byte ptr [rdx+1], 1
0x14005db63  jnz     loc_14005E06B
0x14005db69  cmp     ax, [rdx+2]
0x14005db6d  jnz     loc_14005E06B
0x14005db73  lea     r12, [rdx+4]
0x14005db77  test    byte ptr [r12], 1
0x14005db7c  jnz     loc_14005E06B
0x14005db82  cmp     dword ptr [rdx+0Ch], 20h ; ' '
0x14005db86  ja      loc_14005E06B
0x14005db8c  mov     r13, [rcx+0A38h]
0x14005db93  mov     rax, 0FFFFF78000000014h
0x14005db9d  xor     r14d, r14d
0x14005dba0  mov     rax, [rax]
0x14005dba3  movzx   ecx, byte ptr [r12+5]
0x14005dba9  mov     [rbp+57h+var_80], rax
0x14005dbad  movzx   eax, byte ptr [r12+4]
0x14005dbb3  xor     ecx, eax
0x14005dbb5  and     ecx, 800000FFh
0x14005dbbb  jge     short loc_14005DBC7
0x14005dbbd  dec     ecx
0x14005dbbf  or      ecx, 0FFFFFF00h
0x14005dbc5  inc     ecx
0x14005dbc7  mov     r15d, ecx
0x14005dbca  shl     r15, 4
0x14005dbce  add     r15, 0A0h
0x14005dbd5  add     r15, r13
0x14005dbd8  mov     rsi, [r15]
0x14005dbdb  jmp     short loc_14005DBF6
0x14005dbdd  lea     rcx, [rsi+10h]; Buf1
0x14005dbe1  mov     r8d, 6; Size
0x14005dbe7  mov     rdx, r12; Buf2
0x14005dbea  call    memcmp
0x14005dbef  test    eax, eax
0x14005dbf1  jz      short loc_14005DBFD
0x14005dbf3  mov     rsi, [rsi]
0x14005dbf6  cmp     r15, rsi
0x14005dbf9  jnz     short loc_14005DBDD
0x14005dbfb  xor     esi, esi
0x14005dbfd  or      r15d, 0FFFFFFFFh
0x14005dc01  mov     [rbp+57h+var_78], rsi
0x14005dc05  test    rsi, rsi
0x14005dc08  jz      short loc_14005DC5F
0x14005dc0a  mov     r14, [rsi+40h]
0x14005dc0e  test    r14, r14
0x14005dc11  jz      short loc_14005DC5F
0x14005dc13  cmp     dword ptr [r14+18h], 1
0x14005dc18  jnz     short loc_14005DC3B
0x14005dc1a  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dc21  lea     rbx, WPP_GLOBAL_Control
0x14005dc28  cmp     rcx, rbx
0x14005dc2b  jz      loc_14005E093
0x14005dc31  mov     edx, 0Eh
0x14005dc36  jmp     loc_14005E083
0x14005dc3b  mov     eax, [rsi+28h]
0x14005dc3e  mov     rdx, [rbp+57h+var_80]
0x14005dc42  test    al, 10h
0x14005dc44  jz      short loc_14005DC63
0x14005dc46  cmp     rdx, [rsi+38h]
0x14005dc4a  jb      loc_14005E093
0x14005dc50  and     eax, 0FFFFFFEFh
0x14005dc53  mov     [rsi+28h], eax
0x14005dc56  add     [rdi+154h], r15d
0x14005dc5d  jmp     short loc_14005DC63
0x14005dc5f  mov     rdx, [rbp+57h+var_80]
0x14005dc63  cmp     dword ptr [rdi+64Ch], 1
0x14005dc6a  jnz     loc_14005DE70
0x14005dc70  mov     eax, [rdi+8]
0x14005dc73  test    al, 3
0x14005dc75  jz      loc_14005E093
0x14005dc7b  cmp     dword ptr [rdi+148h], 0
0x14005dc82  jnz     loc_14005DE4F
0x14005dc88  test    al, 4
0x14005dc8a  jnz     loc_14005DE4F
0x14005dc90  cmp     dword ptr [rbx+0Ch], 0
0x14005dc94  jnz     short loc_14005DCB7
0x14005dc96  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dc9d  lea     rbx, WPP_GLOBAL_Control
0x14005dca4  cmp     rcx, rbx
0x14005dca7  jz      loc_14005E093
0x14005dcad  mov     edx, 10h
0x14005dcb2  jmp     loc_14005E083
0x14005dcb7  movups  xmm0, xmmword ptr [rbx+0Ch]
0x14005dcbb  movups  xmmword ptr [rdi+164h], xmm0
0x14005dcc2  movups  xmm1, xmmword ptr [rbx+1Ch]
0x14005dcc6  movups  xmmword ptr [rdi+174h], xmm1
0x14005dccd  mov     eax, [rbx+2Ch]
0x14005dcd0  mov     [rdi+184h], eax
0x14005dcd6  test    cs:byte_1400AF803, 2
0x14005dcdd  jz      short loc_14005DD03
0x14005dcdf  mov     r9, [rdi+0A38h]
0x14005dce6  lea     rdx, AssocStart
0x14005dced  mov     [rsp+0C0h+var_98], r12
0x14005dcf2  lea     r8, [r9+1338h]
0x14005dcf9  mov     [rsp+0C0h+var_A0], r8
0x14005dcfe  call    McTemplateK0pjb6_EtwWriteTransfer
0x14005dd03  xor     eax, eax
0x14005dd05  xorps   xmm0, xmm0
0x14005dd08  mov     [rbp+57h+var_48], ax
0x14005dd0c  mov     eax, cs:dword_1400AE088
0x14005dd12  movups  [rbp+57h+var_58], xmm0
0x14005dd16  cmp     eax, 4
0x14005dd19  jbe     short loc_14005DD93
0x14005dd1b  mov     edx, 4
0x14005dd20  lea     rcx, dword_1400AE088
0x14005dd27  call    _tlgKeywordOn
0x14005dd2c  test    al, al
0x14005dd2e  jz      short loc_14005DD93
0x14005dd30  lea     r8, [rbp+57h+var_58]
0x14005dd34  mov     rcx, r12
0x14005dd37  call    MacAddrToLogString
0x14005dd3c  mov     ecx, [rbx+0Ch]
0x14005dd3f  mov     [rbp+57h+var_80], rax
0x14005dd43  mov     eax, 0FFFFh
0x14005dd48  cmp     ecx, eax
0x14005dd4a  jbe     short loc_14005DD4F
0x14005dd4c  movzx   ecx, ax
0x14005dd4f  lea     rax, [rbx+10h]
0x14005dd53  mov     [rbp+57h+var_60], cx
0x14005dd57  mov     [rbp+57h+var_68], rax
0x14005dd5b  lea     rdx, byte_1400A52F5
0x14005dd62  mov     rax, [rdi+0A38h]
0x14005dd69  add     rax, 1338h
0x14005dd6f  mov     [rbp+57h+var_70], rax
0x14005dd73  lea     rax, [rbp+57h+var_80]
0x14005dd77  mov     [rsp+0C0h+var_90], rax
0x14005dd7c  lea     rax, [rbp+57h+var_68]
0x14005dd80  mov     [rsp+0C0h+var_98], rax
0x14005dd85  lea     rax, [rbp+57h+var_70]
0x14005dd89  mov     [rsp+0C0h+var_A0], rax
0x14005dd8e  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperArray@$00@@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperArray@$00@@AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapperArray<1>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapperArray<1> const &,_tlgWrapSz<char> const &)
0x14005dd93  test    r14, r14
0x14005dd96  jnz     loc_14005DF99
0x14005dd9c  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dda3  lea     rbx, WPP_GLOBAL_Control
0x14005ddaa  cmp     rcx, rbx
0x14005ddad  jz      short loc_14005DDD3
0x14005ddaf  mov     r9, [r13+10h]
0x14005ddb3  lea     edx, [r14+13h]
0x14005ddb7  mov     rcx, [rcx+18h]
0x14005ddbb  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005ddc2  mov     [rsp+0C0h+var_A0], r12
0x14005ddc7  mov     r9d, [r9+6ACh]
0x14005ddce  call    WPP_SF_d_MAC_
0x14005ddd3  lea     r14, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x14005ddda  mov     rcx, r14; Lookaside
0x14005dddd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x14005dde4  nop     dword ptr [rax+rax+00h]
0x14005dde9  mov     r15, rax
0x14005ddec  test    rax, rax
0x14005ddef  jz      loc_14005E093
0x14005ddf5  mov     [rax], r14
0x14005ddf8  lea     r14, [rax+10h]
0x14005ddfc  mov     dword ptr [rax+8], 35617473h
0x14005de03  mov     qword ptr [r14+30h], 0
0x14005de0b  test    rsi, rsi
0x14005de0e  jnz     loc_14005DF1D
0x14005de14  lea     r8, [rbp+57h+var_78]; struct DOT11_MAC_STATE_ENTRY **
0x14005de18  mov     rdx, r12; unsigned __int8 (*)[6]
0x14005de1b  lea     rcx, [r13+0A0h]; struct DOT11_MAC_STATE_MODULE *
0x14005de22  call    ?Dot11AddMacState@@YAHPEAUDOT11_MAC_STATE_MODULE@@PEAY05$$CBEPEAPEAUDOT11_MAC_STATE_ENTRY@@@Z; Dot11AddMacState(DOT11_MAC_STATE_MODULE *,uchar const (*)[6],DOT11_MAC_STATE_ENTRY * *)
0x14005de27  test    eax, eax
0x14005de29  jz      loc_14005DF19
0x14005de2f  mov     rcx, [r15]; Lookaside
0x14005de32  test    rcx, rcx
0x14005de35  jz      loc_14005DF01
0x14005de3b  mov     rdx, r15; Entry
0x14005de3e  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005de45  nop     dword ptr [rax+rax+00h]
0x14005de4a  jmp     loc_14005E093
0x14005de4f  mov     rcx, cs:WPP_GLOBAL_Control
0x14005de56  lea     rbx, WPP_GLOBAL_Control
0x14005de5d  cmp     rcx, rbx
0x14005de60  jz      loc_14005E093
0x14005de66  mov     edx, 0Fh
0x14005de6b  jmp     loc_14005E083
0x14005de70  mov     eax, [rdi+318h]
0x14005de76  cmp     [rdi+154h], eax
0x14005de7c  jb      short loc_14005DECD
0x14005de7e  mov     rcx, rdi
0x14005de81  call    ExtSTARecycleAuthFailedPort
0x14005de86  mov     eax, [rdi+318h]
0x14005de8c  mov     r9d, [rdi+154h]
0x14005de93  cmp     r9d, eax
0x14005de96  jb      short loc_14005DECD
0x14005de98  mov     rcx, cs:WPP_GLOBAL_Control
0x14005de9f  lea     rbx, WPP_GLOBAL_Control
0x14005dea6  cmp     rcx, rbx
0x14005dea9  jz      loc_14005E093
0x14005deaf  mov     edx, 11h
0x14005deb4  mov     rcx, [rcx+18h]
0x14005deb8  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005debf  mov     dword ptr [rsp+0C0h+var_A0], eax
0x14005dec3  call    WPP_SF_Dd
0x14005dec8  jmp     loc_14005E093
0x14005decd  mov     eax, [rdi+314h]
0x14005ded3  mov     r9d, [rdi+148h]
0x14005deda  cmp     r9d, eax
0x14005dedd  jb      loc_14005DCD6
0x14005dee3  mov     rcx, cs:WPP_GLOBAL_Control
0x14005deea  lea     rbx, WPP_GLOBAL_Control
0x14005def1  cmp     rcx, rbx
0x14005def4  jz      loc_14005E093
0x14005defa  mov     edx, 12h
0x14005deff  jmp     short loc_14005DEB4
0x14005df01  mov     edx, [r15+8]; Tag
0x14005df05  mov     rcx, r15; P
0x14005df08  call    cs:__imp_ExFreePoolWithTag
0x14005df0f  nop     dword ptr [rax+rax+00h]
0x14005df14  jmp     loc_14005E093
0x14005df19  mov     rsi, [rbp+57h+var_78]
0x14005df1d  mov     eax, [r12]
0x14005df21  mov     [rdi+18Eh], eax
0x14005df27  movzx   eax, word ptr [r12+4]
0x14005df2d  mov     [rdi+192h], ax
0x14005df34  cmp     qword ptr [rsi+40h], 0
0x14005df39  jz      short loc_14005DF5C
0x14005df3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14005df42  cmp     rcx, rbx
0x14005df45  jz      short loc_14005DF5C
0x14005df47  mov     rcx, [rcx+18h]
0x14005df4b  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005df52  mov     edx, 14h
0x14005df57  call    WPP_SF_
0x14005df5c  inc     dword ptr [rsi+20h]
0x14005df5f  lock inc dword ptr [rsi+24h]
0x14005df63  mov     [r14+10h], rsi
0x14005df67  lea     rax, [rdi+1A0h]
0x14005df6e  mov     [rsi+40h], r14
0x14005df72  mov     rdx, [rax+8]
0x14005df76  cmp     [rdx], rax
0x14005df79  jz      short loc_14005DF82
0x14005df7b  mov     ecx, 3
0x14005df80  int     29h; Win8: RtlFailFast(ecx)
0x14005df82  mov     [r14], rax
0x14005df85  or      r15d, 0FFFFFFFFh
0x14005df89  mov     [r14+8], rdx
0x14005df8d  mov     [rdx], r14
0x14005df90  mov     [rax+8], r14
0x14005df94  jmp     loc_14005E02A
0x14005df99  mov     rcx, cs:WPP_GLOBAL_Control
0x14005dfa0  lea     rbx, WPP_GLOBAL_Control
0x14005dfa7  cmp     rcx, rbx
0x14005dfaa  jz      short loc_14005DFD1
0x14005dfac  mov     r9, [r13+10h]
0x14005dfb0  lea     r8, WPP_a9770ce4a1ad3c6bb5119fd080a73439_Traceguids
0x14005dfb7  mov     rcx, [rcx+18h]
0x14005dfbb  mov     edx, 15h
0x14005dfc0  mov     [rsp+0C0h+var_A0], r12
0x14005dfc5  mov     r9d, [r9+6ACh]
0x14005dfcc  call    WPP_SF_d_MAC_
0x14005dfd1  mov     rcx, [r14+30h]
0x14005dfd5  test    rcx, rcx
0x14005dfd8  jz      short loc_14005E011
0x14005dfda  add     rcx, 0FFFFFFFFFFFFFFF0h; P
0x14005dfde  mov     rax, [rcx]
0x14005dfe1  test    rax, rax
0x14005dfe4  jz      short loc_14005DFFA
0x14005dfe6  mov     rdx, rcx; Entry
0x14005dfe9  mov     rcx, rax; Lookaside
0x14005dfec  call    cs:__imp_ExFreeToNPagedLookasideList
0x14005dff3  nop     dword ptr [rax+rax+00h]
0x14005dff8  jmp     short loc_14005E009
0x14005dffa  mov     edx, [rcx+8]; Tag
0x14005dffd  call    cs:__imp_ExFreePoolWithTag
0x14005e004  nop     dword ptr [rax+rax+00h]
0x14005e009  mov     qword ptr [r14+30h], 0
0x14005e011  add     [rdi+14Ch], r15d
0x14005e018  lea     r8, qword_1400A1D38
0x14005e01f  mov     rdx, rsi; struct DOT11_MAC_STATE_ENTRY *
0x14005e022  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14005e025  call    ExtSTADeleteDataPort
0x14005e02a  cmp     dword ptr [r13+15F8h], 0
0x14005e032  jz      short loc_14005E049
0x14005e034  cmp     dword ptr [r13+1600h], 0
0x14005e03c  jz      short loc_14005E049
0x14005e03e  mov     dword ptr [r13+15FCh], 1
0x14005e049  mov     dword ptr [r14+18h], 1
0x14005e051  mov     rdx, r14; struct EXTSTA_ASSOC_ENTRY *
0x14005e054  mov     rcx, rdi; struct EXTSTA_VELAN *
0x14005e057  mov     [rdi+674h], r15d
  ... truncated ...
```
