# ExtSTABootup(_VELAN *,void *,void * *)

- ea: `0x1400210c8`
- end: `0x140021618`
- name: `?ExtSTABootup@@YAHPEAU_VELAN@@PEAXPEAPEAX@Z`
- size: `1360`
- prototype: `__int64 __fastcall(struct _VELAN *, void *, void **)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036c48`

## callees

- `0x14000d22c`
- `0x140019bbc`
- `0x140020dc0`
- `0x1400210c8`
- `0x140021620`
- `0x140063bdc`
- `0x140063f00`
- `0x140064584`
- `0x1400648dc`
- `0x140065140`
- `0x140065214`
- `0x140065530`
- `0x140065ed4`
- `0x140079e34`
- `0x14007a964`
- `0x14009a3d0`
- `0x14009a7c0`
- `0x1400b9ff4`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002121d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x14002121d`
- `ntoskrnl!ExAllocatePool2` at `0x140021238`
- `ntoskrnl!ExAllocatePool2` at `0x140021238`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400213fe`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400213fe`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021415`
- `ntoskrnl!ExFreePoolWithTag` at `0x140021415`
- `NETIO!NotifyUnicastIpAddressChange` at `0x140021565`
- `NETIO!NotifyUnicastIpAddressChange` at `0x140021565`
- `NETIO!CancelMibChangeNotify2` at `0x1400213cf`
- `NETIO!CancelMibChangeNotify2` at `0x1400213cf`

## pseudocode

```c
__int64 __fastcall ExtSTABootup(struct _VELAN *a1, void *a2, struct EXTSTA_VELAN **a3)
{
  _ADAPT *pAdapt; // rcx
  int v6; // eax
  unsigned int RawData; // eax
  unsigned int v8; // edi
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rdx
  __int64 v11; // r9
  unsigned int v12; // edi
  unsigned int v13; // eax
  struct _NPAGED_LOOKASIDE_LIST *p_DeviceQueue; // rbx
  _DWORD *Pool2; // rax
  PNPAGED_LOOKASIDE_LIST *v16; // rsi
  struct EXTSTA_VELAN *v17; // rbx
  DOT11_STATISTICS *v18; // rdx
  int v19; // eax
  __int64 v20; // rcx
  DOT11_STATISTICS *v21; // rdx
  unsigned int v22; // eax
  struct _WFD_ROLE **p_pWFDRole; // r15
  void *hIfChangeNotificationHandle; // rcx
  DOT11_EXTSTA_ATTRIBUTES *ExtSTAAttributes; // rax
  unsigned int uMaxNetworkOffloadListSize; // edx
  _ADAPT *v27; // rcx
  bool v28; // al
  DOT11_EXTSTA_ATTRIBUTES *v29; // rax
  unsigned int ULong; // eax
  unsigned int v31; // eax
  char *v33; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v34; // [rsp+38h] [rbp-C8h] BYREF
  _DWORD v35[192]; // [rsp+40h] [rbp-C0h] BYREF

  v34 = 0;
  memset(v35, 0, sizeof(v35));
  pAdapt = a1->pAdapt;
  v6 = 4;
  if ( pAdapt->uConfiguredOpMode == 64 )
    v6 = 64;
  HIDWORD(v34) = v6;
  RawData = PtRequestAdapterSync(pAdapt, 1u, 0xD010308u, &v34, 8u);
  v8 = RawData;
  if ( RawData )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
    {
LABEL_58:
      v17 = 0;
      goto LABEL_59;
    }
    v10 = 17;
LABEL_6:
    WPP_SF_d(v9->AttachedDevice, v10, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids, RawData);
    goto LABEL_58;
  }
  RawData = QueryRawData(a1->pAdapt, v35);
  v8 = RawData;
  if ( RawData )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      goto LABEL_58;
    v10 = 18;
    goto LABEL_6;
  }
  v12 = v35[1] + v35[2] + v35[0] + 2752;
  v13 = v12 + 16;
  if ( v12 >= 0xFFFFFFF0 )
  {
LABEL_56:
    v8 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids);
    goto LABEL_58;
  }
  if ( v13 <= 0x40 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
LABEL_19:
    Pool2 = ExAllocateFromNPagedLookasideList(p_DeviceQueue);
    goto LABEL_21;
  }
  if ( v13 <= 0x100 )
  {
    p_DeviceQueue = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
    goto LABEL_19;
  }
  if ( v13 <= 0x400 )
  {
    p_DeviceQueue = &Lookaside;
    goto LABEL_19;
  }
  if ( v13 <= 0x800 )
  {
    p_DeviceQueue = &stru_1400B0180;
    goto LABEL_19;
  }
  p_DeviceQueue = 0;
  Pool2 = (_DWORD *)ExAllocatePool2(64, v13, 828470387, v11);
LABEL_21:
  v16 = (PNPAGED_LOOKASIDE_LIST *)Pool2;
  if ( !Pool2 )
    goto LABEL_56;
  *(_QWORD *)Pool2 = p_DeviceQueue;
  v17 = (struct EXTSTA_VELAN *)(Pool2 + 4);
  Pool2[2] = 828470387;
  memset(Pool2 + 4, 0, v12);
  v33 = (char *)&v17[1];
  ExtSTASetPerftrackInfo(&v17->PerftrackInfo, 0);
  InitRoS(v35, &v17->RoS, &v33);
  v18 = (DOT11_STATISTICS *)v33;
  v17->RoD.uSizeOfStatistics = v35[191];
  v19 = v35[190];
  v17->RoD.pStatistics = v18;
  v20 = (144 * v19 + 263) & 0xFFFFFFF8;
  v21 = (DOT11_STATISTICS *)((char *)v18 + v20);
  v17->RoD.pBaseStatistics = v21;
  v33 = (char *)(&v21->Header.Type + v20);
  InitRw(v35, &v17->Rw, &v33);
  v17->Rw.uRequestedPowerMgmtMode = a1->uRequestedPowerMgmtMode;
  v17->pGenVElan = a1;
  a1->bInitState = 1;
  *(_DWORD *)&v17->RoD &= ~1u;
  v17->ModuleStatus.uValue = 0;
  v22 = ExtSTAInitialize(v17);
  v8 = v22;
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids, v22);
    p_pWFDRole = &v17->pWFDRole;
LABEL_30:
    hIfChangeNotificationHandle = v17->hIfChangeNotificationHandle;
    if ( hIfChangeNotificationHandle )
    {
      CancelMibChangeNotify2(hIfChangeNotificationHandle);
      v17->hIfChangeNotificationHandle = 0;
    }
    if ( *p_pWFDRole )
      WFDRoleDeInitialize(*p_pWFDRole);
    if ( *v16 )
      ExFreeToNPagedLookasideList(*v16, v16);
    else
      ExFreePoolWithTag(v16, *((_DWORD *)v16 + 2));
    goto LABEL_58;
  }
  if ( a1->pAdapt->uConfiguredOpMode == 64 )
  {
    p_pWFDRole = &v17->pWFDRole;
    v8 = WFDRoleInitialize(a1, a1->hMiniport, WFD_ROLE_TYPE_CLIENT, &v17->pWFDRole);
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids);
      goto LABEL_30;
    }
  }
  ExtSTAAttributes = a1->pAdapt->pNwfAttrs->ExtSTAAttributes;
  if ( ExtSTAAttributes->Header.Revision >= 3u )
  {
    v17->RoD.bAutoPowerSaveMode = ExtSTAAttributes->bAutoPowerSaveMode;
    uMaxNetworkOffloadListSize = a1->pAdapt->pNwfAttrs->ExtSTAAttributes->uMaxNetworkOffloadListSize;
    v17->RoD.uMaxNetworkOffloadListSize = uMaxNetworkOffloadListSize;
    v27 = v17->pGenVElan->pAdapt;
    v28 = v27->PmCapabilities.Header.Revision == 2
       && (v27->PmCapabilities.SupportedWoLPacketPatterns & 1) != 0
       && v27->PmCapabilities.NumTotalWoLPatterns >= 0x10
       && v27->PmCapabilities.MaxWoLPatternSize >= 0x4A
       && (unsigned int)(v27->PmCapabilities.MinPatternWakeUp - 3) <= 1
       && (v27->PmCapabilities.MediaSpecificWakeUpEvents & 3) == 3
       && (v27->PmCapabilities.SupportedProtocolOffloads & 3) == 3
       && uMaxNetworkOffloadListSize >= 0xA;
    v17->bAOACSupported = v28;
  }
  v17->bAutoPowerSaveSentToNic = 0;
  iReportNicAOACCompliance(v17, 1u);
  v17->RoD.bMFPCapable = 0;
  v29 = a1->pAdapt->pNwfAttrs->ExtSTAAttributes;
  if ( v29->Header.Revision >= 3u )
    v17->RoD.bMFPCapable = v29->bMFPCapable;
  ExtSTAInitPmSettings(v17);
  ExtSTAReadAPSDCheckRegKey(v17);
  ULong = Dot11ReadULong(WPP_MAIN_CB.Queue.Wcb.CurrentIrp, (unsigned int)L"ConnectScanDropTime", 30, 0, 120);
  v17->SecondsToSkipScanForIPAddress = ULong;
  if ( ULong )
  {
    v31 = NotifyUnicastIpAddressChange(
            0,
            ExtSTAUnicastIpAddressChangeCallback,
            v17,
            0,
            &v17->hIfChangeNotificationHandle);
    if ( v31 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids, v31);
      v17->SecondsToSkipScanForIPAddress = 0;
    }
  }
LABEL_59:
  *a3 = v17;
  FreeRawData(v35);
  return v8;
}

```

## disassembly

```asm
0x1400210c8  mov     [rsp-8+arg_8], rbx
0x1400210cd  mov     [rsp-8+arg_18], rsi
0x1400210d2  push    rbp
0x1400210d3  push    rdi
0x1400210d4  push    r12
0x1400210d6  push    r14
0x1400210d8  push    r15
0x1400210da  lea     rbp, [rsp-250h]
0x1400210e2  sub     rsp, 350h
0x1400210e9  mov     rax, cs:__security_cookie
0x1400210f0  xor     rax, rsp
0x1400210f3  mov     [rbp+270h+var_30], rax
0x1400210fa  mov     r12, r8
0x1400210fd  mov     [rsp+370h+var_338], 0
0x140021106  mov     r14, rcx
0x140021109  mov     r8d, 300h; Size
0x14002110f  lea     rcx, [rsp+370h+var_330]; void *
0x140021114  xor     edx, edx; Val
0x140021116  call    memset
0x14002111b  mov     rcx, [r14+10h]; struct _ADAPT *
0x14002111f  lea     r9, [rsp+370h+var_338]; void *
0x140021124  mov     eax, 4
0x140021129  mov     dword ptr [rsp+370h+NotificationHandle], 8; unsigned int
0x140021131  mov     r8d, 0D010308h; unsigned int
0x140021137  lea     r15d, [rax+3Ch]
0x14002113b  cmp     [rcx+118h], r15d
0x140021142  lea     edx, [r15-3Fh]; unsigned int
0x140021146  cmovz   eax, r15d
0x14002114a  mov     dword ptr [rsp+370h+var_338+4], eax
0x14002114e  call    ?PtRequestAdapterSync@@YAHPEAU_ADAPT@@KKPEAXK@Z; PtRequestAdapterSync(_ADAPT *,ulong,ulong,void *,ulong)
0x140021153  mov     edi, eax
0x140021155  test    eax, eax
0x140021157  jz      short loc_14002118C
0x140021159  mov     rcx, cs:WPP_GLOBAL_Control
0x140021160  lea     rdx, WPP_GLOBAL_Control
0x140021167  cmp     rcx, rdx
0x14002116a  jz      loc_1400215DA
0x140021170  lea     edx, [r15-2Fh]
0x140021174  mov     rcx, [rcx+18h]
0x140021178  lea     r8, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids
0x14002117f  mov     r9d, eax
0x140021182  call    WPP_SF_d
0x140021187  jmp     loc_1400215DA
0x14002118c  mov     rcx, [r14+10h]
0x140021190  lea     rdx, [rsp+370h+var_330]
0x140021195  call    QueryRawData
0x14002119a  mov     edi, eax
0x14002119c  test    eax, eax
0x14002119e  jz      short loc_1400211BE
0x1400211a0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400211a7  lea     rdx, WPP_GLOBAL_Control
0x1400211ae  cmp     rcx, rdx
0x1400211b1  jz      loc_1400215DA
0x1400211b7  mov     edx, 12h
0x1400211bc  jmp     short loc_140021174
0x1400211be  mov     edx, [rsp+370h+var_328]
0x1400211c2  add     edx, [rsp+370h+var_32C]
0x1400211c6  mov     edi, [rsp+370h+var_330]
0x1400211ca  add     edi, 0AC0h
0x1400211d0  add     edi, edx
0x1400211d2  lea     eax, [rdi+10h]
0x1400211d5  cmp     eax, 10h
0x1400211d8  jb      loc_1400215AD
0x1400211de  cmp     eax, r15d
0x1400211e1  ja      short loc_1400211EC
0x1400211e3  lea     rbx, WPP_MAIN_CB.DeviceQueue
0x1400211ea  jmp     short loc_14002121A
0x1400211ec  cmp     eax, 100h
0x1400211f1  ja      short loc_1400211FC
0x1400211f3  lea     rbx, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x1400211fa  jmp     short loc_14002121A
0x1400211fc  cmp     eax, 400h
0x140021201  ja      short loc_14002120C
0x140021203  lea     rbx, Lookaside
0x14002120a  jmp     short loc_14002121A
0x14002120c  cmp     eax, 800h
0x140021211  ja      short loc_14002122B
0x140021213  lea     rbx, stru_1400B0180
0x14002121a  mov     rcx, rbx; Lookaside
0x14002121d  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140021224  nop     dword ptr [rax+rax+00h]
0x140021229  jmp     short loc_140021244
0x14002122b  xor     ebx, ebx
0x14002122d  mov     edx, eax
0x14002122f  mov     r8d, 31617473h
0x140021235  mov     rcx, r15
0x140021238  call    cs:__imp_ExAllocatePool2
0x14002123f  nop     dword ptr [rax+rax+00h]
0x140021244  mov     rsi, rax
0x140021247  test    rax, rax
0x14002124a  jz      loc_1400215AD
0x140021250  mov     [rax], rbx
0x140021253  xor     edx, edx; Val
0x140021255  lea     rbx, [rax+10h]
0x140021259  mov     r8d, edi; Size
0x14002125c  mov     rcx, rbx; void *
0x14002125f  mov     dword ptr [rax+8], 31617473h
0x140021266  call    memset
0x14002126b  lea     rax, [rbx+0AC0h]
0x140021272  xor     edx, edx; int
0x140021274  lea     rcx, [rbx+608h]; struct EXTSTA_PERFTRACK_INFO *
0x14002127b  mov     [rsp+370h+var_340], rax
0x140021280  call    ?ExtSTASetPerftrackInfo@@YAXPEAUEXTSTA_PERFTRACK_INFO@@H@Z; ExtSTASetPerftrackInfo(EXTSTA_PERFTRACK_INFO *,int)
0x140021285  lea     rdx, [rbx+728h]
0x14002128c  lea     r8, [rsp+370h+var_340]
0x140021291  lea     rcx, [rsp+370h+var_330]
0x140021296  call    InitRoS
0x14002129b  mov     rdx, [rsp+370h+var_340]
0x1400212a0  lea     r8, [rsp+370h+var_340]
0x1400212a5  mov     eax, [rbp+270h+var_34]
0x1400212ab  mov     [rbx+684h], eax
0x1400212b1  mov     eax, [rbp+270h+var_38]
0x1400212b7  mov     [rbx+688h], rdx
0x1400212be  lea     ecx, [rax+rax*8]
0x1400212c1  mov     eax, 0FFFFFFF8h
0x1400212c6  shl     ecx, 4
0x1400212c9  add     ecx, 107h
0x1400212cf  and     rcx, rax
0x1400212d2  add     rdx, rcx
0x1400212d5  mov     [rbx+690h], rdx
0x1400212dc  lea     rax, [rcx+rdx]
0x1400212e0  lea     rdx, [rbx+6B8h]
0x1400212e7  mov     [rsp+370h+var_340], rax
0x1400212ec  lea     rcx, [rsp+370h+var_330]
0x1400212f1  call    InitRw
0x1400212f6  mov     eax, [r14+1F94h]
0x1400212fd  mov     rcx, rbx; struct EXTSTA_VELAN *
0x140021300  mov     [rbx+6F4h], eax
0x140021306  mov     [rbx+0A38h], r14
0x14002130d  mov     dword ptr [r14+15F0h], 1
0x140021318  and     dword ptr [rbx+610h], 0FFFFFFFEh
0x14002131f  mov     dword ptr [rbx], 0
0x140021325  call    ExtSTAInitialize
0x14002132a  mov     edi, eax
0x14002132c  test    eax, eax
0x14002132e  jz      short loc_140021364
0x140021330  mov     rcx, cs:WPP_GLOBAL_Control
0x140021337  lea     rdx, WPP_GLOBAL_Control
0x14002133e  cmp     rcx, rdx
0x140021341  jz      short loc_14002135B
0x140021343  mov     rcx, [rcx+18h]
0x140021347  lea     r8, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids
0x14002134e  mov     edx, 14h
0x140021353  mov     r9d, eax
0x140021356  call    WPP_SF_d
0x14002135b  lea     r15, [rbx+0A40h]
0x140021362  jmp     short loc_1400213C3
0x140021364  mov     rax, [r14+10h]
0x140021368  cmp     [rax+118h], r15d
0x14002136f  jnz     loc_140021426
0x140021375  mov     rdx, [r14+20h]; void *
0x140021379  lea     r15, [rbx+0A40h]
0x140021380  mov     r9, r15; struct _WFD_ROLE **
0x140021383  mov     r8d, 4; enum _WFD_ROLE_TYPE
0x140021389  mov     rcx, r14; struct _VELAN *
0x14002138c  call    ?WFDRoleInitialize@@YAHPEAU_VELAN@@PEAXW4_WFD_ROLE_TYPE@@PEAPEAU_WFD_ROLE@@@Z; WFDRoleInitialize(_VELAN *,void *,_WFD_ROLE_TYPE,_WFD_ROLE * *)
0x140021391  mov     edi, eax
0x140021393  test    eax, eax
0x140021395  jz      loc_140021426
0x14002139b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400213a2  lea     rdx, WPP_GLOBAL_Control
0x1400213a9  cmp     rcx, rdx
0x1400213ac  jz      short loc_1400213C3
0x1400213ae  mov     rcx, [rcx+18h]
0x1400213b2  lea     r8, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids
0x1400213b9  mov     edx, 15h
0x1400213be  call    WPP_SF_
0x1400213c3  mov     rcx, [rbx+0A68h]; NotificationHandle
0x1400213ca  test    rcx, rcx
0x1400213cd  jz      short loc_1400213E6
0x1400213cf  call    cs:__imp_CancelMibChangeNotify2
0x1400213d6  nop     dword ptr [rax+rax+00h]
0x1400213db  mov     qword ptr [rbx+0A68h], 0
0x1400213e6  mov     rcx, [r15]; struct _WFD_ROLE *
0x1400213e9  test    rcx, rcx
0x1400213ec  jz      short loc_1400213F3
0x1400213ee  call    ?WFDRoleDeInitialize@@YAXPEAU_WFD_ROLE@@@Z; WFDRoleDeInitialize(_WFD_ROLE *)
0x1400213f3  mov     rcx, [rsi]; Lookaside
0x1400213f6  test    rcx, rcx
0x1400213f9  jz      short loc_14002140F
0x1400213fb  mov     rdx, rsi; Entry
0x1400213fe  call    cs:__imp_ExFreeToNPagedLookasideList
0x140021405  nop     dword ptr [rax+rax+00h]
0x14002140a  jmp     loc_1400215DA
0x14002140f  mov     edx, [rsi+8]; Tag
0x140021412  mov     rcx, rsi; P
0x140021415  call    cs:__imp_ExFreePoolWithTag
0x14002141c  nop     dword ptr [rax+rax+00h]
0x140021421  jmp     loc_1400215DA
0x140021426  mov     rax, [r14+10h]
0x14002142a  mov     esi, 3
0x14002142f  mov     rcx, [rax+18h]
0x140021433  mov     rax, [rcx+20h]
0x140021437  cmp     [rax+1], sil
0x14002143b  jb      loc_1400214CD
0x140021441  mov     al, [rax+80h]
0x140021447  mov     [rbx+6A8h], al
0x14002144d  mov     rax, [r14+10h]
0x140021451  mov     rcx, [rax+18h]
0x140021455  mov     rax, [rcx+20h]
0x140021459  mov     edx, [rax+84h]
0x14002145f  mov     [rbx+6ACh], edx
0x140021465  mov     rax, [rbx+0A38h]
0x14002146c  mov     rcx, [rax+10h]
0x140021470  cmp     byte ptr [rcx+3D9h], 2
0x140021477  jnz     short loc_1400214C5
0x140021479  mov     eax, [rcx+3E0h]
0x14002147f  test    al, 1
0x140021481  jz      short loc_1400214C5
0x140021483  cmp     dword ptr [rcx+3E4h], 10h
0x14002148a  jb      short loc_1400214C5
0x14002148c  cmp     dword ptr [rcx+3E8h], 4Ah ; 'J'
0x140021493  jb      short loc_1400214C5
0x140021495  mov     eax, [rcx+404h]
0x14002149b  sub     eax, esi
0x14002149d  cmp     eax, 1
0x1400214a0  ja      short loc_1400214C5
0x1400214a2  mov     eax, [rcx+410h]
0x1400214a8  and     eax, esi
0x1400214aa  cmp     al, sil
0x1400214ad  jnz     short loc_1400214C5
0x1400214af  mov     eax, [rcx+3F4h]
0x1400214b5  and     eax, esi
0x1400214b7  cmp     al, sil
0x1400214ba  jnz     short loc_1400214C5
0x1400214bc  cmp     edx, 0Ah
0x1400214bf  jb      short loc_1400214C5
0x1400214c1  mov     al, 1
0x1400214c3  jmp     short loc_1400214C7
0x1400214c5  xor     eax, eax
0x1400214c7  mov     [rbx+0A4Ch], al
0x1400214cd  mov     dl, 1; unsigned __int8
0x1400214cf  mov     dword ptr [rbx+0A50h], 0
0x1400214d9  mov     rcx, rbx; struct EXTSTA_VELAN *
0x1400214dc  call    ?iReportNicAOACCompliance@@YAXPEAUEXTSTA_VELAN@@E@Z; iReportNicAOACCompliance(EXTSTA_VELAN *,uchar)
0x1400214e1  mov     byte ptr [rbx+6B0h], 0
0x1400214e8  mov     rax, [r14+10h]
0x1400214ec  mov     rcx, [rax+18h]
0x1400214f0  mov     rax, [rcx+20h]
0x1400214f4  cmp     [rax+1], sil
0x1400214f8  jb      short loc_140021506
0x1400214fa  mov     al, [rax+88h]
0x140021500  mov     [rbx+6B0h], al
0x140021506  mov     rcx, rbx
0x140021509  call    ExtSTAInitPmSettings
0x14002150e  mov     rcx, rbx
0x140021511  call    ExtSTAReadAPSDCheckRegKey
0x140021516  mov     rcx, qword ptr cs:WPP_MAIN_CB.Queue+38h
0x14002151d  lea     rdx, aConnectscandro; "ConnectScanDropTime"
0x140021524  xor     r9d, r9d
0x140021527  mov     dword ptr [rsp+370h+NotificationHandle], 78h ; 'x'
0x14002152f  lea     r8d, [r9+1Eh]
0x140021533  call    Dot11ReadULong
0x140021538  mov     eax, eax
0x14002153a  mov     [rbx+0A78h], rax
0x140021541  test    rax, rax
0x140021544  jz      loc_1400215DC
0x14002154a  lea     rax, [rbx+0A68h]
0x140021551  xor     ecx, ecx; Family
0x140021553  xor     r9d, r9d; InitialNotification
0x140021556  mov     [rsp+370h+NotificationHandle], rax; NotificationHandle
0x14002155b  mov     r8, rbx; CallerContext
0x14002155e  lea     rdx, ?ExtSTAUnicastIpAddressChangeCallback@@YAXPEAXPEAU_MIB_UNICASTIPADDRESS_ROW@@W4_MIB_NOTIFICATION_TYPE@@@Z; Callback
0x140021565  call    cs:__imp_NotifyUnicastIpAddressChange
0x14002156c  nop     dword ptr [rax+rax+00h]
0x140021571  test    eax, eax
0x140021573  jz      short loc_1400215DC
0x140021575  mov     rcx, cs:WPP_GLOBAL_Control
0x14002157c  lea     rdx, WPP_GLOBAL_Control
0x140021583  cmp     rcx, rdx
0x140021586  jz      short loc_1400215A0
0x140021588  mov     rcx, [rcx+18h]
0x14002158c  lea     r8, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids
0x140021593  mov     edx, 16h
0x140021598  mov     r9d, eax
0x14002159b  call    WPP_SF_d
0x1400215a0  mov     qword ptr [rbx+0A78h], 0
0x1400215ab  jmp     short loc_1400215DC
0x1400215ad  mov     edi, 0C000009Ah
0x1400215b2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400215b9  lea     rdx, WPP_GLOBAL_Control
0x1400215c0  cmp     rcx, rdx
0x1400215c3  jz      short loc_1400215DA
0x1400215c5  mov     rcx, [rcx+18h]
0x1400215c9  lea     r8, WPP_d959abdf45013e0130d255b0dfbf5ac4_Traceguids
0x1400215d0  mov     edx, 13h
0x1400215d5  call    WPP_SF_
0x1400215da  xor     ebx, ebx
0x1400215dc  lea     rcx, [rsp+370h+var_330]
0x1400215e1  mov     [r12], rbx
0x1400215e5  call    FreeRawData
0x1400215ea  mov     eax, edi
0x1400215ec  mov     rcx, [rbp+270h+var_30]
0x1400215f3  xor     rcx, rsp; StackCookie
0x1400215f6  call    __security_check_cookie
0x1400215fb  lea     r11, [rsp+370h+var_20]
0x140021603  mov     rbx, [r11+38h]
0x140021607  mov     rsi, [r11+48h]
0x14002160b  mov     rsp, r11
0x14002160e  pop     r15
  ... truncated ...
```
