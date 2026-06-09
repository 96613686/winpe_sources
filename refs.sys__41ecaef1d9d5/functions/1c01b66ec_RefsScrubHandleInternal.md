# RefsScrubHandleInternal

- ea: `0x1c01b66ec`
- end: `0x1c01b79f7`
- name: `RefsScrubHandleInternal`
- size: `4875`
- prototype: ``
- caller_count: `1`
- callee_count: `24`
- tags: `loader_planting, installer_update`

## callers

- `0x1c01b610c`

## callees

- `0x1c0004300`
- `0x1c000f770`
- `0x1c0063db0`
- `0x1c0068168`
- `0x1c0068960`
- `0x1c006acc0`
- `0x1c006af80`
- `0x1c0093ddc`
- `0x1c0099530`
- `0x1c0099924`
- `0x1c0099b3c`
- `0x1c00b22d8`
- `0x1c00b30ec`
- `0x1c00b3140`
- `0x1c00b3170`
- `0x1c00b3234`
- `0x1c00b3244`
- `0x1c00b3294`
- `0x1c00b32c0`
- `0x1c01632d4`
- `0x1c01971b8`
- `0x1c0199ed8`
- `0x1c019a088`
- `0x1c01b66ec`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x1c01b75e9`
- `ntoskrnl!ExAcquireFastMutex` at `0x1c01b75e9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01b7612`
- `ntoskrnl!ExReleaseFastMutex` at `0x1c01b7612`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6cff`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6dad`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6e83`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6f4d`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b7016`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b7116`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b71c1`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b72a5`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b739a`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b746e`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b757e`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6cff`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6dad`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6e83`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b6f4d`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b7016`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b7116`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b71c1`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b72a5`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b739a`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b746e`
- `ntoskrnl!PsIsThreadTerminating` at `0x1c01b757e`

## pseudocode

```c
__int64 __fastcall RefsScrubHandleInternal(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  __int64 v7; // rax
  int v8; // esi
  __int64 v9; // r14
  __int64 v10; // r8
  _DWORD *v11; // r15
  unsigned int v12; // edx
  unsigned int v14; // eax
  __int64 v15; // rax
  int v16; // ecx
  int v17; // eax
  int v18; // r9d
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r8
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  __int64 v26; // rbx
  __int64 v27; // r13
  int v28; // r8d
  __int64 v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rcx
  __int64 v34; // rcx
  _QWORD *v35; // rdi
  __int64 v36; // r13
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rcx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  __int64 v44; // rdi
  __int64 v45; // r13
  __int64 v46; // rcx
  __int64 v47; // rcx
  int v48; // r8d
  __int64 v49; // rcx
  __int64 v50; // rcx
  int v51; // edx
  __int64 v52; // r8
  int v53; // r9d
  unsigned __int8 v54; // al
  __int64 v55; // rcx
  __int64 v56; // rcx
  __int64 v57; // rcx
  __int64 v58; // rcx
  unsigned int v59; // r8d
  unsigned __int8 v60; // al
  __int64 v61; // rcx
  __int64 v62; // rcx
  unsigned __int8 v63; // al
  __int64 v64; // rcx
  unsigned __int64 v65; // rsi
  struct _SmsCancelScrub *v66; // rdx
  __int64 v67; // rdx
  _DWORD *v68; // r12
  __int64 v69; // r15
  _WORD *v70; // rdx
  unsigned __int16 v71; // ax
  __int64 v72; // rdi
  size_t v73; // rbx
  void *v74; // rcx
  __int64 v75; // r13
  _WORD *v76; // rdx
  unsigned __int16 v77; // ax
  size_t v78; // rbx
  __int64 v79; // rcx
  unsigned int Status; // [rsp+40h] [rbp-C8h]
  char v82; // [rsp+50h] [rbp-B8h]
  unsigned int v83; // [rsp+54h] [rbp-B4h] BYREF
  __int64 v84; // [rsp+58h] [rbp-B0h]
  __int64 v85; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+68h] [rbp-A0h]
  __int64 v87; // [rsp+70h] [rbp-98h]
  __int64 v88; // [rsp+78h] [rbp-90h]
  __int128 v89; // [rsp+80h] [rbp-88h]
  PETHREAD CurrentThread; // [rsp+90h] [rbp-78h]
  _OWORD v91[3]; // [rsp+98h] [rbp-70h] BYREF

  v86 = a2;
  v85 = 0;
  v83 = 0x100000;
  v87 = *(_QWORD *)(a4 + 120);
  v7 = *(_QWORD *)(a4 + 128);
  v84 = v7;
  v8 = 0;
  Status = 0;
  v9 = *(_QWORD *)(a2 + 24);
  v10 = *(_QWORD *)(a2 + 184);
  v88 = v10;
  v11 = (_DWORD *)(v9 + 128);
  v12 = *(_DWORD *)(v10 + 16);
  if ( v12 < 0x80 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 431, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return 3221225485LL;
    goto LABEL_59;
  }
  if ( *(_DWORD *)v9 != 944 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 432, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
    }
    if ( !RefsStatusDebugEnabled )
      return 3221225485LL;
    goto LABEL_59;
  }
  if ( *(_DWORD *)(v7 + 304) < 2u && (*(_DWORD *)(v9 + 4) & 0x18) == 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 433, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221226617LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073740679);
    return 3221226617LL;
  }
  if ( (*(_DWORD *)(v9 + 4) & 1) != 0 )
  {
    v14 = *(_DWORD *)(v9 + 140);
    if ( v14 > 0x200 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 434, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        return 3221225485LL;
      goto LABEL_59;
    }
    if ( v12 < v14 + 224 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 435, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        return 3221225485LL;
      goto LABEL_59;
    }
  }
  if ( *(_DWORD *)(v10 + 8) < 0x3B0u )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 436, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225507LL);
    }
    if ( RefsStatusDebugEnabled )
      RefsStatusDebug(-1073741789);
    return 3221225507LL;
  }
  if ( (*(_DWORD *)(v9 + 4) & 1) != 0 )
  {
    if ( *v11 != 2
      || *(_BYTE *)(v9 + 132) >= 0x18u
      || *(_BYTE *)(v9 + 133) >= 5u
      || *(_BYTE *)(v9 + 134) >= 0xAu
      || (v15 = *(unsigned int *)(v9 + 140), (unsigned int)v15 > 0x3B0)
      || v15 + v9 + 224 > (unsigned __int64)(v9 + 1072) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(WPP_GLOBAL_Control->AttachedDevice, 437, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids, 3221225485LL);
      }
      if ( !RefsStatusDebugEnabled )
        return 3221225485LL;
LABEL_59:
      RefsStatusDebug(-1073741811);
      return 3221225485LL;
    }
  }
  else
  {
    *(_WORD *)(v9 + 132) = 0;
    *(_BYTE *)(v9 + 134) = 9;
    MsInitializeScrubKey(v9 + 128);
    memset((void *)(v9 + 144), 0, 0x50u);
  }
  *v11 = 2;
  v16 = *(_DWORD *)(v9 + 8);
  *(_DWORD *)(v9 + 136) = v16;
  if ( !v16 )
  {
    v16 = 0x7FFFFFFF;
    *(_DWORD *)(v9 + 136) = 0x7FFFFFFF;
  }
  v17 = *(_DWORD *)(v9 + 136);
  if ( v16 < 2 )
    v17 = 2;
  *(_DWORD *)(v9 + 136) = v17;
  memset((void *)(v9 + 736), 0, 0x88u);
  *(_QWORD *)(v9 + 744) = v9 + 224;
  v19 = *(_DWORD *)(v9 + 140);
  *(_DWORD *)(v9 + 736) = v19;
  *(_QWORD *)(v9 + 760) = v9 + 224;
  *(_DWORD *)(v9 + 752) = v19;
  v20 = *(_DWORD *)(v9 + 4);
  v21 = 1;
  if ( (v20 & 2) != 0 )
  {
    *(_DWORD *)(v9 + 768) |= 1u;
    v20 = *(_DWORD *)(v9 + 4);
  }
  if ( (v20 & 4) != 0 )
  {
    *(_DWORD *)(v9 + 768) |= 4u;
    v20 = *(_DWORD *)(v9 + 4);
  }
  if ( (v20 & 8) != 0 )
  {
    *(_DWORD *)(v9 + 768) |= 8u;
    v20 = *(_DWORD *)(v9 + 4);
  }
  if ( (v20 & 0x40) != 0 )
    *(_DWORD *)(v9 + 768) |= 0x10u;
  *(_QWORD *)(v9 + 832) = v9 + 872;
  *(_WORD *)(v9 + 872) = 24;
  v22 = 0;
  *(_WORD *)(*(_QWORD *)(v9 + 832) + 2LL) = 0;
  *(_WORD *)(*(_QWORD *)(v9 + 832) + 4LL) = 0;
  *(_WORD *)(*(_QWORD *)(v9 + 832) + 6LL) = 4;
  v23 = *(_DWORD *)(v88 + 8);
  if ( v23 > 0x3B0 )
  {
    v24 = v23 - 944;
    if ( v24 >= 0x4000 )
      LOWORD(v24) = 0x4000;
    *(_WORD *)(*(_QWORD *)(v9 + 832) + 6LL) += (unsigned __int16)v24 >> 4;
  }
  *(_QWORD *)(v9 + 824) = v91;
  memset(v91, 0, sizeof(v91));
  if ( a5 != 4 )
  {
    if ( (unsigned __int16)(*(_WORD *)a4 - 2051) <= 1u )
    {
      v82 = 0;
      v67 = a3;
      v26 = a1;
      v8 = MsScrubTable(*(_QWORD *)(a1 + 24), v67, *(_QWORD *)(a4 + 384), v9 + 128);
      Status = v8;
      goto LABEL_231;
    }
    v82 = 1;
    if ( (*(_DWORD *)(a4 + 136) & 8) != 0 )
    {
      v8 = 0;
      Status = 0;
      goto LABEL_85;
    }
    v63 = *(_BYTE *)(v9 + 133);
    if ( v63 <= 1u )
    {
      v8 = MsScrubTable(*(_QWORD *)(a1 + 24), a3, *(_QWORD *)(v87 + 240), v9 + 128);
      Status = v8;
      if ( v8 < 0 )
        goto LABEL_85;
      if ( *(int *)(v9 + 136) <= 0 )
        goto LABEL_94;
      if ( **(_BYTE **)a3 )
        goto LABEL_94;
      if ( (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0 )
        goto LABEL_94;
      CurrentThread = KeGetCurrentThread();
      if ( PsIsThreadTerminating(CurrentThread)
        || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
        || (unsigned __int8)((__int64 (*)(void))MsScrubContextParityExtentDataFull)() )
      {
        goto LABEL_94;
      }
      *(_BYTE *)(v9 + 133) = 2;
      MsInitializeScrubKey(v64);
    }
    else if ( v63 != 2 && v63 != 4 )
    {
      goto LABEL_85;
    }
    LOBYTE(v18) = 1;
    RefsCreateMdlAndBuffer(a1, v21, v22, v18, (__int64)&v83, v22, (__int64)&v85);
    ExAcquireFastMutex(*(PFAST_MUTEX *)(a4 + 48));
    _InterlockedAdd((volatile signed __int32 *)(a4 + 156), 1u);
    v88 = *(_QWORD *)(a4 + 32);
    _InterlockedAdd((volatile signed __int32 *)(a4 + 156), 1u);
    ExReleaseFastMutex(*(PFAST_MUTEX *)(a4 + 48));
    v65 = ~(*(unsigned int *)(v84 + 276) - 1LL) & (v88 + (unsigned int)(*(_DWORD *)(v84 + 276) - 1));
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qDi(
        WPP_GLOBAL_Control->AttachedDevice,
        438,
        WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
        *(_QWORD *)(a4 + 360),
        v83,
        v65);
    }
    if ( (*(_DWORD *)(v87 + 160) & 0x20000) != 0 || (*(_BYTE *)(v9 + 4) & 0x10) != 0 )
      *(_DWORD *)(v9 + 768) |= 2u;
    v66 = (struct _SmsCancelScrub *)a3;
    v26 = a1;
    v8 = MsScrubStream(
           *(struct CmsTransactionContext **)(a1 + 24),
           v66,
           *(CmsStream **)(a4 + 360),
           v83,
           v65,
           (struct _SCB *)a4,
           (struct _SmsScrubContext *)(v9 + 128));
    Status = v8;
    if ( (*(_DWORD *)(v87 + 160) & 0x20000) != 0 || (*(_BYTE *)(v9 + 4) & 0x10) != 0 )
      *(_DWORD *)(v9 + 768) &= ~2u;
    goto LABEL_231;
  }
  v82 = 0;
  v25 = *(unsigned __int8 *)(v9 + 132);
  if ( v25 <= 0x13 )
  {
    if ( v25 == 19 )
    {
      v35 = (_QWORD *)v84;
      v36 = a1;
LABEL_130:
      if ( v35[22] != v22 )
      {
        MsScrubSetTableIndex(19, v9 + 128);
        v8 = MsScrubTable(*(_QWORD *)(v36 + 24), a3, v35[22], v9 + 128);
        Status = v8;
        MsScrubClearTableIndex(v9 + 128);
        LODWORD(v22) = 0;
      }
      if ( v8 < 0 )
        goto LABEL_85;
      if ( *(_DWORD *)(v9 + 136) <= (int)v22
        || **(_BYTE **)a3 != (_BYTE)v22
        || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
        || (unsigned __int8)MsScrubContextParityExtentDataFull(v39) )
      {
        goto LABEL_94;
      }
      *(_WORD *)(v9 + 132) = 20;
      MsInitializeScrubKey(v40);
      v8 = Status;
      goto LABEL_147;
    }
    if ( v25 <= 1 )
    {
      v27 = a1;
      if ( (*(_DWORD *)(v9 + 768) & 1) == 0 )
      {
        v8 = RefsScrubBootSector(a1, v86, v9 + 128);
        Status = v8;
      }
      *(_WORD *)(v9 + 132) = 2;
      MsInitializeScrubKey(v9 + 128);
      if ( v8 < 0 )
        goto LABEL_85;
      if ( *(_DWORD *)(v9 + 136) <= v28
        || **(_BYTE **)a3 != (_BYTE)v28
        || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
        || (unsigned __int8)MsScrubContextParityExtentDataFull(v9 + 128) )
      {
        goto LABEL_94;
      }
      *(_WORD *)(v9 + 132) = 2;
      MsInitializeScrubKey(v29);
    }
    else
    {
      if ( v25 > 0x10 )
      {
        if ( v25 != 17 )
        {
          v35 = (_QWORD *)v84;
LABEL_118:
          if ( v35[12] == v22 )
          {
            v36 = a1;
          }
          else
          {
            MsScrubSetTableIndex(18, v9 + 128);
            v36 = a1;
            v8 = MsScrubTable(*(_QWORD *)(a1 + 24), a3, v35[12], v9 + 128);
            Status = v8;
            MsScrubClearTableIndex(v9 + 128);
            LODWORD(v22) = 0;
          }
          if ( v8 < 0 )
            goto LABEL_85;
          if ( *(_DWORD *)(v9 + 136) <= (int)v22
            || **(_BYTE **)a3 != (_BYTE)v22
            || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
            || PsIsThreadTerminating(KeGetCurrentThread())
            || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
            || (unsigned __int8)MsScrubContextParityExtentDataFull(v37) )
          {
            goto LABEL_94;
          }
          *(_WORD *)(v9 + 132) = 19;
          MsInitializeScrubKey(v38);
          v8 = Status;
          goto LABEL_130;
        }
        v35 = (_QWORD *)v84;
        v27 = a1;
LABEL_107:
        v32 = v35[10];
        if ( v32 && *(_QWORD *)(v32 + 384) != v22 )
        {
          MsScrubSetTableIndex(17, v9 + 128);
          v8 = MsScrubTable(*(_QWORD *)(v27 + 24), a3, *(_QWORD *)(v35[10] + 384LL), v9 + 128);
          Status = v8;
          MsScrubClearTableIndex(v9 + 128);
          LODWORD(v22) = 0;
        }
        if ( v8 < 0 )
          goto LABEL_85;
        if ( *(_DWORD *)(v9 + 136) <= (int)v22
          || **(_BYTE **)a3 != (_BYTE)v22
          || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
          || PsIsThreadTerminating(KeGetCurrentThread())
          || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
          || (unsigned __int8)MsScrubContextParityExtentDataFull(v33) )
        {
          goto LABEL_94;
        }
        *(_WORD *)(v9 + 132) = 18;
        MsInitializeScrubKey(v34);
        v8 = Status;
        goto LABEL_118;
      }
      v27 = a1;
    }
    v35 = (_QWORD *)v84;
    v8 = MsScrubVolumeMetaData(
           *(struct CmsTransactionContext **)(v27 + 24),
           (struct _SmsCancelScrub *)a3,
           *(CmsVolume **)(v84 + 104));
    Status = v8;
    if ( v8 < 0 )
      goto LABEL_85;
    RefsCheckpointCurrentTransaction(v27);
    RefsBindMinstoreTransaction(v27);
    if ( *(int *)(v9 + 136) <= 0
      || **(_BYTE **)a3
      || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
      || (unsigned __int8)MsScrubContextParityExtentDataFull(v30) )
    {
      goto LABEL_94;
    }
    *(_WORD *)(v9 + 132) = 17;
    MsInitializeScrubKey(v31);
    goto LABEL_107;
  }
  v41 = v25 - 20;
  if ( !v41 )
  {
    v35 = (_QWORD *)v84;
LABEL_147:
    if ( v35[23] == v22 )
    {
      v45 = a1;
    }
    else
    {
      MsScrubSetTableIndex(20, v9 + 128);
      v45 = a1;
      v8 = MsScrubTable(*(_QWORD *)(a1 + 24), a3, v35[23], v9 + 128);
      Status = v8;
      MsScrubClearTableIndex(v9 + 128);
      LODWORD(v22) = 0;
    }
    if ( v8 < 0 )
      goto LABEL_85;
    if ( *(_DWORD *)(v9 + 136) > (int)v22
      && **(_BYTE **)a3 == (_BYTE)v22
      && (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) == 0
      && !PsIsThreadTerminating(KeGetCurrentThread())
      && !(unsigned __int8)MsScrubContextFoundError(v9 + 128)
      && !(unsigned __int8)MsScrubContextParityExtentDataFull(v46) )
    {
      *(_WORD *)(v9 + 132) = 21;
      MsInitializeScrubKey(v47);
      goto LABEL_159;
    }
LABEL_94:
    v8 = -2147483643;
    Status = -2147483643;
    goto LABEL_85;
  }
  v42 = v41 - 1;
  if ( v42 )
  {
    v43 = v42 - 1;
    if ( v43 )
    {
      if ( v43 != 1 )
        goto LABEL_85;
      v44 = v84;
      goto LABEL_191;
    }
    v45 = a1;
    goto LABEL_167;
  }
  v45 = a1;
LABEL_159:
  v8 = RefsScrubVerifyBlock(v45, v86, v9 + 128);
  Status = v8;
  *(_WORD *)(v9 + 132) = 22;
  MsInitializeScrubKey(v9 + 128);
  if ( v8 < 0 )
    goto LABEL_85;
  if ( *(_DWORD *)(v9 + 136) <= v48
    || **(_BYTE **)a3 != (_BYTE)v48
    || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
    || PsIsThreadTerminating(KeGetCurrentThread())
    || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
    || (unsigned __int8)MsScrubContextParityExtentDataFull(v49) )
  {
    goto LABEL_94;
  }
  *(_WORD *)(v9 + 132) = 22;
  MsInitializeScrubKey(v50);
LABEL_167:
  v44 = v84;
  if ( *(_QWORD *)(v84 + 64) == v22 )
    goto LABEL_183;
  MsScrubSetTableIndex(22, v9 + 128);
  v54 = *(_BYTE *)(v9 + 133);
  if ( v54 > 1u )
  {
    if ( v54 != 2 && v54 != 4 )
      goto LABEL_182;
LABEL_180:
    LOBYTE(v53) = 1;
    RefsCreateMdlAndBuffer(v45, v51, v52, v53, (__int64)&v83, v52, (__int64)&v85);
    v8 = MsScrubStream(
           *(struct CmsTransactionContext **)(v45 + 24),
           (struct _SmsCancelScrub *)a3,
           *(CmsStream **)(*(_QWORD *)(v44 + 64) + 360LL),
           v83,
           0xFFFFFFFF00000000uLL,
           0,
           (struct _SmsScrubContext *)(v9 + 128));
    Status = v8;
    goto LABEL_182;
  }
  v8 = MsScrubTable(
         *(_QWORD *)(v45 + 24),
         a3,
         *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v84 + 64) + 120LL) + 240LL),
         v9 + 128);
  Status = v8;
  if ( v8 >= 0 )
  {
    if ( *(int *)(v9 + 136) <= 0
      || **(_BYTE **)a3
      || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
      || PsIsThreadTerminating(KeGetCurrentThread())
      || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
      || (unsigned __int8)MsScrubContextParityExtentDataFull(v55) )
    {
      v8 = -2147483643;
      Status = -2147483643;
      goto LABEL_182;
    }
    *(_BYTE *)(v9 + 133) = 2;
    MsInitializeScrubKey(v56);
    goto LABEL_180;
  }
LABEL_182:
  MsScrubClearTableIndex(v9 + 128);
LABEL_183:
  if ( v8 < 0 )
    goto LABEL_85;
  if ( *(_DWORD *)(v9 + 136) <= (int)v22
    || **(_BYTE **)a3 != (_BYTE)v22
    || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
    || PsIsThreadTerminating(KeGetCurrentThread())
    || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
    || (unsigned __int8)MsScrubContextParityExtentDataFull(v57) )
  {
    goto LABEL_94;
  }
  *(_WORD *)(v9 + 132) = 23;
  MsInitializeScrubKey(v58);
  v8 = Status;
LABEL_191:
  if ( *(_QWORD *)(v44 + 40) != v22 )
  {
    MsScrubSetTableIndex(23, v9 + 128);
    v60 = *(_BYTE *)(v9 + 133);
    if ( v60 <= 1u )
    {
      v8 = MsScrubTable(
             *(_QWORD *)(a1 + 24),
             a3,
             *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(v44 + 40) + 120LL) + 240LL),
             v9 + 128);
      Status = v8;
      if ( v8 < 0 )
      {
LABEL_206:
        MsScrubClearTableIndex(v9 + 128);
        goto LABEL_85;
      }
      if ( *(int *)(v9 + 136) <= 0
        || **(_BYTE **)a3
        || (**(_DWORD **)(a3 + 8) & *(_DWORD *)(a3 + 16)) != 0
        || PsIsThreadTerminating(KeGetCurrentThread())
        || (unsigned __int8)MsScrubContextFoundError(v9 + 128)
        || (unsigned __int8)MsScrubContextParityExtentDataFull(v61) )
      {
        v8 = -2147483643;
        Status = -2147483643;
        goto LABEL_206;
      }
      *(_BYTE *)(v9 + 133) = 2;
      MsInitializeScrubKey(v62);
    }
    else if ( v60 != 2 && v60 != 4 )
    {
      goto LABEL_206;
    }
    v8 = v59;
    Status = v59;
    goto LABEL_206;
  }
LABEL_85:
  v26 = a1;
LABEL_231:
  *(_DWORD *)(v9 + 4) = 0;
  if ( v8 == -2147483643 )
  {
    v89 = 0;
    *(_DWORD *)v9 = 944;
    *(_QWORD *)(v9 + 4) = 1;
    v8 = 0;
    v68 = (_DWORD *)(v9 + 736);
    if ( *(_DWORD *)(v9 + 736) == 16 )
      v89 = *(_OWORD *)*(_QWORD *)(v9 + 744);
    LOBYTE(v21) = v82;
    RefsScrubConvertMsScrubContextToScrubOutput(v9, v21);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_iDLLD(
        WPP_GLOBAL_Control->AttachedDevice,
        *(unsigned __int8 *)(v9 + 132),
        WPP_GLOBAL_Control,
        v89,
        *v68,
        *(unsigned __int8 *)(v9 + 132),
        *(unsigned __int8 *)(v9 + 133),
        *(unsigned __int16 *)(*(_QWORD *)(v9 + 832) + 4LL),
        0);
    }
    *(_DWORD *)(v9 + 140) = *v68;
    v69 = v86;
    *(_QWORD *)(v86 + 56) = 128;
    *(_QWORD *)(v69 + 56) = 224;
    *(_QWORD *)(v69 + 56) = *(unsigned int *)(v9 + 140) + 224LL;
    *(_WORD *)(v9 + 56) = *(_WORD *)(v9 + 140) + 96;
    *(_DWORD *)(v9 + 4) |= 0x40000u;
    v70 = *(_WORD **)(v9 + 832);
    v71 = v70[2];
    if ( v71 )
    {
      v72 = *(unsigned __int16 *)(v69 + 56);
      v73 = 16LL * v71 + 8;
      memmove((void *)(v9 + v72), v70, v73);
      *(_WORD *)(v9 + 58) = v72;
      *(_DWORD *)(v9 + 4) |= 0x20000u;
      *(_QWORD *)(v69 + 56) += v73;
    }
    v74 = (void *)(v9 + 736);
  }
  else
  {
    if ( v8 < 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x100) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          440,
          WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
          (unsigned int)v8);
      }
      if ( RefsStatusDebugEnabled )
        RefsStatusDebug(Status);
      RefsRaiseStatusInternal(v26, Status);
    }
    *(_DWORD *)v9 = 944;
    *(_DWORD *)(v9 + 8) = 0;
    v75 = v86;
    *(_QWORD *)(v86 + 56) = 128;
    v76 = *(_WORD **)(v9 + 832);
    v77 = v76[2];
    if ( v77 )
    {
      v78 = 16LL * v77 + 8;
      memmove((void *)(v9 + 128), v76, v78);
      *(_WORD *)(v9 + 58) = 128;
      *(_DWORD *)(v9 + 4) |= 0x20000u;
      *(_QWORD *)(v75 + 56) += v78;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_D(
          WPP_GLOBAL_Control->AttachedDevice,
          441,
          WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids,
          *(unsigned __int16 *)(*(_QWORD *)(v9 + 832) + 4LL));
      }
    }
    LOBYTE(v76) = v82;
    RefsScrubConvertMsScrubContextToScrubOutput(v9, v76);
    v74 = (void *)(v9 + 736);
  }
  memset(v74, 0, 0x88u);
  if ( v85 )
    RefsDeleteMdlAndBuffer(v79, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1c01b66ec  push    rbx
0x1c01b66ee  push    rsi
0x1c01b66ef  push    rdi
0x1c01b66f0  push    r12
0x1c01b66f2  push    r13
0x1c01b66f4  push    r14
0x1c01b66f6  push    r15
0x1c01b66f8  sub     rsp, 0D0h
0x1c01b66ff  mov     rax, cs:__security_cookie
0x1c01b6706  xor     rax, rsp
0x1c01b6709  mov     [rsp+108h+var_40], rax
0x1c01b6711  mov     r13, r9
0x1c01b6714  mov     rbx, r8
0x1c01b6717  mov     [rsp+108h+var_A0], rdx
0x1c01b671c  mov     [rsp+108h+var_C0], rcx
0x1c01b6721  xor     r12d, r12d
0x1c01b6724  mov     [rsp+108h+var_A8], r12
0x1c01b6729  mov     [rsp+108h+var_B4], 100000h
0x1c01b6731  mov     rax, [r9+78h]
0x1c01b6735  mov     [rsp+108h+var_98], rax
0x1c01b673a  mov     rax, [r9+80h]
0x1c01b6741  mov     [rsp+108h+var_B0], rax
0x1c01b6746  mov     esi, r12d
0x1c01b6749  mov     [rsp+108h+Status], r12d
0x1c01b674e  mov     r14, [rdx+18h]
0x1c01b6752  mov     r8, [rdx+0B8h]
0x1c01b6759  mov     [rsp+108h+var_90], r8
0x1c01b675e  lea     r15, [r14+80h]
0x1c01b6765  mov     edx, [r8+10h]
0x1c01b6769  mov     ecx, 80h
0x1c01b676e  cmp     edx, ecx
0x1c01b6770  jnb     short loc_1C01B67CE
0x1c01b6772  lea     rdi, WPP_GLOBAL_Control
0x1c01b6779  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b6780  cmp     rcx, rdi
0x1c01b6783  jz      short loc_1C01B67B5
0x1c01b6785  test    dword ptr [rcx+2Ch], 100h
0x1c01b678c  jz      short loc_1C01B67B5
0x1c01b678e  mov     r12d, 4
0x1c01b6794  cmp     [rcx+29h], r12b
0x1c01b6798  jb      short loc_1C01B67B5
0x1c01b679a  mov     edx, 1AFh
0x1c01b679f  mov     r9d, 0C000000Dh
0x1c01b67a5  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b67ac  mov     rcx, [rcx+18h]
0x1c01b67b0  call    WPP_SF_D
0x1c01b67b5  mov     al, cs:RefsStatusDebugEnabled
0x1c01b67bb  test    al, al
0x1c01b67bd  jz      loc_1C01B6AC2
0x1c01b67c3  mov     r8d, 3C8Dh
0x1c01b67c9  jmp     loc_1C01B6AB1
0x1c01b67ce  mov     r10d, 3B0h
0x1c01b67d4  cmp     [r14], r10d
0x1c01b67d7  jz      short loc_1C01B6835
0x1c01b67d9  lea     rdi, WPP_GLOBAL_Control
0x1c01b67e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b67e7  cmp     rcx, rdi
0x1c01b67ea  jz      short loc_1C01B681C
0x1c01b67ec  test    dword ptr [rcx+2Ch], 100h
0x1c01b67f3  jz      short loc_1C01B681C
0x1c01b67f5  mov     r12d, 4
0x1c01b67fb  cmp     [rcx+29h], r12b
0x1c01b67ff  jb      short loc_1C01B681C
0x1c01b6801  mov     edx, 1B0h
0x1c01b6806  mov     r9d, 0C000000Dh
0x1c01b680c  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b6813  mov     rcx, [rcx+18h]
0x1c01b6817  call    WPP_SF_D
0x1c01b681c  mov     al, cs:RefsStatusDebugEnabled
0x1c01b6822  test    al, al
0x1c01b6824  jz      loc_1C01B6AC2
0x1c01b682a  mov     r8d, 3C96h
0x1c01b6830  jmp     loc_1C01B6AB1
0x1c01b6835  mov     r9d, 2
0x1c01b683b  lea     edi, [r9+16h]
0x1c01b683f  cmp     [rax+130h], r9d
0x1c01b6846  jnb     short loc_1C01B68BE
0x1c01b6848  mov     eax, [r14+4]
0x1c01b684c  test    dil, al
0x1c01b684f  jnz     short loc_1C01B68BE
0x1c01b6851  lea     rdi, WPP_GLOBAL_Control
0x1c01b6858  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b685f  cmp     rcx, rdi
0x1c01b6862  jz      short loc_1C01B6892
0x1c01b6864  test    dword ptr [rcx+2Ch], 100h
0x1c01b686b  jz      short loc_1C01B6892
0x1c01b686d  lea     r12d, [r9+2]
0x1c01b6871  cmp     [rcx+29h], r12b
0x1c01b6875  jb      short loc_1C01B6892
0x1c01b6877  mov     edx, 1B1h
0x1c01b687c  mov     r9d, 0C0000479h
0x1c01b6882  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b6889  mov     rcx, [rcx+18h]
0x1c01b688d  call    WPP_SF_D
0x1c01b6892  mov     al, cs:RefsStatusDebugEnabled
0x1c01b6898  test    al, al
0x1c01b689a  jz      short loc_1C01B68B3
0x1c01b689c  mov     r8d, 3CA6h
0x1c01b68a2  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b68a9  mov     ecx, 0C0000479h; Status
0x1c01b68ae  call    RefsStatusDebug
0x1c01b68b3  mov     eax, 0C0000479h
0x1c01b68b8  jmp     loc_1C01B79B3
0x1c01b68be  mov     ecx, [r14+4]
0x1c01b68c2  and     ecx, 1
0x1c01b68c5  jz      loc_1C01B699A
0x1c01b68cb  mov     eax, [r14+8Ch]
0x1c01b68d2  cmp     eax, 200h
0x1c01b68d7  jbe     short loc_1C01B6935
0x1c01b68d9  lea     rdi, WPP_GLOBAL_Control
0x1c01b68e0  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b68e7  cmp     rcx, rdi
0x1c01b68ea  jz      short loc_1C01B691C
0x1c01b68ec  test    dword ptr [rcx+2Ch], 100h
0x1c01b68f3  jz      short loc_1C01B691C
0x1c01b68f5  mov     r12d, 4
0x1c01b68fb  cmp     [rcx+29h], r12b
0x1c01b68ff  jb      short loc_1C01B691C
0x1c01b6901  mov     edx, 1B2h
0x1c01b6906  mov     r9d, 0C000000Dh
0x1c01b690c  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b6913  mov     rcx, [rcx+18h]
0x1c01b6917  call    WPP_SF_D
0x1c01b691c  mov     al, cs:RefsStatusDebugEnabled
0x1c01b6922  test    al, al
0x1c01b6924  jz      loc_1C01B6AC2
0x1c01b692a  mov     r8d, 3CB2h
0x1c01b6930  jmp     loc_1C01B6AB1
0x1c01b6935  add     eax, 0E0h
0x1c01b693a  cmp     edx, eax
0x1c01b693c  jnb     short loc_1C01B699A
0x1c01b693e  lea     rdi, WPP_GLOBAL_Control
0x1c01b6945  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b694c  cmp     rcx, rdi
0x1c01b694f  jz      short loc_1C01B6981
0x1c01b6951  test    dword ptr [rcx+2Ch], 100h
0x1c01b6958  jz      short loc_1C01B6981
0x1c01b695a  mov     r12d, 4
0x1c01b6960  cmp     [rcx+29h], r12b
0x1c01b6964  jb      short loc_1C01B6981
0x1c01b6966  mov     edx, 1B3h
0x1c01b696b  mov     r9d, 0C000000Dh
0x1c01b6971  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b6978  mov     rcx, [rcx+18h]
0x1c01b697c  call    WPP_SF_D
0x1c01b6981  mov     al, cs:RefsStatusDebugEnabled
0x1c01b6987  test    al, al
0x1c01b6989  jz      loc_1C01B6AC2
0x1c01b698f  mov     r8d, 3CBAh
0x1c01b6995  jmp     loc_1C01B6AB1
0x1c01b699a  cmp     [r8+8], r10d
0x1c01b699e  jnb     short loc_1C01B6A0E
0x1c01b69a0  lea     rdi, WPP_GLOBAL_Control
0x1c01b69a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b69ae  cmp     rcx, rdi
0x1c01b69b1  jz      short loc_1C01B69E3
0x1c01b69b3  test    dword ptr [rcx+2Ch], 100h
0x1c01b69ba  jz      short loc_1C01B69E3
0x1c01b69bc  mov     r12d, 4
0x1c01b69c2  cmp     [rcx+29h], r12b
0x1c01b69c6  jb      short loc_1C01B69E3
0x1c01b69c8  mov     edx, 1B4h
0x1c01b69cd  mov     r9d, 0C0000023h
0x1c01b69d3  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b69da  mov     rcx, [rcx+18h]
0x1c01b69de  call    WPP_SF_D
0x1c01b69e3  mov     al, cs:RefsStatusDebugEnabled
0x1c01b69e9  test    al, al
0x1c01b69eb  jz      short loc_1C01B6A04
0x1c01b69ed  mov     r8d, 3CC5h
0x1c01b69f3  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b69fa  mov     ecx, 0C0000023h; Status
0x1c01b69ff  call    RefsStatusDebug
0x1c01b6a04  mov     eax, 0C0000023h
0x1c01b6a09  jmp     loc_1C01B79B3
0x1c01b6a0e  test    ecx, ecx
0x1c01b6a10  jz      loc_1C01B6ACC
0x1c01b6a16  cmp     [r15], r9d
0x1c01b6a19  jnz     short loc_1C01B6A5E
0x1c01b6a1b  cmp     [r14+84h], dil
0x1c01b6a22  jnb     short loc_1C01B6A5E
0x1c01b6a24  cmp     byte ptr [r14+85h], 5
0x1c01b6a2c  jnb     short loc_1C01B6A5E
0x1c01b6a2e  cmp     byte ptr [r14+86h], 0Ah
0x1c01b6a36  jnb     short loc_1C01B6A5E
0x1c01b6a38  mov     eax, [r14+8Ch]
0x1c01b6a3f  cmp     eax, r10d
0x1c01b6a42  ja      short loc_1C01B6A5E
0x1c01b6a44  lea     rcx, [r14+0E0h]
0x1c01b6a4b  add     rcx, rax
0x1c01b6a4e  lea     rax, [r14+430h]
0x1c01b6a55  cmp     rcx, rax
0x1c01b6a58  jbe     loc_1C01B6AFC
0x1c01b6a5e  lea     rdi, WPP_GLOBAL_Control
0x1c01b6a65  mov     rcx, cs:WPP_GLOBAL_Control
0x1c01b6a6c  cmp     rcx, rdi
0x1c01b6a6f  jz      short loc_1C01B6AA1
0x1c01b6a71  test    dword ptr [rcx+2Ch], 100h
0x1c01b6a78  jz      short loc_1C01B6AA1
0x1c01b6a7a  mov     r12d, 4
0x1c01b6a80  cmp     [rcx+29h], r12b
0x1c01b6a84  jb      short loc_1C01B6AA1
0x1c01b6a86  mov     edx, 1B5h
0x1c01b6a8b  mov     r9d, 0C000000Dh
0x1c01b6a91  lea     r8, WPP_c36f31a1ca0b3c923a8bdb6c6ea39488_Traceguids
0x1c01b6a98  mov     rcx, [rcx+18h]
0x1c01b6a9c  call    WPP_SF_D
0x1c01b6aa1  mov     al, cs:RefsStatusDebugEnabled
0x1c01b6aa7  test    al, al
0x1c01b6aa9  jz      short loc_1C01B6AC2
0x1c01b6aab  mov     r8d, 3CD7h
0x1c01b6ab1  lea     rdx, aFsctrlC; "FsCtrl.c"
0x1c01b6ab8  mov     ecx, 0C000000Dh; Status
0x1c01b6abd  call    RefsStatusDebug
0x1c01b6ac2  mov     eax, 0C000000Dh
0x1c01b6ac7  jmp     loc_1C01B79B3
0x1c01b6acc  mov     [r14+84h], r12w
0x1c01b6ad4  mov     byte ptr [r14+86h], 9
0x1c01b6adc  mov     rcx, r15
0x1c01b6adf  call    MsInitializeScrubKey
0x1c01b6ae4  lea     rcx, [r14+90h]; void *
0x1c01b6aeb  xor     edx, edx; Val
0x1c01b6aed  lea     r8d, [rdx+50h]; Size
0x1c01b6af1  call    memset
0x1c01b6af6  mov     r9d, 2
0x1c01b6afc  mov     [r15], r9d
0x1c01b6aff  mov     ecx, [r14+8]
0x1c01b6b03  mov     [r14+88h], ecx
0x1c01b6b0a  test    ecx, ecx
0x1c01b6b0c  jnz     short loc_1C01B6B1A
0x1c01b6b0e  mov     ecx, 7FFFFFFFh
0x1c01b6b13  mov     [r14+88h], ecx
0x1c01b6b1a  mov     eax, [r14+88h]
0x1c01b6b21  cmp     ecx, r9d
0x1c01b6b24  cmovl   eax, r9d
0x1c01b6b28  mov     [r14+88h], eax
0x1c01b6b2f  lea     r12, [r14+2E0h]
0x1c01b6b36  xor     edx, edx; Val
0x1c01b6b38  mov     r8d, 88h; Size
0x1c01b6b3e  mov     rcx, r12; void *
0x1c01b6b41  call    memset
0x1c01b6b46  lea     rcx, [r14+0E0h]
0x1c01b6b4d  mov     [r14+2E8h], rcx
0x1c01b6b54  mov     eax, [r14+8Ch]
0x1c01b6b5b  mov     [r12], eax
0x1c01b6b5f  mov     [r14+2F8h], rcx
0x1c01b6b66  mov     [r14+2F0h], eax
0x1c01b6b6d  mov     eax, [r14+4]
0x1c01b6b71  mov     edx, 1
0x1c01b6b76  test    al, 2
0x1c01b6b78  jz      short loc_1C01B6B85
0x1c01b6b7a  or      [r14+300h], edx
0x1c01b6b81  mov     eax, [r14+4]
0x1c01b6b85  mov     r12d, 4
0x1c01b6b8b  test    r12b, al
0x1c01b6b8e  jz      short loc_1C01B6B9B
0x1c01b6b90  or      [r14+300h], r12d
0x1c01b6b97  mov     eax, [r14+4]
0x1c01b6b9b  test    al, 8
0x1c01b6b9d  jz      short loc_1C01B6BAB
0x1c01b6b9f  or      dword ptr [r14+300h], 8
0x1c01b6ba7  mov     eax, [r14+4]
0x1c01b6bab  test    al, 40h
0x1c01b6bad  jz      short loc_1C01B6BB7
0x1c01b6baf  or      dword ptr [r14+300h], 10h
0x1c01b6bb7  lea     rax, [r14+368h]
0x1c01b6bbe  mov     [r14+340h], rax
0x1c01b6bc5  mov     [rax], di
0x1c01b6bc8  mov     rax, [r14+340h]
0x1c01b6bcf  xor     r8d, r8d
0x1c01b6bd2  mov     [rax+2], r8w
0x1c01b6bd7  mov     rax, [r14+340h]
0x1c01b6bde  mov     [rax+4], r8w
0x1c01b6be3  mov     rax, [r14+340h]
0x1c01b6bea  mov     [rax+6], r12w
0x1c01b6bef  mov     rax, [rsp+108h+var_90]
0x1c01b6bf4  mov     ecx, [rax+8]
0x1c01b6bf7  cmp     ecx, 3B0h
0x1c01b6bfd  jbe     short loc_1C01B6C1E
0x1c01b6bff  add     ecx, 0FFFFFC50h
0x1c01b6c05  mov     eax, 4000h
0x1c01b6c0a  cmp     ecx, eax
0x1c01b6c0c  cmovnb  ecx, eax
0x1c01b6c0f  mov     rax, [r14+340h]
0x1c01b6c16  shr     cx, 4
0x1c01b6c1a  add     [rax+6], cx
0x1c01b6c1e  lea     rax, [rsp+108h+var_70]
0x1c01b6c26  mov     [r14+338h], rax
0x1c01b6c2d  xorps   xmm0, xmm0
0x1c01b6c30  movups  [rsp+108h+var_70], xmm0
0x1c01b6c38  movups  [rsp+108h+var_60], xmm0
0x1c01b6c40  movups  [rsp+108h+var_50], xmm0
0x1c01b6c48  cmp     [rsp+108h+arg_20], r12d
0x1c01b6c50  jnz     loc_1C01B74C3
0x1c01b6c56  mov     [rsp+108h+var_B8], r8b
0x1c01b6c5b  movzx   ecx, byte ptr [r14+84h]
0x1c01b6c63  cmp     ecx, 13h
0x1c01b6c66  ja      loc_1C01B705F
0x1c01b6c6c  jz      loc_1C01B6F96
0x1c01b6c72  cmp     ecx, edx
  ... truncated ...
```
