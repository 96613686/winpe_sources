# SmbPseExchangeStart_Write

- ea: `0x140044c70`
- end: `0x140045882`
- name: `SmbPseExchangeStart_Write`
- size: `3090`
- prototype: `__int64 __fastcall(PVOID pContext)`
- caller_count: `0`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callees

- `0x14000b120`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000f050`
- `0x140010358`
- `0x1400104d4`
- `0x14001086c`
- `0x140015918`
- `0x140015988`
- `0x1400159f4`
- `0x140042fd4`
- `0x140044568`
- `0x140044c70`
- `0x140045890`
- `0x140045d50`
- `0x140046120`
- `0x140046a50`
- `0x14004ee60`
- `0x14004f820`
- `0x140053c10`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14004537e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004539d`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004537e`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004539d`
- `ntoskrnl!IoBuildPartialMdl` at `0x140044ddc`
- `ntoskrnl!IoBuildPartialMdl` at `0x140044ddc`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045093`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045438`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400456e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045839`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045093`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045438`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400456e8`
- `ntoskrnl!ExReleaseFastMutex` at `0x140045839`
- `ntoskrnl!ExAcquireFastMutex` at `0x140044f18`
- `ntoskrnl!ExAcquireFastMutex` at `0x140045411`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400454a3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004573e`
- `ntoskrnl!ExAcquireFastMutex` at `0x140044f18`
- `ntoskrnl!ExAcquireFastMutex` at `0x140045411`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400454a3`
- `ntoskrnl!ExAcquireFastMutex` at `0x14004573e`
- `ntoskrnl!KeSetEvent` at `0x14004517e`
- `ntoskrnl!KeSetEvent` at `0x14004517e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004518f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004518f`
- `rdbss!RxLowIoCompletion` at `0x140045160`
- `rdbss!RxLowIoCompletion` at `0x140045160`
- `mrxsmb!MRxSmbLegacyPerfCtrs` at `0x140044e2d`

## pseudocode

```c
__int64 __fastcall SmbPseExchangeStart_Write(char *pContext, __int64 a2)
{
  struct _MDL *v2; // r10
  __int64 v3; // r8
  char *v5; // rsi
  __int64 v6; // r12
  __int64 v8; // rcx
  unsigned __int8 v9; // al
  __int64 v10; // r9
  int v11; // ecx
  __int64 v12; // r14
  unsigned __int8 v13; // bp
  ULONG v14; // ecx
  __int64 v15; // rdx
  __int64 v16; // rsi
  struct _MDL *v17; // rdi
  unsigned int v18; // ebp
  unsigned int v20; // edi
  __int64 v21; // rdx
  __int64 v22; // r8
  __int64 v23; // r8
  char v24; // di
  int v25; // eax
  __int64 i; // r9
  int v27; // edx
  int v28; // eax
  signed __int32 v29; // ecx
  __int64 v30; // rdi
  __int64 v31; // r8
  __int64 v32; // rbx
  int v33; // esi
  signed __int32 v34; // r15d
  __int64 v35; // rax
  __int64 ExchangeSession; // rax
  __int64 v37; // rsi
  unsigned int v38; // eax
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // r9
  __int64 v42; // rdx
  __int64 v43; // rax
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  signed __int32 v46; // ecx
  __int64 v47; // [rsp+20h] [rbp-58h]
  unsigned __int8 v48; // [rsp+80h] [rbp+8h]
  __int64 v49; // [rsp+88h] [rbp+10h]
  struct _MDL *v50; // [rsp+90h] [rbp+18h]

  v2 = *(struct _MDL **)(a2 + 544);
  v3 = 0;
  v5 = pContext + 888;
  v6 = *((_QWORD *)pContext + 107);
  v50 = v2;
  v8 = *(_QWORD *)(*(_QWORD *)(a2 + 64) + 32LL);
  if ( v8 )
    v49 = *(_QWORD *)(v8 + 48);
  else
    v49 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids);
    v2 = v50;
    v3 = 0;
  }
  ++*((_DWORD *)pContext + 93);
  v9 = *(_BYTE *)(a2 + 536) & 1;
  *((_WORD *)pContext + 192) |= 4u;
  v48 = v9;
  while ( 2 )
  {
    v10 = 208;
    while ( 1 )
    {
      v11 = (unsigned __int8)pContext[387];
      v12 = *((_QWORD *)pContext + 10);
      if ( v11 == 1 )
        break;
      if ( !pContext[387] )
      {
        pContext[387] = 1;
        MRxSmbSetInitialSMB(v5);
        v2 = v50;
        break;
      }
      if ( (unsigned int)(v11 - 2) < 2 )
        goto LABEL_23;
    }
    *((_DWORD *)pContext + 98) = MRxSmbWriteSendOptions;
    pContext[387] = 2;
    if ( (*(_DWORD *)(v12 + 420) & 0x20010) != 0x20010
      || *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v5 + 6) + 56LL) + 120LL) + 77LL) == 3 )
    {
      v13 = 11;
    }
    else
    {
      v13 = 47;
    }
    v14 = *((_DWORD *)pContext + 122);
    v15 = *((unsigned int *)pContext + 125);
    if ( v14 < 0x40 )
    {
      *((_DWORD *)pContext + 124) = v14;
      v16 = *((_QWORD *)pContext + 59) + v15;
      v17 = 0;
    }
    else
    {
      v16 = 0;
      if ( v14 >= *((_DWORD *)pContext + 202) )
        v14 = *((_DWORD *)pContext + 202);
      *((_DWORD *)pContext + 124) = v14;
      if ( (_DWORD)v15 || v14 != v2->ByteCount )
      {
        *((_QWORD *)pContext + 70) = 0;
        v17 = (struct _MDL *)(pContext + 528);
        *((_QWORD *)pContext + 66) = 0;
        *((_DWORD *)pContext + 134) = 208;
        *((_QWORD *)pContext + 71) = 81920;
        IoBuildPartialMdl(v2, (PMDL)pContext + 11, (char *)v2->StartVa + v2->ByteOffset + v15, v14);
      }
      else
      {
        v17 = v2;
      }
    }
    v18 = MRxSmbBuildWriteRequest(
            (_DWORD)pContext,
            v48,
            v13,
            *((_DWORD *)pContext + 124),
            (__int64)(pContext + 504),
            v16,
            (__int64)v17);
    if ( !v18 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(((unsigned __int64)HIDWORD(KeGetPcr()[1].LockArray) << 8)
                                                      + MRxSmbLegacyPerfCtrs
                                                      + 128));
      v18 = SmbPseOrdinaryExchange(pContext);
      if ( v18 == 259 )
        goto LABEL_17;
      v5 = pContext + 888;
LABEL_23:
      if ( *((_DWORD *)pContext + 12) != -1069481983 )
        pContext[386] |= 0x40u;
      pContext[387] = 1;
      if ( pContext[516] )
      {
        if ( (pContext[746] & 0x20) != 0 )
          MmUnmapLockedPages(*((PVOID *)pContext + 95), (PMDL)(pContext + 736));
        pContext[517] = 0;
      }
      if ( pContext[517] )
      {
        if ( (pContext[538] & 0x20) != 0 )
          MmUnmapLockedPages(*((PVOID *)pContext + 69), (PMDL)pContext + 11);
        pContext[517] = 0;
      }
      v18 = *((_DWORD *)pContext + 12);
      if ( v18 )
      {
        v20 = *((_DWORD *)pContext + 12);
      }
      else
      {
        v18 = *((_DWORD *)pContext + 10);
        v20 = v18;
        if ( !v18 )
        {
LABEL_29:
          ExAcquireFastMutex(&MRxSmbReadWriteMutex);
          if ( !v20 )
          {
            v39 = *((unsigned int *)pContext + 128);
            *((_DWORD *)pContext + 122) -= v39;
            *(_QWORD *)(a2 + 184) += v39;
            v40 = *((unsigned int *)pContext + 128);
            *((_QWORD *)pContext + 63) += v40;
            *((_DWORD *)pContext + 125) += v40;
            if ( pContext[518] )
            {
              *(_QWORD *)(v49 + 88) += v40;
              MRxSmbUpdateFileInfoCacheFileSize(a2, (struct _LIST_ENTRY **)(v49 + 88));
            }
          }
          if ( v18 )
          {
LABEL_31:
            if ( *((_DWORD *)pContext + 122) )
              goto LABEL_32;
            goto LABEL_69;
          }
LABEL_102:
          if ( *((_DWORD *)pContext + 122) )
          {
            ExReleaseFastMutex(&MRxSmbReadWriteMutex);
LABEL_50:
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
                WPP_SF_qDD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  26,
                  WPP_ce2c64477360322a8496f3fa453cac86_Traceguids,
                  pContext,
                  *((_DWORD *)pContext + 122),
                  *((_DWORD *)pContext + 125));
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
              {
                WPP_SF_qDD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  27,
                  WPP_ce2c64477360322a8496f3fa453cac86_Traceguids,
                  pContext,
                  *((_DWORD *)pContext + 124),
                  *((_DWORD *)pContext + 128));
              }
            }
            MRxSmbSetInitialSMB(v5);
            v2 = v50;
            v3 = 0;
            continue;
          }
LABEL_69:
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          {
            if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              LODWORD(v47) = *((_DWORD *)pContext + 124);
              WPP_SF_qLLLL(
                WPP_GLOBAL_Control->AttachedDevice,
                21,
                WPP_ce2c64477360322a8496f3fa453cac86_Traceguids,
                pContext,
                v47,
                0,
                *((_DWORD *)pContext + 128),
                *((_DWORD *)pContext + 125));
            }
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
            {
              WPP_SF_d(
                WPP_GLOBAL_Control->AttachedDevice,
                22,
                WPP_ce2c64477360322a8496f3fa453cac86_Traceguids,
                *(unsigned int *)(a2 + 184));
            }
          }
          if ( !*((_DWORD *)pContext + 122) )
          {
            v35 = *((unsigned int *)pContext + 203);
            if ( *(_DWORD *)(v6 + 4 * v35 + 380) == 1 )
            {
              *(_DWORD *)(v6 + 4 * v35 + 380) = 2;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
              {
                LODWORD(v47) = *((_DWORD *)pContext + 124);
                WPP_SF_dDDD(
                  WPP_GLOBAL_Control->AttachedDevice,
                  v21,
                  v22,
                  *((unsigned int *)pContext + 203),
                  v47,
                  *((_DWORD *)pContext + 128),
                  *(_DWORD *)(a2 + 184));
              }
LABEL_33:
              if ( v18 != -1069481983 && v18 )
              {
                v24 = 0;
                if ( v18 != -1063771909 )
                  goto LABEL_44;
                *(_DWORD *)(v6 + 360) = -1063771909;
              }
              v23 = *((_QWORD *)pContext + 107);
              v24 = 0;
              v25 = *(_DWORD *)(v23 + 360);
              if ( !v25 || v25 == -1063771909 )
              {
                v18 = 0;
                if ( v25 == -1063771909 )
                {
                  *(_QWORD *)(a2 + 184) = 0;
                  v41 = 0;
                  *(_DWORD *)(v23 + 360) = 0;
                  for ( *((_DWORD *)pContext + 12) = 0;
                        (unsigned int)v41 < *(_DWORD *)(v23 + 328);
                        v41 = (unsigned int)(v41 + 1) )
                  {
                    v42 = v23 + 4 * v41;
                    if ( *(_DWORD *)(v42 + 380) == 1 )
                    {
                      *(_DWORD *)(v42 + 380) = 3;
                    }
                    else if ( *(_DWORD *)(v42 + 380) == 2 )
                    {
                      *(_DWORD *)(v42 + 380) = 0;
                    }
                  }
                }
                for ( i = 0; (unsigned int)i < *(_DWORD *)(v23 + 328); i = (unsigned int)(i + 1) )
                {
                  if ( !*(_DWORD *)(v23 + 4 * i + 380) )
                  {
                    *(_DWORD *)(v23 + 4 * i + 380) = 1;
                    *((_QWORD *)pContext + 63) = *(_QWORD *)(v23 + 32)
                                               + (unsigned int)i * (unsigned __int64)*(unsigned int *)(v23 + 336);
                    if ( (_DWORD)i != *(_DWORD *)(v23 + 328) - 1
                      || (v27 = *(_DWORD *)(v23 + 16) % *(_DWORD *)(v23 + 336)) == 0 )
                    {
                      v27 = 0;
                      if ( *(_DWORD *)(v23 + 16) )
                        v27 = *(_DWORD *)(v23 + 336);
                    }
                    *((_DWORD *)pContext + 122) = v27;
                    v28 = *(_DWORD *)(v23 + 336) * i;
                    *((_DWORD *)pContext + 203) = i;
                    *((_DWORD *)pContext + 125) = v28;
                    _InterlockedIncrement((volatile signed __int32 *)(v23 + 332));
                    v24 = 1;
                    v18 = -1073741802;
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
                    {
                      HIDWORD(v47) = HIDWORD(pContext);
                      WPP_SF_dq(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids);
                    }
                    break;
                  }
                }
              }
              else
              {
                v18 = *(_DWORD *)(v23 + 360);
              }
LABEL_44:
              v29 = _InterlockedDecrement((volatile signed __int32 *)(v6 + 332));
              if ( v24 )
              {
LABEL_49:
                ExReleaseFastMutex(&MRxSmbReadWriteMutex);
                if ( !v24 )
                  goto LABEL_57;
                goto LABEL_50;
              }
              if ( v18 == -1073741631 )
              {
                if ( v29 )
                {
                  v18 = 0;
                  goto LABEL_47;
                }
              }
              else if ( !v18 )
              {
                goto LABEL_47;
              }
              if ( !*(_DWORD *)(v6 + 360) )
                *(_DWORD *)(v6 + 360) = v18;
LABEL_47:
              pContext[519] = 1;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
              {
                LODWORD(v47) = v18;
                WPP_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_GLOBAL_Control, pContext, v47, v29);
                ExReleaseFastMutex(&MRxSmbReadWriteMutex);
                goto LABEL_57;
              }
              goto LABEL_49;
            }
          }
LABEL_32:
          *(_DWORD *)(v6 + 4LL * *((unsigned int *)pContext + 203) + 380) = 0;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->AttachedDevice,
              24,
              WPP_ce2c64477360322a8496f3fa453cac86_Traceguids,
              *((unsigned int *)pContext + 203));
          }
          goto LABEL_33;
        }
      }
      ExchangeSession = SmbCeGetExchangeSession(pContext, a2, v3, v10);
      v37 = ExchangeSession;
      if ( v20 == -1069481983 )
      {
        SmbCeUninitializeExchangeTransport();
        SmbCeReconnect(*((PVOID *)pContext + 11));
        v18 = v38;
        if ( v38 )
          goto LABEL_57;
        *((_DWORD *)pContext + 12) = 0;
        *((_DWORD *)pContext + 10) = 0;
        v18 = SmbCeInitializeExchangeTransport(pContext);
        if ( v18 )
          goto LABEL_57;
        goto LABEL_101;
      }
      if ( ((*(_DWORD *)(ExchangeSession + 8) & 8) != 0 || *(_BYTE *)(v12 + 640))
        && *(_QWORD *)(v49 + 16)
        && (unsigned __int8)SmbCeIsReconnectableError(v20) )
      {
        v18 = SmbCeRemoteBootReconnect(pContext, a2);
        if ( !v18 )
        {
          *((_DWORD *)pContext + 10) = 0;
          SmbCeInitializeExchangeTransport(pContext);
LABEL_101:
          ExAcquireFastMutex(&MRxSmbReadWriteMutex);
          v5 = pContext + 888;
          goto LABEL_102;
        }
        if ( (*(_DWORD *)(v37 + 8) & 8) != 0 )
        {
          v18 = -1069481983;
          ExAcquireFastMutex(&MRxSmbReadWriteMutex);
          v5 = pContext + 888;
          goto LABEL_31;
        }
      }
      v5 = pContext + 888;
      goto LABEL_29;
    }
    break;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids);
LABEL_57:
  if ( v18 != 259 )
  {
    v30 = *((_QWORD *)pContext + 107);
    if ( pContext[519] )
    {
LABEL_59:
      SmbPseFinalizeOrdinaryExchange((unsigned __int8 *)pContext);
      v32 = *(_QWORD *)(v30 + 8);
      v33 = *(_DWORD *)(v32 + 120);
      v34 = _InterlockedDecrement((volatile signed __int32 *)(v30 + 344));
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        LODWORD(v47) = v34;
        WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 10, v31, v30, v47);
      }
      if ( !v34 )
      {
        *(_DWORD *)(v32 + 176) = *(_DWORD *)(v30 + 360);
        RxLowIoCompletion((PRX_CONTEXT)v32);
        if ( (v33 & 0x1000) == 0 )
          KeSetEvent(*(PRKEVENT *)(v30 + 352), 0, 0);
        ExFreePoolWithTag((PVOID)v30, 0);
      }
      v18 = 259;
      goto LABEL_17;
    }
    ExAcquireFastMutex(&MRxSmbReadWriteMutex);
    if ( *((_DWORD *)pContext + 122) || (v43 = *((unsigned int *)pContext + 203), *(_DWORD *)(v30 + 4 * v43 + 380) != 1) )
    {
      *(_DWORD *)(v30 + 4LL * *((unsigned int *)pContext + 203) + 380) = 0;
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v45 = 29;
        goto LABEL_147;
      }
    }
    else
    {
      *(_DWORD *)(v30 + 4 * v43 + 380) = 2;
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        v45 = 28;
LABEL_147:
        WPP_SF_d(
          v44->AttachedDevice,
          v45,
          WPP_ce2c64477360322a8496f3fa453cac86_Traceguids,
          *((unsigned int *)pContext + 203));
      }
    }
    v46 = _InterlockedDecrement((volatile signed __int32 *)(v30 + 332));
    if ( v18 == -1073741631 )
    {
      if ( v46 )
      {
        v18 = 0;
        goto LABEL_154;
      }
    }
    else if ( !v18 )
    {
LABEL_154:
      pContext[519] = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      {
        LODWORD(v47) = v18;
        WPP_SF_qDd(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_GLOBAL_Control, pContext, v47, v46);
      }
      ExReleaseFastMutex(&MRxSmbReadWriteMutex);
      goto LABEL_59;
    }
    if ( !*(_DWORD *)(v30 + 360) )
      *(_DWORD *)(v30 + 360) = v18;
    goto LABEL_154;
  }
LABEL_17:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids, v18);
  return v18;
}

```

## disassembly

```asm
0x140044c70  mov     rax, rsp
0x140044c73  sub     rsp, 78h
0x140044c77  mov     r10, [rdx+220h]
0x140044c7e  xor     r8d, r8d
0x140044c81  mov     [rax+20h], rbx
0x140044c85  mov     rbx, rcx
0x140044c88  mov     [rax-10h], rsi
0x140044c8c  lea     rsi, [rcx+378h]
0x140044c93  mov     [rax-20h], r12
0x140044c97  mov     r12, [rcx+358h]
0x140044c9e  mov     [rax-28h], r13
0x140044ca2  mov     r13, rdx
0x140044ca5  mov     [rax-30h], r14
0x140044ca9  mov     [rax-38h], r15
0x140044cad  mov     rax, [rdx+40h]
0x140044cb1  mov     [rsp+78h+arg_10], r10
0x140044cb9  mov     rcx, [rax+20h]
0x140044cbd  test    rcx, rcx
0x140044cc0  jnz     loc_140044EB0
0x140044cc6  mov     [rsp+78h+arg_8], r8
0x140044cce  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044cd5  lea     rax, WPP_GLOBAL_Control
0x140044cdc  cmp     rcx, rax
0x140044cdf  jnz     loc_14004519D
0x140044ce5  inc     dword ptr [rbx+174h]
0x140044ceb  mov     r15d, 0FFFFFFFFh
0x140044cf1  movzx   eax, byte ptr [r13+218h]
0x140044cf9  and     al, 1
0x140044cfb  mov     [rsp+78h+var_8], rbp
0x140044d00  or      word ptr [rbx+180h], 4
0x140044d08  mov     [rsp+78h+arg_0], al
0x140044d0f  mov     [rsp+78h+var_18], rdi
0x140044d14  mov     r9d, 0D0h
0x140044d1a  movzx   ecx, byte ptr [rbx+183h]
0x140044d21  mov     r14, [rbx+50h]
0x140044d25  cmp     ecx, 1
0x140044d28  jnz     loc_140045294
0x140044d2e  mov     eax, cs:MRxSmbWriteSendOptions
0x140044d34  mov     [rbx+188h], eax
0x140044d3a  mov     byte ptr [rbx+183h], 2
0x140044d41  mov     eax, [r14+1A4h]
0x140044d48  and     eax, 20010h
0x140044d4d  cmp     eax, 20010h
0x140044d52  jnz     loc_14004533E
0x140044d58  mov     rax, [rsi+30h]
0x140044d5c  mov     rcx, [rax+38h]
0x140044d60  mov     rax, [rcx+78h]
0x140044d64  cmp     byte ptr [rax+4Dh], 3
0x140044d68  jz      loc_14004533E
0x140044d6e  mov     bpl, 2Fh ; '/'
0x140044d71  mov     ecx, [rbx+1E8h]
0x140044d77  mov     edx, [rbx+1F4h]
0x140044d7d  cmp     ecx, 40h ; '@'
0x140044d80  jb      loc_140045358
0x140044d86  mov     eax, [rbx+328h]
0x140044d8c  mov     rsi, r8
0x140044d8f  cmp     ecx, eax
0x140044d91  cmovnb  ecx, eax
0x140044d94  mov     [rbx+1F0h], ecx
0x140044d9a  test    edx, edx
0x140044d9c  jz      loc_140045346
0x140044da2  mov     [rbx+230h], r8
0x140044da9  lea     rdi, [rbx+210h]
0x140044db0  mov     [rdi], r8
0x140044db3  mov     r9d, ecx; Length
0x140044db6  mov     dword ptr [rbx+218h], 0D0h
0x140044dc0  mov     rcx, r10; SourceMdl
0x140044dc3  mov     qword ptr [rbx+238h], 14000h
0x140044dce  mov     r8d, [r10+2Ch]
0x140044dd2  add     r8, [r10+20h]
0x140044dd6  add     r8, rdx; VirtualAddress
0x140044dd9  mov     rdx, rdi; TargetMdl
0x140044ddc  call    cs:__imp_IoBuildPartialMdl
0x140044de3  nop     dword ptr [rax+rax+00h]
0x140044de8  mov     r9d, [rbx+1F0h]
0x140044def  lea     rax, [rbx+1F8h]
0x140044df6  movzx   edx, [rsp+78h+arg_0]
0x140044dfe  movzx   r8d, bpl
0x140044e02  mov     [rsp+78h+var_48], rdi
0x140044e07  mov     rcx, rbx
0x140044e0a  mov     [rsp+78h+var_50], rsi
0x140044e0f  mov     [rsp+78h+var_58], rax
0x140044e14  call    MRxSmbBuildWriteRequest
0x140044e19  mov     ebp, eax
0x140044e1b  test    eax, eax
0x140044e1d  jnz     loc_1400456F9
0x140044e23  mov     eax, gs:1A4h
0x140044e2b  mov     edx, eax
0x140044e2d  mov     rax, cs:__imp_MRxSmbLegacyPerfCtrs
0x140044e34  shl     rdx, 8
0x140044e38  mov     rcx, [rax]
0x140044e3b  lock inc dword ptr [rdx+rcx+80h]
0x140044e43  mov     r8d, 5
0x140044e49  mov     rdx, r13
0x140044e4c  mov     rcx, rbx; pContext
0x140044e4f  call    SmbPseOrdinaryExchange
0x140044e54  mov     ebp, eax
0x140044e56  cmp     eax, 103h
0x140044e5b  jnz     short loc_140044EC1
0x140044e5d  lea     r14, WPP_GLOBAL_Control
0x140044e64  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044e6b  mov     r15, [rsp+78h+var_38]
0x140044e70  cmp     rcx, r14
0x140044e73  mov     r14, [rsp+78h+var_30]
0x140044e78  mov     r13, [rsp+78h+var_28]
0x140044e7d  mov     r12, [rsp+78h+var_20]
0x140044e82  mov     rdi, [rsp+78h+var_18]
0x140044e87  mov     rsi, [rsp+78h+var_10]
0x140044e8c  mov     rbx, [rsp+78h+arg_18]
0x140044e94  jz      short loc_140044EA3
0x140044e96  test    dword ptr [rcx+2Ch], 400h
0x140044e9d  jnz     loc_140045865
0x140044ea3  mov     eax, ebp
0x140044ea5  mov     rbp, [rsp+78h+var_8]
0x140044eaa  add     rsp, 78h
0x140044eae  retn
0x140044eb0  mov     rax, [rcx+30h]
0x140044eb4  mov     [rsp+78h+arg_8], rax
0x140044ebc  jmp     loc_140044CCE
0x140044ec1  lea     rsi, [rbx+378h]
0x140044ec8  cmp     dword ptr [rbx+30h], 0C0410001h
0x140044ecf  jz      short loc_140044ED8
0x140044ed1  or      byte ptr [rbx+182h], 40h
0x140044ed8  mov     byte ptr [rbx+183h], 1
0x140044edf  cmp     byte ptr [rbx+204h], 0
0x140044ee6  jnz     loc_1400452CE
0x140044eec  cmp     byte ptr [rbx+205h], 0
0x140044ef3  jnz     loc_1400452E7
0x140044ef9  mov     ebp, [rbx+30h]
0x140044efc  test    ebp, ebp
0x140044efe  jnz     loc_1400453AE
0x140044f04  mov     ebp, [rbx+28h]
0x140044f07  mov     edi, ebp
0x140044f09  test    ebp, ebp
0x140044f0b  jnz     loc_1400453B0
0x140044f11  lea     rcx, MRxSmbReadWriteMutex; FastMutex
0x140044f18  call    cs:__imp_ExAcquireFastMutex
0x140044f1f  nop     dword ptr [rax+rax+00h]
0x140044f24  test    edi, edi
0x140044f26  jz      loc_1400454C7
0x140044f2c  test    ebp, ebp
0x140044f2e  jz      loc_140045424
0x140044f34  cmp     dword ptr [rbx+1E8h], 0
0x140044f3b  jz      loc_1400451CF
0x140044f41  mov     eax, [rbx+32Ch]
0x140044f47  mov     dword ptr [r12+rax*4+17Ch], 0
0x140044f53  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044f5a  lea     r14, WPP_GLOBAL_Control
0x140044f61  cmp     rcx, r14
0x140044f64  jnz     loc_140045566
0x140044f6a  cmp     ebp, 0C0410001h
0x140044f70  jnz     loc_14004526C
0x140044f76  mov     r8, [rbx+358h]
0x140044f7d  xor     dil, dil
0x140044f80  mov     eax, [r8+168h]
0x140044f87  test    eax, eax
0x140044f89  jnz     loc_140045594
0x140044f8f  xor     ebp, ebp
0x140044f91  cmp     eax, 0C09820FBh
0x140044f96  jz      loc_1400455A6
0x140044f9c  mov     eax, [r8+148h]
0x140044fa3  xor     r9d, r9d
0x140044fa6  cmp     r9d, eax
0x140044fa9  jnb     loc_140045043
0x140044faf  mov     ecx, r9d
0x140044fb2  cmp     [r8+r9*4+17Ch], ebp
0x140044fba  jz      short loc_140044FC1
0x140044fbc  inc     r9d
0x140044fbf  jmp     short loc_140044FA6
0x140044fc1  mov     dword ptr [r8+r9*4+17Ch], 1
0x140044fcd  mov     eax, [r8+150h]
0x140044fd4  imul    rax, rcx
0x140044fd8  add     rax, [r8+20h]
0x140044fdc  mov     [rbx+1F8h], rax
0x140044fe3  mov     eax, [r8+148h]
0x140044fea  mov     ecx, [r8+150h]
0x140044ff1  dec     eax
0x140044ff3  cmp     r9d, eax
0x140044ff6  jz      loc_1400455FE
0x140044ffc  xor     edx, edx
0x140044ffe  cmp     [r8+10h], edx
0x140045002  cmovnz  edx, ecx
0x140045005  mov     [rbx+1E8h], edx
0x14004500b  mov     eax, r9d
0x14004500e  imul    eax, [r8+150h]
0x140045016  mov     [rbx+32Ch], r9d
0x14004501d  mov     [rbx+1F4h], eax
0x140045023  lock inc dword ptr [r8+14Ch]
0x14004502b  mov     dil, 1
0x14004502e  mov     ebp, 0C0000016h
0x140045033  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004503a  cmp     rcx, r14
0x14004503d  jnz     loc_140045613
0x140045043  mov     ecx, r15d
0x140045046  lock xadd [r12+14Ch], ecx
0x140045050  dec     ecx
0x140045052  test    dil, dil
0x140045055  jnz     short loc_14004508C
0x140045057  cmp     ebp, 0C00000C1h
0x14004505d  jz      loc_14004563F
0x140045063  test    ebp, ebp
0x140045065  jnz     loc_14004564A
0x14004506b  mov     byte ptr [rbx+207h], 1
0x140045072  mov     r8, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045079  cmp     r8, r14
0x14004507c  jz      short loc_14004508C
0x14004507e  test    dword ptr [r8+2Ch], 200h
0x140045086  jnz     loc_1400456C8
0x14004508c  lea     rcx, MRxSmbReadWriteMutex; FastMutex
0x140045093  call    cs:__imp_ExReleaseFastMutex
0x14004509a  nop     dword ptr [rax+rax+00h]
0x14004509f  test    dil, dil
0x1400450a2  jz      short loc_1400450EE
0x1400450a4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400450ab  cmp     rcx, r14
0x1400450ae  jz      short loc_1400450D6
0x1400450b0  test    dword ptr [rcx+2Ch], 400h
0x1400450b7  jnz     loc_140045666
0x1400450bd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400450c4  cmp     rcx, r14
0x1400450c7  jz      short loc_1400450D6
0x1400450c9  test    dword ptr [rcx+2Ch], 400h
0x1400450d0  jnz     loc_140045697
0x1400450d6  mov     rcx, rsi
0x1400450d9  call    MRxSmbSetInitialSMB
0x1400450de  mov     r10, [rsp+78h+arg_10]
0x1400450e6  xor     r8d, r8d
0x1400450e9  jmp     loc_140044D14
0x1400450ee  cmp     ebp, 103h
0x1400450f4  jz      loc_140044E64
0x1400450fa  cmp     byte ptr [rbx+207h], 0
0x140045101  mov     rdi, [rbx+358h]
0x140045108  jz      loc_140045737
0x14004510e  mov     rcx, rbx; pContext
0x140045111  call    SmbPseFinalizeOrdinaryExchange
0x140045116  mov     rbx, [rdi+8]
0x14004511a  mov     esi, [rbx+78h]
0x14004511d  lock xadd [rdi+158h], r15d
0x140045126  dec     r15d
0x140045129  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045130  cmp     rcx, r14
0x140045133  jz      short loc_140045142
0x140045135  test    dword ptr [rcx+2Ch], 200h
0x14004513c  jnz     loc_14004584A
0x140045142  test    r15d, r15d
0x140045145  jz      short loc_140045151
0x140045147  mov     ebp, 103h
0x14004514c  jmp     loc_140044E64
0x140045151  mov     eax, [rdi+168h]
0x140045157  mov     rcx, rbx; RxContext
0x14004515a  mov     [rbx+0B0h], eax
0x140045160  call    cs:__imp_RxLowIoCompletion
0x140045167  nop     dword ptr [rax+rax+00h]
0x14004516c  bt      esi, 0Ch
0x140045170  jb      short loc_14004518A
0x140045172  mov     rcx, [rdi+160h]; Event
0x140045179  xor     r8d, r8d; Wait
0x14004517c  xor     edx, edx; Increment
0x14004517e  call    cs:__imp_KeSetEvent
0x140045185  nop     dword ptr [rax+rax+00h]
0x14004518a  xor     edx, edx; Tag
0x14004518c  mov     rcx, rdi; P
0x14004518f  call    cs:__imp_ExFreePoolWithTag
0x140045196  nop     dword ptr [rax+rax+00h]
0x14004519b  jmp     short loc_140045147
0x14004519d  test    dword ptr [rcx+2Ch], 400h
0x1400451a4  jz      loc_140044CE5
0x1400451aa  mov     rcx, [rcx+18h]
0x1400451ae  lea     r8, WPP_ce2c64477360322a8496f3fa453cac86_Traceguids
0x1400451b5  mov     edx, 13h
0x1400451ba  call    WPP_SF_
0x1400451bf  mov     r10, [rsp+78h+arg_10]
0x1400451c7  xor     r8d, r8d
0x1400451ca  jmp     loc_140044CE5
0x1400451cf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400451d6  lea     rdi, WPP_GLOBAL_Control
0x1400451dd  cmp     rcx, rdi
0x1400451e0  jnz     loc_140045516
0x1400451e6  cmp     dword ptr [rbx+1E8h], 0
0x1400451ed  jnz     loc_140044F41
0x1400451f3  mov     eax, [rbx+32Ch]
0x1400451f9  cmp     dword ptr [r12+rax*4+17Ch], 1
0x140045202  jnz     loc_140044F41
0x140045208  mov     dword ptr [r12+rax*4+17Ch], 2
0x140045214  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004521b  lea     r14, WPP_GLOBAL_Control
0x140045222  cmp     rcx, r14
0x140045225  jz      loc_140044F6A
0x14004522b  test    dword ptr [rcx+2Ch], 200h
0x140045232  jz      loc_140044F6A
0x140045238  mov     eax, [r13+0B8h]
0x14004523f  mov     r9d, [rbx+32Ch]
0x140045246  mov     rcx, [rcx+18h]
0x14004524a  mov     dword ptr [rsp+78h+var_48], eax
0x14004524e  mov     eax, [rbx+200h]
0x140045254  mov     dword ptr [rsp+78h+var_50], eax
0x140045258  mov     eax, [rbx+1F0h]
0x14004525e  mov     dword ptr [rsp+78h+var_58], eax
0x140045262  call    WPP_SF_dDDD
0x140045267  jmp     loc_140044F6A
  ... truncated ...
```
