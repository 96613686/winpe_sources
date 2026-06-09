# MRxSmbCreate

- ea: `0x140036d40`
- end: `0x14003777a`
- name: `MRxSmbCreate`
- size: `2618`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400381d0`

## callees

- `0x14000dc44`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e52c`
- `0x14000e694`
- `0x14000e708`
- `0x14000e998`
- `0x1400104d4`
- `0x140036d40`
- `0x140037780`
- `0x140043228`
- `0x140043c5c`
- `0x140044700`
- `0x140046120`
- `0x14004ab38`
- `0x14004b1b0`
- `0x14004d7f0`
- `0x14004dd50`
- `0x14004ef00`
- `0x14004f5e0`
- `0x1400507a0`
- `0x1400521e0`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x140036fdd`
- `ntoskrnl!ExAllocatePool2` at `0x14003707c`
- `ntoskrnl!ExAllocatePool2` at `0x140036fdd`
- `ntoskrnl!ExAllocatePool2` at `0x14003707c`
- `rdbss!RxProcessFcbChangeBufferingStateRequest` at `0x140037580`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x14003756a`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x14003756a`
- `rdbss!RxCreateNetFobx` at `0x1400371d9`
- `rdbss!RxCreateNetFobx` at `0x1400371d9`
- `mrxsmb!MRxSmbBootedRemotely` at `0x1400370fd`

## pseudocode

```c
__int64 __fastcall MRxSmbCreate(PRX_CONTEXT RxContext, __int64 a2, __int64 a3, __int64 a4)
{
  PMRX_FCB pFcb; // r12
  PSZ v5; // rdx
  __int64 v7; // r14
  PSZ FileName; // rsi
  ULONG PipeCompletionMode; // r15d
  int v10; // r13d
  PDEVICE_OBJECT v11; // rcx
  PSZ v12; // rax
  struct _LIST_ENTRY *v13; // r10
  char v14; // si
  unsigned int v15; // ebx
  PSZ v16; // rcx
  ULONGLONG ActualAllocationLength; // rcx
  __int64 Pool2; // rax
  _WORD *v20; // rdx
  PMRX_SRV_OPEN v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  _DWORD *v24; // rbx
  char IsStreamFile; // al
  PERESOURCE *v26; // rsi
  struct _MRX_FOBX_ *NetFobx; // rax
  char v28; // cl
  char v29; // r12
  __int64 v30; // rax
  bool v31; // bl
  int v32; // r14d
  PMRX_SRV_OPEN v33; // r13
  unsigned int OrdinaryExchange; // eax
  char IsFileNotFoundCached; // al
  int v36; // r14d
  _DWORD *v37; // rbx
  PMRX_FCB v38; // rsi
  PMRX_FCB v39; // rcx
  int v40; // eax
  int v41; // eax
  ULONG v42; // r15d
  ULONG v43; // r15d
  ULONG v44; // r15d
  ULONG v45; // r15d
  __int64 v46; // [rsp+20h] [rbp-49h]
  __int64 v47; // [rsp+28h] [rbp-41h]
  PMRX_SRV_OPEN MrxSrvOpen; // [rsp+30h] [rbp-39h]
  __int64 v49; // [rsp+38h] [rbp-31h]
  PVOID pContext; // [rsp+40h] [rbp-29h] BYREF
  PMRX_FCB v51; // [rsp+48h] [rbp-21h]
  struct _LIST_ENTRY *Flink; // [rsp+50h] [rbp-19h]
  char v53[104]; // [rsp+58h] [rbp-11h] BYREF
  PERESOURCE *p_Resource; // [rsp+D0h] [rbp+67h] BYREF
  int v55; // [rsp+D8h] [rbp+6Fh]
  int v56; // [rsp+E0h] [rbp+77h]
  int v57; // [rsp+E8h] [rbp+7Fh]

  pFcb = RxContext->pFcb;
  v5 = 0;
  v7 = *(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease;
  FileName = RxContext->TrackerHistory[0].FileName;
  PipeCompletionMode = RxContext->Create.PipeCompletionMode;
  MrxSrvOpen = RxContext->pRelevantSrvOpen;
  v49 = *(_QWORD *)(v7 + 32);
  v56 = 0;
  v51 = pFcb;
  v10 = *(_DWORD *)(v49 + 420);
  Flink = RxContext->OverflowListEntry.Flink;
  pContext = 0;
  p_Resource = &pFcb[2].Header.Resource;
  v55 = 0;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
    v5 = 0;
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 2) != 0 )
  {
    LODWORD(v46) = 0;
    LOBYTE(a4) = -76;
    McTemplateK0uq_EtwWriteTransfer(v11, 0, &RxContext->LowIoContext.Flags + 1, a4);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_Z(
      WPP_GLOBAL_Control->AttachedDevice,
      12,
      WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
      &pFcb[2].Header.Resource);
  v12 = RxContext->TrackerHistory[1].FileName;
  v13 = 0;
  if ( v12 && *((_DWORD *)v12 + 2) == 3 )
  {
    v14 = 0;
LABEL_12:
    v15 = -1073741311;
    goto LABEL_13;
  }
  ActualAllocationLength = pFcb->ActualAllocationLength;
  if ( !ActualAllocationLength )
  {
    Pool2 = ExAllocatePool2(256, 104, 1766223187);
    pFcb->ActualAllocationLength = Pool2;
    ActualAllocationLength = Pool2;
    if ( !Pool2 )
    {
      v15 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          13,
          WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
          pFcb,
          -1073741670);
      }
      v14 = 90;
      goto LABEL_26;
    }
  }
  v20 = (_WORD *)(ActualAllocationLength & ((unsigned __int128)-(__int128)(unsigned __int64)pFcb >> 64));
  *v20 = -4608;
  MRxSmbRetrieveSid((__int64)RxContext, v20 + 8);
  v21 = MrxSrvOpen;
  v13 = 0;
  v22 = *(_QWORD *)&MrxSrvOpen->Flags;
  if ( !v22 )
  {
    v23 = ExAllocatePool2(256, 176, 1766223187);
    v21 = MrxSrvOpen;
    v13 = 0;
    v22 = v23;
    *(_QWORD *)&MrxSrvOpen->Flags = v23;
    if ( !v23 )
    {
      v15 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          14,
          WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
          MrxSrvOpen,
          -1073741670);
      }
      v14 = 110;
      goto LABEL_26;
    }
  }
  v24 = (_DWORD *)(v22 & -(__int64)(v21 != 0));
  if ( (HIDWORD(pFcb->SrvOpenList.Flink) & 4) != 0 && !MRxSmbBootedRemotely )
  {
    v15 = -1073741822;
    v14 = 120;
    goto LABEL_26;
  }
  a4 = v49;
  if ( (*(_DWORD *)(v49 + 420) & 0x100000) == 0 )
  {
    IsStreamFile = MRxSmbIsStreamFile(&pFcb[2].Header.Resource, 0);
    v13 = 0;
    if ( IsStreamFile )
    {
      v15 = -1073741766;
      v14 = 0x80;
      goto LABEL_26;
    }
    v21 = MrxSrvOpen;
    a4 = v49;
  }
  if ( (*(_DWORD *)(a4 + 420) & 0x1000000) == 0 )
    *((_DWORD *)&RxContext->9 + 35) &= 0xFFFFFu;
  v5 = (PSZ)*((unsigned int *)&RxContext->9 + 28);
  v57 = v55;
  if ( ((unsigned __int8)v5 & 0x21) == 0 && ((unsigned __int8)v5 & 6) != 0 )
  {
    if ( !MRxSmbEnableCachingOnWriteOnlyOpens || RxContext->OverflowListEntry.Flink )
    {
      *v24 |= 0x10u;
      LODWORD(v21->Key) |= 2u;
    }
    else
    {
      v5 = (PSZ)((unsigned int)v5 | 0x81);
      *((_DWORD *)&RxContext->9 + 28) = (_DWORD)v5;
      RxContext->OverflowListEntry.Flink = (struct _LIST_ENTRY *)2863311530LL;
    }
  }
  if ( FileName[77] != 1 )
  {
    v26 = p_Resource;
LABEL_75:
    if ( v24[32] )
    {
      v29 = 0;
    }
    else
    {
      v10 = *(_DWORD *)(*(_QWORD *)(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease + 32LL) + 420LL);
      if ( RxContext->TrackerHistory[3].AcquireRelease
        || *(_DWORD *)&RxContext->TrackerHistory[3].SavedTrackerValue
        || (v28 = 0, LOWORD(RxContext->pFcb[2].Header.Resource) > 0x10ACu) )
      {
        v28 = 1;
      }
      v29 = (*(_DWORD *)(a4 + 420) & 0x40000) != 0 ? v28 : 0;
    }
    v30 = *(_QWORD *)(v7 + 32);
    v31 = 0;
    if ( v30 )
      v31 = *(_DWORD *)(v30 + 12) != 0;
    if ( RxContext->TrackerHistory[3].AcquireRelease && (v10 & 0x1000) == 0 )
    {
      v15 = -1073741637;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      {
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          16,
          WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
          a4,
          -1073741637);
        v13 = 0;
      }
      v14 = -41;
      goto LABEL_13;
    }
    v32 = 45;
    if ( LOWORD(RxContext->pFcb[2].Header.Resource)
      && (PipeCompletionMode <= 5 && _bittest(&v32, PipeCompletionMode)
       || _bittest((const signed __int32 *)&RxContext->9 + 28, 0x10u)
       || v31
       || v29) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
      }
      MRxSmbInvalidateFullDirectoryCacheParent((__int64)RxContext, 0);
    }
    if ( (*((_DWORD *)&RxContext->9 + 35) & 0x4000) != 0 )
      MRxSmbInvalidateFullDirectoryCacheParent((__int64)RxContext, 0);
    if ( PipeCompletionMode <= 5 && _bittest(&v32, PipeCompletionMode) )
    {
      if ( v31 || !v29 )
        goto LABEL_106;
    }
    else
    {
      if ( v31 )
        goto LABEL_106;
      if ( !v29 )
      {
        IsFileNotFoundCached = MRxSmbIsFileNotFoundCached((__int64)RxContext);
        v13 = 0;
        if ( IsFileNotFoundCached )
        {
          v15 = -1073741772;
          v56 = 12;
          v14 = 1;
          goto LABEL_13;
        }
        if ( LOWORD(RxContext->pFcb[2].Header.Resource) )
        {
          if ( !_bittest((const signed __int32 *)&RxContext->9 + 28, 0x10u) )
          {
            LOBYTE(p_Resource) = 0;
            if ( MRxSmbIsFileInFullDirectoryCache((__int64)RxContext, &p_Resource, (__int64)v53) )
            {
              if ( !(_BYTE)p_Resource )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                {
                  WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v26);
                }
                v36 = -1073741772;
                v56 = 12;
                v14 = 26;
                goto LABEL_122;
              }
            }
          }
        }
LABEL_106:
        v33 = MrxSrvOpen;
        OrdinaryExchange = _SmbPseCreateOrdinaryExchange(
                             (__int64)RxContext,
                             (__int64)MrxSrvOpen->ShadowContext,
                             12,
                             (__int64)SmbPseExchangeStart_Create,
                             v46,
                             (__int64 *)&pContext);
        v13 = 0;
        v15 = OrdinaryExchange;
        if ( OrdinaryExchange )
        {
          v14 = 44;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
            v13 = 0;
          }
LABEL_156:
          if ( v15 == -1073741623 )
          {
            v14 = -18;
            goto LABEL_20;
          }
LABEL_13:
          if ( !*(_BYTE *)(v49 + 507) && !*(_BYTE *)(v49 + 640) || !(unsigned __int8)SmbCeIsReconnectableError(v15) )
          {
LABEL_21:
            if ( Flink == v13 && RxContext->OverflowListEntry.Flink != v13 )
            {
              *((_DWORD *)&RxContext->9 + 28) &= 0xFFFFFF7E;
              if ( v15 == -1073741790 || v15 == -1073741757 )
              {
                v15 = -1069481983;
                v14 = 3;
              }
            }
            goto LABEL_26;
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v15);
            v13 = 0;
          }
          v14 = -9;
LABEL_20:
          v15 = -1069481983;
          goto LABEL_21;
        }
        v37 = pContext;
        v38 = v51;
        v39 = v51;
        *((_BYTE *)pContext + 564) = v29;
        v37[18] |= 0x1010u;
        *((_QWORD *)v37 + 15) = &RxContext->PrefixClaim.NetRootType;
        v37[104] = v55;
        *((_QWORD *)v37 + 56) = RxFcbGetOutstandingBufferingChangeEvent(v39);
        *((_QWORD *)v37 + 57) = RxProcessFcbChangeBufferingStateRequest;
        *((_QWORD *)v37 + 58) = v38;
        v14 = 73;
        v40 = SmbCeInitiateExchange(v37);
        *((_QWORD *)v37 + 15) = 0;
        v36 = v40;
        v55 = v37[104];
        SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)v37);
        if ( !v29 || v36 )
        {
LABEL_141:
          switch ( v36 )
          {
            case -1073741514:
              if ( PipeCompletionMode )
              {
                v42 = PipeCompletionMode - 1;
                if ( v42 )
                {
                  v43 = v42 - 1;
                  if ( !v43 )
                  {
                    v14 = -108;
                    v36 = -1073741771;
                    goto LABEL_155;
                  }
                  v44 = v43 - 1;
                  if ( !v44 )
                    goto LABEL_148;
                  v45 = v44 - 1;
                  if ( v45 )
                  {
                    if ( v45 != 1 )
                    {
LABEL_155:
                      MRxSmbInvalidateFileNotFoundCache((__int64)RxContext);
                      goto LABEL_123;
                    }
LABEL_148:
                    v14 = -83;
                    v36 = -1073741622;
                    goto LABEL_155;
                  }
                }
              }
              v14 = -96;
              v36 = -1073741772;
              break;
            case 0:
              MRxSmbInvalidateFileNotFoundCache((__int64)RxContext);
              v13 = 0;
              v15 = 0;
              LODWORD(v33->Key) |= 0x200000u;
              goto LABEL_13;
            case -1073741772:
            case -1073741766:
              break;
            default:
              goto LABEL_155;
          }
LABEL_122:
          MRxSmbCacheFileNotFound((__int64)RxContext);
          MRxSmbInvalidateInternalFileInfoCache((__int64)RxContext);
LABEL_123:
          v15 = v36;
          MRxSmbInvalidateFileInfoCache(RxContext);
          v13 = 0;
          goto LABEL_156;
        }
LABEL_128:
        if ( v57 != v55 )
        {
          *(_OWORD *)&RxContext->MRxContext[2] = 0;
          *(_OWORD *)&RxContext->WriteOnlyOpenRetryContext = 0;
          RxContext->ResumeRoutine = 0;
        }
        v14 = 102;
        SmbCeReconnect(*(PVOID *)(*(_QWORD *)&RxContext->TrackerHistory[0].Flags + 40LL));
        v13 = 0;
        v36 = v41;
        if ( !v41 )
        {
          v5 = RxContext->TrackerHistory[1].FileName;
          if ( v5 )
          {
            if ( ((*((_DWORD *)v5 + 2) - 2) & 0xFFFFFFFD) == 0
              && (*(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*(_QWORD *)&RxContext->TrackerHistory[0].Flags + 40LL)
                                                   + 96LL)
                                       + 64LL)
                           + 672LL)
                & 8) == 0 )
            {
              goto LABEL_12;
            }
            if ( (*((_DWORD *)v5 + 3) & 8) != 0 )
            {
              a4 = *(_QWORD *)(*(_QWORD *)(*(_QWORD *)&RxContext->TrackerHistory[0].Flags + 40LL) + 96LL);
              if ( !*(_BYTE *)(a4 + 381) )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
                {
                  WPP_SF_qq(
                    WPP_GLOBAL_Control->AttachedDevice,
                    20,
                    WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
                    a4,
                    RxContext);
                  v13 = 0;
                }
                v15 = -1073741311;
                goto LABEL_13;
              }
            }
          }
          v36 = MRxSmbCreateWithExtraOptions(RxContext);
        }
        goto LABEL_141;
      }
    }
    v33 = MrxSrvOpen;
    goto LABEL_128;
  }
  v26 = &pFcb[2].Header.Resource;
  if ( LOWORD(pFcb[2].Header.Resource) > 2u )
    goto LABEL_75;
  NetFobx = RxCreateNetFobx(RxContext, v21);
  RxContext->pFobx = NetFobx;
  if ( NetFobx )
  {
    *v24 |= 0x200u;
    v14 = -82;
    v15 = 0;
  }
  else
  {
    v15 = -1073741670;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        WPP_d95790c14120305e97e490eb33b089fe_Traceguids,
        MrxSrvOpen,
        -1073741670);
    v14 = -76;
  }
LABEL_26:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_d95790c14120305e97e490eb33b089fe_Traceguids, v15);
  v16 = RxContext->TrackerHistory[1].FileName;
  if ( v16 )
  {
    if ( ((*((_DWORD *)v16 + 2) - 2) & 0xFFFFFFFD) == 0 )
      *((_DWORD *)v16 + 5) = 2;
    v16 = RxContext->TrackerHistory[1].FileName;
    if ( (*((_DWORD *)v16 + 3) & 8) != 0 )
      *((_DWORD *)v16 + 6) |= 8u;
  }
  if ( (v15 & 0x80000000) != 0 && (Microsoft_Windows_SMBClientEnableBits & 1) != 0 )
  {
    LODWORD(v47) = v56;
    McTemplateK0qqq_EtwWriteTransfer((_DWORD)v16, (unsigned int)CreateFileError, (_DWORD)RxContext + 412, v15, v14, v47);
  }
  if ( (Microsoft_Windows_SMBClientEnableBits & 2) != 0 )
  {
    LOBYTE(a4) = -75;
    McTemplateK0uq_EtwWriteTransfer(v16, v5, &RxContext->LowIoContext.Flags + 1, a4);
  }
  return v15;
}

```

## disassembly

```asm
0x140036d40  push    rbp
0x140036d42  push    rbx
0x140036d43  push    rsi
0x140036d44  push    rdi
0x140036d45  push    r12
0x140036d47  push    r13
0x140036d49  push    r14
0x140036d4b  push    r15
0x140036d4d  lea     rbp, [rsp-1Fh]
0x140036d52  sub     rsp, 88h
0x140036d59  mov     r12, [rcx+38h]
0x140036d5d  xor     edx, edx
0x140036d5f  mov     r13, [rcx+48h]
0x140036d63  mov     rdi, rcx
0x140036d66  mov     r14, [rcx+280h]
0x140036d6d  mov     rsi, [rcx+288h]
0x140036d74  mov     r15d, [rcx+218h]
0x140036d7b  lea     rbx, [r12+168h]
0x140036d83  mov     [rbp+57h+MrxSrvOpen], r13
0x140036d87  mov     rax, [r14+20h]
0x140036d8b  mov     [rbp+57h+var_88], rax
0x140036d8f  mov     [rbp+57h+arg_10], edx
0x140036d92  mov     [rbp+57h+var_78], r12
0x140036d96  mov     r13d, [rax+1A4h]
0x140036d9d  mov     rax, [rcx+120h]
0x140036da4  mov     [rbp+57h+var_70], rax
0x140036da8  mov     [rbp+57h+pContext], rdx
0x140036dac  mov     [rbp+57h+arg_0], rbx
0x140036db0  mov     [rbp+57h+arg_8], edx
0x140036db3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036dba  lea     rax, WPP_GLOBAL_Control
0x140036dc1  cmp     rcx, rax
0x140036dc4  jz      short loc_140036DE6
0x140036dc6  test    dword ptr [rcx+2Ch], 400h
0x140036dcd  jz      short loc_140036DE6
0x140036dcf  mov     rcx, [rcx+18h]
0x140036dd3  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036dda  mov     edx, 0Bh
0x140036ddf  call    WPP_SF_
0x140036de4  xor     edx, edx
0x140036de6  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 2
0x140036ded  jz      short loc_140036E02
0x140036def  lea     r8, [rdi+19Ch]
0x140036df6  mov     dword ptr [rsp+0C0h+var_A0], edx
0x140036dfa  mov     r9b, 0B4h
0x140036dfd  call    McTemplateK0uq_EtwWriteTransfer
0x140036e02  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036e09  lea     rax, WPP_GLOBAL_Control
0x140036e10  cmp     rcx, rax
0x140036e13  jz      short loc_140036E36
0x140036e15  test    dword ptr [rcx+2Ch], 400h
0x140036e1c  jz      short loc_140036E36
0x140036e1e  mov     rcx, [rcx+18h]
0x140036e22  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036e29  mov     edx, 0Ch
0x140036e2e  mov     r9, rbx
0x140036e31  call    WPP_SF_Z
0x140036e36  mov     rax, [rdi+2A0h]
0x140036e3d  xor     r10d, r10d
0x140036e40  test    rax, rax
0x140036e43  jz      loc_140036FC0
0x140036e49  cmp     dword ptr [rax+8], 3
0x140036e4d  jnz     loc_140036FC0
0x140036e53  mov     esi, r10d
0x140036e56  mov     ebx, 0C0000201h
0x140036e5b  lea     r14, WPP_GLOBAL_Control
0x140036e62  mov     rax, [rbp+57h+var_88]
0x140036e66  cmp     [rax+1FBh], r10b
0x140036e6d  jnz     short loc_140036E78
0x140036e6f  cmp     [rax+280h], r10b
0x140036e76  jz      short loc_140036EBD
0x140036e78  mov     ecx, ebx
0x140036e7a  call    SmbCeIsReconnectableError
0x140036e7f  test    al, al
0x140036e81  jz      short loc_140036EBD
0x140036e83  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036e8a  cmp     rcx, r14
0x140036e8d  jz      short loc_140036EB3
0x140036e8f  test    dword ptr [rcx+2Ch], 400h
0x140036e96  jz      short loc_140036EB3
0x140036e98  mov     rcx, [rcx+18h]
0x140036e9c  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036ea3  mov     edx, 15h
0x140036ea8  mov     r9d, ebx
0x140036eab  call    WPP_SF_d
0x140036eb0  xor     r10d, r10d
0x140036eb3  mov     esi, 3F7h
0x140036eb8  mov     ebx, 0C0410001h
0x140036ebd  cmp     [rbp+57h+var_70], r10
0x140036ec1  jnz     short loc_140036EF0
0x140036ec3  cmp     [rdi+120h], r10
0x140036eca  jz      short loc_140036EF0
0x140036ecc  and     dword ptr [rdi+200h], 0FFFFFF7Eh
0x140036ed6  cmp     ebx, 0C0000022h
0x140036edc  jz      short loc_140036EE6
0x140036ede  cmp     ebx, 0C0000043h
0x140036ee4  jnz     short loc_140036EF0
0x140036ee6  mov     ebx, 0C0410001h
0x140036eeb  mov     esi, 403h
0x140036ef0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140036ef7  lea     rax, WPP_GLOBAL_Control
0x140036efe  cmp     rcx, rax
0x140036f01  jz      short loc_140036F24
0x140036f03  test    dword ptr [rcx+2Ch], 200h
0x140036f0a  jz      short loc_140036F24
0x140036f0c  mov     rcx, [rcx+18h]
0x140036f10  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140036f17  mov     edx, 16h
0x140036f1c  mov     r9d, ebx
0x140036f1f  call    WPP_SF_d
0x140036f24  mov     rcx, [rdi+2A0h]
0x140036f2b  mov     r14d, 2
0x140036f31  test    rcx, rcx
0x140036f34  jz      short loc_140036F59
0x140036f36  mov     eax, [rcx+8]
0x140036f39  sub     eax, r14d
0x140036f3c  test    eax, 0FFFFFFFDh
0x140036f41  jnz     short loc_140036F47
0x140036f43  mov     [rcx+14h], r14d
0x140036f47  mov     rcx, [rdi+2A0h]
0x140036f4e  mov     eax, [rcx+0Ch]
0x140036f51  test    al, 8
0x140036f53  jz      short loc_140036F59
0x140036f55  or      dword ptr [rcx+18h], 8
0x140036f59  test    ebx, ebx
0x140036f5b  jns     short loc_140036F8D
0x140036f5d  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, 1
0x140036f64  jz      short loc_140036F8D
0x140036f66  mov     eax, [rbp+57h+arg_10]
0x140036f69  lea     r8, [rdi+19Ch]
0x140036f70  or      esi, 10400000h
0x140036f76  mov     dword ptr [rsp+0C0h+var_98], eax
0x140036f7a  mov     r9d, ebx
0x140036f7d  mov     dword ptr [rsp+0C0h+var_A0], esi
0x140036f81  lea     rdx, CreateFileError
0x140036f88  call    McTemplateK0qqq_EtwWriteTransfer
0x140036f8d  test    byte ptr cs:Microsoft_Windows_SMBClientEnableBits, r14b
0x140036f94  jz      short loc_140036FA9
0x140036f96  lea     r8, [rdi+19Ch]
0x140036f9d  mov     dword ptr [rsp+0C0h+var_A0], ebx
0x140036fa1  mov     r9b, 0B5h
0x140036fa4  call    McTemplateK0uq_EtwWriteTransfer
0x140036fa9  mov     eax, ebx
0x140036fab  add     rsp, 88h
0x140036fb2  pop     r15
0x140036fb4  pop     r14
0x140036fb6  pop     r13
0x140036fb8  pop     r12
0x140036fba  pop     rdi
0x140036fbb  pop     rsi
0x140036fbc  pop     rbx
0x140036fbd  pop     rbp
0x140036fbe  retn
0x140036fc0  mov     rcx, [r12+88h]
0x140036fc8  mov     ebx, 69466D53h
0x140036fcd  test    rcx, rcx
0x140036fd0  jnz     short loc_140037044
0x140036fd2  lea     edx, [rcx+68h]
0x140036fd5  mov     r8d, ebx
0x140036fd8  mov     ecx, 100h
0x140036fdd  call    cs:__imp_ExAllocatePool2
0x140036fe4  nop     dword ptr [rax+rax+00h]
0x140036fe9  mov     [r12+88h], rax
0x140036ff1  mov     rcx, rax
0x140036ff4  test    rax, rax
0x140036ff7  jnz     short loc_140037044
0x140036ff9  mov     ebx, 0C000009Ah
0x140036ffe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140037005  lea     rax, WPP_GLOBAL_Control
0x14003700c  cmp     rcx, rax
0x14003700f  jz      short loc_14003703A
0x140037011  test    dword ptr [rcx+2Ch], 100h
0x140037018  jz      short loc_14003703A
0x14003701a  mov     rcx, [rcx+18h]
0x14003701e  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140037025  mov     edx, 0Dh
0x14003702a  mov     dword ptr [rsp+0C0h+var_A0], 0C000009Ah
0x140037032  mov     r9, r12
0x140037035  call    WPP_SF_qD
0x14003703a  mov     esi, 25Ah
0x14003703f  jmp     loc_140036EF0
0x140037044  mov     rax, r12
0x140037047  neg     rax
0x14003704a  sbb     rdx, rdx
0x14003704d  and     rdx, rcx
0x140037050  mov     rcx, rdi
0x140037053  mov     word ptr [rdx], 0EE00h
0x140037058  add     rdx, 10h
0x14003705c  call    MRxSmbRetrieveSid
0x140037061  mov     r8, [rbp+57h+MrxSrvOpen]
0x140037065  xor     r10d, r10d
0x140037068  mov     rcx, [r8+30h]
0x14003706c  test    rcx, rcx
0x14003706f  jnz     short loc_1400370E5
0x140037071  mov     edx, 0B0h
0x140037076  mov     r8d, ebx
0x140037079  lea     ecx, [rdx+50h]
0x14003707c  call    cs:__imp_ExAllocatePool2
0x140037083  nop     dword ptr [rax+rax+00h]
0x140037088  mov     r8, [rbp+57h+MrxSrvOpen]
0x14003708c  xor     r10d, r10d
0x14003708f  mov     rcx, rax
0x140037092  mov     [r8+30h], rax
0x140037096  test    rax, rax
0x140037099  jnz     short loc_1400370E5
0x14003709b  mov     ebx, 0C000009Ah
0x1400370a0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400370a7  lea     rax, WPP_GLOBAL_Control
0x1400370ae  cmp     rcx, rax
0x1400370b1  jz      short loc_1400370DB
0x1400370b3  test    dword ptr [rcx+2Ch], 100h
0x1400370ba  jz      short loc_1400370DB
0x1400370bc  mov     rcx, [rcx+18h]
0x1400370c0  lea     edx, [r10+0Eh]
0x1400370c4  mov     r9, r8
0x1400370c7  mov     dword ptr [rsp+0C0h+var_A0], 0C000009Ah
0x1400370cf  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400370d6  call    WPP_SF_qD
0x1400370db  mov     esi, 26Eh
0x1400370e0  jmp     loc_140036EF0
0x1400370e5  mov     rax, r8
0x1400370e8  neg     rax
0x1400370eb  mov     eax, [r12+9Ch]
0x1400370f3  sbb     rbx, rbx
0x1400370f6  and     rbx, rcx
0x1400370f9  test    al, 4
0x1400370fb  jz      short loc_140037118
0x1400370fd  mov     rax, cs:__imp_MRxSmbBootedRemotely
0x140037104  cmp     [rax], r10b
0x140037107  jnz     short loc_140037118
0x140037109  mov     ebx, 0C0000002h
0x14003710e  mov     esi, 278h
0x140037113  jmp     loc_140036EF0
0x140037118  mov     r9, [rbp+57h+var_88]
0x14003711c  test    dword ptr [r9+1A4h], 100000h
0x140037127  jnz     short loc_140037156
0x140037129  xor     edx, edx
0x14003712b  lea     rcx, [r12+168h]
0x140037133  call    MRxSmbIsStreamFile
0x140037138  xor     r10d, r10d
0x14003713b  test    al, al
0x14003713d  jz      short loc_14003714E
0x14003713f  mov     ebx, 0C000003Ah
0x140037144  mov     esi, 280h
0x140037149  jmp     loc_140036EF0
0x14003714e  mov     r8, [rbp+57h+MrxSrvOpen]
0x140037152  mov     r9, [rbp+57h+var_88]
0x140037156  test    dword ptr [r9+1A4h], 1000000h
0x140037161  jnz     short loc_14003716D
0x140037163  and     dword ptr [rdi+21Ch], 0FFFFFh
0x14003716d  mov     edx, [rdi+200h]
0x140037173  test    dl, 21h
0x140037176  mov     eax, [rbp+57h+arg_8]
0x140037179  setz    cl
0x14003717c  mov     [rbp+57h+arg_18], eax
0x14003717f  test    dl, 6
0x140037182  setnz   al
0x140037185  test    al, cl
0x140037187  jz      short loc_1400371B3
0x140037189  cmp     cs:MRxSmbEnableCachingOnWriteOnlyOpens, r10b
0x140037190  jz      short loc_140037202
0x140037192  cmp     [rdi+120h], r10
0x140037199  jnz     short loc_140037202
0x14003719b  or      edx, 81h
0x1400371a1  mov     eax, 0AAAAAAAAh
0x1400371a6  mov     [rdi+200h], edx
0x1400371ac  mov     [rdi+120h], rax
0x1400371b3  mov     eax, 2
0x1400371b8  cmp     byte ptr [rsi+4Dh], 1
0x1400371bc  jnz     loc_14003725C
0x1400371c2  lea     rsi, [r12+168h]
0x1400371ca  cmp     [rsi], ax
0x1400371cd  ja      loc_140037260
0x1400371d3  mov     rdx, r8; MrxSrvOpen
0x1400371d6  mov     rcx, rdi; RxContext
0x1400371d9  call    cs:__imp_RxCreateNetFobx
0x1400371e0  nop     dword ptr [rax+rax+00h]
0x1400371e5  xor     r10d, r10d
0x1400371e8  mov     [rdi+40h], rax
0x1400371ec  test    rax, rax
0x1400371ef  jz      short loc_140037210
0x1400371f1  bts     dword ptr [rbx], 9
0x1400371f5  mov     esi, 2AEh
0x1400371fa  mov     ebx, r10d
0x1400371fd  jmp     loc_140036EF0
0x140037202  or      dword ptr [rbx], 10h
0x140037205  mov     eax, 2
0x14003720a  or      [r8+48h], eax
0x14003720e  jmp     short loc_1400371B8
0x140037210  mov     ebx, 0C000009Ah
0x140037215  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14003721c  lea     rax, WPP_GLOBAL_Control
0x140037223  cmp     rcx, rax
0x140037226  jz      short loc_140037252
0x140037228  test    dword ptr [rcx+2Ch], 100h
0x14003722f  jz      short loc_140037252
0x140037231  mov     r9, [rbp+57h+MrxSrvOpen]
0x140037235  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x14003723c  mov     rcx, [rcx+18h]
0x140037240  mov     edx, 0Fh
  ... truncated ...
```
