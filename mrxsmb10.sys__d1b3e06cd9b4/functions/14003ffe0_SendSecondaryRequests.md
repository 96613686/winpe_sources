# SendSecondaryRequests

- ea: `0x14003ffe0`
- end: `0x140040b0b`
- name: `SendSecondaryRequests`
- size: `2859`
- prototype: `void __fastcall(char *Context)`
- caller_count: `0`
- callee_count: `12`
- tags: ``

## callees

- `0x1400054b0`
- `0x14000a600`
- `0x14000dfa8`
- `0x14000dfd8`
- `0x14000e01c`
- `0x14000ebd8`
- `0x1400145e0`
- `0x140014670`
- `0x1400148c4`
- `0x14003f0c8`
- `0x14003ffe0`
- `0x1400512e0`

## import_xrefs

- `ntoskrnl!MmUnmapLockedPages` at `0x14004050f`
- `ntoskrnl!MmUnmapLockedPages` at `0x140040643`
- `ntoskrnl!MmUnmapLockedPages` at `0x14004050f`
- `ntoskrnl!MmUnmapLockedPages` at `0x140040643`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004045a`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14004045a`
- `ntoskrnl!IoBuildPartialMdl` at `0x14004053b`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400405f3`
- `ntoskrnl!IoBuildPartialMdl` at `0x140040671`
- `ntoskrnl!IoBuildPartialMdl` at `0x14004053b`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400405f3`
- `ntoskrnl!IoBuildPartialMdl` at `0x140040671`
- `ntoskrnl!IoFreeMdl` at `0x140040424`
- `ntoskrnl!IoFreeMdl` at `0x140040a40`
- `ntoskrnl!IoFreeMdl` at `0x140040a63`
- `ntoskrnl!IoFreeMdl` at `0x140040a97`
- `ntoskrnl!IoFreeMdl` at `0x140040ab3`
- `ntoskrnl!IoFreeMdl` at `0x140040424`
- `ntoskrnl!IoFreeMdl` at `0x140040a40`
- `ntoskrnl!IoFreeMdl` at `0x140040a63`
- `ntoskrnl!IoFreeMdl` at `0x140040a97`
- `ntoskrnl!IoFreeMdl` at `0x140040ab3`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400403a1`
- `ntoskrnl!MmProbeAndLockPages` at `0x1400403a1`
- `ntoskrnl!ExAllocatePool2` at `0x1400400d6`
- `ntoskrnl!ExAllocatePool2` at `0x1400400d6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a7e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140040a7e`
- `rdbss!RxUnlockHeaderPages` at `0x140040a54`
- `rdbss!RxUnlockHeaderPages` at `0x140040a54`
- `rdbss!RxAllocateMdl2` at `0x14004021b`
- `rdbss!RxAllocateMdl2` at `0x1400402cd`
- `rdbss!RxAllocateMdl2` at `0x1400402f3`
- `rdbss!RxAllocateMdl2` at `0x140040361`
- `rdbss!RxAllocateMdl2` at `0x14004021b`
- `rdbss!RxAllocateMdl2` at `0x1400402cd`
- `rdbss!RxAllocateMdl2` at `0x1400402f3`
- `rdbss!RxAllocateMdl2` at `0x140040361`

## pseudocode

```c
void __fastcall SendSecondaryRequests(char *Context)
{
  int v2; // edi
  struct _MDL *v3; // r15
  _BYTE *v4; // rsi
  int v5; // ecx
  int v6; // ecx
  unsigned int v7; // r12d
  __int64 Pool2; // rax
  __int64 v9; // rdx
  unsigned int v10; // edi
  unsigned int v11; // r9d
  unsigned int v12; // edx
  unsigned int v13; // edx
  __int64 Mdl2; // rax
  struct _MDL *v15; // rax
  PVOID MappedSystemVa; // rax
  char v17; // cl
  struct _MDL *v18; // rsi
  unsigned int v19; // edi
  ULONG v20; // r13d
  unsigned int v21; // eax
  ULONG v22; // r9d
  ULONG v23; // r12d
  ULONG v24; // eax
  ULONG v25; // edi
  unsigned int v26; // esi
  unsigned int v27; // r8d
  _BYTE *v28; // rdx
  __int64 v29; // r8
  unsigned int v30; // ecx
  ULONG v31; // esi
  unsigned __int16 v32; // di
  unsigned int v33; // eax
  ULONG v34; // [rsp+50h] [rbp-C8h]
  unsigned int v35; // [rsp+54h] [rbp-C4h]
  int v36; // [rsp+58h] [rbp-C0h]
  unsigned int v37; // [rsp+5Ch] [rbp-BCh]
  unsigned int v38; // [rsp+60h] [rbp-B8h]
  unsigned int v39; // [rsp+64h] [rbp-B4h]
  int v40; // [rsp+68h] [rbp-B0h]
  unsigned int v41; // [rsp+6Ch] [rbp-ACh]
  int v42; // [rsp+70h] [rbp-A8h]
  __int64 v43; // [rsp+78h] [rbp-A0h]
  char *v44; // [rsp+80h] [rbp-98h]
  PMDL Mdl; // [rsp+88h] [rbp-90h]
  PMDL MemoryDescriptorList; // [rsp+90h] [rbp-88h]
  char *VirtualAddress; // [rsp+98h] [rbp-80h]
  struct _MDL *TargetMdl; // [rsp+A0h] [rbp-78h]
  __int64 v49; // [rsp+B0h] [rbp-68h]
  __int64 v50; // [rsp+B8h] [rbp-60h]
  _BYTE *v51; // [rsp+C8h] [rbp-50h]
  PVOID P; // [rsp+D0h] [rbp-48h]
  char v53; // [rsp+120h] [rbp+8h]
  char v54; // [rsp+128h] [rbp+10h]
  unsigned int v55; // [rsp+130h] [rbp+18h]
  unsigned int v56; // [rsp+138h] [rbp+20h]

  v2 = 0;
  v56 = 0;
  Mdl = 0;
  MemoryDescriptorList = 0;
  TargetMdl = 0;
  v3 = 0;
  VirtualAddress = 0;
  v44 = 0;
  LODWORD(v49) = 0;
  LODWORD(v50) = 0;
  v41 = *((_DWORD *)Context + 104);
  v39 = v41 - *((_DWORD *)Context + 105);
  v40 = *((_DWORD *)Context + 94);
  v34 = v40 - *((_DWORD *)Context + 95);
  v4 = Context + 509;
  v51 = Context + 509;
  v5 = (unsigned __int8)Context[509] - 37;
  if ( v5 && (v6 = v5 - 13) != 0 )
  {
    if ( v6 == 110 )
    {
      v7 = 72;
    }
    else
    {
      v2 = -1073741297;
      v7 = 0;
    }
  }
  else
  {
    v7 = 56;
  }
  v55 = v7;
  Pool2 = ExAllocatePool2(66, v7 + 32, 1918135635);
  P = (PVOID)Pool2;
  if ( v2 || !Pool2 )
  {
    v43 = 0;
    v10 = -1073741670;
  }
  else
  {
    v43 = Pool2 + 32;
    LOBYTE(v9) = *v4 + 1;
    v10 = SmbTransactBuildHeader(Context, v9, Pool2 + 32);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 93, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v10);
  }
  if ( v10 )
    goto LABEL_51;
  v11 = *((_DWORD *)Context + 130);
  v56 = v11;
  if ( v34 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 94, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v34);
      v11 = v56;
    }
    v50 = *(_QWORD *)(*((_QWORD *)Context + 46) + 32LL) + *(unsigned int *)(*((_QWORD *)Context + 46) + 44LL);
    v44 = (char *)(v50 + *((unsigned int *)Context + 95));
    v12 = v11;
    if ( *((_DWORD *)Context + 94) < v11 )
      v12 = *((_DWORD *)Context + 94);
    Mdl = (PMDL)RxAllocateMdl2(0, v12 + 4095, 0, 0, 0);
    if ( !Mdl )
      v10 = -1073741670;
  }
  if ( v39 )
  {
    if ( v10 )
      goto LABEL_51;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 95, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v39);
    v49 = *(_QWORD *)(*((_QWORD *)Context + 50) + 32LL) + *(unsigned int *)(*((_QWORD *)Context + 50) + 44LL);
    VirtualAddress = (char *)(v49 + *((unsigned int *)Context + 105));
    v13 = v56;
    if ( *((_DWORD *)Context + 104) < v56 )
      v13 = *((_DWORD *)Context + 104);
    MemoryDescriptorList = (PMDL)RxAllocateMdl2(0, v13 + 4095, 0, 0, 0);
    Mdl2 = RxAllocateMdl2(0, 4099, 0, 0, 0);
    TargetMdl = (struct _MDL *)Mdl2;
    if ( !MemoryDescriptorList || !Mdl2 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
      }
      v10 = -1073741670;
    }
  }
  if ( !v10 )
  {
    v15 = (struct _MDL *)RxAllocateMdl2(v43, v7, 0, 0, 0);
    v3 = v15;
    if ( v15 && v15->ByteOffset >= 0x20 )
      v15->MdlFlags |= 0x1000u;
    if ( v15 )
    {
      v10 = 0;
      MmProbeAndLockPages(v15, 0, IoModifyAccess);
      if ( (v3->MdlFlags & 5) != 0 )
        MappedSystemVa = v3->MappedSystemVa;
      else
        MappedSystemVa = MmMapLockedPagesSpecifyCache(v3, 0, MmCached, 0, 0, 0x40000000u);
      if ( MappedSystemVa )
        goto LABEL_51;
    }
    else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
           && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids);
    }
    v10 = -1073741670;
  }
LABEL_51:
  v36 = 0;
  v17 = 0;
  v54 = 0;
  v53 = 0;
  while ( !v10 && (v39 || v34) )
  {
    v35 = 0;
    v18 = v3;
    v19 = v7;
    v37 = v7;
    v20 = v39;
    if ( v56 - v7 < v39 )
      v20 = v56 - v7;
    if ( v20 )
    {
      v18 = MemoryDescriptorList;
      if ( v17 && (MemoryDescriptorList->MdlFlags & 0x20) != 0 )
        MmUnmapLockedPages(MemoryDescriptorList->MappedSystemVa, MemoryDescriptorList);
      v54 = 1;
      IoBuildPartialMdl(*((PMDL *)Context + 50), MemoryDescriptorList, VirtualAddress, v20);
      v35 = (_DWORD)VirtualAddress - v49;
      VirtualAddress += v20;
      v39 -= v20;
      v19 = v7 + ((v20 + 7) & 0xFFFFFFF8);
      v37 = v19;
      v3->Next = MemoryDescriptorList;
    }
    v21 = v56;
    if ( v19 < v56 && (v22 = v34) != 0 )
    {
      v23 = v19 - v55 - v20;
      if ( v19 - v55 != v20 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 98, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v23);
        }
        IoBuildPartialMdl(
          (PMDL)MrxSmbCeGlobalPadding,
          TargetMdl,
          (PVOID)(*((_QWORD *)MrxSmbCeGlobalPadding + 4) + *((unsigned int *)MrxSmbCeGlobalPadding + 11)),
          v23);
        v18->Next = TargetMdl;
        v18 = TargetMdl;
        v22 = v34;
        v21 = v56;
      }
      v24 = v21 - v19;
      v25 = v22;
      if ( v24 < v22 )
        v25 = v24;
      if ( v53 && (Mdl->MdlFlags & 0x20) != 0 )
        MmUnmapLockedPages(Mdl->MappedSystemVa, Mdl);
      v53 = 1;
      IoBuildPartialMdl(*((PMDL *)Context + 46), Mdl, v44, v25);
      v18->Next = Mdl;
      v42 = (_DWORD)v44 - v50;
      v44 += v25;
      v34 -= v25;
      v26 = v37;
    }
    else
    {
      v23 = 0;
      v25 = 0;
      v42 = 0;
      v26 = 0;
      v37 = 0;
    }
    v27 = v20 != 0 ? v55 : 0;
    v38 = v27;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_lll(WPP_GLOBAL_Control->AttachedDevice, 99);
      v27 = v20 != 0 ? v55 : 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v27, v26);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v35, v42);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 102, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v41, v40);
    v28 = v51;
    if ( *v51 == 37 || *v51 == 50 )
    {
      v29 = v43;
      *(_BYTE *)(v43 + 32) = 8;
      *(_WORD *)(v43 + 33) = v41;
      *(_WORD *)(v43 + 35) = v40;
      *(_WORD *)(v43 + 37) = v20;
      *(_WORD *)(v43 + 39) = v38;
      *(_WORD *)(v43 + 41) = v35;
      *(_WORD *)(v43 + 43) = v25;
      *(_WORD *)(v43 + 45) = v26;
      *(_WORD *)(v43 + 47) = v42;
      v30 = 17;
      v36 = 17;
      if ( *v51 == 50 )
      {
        v30 = 19;
        v36 = 19;
        *(_BYTE *)(v43 + 32) = 9;
        *(_WORD *)(v43 + 49) = 0;
      }
    }
    else
    {
      v29 = v43;
      if ( (unsigned __int8)*v51 == 160 )
      {
        *(_DWORD *)(v43 + 32) = 18;
        *(_DWORD *)(v43 + 36) = v41;
        *(_DWORD *)(v43 + 40) = v40;
        *(_DWORD *)(v43 + 44) = v20;
        *(_DWORD *)(v43 + 48) = v38;
        *(_DWORD *)(v43 + 52) = v35;
        *(_DWORD *)(v43 + 56) = v25;
        *(_DWORD *)(v43 + 60) = v26;
        *(_DWORD *)(v43 + 64) = v42;
        *(_BYTE *)(v43 + 68) = 0;
        v30 = 37;
        v36 = 37;
      }
      else
      {
        v30 = v36;
      }
    }
    v31 = v23 + v20 + v25 + v55;
    v32 = v23 + v20 + v25 + v55 - v30 - 34;
    *(_WORD *)(v30 + v29 + 32) = v32;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
    {
      WPP_SF_ddD(WPP_GLOBAL_Control->AttachedDevice, v51, v29, v31, v32, v32);
      v29 = v43;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v29);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_LLLLLL(WPP_GLOBAL_Control->AttachedDevice, v28, v29, v38, v35, v41, v37, v42, v40);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x200) != 0 )
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v32, v31);
    v33 = SmbCeSend(Context);
    v10 = v33;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v33);
    if ( v10 != 259 && v10 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) != 0 )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 108, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids, v10);
      }
      break;
    }
    v10 = 0;
    v7 = v55;
    v17 = v54;
  }
  if ( Mdl )
    IoFreeMdl(Mdl);
  if ( v3 )
  {
    RxUnlockHeaderPages(v3);
    IoFreeMdl(v3);
  }
  if ( P )
    ExFreePoolWithTag(P, 0);
  if ( MemoryDescriptorList )
    IoFreeMdl(MemoryDescriptorList);
  if ( TargetMdl )
    IoFreeMdl(TargetMdl);
  if ( v10 || (Context[510] & 2) != 0 )
  {
    *((_DWORD *)Context + 12) = v10;
    if ( (Context[510] & 2) == 0 )
      SmbCeDecrementPendingOperations(Context, 8);
  }
  SmbCeDecrementPendingOperationsAndFinalize(Context);
}

```

## disassembly

```asm
0x14003ffe0  mov     [rsp+arg_0], rcx
0x14003ffe5  push    rbx
0x14003ffe6  push    rsi
0x14003ffe7  push    rdi
0x14003ffe8  push    r12
0x14003ffea  push    r13
0x14003ffec  push    r14
0x14003ffee  push    r15
0x14003fff0  sub     rsp, 0E0h
0x14003fff7  mov     r14, rcx
0x14003fffa  xor     ebx, ebx
0x14003fffc  mov     edi, ebx
0x14003fffe  mov     [rsp+118h+arg_18], ebx
0x140040005  mov     [rsp+118h+Mdl], rbx
0x14004000d  mov     [rsp+118h+MemoryDescriptorList], rbx
0x140040015  mov     [rsp+118h+TargetMdl], rbx
0x14004001d  mov     r15d, ebx
0x140040020  mov     [rsp+118h+VirtualAddress], rbx
0x140040028  mov     [rsp+118h+var_A8], rbx
0x14004002d  mov     [rsp+118h+var_98], rbx
0x140040035  mov     [rsp+118h+var_70], rbx
0x14004003d  mov     [rsp+118h+var_68], rbx
0x140040045  mov     [rsp+118h+var_60], rbx
0x14004004d  mov     eax, [rcx+1A0h]
0x140040053  mov     [rsp+118h+var_AC], eax
0x140040057  mov     [rsp+118h+var_C0], eax
0x14004005b  sub     eax, [rcx+1A4h]
0x140040061  mov     [rsp+118h+var_B4], eax
0x140040065  mov     [rsp+118h+var_B8], eax
0x140040069  mov     eax, [rcx+178h]
0x14004006f  mov     [rsp+118h+var_B0], eax
0x140040073  mov     [rsp+118h+var_C4], eax
0x140040077  sub     eax, [rcx+17Ch]
0x14004007d  mov     [rsp+118h+var_C8], eax
0x140040081  mov     [rsp+118h+var_BC], eax
0x140040085  lea     rsi, [rcx+1FDh]
0x14004008c  mov     [rsp+118h+var_50], rsi
0x140040094  movzx   ecx, byte ptr [rsi]
0x140040097  sub     ecx, 25h ; '%'
0x14004009a  jz      short loc_1400400B8
0x14004009c  sub     ecx, 0Dh
0x14004009f  jz      short loc_1400400B8
0x1400400a1  cmp     ecx, 6Eh ; 'n'
0x1400400a4  jz      short loc_1400400B0
0x1400400a6  mov     edi, 0C000020Fh
0x1400400ab  mov     r12d, ebx
0x1400400ae  jmp     short loc_1400400BE
0x1400400b0  mov     r12d, 48h ; 'H'
0x1400400b6  jmp     short loc_1400400BE
0x1400400b8  mov     r12d, 38h ; '8'
0x1400400be  mov     [rsp+118h+arg_10], r12d
0x1400400c6  lea     edx, [r12+20h]
0x1400400cb  mov     ecx, 42h ; 'B'
0x1400400d0  mov     r8d, 72546D53h
0x1400400d6  call    cs:__imp_ExAllocatePool2
0x1400400dd  nop     dword ptr [rax+rax+00h]
0x1400400e2  mov     [rsp+118h+P], rax
0x1400400ea  test    edi, edi
0x1400400ec  jnz     short loc_140040152
0x1400400ee  test    rax, rax
0x1400400f1  jz      short loc_140040152
0x1400400f3  add     rax, 20h ; ' '
0x1400400f7  mov     [rsp+118h+var_A0], rax
0x1400400fc  mov     dl, [rsi]
0x1400400fe  inc     dl
0x140040100  mov     r8, rax
0x140040103  mov     rcx, r14
0x140040106  call    SmbTransactBuildHeader
0x14004010b  mov     edi, eax
0x14004010d  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140040114  mov     rcx, cs:WPP_GLOBAL_Control
0x14004011b  mov     r13d, 400h
0x140040121  cmp     rcx, rax
0x140040124  jz      short loc_14004014B
0x140040126  test    [rcx+2Ch], r13d
0x14004012a  jz      short loc_140040144
0x14004012c  mov     edx, 5Dh ; ']'
0x140040131  mov     r9d, edi
0x140040134  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14004013b  mov     rcx, [rcx+18h]
0x14004013f  call    WPP_SF_d
0x140040144  mov     esi, 0C000009Ah
0x140040149  jmp     short loc_140040164
0x14004014b  mov     esi, 0C000009Ah
0x140040150  jmp     short loc_14004016B
0x140040152  mov     [rsp+118h+var_A0], rbx
0x140040157  mov     esi, 0C000009Ah
0x14004015c  mov     edi, esi
0x14004015e  mov     r13d, 400h
0x140040164  lea     rax, WPP_GLOBAL_Control
0x14004016b  test    edi, edi
0x14004016d  jnz     loc_14004049D
0x140040173  mov     r9d, [r14+208h]
0x14004017a  mov     [rsp+118h+arg_18], r9d
0x140040182  mov     [rsp+118h+arg_8], r9d
0x14004018a  mov     r8d, [rsp+118h+var_C8]
0x14004018f  test    r8d, r8d
0x140040192  jz      loc_140040235
0x140040198  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004019f  cmp     rcx, rax
0x1400401a2  jz      short loc_1400401C8
0x1400401a4  test    [rcx+2Ch], r13d
0x1400401a8  jz      short loc_1400401C8
0x1400401aa  lea     edx, [rdi+5Eh]
0x1400401ad  mov     r9d, r8d
0x1400401b0  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x1400401b7  mov     rcx, [rcx+18h]
0x1400401bb  call    WPP_SF_d
0x1400401c0  mov     r9d, [rsp+118h+arg_18]
0x1400401c8  mov     rax, [r14+170h]
0x1400401cf  mov     ecx, [rax+2Ch]
0x1400401d2  add     rcx, [rax+20h]
0x1400401d6  mov     [rsp+118h+var_60], rcx
0x1400401de  mov     eax, [r14+17Ch]
0x1400401e5  add     rax, rcx
0x1400401e8  mov     [rsp+118h+var_98], rax
0x1400401f0  mov     [rsp+118h+var_70], rax
0x1400401f8  mov     eax, [r14+178h]
0x1400401ff  mov     edx, r9d
0x140040202  cmp     eax, r9d
0x140040205  cmovb   edx, eax
0x140040208  add     edx, 0FFFh
0x14004020e  mov     qword ptr [rsp+118h+BugCheckOnFailure], rbx
0x140040213  xor     r9d, r9d
0x140040216  xor     r8d, r8d
0x140040219  xor     ecx, ecx
0x14004021b  call    cs:__imp_RxAllocateMdl2
0x140040222  nop     dword ptr [rax+rax+00h]
0x140040227  mov     [rsp+118h+Mdl], rax
0x14004022f  test    rax, rax
0x140040232  cmovz   edi, esi
0x140040235  mov     r8d, [rsp+118h+var_B4]
0x14004023a  test    r8d, r8d
0x14004023d  jz      loc_140040346
0x140040243  test    edi, edi
0x140040245  jnz     loc_14004049D
0x14004024b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140040252  lea     rax, WPP_GLOBAL_Control
0x140040259  cmp     rcx, rax
0x14004025c  jz      short loc_14004027A
0x14004025e  test    [rcx+2Ch], r13d
0x140040262  jz      short loc_14004027A
0x140040264  lea     edx, [rdi+5Fh]
0x140040267  mov     r9d, r8d
0x14004026a  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140040271  mov     rcx, [rcx+18h]
0x140040275  call    WPP_SF_d
0x14004027a  mov     rax, [r14+190h]
0x140040281  mov     ecx, [rax+2Ch]
0x140040284  add     rcx, [rax+20h]
0x140040288  mov     [rsp+118h+var_68], rcx
0x140040290  mov     eax, [r14+1A4h]
0x140040297  add     rax, rcx
0x14004029a  mov     [rsp+118h+VirtualAddress], rax
0x1400402a2  mov     [rsp+118h+var_A8], rax
0x1400402a7  mov     eax, [r14+1A0h]
0x1400402ae  mov     edx, [rsp+118h+arg_18]
0x1400402b5  cmp     eax, edx
0x1400402b7  cmovb   edx, eax
0x1400402ba  add     edx, 0FFFh
0x1400402c0  mov     qword ptr [rsp+118h+BugCheckOnFailure], rbx
0x1400402c5  xor     r9d, r9d
0x1400402c8  xor     r8d, r8d
0x1400402cb  xor     ecx, ecx
0x1400402cd  call    cs:__imp_RxAllocateMdl2
0x1400402d4  nop     dword ptr [rax+rax+00h]
0x1400402d9  mov     [rsp+118h+MemoryDescriptorList], rax
0x1400402e1  mov     qword ptr [rsp+118h+BugCheckOnFailure], rbx
0x1400402e6  xor     r9d, r9d
0x1400402e9  xor     r8d, r8d
0x1400402ec  mov     edx, 1003h
0x1400402f1  xor     ecx, ecx
0x1400402f3  call    cs:__imp_RxAllocateMdl2
0x1400402fa  nop     dword ptr [rax+rax+00h]
0x1400402ff  mov     [rsp+118h+TargetMdl], rax
0x140040307  cmp     [rsp+118h+MemoryDescriptorList], rbx
0x14004030f  jz      short loc_140040316
0x140040311  test    rax, rax
0x140040314  jnz     short loc_140040346
0x140040316  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004031d  lea     rax, WPP_GLOBAL_Control
0x140040324  cmp     rcx, rax
0x140040327  jz      short loc_140040344
0x140040329  test    [rcx+2Ch], r13d
0x14004032d  jz      short loc_140040344
0x14004032f  mov     edx, 60h ; '`'
0x140040334  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x14004033b  mov     rcx, [rcx+18h]
0x14004033f  call    WPP_SF_
0x140040344  mov     edi, esi
0x140040346  test    edi, edi
0x140040348  jnz     loc_14004049D
0x14004034e  mov     qword ptr [rsp+118h+BugCheckOnFailure], rbx
0x140040353  xor     r9d, r9d
0x140040356  xor     r8d, r8d
0x140040359  mov     edx, r12d
0x14004035c  mov     rcx, [rsp+118h+var_A0]
0x140040361  call    cs:__imp_RxAllocateMdl2
0x140040368  nop     dword ptr [rax+rax+00h]
0x14004036d  mov     r15, rax
0x140040370  mov     [rsp+118h+var_58], rax
0x140040378  test    rax, rax
0x14004037b  jz      short loc_14004038D
0x14004037d  cmp     dword ptr [rax+2Ch], 20h ; ' '
0x140040381  jb      short loc_14004038D
0x140040383  mov     eax, 1000h
0x140040388  or      [r15+0Ah], ax
0x14004038d  test    r15, r15
0x140040390  jz      loc_14004046D
0x140040396  mov     edi, ebx
0x140040398  xor     edx, edx; AccessMode
0x14004039a  lea     r8d, [rdx+2]; Operation
0x14004039e  mov     rcx, r15; MemoryDescriptorList
0x1400403a1  call    cs:__imp_MmProbeAndLockPages
0x1400403a8  nop     dword ptr [rax+rax+00h]
0x1400403ad  jmp     short loc_14004041D
0x1400403af  mov     edi, eax
0x1400403b1  xor     ebx, ebx
0x1400403b3  mov     esi, 0C000009Ah
0x1400403b8  mov     r14, [rsp+118h+arg_0]
0x1400403c0  mov     eax, [rsp+118h+arg_8]
0x1400403c7  mov     [rsp+118h+arg_18], eax
0x1400403ce  mov     r15, [rsp+118h+var_58]
0x1400403d6  mov     r8d, [rsp+118h+var_B8]
0x1400403db  mov     [rsp+118h+var_B4], r8d
0x1400403e0  mov     eax, [rsp+118h+var_BC]
0x1400403e4  mov     [rsp+118h+var_C8], eax
0x1400403e8  mov     rax, [rsp+118h+var_A8]
0x1400403ed  mov     [rsp+118h+VirtualAddress], rax
0x1400403f5  mov     rax, [rsp+118h+var_70]
0x1400403fd  mov     [rsp+118h+var_98], rax
0x140040405  mov     eax, [rsp+118h+var_C0]
0x140040409  mov     [rsp+118h+var_AC], eax
0x14004040d  mov     eax, [rsp+118h+var_C4]
0x140040411  mov     [rsp+118h+var_B0], eax
0x140040415  mov     r12d, [rsp+118h+arg_10]
0x14004041d  test    edi, edi
0x14004041f  jz      short loc_140040435
0x140040421  mov     rcx, r15; Mdl
0x140040424  call    cs:__imp_IoFreeMdl
0x14004042b  nop     dword ptr [rax+rax+00h]
0x140040430  mov     r15, rbx
0x140040433  jmp     short loc_14004049D
0x140040435  test    byte ptr [r15+0Ah], 5
0x14004043a  jz      short loc_140040442
0x14004043c  mov     rax, [r15+18h]
0x140040440  jmp     short loc_140040466
0x140040442  mov     [rsp+118h+Priority], 40000000h; Priority
0x14004044a  mov     [rsp+118h+BugCheckOnFailure], ebx; BugCheckOnFailure
0x14004044e  xor     r9d, r9d; RequestedAddress
0x140040451  xor     edx, edx; AccessMode
0x140040453  lea     r8d, [r9+1]; CacheType
0x140040457  mov     rcx, r15; MemoryDescriptorList
0x14004045a  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140040461  nop     dword ptr [rax+rax+00h]
0x140040466  test    rax, rax
0x140040469  jnz     short loc_14004049D
0x14004046b  jmp     short loc_14004049B
0x14004046d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140040474  lea     rax, WPP_GLOBAL_Control
0x14004047b  cmp     rcx, rax
0x14004047e  jz      short loc_14004049B
0x140040480  test    [rcx+2Ch], r13d
0x140040484  jz      short loc_14004049B
0x140040486  mov     edx, 61h ; 'a'
0x14004048b  lea     r8, WPP_19ab601387ce39e1c41ce94b9491d1fd_Traceguids
0x140040492  mov     rcx, [rcx+18h]
0x140040496  call    WPP_SF_
0x14004049b  mov     edi, esi
0x14004049d  mov     [rsp+118h+var_C0], ebx
0x1400404a1  mov     cl, bl
0x1400404a3  mov     byte ptr [rsp+118h+arg_8], bl
0x1400404aa  mov     byte ptr [rsp+118h+arg_0], bl
0x1400404b1  test    edi, edi
0x1400404b3  jnz     loc_140040A30
0x1400404b9  mov     edx, [rsp+118h+var_B4]
0x1400404bd  test    edx, edx
0x1400404bf  jnz     short loc_1400404CB
0x1400404c1  cmp     [rsp+118h+var_C8], ebx
0x1400404c5  jbe     loc_140040A30
0x1400404cb  mov     [rsp+118h+var_C4], ebx
0x1400404cf  mov     rsi, r15
0x1400404d2  mov     edi, r12d
0x1400404d5  mov     [rsp+118h+var_BC], r12d
0x1400404da  mov     eax, [rsp+118h+arg_18]
0x1400404e1  sub     eax, r12d
0x1400404e4  mov     r13d, edx
0x1400404e7  cmp     eax, edx
0x1400404e9  cmovb   r13d, eax
0x1400404ed  test    r13d, r13d
0x1400404f0  jz      loc_140040578
0x1400404f6  mov     rsi, [rsp+118h+MemoryDescriptorList]
0x1400404fe  test    cl, cl
0x140040500  jz      short loc_14004051B
0x140040502  test    byte ptr [rsi+0Ah], 20h
0x140040506  jz      short loc_14004051B
0x140040508  mov     rdx, rsi; MemoryDescriptorList
0x14004050b  mov     rcx, [rsi+18h]; BaseAddress
0x14004050f  call    cs:__imp_MmUnmapLockedPages
0x140040516  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
