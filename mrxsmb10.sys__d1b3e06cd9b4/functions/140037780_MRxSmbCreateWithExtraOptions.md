# MRxSmbCreateWithExtraOptions

- ea: `0x140037780`
- end: `0x140038198`
- name: `MRxSmbCreateWithExtraOptions`
- size: `2584`
- prototype: `__int64 __fastcall(PRX_CONTEXT RxContext)`
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x140036d40`

## callees

- `0x14000b210`
- `0x14000dfa8`
- `0x1400107f8`
- `0x140016560`
- `0x1400166c0`
- `0x1400169c0`
- `0x14003608c`
- `0x140037780`
- `0x14003889c`
- `0x1400394f0`
- `0x14003ef9c`
- `0x140044700`
- `0x14004b5f0`
- `0x140051880`

## import_xrefs

- `ntoskrnl!MmUnlockPages` at `0x1400380d0`
- `ntoskrnl!MmUnlockPages` at `0x1400380d0`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037fa3`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x140037fa3`
- `ntoskrnl!RtlxUnicodeStringToAnsiSize` at `0x1400379d6`
- `ntoskrnl!RtlxUnicodeStringToAnsiSize` at `0x1400379d6`
- `ntoskrnl!IoBuildPartialMdl` at `0x140037f58`
- `ntoskrnl!IoBuildPartialMdl` at `0x140037f58`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140037df9`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140037df9`
- `ntoskrnl!IoFreeMdl` at `0x1400380ec`
- `ntoskrnl!IoFreeMdl` at `0x140038108`
- `ntoskrnl!IoFreeMdl` at `0x140038121`
- `ntoskrnl!IoFreeMdl` at `0x1400380ec`
- `ntoskrnl!IoFreeMdl` at `0x140038108`
- `ntoskrnl!IoFreeMdl` at `0x140038121`
- `ntoskrnl!MmProbeAndLockPages` at `0x140037beb`
- `ntoskrnl!MmProbeAndLockPages` at `0x140037e70`
- `ntoskrnl!MmProbeAndLockPages` at `0x140037beb`
- `ntoskrnl!MmProbeAndLockPages` at `0x140037e70`
- `ntoskrnl!ExAllocatePool2` at `0x1400379fb`
- `ntoskrnl!ExAllocatePool2` at `0x140037b8e`
- `ntoskrnl!ExAllocatePool2` at `0x1400379fb`
- `ntoskrnl!ExAllocatePool2` at `0x140037b8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038137`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038155`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038137`
- `ntoskrnl!ExFreePoolWithTag` at `0x140038155`
- `rdbss!RxProcessFcbChangeBufferingStateRequest` at `0x140038005`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x140037ff1`
- `rdbss!RxFcbGetOutstandingBufferingChangeEvent` at `0x140037ff1`
- `rdbss!RxAllocateMdl2` at `0x140037bbb`
- `rdbss!RxAllocateMdl2` at `0x140037dd6`
- `rdbss!RxAllocateMdl2` at `0x140037e3d`
- `rdbss!RxAllocateMdl2` at `0x140037f20`
- `rdbss!RxAllocateMdl2` at `0x140037bbb`
- `rdbss!RxAllocateMdl2` at `0x140037dd6`
- `rdbss!RxAllocateMdl2` at `0x140037e3d`
- `rdbss!RxAllocateMdl2` at `0x140037f20`

## pseudocode

```c
__int64 __fastcall MRxSmbCreateWithExtraOptions(PRX_CONTEXT RxContext)
{
  PMRX_FCB pFcb; // rdi
  __int64 v3; // rbx
  int v4; // r12d
  const UNICODE_STRING *p_Resource; // r15
  __int64 v6; // rdi
  char v7; // cl
  char v8; // dl
  char v9; // cl
  char v10; // bl
  char IsStreamFile; // al
  char v12; // cl
  __int16 v13; // ax
  ULONG Length; // ebx
  __int64 Pool2; // rax
  char *v16; // r15
  struct _MDL *v17; // rcx
  int v18; // ebx
  char v19; // r8
  __int64 v20; // rax
  __int64 v21; // rdx
  PMDL v22; // r8
  ULONG v23; // r13d
  ULONG v24; // r12d
  PVOID *v25; // rcx
  void *v26; // rax
  ULONG v27; // ebx
  PVOID v28; // rbx
  struct _MDL *Mdl2; // rax
  struct _MDL *v30; // rax
  PMDL v31; // rax
  PMRX_FCB v32; // rdi
  char v34; // [rsp+80h] [rbp-1C8h]
  int v35; // [rsp+84h] [rbp-1C4h]
  unsigned int v36; // [rsp+84h] [rbp-1C4h]
  int v37; // [rsp+88h] [rbp-1C0h]
  struct _MDL *MemoryDescriptorList; // [rsp+90h] [rbp-1B8h]
  __int64 v39; // [rsp+98h] [rbp-1B0h] BYREF
  ULONG v40; // [rsp+A0h] [rbp-1A8h] BYREF
  PVOID P; // [rsp+A8h] [rbp-1A0h]
  __int64 v42; // [rsp+B0h] [rbp-198h] BYREF
  ULONG AcquireRelease; // [rsp+B8h] [rbp-190h]
  PMRX_FCB v44; // [rsp+C0h] [rbp-188h]
  PMDL Mdl; // [rsp+C8h] [rbp-180h]
  PMDL v46; // [rsp+D0h] [rbp-178h]
  PVOID *p_EaBuffer; // [rsp+D8h] [rbp-170h]
  __int64 v48; // [rsp+E0h] [rbp-168h]
  unsigned int v49; // [rsp+E8h] [rbp-160h]
  __int64 v50; // [rsp+F0h] [rbp-158h]
  PRX_CONTEXT v51; // [rsp+100h] [rbp-148h]
  PMRX_FCB v52; // [rsp+108h] [rbp-140h]
  _OWORD v53[2]; // [rsp+110h] [rbp-138h] BYREF
  _QWORD v54[14]; // [rsp+130h] [rbp-118h] BYREF
  _BYTE v55[112]; // [rsp+1A0h] [rbp-A8h] BYREF

  v51 = RxContext;
  pFcb = RxContext->pFcb;
  v44 = pFcb;
  v52 = pFcb;
  v3 = *(_QWORD *)(*(_QWORD *)&RxContext->TrackerHistory[0].AcquireRelease + 32LL);
  v48 = v3;
  v39 = *((_QWORD *)RxContext->TrackerHistory[0].FileName + 5);
  memset(v54, 0, 0x68u);
  memset(v53, 0, 24);
  memset(v55, 0, 0x65u);
  v42 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 67, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( (*(_DWORD *)(v3 + 420) & 0x40000) == 0 )
    return MRxSmbT2OpenFile(RxContext);
  v4 = *(_DWORD *)(v3 + 420) & 0x8000;
  v37 = v4;
  p_Resource = (const UNICODE_STRING *)&pFcb[2].Header.Resource;
  p_EaBuffer = &RxContext->Create.EaBuffer;
  P = 0;
  v6 = 0;
  Mdl = 0;
  MemoryDescriptorList = 0;
  v34 = 0;
  v46 = 0;
  v35 = 0;
  MRxSmbAdjustCreateParameters(RxContext, &v42);
  v7 = 1;
  if ( (*((_DWORD *)&RxContext->9 + 35) & 1) != 0 || (*((_DWORD *)&RxContext->9 + 28) & 0x23) == 0 )
  {
    LODWORD(RxContext->pRelevantSrvOpen->Key) |= 0x200u;
    v7 = 0;
  }
  v8 = 0;
  if ( !*(_BYTE *)(v39 + 105) )
    v8 = v7;
  v9 = 0;
  if ( !*(_BYTE *)(v48 + 505) )
    v9 = v8;
  v10 = v9;
  IsStreamFile = MRxSmbIsStreamFile(p_Resource, 0);
  v12 = 0;
  if ( !IsStreamFile )
    v12 = v10;
  if ( !MRxSmbOplocksDisabled && v12 )
  {
    v13 = WORD1(RxContext->TrackerHistory[4].FileName);
    if ( (v13 & 0x800) != 0 )
    {
      v35 = 0;
    }
    else if ( (v13 & 0x400) != 0 )
    {
      v35 = 2;
      *(&RxContext->TrackerHistory[3].Flags + 1) = 9;
    }
    else
    {
      v35 = 6;
      *(&RxContext->TrackerHistory[3].Flags + 1) = 31;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 68, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
  if ( v4 )
    Length = p_Resource->Length;
  else
    Length = RtlxUnicodeStringToAnsiSize(p_Resource);
  v49 = Length + 54;
  Pool2 = ExAllocatePool2(258, Length + 54, 1651340120);
  v16 = (char *)Pool2;
  v48 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 69, WPP_d95790c14120305e97e490eb33b089fe_Traceguids);
    goto LABEL_31;
  }
  v20 = Pool2 + 53;
  if ( v4 )
  {
    memmove((void *)((v20 + 1) & 0xFFFFFFFFFFFFFFFEuLL), v44[2].Header.PagingIoResource, Length);
  }
  else
  {
    v39 = v20;
    v40 = Length;
    SmbPutUnicodeStringAsOemString(&v39, &v44[2].Header.Resource, &v40);
  }
  AcquireRelease = RxContext->TrackerHistory[3].AcquireRelease;
  v23 = AcquireRelease;
  v40 = *(_DWORD *)&RxContext->TrackerHistory[3].SavedTrackerValue;
  v24 = v40;
  *(_DWORD *)v16 = v35 | 0x10;
  *((_DWORD *)v16 + 1) = 0;
  v25 = p_EaBuffer;
  *((_DWORD *)v16 + 2) = *(_DWORD *)p_EaBuffer;
  *(_QWORD *)(v16 + 12) = v25[1];
  *((_DWORD *)v16 + 5) = *((_DWORD *)v25 + 4);
  *((_DWORD *)v16 + 6) = *((_DWORD *)v25 + 5);
  *((_DWORD *)v16 + 7) = *((_DWORD *)v25 + 6);
  *((_DWORD *)v16 + 8) = *((_DWORD *)v25 + 7);
  *((_DWORD *)v16 + 9) = v24;
  *((_DWORD *)v16 + 10) = v23;
  if ( !v37 )
    --Length;
  *((_DWORD *)v16 + 11) = Length;
  *((_DWORD *)v16 + 12) = *((_DWORD *)v25 + 10);
  v16[52] = BYTE4(v42);
  if ( !v23 )
    goto LABEL_52;
  if ( !v24 )
  {
    Mdl2 = (struct _MDL *)RxAllocateMdl2(RxContext->TrackerHistory[2].FileName, v23, 0, 0, 0);
    v6 = (__int64)Mdl2;
    Mdl = Mdl2;
    if ( !Mdl2 )
      goto LABEL_31;
    MmBuildMdlForNonPagedPool(Mdl2);
    *(_QWORD *)v6 = 0;
    v25 = p_EaBuffer;
LABEL_52:
    v39 = 0;
    if ( v24 )
    {
      v6 = RxAllocateMdl2(*(_QWORD *)(*((_QWORD *)v25[4] + 1) + 64LL), v24, 0, 0, 0);
      v17 = (struct _MDL *)v6;
      MemoryDescriptorList = (struct _MDL *)v6;
      v42 = v6;
      if ( !v6 )
        goto LABEL_32;
      MmProbeAndLockPages((PMDL)v6, 0, IoModifyAccess);
      v34 = 1;
      v21 = 4294967292LL;
      v27 = ((v24 + 3) & 0xFFFFFFFC) - v24;
      if ( v27 && v23 )
      {
        v30 = (struct _MDL *)RxAllocateMdl2(0, 4099, 0, 0, 0);
        v46 = v30;
        if ( !v30 )
          goto LABEL_57;
        IoBuildPartialMdl(
          (PMDL)MrxSmbCeGlobalPadding,
          v30,
          (PVOID)(*((_QWORD *)MrxSmbCeGlobalPadding + 4) + *((unsigned int *)MrxSmbCeGlobalPadding + 11)),
          v27);
        v22 = v46;
        v46->Next = Mdl;
        v31 = v22;
      }
      else
      {
        v31 = Mdl;
      }
      *(_QWORD *)v6 = v31;
LABEL_44:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_dddq(WPP_GLOBAL_Control->AttachedDevice, v21, v22, v24, v27, v23, RxContext->TrackerHistory[2].FileName);
      }
      *(_OWORD *)((char *)v53 + 4) = *(__int128 *)((char *)&RxDefaultTransactionOptions + 4);
      WORD1(v53[0]) = WORD1(RxDefaultTransactionOptions) | 0x4000;
      LOWORD(v53[0]) = 1;
      DWORD1(v53[1]) = 0xFFFF;
      if ( !v6 )
      {
        v28 = 0;
        LODWORD(v39) = 0;
LABEL_67:
        SmbCeInitializeTransactionResumptionContext(v54);
        v32 = v44;
        v54[10] = RxFcbGetOutstandingBufferingChangeEvent(v44);
        v54[11] = RxProcessFcbChangeBufferingStateRequest;
        v54[12] = v32;
        v18 = SmbCeTransact(
                (int)RxContext,
                (__int64)v53,
                0,
                0,
                0,
                0,
                (__int64)v16,
                v49,
                (__int64)v55,
                0x65u,
                (__int64)v28,
                v39,
                0,
                0,
                (__int64)v54);
        if ( v18 >= 0 )
        {
          MRxSmbFinishLongNameCreateFile(RxContext);
          if ( *((_DWORD *)p_EaBuffer + 6) == 1 )
            MRxSmbAdjustReturnedCreateAction(RxContext);
        }
        goto LABEL_70;
      }
      if ( (*(_BYTE *)(v6 + 10) & 5) != 0 )
        v28 = *(PVOID *)(v6 + 24);
      else
        v28 = MmMapLockedPagesSpecifyCache((PMDL)v6, 0, MmCached, 0, 0, 0x40000000u);
      if ( v28 )
      {
        if ( !v23 || !v24 )
          v39 = v24 + v23;
        goto LABEL_67;
      }
LABEL_57:
      v18 = -1073741670;
LABEL_70:
      v17 = MemoryDescriptorList;
      v19 = v34;
      goto LABEL_71;
    }
LABEL_43:
    v27 = 0;
    goto LABEL_44;
  }
  v36 = (v24 + 3) & 0xFFFFFFFC;
  v39 = (v23 + v36 + 3) & 0xFFFFFFFC;
  v50 = v39;
  v26 = (void *)ExAllocatePool2(258, v39, 6450547);
  P = v26;
  if ( v26 )
  {
    v17 = (struct _MDL *)RxAllocateMdl2(v26, (v23 + v36 + 3) & 0xFFFFFFFC, 0, 0, 0);
    MemoryDescriptorList = v17;
    v42 = (__int64)v17;
    if ( !v17 )
      goto LABEL_32;
    MmProbeAndLockPages(v17, 0, IoModifyAccess);
    v34 = 1;
    memmove(P, *(const void **)(*((_QWORD *)p_EaBuffer[4] + 1) + 64LL), v24);
    memset((char *)P + v24, 0, v36 - v24);
    memmove((char *)P + v36, RxContext->TrackerHistory[2].FileName, v23);
    memset((char *)P + v36 + (unsigned __int64)v23, 0, (_DWORD)v39 - v36 - v23);
    v6 = (__int64)MemoryDescriptorList;
    goto LABEL_43;
  }
LABEL_31:
  v17 = 0;
LABEL_32:
  v18 = -1073741670;
  v19 = 0;
LABEL_71:
  if ( v19 )
    MmUnlockPages(v17);
  if ( Mdl )
    IoFreeMdl(Mdl);
  if ( v46 )
    IoFreeMdl(v46);
  if ( MemoryDescriptorList )
    IoFreeMdl(MemoryDescriptorList);
  if ( v16 )
    ExFreePoolWithTag(v16, 0);
  if ( P )
    ExFreePoolWithTag(P, 0);
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x140037780  mov     [rsp+arg_8], rbx
0x140037785  mov     [rsp+arg_10], rsi
0x14003778a  push    rdi
0x14003778b  push    r12
0x14003778d  push    r13
0x14003778f  push    r14
0x140037791  push    r15
0x140037793  sub     rsp, 220h
0x14003779a  mov     rax, cs:__security_cookie
0x1400377a1  xor     rax, rsp
0x1400377a4  mov     [rsp+248h+var_38], rax
0x1400377ac  mov     r14, rcx
0x1400377af  mov     [rsp+248h+var_148], rcx
0x1400377b7  mov     rdi, [rcx+38h]
0x1400377bb  mov     [rsp+248h+var_188], rdi
0x1400377c3  mov     [rsp+248h+var_140], rdi
0x1400377cb  mov     rax, [rcx+280h]
0x1400377d2  mov     rbx, [rax+20h]
0x1400377d6  mov     [rsp+248h+var_168], rbx
0x1400377de  mov     rax, [rcx+288h]
0x1400377e5  mov     rax, [rax+28h]
0x1400377e9  mov     [rsp+248h+var_1B0], rax
0x1400377f1  xor     edx, edx; Val
0x1400377f3  lea     r8d, [rdx+68h]; Size
0x1400377f7  lea     rcx, [rsp+248h+var_118]; void *
0x1400377ff  call    memset
0x140037804  xorps   xmm0, xmm0
0x140037807  xor     eax, eax
0x140037809  movups  [rsp+248h+var_138], xmm0
0x140037811  mov     [rsp+248h+var_128], rax
0x140037819  xor     edx, edx; Val
0x14003781b  lea     r8d, [rax+65h]; Size
0x14003781f  lea     rcx, [rsp+248h+var_A8]; void *
0x140037827  call    memset
0x14003782c  xor     esi, esi
0x14003782e  mov     [rsp+248h+var_198], rsi
0x140037836  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14003783d  mov     rcx, cs:WPP_GLOBAL_Control
0x140037844  mov     r13d, 400h
0x14003784a  cmp     rcx, rax
0x14003784d  jz      short loc_140037868
0x14003784f  test    [rcx+2Ch], r13d
0x140037853  jz      short loc_140037868
0x140037855  lea     edx, [rsi+43h]
0x140037858  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x14003785f  mov     rcx, [rcx+18h]
0x140037863  call    WPP_SF_
0x140037868  mov     r12d, [rbx+1A4h]
0x14003786f  mov     rcx, r14; RxContext
0x140037872  bt      r12d, 12h
0x140037877  jnb     loc_140038165
0x14003787d  and     r12d, 8000h
0x140037884  mov     [rsp+248h+var_1C0], r12d
0x14003788c  lea     r15, [rdi+168h]
0x140037893  lea     rbx, [r14+200h]
0x14003789a  mov     [rsp+248h+var_170], rbx
0x1400378a2  mov     [rsp+248h+P], rsi
0x1400378aa  mov     rdi, rsi
0x1400378ad  mov     [rsp+248h+Mdl], rsi
0x1400378b5  mov     [rsp+248h+MemoryDescriptorList], rsi
0x1400378bd  mov     [rsp+248h+var_1C8], sil
0x1400378c5  mov     [rsp+248h+var_178], rsi
0x1400378cd  mov     [rsp+248h+var_1C4], esi
0x1400378d4  lea     rdx, [rsp+248h+var_198]
0x1400378dc  call    MRxSmbAdjustCreateParameters
0x1400378e1  mov     eax, [rbx+1Ch]
0x1400378e4  mov     ecx, 1
0x1400378e9  test    cl, al
0x1400378eb  jnz     short loc_1400378F3
0x1400378ed  mov     eax, [rbx]
0x1400378ef  test    al, 23h
0x1400378f1  jnz     short loc_1400378FF
0x1400378f3  mov     rax, [r14+48h]
0x1400378f7  bts     dword ptr [rax+48h], 9
0x1400378fc  mov     cl, sil
0x1400378ff  mov     r8, [rsp+248h+var_168]
0x140037907  mov     r8b, [r8+1F9h]
0x14003790e  mov     edx, esi
0x140037910  movzx   eax, cl
0x140037913  mov     rcx, [rsp+248h+var_1B0]
0x14003791b  cmp     [rcx+69h], sil
0x14003791f  cmovz   edx, eax
0x140037922  mov     ecx, esi
0x140037924  movzx   eax, dl
0x140037927  test    r8b, r8b
0x14003792a  cmovz   ecx, eax
0x14003792d  movzx   ebx, cl
0x140037930  xor     edx, edx
0x140037932  mov     rcx, r15
0x140037935  call    MRxSmbIsStreamFile
0x14003793a  mov     ecx, esi
0x14003793c  test    al, al
0x14003793e  cmovz   ecx, ebx
0x140037941  cmp     cs:MRxSmbOplocksDisabled, sil
0x140037948  jnz     short loc_14003799A
0x14003794a  test    cl, cl
0x14003794c  jz      short loc_14003799A
0x14003794e  movzx   eax, word ptr [r14+2EAh]
0x140037956  bt      ax, 0Bh
0x14003795b  jnb     short loc_140037966
0x14003795d  mov     [rsp+248h+var_1C4], esi
0x140037964  jmp     short loc_14003799A
0x140037966  test    r13w, ax
0x14003796a  jz      short loc_140037984
0x14003796c  mov     [rsp+248h+var_1C4], 2
0x140037977  mov     dword ptr [r14+2DCh], 9
0x140037982  jmp     short loc_14003799A
0x140037984  mov     [rsp+248h+var_1C4], 6
0x14003798f  mov     dword ptr [r14+2DCh], 1Fh
0x14003799a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400379a1  lea     rax, WPP_GLOBAL_Control
0x1400379a8  cmp     rcx, rax
0x1400379ab  jz      short loc_1400379C8
0x1400379ad  test    [rcx+2Ch], r13d
0x1400379b1  jz      short loc_1400379C8
0x1400379b3  mov     edx, 44h ; 'D'
0x1400379b8  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x1400379bf  mov     rcx, [rcx+18h]
0x1400379c3  call    WPP_SF_
0x1400379c8  test    r12d, r12d
0x1400379cb  jz      short loc_1400379D3
0x1400379cd  movzx   ebx, word ptr [r15]
0x1400379d1  jmp     short loc_1400379E4
0x1400379d3  mov     rcx, r15; UnicodeString
0x1400379d6  call    cs:__imp_RtlxUnicodeStringToAnsiSize
0x1400379dd  nop     dword ptr [rax+rax+00h]
0x1400379e2  mov     ebx, eax
0x1400379e4  lea     eax, [rbx+36h]
0x1400379e7  mov     [rsp+248h+var_160], eax
0x1400379ee  mov     edx, eax
0x1400379f0  mov     ecx, 102h
0x1400379f5  mov     r8d, 626D7358h
0x1400379fb  call    cs:__imp_ExAllocatePool2
0x140037a02  nop     dword ptr [rax+rax+00h]
0x140037a07  mov     r15, rax
0x140037a0a  mov     [rsp+248h+var_168], rax
0x140037a12  test    rax, rax
0x140037a15  jnz     short loc_140037A54
0x140037a17  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140037a1e  lea     rax, WPP_GLOBAL_Control
0x140037a25  cmp     rcx, rax
0x140037a28  jz      short loc_140037A44
0x140037a2a  test    [rcx+2Ch], r13d
0x140037a2e  jz      short loc_140037A44
0x140037a30  lea     edx, [r15+45h]
0x140037a34  lea     r8, WPP_d95790c14120305e97e490eb33b089fe_Traceguids
0x140037a3b  mov     rcx, [rcx+18h]
0x140037a3f  call    WPP_SF_
0x140037a44  mov     rcx, rsi
0x140037a47  mov     ebx, 0C000009Ah
0x140037a4c  mov     r8b, sil
0x140037a4f  jmp     loc_1400380CB
0x140037a54  add     rax, 35h ; '5'
0x140037a58  test    r12d, r12d
0x140037a5b  jz      short loc_140037A7E
0x140037a5d  mov     r8d, ebx; Size
0x140037a60  lea     rcx, [rax+1]
0x140037a64  and     rcx, 0FFFFFFFFFFFFFFFEh; void *
0x140037a68  mov     rax, [rsp+248h+var_188]
0x140037a70  mov     rdx, [rax+170h]; Src
0x140037a77  call    memmove
0x140037a7c  jmp     short loc_140037AB1
0x140037a7e  mov     [rsp+248h+var_1B0], rax
0x140037a86  mov     [rsp+248h+var_1A8], ebx
0x140037a8d  lea     r8, [rsp+248h+var_1A8]
0x140037a95  mov     rdx, [rsp+248h+var_188]
0x140037a9d  add     rdx, 168h
0x140037aa4  lea     rcx, [rsp+248h+var_1B0]
0x140037aac  call    SmbPutUnicodeStringAsOemString
0x140037ab1  mov     r13d, [r14+2C8h]
0x140037ab8  mov     [rsp+248h+var_190], r13d
0x140037ac0  mov     r12d, [r14+2CCh]
0x140037ac7  mov     [rsp+248h+var_1A8], r12d
0x140037acf  mov     eax, [rsp+248h+var_1C4]
0x140037ad6  or      eax, 10h
0x140037ad9  mov     [r15], eax
0x140037adc  mov     [r15+4], esi
0x140037ae0  mov     rcx, [rsp+248h+var_170]
0x140037ae8  mov     eax, [rcx]
0x140037aea  mov     [r15+8], eax
0x140037aee  mov     rax, [rcx+8]
0x140037af2  mov     [r15+0Ch], rax
0x140037af6  mov     eax, [rcx+10h]
0x140037af9  mov     [r15+14h], eax
0x140037afd  mov     eax, [rcx+14h]
0x140037b00  mov     [r15+18h], eax
0x140037b04  mov     eax, [rcx+18h]
0x140037b07  mov     [r15+1Ch], eax
0x140037b0b  mov     eax, [rcx+1Ch]
0x140037b0e  mov     [r15+20h], eax
0x140037b12  mov     [r15+24h], r12d
0x140037b16  mov     [r15+28h], r13d
0x140037b1a  cmp     [rsp+248h+var_1C0], esi
0x140037b21  jnz     short loc_140037B25
0x140037b23  dec     ebx
0x140037b25  mov     [r15+2Ch], ebx
0x140037b29  mov     eax, [rcx+28h]
0x140037b2c  mov     [r15+30h], eax
0x140037b30  mov     al, byte ptr [rsp+248h+var_198+4]
0x140037b37  mov     [r15+34h], al
0x140037b3b  test    r13d, r13d
0x140037b3e  jz      loc_140037E10
0x140037b44  test    r12d, r12d
0x140037b47  jz      loc_140037DBC
0x140037b4d  lea     eax, [r12+3]
0x140037b52  mov     edx, 0FFFFFFFCh
0x140037b57  and     eax, edx
0x140037b59  mov     [rsp+248h+var_1C4], eax
0x140037b60  mov     [rsp+248h+var_1C0], eax
0x140037b67  add     eax, 3
0x140037b6a  add     eax, r13d
0x140037b6d  and     eax, edx
0x140037b6f  mov     edi, eax
0x140037b71  mov     [rsp+248h+var_1B0], rdi
0x140037b79  mov     [rsp+248h+var_158], rdi
0x140037b81  mov     edx, eax
0x140037b83  mov     ecx, 102h
0x140037b88  mov     r8d, 626D73h
0x140037b8e  call    cs:__imp_ExAllocatePool2
0x140037b95  nop     dword ptr [rax+rax+00h]
0x140037b9a  mov     [rsp+248h+P], rax
0x140037ba2  test    rax, rax
0x140037ba5  jz      loc_140037A44
0x140037bab  mov     qword ptr [rsp+248h+BugCheckOnFailure], rsi
0x140037bb0  xor     r9d, r9d
0x140037bb3  xor     r8d, r8d
0x140037bb6  mov     edx, edi
0x140037bb8  mov     rcx, rax
0x140037bbb  call    cs:__imp_RxAllocateMdl2
0x140037bc2  nop     dword ptr [rax+rax+00h]
0x140037bc7  mov     rcx, rax; MemoryDescriptorList
0x140037bca  mov     [rsp+248h+MemoryDescriptorList], rax
0x140037bd2  mov     [rsp+248h+var_198], rax
0x140037bda  test    rax, rax
0x140037bdd  jz      loc_140037A47
0x140037be3  mov     ebx, esi
0x140037be5  xor     edx, edx; AccessMode
0x140037be7  lea     r8d, [rdx+2]; Operation
0x140037beb  call    cs:__imp_MmProbeAndLockPages
0x140037bf2  nop     dword ptr [rax+rax+00h]
0x140037bf7  mov     rcx, [rsp+248h+MemoryDescriptorList]
0x140037bff  mov     edi, [rsp+248h+var_1C4]
0x140037c06  mov     edx, 1
0x140037c0b  mov     r8b, [rsp+248h+var_1C8]
0x140037c13  jmp     short loc_140037C85
0x140037c15  mov     ebx, eax
0x140037c17  xor     esi, esi
0x140037c19  lea     edx, [rsi+1]
0x140037c1c  mov     rcx, [rsp+248h+var_198]
0x140037c24  mov     [rsp+248h+MemoryDescriptorList], rcx
0x140037c2c  mov     r8b, sil
0x140037c2f  mov     [rsp+248h+var_178], rsi
0x140037c37  mov     r14, [rsp+248h+var_148]
0x140037c3f  mov     r15, [rsp+248h+var_168]
0x140037c47  mov     rax, [rsp+248h+var_140]
0x140037c4f  mov     [rsp+248h+var_188], rax
0x140037c57  mov     r13d, [rsp+248h+var_190]
0x140037c5f  mov     r12d, [rsp+248h+var_1A8]
0x140037c67  mov     edi, [rsp+248h+var_1C0]
0x140037c6e  mov     [rsp+248h+var_1C4], edi
0x140037c75  mov     rax, [rsp+248h+var_158]
0x140037c7d  mov     [rsp+248h+var_1B0], rax
0x140037c85  test    ebx, ebx
0x140037c87  js      loc_1400380CB
0x140037c8d  mov     [rsp+248h+var_1C8], dl
0x140037c94  mov     ebx, r12d
0x140037c97  mov     rax, [rsp+248h+var_170]
0x140037c9f  mov     rax, [rax+20h]
0x140037ca3  mov     rdx, [rax+8]
0x140037ca7  mov     r8d, r12d; Size
0x140037caa  mov     rdx, [rdx+40h]; Src
0x140037cae  mov     rcx, [rsp+248h+P]; void *
0x140037cb6  call    memmove
0x140037cbb  mov     r8d, edi
0x140037cbe  sub     r8d, r12d; Size
0x140037cc1  mov     rcx, [rsp+248h+P]
0x140037cc9  add     rcx, rbx; void *
0x140037ccc  xor     edx, edx; Val
0x140037cce  call    memset
0x140037cd3  mov     edi, r13d
0x140037cd6  mov     ebx, [rsp+248h+var_1C4]
0x140037cdd  mov     rcx, [rsp+248h+P]
0x140037ce5  add     rcx, rbx; void *
0x140037ce8  mov     r8d, r13d; Size
0x140037ceb  mov     rdx, [r14+2B8h]; Src
0x140037cf2  call    memmove
0x140037cf7  mov     r8d, dword ptr [rsp+248h+var_1B0]
0x140037cff  sub     r8d, [rsp+248h+var_1C4]
0x140037d07  sub     r8d, r13d; Size
0x140037d0a  lea     rcx, [rbx+rdi]
0x140037d0e  add     rcx, [rsp+248h+P]; void *
0x140037d16  xor     edx, edx; Val
0x140037d18  call    memset
0x140037d1d  mov     rdi, [rsp+248h+MemoryDescriptorList]
0x140037d25  mov     ebx, esi
0x140037d27  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140037d2e  lea     rax, WPP_GLOBAL_Control
0x140037d35  cmp     rcx, rax
0x140037d38  jz      short loc_140037D64
0x140037d3a  test    dword ptr [rcx+2Ch], 400h
  ... truncated ...
```
