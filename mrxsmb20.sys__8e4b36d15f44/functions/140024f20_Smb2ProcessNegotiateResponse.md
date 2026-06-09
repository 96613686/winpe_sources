# Smb2ProcessNegotiateResponse

- ea: `0x140024f20`
- end: `0x140025b60`
- name: `Smb2ProcessNegotiateResponse`
- size: `3136`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int, __int64, unsigned int, char, __int64, _DWORD *, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1400576e0`
- `0x140057f20`

## callees

- `0x14000b940`
- `0x1400122d0`
- `0x14001b4c0`
- `0x140024f20`
- `0x140028000`
- `0x140029764`
- `0x1400297a8`
- `0x14002a1dc`
- `0x14002a6a8`
- `0x14002a9ac`
- `0x14002ba20`
- `0x14002caf4`
- `0x140037120`
- `0x1400372c0`
- `0x140056c30`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140025247`
- `ntoskrnl!ExFreePoolWithTag` at `0x140025247`
- `ntoskrnl!RtlCompareMemory` at `0x1400256ac`
- `ntoskrnl!RtlCompareMemory` at `0x1400256ac`
- `ntoskrnl!ExAllocatePool2` at `0x140025122`
- `ntoskrnl!ExAllocatePool2` at `0x140025334`
- `ntoskrnl!ExAllocatePool2` at `0x140025122`
- `ntoskrnl!ExAllocatePool2` at `0x140025334`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140025721`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140025a78`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140025add`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140025721`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140025a78`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140025add`
- `mrxsmb!SmbCryptoHashDestroy` at `0x140025b33`
- `mrxsmb!SmbCryptoHashDestroy` at `0x140025b33`
- `mrxsmb!SmbCeSetServerBufferSizes` at `0x1400258b2`
- `mrxsmb!SmbCeSetServerBufferSizes` at `0x1400258b2`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x140025378`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x1400253f0`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x140025378`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x1400253f0`
- `mrxsmb!SmbCryptoHashGetOutputLength` at `0x140025315`
- `mrxsmb!SmbCryptoHashGetOutputLength` at `0x140025315`
- `mrxsmb!SmbCryptoHashCreate` at `0x1400252fa`
- `mrxsmb!SmbCryptoHashCreate` at `0x1400252fa`
- `mrxsmb!MRxSmbSetServerEntryDialect` at `0x1400250cb`
- `mrxsmb!MRxSmbSetServerEntryDialect` at `0x1400250cb`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140025021`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002503f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400257b9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400257d7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140025851`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140025021`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002503f`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400257b9`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400257d7`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140025851`

## pseudocode

```c
void __fastcall Smb2ProcessNegotiateResponse(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        unsigned int a6,
        char a7,
        __int64 a8,
        _DWORD *a9,
        __int64 a10)
{
  _DWORD *v11; // r15
  int updated; // ebx
  bool v15; // zf
  char v16; // bl
  __int64 v17; // rcx
  __int64 ConfigurationBlock; // rax
  int v19; // r8d
  unsigned int v20; // r15d
  unsigned int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // r8
  unsigned __int64 v24; // rax
  __int64 v25; // rdx
  void *Pool2; // rax
  int v27; // edx
  __int64 v28; // r9
  BOOL v29; // eax
  __int64 v30; // rdx
  __int64 v31; // r8
  void *v32; // rcx
  __int64 v33; // r8
  unsigned int OutputLength; // eax
  __int64 v35; // rax
  int v36; // ecx
  __int64 v37; // r13
  int v38; // ebx
  int v39; // eax
  KIRQL v40; // al
  char v41; // r8
  unsigned __int8 v42; // dl
  char v43; // cl
  __int128 v44; // xmm0
  KIRQL v45; // dl
  int v46; // edx
  int v47; // ecx
  int v48; // edx
  int v49; // ecx
  int v50; // edx
  int v51; // eax
  __int64 v52; // rcx
  __int64 v53; // rax
  int v54; // r8d
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rdx
  char v58; // cl
  int v59; // eax
  unsigned int v60; // eax
  char v61; // cl
  int v62; // r8d
  bool v63; // al
  __int64 v64; // rax
  __int16 v65; // ax
  KIRQL v66; // dl
  int v67; // edi
  KIRQL v68; // dl
  char v69; // [rsp+38h] [rbp-D0h] BYREF
  KIRQL v70; // [rsp+39h] [rbp-CFh] BYREF
  int v71; // [rsp+3Ch] [rbp-CCh]
  int v72; // [rsp+40h] [rbp-C8h] BYREF
  __int16 v73; // [rsp+44h] [rbp-C4h] BYREF
  __int64 v74; // [rsp+48h] [rbp-C0h] BYREF
  __int64 v75; // [rsp+50h] [rbp-B8h]
  __int64 v76; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v77; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v78; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v79; // [rsp+70h] [rbp-98h] BYREF
  __int64 v80; // [rsp+78h] [rbp-90h]
  struct _EVENT_DATA_DESCRIPTOR v81; // [rsp+88h] [rbp-80h] BYREF
  __int64 *v82; // [rsp+A8h] [rbp-60h]
  __int64 v83; // [rsp+B0h] [rbp-58h]
  __int16 *v84; // [rsp+B8h] [rbp-50h]
  __int64 v85; // [rsp+C0h] [rbp-48h]
  __int64 *v86; // [rsp+C8h] [rbp-40h]
  __int64 v87; // [rsp+D0h] [rbp-38h]
  KIRQL *v88; // [rsp+D8h] [rbp-30h]
  __int64 v89; // [rsp+E0h] [rbp-28h]
  char *v90; // [rsp+E8h] [rbp-20h]
  __int64 v91; // [rsp+F0h] [rbp-18h]
  int *v92; // [rsp+F8h] [rbp-10h]
  __int64 v93; // [rsp+100h] [rbp-8h]
  __int64 *v94; // [rsp+108h] [rbp+0h]
  __int64 v95; // [rsp+110h] [rbp+8h]
  __int64 *v96; // [rsp+118h] [rbp+10h]
  __int64 v97; // [rsp+120h] [rbp+18h]

  v11 = a9;
  LODWORD(v74) = a4;
  v77 = a3;
  v75 = (__int64)a9;
  v79 = a8;
  v71 = 0;
  v78 = 0;
  if ( a6 < 0x80 )
  {
    updated = -1073741629;
    Smb2LkmdTelCollectParsingFailure(a10, 0, 1);
LABEL_153:
    v67 = v71;
    goto LABEL_154;
  }
  if ( *(_DWORD *)a5 != 1112364030 )
  {
    updated = -1073741629;
    Smb2LkmdTelCollectParsingFailure(a10, 0, 2);
    goto LABEL_153;
  }
  if ( *(_WORD *)(a5 + 64) != 65 )
  {
    updated = -1073741629;
    Smb2LkmdTelCollectParsingFailure(a10, 0, 3);
    goto LABEL_153;
  }
  v15 = (*(_BYTE *)(a5 + 66) & 1) == 0;
  v16 = a7;
  v80 = *(_QWORD *)(a1 + 24);
  if ( v15 && a7 )
  {
    if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(a1) + 477) && (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 8) != 0 )
    {
      ConfigurationBlock = MRxSmbGetConfigurationBlock(v17);
      McTemplateK0hzr0t_EtwWriteTransfer(
        *(unsigned __int8 *)(ConfigurationBlock + 188),
        (unsigned int)ServerDoesNotSupportSigning,
        v19,
        *(_WORD *)(a1 + 80) >> 1,
        *(_QWORD *)(a1 + 88),
        *(_BYTE *)(ConfigurationBlock + 188));
    }
    a3 = v77;
  }
  v20 = *(unsigned __int16 *)(a5 + 68);
  if ( a4 >= 0x40 && *(_DWORD *)a3 == 1112364030 )
  {
    v21 = *(unsigned __int16 *)(a3 + 66);
    v22 = 0;
    if ( *(_WORD *)(a3 + 66) )
    {
      while ( (_WORD)v20 != *(_WORD *)(a3 + 2 * v22 + 100) )
      {
        v22 = (unsigned int)(v22 + 1);
        if ( (unsigned int)v22 >= v21 )
          goto LABEL_18;
      }
    }
    else
    {
LABEL_18:
      if ( (unsigned int)v22 >= v21 )
      {
        v23 = 4;
LABEL_151:
        updated = -1073741629;
        Smb2LkmdTelCollectParsingFailure(a10, 0, v23);
        goto LABEL_152;
      }
    }
  }
  if ( !a7 )
  {
    v27 = *(unsigned __int16 *)(*(_QWORD *)(a1 + 64) + 8LL);
    if ( (_WORD)v20 == (_WORD)v27 )
      goto LABEL_23;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        31,
        WPP_48214901e2dc3d654588515547715784_Traceguids,
        *(unsigned __int16 *)(a5 + 68),
        v27);
    }
    updated = -1073741616;
LABEL_34:
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_48214901e2dc3d654588515547715784_Traceguids, v20);
    }
    goto LABEL_152;
  }
  updated = MRxSmbSetServerEntryDialect(a1, (unsigned __int16)v20);
  if ( updated < 0 )
    goto LABEL_34;
  v16 = a7;
LABEL_23:
  v24 = *(unsigned __int16 *)(a5 + 120);
  v25 = *(unsigned __int16 *)(a5 + 122);
  if ( v24 + v25 < v24 || v24 + v25 > a6 )
  {
    v23 = 5;
    goto LABEL_151;
  }
  if ( (_WORD)v25 )
  {
    Pool2 = (void *)ExAllocatePool2(66, v25, 1834182478);
    *(_QWORD *)(a2 + 552) = Pool2;
    if ( !Pool2 )
    {
      updated = -1073741670;
      goto LABEL_152;
    }
    *(_DWORD *)(a2 + 560) = *(unsigned __int16 *)(a5 + 122);
    memmove(Pool2, (const void *)(a5 + *(unsigned __int16 *)(a5 + 120)), *(unsigned __int16 *)(a5 + 122));
  }
  v28 = 768;
  v29 = (unsigned __int16)v20 >= 0x300u;
  *(_DWORD *)(a2 + 600) = v29;
  if ( v16 )
    *(_WORD *)(a1 + 744) = v29;
  v30 = 1;
  v31 = 767;
  if ( (unsigned __int16)v20 < 0x311u )
  {
    v36 = *(_DWORD *)(a5 + 88);
    v37 = v80;
    if ( (_WORD)v20 == 767 )
    {
      LOBYTE(v31) = 0;
      v38 = *(_DWORD *)(a5 + 88) & 1;
      LOBYTE(v36) = 0;
      v69 = 0;
      LODWORD(v74) = v36;
      LOBYTE(v72) = 0;
      LOBYTE(v73) = 0;
      goto LABEL_91;
    }
    LOBYTE(v72) = 0;
    LOBYTE(v73) = 0;
    v31 = 528;
    if ( (unsigned __int16)v20 < 0x210u )
    {
      LOBYTE(v31) = 0;
      v38 = v36 & 1;
      v69 = 0;
    }
    else
    {
      v69 = 1;
      v38 = v36 & 7;
    }
  }
  else
  {
    v32 = *(void **)(a2 + 616);
    if ( v32 )
    {
      ExFreePoolWithTag(v32, 0x6D53674Eu);
      *(_QWORD *)(a2 + 616) = 0;
      *(_DWORD *)(a2 + 624) = 0;
    }
    updated = Smb2ProcessNegotiateContexts(a1, a2, a5, a6, v79, a10);
    if ( updated < 0 )
      goto LABEL_152;
    if ( a7 )
    {
      *(_WORD *)(a1 + 742) = *(_WORD *)(a2 + 584);
      *(_WORD *)(a1 + 744) = *(_WORD *)(a2 + 600);
      *(_DWORD *)(a1 + 748) = *(_DWORD *)(a2 + 612);
    }
    else if ( *(unsigned __int16 *)(a1 + 742) != *(_DWORD *)(a2 + 584)
           || *(unsigned __int16 *)(a1 + 744) != *(_DWORD *)(a2 + 600) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_48214901e2dc3d654588515547715784_Traceguids);
      }
      updated = -1073741616;
      goto LABEL_152;
    }
    LOBYTE(v33) = 1;
    updated = SmbCryptoHashCreate(&v78, *(unsigned int *)(a2 + 568), v33);
    if ( updated < 0 )
    {
LABEL_152:
      v11 = (_DWORD *)v75;
      goto LABEL_153;
    }
    OutputLength = SmbCryptoHashGetOutputLength(v78);
    *(_DWORD *)(a2 + 572) = OutputLength;
    v35 = ExAllocatePool2(256, OutputLength, 1834182736);
    *(_QWORD *)(a2 + 576) = v35;
    if ( !v35 )
    {
      *(_DWORD *)(a2 + 572) = 0;
      updated = -1073741670;
      goto LABEL_152;
    }
    updated = SmbCryptoUpdatePreauthIntegrityHashValue(v78, v35, *(unsigned int *)(a2 + 572), v77, v74);
    if ( updated < 0 )
      goto LABEL_152;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_DDq(
        WPP_GLOBAL_Control->AttachedDevice,
        34,
        WPP_48214901e2dc3d654588515547715784_Traceguids,
        **(unsigned int **)(a2 + 576),
        v74,
        a2);
    }
    updated = SmbCryptoUpdatePreauthIntegrityHashValue(v78, *(_QWORD *)(a2 + 576), *(unsigned int *)(a2 + 572), a5, a6);
    if ( updated < 0 )
      goto LABEL_152;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_DDq(
        WPP_GLOBAL_Control->AttachedDevice,
        35,
        WPP_48214901e2dc3d654588515547715784_Traceguids,
        **(unsigned int **)(a2 + 576),
        a6,
        a2);
    }
    v36 = *(_DWORD *)(a5 + 88);
    LOBYTE(v31) = 0;
    v37 = v80;
    LOBYTE(v72) = 0;
    LOBYTE(v73) = 0;
    v30 = 1;
    v38 = v36 & 1 | v36 & 6;
    v69 = 1;
    v28 = 768;
  }
  if ( (unsigned __int16)v20 >= 0x300u )
  {
    LOBYTE(v72) = 1;
    v39 = v38 | v36 & 0xB8;
    if ( (unsigned __int16)v20 >= 0x311u )
    {
      v38 |= v36 & 0xB8;
    }
    else
    {
      v38 = v39 | v36 & 0x40;
      if ( v39 & 0x40 | v36 & 0x40 )
      {
        if ( a7 )
        {
          v28 = v79;
          v36 = 0;
          v31 = *(unsigned __int16 *)(v79 + 16);
          if ( (_WORD)v31 )
          {
            while ( *(_DWORD *)(v79 + 4LL * (unsigned __int16)v36) != 1 )
            {
              LOWORD(v36) = v36 + 1;
              if ( (unsigned __int16)v36 >= (unsigned __int16)v31 )
                goto LABEL_84;
            }
            *(_WORD *)(a1 + 742) = 1;
            *(_DWORD *)(a2 + 584) = 1;
          }
        }
        else if ( *(_WORD *)(a1 + 742) == 1 )
        {
          *(_DWORD *)(a2 + 584) = 1;
        }
      }
    }
LABEL_84:
    if ( (v38 & 8) == 0 && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x800000) != 0 )
      McTemplateK0hzr0_EtwWriteTransfer(
        v36,
        (unsigned int)ServerMultiChannelIncapable,
        v31,
        *(_WORD *)(a1 + 80) >> 1,
        *(_QWORD *)(a1 + 88));
  }
  LODWORD(v74) = (unsigned __int16)v20 >= 0x302u;
  if ( (unsigned __int16)v20 >= 0x311u )
  {
    v15 = *(_DWORD *)(a2 + 584) == 0;
    LOBYTE(v73) = 1;
    if ( !v15 )
      v38 |= 0x40u;
  }
LABEL_91:
  v40 = SmbCeAcquireSpinLock(v37, v30, v31, v28);
  v41 = *(_BYTE *)(a1 + 736);
  v42 = a7;
  v43 = v41 & 0x20;
  v70 = v40;
  if ( a7 )
  {
    if ( !v43 )
    {
      *(_WORD *)(a1 + 672) = *(_WORD *)(a5 + 66);
      *(_DWORD *)(a1 + 676) = v38;
      *(_WORD *)(a1 + 674) = v20;
      v44 = *(_OWORD *)(a5 + 72);
      *(_BYTE *)(a1 + 736) = v41 | 0x20;
      *(_OWORD *)(a1 + 656) = v44;
LABEL_99:
      v45 = v70;
      *(_BYTE *)(a1 + 736) = (4 * (v69 & 9 | (2 * (v72 & 5 | (16 * v73)))))
                           | *(_BYTE *)(a1 + 736) & 0x23
                           | (16 * (v72 & 3 | (4 * v74))) & 0x7F;
      *(_DWORD *)(v37 + 2352) = -1;
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v37 + 1920), v45);
      v46 = (16 * (v38 & 1)) | 0x20;
      if ( (v38 & 2) == 0 )
        v46 = 16 * (v38 & 1);
      v47 = v46 | 0x800;
      if ( (v38 & 4) == 0 )
        v47 = v46;
      v48 = v47 | 0x1000;
      if ( (v38 & 8) == 0 )
        v48 = v47;
      v49 = v48 | 0x2000;
      if ( (v38 & 0x10) == 0 )
        v49 = v48;
      v50 = v49 | 0x4000;
      if ( (v38 & 0x20) == 0 )
        v50 = v49;
      v51 = v50 | 0x8000;
      if ( (v38 & 0x40) == 0 )
        v51 = v50;
      *(_DWORD *)(a1 + 716) = v51;
      if ( (unsigned __int16)v20 < 0x311u && (v51 & 0x8000) != 0 && *(_DWORD *)(a2 + 584) != 1 )
      {
        v51 &= ~0x8000u;
        *(_DWORD *)(a1 + 716) = v51;
      }
      if ( (v51 & 0x8000) == 0
        && a7
        && *(_BYTE *)(MRxSmbGetConfigurationBlock(785) + 476)
        && (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 8) != 0 )
      {
        v53 = MRxSmbGetConfigurationBlock(v52);
        McTemplateK0hzr0t_EtwWriteTransfer(
          *(unsigned __int8 *)(v53 + 189),
          (unsigned int)ServerDoesNotSupportEncryption,
          v54,
          *(_WORD *)(a1 + 80) >> 1,
          *(_QWORD *)(a1 + 88),
          *(_BYTE *)(v53 + 189));
      }
      v55 = *(unsigned __int8 *)(a1 + 736);
      if ( (*(_BYTE *)(a5 + 66) & 2) != 0 )
      {
        LOBYTE(v55) = v55 | 2;
        *(_BYTE *)(a1 + 736) = v55;
        *(_BYTE *)(a2 + 608) = 1;
      }
      else
      {
        LOBYTE(v55) = v55 & 0xFD;
        *(_BYTE *)(a1 + 736) = v55;
      }
      if ( (unsigned __int16)v20 <= 0x2FEu )
        *(_BYTE *)(a1 + 737) = *(_BYTE *)(a1 + 737) & 0xF0 | 0xA;
      v56 = MRxSmbGetConfigurationBlock(v55);
      v57 = *(_QWORD *)(a1 + 656) - *(_QWORD *)(v56 + 68);
      if ( !v57 )
        v57 = *(_QWORD *)(a1 + 664) - *(_QWORD *)(v56 + 76);
      v58 = *(_BYTE *)(a1 + 736);
      v59 = *(_DWORD *)(a1 + 716);
      if ( v57 )
      {
        v60 = v59 & 0xFFFFFF7F;
        v61 = v58 & 0xFE;
      }
      else
      {
        v60 = v59 | 0x80;
        v61 = v58 | 1;
      }
      *(_BYTE *)(a1 + 736) = v61;
      *(_DWORD *)(a1 + 716) = v60;
      updated = SmbCeSetServerBufferSizes(
                  a1,
                  *(unsigned int *)(a5 + 96),
                  *(unsigned int *)(a5 + 100),
                  *(unsigned int *)(a5 + 92));
      if ( !updated
        && (_WORD)v20 != 767
        && (unsigned int)dword_140046050 > 5
        && (qword_140046060 & 0x400000000000LL) != 0
        && (qword_140046068 & 0x400000000000LL) == qword_140046068 )
      {
        v83 = 8;
        v79 = 1;
        v82 = &v79;
        v84 = &v73;
        LODWORD(v77) = *(_DWORD *)(a1 + 716);
        v86 = &v77;
        v63 = (*(_BYTE *)(a1 + 736) & 2) != 0;
        v73 = v20;
        v70 = v63;
        v88 = &v70;
        v90 = &v69;
        v64 = *(_QWORD *)(a2 + 32);
        v85 = 2;
        v87 = 4;
        v89 = 1;
        v69 = a7;
        v91 = 1;
        if ( v64 )
          v65 = *(_WORD *)(v64 + 56);
        else
          v65 = 255;
        LOWORD(v72) = v65;
        v93 = 2;
        v92 = &v72;
        LOWORD(v76) = *(_WORD *)(a2 + 600);
        v94 = &v76;
        LOWORD(v74) = *(_WORD *)(a5 + 66);
        v96 = &v74;
        v95 = 2;
        v97 = 2;
        tlgWriteAgg(1, (int)&byte_1400401B3, v62, 10, &v81);
      }
      goto LABEL_152;
    }
  }
  else if ( !v43 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_48214901e2dc3d654588515547715784_Traceguids, a1, a2);
    }
    v68 = v70;
    updated = -1073741300;
    *(_DWORD *)(v37 + 2352) = -1;
    ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v37 + 1920), v68);
    goto LABEL_152;
  }
  if ( *(_WORD *)(a5 + 66) == *(_WORD *)(a1 + 672) && v38 == *(_DWORD *)(a1 + 676) && (_WORD)v20 == *(_WORD *)(a1 + 674) )
  {
    if ( RtlCompareMemory((const void *)(a5 + 72), (const void *)(a1 + 656), 0x10u) == 16 )
      goto LABEL_99;
    v42 = a7;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqD(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_48214901e2dc3d654588515547715784_Traceguids, a1, a2, v42);
  }
  v66 = v70;
  updated = -1073741300;
  *(_DWORD *)(v37 + 2352) = -1;
  v67 = 5;
  ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v37 + 1920), v66);
  v11 = (_DWORD *)v75;
LABEL_154:
  if ( v78 )
    SmbCryptoHashDestroy();
  v11[1] = v67;
  *v11 = updated;
}

```

## disassembly

```asm
0x140024f20  mov     r11, rsp
0x140024f23  push    rbp
0x140024f24  push    rbx
0x140024f25  push    rdi
0x140024f26  push    r15
0x140024f28  lea     rbp, [r11-78h]
0x140024f2c  sub     rsp, 158h
0x140024f33  mov     rax, cs:__security_cookie
0x140024f3a  xor     rax, rsp
0x140024f3d  mov     [rbp+70h+var_50], rax
0x140024f41  cmp     [rbp+70h+arg_28], 80h
0x140024f4b  mov     rdi, rcx
0x140024f4e  mov     r15, [rbp+70h+arg_40]
0x140024f55  mov     rax, [rbp+70h+arg_38]
0x140024f5c  mov     [r11-28h], rsi
0x140024f60  mov     rsi, rdx
0x140024f63  mov     [r11-30h], r12
0x140024f67  mov     r12d, r9d
0x140024f6a  mov     [r11-38h], r13
0x140024f6e  mov     r13, [rbp+70h+arg_48]
0x140024f75  mov     [r11-40h], r14
0x140024f79  mov     r14, [rbp+70h+arg_20]
0x140024f80  mov     dword ptr [rsp+170h+var_130], r9d
0x140024f85  mov     [rsp+170h+var_118], r8
0x140024f8a  mov     [rsp+170h+var_128], r15
0x140024f8f  mov     [rsp+170h+var_108], rax
0x140024f94  mov     [rsp+170h+var_13C], 0
0x140024f9c  mov     [rsp+170h+var_110], 0
0x140024fa5  jnb     short loc_140024FC1
0x140024fa7  xor     edx, edx
0x140024fa9  mov     r8d, 1
0x140024faf  mov     rcx, r13
0x140024fb2  mov     ebx, 0C00000C3h
0x140024fb7  call    Smb2LkmdTelCollectParsingFailure
0x140024fbc  jmp     loc_140025B05
0x140024fc1  cmp     dword ptr [r14], 424D53FEh
0x140024fc8  jz      short loc_140024FE4
0x140024fca  xor     edx, edx
0x140024fcc  mov     r8d, 2
0x140024fd2  mov     rcx, r13
0x140024fd5  mov     ebx, 0C00000C3h
0x140024fda  call    Smb2LkmdTelCollectParsingFailure
0x140024fdf  jmp     loc_140025B05
0x140024fe4  cmp     word ptr [r14+40h], 41h ; 'A'
0x140024fea  jz      short loc_140025006
0x140024fec  xor     edx, edx
0x140024fee  mov     r8d, 3
0x140024ff4  mov     rcx, r13
0x140024ff7  mov     ebx, 0C00000C3h
0x140024ffc  call    Smb2LkmdTelCollectParsingFailure
0x140025001  jmp     loc_140025B05
0x140025006  test    byte ptr [r14+42h], 1
0x14002500b  mov     rax, [rcx+18h]
0x14002500f  movzx   ebx, [rbp+70h+arg_30]
0x140025016  mov     [rsp+170h+var_100], rax
0x14002501b  jnz     short loc_140025079
0x14002501d  test    bl, bl
0x14002501f  jz      short loc_140025079
0x140025021  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140025028  nop     dword ptr [rax+rax+00h]
0x14002502d  cmp     byte ptr [rax+1DDh], 0
0x140025034  jz      short loc_140025074
0x140025036  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 8
0x14002503d  jz      short loc_140025074
0x14002503f  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140025046  nop     dword ptr [rax+rax+00h]
0x14002504b  movzx   r9d, word ptr [rdi+50h]
0x140025050  lea     rdx, ServerDoesNotSupportSigning
0x140025057  shr     r9w, 1
0x14002505b  movzx   ecx, byte ptr [rax+0BCh]
0x140025062  mov     rax, [rdi+58h]
0x140025066  mov     dword ptr [rsp+170h+var_148], ecx
0x14002506a  mov     [rsp+170h+var_150], rax
0x14002506f  call    McTemplateK0hzr0t_EtwWriteTransfer
0x140025074  mov     r8, [rsp+170h+var_118]
0x140025079  movzx   r15d, word ptr [r14+44h]
0x14002507e  cmp     r12d, 40h ; '@'
0x140025082  jb      short loc_1400250B5
0x140025084  cmp     dword ptr [r8], 424D53FEh
0x14002508b  jnz     short loc_1400250B5
0x14002508d  movzx   edx, word ptr [r8+42h]
0x140025092  xor     ecx, ecx
0x140025094  test    edx, edx
0x140025096  jz      short loc_1400250A6
0x140025098  cmp     r15w, [r8+rcx*2+64h]
0x14002509e  jz      short loc_1400250B5
0x1400250a0  inc     ecx
0x1400250a2  cmp     ecx, edx
0x1400250a4  jb      short loc_140025098
0x1400250a6  cmp     ecx, edx
0x1400250a8  jb      short loc_1400250B5
0x1400250aa  mov     r8d, 4
0x1400250b0  jmp     loc_140025AF1
0x1400250b5  lea     r12, WPP_GLOBAL_Control
0x1400250bc  test    bl, bl
0x1400250be  jz      loc_14002514B
0x1400250c4  movzx   edx, r15w
0x1400250c8  mov     rcx, rdi
0x1400250cb  call    cs:__imp_MRxSmbSetServerEntryDialect
0x1400250d2  nop     dword ptr [rax+rax+00h]
0x1400250d7  mov     ebx, eax
0x1400250d9  test    eax, eax
0x1400250db  js      loc_140025195
0x1400250e1  movzx   ebx, [rbp+70h+arg_30]
0x1400250e8  movzx   eax, word ptr [r14+78h]
0x1400250ed  movzx   edx, word ptr [r14+7Ah]
0x1400250f2  lea     rcx, [rax+rdx]
0x1400250f6  cmp     rcx, rax
0x1400250f9  jb      loc_140025AEB
0x1400250ff  mov     eax, [rbp+70h+arg_28]
0x140025105  cmp     rcx, rax
0x140025108  ja      loc_140025AEB
0x14002510e  test    dx, dx
0x140025111  jz      loc_1400251F4
0x140025117  mov     ecx, 42h ; 'B'
0x14002511c  mov     r8d, 6D53674Eh
0x140025122  call    cs:__imp_ExAllocatePool2
0x140025129  nop     dword ptr [rax+rax+00h]
0x14002512e  mov     [rsi+228h], rax
0x140025135  mov     rcx, rax; void *
0x140025138  test    rax, rax
0x14002513b  jnz     loc_1400251D7
0x140025141  mov     ebx, 0C000009Ah
0x140025146  jmp     loc_140025B00
0x14002514b  mov     rax, [rdi+40h]
0x14002514f  movzx   edx, word ptr [rax+8]
0x140025153  cmp     r15w, dx
0x140025157  jz      short loc_1400250E8
0x140025159  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140025160  cmp     rcx, r12
0x140025163  jz      short loc_140025190
0x140025165  mov     eax, [rcx+2Ch]
0x140025168  test    al, 1
0x14002516a  jz      short loc_140025190
0x14002516c  cmp     byte ptr [rcx+29h], 1
0x140025170  jb      short loc_140025190
0x140025172  mov     rcx, [rcx+18h]
0x140025176  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14002517d  mov     eax, edx
0x14002517f  mov     r9d, r15d
0x140025182  mov     edx, 1Fh
0x140025187  mov     dword ptr [rsp+170h+var_150], eax
0x14002518b  call    WPP_SF_DD
0x140025190  mov     ebx, 0C00000D0h
0x140025195  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002519c  cmp     rcx, r12
0x14002519f  jz      loc_140025B00
0x1400251a5  mov     eax, [rcx+2Ch]
0x1400251a8  test    al, 1
0x1400251aa  jz      loc_140025B00
0x1400251b0  cmp     byte ptr [rcx+29h], 1
0x1400251b4  jb      loc_140025B00
0x1400251ba  mov     rcx, [rcx+18h]
0x1400251be  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x1400251c5  mov     r9d, r15d
0x1400251c8  mov     edx, 20h ; ' '
0x1400251cd  call    WPP_SF_d
0x1400251d2  jmp     loc_140025B00
0x1400251d7  movzx   eax, word ptr [r14+7Ah]
0x1400251dc  mov     [rsi+230h], eax
0x1400251e2  movzx   edx, word ptr [r14+78h]
0x1400251e7  movzx   r8d, word ptr [r14+7Ah]; Size
0x1400251ec  add     rdx, r14; Src
0x1400251ef  call    memmove
0x1400251f4  xor     eax, eax
0x1400251f6  mov     r9d, 300h
0x1400251fc  cmp     r15w, r9w
0x140025200  setnb   al
0x140025203  mov     [rsi+258h], eax
0x140025209  test    bl, bl
0x14002520b  jz      short loc_140025214
0x14002520d  mov     [rdi+2E8h], ax
0x140025214  mov     r10d, 311h
0x14002521a  lea     r12, WPP_GLOBAL_Control
0x140025221  mov     edx, 1
0x140025226  mov     r8d, 2FFh
0x14002522c  cmp     r15w, r10w
0x140025230  jb      loc_1400254C5
0x140025236  mov     rcx, [rsi+268h]; P
0x14002523d  test    rcx, rcx
0x140025240  jz      short loc_140025262
0x140025242  mov     edx, 6D53674Eh; Tag
0x140025247  call    cs:__imp_ExFreePoolWithTag
0x14002524e  nop     dword ptr [rax+rax+00h]
0x140025253  xor     eax, eax
0x140025255  mov     [rsi+268h], rax
0x14002525c  mov     [rsi+270h], eax
0x140025262  mov     rax, [rsp+170h+var_108]
0x140025267  mov     r8, r14
0x14002526a  mov     qword ptr [rsp+170h+var_148], r13
0x14002526f  mov     rdx, rsi
0x140025272  mov     r13d, [rbp+70h+arg_28]
0x140025279  mov     rcx, rdi
0x14002527c  mov     r9d, r13d
0x14002527f  mov     [rsp+170h+var_150], rax
0x140025284  call    Smb2ProcessNegotiateContexts
0x140025289  mov     ebx, eax
0x14002528b  test    eax, eax
0x14002528d  js      loc_140025B00
0x140025293  cmp     [rbp+70h+arg_30], 0
0x14002529a  jz      short loc_1400252C6
0x14002529c  movzx   eax, word ptr [rsi+248h]
0x1400252a3  mov     [rdi+2E6h], ax
0x1400252aa  movzx   eax, word ptr [rsi+258h]
0x1400252b1  mov     [rdi+2E8h], ax
0x1400252b8  mov     eax, [rsi+264h]
0x1400252be  mov     [rdi+2ECh], eax
0x1400252c4  jmp     short loc_1400252EC
0x1400252c6  movzx   eax, word ptr [rdi+2E6h]
0x1400252cd  cmp     eax, [rsi+248h]
0x1400252d3  jnz     loc_140025486
0x1400252d9  movzx   eax, word ptr [rdi+2E8h]
0x1400252e0  cmp     eax, [rsi+258h]
0x1400252e6  jnz     loc_140025486
0x1400252ec  mov     edx, [rsi+238h]
0x1400252f2  lea     rcx, [rsp+170h+var_110]
0x1400252f7  mov     r8b, 1
0x1400252fa  call    cs:__imp_SmbCryptoHashCreate
0x140025301  nop     dword ptr [rax+rax+00h]
0x140025306  mov     ebx, eax
0x140025308  test    eax, eax
0x14002530a  js      loc_140025B00
0x140025310  mov     rcx, [rsp+170h+var_110]
0x140025315  call    cs:__imp_SmbCryptoHashGetOutputLength
0x14002531c  nop     dword ptr [rax+rax+00h]
0x140025321  mov     edx, eax
0x140025323  mov     ecx, 100h
0x140025328  mov     r8d, 6D536850h
0x14002532e  mov     [rsi+23Ch], edx
0x140025334  call    cs:__imp_ExAllocatePool2
0x14002533b  nop     dword ptr [rax+rax+00h]
0x140025340  mov     [rsi+240h], rax
0x140025347  test    rax, rax
0x14002534a  jnz     short loc_14002535C
0x14002534c  mov     [rsi+23Ch], eax
0x140025352  mov     ebx, 0C000009Ah
0x140025357  jmp     loc_140025B00
0x14002535c  mov     ecx, dword ptr [rsp+170h+var_130]
0x140025360  mov     rdx, rax
0x140025363  mov     r9, [rsp+170h+var_118]
0x140025368  mov     r8d, [rsi+23Ch]
0x14002536f  mov     dword ptr [rsp+170h+var_150], ecx
0x140025373  mov     rcx, [rsp+170h+var_110]
0x140025378  call    cs:__imp_SmbCryptoUpdatePreauthIntegrityHashValue
0x14002537f  nop     dword ptr [rax+rax+00h]
0x140025384  mov     ebx, eax
0x140025386  test    eax, eax
0x140025388  js      loc_140025B00
0x14002538e  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140025395  cmp     rcx, r12
0x140025398  jz      short loc_1400253D5
0x14002539a  test    dword ptr [rcx+2Ch], 400h
0x1400253a1  jz      short loc_1400253D5
0x1400253a3  cmp     byte ptr [rcx+29h], 4
0x1400253a7  jb      short loc_1400253D5
0x1400253a9  mov     r9, [rsi+240h]
0x1400253b0  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x1400253b7  mov     eax, dword ptr [rsp+170h+var_130]
0x1400253bb  mov     edx, 22h ; '"'
0x1400253c0  mov     rcx, [rcx+18h]
0x1400253c4  mov     qword ptr [rsp+170h+var_148], rsi
0x1400253c9  mov     r9d, [r9]
0x1400253cc  mov     dword ptr [rsp+170h+var_150], eax
0x1400253d0  call    WPP_SF_DDq
0x1400253d5  mov     r8d, [rsi+23Ch]
0x1400253dc  mov     r9, r14
0x1400253df  mov     rdx, [rsi+240h]
0x1400253e6  mov     rcx, [rsp+170h+var_110]
0x1400253eb  mov     dword ptr [rsp+170h+var_150], r13d
0x1400253f0  call    cs:__imp_SmbCryptoUpdatePreauthIntegrityHashValue
0x1400253f7  nop     dword ptr [rax+rax+00h]
0x1400253fc  mov     ebx, eax
0x1400253fe  test    eax, eax
0x140025400  js      loc_140025B00
0x140025406  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002540d  cmp     rcx, r12
0x140025410  jz      short loc_14002544A
0x140025412  test    dword ptr [rcx+2Ch], 400h
0x140025419  jz      short loc_14002544A
0x14002541b  cmp     byte ptr [rcx+29h], 4
0x14002541f  jb      short loc_14002544A
0x140025421  mov     r9, [rsi+240h]
0x140025428  lea     r8, WPP_48214901e2dc3d654588515547715784_Traceguids
0x14002542f  mov     rcx, [rcx+18h]
0x140025433  mov     edx, 23h ; '#'
0x140025438  mov     qword ptr [rsp+170h+var_148], rsi
0x14002543d  mov     dword ptr [rsp+170h+var_150], r13d
0x140025442  mov     r9d, [r9]
0x140025445  call    WPP_SF_DDq
0x14002544a  mov     ecx, [r14+58h]
0x14002544e  xor     r8b, r8b
0x140025451  mov     r13, [rsp+170h+var_100]
0x140025456  mov     eax, ecx
0x140025458  mov     ebx, ecx
0x14002545a  mov     byte ptr [rsp+170h+var_138], r8b
0x14002545f  and     eax, 1
0x140025462  mov     byte ptr [rsp+170h+var_134], r8b
0x140025467  and     ebx, 6
0x14002546a  mov     edx, 1
0x14002546f  or      ebx, eax
  ... truncated ...
```
