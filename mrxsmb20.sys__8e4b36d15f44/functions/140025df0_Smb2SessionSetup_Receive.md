# Smb2SessionSetup_Receive

- ea: `0x140025df0`
- end: `0x14002661d`
- name: `Smb2SessionSetup_Receive`
- size: `2093`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, size_t Size, _DWORD *, _WORD *Src)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x14000b940`
- `0x1400122d0`
- `0x14001ff50`
- `0x140020040`
- `0x140025df0`
- `0x140028ae0`
- `0x140028b20`
- `0x140029084`
- `0x14002a040`
- `0x14002a1dc`
- `0x14002cb78`
- `0x14002f198`
- `0x1400372c0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140026230`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026230`
- `ntoskrnl!ExAllocatePool2` at `0x140026181`
- `ntoskrnl!ExAllocatePool2` at `0x140026181`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002632a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002632a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140026555`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140026555`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002609b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140026154`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x14002609b`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x140026154`
- `rdbss!RxAllocateMdl2` at `0x140026522`
- `rdbss!RxAllocateMdl2` at `0x140026522`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14002635a`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x140026430`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x14002635a`
- `mrxsmb!SmbCryptoUpdatePreauthIntegrityHashValue` at `0x140026430`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140025fb2`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026010`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400260b2`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002610d`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140025fb2`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x140026010`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x1400260b2`
- `mrxsmb!MRxSmbGetConfigurationBlock` at `0x14002610d`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400264d5`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400265b7`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400264d5`
- `mrxsmb!SmbCseUpdateBufferContextStatus` at `0x1400265b7`
- `mrxsmb!SmbCeContinueExchange` at `0x1400264e4`
- `mrxsmb!SmbCeContinueExchange` at `0x1400264e4`

## pseudocode

```c
__int64 __fastcall Smb2SessionSetup_Receive(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        size_t Size,
        _DWORD *a6,
        _WORD *Src)
{
  int v7; // ebx
  unsigned int v8; // r15d
  __int64 v9; // r12
  int v11; // eax
  __int64 v12; // r15
  unsigned int v13; // ebp
  int v14; // eax
  unsigned int v15; // eax
  __int64 v16; // rcx
  __int64 v17; // rdi
  __int64 v18; // rdi
  int v19; // ebx
  __int64 ConfigurationBlock; // rax
  __int64 v21; // rdx
  __int64 v22; // r8
  KIRQL v23; // al
  __int64 v24; // rcx
  __int64 v25; // rcx
  int v26; // r8d
  __int64 v27; // rdx
  __int64 v28; // r8
  __int64 v29; // r9
  KIRQL v30; // al
  __int64 v31; // rcx
  __int64 Pool2; // rax
  __int64 v33; // rcx
  PVOID v34; // rax
  int updated; // eax
  __int64 v36; // rcx
  struct _MDL *Mdl2; // rax
  int v40; // [rsp+A8h] [rbp+20h]

  v40 = a4;
  v7 = *(_DWORD *)(a3 + 16);
  v8 = 0;
  v9 = a2;
  if ( v7 != -1073741629 )
    goto LABEL_8;
  v11 = *(_DWORD *)(a3 + 20);
  if ( v11 == -1073741802 )
  {
    v12 = *(_QWORD *)(a1 + 80);
    v7 = -1073741802;
    goto LABEL_4;
  }
  if ( (unsigned int)(v11 + 1067646966) > 1 )
  {
LABEL_8:
    v12 = *(_QWORD *)(a1 + 80);
    if ( v7 && v7 != -1073741802 )
    {
      if ( v7 < 0 )
      {
        v13 = ((v7 >> 31) & 0xFFFFFFCF) + 2043;
        if ( v7 == -1073741790 && *(_BYTE *)(v12 + 468) && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x40000000) != 0 )
          McTemplateK0qqhzr2_EtwWriteTransfer(
            *(_WORD *)(*(_QWORD *)(v12 + 384) + 80LL) >> 1,
            (unsigned int)NetworkTokenFailure,
            a3,
            11,
            34,
            *(_WORD *)(*(_QWORD *)(v12 + 384) + 80LL) >> 1,
            *(_QWORD *)(*(_QWORD *)(v12 + 384) + 88LL));
      }
      else
      {
        v7 = -1073741629;
        LOBYTE(v13) = ((*(int *)(a3 + 16) >> 31) & 0xCF) - 5;
      }
      v8 = 0;
      *a6 = Size;
      v14 = 11;
      goto LABEL_85;
    }
LABEL_4:
    if ( (unsigned int)a4 < 0x48 )
    {
      LOBYTE(v13) = 20;
      *a6 = Size;
LABEL_82:
      v7 = -1073741629;
      goto LABEL_83;
    }
    if ( Src[32] != 9 )
    {
      LOBYTE(v13) = 29;
      *a6 = Size;
      goto LABEL_82;
    }
    v15 = (unsigned __int16)Src[34];
    if ( v15 > (unsigned int)Size
      || (v16 = (unsigned __int16)Src[35], (unsigned int)v16 > (unsigned int)Size)
      || (unsigned int)v16 + v15 > (unsigned int)Size )
    {
      LOBYTE(v13) = 39;
      *a6 = Size;
      goto LABEL_82;
    }
    v17 = *(_QWORD *)(a1 + 56);
    Src[33] &= ~2u;
    if ( !v7 )
    {
      if ( (Src[33] & 4) != 0 || *(_BYTE *)(MRxSmbGetConfigurationBlock(v16) + 189) )
      {
        if ( (*(_DWORD *)(*(_QWORD *)(v12 + 384) + 716LL) & 0x8000) == 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            v18 = *(_QWORD *)(a1 + 96);
            v19 = ((unsigned __int16)Src[33] >> 2) & 1;
            ConfigurationBlock = MRxSmbGetConfigurationBlock(WPP_GLOBAL_Control);
            WPP_SF_qqdd(
              WPP_GLOBAL_Control->AttachedDevice,
              v21,
              v22,
              v12,
              *(_QWORD *)(v18 + 392),
              *(unsigned __int8 *)(ConfigurationBlock + 189),
              v19);
          }
          v7 = -1067646968;
          LOBYTE(v13) = 83;
          *a6 = Size;
          goto LABEL_83;
        }
        if ( !*(_BYTE *)(a1 + 1083) )
        {
          v23 = SmbCeAcquireSpinLock(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL), a2, a3, a4);
          *(_DWORD *)(v12 + 4) |= 4u;
          v24 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL);
          *(_DWORD *)(v24 + 2352) = -1;
          ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v24 + 1920), v23);
        }
      }
      if ( (Src[33] & 1) != 0 )
      {
        if ( *(_BYTE *)(MRxSmbGetConfigurationBlock(v16) + 478)
          && (WPP_MAIN_CB.Queue.Wcb.WaitQueueEntry.Inserted & 8) != 0 )
        {
          McTemplateK0hzr0_EtwWriteTransfer(
            v25,
            (unsigned int)InsecureGuestLogon,
            v26,
            *(_WORD *)(*(_QWORD *)(v12 + 384) + 80LL) >> 1,
            *(_QWORD *)(*(_QWORD *)(v12 + 384) + 88LL));
        }
        if ( *(_BYTE *)(a1 + 1083) || (Src[33] & 4) != 0 || *(_BYTE *)(MRxSmbGetConfigurationBlock(v25) + 189) )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_qq(
              WPP_GLOBAL_Control->AttachedDevice,
              36,
              WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
              v12,
              *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL));
          }
          v7 = -1067646969;
          LOBYTE(v13) = -124;
          *a6 = Size;
          goto LABEL_83;
        }
        v30 = SmbCeAcquireSpinLock(*(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL), v27, v28, v29);
        *(_DWORD *)(v12 + 4) |= 2u;
        v31 = *(_QWORD *)(*(_QWORD *)(a1 + 72) + 24LL);
        *(_DWORD *)(v31 + 2352) = -1;
        ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)(v31 + 1920), v30);
      }
    }
    *(_QWORD *)(v12 + 440) = *((_QWORD *)Src + 5);
    *(_DWORD *)(v9 + 748) = Size;
    Pool2 = ExAllocatePool2(66, (unsigned int)Size, 1834185555);
    *(_QWORD *)(v9 + 712) = Pool2;
    if ( !Pool2 )
    {
      v7 = -1073741670;
      LOBYTE(v13) = -61;
      *a6 = Size;
LABEL_83:
      v8 = 0;
      goto LABEL_84;
    }
    LOBYTE(v13) = -54;
    if ( *(_BYTE *)(a1 + 1082) )
    {
      ExFreePoolWithTag(*(PVOID *)(a1 + 1056), 0x6D53674Eu);
      *(_QWORD *)(a1 + 1056) = 0;
      *(_BYTE *)(a1 + 1082) = 0;
    }
    *(_QWORD *)(a1 + 1056) = 0;
    *(_DWORD *)(a1 + 1064) = 0;
    if ( Src[35] )
    {
      *(_QWORD *)(a1 + 1056) = *(_QWORD *)(v9 + 712) + (unsigned __int16)Src[34];
      *(_DWORD *)(a1 + 1064) = (unsigned __int16)Src[35];
    }
    if ( v7 != -1073741802 && !*(_BYTE *)(a1 + 1081) )
    {
      if ( v17 )
      {
        SmbCeAcquireCompoundingKeyLock(v17);
        _InterlockedAnd((volatile signed __int32 *)(a1 + 68), 0xFFFFF7FF);
        *(_DWORD *)(v9 + 4) &= ~0x1000u;
        SmbCeReleaseCompoundingKeyLock(v17);
      }
      else
      {
        SmbCeAcquireExchangeLock(a1);
        _InterlockedAnd((volatile signed __int32 *)(a1 + 68), 0xFFFFF7FF);
        *(_DWORD *)(v9 + 4) &= ~0x1000u;
        SmbCeReleaseExchangeLock(a1);
      }
    }
    if ( v40 != (_DWORD)Size )
    {
      Mdl2 = (struct _MDL *)RxAllocateMdl2(*(_QWORD *)(v9 + 712), *(unsigned int *)(v9 + 748), 0, 0, 0);
      *(_QWORD *)(v9 + 720) = Mdl2;
      if ( Mdl2 )
      {
        MmBuildMdlForNonPagedPool(Mdl2);
        v8 = -1073741802;
        *a6 = 0;
        v14 = 0;
        goto LABEL_85;
      }
      v7 = -1073741670;
      LOBYTE(v13) = 78;
      *a6 = Size;
      goto LABEL_83;
    }
    if ( *(_QWORD *)(a1 + 1032) )
    {
      v33 = *(_QWORD *)(v9 + 96);
      if ( (*(_BYTE *)(v33 + 10) & 5) != 0 )
        v34 = *(PVOID *)(v33 + 24);
      else
        v34 = MmMapLockedPagesSpecifyCache((PMDL)v33, 0, MmCached, 0, 0, 0x40000010u);
      updated = SmbCryptoUpdatePreauthIntegrityHashValue(
                  *(_QWORD *)(a1 + 1032),
                  *(_QWORD *)(a1 + 1040),
                  *(unsigned int *)(a1 + 1048),
                  v34,
                  *(_DWORD *)(v9 + 728));
      if ( updated < 0 )
      {
        v7 = updated;
        v8 = 0;
        LOBYTE(v13) = 5;
        *a6 = Size;
        goto LABEL_84;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDqq(
          WPP_GLOBAL_Control->AttachedDevice,
          38,
          WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
          **(unsigned int **)(a1 + 1040),
          *(_DWORD *)(v9 + 728),
          v12,
          *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL));
      }
    }
    memmove(*(void **)(v9 + 712), Src, (unsigned int)Size);
    *a6 = Size;
    if ( v7 != -1073741802 )
    {
      v9 = a2;
      v8 = 0;
      goto LABEL_84;
    }
    v36 = *(_QWORD *)(a1 + 1032);
    if ( v36 )
    {
      v7 = SmbCryptoUpdatePreauthIntegrityHashValue(
             v36,
             *(_QWORD *)(a1 + 1040),
             *(unsigned int *)(a1 + 1048),
             Src,
             Size);
      if ( v7 < 0 )
      {
        *a6 = Size;
        v8 = 0;
        v9 = a2;
        LOBYTE(v13) = 49;
        goto LABEL_84;
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_DDqq(
          WPP_GLOBAL_Control->AttachedDevice,
          39,
          WPP_981a12f1532a3df13e243e2e48204374_Traceguids,
          **(unsigned int **)(a1 + 1040),
          Size,
          v12,
          *(_QWORD *)(*(_QWORD *)(a1 + 96) + 392LL));
      }
    }
    SmbCseUpdateBufferContextStatus(a2, 3221225494LL);
    SmbCeContinueExchange(a1);
    return 0;
  }
  LOBYTE(v13) = -22;
  *a6 = Size;
  v7 = *(_DWORD *)(a3 + 20);
LABEL_84:
  v14 = 0;
LABEL_85:
  SmbCseUpdateBufferContextStatus(v9, __PAIR64__(v14, v7));
  if ( (int)(v7 + 0x80000000) >= 0 && v7 != -1073741802 && (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 1) != 0 )
    McTemplateK0qqq_EtwWriteTransfer(0x80000000, (unsigned int)SessionSetupError, a1 + 312, v7, v13, 11);
  return v8;
}

```

## disassembly

```asm
0x140025df0  mov     [rsp+arg_18], r9d
0x140025df5  mov     [rsp+arg_8], rdx
0x140025dfa  push    rbx
0x140025dfb  push    rbp
0x140025dfc  push    rsi
0x140025dfd  push    rdi
0x140025dfe  push    r12
0x140025e00  push    r13
0x140025e02  push    r14
0x140025e04  push    r15
0x140025e06  sub     rsp, 48h
0x140025e0a  mov     ebx, [r8+10h]
0x140025e0e  xor     r15d, r15d
0x140025e11  mov     [rsp+88h+arg_10], r15d
0x140025e19  mov     r12, rdx
0x140025e1c  mov     dword ptr [rsp+88h+arg_0], r15d
0x140025e24  mov     rsi, rcx
0x140025e27  cmp     ebx, 0C00000C3h
0x140025e2d  jnz     short loc_140025E8E
0x140025e2f  mov     eax, [r8+14h]
0x140025e33  cmp     eax, 0C0000016h
0x140025e38  jnz     short loc_140025E65
0x140025e3a  mov     r15, [rcx+50h]
0x140025e3e  mov     ebx, eax
0x140025e40  cmp     r9d, 48h ; 'H'
0x140025e44  jnb     loc_140025F39
0x140025e4a  mov     rax, [rsp+88h+arg_28]
0x140025e52  mov     ebp, 814h
0x140025e57  mov     ecx, dword ptr [rsp+88h+Size]
0x140025e5e  mov     [rax], ecx
0x140025e60  jmp     loc_14002658E
0x140025e65  add     eax, 3FA2FFF6h
0x140025e6a  cmp     eax, 1
0x140025e6d  ja      short loc_140025E8E
0x140025e6f  mov     rax, [rsp+88h+arg_28]
0x140025e77  mov     ebp, 7EAh
0x140025e7c  mov     ecx, dword ptr [rsp+88h+Size]
0x140025e83  mov     [rax], ecx
0x140025e85  mov     ebx, [r8+14h]
0x140025e89  jmp     loc_14002659B
0x140025e8e  mov     r15, [rcx+50h]
0x140025e92  test    ebx, ebx
0x140025e94  jz      short loc_140025E40
0x140025e96  mov     edi, ebx
0x140025e98  cmp     ebx, 0C0000016h
0x140025e9e  jz      short loc_140025E40
0x140025ea0  test    ebx, ebx
0x140025ea2  js      short loc_140025EB7
0x140025ea4  sar     edi, 1Fh
0x140025ea7  mov     ebx, 0C00000C3h
0x140025eac  and     edi, 0FFFFFFCFh
0x140025eaf  lea     ebp, [rdi+7FBh]
0x140025eb5  jmp     short loc_140025F16
0x140025eb7  mov     ebp, edi
0x140025eb9  sar     ebp, 1Fh
0x140025ebc  and     ebp, 0FFFFFFCFh
0x140025ebf  add     ebp, 7FBh
0x140025ec5  cmp     edi, 0C0000022h
0x140025ecb  jnz     short loc_140025F16
0x140025ecd  cmp     byte ptr [r15+1D4h], 0
0x140025ed5  jz      short loc_140025F16
0x140025ed7  test    byte ptr cs:WPP_MAIN_CB.Queue+13h, 40h
0x140025ede  jz      short loc_140025F16
0x140025ee0  mov     rax, [r15+180h]
0x140025ee7  lea     rdx, NetworkTokenFailure
0x140025eee  mov     r9d, 0Bh
0x140025ef4  movzx   ecx, word ptr [rax+50h]
0x140025ef8  mov     rax, [rax+58h]
0x140025efc  mov     [rsp+88h+var_58], rax
0x140025f01  shr     cx, 1
0x140025f04  mov     word ptr [rsp+88h+Priority], cx
0x140025f09  mov     [rsp+88h+BugCheckOnFailure], 0C0000022h
0x140025f11  call    McTemplateK0qqhzr2_EtwWriteTransfer
0x140025f16  mov     eax, dword ptr [rsp+88h+Size]
0x140025f1d  mov     rcx, [rsp+88h+arg_28]
0x140025f25  mov     r15d, [rsp+88h+arg_10]
0x140025f2d  mov     [rcx], eax
0x140025f2f  mov     eax, 0Bh
0x140025f34  jmp     loc_14002659E
0x140025f39  mov     r13, [rsp+88h+Src]
0x140025f41  cmp     word ptr [r13+40h], 9
0x140025f47  jz      short loc_140025F64
0x140025f49  mov     rax, [rsp+88h+arg_28]
0x140025f51  mov     ebp, 81Dh
0x140025f56  mov     ecx, dword ptr [rsp+88h+Size]
0x140025f5d  mov     [rax], ecx
0x140025f5f  jmp     loc_14002658E
0x140025f64  movzx   eax, word ptr [r13+44h]
0x140025f69  mov     r14d, dword ptr [rsp+88h+Size]
0x140025f71  cmp     eax, r14d
0x140025f74  ja      loc_14002657E
0x140025f7a  movzx   ecx, word ptr [r13+46h]
0x140025f7f  cmp     ecx, r14d
0x140025f82  ja      loc_14002657E
0x140025f88  add     eax, ecx
0x140025f8a  cmp     eax, r14d
0x140025f8d  ja      loc_14002657E
0x140025f93  mov     rdi, [rsi+38h]
0x140025f97  mov     eax, 0FFFDh
0x140025f9c  and     [r13+42h], ax
0x140025fa1  movzx   eax, word ptr [r13+42h]
0x140025fa6  test    ebx, ebx
0x140025fa8  jnz     loc_140026160
0x140025fae  test    al, 4
0x140025fb0  jnz     short loc_140025FCA
0x140025fb2  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140025fb9  nop     dword ptr [rax+rax+00h]
0x140025fbe  cmp     [rax+0BDh], bl
0x140025fc4  jz      loc_1400260A7
0x140025fca  mov     rax, [r15+180h]
0x140025fd1  test    dword ptr [rax+2CCh], 8000h
0x140025fdb  jnz     loc_140026064
0x140025fe1  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140025fe8  lea     rdi, WPP_GLOBAL_Control
0x140025fef  cmp     rcx, rdi
0x140025ff2  jz      short loc_14002604A
0x140025ff4  mov     eax, [rcx+2Ch]
0x140025ff7  test    al, 1
0x140025ff9  jz      short loc_14002604A
0x140025ffb  cmp     byte ptr [rcx+29h], 1
0x140025fff  jb      short loc_14002604A
0x140026001  movzx   ebx, word ptr [r13+42h]
0x140026006  mov     rdi, [rsi+60h]
0x14002600a  shr     ebx, 2
0x14002600d  and     ebx, 1
0x140026010  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140026017  nop     dword ptr [rax+rax+00h]
0x14002601c  mov     dword ptr [rsp+88h+var_58], ebx
0x140026020  mov     r9, r15
0x140026023  movzx   ecx, byte ptr [rax+0BDh]
0x14002602a  mov     rax, [rdi+188h]
0x140026031  mov     [rsp+88h+Priority], ecx
0x140026035  mov     rcx, cs:WPP_GLOBAL_Control
0x14002603c  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x140026041  mov     rcx, [rcx+18h]
0x140026045  call    WPP_SF_qqdd
0x14002604a  mov     rax, [rsp+88h+arg_28]
0x140026052  mov     ebx, 0C05D0008h
0x140026057  mov     ebp, 853h
0x14002605c  mov     [rax], r14d
0x14002605f  jmp     loc_140026593
0x140026064  cmp     byte ptr [rsi+43Bh], 0
0x14002606b  jnz     short loc_1400260A7
0x14002606d  mov     rcx, [rsi+48h]
0x140026071  mov     rcx, [rcx+18h]
0x140026075  call    SmbCeAcquireSpinLock
0x14002607a  or      dword ptr [r15+4], 4
0x14002607f  movzx   edx, al; OldIrql
0x140026082  mov     rcx, [rsi+48h]
0x140026086  mov     rcx, [rcx+18h]
0x14002608a  mov     dword ptr [rcx+930h], 0FFFFFFFFh
0x140026094  add     rcx, 780h; SpinLock
0x14002609b  call    cs:__imp_ExReleaseSpinLockExclusive
0x1400260a2  nop     dword ptr [rax+rax+00h]
0x1400260a7  test    byte ptr [r13+42h], 1
0x1400260ac  jz      loc_140026160
0x1400260b2  call    cs:__imp_MRxSmbGetConfigurationBlock
0x1400260b9  nop     dword ptr [rax+rax+00h]
0x1400260be  cmp     byte ptr [rax+1DEh], 0
0x1400260c5  jz      short loc_1400260F5
0x1400260c7  test    byte ptr cs:WPP_MAIN_CB.Queue+14h, 8
0x1400260ce  jz      short loc_1400260F5
0x1400260d0  mov     rax, [r15+180h]
0x1400260d7  lea     rdx, InsecureGuestLogon
0x1400260de  movzx   r9d, word ptr [rax+50h]
0x1400260e3  mov     rax, [rax+58h]
0x1400260e7  shr     r9w, 1
0x1400260eb  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x1400260f0  call    McTemplateK0hzr0_EtwWriteTransfer
0x1400260f5  cmp     byte ptr [rsi+43Bh], 0
0x1400260fc  jnz     loc_1400261B4
0x140026102  test    byte ptr [r13+42h], 4
0x140026107  jnz     loc_1400261B4
0x14002610d  call    cs:__imp_MRxSmbGetConfigurationBlock
0x140026114  nop     dword ptr [rax+rax+00h]
0x140026119  cmp     byte ptr [rax+0BDh], 0
0x140026120  jnz     loc_1400261B4
0x140026126  mov     rcx, [rsi+48h]
0x14002612a  mov     rcx, [rcx+18h]
0x14002612e  call    SmbCeAcquireSpinLock
0x140026133  or      dword ptr [r15+4], 2
0x140026138  movzx   edx, al; OldIrql
0x14002613b  mov     rcx, [rsi+48h]
0x14002613f  mov     rcx, [rcx+18h]
0x140026143  mov     dword ptr [rcx+930h], 0FFFFFFFFh
0x14002614d  add     rcx, 780h; SpinLock
0x140026154  call    cs:__imp_ExReleaseSpinLockExclusive
0x14002615b  nop     dword ptr [rax+rax+00h]
0x140026160  mov     rax, [r13+28h]
0x140026164  mov     rdx, r14
0x140026167  mov     [r15+1B8h], rax
0x14002616e  mov     ecx, 42h ; 'B'
0x140026173  mov     r8d, 6D537353h
0x140026179  mov     [r12+2ECh], r14d
0x140026181  call    cs:__imp_ExAllocatePool2
0x140026188  nop     dword ptr [rax+rax+00h]
0x14002618d  mov     [r12+2C8h], rax
0x140026195  test    rax, rax
0x140026198  jnz     short loc_140026216
0x14002619a  mov     rax, [rsp+88h+arg_28]
0x1400261a2  mov     ebx, 0C000009Ah
0x1400261a7  mov     ebp, 8C3h
0x1400261ac  mov     [rax], r14d
0x1400261af  jmp     loc_140026593
0x1400261b4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400261bb  lea     rdi, WPP_GLOBAL_Control
0x1400261c2  cmp     rcx, rdi
0x1400261c5  jz      short loc_1400261FC
0x1400261c7  mov     eax, [rcx+2Ch]
0x1400261ca  test    al, 1
0x1400261cc  jz      short loc_1400261FC
0x1400261ce  cmp     byte ptr [rcx+29h], 1
0x1400261d2  jb      short loc_1400261FC
0x1400261d4  mov     rax, [rsi+60h]
0x1400261d8  lea     r8, WPP_981a12f1532a3df13e243e2e48204374_Traceguids
0x1400261df  mov     rcx, [rcx+18h]
0x1400261e3  mov     edx, 24h ; '$'
0x1400261e8  mov     r9, r15
0x1400261eb  mov     rax, [rax+188h]
0x1400261f2  mov     qword ptr [rsp+88h+BugCheckOnFailure], rax
0x1400261f7  call    WPP_SF_qq
0x1400261fc  mov     rax, [rsp+88h+arg_28]
0x140026204  mov     ebx, 0C05D0007h
0x140026209  mov     ebp, 884h
0x14002620e  mov     [rax], r14d
0x140026211  jmp     loc_140026593
0x140026216  cmp     byte ptr [rsi+43Ah], 0
0x14002621d  mov     ebp, 7CAh
0x140026222  jz      short loc_14002624D
0x140026224  mov     rcx, [rsi+420h]; P
0x14002622b  mov     edx, 6D53674Eh; Tag
0x140026230  call    cs:__imp_ExFreePoolWithTag
0x140026237  nop     dword ptr [rax+rax+00h]
0x14002623c  xor     edx, edx
0x14002623e  mov     [rsi+420h], rdx
0x140026245  mov     [rsi+43Ah], dl
0x14002624b  jmp     short loc_14002624F
0x14002624d  xor     edx, edx
0x14002624f  mov     [rsi+420h], rdx
0x140026256  mov     [rsi+428h], edx
0x14002625c  cmp     word ptr [r13+46h], 0
0x140026262  jz      short loc_140026283
0x140026264  movzx   eax, word ptr [r13+44h]
0x140026269  add     rax, [r12+2C8h]
0x140026271  mov     [rsi+420h], rax
0x140026278  movzx   eax, word ptr [r13+46h]
0x14002627d  mov     [rsi+428h], eax
0x140026283  cmp     ebx, 0C0000016h
0x140026289  jz      short loc_1400262DF
0x14002628b  cmp     byte ptr [rsi+439h], 0
0x140026292  jnz     short loc_1400262DF
0x140026294  test    rdi, rdi
0x140026297  jz      short loc_1400262BC
0x140026299  mov     rcx, rdi
0x14002629c  call    SmbCeAcquireCompoundingKeyLock
0x1400262a1  lock and dword ptr [rsi+44h], 0FFFFF7FFh
0x1400262a9  and     dword ptr [r12+4], 0FFFFEFFFh
0x1400262b2  mov     rcx, rdi
0x1400262b5  call    SmbCeReleaseCompoundingKeyLock
0x1400262ba  jmp     short loc_1400262DD
0x1400262bc  mov     rcx, rsi
0x1400262bf  call    SmbCeAcquireExchangeLock
0x1400262c4  lock and dword ptr [rsi+44h], 0FFFFF7FFh
0x1400262cc  and     dword ptr [r12+4], 0FFFFEFFFh
0x1400262d5  mov     rcx, rsi
0x1400262d8  call    SmbCeReleaseExchangeLock
0x1400262dd  xor     edx, edx
0x1400262df  cmp     [rsp+88h+arg_18], r14d
0x1400262e7  jnz     loc_140026507
0x1400262ed  cmp     qword ptr [rsi+408h], 0
0x1400262f5  lea     rdi, WPP_GLOBAL_Control
0x1400262fc  jz      loc_1400263DF
0x140026302  mov     rcx, [r12+60h]; MemoryDescriptorList
0x140026307  test    byte ptr [rcx+0Ah], 5
0x14002630b  jz      short loc_140026313
0x14002630d  mov     rax, [rcx+18h]
0x140026311  jmp     short loc_140026336
0x140026313  mov     [rsp+88h+Priority], 40000010h; Priority
0x14002631b  xor     r9d, r9d; RequestedAddress
0x14002631e  mov     [rsp+88h+BugCheckOnFailure], edx; BugCheckOnFailure
0x140026322  mov     r8d, 1; CacheType
0x140026328  xor     edx, edx; AccessMode
0x14002632a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140026331  nop     dword ptr [rax+rax+00h]
0x140026336  mov     ecx, [r12+2D8h]
0x14002633e  mov     r9, rax
0x140026341  mov     r8d, [rsi+418h]
0x140026348  mov     rdx, [rsi+410h]
0x14002634f  mov     [rsp+88h+BugCheckOnFailure], ecx
0x140026353  mov     rcx, [rsi+408h]
0x14002635a  call    cs:__imp_SmbCryptoUpdatePreauthIntegrityHashValue
0x140026361  nop     dword ptr [rax+rax+00h]
0x140026366  test    eax, eax
0x140026368  jns     short loc_140026384
0x14002636a  mov     ebx, eax
0x14002636c  xor     r15d, r15d
0x14002636f  mov     rax, [rsp+88h+arg_28]
0x140026377  mov     ebp, 905h
0x14002637c  mov     [rax], r14d
0x14002637f  jmp     loc_14002659B
  ... truncated ...
```
