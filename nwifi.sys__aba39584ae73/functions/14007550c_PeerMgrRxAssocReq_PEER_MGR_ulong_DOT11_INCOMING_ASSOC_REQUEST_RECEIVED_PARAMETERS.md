# PeerMgrRxAssocReq(_PEER_MGR *,ulong,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *)

- ea: `0x14007550c`
- end: `0x140075bf2`
- name: `?PeerMgrRxAssocReq@@YAXPEAU_PEER_MGR@@KPEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@@Z`
- size: `1766`
- prototype: `void(struct _PEER_MGR *, unsigned int, struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140071830`

## callees

- `0x14000d21c`
- `0x140020dc0`
- `0x140030b7c`
- `0x140031038`
- `0x1400314ec`
- `0x14003b04c`
- `0x140070b98`
- `0x140074f10`
- `0x14007550c`
- `0x1400768d4`
- `0x140077204`
- `0x1400773e4`
- `0x140078660`
- `0x140078f00`
- `0x140079adc`
- `0x14007baac`
- `0x14007ce90`
- `0x14007cf98`
- `0x14009bbb0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007576c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14007576c`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075b9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140075b9a`
- `ntoskrnl!RtlCompareMemory` at `0x1400757d5`
- `ntoskrnl!RtlCompareMemory` at `0x1400757d5`

## pseudocode

```c
void __fastcall PeerMgrRxAssocReq(
        struct _PEER_MGR *a1,
        unsigned int a2,
        struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *a3)
{
  int v3; // r12d
  unsigned int v5; // r8d
  int WPSEnabled; // edi
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 *v8; // r14
  int v9; // eax
  _EXTAP_VELAN *pAPVElan; // rax
  bool v11; // zf
  int v12; // ebx
  __int64 v13; // rdx
  __int64 v14; // r15
  struct _WFD_ROLE *pWFDRole; // rcx
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 *v16; // rdi
  unsigned int v17; // r15d
  int v18; // edx
  unsigned __int8 v19; // r15
  __int64 v20; // rbx
  PDEVICE_OBJECT v21; // rcx
  __int64 v22; // rdx
  void *hPeerList; // rcx
  PDEVICE_OBJECT v24; // rcx
  __int64 v25; // rdx
  struct _PEER_OBJECT *v26; // rbx
  _EXTAP_VELAN *v27; // rcx
  unsigned int v28[2]; // [rsp+30h] [rbp-49h] BYREF
  unsigned int v29; // [rsp+38h] [rbp-41h]
  _BYTE v30[40]; // [rsp+40h] [rbp-39h] BYREF
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 *v31; // [rsp+68h] [rbp-11h] BYREF
  void *v32; // [rsp+70h] [rbp-9h] BYREF
  struct _PEER_OBJECT *v33; // [rsp+78h] [rbp-1h] BYREF
  UCHAR *PeerMacAddr; // [rsp+80h] [rbp+7h] BYREF
  int v35; // [rsp+88h] [rbp+Fh]
  int v36; // [rsp+8Ch] [rbp+13h]
  _DWORD Source1[2]; // [rsp+90h] [rbp+17h] BYREF

  v3 = 0;
  v29 = a2;
  v33 = 0;
  Source1[0] = 0;
  LOWORD(Source1[1]) = 0;
  v5 = a2;
  v36 = 0;
  WPSEnabled = 0;
  v32 = 0;
  v8 = 0;
  v31 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
    {
      WPP_SF__MAC_(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_f879689d21dd3549a6d6da889544dc78_Traceguids,
        a3->PeerMacAddr);
    }
    v5 = v29;
  }
  v9 = *(_DWORD *)a3->PeerMacAddr;
  memset(&v30[1], 0, 27);
  *(_DWORD *)&v30[4] = v9;
  *(_WORD *)&v30[8] = *(_WORD *)&a3->PeerMacAddr[4];
  pAPVElan = a1->pAPVElan;
  *(_DWORD *)v30 = 1835648;
  *(_QWORD *)&v30[16] = 28;
  v11 = pAPVElan->LastSetAuthAlgo == DOT11_AUTH_ALGO_80211_OPEN;
  v30[10] = 1;
  if ( !v11 || (v12 = 1, pAPVElan->LastSetUcastCipher) )
    v12 = 0;
  *(_QWORD *)v28 = PeerMgrFindRsnIe(v5, a3);
  v14 = *(_QWORD *)v28;
  if ( !*(_QWORD *)v28 && !v12 )
    v3 = 1;
  pWFDRole = a1->pAPVElan->pWFDRole;
  if ( !pWFDRole )
    goto LABEL_55;
  if ( v3 )
  {
    v28[0] = 0;
    WPSEnabled = WFDRoleGetWPSEnabled(pWFDRole, (int *)v28);
    if ( WPSEnabled )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
      goto LABEL_30;
    }
    if ( !v28[0] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
      }
      v30[10] = 0;
      strcpy(&v30[12], "-");
      v30[24] = 1;
      goto LABEL_24;
    }
    WFDRoleParsePeerDeviceMacAddressFromAssocReq(
      a1->pAPVElan->pWFDRole,
      a3,
      (unsigned __int8 (*)[6])a1->WFDLastWPSPeerDeviceMacAddr);
LABEL_55:
    hPeerList = a1->hPeerList;
    PeerMacAddr = a3->PeerMacAddr;
    v35 = 6;
    PeerListFindAndAddRef(hPeerList, v13, &PeerMacAddr, 1, &v32, &v33);
    if ( !v32 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 41, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
      }
      v30[10] = 0;
      *(_WORD *)&v30[12] = 17;
      v30[24] = 3;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        goto LABEL_24;
      v25 = 42;
LABEL_62:
      WPP_SF_(v24->AttachedDevice, v25, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
      goto LABEL_24;
    }
    v26 = v33;
    v28[0] = 0;
    PeerObjValidateAssocRequest(v33, v29, a3, (struct _DOT11_INCOMING_ASSOC_DECISION_V2 *)v30, (int *)v28);
    *((_DWORD *)v26 + 16) = v3;
    if ( v28[0] && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 43, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
    if ( !v30[10] )
    {
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_24;
      }
      v25 = 44;
      goto LABEL_62;
    }
    if ( v14 && a1->pAPVElan->pVElan->pAdapt->AdapterEnhancedCapabilities.uWindowsWifiCxVersion )
    {
      Feature_Wpa3SoftAp__private_IsEnabledPreCheck();
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 45, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
      }
      *(_QWORD *)v30 = 47;
      *(_DWORD *)&v30[12] = 0;
      *(_OWORD *)&v30[24] = 0;
      *(_DWORD *)&v30[8] = v29;
      *(_QWORD *)&v30[16] = a3;
      APVElanSendUpcallRequest(a1->pAPVElan, 1, (struct DOT11_AUTH_UPCALL_REQUEST *)v30);
      goto LABEL_28;
    }
    if ( a1->pAPVElan->pWFDRole )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 46, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
      v27 = a1->pAPVElan;
      v17 = 28;
      v28[0] = 0;
      WPSEnabled = WFDRoleAddCachedIEsToAssocDecisionOidStructure(
                     v27->pWFDRole,
                     (struct _DOT11_INCOMING_ASSOC_DECISION_V2 *)v30,
                     0x1Cu,
                     &v31,
                     v28);
      if ( WPSEnabled )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 47, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
        v8 = v31;
        goto LABEL_28;
      }
      v8 = v31;
      if ( v31 )
      {
        v17 = v28[0];
        v16 = v31;
LABEL_89:
        PeerObjPrepareForAssocCompletion(v26, v16);
        if ( !*((_BYTE *)v16 + 10)
          && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 48, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
        }
        goto LABEL_25;
      }
    }
    else
    {
      v17 = 28;
    }
    v16 = (struct _DOT11_INCOMING_ASSOC_DECISION_V2 *)v30;
    goto LABEL_89;
  }
  WPSEnabled = WFDRoleParsePeerDeviceMacAddressFromAssocReq(pWFDRole, a3, (unsigned __int8 (*)[6])Source1);
  if ( WPSEnabled < 0 )
  {
    WPSEnabled = 0;
    goto LABEL_55;
  }
  v19 = WFDRoleLookupPersistentGroupIdListForLocalGO(a1->pAPVElan->pWFDRole, (unsigned __int8 (*)[6])Source1);
  if ( RtlCompareMemory(Source1, a1->WFDLastWPSPeerDeviceMacAddr, 6u) != 6 )
  {
    if ( !v19 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
      {
        goto LABEL_48;
      }
      v22 = 40;
      goto LABEL_47;
    }
LABEL_54:
    v14 = *(_QWORD *)v28;
    goto LABEL_55;
  }
  v20 = MEMORY[0xFFFFF78000000014];
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) != 0 )
  {
    ((void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD))WPP_SF_qq)(
      WPP_GLOBAL_Control->AttachedDevice,
      38,
      WPP_f879689d21dd3549a6d6da889544dc78_Traceguids,
      MEMORY[0xFFFFF78000000014],
      (_LARGE_INTEGER)a1->liWFDLastWPSDisassocTime.QuadPart);
  }
  if ( (unsigned __int64)(v20 - a1->liWFDLastWPSDisassocTime.QuadPart) < 0x8F0D180 || v19 )
    goto LABEL_54;
  v21 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || BYTE1(WPP_GLOBAL_Control->Timer) < 3u
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100000) == 0 )
  {
    goto LABEL_48;
  }
  v22 = 39;
LABEL_47:
  WPP_SF_(v21->AttachedDevice, v22, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
LABEL_48:
  v30[10] = 0;
  *(_WORD *)&v30[12] = 12;
  v30[24] = 8;
LABEL_24:
  v16 = (struct _DOT11_INCOMING_ASSOC_DECISION_V2 *)v30;
  v17 = 28;
LABEL_25:
  v28[0] = NwifiSetDirectOidRequestAsync(a1->pAPVElan->pVElan->pAdapt, 0xE030106u, v16, v17);
  MapPendingDirectOidStatus((int *)v28);
  WPSEnabled = v28[0];
  if ( v28[0] && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 49, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids, v28[0]);
LABEL_28:
  if ( v32 )
    PeerListDeref(a1->hPeerList, v18, v32, 1u);
LABEL_30:
  if ( v8 )
  {
    if ( *((_QWORD *)v8 - 2) )
      ExFreeToNPagedLookasideList(*((PNPAGED_LOOKASIDE_LIST *)v8 - 2), (char *)v8 - 16);
    else
      ExFreePoolWithTag((char *)v8 - 16, *((_DWORD *)v8 - 2));
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      50,
      WPP_f879689d21dd3549a6d6da889544dc78_Traceguids,
      (unsigned int)WPSEnabled);
}

```

## disassembly

```asm
0x14007550c  mov     [rsp-8+arg_18], rbx
0x140075511  push    rbp
0x140075512  push    rsi
0x140075513  push    rdi
0x140075514  push    r12
0x140075516  push    r13
0x140075518  push    r14
0x14007551a  push    r15
0x14007551c  lea     rbp, [rsp-27h]
0x140075521  sub     rsp, 0A0h
0x140075528  mov     rax, cs:__security_cookie
0x14007552f  xor     rax, rsp
0x140075532  mov     [rbp+57h+var_38], rax
0x140075536  xor     r12d, r12d
0x140075539  mov     [rbp+57h+var_98], edx
0x14007553c  xor     eax, eax
0x14007553e  mov     [rbp+57h+var_58], r12
0x140075542  mov     r13, r8
0x140075545  mov     [rbp+57h+Source1], eax
0x140075548  mov     [rbp+57h+var_3C], ax
0x14007554c  mov     r8d, edx
0x14007554f  mov     rsi, rcx
0x140075552  mov     dword ptr [rbp+57h+var_50+0Ch], r12d
0x140075556  mov     edi, r12d
0x140075559  mov     [rbp+57h+var_60], r12
0x14007555d  mov     r14d, r12d
0x140075560  mov     [rbp+57h+var_68], r12
0x140075564  mov     rcx, cs:WPP_GLOBAL_Control
0x14007556b  lea     rbx, WPP_GLOBAL_Control
0x140075572  cmp     rcx, rbx
0x140075575  jz      short loc_1400755C2
0x140075577  mov     rcx, [rcx+18h]
0x14007557b  lea     edx, [rax+22h]
0x14007557e  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140075585  call    WPP_SF_
0x14007558a  mov     rcx, cs:WPP_GLOBAL_Control
0x140075591  cmp     rcx, rbx
0x140075594  jz      short loc_1400755BE
0x140075596  cmp     byte ptr [rcx+29h], 3
0x14007559a  jb      short loc_1400755BE
0x14007559c  test    dword ptr [rcx+2Ch], 100000h
0x1400755a3  jz      short loc_1400755BE
0x1400755a5  mov     rcx, [rcx+18h]
0x1400755a9  lea     r9, [r13+4]
0x1400755ad  lea     edx, [r12+23h]
0x1400755b2  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x1400755b9  call    WPP_SF__MAC_
0x1400755be  mov     r8d, [rbp+57h+var_98]
0x1400755c2  mov     eax, [r13+4]
0x1400755c6  xorps   xmm0, xmm0
0x1400755c9  movups  xmmword ptr [rbp+57h+var_90+1], xmm0
0x1400755cd  mov     dword ptr [rbp+57h+var_90+4], eax
0x1400755d0  movzx   eax, word ptr [r13+8]
0x1400755d5  mov     word ptr [rbp+57h+var_88], ax
0x1400755d9  mov     rax, [rsi]
0x1400755dc  movups  xmmword ptr [rbp+57h+var_84], xmm0
0x1400755e0  mov     dword ptr [rbp-39h], 1C0280h
0x1400755e7  mov     [rbp+57h+var_80], 1Ch
0x1400755ef  cmp     dword ptr [rax+70h], 1
0x1400755f3  mov     byte ptr [rbp+57h+var_88+2], 1
0x1400755f7  jnz     short loc_140075604
0x1400755f9  mov     ebx, 1
0x1400755fe  cmp     [rax+74h], r12d
0x140075602  jz      short loc_140075607
0x140075604  mov     ebx, r12d
0x140075607  mov     rdx, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x14007560a  mov     ecx, r8d; unsigned int
0x14007560d  call    ?PeerMgrFindRsnIe@@YAPEBEKPEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@@Z; PeerMgrFindRsnIe(ulong,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *)
0x140075612  mov     qword ptr [rbp+57h+var_A0], rax
0x140075616  mov     r15, rax
0x140075619  test    rax, rax
0x14007561c  jnz     short loc_140075626
0x14007561e  test    ebx, ebx
0x140075620  jnz     short loc_140075626
0x140075622  lea     r12d, [rax+1]
0x140075626  mov     rax, [rsi]
0x140075629  mov     rcx, [rax+1B0h]; struct _WFD_ROLE *
0x140075630  test    rcx, rcx
0x140075633  jz      loc_1400758D0
0x140075639  test    r12d, r12d
0x14007563c  jz      loc_140075798
0x140075642  lea     rdx, [rbp+57h+var_A0]; int *
0x140075646  mov     [rbp+57h+var_A0], edi
0x140075649  call    ?WFDRoleGetWPSEnabled@@YAKPEAU_WFD_ROLE@@PEAH@Z; WFDRoleGetWPSEnabled(_WFD_ROLE *,int *)
0x14007564e  mov     edi, eax
0x140075650  test    eax, eax
0x140075652  jz      short loc_140075685
0x140075654  mov     rcx, cs:WPP_GLOBAL_Control
0x14007565b  lea     r12, WPP_GLOBAL_Control
0x140075662  cmp     rcx, r12
0x140075665  jz      loc_14007574D
0x14007566b  mov     rcx, [rcx+18h]
0x14007566f  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140075676  mov     edx, 24h ; '$'
0x14007567b  call    WPP_SF_
0x140075680  jmp     loc_14007574D
0x140075685  cmp     [rbp+57h+var_A0], r14d
0x140075689  jnz     loc_14007577D
0x14007568f  mov     rcx, cs:WPP_GLOBAL_Control
0x140075696  lea     r12, WPP_GLOBAL_Control
0x14007569d  cmp     rcx, r12
0x1400756a0  jz      short loc_1400756C6
0x1400756a2  cmp     byte ptr [rcx+29h], 3
0x1400756a6  jb      short loc_1400756C6
0x1400756a8  test    dword ptr [rcx+2Ch], 100000h
0x1400756af  jz      short loc_1400756C6
0x1400756b1  mov     rcx, [rcx+18h]
0x1400756b5  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x1400756bc  mov     edx, 25h ; '%'
0x1400756c1  call    WPP_SF_
0x1400756c6  mov     edx, 2Dh ; '-'
0x1400756cb  mov     byte ptr [rbp+57h+var_88+2], r14b
0x1400756cf  mov     word ptr [rbp+57h+var_84], dx
0x1400756d3  mov     byte ptr [rbp+57h+var_78], 1
0x1400756d7  lea     rdi, [rbp+57h+var_90]
0x1400756db  mov     r15d, 1Ch
0x1400756e1  mov     rax, [rsi]
0x1400756e4  mov     r9d, r15d; unsigned int
0x1400756e7  mov     r8, rdi; void *
0x1400756ea  mov     edx, 0E030106h; unsigned int
0x1400756ef  mov     rcx, [rax]
0x1400756f2  mov     rcx, [rcx+10h]; struct _ADAPT *
0x1400756f6  call    ?NwifiSetDirectOidRequestAsync@@YAHPEAU_ADAPT@@KPEAXK@Z; NwifiSetDirectOidRequestAsync(_ADAPT *,ulong,void *,ulong)
0x1400756fb  lea     rcx, [rbp+57h+var_A0]; int *
0x1400756ff  mov     [rbp+57h+var_A0], eax
0x140075702  call    ?MapPendingDirectOidStatus@@YAXPEAH@Z; MapPendingDirectOidStatus(int *)
0x140075707  mov     edi, [rbp+57h+var_A0]
0x14007570a  test    edi, edi
0x14007570c  jz      short loc_140075732
0x14007570e  mov     rcx, cs:WPP_GLOBAL_Control
0x140075715  cmp     rcx, r12
0x140075718  jz      short loc_140075732
0x14007571a  mov     rcx, [rcx+18h]
0x14007571e  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140075725  mov     edx, 31h ; '1'
0x14007572a  mov     r9d, edi
0x14007572d  call    WPP_SF_d
0x140075732  mov     rax, [rbp+57h+var_60]
0x140075736  test    rax, rax
0x140075739  jz      short loc_14007574D
0x14007573b  mov     rcx, [rsi+10h]; void *
0x14007573f  mov     r9d, 1; unsigned int
0x140075745  mov     r8, rax; void *
0x140075748  call    ?PeerListDeref@@YAXPEAXH0K@Z; PeerListDeref(void *,int,void *,ulong)
0x14007574d  test    r14, r14
0x140075750  jz      loc_140075BA6
0x140075756  lea     rcx, [r14-10h]; P
0x14007575a  mov     rax, [rcx]
0x14007575d  test    rax, rax
0x140075760  jz      loc_140075B97
0x140075766  mov     rdx, rcx; Entry
0x140075769  mov     rcx, rax; Lookaside
0x14007576c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140075773  nop     dword ptr [rax+rax+00h]
0x140075778  jmp     loc_140075BA6
0x14007577d  mov     rcx, [rsi]
0x140075780  lea     r8, [rsi+30h]; unsigned __int8 (*)[6]
0x140075784  mov     rdx, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x140075787  mov     rcx, [rcx+1B0h]; struct _WFD_ROLE *
0x14007578e  call    ?WFDRoleParsePeerDeviceMacAddressFromAssocReq@@YAHPEAU_WFD_ROLE@@PEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@PEAY05E@Z; WFDRoleParsePeerDeviceMacAddressFromAssocReq(_WFD_ROLE *,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *,uchar (*)[6])
0x140075793  jmp     loc_1400758D0
0x140075798  lea     r8, [rbp+57h+Source1]; unsigned __int8 (*)[6]
0x14007579c  mov     rdx, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x14007579f  call    ?WFDRoleParsePeerDeviceMacAddressFromAssocReq@@YAHPEAU_WFD_ROLE@@PEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@PEAY05E@Z; WFDRoleParsePeerDeviceMacAddressFromAssocReq(_WFD_ROLE *,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *,uchar (*)[6])
0x1400757a4  mov     edi, eax
0x1400757a6  test    eax, eax
0x1400757a8  jns     short loc_1400757B1
0x1400757aa  xor     edi, edi
0x1400757ac  jmp     loc_1400758D0
0x1400757b1  mov     rcx, [rsi]
0x1400757b4  lea     rdx, [rbp+57h+Source1]; unsigned __int8 (*)[6]
0x1400757b8  mov     rcx, [rcx+1B0h]; struct _WFD_ROLE *
0x1400757bf  call    ?WFDRoleLookupPersistentGroupIdListForLocalGO@@YAEPEAU_WFD_ROLE@@PEAY05E@Z; WFDRoleLookupPersistentGroupIdListForLocalGO(_WFD_ROLE *,uchar (*)[6])
0x1400757c4  lea     rdx, [rsi+30h]; Source2
0x1400757c8  mov     r8d, 6; Length
0x1400757ce  lea     rcx, [rbp+57h+Source1]; Source1
0x1400757d2  mov     r15b, al
0x1400757d5  call    cs:__imp_RtlCompareMemory
0x1400757dc  nop     dword ptr [rax+rax+00h]
0x1400757e1  cmp     rax, 6
0x1400757e5  jnz     loc_14007589E
0x1400757eb  mov     rbx, 0FFFFF78000000014h
0x1400757f5  mov     rbx, [rbx]
0x1400757f8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400757ff  lea     rax, WPP_GLOBAL_Control
0x140075806  cmp     rcx, rax
0x140075809  jz      short loc_14007583B
0x14007580b  cmp     byte ptr [rcx+29h], 3
0x14007580f  jb      short loc_14007583B
0x140075811  test    dword ptr [rcx+2Ch], 100000h
0x140075818  jz      short loc_14007583B
0x14007581a  mov     rax, [rsi+28h]
0x14007581e  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140075825  mov     rcx, [rcx+18h]
0x140075829  mov     edx, 26h ; '&'
0x14007582e  mov     r9, rbx
0x140075831  mov     [rsp+0D0h+var_B0], rax
0x140075836  call    WPP_SF_qq
0x14007583b  sub     rbx, [rsi+28h]
0x14007583f  cmp     rbx, 8F0D180h
0x140075846  jb      loc_1400758CC
0x14007584c  test    r15b, r15b
0x14007584f  jnz     short loc_1400758CC
0x140075851  mov     rcx, cs:WPP_GLOBAL_Control
0x140075858  lea     r12, WPP_GLOBAL_Control
0x14007585f  cmp     rcx, r12
0x140075862  jz      short loc_140075888
0x140075864  cmp     byte ptr [rcx+29h], 3
0x140075868  jb      short loc_140075888
0x14007586a  test    dword ptr [rcx+2Ch], 100000h
0x140075871  jz      short loc_140075888
0x140075873  mov     edx, 27h ; '''
0x140075878  mov     rcx, [rcx+18h]
0x14007587c  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140075883  call    WPP_SF_
0x140075888  mov     eax, 0Ch
0x14007588d  mov     byte ptr [rbp+57h+var_88+2], r14b
0x140075891  mov     word ptr [rbp+57h+var_84], ax
0x140075895  mov     byte ptr [rbp+57h+var_78], 8
0x140075899  jmp     loc_1400756D7
0x14007589e  test    r15b, r15b
0x1400758a1  jnz     short loc_1400758CC
0x1400758a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400758aa  lea     r12, WPP_GLOBAL_Control
0x1400758b1  cmp     rcx, r12
0x1400758b4  jz      short loc_140075888
0x1400758b6  cmp     byte ptr [rcx+29h], 3
0x1400758ba  jb      short loc_140075888
0x1400758bc  test    dword ptr [rcx+2Ch], 100000h
0x1400758c3  jz      short loc_140075888
0x1400758c5  mov     edx, 28h ; '('
0x1400758ca  jmp     short loc_140075878
0x1400758cc  mov     r15, qword ptr [rbp+57h+var_A0]
0x1400758d0  mov     rcx, [rsi+10h]
0x1400758d4  lea     rax, [r13+4]
0x1400758d8  mov     qword ptr [rbp+57h+var_50], rax
0x1400758dc  lea     r8, [rbp+57h+var_50]
0x1400758e0  mov     dword ptr [rbp+57h+var_50+8], 6
0x1400758e7  lea     rax, [rbp+57h+var_58]
0x1400758eb  movaps  xmm0, [rbp+57h+var_50]
0x1400758ef  mov     r9d, 1
0x1400758f5  mov     [rsp+0D0h+var_A8], rax
0x1400758fa  lea     rax, [rbp+57h+var_60]
0x1400758fe  mov     [rsp+0D0h+var_B0], rax
0x140075903  movdqa  [rbp+57h+var_50], xmm0
0x140075908  call    ?PeerListFindAndAddRef@@YAHPEAXHU_CONTEXT_SIGNATURE@@KPEAPEAX2@Z; PeerListFindAndAddRef(void *,int,_CONTEXT_SIGNATURE,ulong,void * *,void * *)
0x14007590d  cmp     [rbp+57h+var_60], r14
0x140075911  jnz     short loc_140075983
0x140075913  mov     rcx, cs:WPP_GLOBAL_Control
0x14007591a  lea     r12, WPP_GLOBAL_Control
0x140075921  cmp     rcx, r12
0x140075924  jz      short loc_14007594A
0x140075926  cmp     byte ptr [rcx+29h], 3
0x14007592a  jb      short loc_14007594A
0x14007592c  test    dword ptr [rcx+2Ch], 100000h
0x140075933  jz      short loc_14007594A
0x140075935  mov     rcx, [rcx+18h]
0x140075939  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140075940  mov     edx, 29h ; ')'
0x140075945  call    WPP_SF_
0x14007594a  mov     eax, 11h
0x14007594f  mov     byte ptr [rbp+57h+var_88+2], r14b
0x140075953  mov     word ptr [rbp+57h+var_84], ax
0x140075957  mov     byte ptr [rbp+57h+var_78], 3
0x14007595b  mov     rcx, cs:WPP_GLOBAL_Control
0x140075962  cmp     rcx, r12
0x140075965  jz      loc_1400756D7
0x14007596b  lea     edx, [rax+19h]
0x14007596e  mov     rcx, [rcx+18h]
0x140075972  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140075979  call    WPP_SF_
0x14007597e  jmp     loc_1400756D7
0x140075983  mov     rbx, [rbp+57h+var_58]
0x140075987  lea     rax, [rbp+57h+var_A0]
0x14007598b  mov     edx, [rbp+57h+var_98]; unsigned int
0x14007598e  lea     r9, [rbp+57h+var_90]; struct _DOT11_INCOMING_ASSOC_DECISION_V2 *
0x140075992  mov     rcx, rbx; struct _PEER_OBJECT *
0x140075995  mov     [rbp+57h+var_A0], r14d
0x140075999  mov     r8, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x14007599c  mov     [rsp+0D0h+var_B0], rax; int *
0x1400759a1  call    ?PeerObjValidateAssocRequest@@YAXPEAU_PEER_OBJECT@@KPEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@PEAU_DOT11_INCOMING_ASSOC_DECISION_V2@@PEAH@Z; PeerObjValidateAssocRequest(_PEER_OBJECT *,ulong,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *,_DOT11_INCOMING_ASSOC_DECISION_V2 *,int *)
0x1400759a6  mov     [rbx+40h], r12d
0x1400759aa  cmp     [rbp+57h+var_A0], r14d
0x1400759ae  jz      short loc_1400759DA
0x1400759b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400759b7  lea     r12, WPP_GLOBAL_Control
0x1400759be  cmp     rcx, r12
0x1400759c1  jz      short loc_1400759E1
0x1400759c3  mov     rcx, [rcx+18h]
0x1400759c7  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x1400759ce  mov     edx, 2Bh ; '+'
0x1400759d3  call    WPP_SF_
0x1400759d8  jmp     short loc_1400759E1
0x1400759da  lea     r12, WPP_GLOBAL_Control
0x1400759e1  cmp     byte ptr [rbp+57h+var_88+2], r14b
0x1400759e5  jnz     short loc_140075A18
0x1400759e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400759ee  cmp     rcx, r12
0x1400759f1  jz      loc_1400756D7
0x1400759f7  cmp     byte ptr [rcx+29h], 3
  ... truncated ...
```
