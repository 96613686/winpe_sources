# PeerMgrRxAssocReq(_PEER_MGR *,ulong,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *)

- ea: `0x140073cdc`
- end: `0x1400743c2`
- name: `?PeerMgrRxAssocReq@@YAXPEAU_PEER_MGR@@KPEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@@Z`
- size: `1766`
- prototype: `void(struct _PEER_MGR *, unsigned int, struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140070000`

## callees

- `0x14000d22c`
- `0x140020dc0`
- `0x1400308ec`
- `0x140030da8`
- `0x14003125c`
- `0x14003ae2c`
- `0x14006f368`
- `0x1400736e0`
- `0x140073cdc`
- `0x1400750a4`
- `0x1400759d4`
- `0x140075bb4`
- `0x140076e30`
- `0x1400776d0`
- `0x1400782ac`
- `0x14007a27c`
- `0x14007b660`
- `0x14007b768`
- `0x14009a3d0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073f3c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140073f3c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007436a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007436a`
- `ntoskrnl!RtlCompareMemory` at `0x140073fa5`
- `ntoskrnl!RtlCompareMemory` at `0x140073fa5`

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
  __int64 v29; // [rsp+38h] [rbp-41h]
  _BYTE v30[40]; // [rsp+40h] [rbp-39h] BYREF
  struct _DOT11_INCOMING_ASSOC_DECISION_V2 *v31; // [rsp+68h] [rbp-11h] BYREF
  void *v32; // [rsp+70h] [rbp-9h] BYREF
  struct _PEER_OBJECT *v33; // [rsp+78h] [rbp-1h] BYREF
  UCHAR *PeerMacAddr; // [rsp+80h] [rbp+7h] BYREF
  int v35; // [rsp+88h] [rbp+Fh]
  int v36; // [rsp+8Ch] [rbp+13h]
  _DWORD Source1[2]; // [rsp+90h] [rbp+17h] BYREF

  v3 = 0;
  LODWORD(v29) = a2;
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
    PeerListFindAndAddRef(hPeerList, v13, &PeerMacAddr, 1, &v32, &v33, *(_QWORD *)v28, v29);
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
    WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids);
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
  v28[0] = NwifiSetDirectOidRequestAsync(a1->pAPVElan->pVElan->pAdapt, 235077894, v16, v17);
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
0x140073cdc  mov     [rsp-8+arg_18], rbx
0x140073ce1  push    rbp
0x140073ce2  push    rsi
0x140073ce3  push    rdi
0x140073ce4  push    r12
0x140073ce6  push    r13
0x140073ce8  push    r14
0x140073cea  push    r15
0x140073cec  lea     rbp, [rsp-27h]
0x140073cf1  sub     rsp, 0A0h
0x140073cf8  mov     rax, cs:__security_cookie
0x140073cff  xor     rax, rsp
0x140073d02  mov     [rbp+57h+var_38], rax
0x140073d06  xor     r12d, r12d
0x140073d09  mov     dword ptr [rbp+57h+var_98], edx
0x140073d0c  xor     eax, eax
0x140073d0e  mov     [rbp+57h+var_58], r12
0x140073d12  mov     r13, r8
0x140073d15  mov     [rbp+57h+Source1], eax
0x140073d18  mov     [rbp+57h+var_3C], ax
0x140073d1c  mov     r8d, edx
0x140073d1f  mov     rsi, rcx
0x140073d22  mov     dword ptr [rbp+57h+var_50+0Ch], r12d
0x140073d26  mov     edi, r12d
0x140073d29  mov     [rbp+57h+var_60], r12
0x140073d2d  mov     r14d, r12d
0x140073d30  mov     [rbp+57h+var_68], r12
0x140073d34  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d3b  lea     rbx, WPP_GLOBAL_Control
0x140073d42  cmp     rcx, rbx
0x140073d45  jz      short loc_140073D92
0x140073d47  mov     rcx, [rcx+18h]
0x140073d4b  lea     edx, [rax+22h]
0x140073d4e  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140073d55  call    WPP_SF_
0x140073d5a  mov     rcx, cs:WPP_GLOBAL_Control
0x140073d61  cmp     rcx, rbx
0x140073d64  jz      short loc_140073D8E
0x140073d66  cmp     byte ptr [rcx+29h], 3
0x140073d6a  jb      short loc_140073D8E
0x140073d6c  test    dword ptr [rcx+2Ch], 100000h
0x140073d73  jz      short loc_140073D8E
0x140073d75  mov     rcx, [rcx+18h]
0x140073d79  lea     r9, [r13+4]
0x140073d7d  lea     edx, [r12+23h]
0x140073d82  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140073d89  call    WPP_SF__MAC_
0x140073d8e  mov     r8d, dword ptr [rbp+57h+var_98]
0x140073d92  mov     eax, [r13+4]
0x140073d96  xorps   xmm0, xmm0
0x140073d99  movups  xmmword ptr [rbp+57h+var_90+1], xmm0
0x140073d9d  mov     dword ptr [rbp+57h+var_90+4], eax
0x140073da0  movzx   eax, word ptr [r13+8]
0x140073da5  mov     word ptr [rbp+57h+var_88], ax
0x140073da9  mov     rax, [rsi]
0x140073dac  movups  xmmword ptr [rbp+57h+var_84], xmm0
0x140073db0  mov     dword ptr [rbp-39h], 1C0280h
0x140073db7  mov     [rbp+57h+var_80], 1Ch
0x140073dbf  cmp     dword ptr [rax+70h], 1
0x140073dc3  mov     byte ptr [rbp+57h+var_88+2], 1
0x140073dc7  jnz     short loc_140073DD4
0x140073dc9  mov     ebx, 1
0x140073dce  cmp     [rax+74h], r12d
0x140073dd2  jz      short loc_140073DD7
0x140073dd4  mov     ebx, r12d
0x140073dd7  mov     rdx, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x140073dda  mov     ecx, r8d; unsigned int
0x140073ddd  call    ?PeerMgrFindRsnIe@@YAPEBEKPEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@@Z; PeerMgrFindRsnIe(ulong,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *)
0x140073de2  mov     qword ptr [rbp+57h+var_A0], rax
0x140073de6  mov     r15, rax
0x140073de9  test    rax, rax
0x140073dec  jnz     short loc_140073DF6
0x140073dee  test    ebx, ebx
0x140073df0  jnz     short loc_140073DF6
0x140073df2  lea     r12d, [rax+1]
0x140073df6  mov     rax, [rsi]
0x140073df9  mov     rcx, [rax+1B0h]; struct _WFD_ROLE *
0x140073e00  test    rcx, rcx
0x140073e03  jz      loc_1400740A0
0x140073e09  test    r12d, r12d
0x140073e0c  jz      loc_140073F68
0x140073e12  lea     rdx, [rbp+57h+var_A0]; int *
0x140073e16  mov     [rbp+57h+var_A0], edi
0x140073e19  call    ?WFDRoleGetWPSEnabled@@YAKPEAU_WFD_ROLE@@PEAH@Z; WFDRoleGetWPSEnabled(_WFD_ROLE *,int *)
0x140073e1e  mov     edi, eax
0x140073e20  test    eax, eax
0x140073e22  jz      short loc_140073E55
0x140073e24  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e2b  lea     r12, WPP_GLOBAL_Control
0x140073e32  cmp     rcx, r12
0x140073e35  jz      loc_140073F1D
0x140073e3b  mov     rcx, [rcx+18h]
0x140073e3f  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140073e46  mov     edx, 24h ; '$'
0x140073e4b  call    WPP_SF_
0x140073e50  jmp     loc_140073F1D
0x140073e55  cmp     [rbp+57h+var_A0], r14d
0x140073e59  jnz     loc_140073F4D
0x140073e5f  mov     rcx, cs:WPP_GLOBAL_Control
0x140073e66  lea     r12, WPP_GLOBAL_Control
0x140073e6d  cmp     rcx, r12
0x140073e70  jz      short loc_140073E96
0x140073e72  cmp     byte ptr [rcx+29h], 3
0x140073e76  jb      short loc_140073E96
0x140073e78  test    dword ptr [rcx+2Ch], 100000h
0x140073e7f  jz      short loc_140073E96
0x140073e81  mov     rcx, [rcx+18h]
0x140073e85  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140073e8c  mov     edx, 25h ; '%'
0x140073e91  call    WPP_SF_
0x140073e96  mov     edx, 2Dh ; '-'
0x140073e9b  mov     byte ptr [rbp+57h+var_88+2], r14b
0x140073e9f  mov     word ptr [rbp+57h+var_84], dx
0x140073ea3  mov     byte ptr [rbp+57h+var_78], 1
0x140073ea7  lea     rdi, [rbp+57h+var_90]
0x140073eab  mov     r15d, 1Ch
0x140073eb1  mov     rax, [rsi]
0x140073eb4  mov     r9d, r15d; unsigned int
0x140073eb7  mov     r8, rdi; void *
0x140073eba  mov     edx, 0E030106h; unsigned int
0x140073ebf  mov     rcx, [rax]
0x140073ec2  mov     rcx, [rcx+10h]; struct _ADAPT *
0x140073ec6  call    ?NwifiSetDirectOidRequestAsync@@YAHPEAU_ADAPT@@KPEAXK@Z; NwifiSetDirectOidRequestAsync(_ADAPT *,ulong,void *,ulong)
0x140073ecb  lea     rcx, [rbp+57h+var_A0]; int *
0x140073ecf  mov     [rbp+57h+var_A0], eax
0x140073ed2  call    ?MapPendingDirectOidStatus@@YAXPEAH@Z; MapPendingDirectOidStatus(int *)
0x140073ed7  mov     edi, [rbp+57h+var_A0]
0x140073eda  test    edi, edi
0x140073edc  jz      short loc_140073F02
0x140073ede  mov     rcx, cs:WPP_GLOBAL_Control
0x140073ee5  cmp     rcx, r12
0x140073ee8  jz      short loc_140073F02
0x140073eea  mov     rcx, [rcx+18h]
0x140073eee  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140073ef5  mov     edx, 31h ; '1'
0x140073efa  mov     r9d, edi
0x140073efd  call    WPP_SF_d
0x140073f02  mov     rax, [rbp+57h+var_60]
0x140073f06  test    rax, rax
0x140073f09  jz      short loc_140073F1D
0x140073f0b  mov     rcx, [rsi+10h]; void *
0x140073f0f  mov     r9d, 1; unsigned int
0x140073f15  mov     r8, rax; void *
0x140073f18  call    ?PeerListDeref@@YAXPEAXH0K@Z; PeerListDeref(void *,int,void *,ulong)
0x140073f1d  test    r14, r14
0x140073f20  jz      loc_140074376
0x140073f26  lea     rcx, [r14-10h]; P
0x140073f2a  mov     rax, [rcx]
0x140073f2d  test    rax, rax
0x140073f30  jz      loc_140074367
0x140073f36  mov     rdx, rcx; Entry
0x140073f39  mov     rcx, rax; Lookaside
0x140073f3c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140073f43  nop     dword ptr [rax+rax+00h]
0x140073f48  jmp     loc_140074376
0x140073f4d  mov     rcx, [rsi]
0x140073f50  lea     r8, [rsi+30h]; unsigned __int8 (*)[6]
0x140073f54  mov     rdx, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x140073f57  mov     rcx, [rcx+1B0h]; struct _WFD_ROLE *
0x140073f5e  call    ?WFDRoleParsePeerDeviceMacAddressFromAssocReq@@YAHPEAU_WFD_ROLE@@PEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@PEAY05E@Z; WFDRoleParsePeerDeviceMacAddressFromAssocReq(_WFD_ROLE *,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *,uchar (*)[6])
0x140073f63  jmp     loc_1400740A0
0x140073f68  lea     r8, [rbp+57h+Source1]; unsigned __int8 (*)[6]
0x140073f6c  mov     rdx, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x140073f6f  call    ?WFDRoleParsePeerDeviceMacAddressFromAssocReq@@YAHPEAU_WFD_ROLE@@PEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@PEAY05E@Z; WFDRoleParsePeerDeviceMacAddressFromAssocReq(_WFD_ROLE *,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *,uchar (*)[6])
0x140073f74  mov     edi, eax
0x140073f76  test    eax, eax
0x140073f78  jns     short loc_140073F81
0x140073f7a  xor     edi, edi
0x140073f7c  jmp     loc_1400740A0
0x140073f81  mov     rcx, [rsi]
0x140073f84  lea     rdx, [rbp+57h+Source1]; unsigned __int8 (*)[6]
0x140073f88  mov     rcx, [rcx+1B0h]; struct _WFD_ROLE *
0x140073f8f  call    ?WFDRoleLookupPersistentGroupIdListForLocalGO@@YAEPEAU_WFD_ROLE@@PEAY05E@Z; WFDRoleLookupPersistentGroupIdListForLocalGO(_WFD_ROLE *,uchar (*)[6])
0x140073f94  lea     rdx, [rsi+30h]; Source2
0x140073f98  mov     r8d, 6; Length
0x140073f9e  lea     rcx, [rbp+57h+Source1]; Source1
0x140073fa2  mov     r15b, al
0x140073fa5  call    cs:__imp_RtlCompareMemory
0x140073fac  nop     dword ptr [rax+rax+00h]
0x140073fb1  cmp     rax, 6
0x140073fb5  jnz     loc_14007406E
0x140073fbb  mov     rbx, 0FFFFF78000000014h
0x140073fc5  mov     rbx, [rbx]
0x140073fc8  mov     rcx, cs:WPP_GLOBAL_Control
0x140073fcf  lea     rax, WPP_GLOBAL_Control
0x140073fd6  cmp     rcx, rax
0x140073fd9  jz      short loc_14007400B
0x140073fdb  cmp     byte ptr [rcx+29h], 3
0x140073fdf  jb      short loc_14007400B
0x140073fe1  test    dword ptr [rcx+2Ch], 100000h
0x140073fe8  jz      short loc_14007400B
0x140073fea  mov     rax, [rsi+28h]
0x140073fee  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140073ff5  mov     rcx, [rcx+18h]
0x140073ff9  mov     edx, 26h ; '&'
0x140073ffe  mov     r9, rbx
0x140074001  mov     [rsp+0D0h+var_B0], rax
0x140074006  call    WPP_SF_qq
0x14007400b  sub     rbx, [rsi+28h]
0x14007400f  cmp     rbx, 8F0D180h
0x140074016  jb      loc_14007409C
0x14007401c  test    r15b, r15b
0x14007401f  jnz     short loc_14007409C
0x140074021  mov     rcx, cs:WPP_GLOBAL_Control
0x140074028  lea     r12, WPP_GLOBAL_Control
0x14007402f  cmp     rcx, r12
0x140074032  jz      short loc_140074058
0x140074034  cmp     byte ptr [rcx+29h], 3
0x140074038  jb      short loc_140074058
0x14007403a  test    dword ptr [rcx+2Ch], 100000h
0x140074041  jz      short loc_140074058
0x140074043  mov     edx, 27h ; '''
0x140074048  mov     rcx, [rcx+18h]
0x14007404c  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140074053  call    WPP_SF_
0x140074058  mov     eax, 0Ch
0x14007405d  mov     byte ptr [rbp+57h+var_88+2], r14b
0x140074061  mov     word ptr [rbp+57h+var_84], ax
0x140074065  mov     byte ptr [rbp+57h+var_78], 8
0x140074069  jmp     loc_140073EA7
0x14007406e  test    r15b, r15b
0x140074071  jnz     short loc_14007409C
0x140074073  mov     rcx, cs:WPP_GLOBAL_Control
0x14007407a  lea     r12, WPP_GLOBAL_Control
0x140074081  cmp     rcx, r12
0x140074084  jz      short loc_140074058
0x140074086  cmp     byte ptr [rcx+29h], 3
0x14007408a  jb      short loc_140074058
0x14007408c  test    dword ptr [rcx+2Ch], 100000h
0x140074093  jz      short loc_140074058
0x140074095  mov     edx, 28h ; '('
0x14007409a  jmp     short loc_140074048
0x14007409c  mov     r15, qword ptr [rbp+57h+var_A0]
0x1400740a0  mov     rcx, [rsi+10h]
0x1400740a4  lea     rax, [r13+4]
0x1400740a8  mov     qword ptr [rbp+57h+var_50], rax
0x1400740ac  lea     r8, [rbp+57h+var_50]
0x1400740b0  mov     dword ptr [rbp+57h+var_50+8], 6
0x1400740b7  lea     rax, [rbp+57h+var_58]
0x1400740bb  movaps  xmm0, [rbp+57h+var_50]
0x1400740bf  mov     r9d, 1
0x1400740c5  mov     [rsp+0D0h+var_A8], rax
0x1400740ca  lea     rax, [rbp+57h+var_60]
0x1400740ce  mov     [rsp+0D0h+var_B0], rax
0x1400740d3  movdqa  [rbp+57h+var_50], xmm0
0x1400740d8  call    ?PeerListFindAndAddRef@@YAHPEAXHU_CONTEXT_SIGNATURE@@KPEAPEAX2@Z; PeerListFindAndAddRef(void *,int,_CONTEXT_SIGNATURE,ulong,void * *,void * *)
0x1400740dd  cmp     [rbp+57h+var_60], r14
0x1400740e1  jnz     short loc_140074153
0x1400740e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400740ea  lea     r12, WPP_GLOBAL_Control
0x1400740f1  cmp     rcx, r12
0x1400740f4  jz      short loc_14007411A
0x1400740f6  cmp     byte ptr [rcx+29h], 3
0x1400740fa  jb      short loc_14007411A
0x1400740fc  test    dword ptr [rcx+2Ch], 100000h
0x140074103  jz      short loc_14007411A
0x140074105  mov     rcx, [rcx+18h]
0x140074109  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140074110  mov     edx, 29h ; ')'
0x140074115  call    WPP_SF_
0x14007411a  mov     eax, 11h
0x14007411f  mov     byte ptr [rbp+57h+var_88+2], r14b
0x140074123  mov     word ptr [rbp+57h+var_84], ax
0x140074127  mov     byte ptr [rbp+57h+var_78], 3
0x14007412b  mov     rcx, cs:WPP_GLOBAL_Control
0x140074132  cmp     rcx, r12
0x140074135  jz      loc_140073EA7
0x14007413b  lea     edx, [rax+19h]
0x14007413e  mov     rcx, [rcx+18h]
0x140074142  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x140074149  call    WPP_SF_
0x14007414e  jmp     loc_140073EA7
0x140074153  mov     rbx, [rbp+57h+var_58]
0x140074157  lea     rax, [rbp+57h+var_A0]
0x14007415b  mov     edx, dword ptr [rbp+57h+var_98]; unsigned int
0x14007415e  lea     r9, [rbp+57h+var_90]; struct _DOT11_INCOMING_ASSOC_DECISION_V2 *
0x140074162  mov     rcx, rbx; struct _PEER_OBJECT *
0x140074165  mov     [rbp+57h+var_A0], r14d
0x140074169  mov     r8, r13; struct _DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *
0x14007416c  mov     [rsp+0D0h+var_B0], rax; int *
0x140074171  call    ?PeerObjValidateAssocRequest@@YAXPEAU_PEER_OBJECT@@KPEAU_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS@@PEAU_DOT11_INCOMING_ASSOC_DECISION_V2@@PEAH@Z; PeerObjValidateAssocRequest(_PEER_OBJECT *,ulong,_DOT11_INCOMING_ASSOC_REQUEST_RECEIVED_PARAMETERS *,_DOT11_INCOMING_ASSOC_DECISION_V2 *,int *)
0x140074176  mov     [rbx+40h], r12d
0x14007417a  cmp     [rbp+57h+var_A0], r14d
0x14007417e  jz      short loc_1400741AA
0x140074180  mov     rcx, cs:WPP_GLOBAL_Control
0x140074187  lea     r12, WPP_GLOBAL_Control
0x14007418e  cmp     rcx, r12
0x140074191  jz      short loc_1400741B1
0x140074193  mov     rcx, [rcx+18h]
0x140074197  lea     r8, WPP_f879689d21dd3549a6d6da889544dc78_Traceguids
0x14007419e  mov     edx, 2Bh ; '+'
0x1400741a3  call    WPP_SF_
0x1400741a8  jmp     short loc_1400741B1
0x1400741aa  lea     r12, WPP_GLOBAL_Control
0x1400741b1  cmp     byte ptr [rbp+57h+var_88+2], r14b
0x1400741b5  jnz     short loc_1400741E8
0x1400741b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400741be  cmp     rcx, r12
0x1400741c1  jz      loc_140073EA7
0x1400741c7  cmp     byte ptr [rcx+29h], 3
  ... truncated ...
```
