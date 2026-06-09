# CFlipToken::InitializeCompleted(_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN const &,bool)

- ea: `0x14000ae00`
- end: `0x14000b958`
- name: `?InitializeCompleted@CFlipToken@@IEAAJAEBU_D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN@@_N@Z`
- size: `2904`
- prototype: `__int64 __fastcall(CFlipToken *this, const struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *, char)`
- caller_count: `2`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x140009ba0`
- `0x14000aacc`

## callees

- `0x140008438`
- `0x14000ae00`
- `0x14000b960`
- `0x14000b9dc`
- `0x14000ba60`
- `0x14001b9c0`
- `0x140036030`
- `0x14003605c`
- `0x14003637c`
- `0x140060c10`
- `0x140060cbc`
- `0x1400a0bd0`
- `0x1400a0cb0`
- `0x1400a1000`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000aff9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b1d5`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000aff9`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000b1d5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000aeb0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000afe8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b08c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b1c4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000aeb0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000afe8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b08c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000b1c4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b055`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b111`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000af34`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b055`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000b111`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b249`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b25e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b277`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b249`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b25e`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000b277`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000af28`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b049`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b105`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000af28`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b049`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x14000b105`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000aec5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b0a1`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000aec5`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x14000b0a1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000af0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b005`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b02e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b0ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b1e1`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000af0d`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b005`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b02e`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b0ea`
- `ntoskrnl!PsGetCurrentThreadId` at `0x14000b1e1`
- `watchdog!WdLogSingleEntry0` at `0x14000b84b`
- `watchdog!WdLogSingleEntry0` at `0x14000b8a1`
- `watchdog!WdLogSingleEntry0` at `0x14000b8f7`
- `watchdog!WdLogSingleEntry0` at `0x14000b84b`
- `watchdog!WdLogSingleEntry0` at `0x14000b8a1`
- `watchdog!WdLogSingleEntry0` at `0x14000b8f7`

## pseudocode

```c
__int64 __fastcall CFlipToken::InitializeCompleted(
        CFlipToken *this,
        const struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKEN *a2,
        char a3)
{
  int v3; // ebp
  __int64 v7; // rax
  bool v8; // zf
  __int64 v9; // rbx
  __int64 v10; // rsi
  __int64 v11; // rdi
  _QWORD **v12; // rbx
  _QWORD *i; // rax
  unsigned __int8 v14; // bl
  __int64 v15; // r15
  int v16; // edi
  int v17; // esi
  __int64 v18; // rbx
  void (__fastcall *v19)(_QWORD, _QWORD, _QWORD, __int64, int, int, int, __int64, __int64, _DWORD); // r12
  __int64 v20; // r14
  unsigned int v21; // eax
  __int64 result; // rax
  __int64 v23; // rbx
  __int64 v24; // rdi
  int v25; // esi
  __int64 v26; // rdi
  __int64 v27; // rsi
  __int64 v28; // rbx
  _QWORD **v29; // rdi
  _QWORD *k; // rax
  unsigned __int8 v31; // di
  __int64 v32; // r15
  int v33; // ebx
  BOOL v34; // r14d
  int v35; // edi
  __int64 v36; // rsi
  void (__fastcall *v37)(_QWORD, _QWORD, _QWORD, __int64, int, int, BOOL, __int64, __int64, _DWORD); // r12
  __int64 v38; // rbp
  unsigned int v39; // eax
  _QWORD *v40; // rbx
  int v41; // eax
  CPushLock *v42; // rcx
  UINT v43; // eax
  int v44; // edi
  char v45; // cl
  struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS::$999A3466B180106FECC6453D6FF00F87::$CDA7573B07EF0A4513B0E43B6C419F7F Value; // eax
  UINT PlaneIndex; // eax
  UINT v48; // esi
  UINT NumBlts; // ecx
  UINT v50; // ecx
  struct CCompositionBuffer *v51; // rbp
  _QWORD *j; // rax
  CFlipExBuffer *v53; // rbp
  int inserted; // eax
  __int64 v55; // rdx
  char *v56; // rax
  __int64 v57; // rdx
  _BYTE *v58; // rcx
  __int128 v59; // xmm0
  __int128 v60; // xmm1
  __int128 v61; // xmm0
  __int128 v62; // xmm1
  __int128 v63; // xmm0
  __int128 v64; // xmm1
  __int128 v65; // xmm0
  __int128 v66; // xmm1
  unsigned __int64 v67; // rdx
  __int128 v68; // xmm1
  __int128 v69; // xmm0
  __int128 v70; // xmm1
  __int64 v71; // rax
  __int64 v72; // rcx
  unsigned __int64 v73; // rbx
  bool v74; // [rsp+60h] [rbp-238h] BYREF
  unsigned __int64 v75; // [rsp+68h] [rbp-230h] BYREF
  unsigned __int64 v76[2]; // [rsp+70h] [rbp-228h] BYREF
  _BYTE v77[464]; // [rsp+80h] [rbp-218h] BYREF

  v3 = 0;
  *((_DWORD *)this + 6) = 0;
  if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2650;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
  }
  LODWORD(v75) = (*(__int64 (__fastcall **)(char *))(*(_QWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 304968LL) + 40LL))((char *)this + 96);
  v7 = *(_QWORD *)this;
  if ( (v75 & 0x80000000) != 0LL )
  {
    (*(void (__fastcall **)(CFlipToken *))(v7 + 56))(this);
    goto LABEL_8;
  }
  (*(void (__fastcall **)(CFlipToken *))(v7 + 24))(this);
  v43 = a2->Flags.Value & 0x180;
  if ( (a2->Flags.Value & 0x100) == 0 || (v44 = -1073741811, LODWORD(v75) = -1073741811, v43 == 384) )
  {
    v44 = 0;
    LODWORD(v75) = 0;
  }
  if ( v44 < 0 )
  {
    LODWORD(v75) = v44;
    goto LABEL_8;
  }
  *((_QWORD *)this + 13) = a2->FenceValue;
  if ( (signed int)a2->RemainingTokens < a2->ScrollRect.top && a2->ScrollRect.left < a2->ScrollRect.right )
  {
    *((_DWORD *)this + 17) = 1;
    *(_OWORD *)((char *)this + 72) = *(_OWORD *)&a2->RemainingTokens;
    *((_QWORD *)this + 11) = *(_QWORD *)&a2->ScrollRect.bottom;
  }
  *((_DWORD *)this + 32) = a2->FlipInterval;
  *((_DWORD *)this + 31) = a2->ScrollOffset.y;
  *((_DWORD *)this + 30) = a2->SwapChainIndex;
  *((_DWORD *)this + 57) = LODWORD(a2->Transform[4]);
  *((_BYTE *)this + 132) = (a2->Flags.Value & 0x800000) != 0;
  *((_BYTE *)this + 134) = (a2->Flags.Value & 2) != 0;
  *((_BYTE *)this + 152) = (a2->Flags.Value & 8) != 0;
  *((_BYTE *)this + 153) = (a2->Flags.Value & 0x10) != 0;
  *((_BYTE *)this + 133) = (a2->Flags.Value & 0x20) != 0;
  v45 = (a2->Flags.Value & 0x40) != 0;
  *((_BYTE *)this + 154) = v45;
  *((_DWORD *)this + 39) = (a2->Flags.Value >> 7) & 3;
  *((_DWORD *)this + 34) = a2->PresentCount;
  *((_DWORD *)this + 35) = LODWORD(a2->RevealColor[0]);
  *((_DWORD *)this + 36) = LODWORD(a2->RevealColor[1]);
  *((_DWORD *)this + 37) = LODWORD(a2->RevealColor[2]);
  *((_DWORD *)this + 40) = LODWORD(a2->RevealColor[3]);
  *(_OWORD *)((char *)this + 164) = *(_OWORD *)((char *)&a2->1 + 580);
  *(_OWORD *)((char *)this + 180) = *(_OWORD *)&a2->DestWidth;
  *((_DWORD *)this + 49) = a2->SourceRect.right;
  *((_DWORD *)this + 50) = a2->SourceRect.bottom;
  *((_DWORD *)this + 143) = a2->ScatterBlts.Blts[11].DestinationOffset.x;
  *((_BYTE *)this + 579) = (a2->Flags.Value & 0x2000) != 0;
  *((_QWORD *)this + 74) = a2->dxgContext;
  *((_DWORD *)this + 152) = a2->VidPnSourceId;
  *((_DWORD *)this + 58) = a2->CustomDurationFlipInterval;
  *((_DWORD *)this + 153) = a2->CustomDuration;
  *((_BYTE *)this + 584) = (a2->Flags.Value & 0x8000000) != 0;
  *((_DWORD *)this + 51) = a2->TargetRect.right;
  *((_DWORD *)this + 52) = a2->TargetRect.bottom;
  *((_DWORD *)this + 53) = LODWORD(a2->Transform[0]);
  *((_DWORD *)this + 54) = LODWORD(a2->Transform[1]);
  *((_DWORD *)this + 55) = LODWORD(a2->Transform[2]);
  *((_DWORD *)this + 56) = LODWORD(a2->Transform[3]);
  if ( !a2->PresentLimitSemaphoreId )
    *((_BYTE *)this + 578) = 1;
  *((_BYTE *)this + 582) = a3;
  Value = (struct _D3DKMT_FLIPMODEL_PRESENTHISTORYTOKENFLAGS::$999A3466B180106FECC6453D6FF00F87::$CDA7573B07EF0A4513B0E43B6C419F7F)a2->Flags.Value;
  if ( (*(_DWORD *)&Value & 0x100000) != 0 )
  {
    *((_QWORD *)this + 75) = a2->confirmationCookie;
    *((_BYTE *)this + 580) = 1;
  }
  else if ( (*(_DWORD *)&Value & 0x1000000) != 0 )
  {
    *((_BYTE *)this + 581) = 1;
  }
  PlaneIndex = a2->PlaneIndex;
  if ( PlaneIndex )
  {
    if ( PlaneIndex > 0x10 )
    {
      LODWORD(v75) = -1073741811;
      goto LABEL_6;
    }
    *((_DWORD *)this + 78) = PlaneIndex;
    v48 = 0;
    if ( a2->PlaneIndex )
    {
      do
      {
        *(_OWORD *)((char *)this + 16 * v48 + 316) = *((_OWORD *)&a2->ColorSpace + v48);
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 12) + 40LL))(*((_QWORD *)this + 12));
        ++v48;
      }
      while ( v48 < a2->PlaneIndex );
      v45 = *((_BYTE *)this + 154);
      goto LABEL_6;
    }
  }
  LODWORD(v75) = v44;
LABEL_6:
  if ( v45 )
  {
    NumBlts = a2->ScatterBlts.NumBlts;
    *((_DWORD *)this + 59) = NumBlts;
    v50 = NumBlts - 1;
    if ( v50 )
    {
      if ( v50 == 1 )
      {
        *((_OWORD *)this + 15) = *(_OWORD *)((char *)&a2->hSyncObject + 4);
        *((_OWORD *)this + 16) = *(_OWORD *)&a2->HDRMetaDataHDR10Plus.Data[8];
        *((_OWORD *)this + 17) = *(_OWORD *)&a2->HDRMetaDataHDR10Plus.Data[24];
        *((_OWORD *)this + 18) = *(_OWORD *)&a2->HDRMetaDataHDR10Plus.Data[40];
        *((_QWORD *)this + 38) = *(_QWORD *)&a2->HDRMetaDataHDR10Plus.Data[56];
      }
    }
    else
    {
      *((_OWORD *)this + 15) = *(_OWORD *)((char *)&a2->hSyncObject + 4);
      *(_OWORD *)((char *)this + 252) = *(_OWORD *)&a2->HDRMetaDataHDR10Plus.Data[4];
    }
  }
  if ( (a2->Flags.Value & 0x20000000) != 0
    && (!(*(unsigned __int8 (__fastcall **)(CFlipToken *))(*(_QWORD *)this + 144LL))(this)
     || (*(unsigned __int8 (__fastcall **)(CFlipToken *))(*(_QWORD *)this + 152LL))(this)) )
  {
    CFlipToken::SignalGpuFenceAndPresentLimitSemaphore(this, 1);
  }
LABEL_8:
  v8 = *((_DWORD *)this + 6) == 3;
  LODWORD(v76[0]) = 0;
  if ( v8 )
  {
    v9 = *((_QWORD *)this + 6);
    v10 = *((_QWORD *)this + 7);
    KeEnterCriticalRegion();
    v11 = v9 + 48;
    ExAcquirePushLockSharedEx(v9 + 48, 0);
    if ( *(_DWORD *)(v9 + 160) )
    {
      v12 = (_QWORD **)(v9 + 144);
      for ( i = *v12; i != v12; i = (_QWORD *)*i )
      {
        if ( *(i - 1) == v10 )
        {
          v14 = (*(__int64 (__fastcall **)(_QWORD *))(*(i - 3) + 40LL))(i - 3);
          goto LABEL_14;
        }
      }
    }
    v14 = 0;
LABEL_14:
    if ( PsGetCurrentThreadId() == *(HANDLE *)(v11 + 8) )
    {
      *(_QWORD *)(v11 + 8) = 0;
      ExReleasePushLockExclusiveEx(v11, 0);
    }
    else
    {
      ExReleasePushLockSharedEx(v11, 0);
    }
    KeLeaveCriticalRegion();
    LODWORD(v76[0]) = v14;
  }
  if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
  {
    WdLogSingleEntry0(1);
    WdLogGlobalForLineNumber = 2650;
    DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
  }
  v15 = *((_QWORD *)this + 7);
  v16 = *((unsigned __int8 *)this + 579);
  LOBYTE(v3) = *((_BYTE *)this + 582) == 0;
  v17 = *((_DWORD *)this + 6);
  v18 = *((_QWORD *)this + 13);
  v19 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, int, int, __int64, __int64, _DWORD))(*(_QWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 304968LL) + 432LL);
  v20 = *(_QWORD *)(*((_QWORD *)this + 6) + 24LL);
  v21 = (*(__int64 (__fastcall **)(CFlipToken *))(*(_QWORD *)this + 112LL))(this);
  v19(*((_QWORD *)this + 6), *((unsigned int *)this + 30), v21, v18, v17, v16, v3, v20, v15, v76[0]);
  result = (unsigned int)v75;
  if ( (v75 & 0x80000000) == 0LL )
  {
    v23 = *((_QWORD *)this + 6);
    v24 = v23 + 48;
    KeEnterCriticalRegion();
    ExAcquirePushLockExclusiveEx(v23 + 48, 0);
    *(_QWORD *)(v23 + 56) = PsGetCurrentThreadId();
    CPresentRate::NotifyFrame((CPresentRate *)(v23 + 96));
    if ( *(_QWORD *)(v23 + 192) )
    {
      v51 = 0;
      v25 = -1073741275;
      if ( *(_DWORD *)(v23 + 160) )
      {
        for ( j = *(_QWORD **)(v23 + 144); j != (_QWORD *)(v23 + 144); j = (_QWORD *)*j )
        {
          if ( *(j - 1) == *((_QWORD *)this + 7) )
          {
            v51 = (struct CCompositionBuffer *)(j - 3);
            v25 = 0;
            break;
          }
        }
      }
      if ( v25 >= 0 )
      {
        v75 = 0;
        v76[0] = 0;
        memset(v77, 0, 0x1C8u);
        v53 = CFlipExBuffer::FromBuffer(v51);
        inserted = CFlipExBuffer::InsertCascadedTokenWait(v53, &v75, v76);
        v25 = inserted;
        if ( inserted >= 0
          || inserted == -1073741267
          && (CFlipExBuffer::DisableCascadedSignaling(v53),
              LOBYTE(v55) = 1,
              v25 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)(v23 + 192) + 32LL))(
                      *(_QWORD *)(v23 + 192),
                      v55),
              v25 >= 0)
          && (v25 = CCompositionSurface::PairBind((CCompositionSurface *)(v23 + 40), v53), v25 >= 0)
          && (v25 = CFlipExBuffer::InsertCascadedTokenWait(v53, &v75, v76), v25 >= 0) )
        {
          if ( (*(unsigned __int8 (__fastcall **)(CFlipToken *))(*(_QWORD *)this + 168LL))(this) )
          {
            v56 = (char *)this + 120;
            v57 = 3;
            v58 = v77;
            do
            {
              v58 += 128;
              v59 = *(_OWORD *)v56;
              v60 = *((_OWORD *)v56 + 1);
              v56 += 128;
              *((_OWORD *)v58 - 8) = v59;
              v61 = *((_OWORD *)v56 - 6);
              *((_OWORD *)v58 - 7) = v60;
              v62 = *((_OWORD *)v56 - 5);
              *((_OWORD *)v58 - 6) = v61;
              v63 = *((_OWORD *)v56 - 4);
              *((_OWORD *)v58 - 5) = v62;
              v64 = *((_OWORD *)v56 - 3);
              *((_OWORD *)v58 - 4) = v63;
              v65 = *((_OWORD *)v56 - 2);
              *((_OWORD *)v58 - 3) = v64;
              v66 = *((_OWORD *)v56 - 1);
              *((_OWORD *)v58 - 2) = v65;
              *((_OWORD *)v58 - 1) = v66;
              --v57;
            }
            while ( v57 );
            v67 = v75;
            v68 = *((_OWORD *)v56 + 1);
            *(_OWORD *)v58 = *(_OWORD *)v56;
            v69 = *((_OWORD *)v56 + 2);
            *((_OWORD *)v58 + 1) = v68;
            v70 = *((_OWORD *)v56 + 3);
            v71 = *((_QWORD *)v56 + 8);
            *((_OWORD *)v58 + 2) = v69;
            *((_OWORD *)v58 + 3) = v70;
            *((_QWORD *)v58 + 8) = v71;
            v72 = *(_QWORD *)(v23 + 192);
            v73 = v76[0];
            v25 = (*(__int64 (__fastcall **)(__int64, unsigned __int64, unsigned __int64, _BYTE *))(*(_QWORD *)v72 + 40LL))(
                    v72,
                    v67,
                    v76[0],
                    v77);
            if ( v25 < 0 )
              CFlipExBuffer::InsertCascadedTokenSignal(v53, v73);
          }
        }
      }
    }
    else
    {
      v25 = 0;
    }
    if ( PsGetCurrentThreadId() == *(HANDLE *)(v24 + 8) )
    {
      *(_QWORD *)(v24 + 8) = 0;
      ExReleasePushLockExclusiveEx(v24, 0);
    }
    else
    {
      ExReleasePushLockSharedEx(v24, 0);
    }
    KeLeaveCriticalRegion();
    if ( v25 < 0 || *((_BYTE *)this + 582) )
    {
      return (unsigned int)v25;
    }
    else
    {
      v26 = *((_QWORD *)this + 6);
      v27 = *((_QWORD *)this + 7);
      v74 = 0;
      *((_DWORD *)this + 6) = 3;
      KeEnterCriticalRegion();
      v28 = v26 + 48;
      ExAcquirePushLockSharedEx(v26 + 48, 0);
      if ( *(_DWORD *)(v26 + 160) )
      {
        v29 = (_QWORD **)(v26 + 144);
        for ( k = *v29; k != v29; k = (_QWORD *)*k )
        {
          if ( *(k - 1) == v27 )
          {
            v31 = (*(__int64 (__fastcall **)(_QWORD *))(*(k - 3) + 40LL))(k - 3);
            goto LABEL_31;
          }
        }
      }
      v31 = 0;
LABEL_31:
      if ( PsGetCurrentThreadId() == *(HANDLE *)(v28 + 8) )
      {
        *(_QWORD *)(v28 + 8) = 0;
        ExReleasePushLockExclusiveEx(v28, 0);
      }
      else
      {
        ExReleasePushLockSharedEx(v28, 0);
      }
      KeLeaveCriticalRegion();
      LODWORD(v76[0]) = v31;
      if ( !*(_QWORD *)&DXGGLOBAL::m_pGlobal )
      {
        WdLogSingleEntry0(1);
        WdLogGlobalForLineNumber = 2650;
        DxgkLogInternalTriageEvent(0, 262146, -1, (unsigned int)L"m_pGlobal != NULL", 2650, 0, 0, 0, 0);
      }
      v32 = *((_QWORD *)this + 7);
      v33 = *((unsigned __int8 *)this + 579);
      v34 = *((_BYTE *)this + 582) == 0;
      v35 = *((_DWORD *)this + 6);
      v36 = *((_QWORD *)this + 13);
      v37 = *(void (__fastcall **)(_QWORD, _QWORD, _QWORD, __int64, int, int, BOOL, __int64, __int64, _DWORD))(*(_QWORD *)(*(_QWORD *)&DXGGLOBAL::m_pGlobal + 304968LL) + 432LL);
      v38 = *(_QWORD *)(*((_QWORD *)this + 6) + 24LL);
      v39 = (*(__int64 (__fastcall **)(CFlipToken *))(*(_QWORD *)this + 112LL))(this);
      v37(*((_QWORD *)this + 6), *((unsigned int *)this + 30), v39, v36, v35, v33, v34, v38, v32, v76[0]);
      v40 = (_QWORD *)*((_QWORD *)this + 6);
      v74 = 0;
      KeEnterCriticalRegion();
      ExAcquirePushLockExclusiveEx(v40 + 6, 0);
      v40[7] = PsGetCurrentThreadId();
      v41 = CCompositionSurface::NotifyTokenInFrame((CCompositionSurface *)(v40 + 5), this, &v74, 0);
      v42 = (CPushLock *)(v40 + 6);
      LODWORD(v40) = v41;
      CPushLock::ReleaseLock(v42);
      return (unsigned int)v40;
    }
  }
  return result;
}

```

## disassembly

```asm
0x14000ae00  mov     [rsp+arg_10], rbx
0x14000ae05  push    rbp
0x14000ae06  push    rsi
0x14000ae07  push    rdi
0x14000ae08  push    r12
0x14000ae0a  push    r13
0x14000ae0c  push    r14
0x14000ae0e  push    r15
0x14000ae10  sub     rsp, 260h
0x14000ae17  mov     rax, cs:__security_cookie
0x14000ae1e  xor     rax, rsp
0x14000ae21  mov     [rsp+298h+var_48], rax
0x14000ae29  xor     ebp, ebp
0x14000ae2b  movzx   esi, r8b
0x14000ae2f  mov     [rcx+18h], ebp
0x14000ae32  mov     rbx, rdx
0x14000ae35  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, rbp; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14000ae3c  mov     r13, rcx
0x14000ae3f  jz      loc_14000B846
0x14000ae45  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14000ae4c  mov     rcx, [rax+4A748h]
0x14000ae53  mov     rax, [rcx+28h]
0x14000ae57  lea     rcx, [r13+60h]
0x14000ae5b  call    _guard_dispatch_icall
0x14000ae60  mov     edi, eax
0x14000ae62  mov     dword ptr [rsp+298h+var_230], eax
0x14000ae66  mov     rax, [r13+0]
0x14000ae6a  mov     rcx, r13
0x14000ae6d  test    edi, edi
0x14000ae6f  jns     loc_14000B288
0x14000ae75  mov     rax, [rax+38h]
0x14000ae79  call    _guard_dispatch_icall
0x14000ae7e  jmp     short loc_14000AE99
0x14000ae80  mov     dword ptr [rsp+298h+var_230], edi
0x14000ae84  test    cl, cl
0x14000ae86  jnz     loc_14000B59D
0x14000ae8c  test    dword ptr [rbx+2Ch], 20000000h
0x14000ae93  jnz     loc_14000B56C
0x14000ae99  cmp     dword ptr [r13+18h], 3
0x14000ae9e  mov     dword ptr [rsp+298h+var_228], ebp
0x14000aea2  jnz     loc_14000AF47
0x14000aea8  mov     rbx, [r13+30h]
0x14000aeac  mov     rsi, [r13+38h]
0x14000aeb0  call    cs:__imp_KeEnterCriticalRegion
0x14000aeb7  nop     dword ptr [rax+rax+00h]
0x14000aebc  lea     rdi, [rbx+30h]
0x14000aec0  xor     edx, edx
0x14000aec2  mov     rcx, rdi
0x14000aec5  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000aecc  nop     dword ptr [rax+rax+00h]
0x14000aed1  cmp     [rbx+0A0h], ebp
0x14000aed7  jbe     loc_14000B596
0x14000aedd  add     rbx, 90h
0x14000aee4  mov     rax, [rbx]
0x14000aee7  cmp     rax, rbx
0x14000aeea  jz      loc_14000B596
0x14000aef0  cmp     [rax-8], rsi
0x14000aef4  lea     rcx, [rax-18h]
0x14000aef8  jnz     loc_14000B519
0x14000aefe  mov     rax, [rcx]
0x14000af01  mov     rax, [rax+28h]
0x14000af05  call    _guard_dispatch_icall
0x14000af0a  movzx   ebx, al
0x14000af0d  call    cs:__imp_PsGetCurrentThreadId
0x14000af14  nop     dword ptr [rax+rax+00h]
0x14000af19  xor     edx, edx
0x14000af1b  mov     rcx, rdi
0x14000af1e  cmp     rax, [rdi+8]
0x14000af22  jz      loc_14000B25A
0x14000af28  call    cs:__imp_ExReleasePushLockSharedEx
0x14000af2f  nop     dword ptr [rax+rax+00h]
0x14000af34  call    cs:__imp_KeLeaveCriticalRegion
0x14000af3b  nop     dword ptr [rax+rax+00h]
0x14000af40  movzx   eax, bl
0x14000af43  mov     dword ptr [rsp+298h+var_228], eax
0x14000af47  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, rbp; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14000af4e  jz      loc_14000B89C
0x14000af54  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14000af5b  cmp     [r13+246h], bpl
0x14000af62  mov     r15, [r13+38h]
0x14000af66  movzx   edi, byte ptr [r13+243h]
0x14000af6e  setz    bpl
0x14000af72  mov     rcx, [rax+4A748h]
0x14000af79  mov     rax, [r13+30h]
0x14000af7d  mov     esi, [r13+18h]
0x14000af81  mov     rbx, [r13+68h]
0x14000af85  mov     r12, [rcx+1B0h]
0x14000af8c  mov     rcx, r13
0x14000af8f  mov     r14, [rax+18h]
0x14000af93  mov     rax, [r13+0]
0x14000af97  mov     rax, [rax+70h]
0x14000af9b  call    _guard_dispatch_icall
0x14000afa0  mov     ecx, dword ptr [rsp+298h+var_228]
0x14000afa4  mov     r8d, eax
0x14000afa7  mov     edx, [r13+78h]
0x14000afab  mov     r9, rbx
0x14000afae  mov     [rsp+298h+var_250], ecx
0x14000afb2  mov     rax, r12
0x14000afb5  mov     rcx, [r13+30h]
0x14000afb9  mov     [rsp+298h+var_258], r15
0x14000afbe  mov     [rsp+298h+var_260], r14
0x14000afc3  mov     dword ptr [rsp+298h+var_268], ebp
0x14000afc7  mov     dword ptr [rsp+298h+var_270], edi
0x14000afcb  mov     dword ptr [rsp+298h+var_278], esi
0x14000afcf  call    _guard_dispatch_icall
0x14000afd4  mov     eax, dword ptr [rsp+298h+var_230]
0x14000afd8  test    eax, eax
0x14000afda  js      loc_14000B211
0x14000afe0  mov     rbx, [r13+30h]
0x14000afe4  lea     rdi, [rbx+30h]
0x14000afe8  call    cs:__imp_KeEnterCriticalRegion
0x14000afef  nop     dword ptr [rax+rax+00h]
0x14000aff4  xor     edx, edx
0x14000aff6  mov     rcx, rdi
0x14000aff9  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b000  nop     dword ptr [rax+rax+00h]
0x14000b005  call    cs:__imp_PsGetCurrentThreadId
0x14000b00c  nop     dword ptr [rax+rax+00h]
0x14000b011  lea     rcx, [rbx+60h]; this
0x14000b015  mov     [rdi+8], rax
0x14000b019  call    ?NotifyFrame@CPresentRate@@QEAAXXZ; CPresentRate::NotifyFrame(void)
0x14000b01e  cmp     qword ptr [rbx+0C0h], 0
0x14000b026  jnz     loc_14000B62C
0x14000b02c  xor     esi, esi
0x14000b02e  call    cs:__imp_PsGetCurrentThreadId
0x14000b035  nop     dword ptr [rax+rax+00h]
0x14000b03a  xor     edx, edx
0x14000b03c  mov     rcx, rdi
0x14000b03f  cmp     rax, [rdi+8]
0x14000b043  jz      loc_14000B241
0x14000b049  call    cs:__imp_ExReleasePushLockSharedEx
0x14000b050  nop     dword ptr [rax+rax+00h]
0x14000b055  call    cs:__imp_KeLeaveCriticalRegion
0x14000b05c  nop     dword ptr [rax+rax+00h]
0x14000b061  test    esi, esi
0x14000b063  js      loc_14000B23D
0x14000b069  cmp     byte ptr [r13+246h], 0
0x14000b071  jnz     loc_14000B23D
0x14000b077  mov     rdi, [r13+30h]
0x14000b07b  mov     rsi, [r13+38h]
0x14000b07f  mov     [rsp+298h+var_238], 0
0x14000b084  mov     dword ptr [r13+18h], 3
0x14000b08c  call    cs:__imp_KeEnterCriticalRegion
0x14000b093  nop     dword ptr [rax+rax+00h]
0x14000b098  lea     rbx, [rdi+30h]
0x14000b09c  xor     edx, edx
0x14000b09e  mov     rcx, rbx
0x14000b0a1  call    cs:__imp_ExAcquirePushLockSharedEx
0x14000b0a8  nop     dword ptr [rax+rax+00h]
0x14000b0ad  cmp     dword ptr [rdi+0A0h], 0
0x14000b0b4  jbe     loc_14000B624
0x14000b0ba  add     rdi, 90h
0x14000b0c1  mov     rax, [rdi]
0x14000b0c4  cmp     rax, rdi
0x14000b0c7  jz      loc_14000B624
0x14000b0cd  cmp     [rax-8], rsi
0x14000b0d1  lea     rcx, [rax-18h]
0x14000b0d5  jnz     loc_14000B521
0x14000b0db  mov     rax, [rcx]
0x14000b0de  mov     rax, [rax+28h]
0x14000b0e2  call    _guard_dispatch_icall
0x14000b0e7  movzx   edi, al
0x14000b0ea  call    cs:__imp_PsGetCurrentThreadId
0x14000b0f1  nop     dword ptr [rax+rax+00h]
0x14000b0f6  xor     edx, edx
0x14000b0f8  mov     rcx, rbx
0x14000b0fb  cmp     rax, [rbx+8]
0x14000b0ff  jz      loc_14000B26F
0x14000b105  call    cs:__imp_ExReleasePushLockSharedEx
0x14000b10c  nop     dword ptr [rax+rax+00h]
0x14000b111  call    cs:__imp_KeLeaveCriticalRegion
0x14000b118  nop     dword ptr [rax+rax+00h]
0x14000b11d  cmp     cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA, 0; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14000b125  movzx   eax, dil
0x14000b129  mov     dword ptr [rsp+298h+var_228], eax
0x14000b12d  jz      loc_14000B8F2
0x14000b133  mov     rax, cs:?m_pGlobal@DXGGLOBAL@@0PEAV1@EA; DXGGLOBAL * DXGGLOBAL::m_pGlobal
0x14000b13a  xor     r14d, r14d
0x14000b13d  cmp     [r13+246h], r14b
0x14000b144  mov     r15, [r13+38h]
0x14000b148  movzx   ebx, byte ptr [r13+243h]
0x14000b150  setz    r14b
0x14000b154  mov     rcx, [rax+4A748h]
0x14000b15b  mov     rax, [r13+30h]
0x14000b15f  mov     edi, [r13+18h]
0x14000b163  mov     rsi, [r13+68h]
0x14000b167  mov     r12, [rcx+1B0h]
0x14000b16e  mov     rcx, r13
0x14000b171  mov     rbp, [rax+18h]
0x14000b175  mov     rax, [r13+0]
0x14000b179  mov     rax, [rax+70h]
0x14000b17d  call    _guard_dispatch_icall
0x14000b182  mov     ecx, dword ptr [rsp+298h+var_228]
0x14000b186  mov     r8d, eax
0x14000b189  mov     edx, [r13+78h]
0x14000b18d  mov     r9, rsi
0x14000b190  mov     [rsp+298h+var_250], ecx
0x14000b194  mov     rax, r12
0x14000b197  mov     rcx, [r13+30h]
0x14000b19b  mov     [rsp+298h+var_258], r15
0x14000b1a0  mov     [rsp+298h+var_260], rbp
0x14000b1a5  mov     dword ptr [rsp+298h+var_268], r14d
0x14000b1aa  mov     dword ptr [rsp+298h+var_270], ebx
0x14000b1ae  mov     dword ptr [rsp+298h+var_278], edi
0x14000b1b2  call    _guard_dispatch_icall
0x14000b1b7  mov     rbx, [r13+30h]
0x14000b1bb  mov     [rsp+298h+var_238], 0
0x14000b1c0  lea     rdi, [rbx+30h]
0x14000b1c4  call    cs:__imp_KeEnterCriticalRegion
0x14000b1cb  nop     dword ptr [rax+rax+00h]
0x14000b1d0  xor     edx, edx
0x14000b1d2  mov     rcx, rdi
0x14000b1d5  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000b1dc  nop     dword ptr [rax+rax+00h]
0x14000b1e1  call    cs:__imp_PsGetCurrentThreadId
0x14000b1e8  nop     dword ptr [rax+rax+00h]
0x14000b1ed  xor     r9d, r9d; unsigned __int64
0x14000b1f0  lea     r8, [rsp+298h+var_238]; bool *
0x14000b1f5  lea     rcx, [rbx+28h]; this
0x14000b1f9  mov     [rdi+8], rax
0x14000b1fd  mov     rdx, r13; struct CToken *
0x14000b200  call    ?NotifyTokenInFrame@CCompositionSurface@@IEAAJAEBVCToken@@PEA_N_K@Z; CCompositionSurface::NotifyTokenInFrame(CToken const &,bool *,unsigned __int64)
0x14000b205  mov     rcx, rdi; this
0x14000b208  mov     ebx, eax
0x14000b20a  call    ?ReleaseLock@CPushLock@@QEBAXXZ; CPushLock::ReleaseLock(void)
0x14000b20f  mov     eax, ebx
0x14000b211  mov     rcx, [rsp+298h+var_48]
0x14000b219  xor     rcx, rsp; StackCookie
0x14000b21c  call    __security_check_cookie
0x14000b221  mov     rbx, [rsp+298h+arg_10]
0x14000b229  add     rsp, 260h
0x14000b230  pop     r15
0x14000b232  pop     r14
0x14000b234  pop     r13
0x14000b236  pop     r12
0x14000b238  pop     rdi
0x14000b239  pop     rsi
0x14000b23a  pop     rbp
0x14000b23b  retn
0x14000b23d  mov     eax, esi
0x14000b23f  jmp     short loc_14000B211
0x14000b241  mov     qword ptr [rdi+8], 0
0x14000b249  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b250  nop     dword ptr [rax+rax+00h]
0x14000b255  jmp     loc_14000B055
0x14000b25a  mov     [rdi+8], rbp
0x14000b25e  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b265  nop     dword ptr [rax+rax+00h]
0x14000b26a  jmp     loc_14000AF34
0x14000b26f  mov     qword ptr [rbx+8], 0
0x14000b277  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000b27e  nop     dword ptr [rax+rax+00h]
0x14000b283  jmp     loc_14000B111
0x14000b288  mov     rax, [rax+18h]
0x14000b28c  call    _guard_dispatch_icall
0x14000b291  mov     eax, [rbx+2Ch]
0x14000b294  and     eax, 180h
0x14000b299  test    eax, 0FFFFFF7Fh
0x14000b29e  jnz     loc_14000B529
0x14000b2a4  mov     edi, ebp
0x14000b2a6  mov     dword ptr [rsp+298h+var_230], ebp
0x14000b2aa  test    edi, edi
0x14000b2ac  js      loc_14000B61B
0x14000b2b2  mov     rax, [rbx]
0x14000b2b5  mov     [r13+68h], rax
0x14000b2b9  mov     eax, [rbx+58h]
0x14000b2bc  cmp     [rbx+50h], eax
0x14000b2bf  jl      loc_14000B542
0x14000b2c5  mov     eax, [rbx+28h]
0x14000b2c8  mov     [r13+80h], eax
0x14000b2cf  mov     eax, [rbx+68h]
0x14000b2d2  mov     [r13+7Ch], eax
0x14000b2d6  mov     eax, [rbx+1Ch]
0x14000b2d9  mov     [r13+78h], eax
0x14000b2dd  mov     eax, [rbx+30Ch]
0x14000b2e3  mov     [r13+0E4h], eax
0x14000b2ea  mov     eax, [rbx+2Ch]
0x14000b2ed  shr     eax, 17h
0x14000b2f0  and     al, 1
0x14000b2f2  mov     [r13+84h], al
0x14000b2f9  mov     eax, [rbx+2Ch]
0x14000b2fc  shr     eax, 1
0x14000b2fe  and     al, 1
0x14000b300  mov     [r13+86h], al
0x14000b307  mov     eax, [rbx+2Ch]
0x14000b30a  shr     eax, 3
0x14000b30d  and     al, 1
0x14000b30f  mov     [r13+98h], al
0x14000b316  mov     eax, [rbx+2Ch]
0x14000b319  shr     eax, 4
0x14000b31c  and     al, 1
0x14000b31e  mov     [r13+99h], al
0x14000b325  mov     eax, [rbx+2Ch]
0x14000b328  shr     eax, 5
0x14000b32b  and     al, 1
0x14000b32d  mov     [r13+85h], al
0x14000b334  mov     ecx, [rbx+2Ch]
0x14000b337  shr     ecx, 6
0x14000b33a  and     cl, 1
0x14000b33d  mov     [r13+9Ah], cl
  ... truncated ...
```
