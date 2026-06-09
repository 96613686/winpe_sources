# FveVerifyIceCrypto

- ea: `0x1400af494`
- end: `0x1400b092f`
- name: `FveVerifyIceCrypto`
- size: `5275`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, int, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `30`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400a9224`
- `0x1400adfbc`
- `0x1400ba750`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140005e60`
- `0x140007da8`
- `0x140008348`
- `0x140008cd0`
- `0x140008d20`
- `0x140008d68`
- `0x140008e80`
- `0x14000afb4`
- `0x14000c1e0`
- `0x14000c224`
- `0x14000c808`
- `0x14000c89c`
- `0x14000cda8`
- `0x14000cf18`
- `0x140014d88`
- `0x140017a34`
- `0x140017a50`
- `0x140022bf0`
- `0x140023040`
- `0x140063bd4`
- `0x14009eed0`
- `0x1400a865c`
- `0x1400af1a8`
- `0x1400af494`
- `0x1400b6f14`
- `0x1400cb034`
- `0x1400e1690`
- `0x1400e1d84`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400afb2a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400afb39`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400afb2a`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400afb39`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400afb50`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400afb62`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400afb50`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400afb62`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400afa5b`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400afa5b`
- `ntoskrnl!IoFreeIrp` at `0x1400b0620`
- `ntoskrnl!IoFreeIrp` at `0x1400b0620`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400afede`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400b00ac`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400b03a2`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400b04dd`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400afede`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400b00ac`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400b03a2`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400b04dd`
- `ntoskrnl!RtlCompareMemory` at `0x1400aff88`
- `ntoskrnl!RtlCompareMemory` at `0x1400b0124`
- `ntoskrnl!RtlCompareMemory` at `0x1400b0544`
- `ntoskrnl!RtlCompareMemory` at `0x1400aff88`
- `ntoskrnl!RtlCompareMemory` at `0x1400b0124`
- `ntoskrnl!RtlCompareMemory` at `0x1400b0544`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400afe22`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400affed`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400b02f9`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400b042c`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400afe22`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400affed`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400b02f9`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400b042c`
- `ntoskrnl!IoFreeMdl` at `0x1400b0638`
- `ntoskrnl!IoFreeMdl` at `0x1400b0650`
- `ntoskrnl!IoFreeMdl` at `0x1400b0668`
- `ntoskrnl!IoFreeMdl` at `0x1400b0638`
- `ntoskrnl!IoFreeMdl` at `0x1400b0650`
- `ntoskrnl!IoFreeMdl` at `0x1400b0668`
- `ntoskrnl!IoAllocateMdl` at `0x1400afa80`
- `ntoskrnl!IoAllocateMdl` at `0x1400afaa5`
- `ntoskrnl!IoAllocateMdl` at `0x1400afacd`
- `ntoskrnl!IoAllocateMdl` at `0x1400afa80`
- `ntoskrnl!IoAllocateMdl` at `0x1400afaa5`
- `ntoskrnl!IoAllocateMdl` at `0x1400afacd`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af732`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b01b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b05ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b060c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af732`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b01b5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b05ef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b060c`
- `ntoskrnl!ExAllocatePool2` at `0x1400af96d`
- `ntoskrnl!ExAllocatePool2` at `0x1400af9fe`
- `ntoskrnl!ExAllocatePool2` at `0x1400afa19`
- `ntoskrnl!ExAllocatePool2` at `0x1400afa3a`
- `ntoskrnl!ExAllocatePool2` at `0x1400af96d`
- `ntoskrnl!ExAllocatePool2` at `0x1400af9fe`
- `ntoskrnl!ExAllocatePool2` at `0x1400afa19`
- `ntoskrnl!ExAllocatePool2` at `0x1400afa3a`
- `ksecdd!BCryptGenRandom` at `0x1400afba7`
- `ksecdd!BCryptGenRandom` at `0x1400afba7`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400af751`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400af751`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400afb7f`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400afb7f`

## pseudocode

```c
unsigned __int8 __fastcall FveVerifyIceCrypto(
        __int64 *a1,
        char a2,
        __int16 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        unsigned __int64 a7,
        unsigned __int64 a8,
        NTSTATUS *a9)
{
  __int64 *v10; // r12
  unsigned __int64 v11; // rsi
  USHORT v12; // r14
  __int64 Pool2; // r13
  __int64 v14; // rax
  unsigned int v15; // ecx
  int v16; // ebx
  unsigned int v17; // edi
  bool v18; // r15
  unsigned __int64 v19; // rdx
  unsigned __int64 v20; // rcx
  NTSTATUS IceKey; // edi
  char v22; // r15
  ULONG v23; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  __int16 v25; // r9
  unsigned int v26; // r14d
  unsigned int v27; // r10d
  __int64 v28; // rax
  unsigned int v29; // r8d
  __int64 v30; // r8
  __int64 v31; // r9
  unsigned __int8 v32; // bl
  unsigned int v33; // r15d
  unsigned int v34; // r12d
  unsigned __int16 v35; // r13
  unsigned int v36; // r8d
  __int64 *v37; // rbx
  __int64 v38; // rax
  __int64 *v39; // rax
  void *v40; // rdi
  void *v41; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  IRP *v44; // rbx
  struct _MDL *Mdl; // rax
  struct _MDL *v46; // rdi
  __int64 v47; // rdx
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  char v51; // al
  __int64 v52; // rdx
  __int64 v53; // rcx
  int v54; // edi
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // rcx
  __int64 v58; // rdx
  __int64 v59; // rcx
  char *v60; // rcx
  __int64 v61; // rdx
  unsigned int v62; // eax
  size_t v63; // rdx
  char *v64; // r15
  __int64 v65; // rdx
  char *v66; // r8
  unsigned __int64 v67; // rax
  char *v68; // rdi
  unsigned int v69; // eax
  ULONG v70; // r12d
  __int64 v71; // rdi
  char *v72; // rdx
  struct _MDL *v73; // rcx
  char *v74; // rax
  size_t v75; // r12
  __int64 v76; // rdx
  __int64 v77; // rcx
  int v78; // eax
  __int64 *v79; // r12
  __int64 v80; // rdx
  __int64 v81; // rcx
  int v82; // eax
  SIZE_T v83; // r8
  __int64 v84; // rax
  ULONG v85; // r12d
  char *v86; // rdi
  __int64 v87; // rdx
  __int64 v88; // rcx
  int v89; // eax
  __int64 *v90; // rax
  size_t v91; // rax
  int v92; // eax
  PVOID v93; // r14
  PDEVICE_OBJECT v94; // rcx
  __int64 v95; // rdx
  unsigned __int64 v96; // r15
  PMDL v97; // rdi
  __int64 v98; // rdx
  __int64 v99; // rcx
  int v100; // eax
  char *v101; // r12
  unsigned __int64 v102; // r15
  PMDL v103; // rdi
  char *v104; // r12
  ULONG v105; // r14d
  __int64 v106; // rdx
  __int64 v107; // rcx
  int v108; // eax
  __int64 *v109; // rax
  SIZE_T v110; // r8
  __int64 v111; // rcx
  __int64 v112; // r8
  unsigned int v113; // eax
  ULONG Irp; // [rsp+20h] [rbp-E0h]
  PUCHAR v116; // [rsp+30h] [rbp-D0h]
  int v117; // [rsp+38h] [rbp-C8h]
  __int64 v118; // [rsp+40h] [rbp-C0h]
  USHORT pusResult[2]; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID v120; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v121; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v122; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v123; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v124; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v125; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v126; // [rsp+88h] [rbp-78h] BYREF
  void *Source1; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  PVOID VirtualAddress; // [rsp+A0h] [rbp-60h]
  int v130[2]; // [rsp+A8h] [rbp-58h] BYREF
  size_t Size; // [rsp+B0h] [rbp-50h]
  PMDL SourceMdl; // [rsp+B8h] [rbp-48h]
  PMDL TargetMdl; // [rsp+C0h] [rbp-40h]
  char *v134; // [rsp+C8h] [rbp-38h]
  __int64 v135; // [rsp+D0h] [rbp-30h]
  PMDL MemoryDescriptorList; // [rsp+D8h] [rbp-28h]
  void *Source2; // [rsp+E0h] [rbp-20h]
  __int64 v138; // [rsp+E8h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+F0h] [rbp-10h] BYREF
  NTSTATUS *v140; // [rsp+F8h] [rbp-8h]
  PUCHAR v141; // [rsp+100h] [rbp+0h] BYREF
  _DWORD *v142; // [rsp+108h] [rbp+8h]
  __int64 v143; // [rsp+110h] [rbp+10h]
  __int128 v144; // [rsp+118h] [rbp+18h] BYREF
  __int64 v145; // [rsp+128h] [rbp+28h]
  int v146[64]; // [rsp+130h] [rbp+30h] BYREF
  UCHAR pbBuffer[64]; // [rsp+230h] [rbp+130h] BYREF

  LOWORD(v121) = a3;
  v10 = a1;
  v126 = a1;
  v124 = a4;
  v140 = a9;
  memset(pbBuffer, 0, sizeof(pbBuffer));
  v11 = *((unsigned int *)v10 + 327);
  v138 = 0;
  v145 = 0;
  v12 = 0;
  v142 = (_DWORD *)v10[592];
  Pool2 = 0;
  v143 = v10[593];
  v14 = v10[1];
  P = 0;
  hAlgorithm = 0;
  v144 = 0;
  v15 = *(_DWORD *)(v14 + 9928);
  v16 = v15 & 0x1000;
  v135 = 0;
  *(_QWORD *)v130 = 0;
  v120 = 0;
  v134 = 0;
  LOWORD(v123) = 0;
  pusResult[0] = 0;
  v122 = v15;
  if ( a2 )
  {
    v17 = v15 >> 9;
    v18 = (v15 & 0x400) != 0;
    LOBYTE(v17) = (v15 & 0x200) != 0;
    v125 = v17;
  }
  else
  {
    LOBYTE(v125) = (v15 & 0x20) != 0;
    v18 = (v15 & 0x40) != 0;
  }
  memset(v146, 0, sizeof(v146));
  v146[29] = v11;
  v144 = 0;
  v145 = 0;
  v20 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 251, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
  }
  if ( !v16 )
  {
    v23 = FveIceAlgorithmBitSizeToKeySize(a5, a6);
    IceKey = RtlULongToUShort(v23, pusResult);
    if ( IceKey < 0 )
    {
      v12 = pusResult[0];
      goto LABEL_48;
    }
    IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v20, v19);
    v12 = pusResult[0];
    *(_DWORD *)pusResult = pusResult[0];
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( !v142 )
        goto LABEL_47;
      if ( !v140 )
        goto LABEL_47;
      v20 = 4095;
      if ( (unsigned __int16)(v121 + 0x8000) > 0xFFFu || !(_DWORD)v11 || (((_DWORD)v11 - 1) & (unsigned int)v11) != 0 )
        goto LABEL_47;
      v26 = 0x10000;
      if ( (unsigned int)v11 <= 0x10000 )
      {
        v19 = 0x10000 % (unsigned int)v11;
        if ( !(0x10000 % (unsigned int)v11) && pusResult[0] <= 0x40u )
        {
          v36 = v142[3];
          if ( v36 )
          {
            LODWORD(v20) = 0;
            while ( 1 )
            {
              v19 = (unsigned int)(v142[4] + v20 * v142[5]);
              if ( *(_DWORD *)((char *)v142 + v19 + 8) == v124
                && *(_DWORD *)((char *)v142 + v19 + 12) == a5
                && *(_DWORD *)((char *)v142 + v19 + 16) == a6 )
              {
                break;
              }
              v20 = (unsigned int)(v20 + 1);
              if ( (unsigned int)v20 >= v36 )
                goto LABEL_26;
            }
            v25 = v121;
            v29 = a5;
            v27 = v124;
LABEL_65:
            v37 = v10 + 597;
            v38 = v10[597];
            if ( (__int64 *)v38 != v10 + 597 )
            {
              v20 = a6;
              do
              {
                if ( *(_DWORD *)(v38 + 20) == (_DWORD)v11
                  && *(_WORD *)(v38 + 32) == v25
                  && *(_DWORD *)(v38 + 24) == v29
                  && *(_DWORD *)(v38 + 16) == v27 )
                {
                  Pool2 = v38;
                  if ( *(_DWORD *)(v38 + 28) == a6 )
                    break;
                }
                v38 = *(_QWORD *)v38;
                Pool2 = 0;
              }
              while ( (__int64 *)v38 != v37 );
              if ( Pool2 && *(int *)(Pool2 + 36) >= 0 )
              {
                v22 = *(_BYTE *)(Pool2 + 34);
                goto LABEL_27;
              }
            }
            v20 = a8;
            if ( !a8 || !(_BYTE)v125 && !v18 )
            {
              v22 = 1;
              goto LABEL_27;
            }
            if ( a8 < v11 )
            {
LABEL_80:
              v22 = 0;
              IceKey = -1073741811;
              goto LABEL_27;
            }
            if ( a8 < 0x10000 )
            {
              v19 = (unsigned int)a8 % (unsigned int)v11;
              if ( (unsigned int)a8 % (unsigned int)v11 )
                goto LABEL_80;
              v26 = a8;
            }
            if ( !Pool2 )
            {
              Pool2 = ExAllocatePool2(64, 40, 809850438);
              if ( !Pool2 )
              {
                IceKey = -1073741670;
                v22 = 0;
                goto LABEL_27;
              }
              *(_QWORD *)Pool2 = 0;
              *(_QWORD *)(Pool2 + 8) = 0;
              *(_DWORD *)(Pool2 + 34) = 0;
              *(_WORD *)(Pool2 + 38) = 0;
              *(_WORD *)(Pool2 + 32) = v121;
              *(_DWORD *)(Pool2 + 24) = a5;
              *(_DWORD *)(Pool2 + 16) = v124;
              *(_DWORD *)(Pool2 + 28) = a6;
              *(_DWORD *)(Pool2 + 20) = v11;
              v39 = (__int64 *)v10[598];
              if ( (__int64 *)*v39 != v37 )
                __fastfail(3u);
              *(_QWORD *)Pool2 = v37;
              *(_QWORD *)(Pool2 + 8) = v39;
              *v39 = Pool2;
              v10[598] = Pool2;
            }
            Size = v26;
            VirtualAddress = (PVOID)ExAllocatePool2(72, v26, 809850438);
            Source1 = (void *)ExAllocatePool2(72, v26, 809850438);
            v40 = Source1;
            v41 = (void *)ExAllocatePool2(72, v26, 809850438);
            v42 = v10[14];
            Source2 = v41;
            LOBYTE(v43) = *(_BYTE *)(v42 + 76) + 1;
            v44 = (IRP *)IoAllocateIrpEx(-1, v43, 0);
            MemoryDescriptorList = IoAllocateMdl(VirtualAddress, v26, 0, 0, 0);
            SourceMdl = IoAllocateMdl(v40, v26, 0, 0, 0);
            Mdl = IoAllocateMdl(0, v26 + 4096, 0, 0, 0);
            v19 = (unsigned __int64)VirtualAddress;
            TargetMdl = Mdl;
            if ( !VirtualAddress
              || !v40
              || !Source2
              || !v44
              || (v20 = (unsigned __int64)MemoryDescriptorList) == 0
              || (v46 = SourceMdl) == 0
              || !Mdl )
            {
              v22 = 0;
              IceKey = -1073741670;
              if ( !VirtualAddress )
              {
                v93 = v120;
                goto LABEL_217;
              }
              goto LABEL_170;
            }
            MmBuildMdlForNonPagedPool(MemoryDescriptorList);
            MmBuildMdlForNonPagedPool(v46);
            MmMdlPageContentsState(MemoryDescriptorList, 1);
            MmMdlPageContentsState(SourceMdl, 1);
            IceKey = BCryptOpenAlgorithmProvider(&hAlgorithm, L"RNG", 0, 1u);
            if ( IceKey < 0 )
              goto LABEL_169;
            IceKey = BCryptGenRandom(hAlgorithm, pbBuffer, 0x40u, 0);
            if ( IceKey < 0 )
              goto LABEL_169;
            v49 = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v48, v47);
            v50 = (unsigned __int16)v121;
            if ( v49 )
            {
              v51 = FveMapHwWrappedToNonHwWrappedKeyType((unsigned __int16)v121, &v123);
              v50 = (unsigned __int16)v123;
              if ( !v51 )
                LOWORD(v50) = v121;
            }
            IceKey = FveDatumKeyCreate(v50, pbBuffer, pusResult[0], v130);
            if ( IceKey < 0 )
            {
              v135 = *(_QWORD *)v130;
              goto LABEL_169;
            }
            v54 = v130[0];
            v135 = *(_QWORD *)v130;
            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v53, v52) )
              v55 = FveFvekDataFromFvekDatum2(v11, v54);
            else
              v55 = FveFvekDataFromFvekDatum(v11, v54);
            IceKey = v55;
            if ( v55 < 0 )
            {
              v93 = v134;
              v22 = 0;
              goto LABEL_171;
            }
            v120 = v134;
            *(_QWORD *)&v146[16] = v134;
            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v57, v56) )
            {
              if ( (unsigned __int8)FveIsHwWrappedKeyType((unsigned __int16)v121) )
              {
                IceKey = FveIceHwWrapFvek(v10, 1, v135, &v138);
                if ( IceKey < 0 )
                  goto LABEL_169;
              }
            }
            Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v59, v58);
            IceKey = FveCreateIceKey((int)v10, a6, (__int64)&P);
            if ( IceKey < 0 )
              goto LABEL_169;
            v61 = v122 & 2;
            v122 &= 2u;
            if ( (_BYTE)v125 )
            {
              v62 = v11;
              v123 = v11;
              if ( (unsigned int)v11 <= v26 )
              {
                v63 = Size;
                while ( 1 )
                {
                  v60 = 0;
                  v134 = 0;
                  if ( v63 <= a8 )
                    break;
LABEL_163:
                  v62 += v11;
                  v123 = v62;
                  if ( v62 > v26 )
                  {
                    v61 = v122;
                    goto LABEL_165;
                  }
                }
LABEL_115:
                v64 = &v60[a7];
                if ( &v60[a7] >= v60 )
                {
                  v65 = 0;
                  v66 = (char *)VirtualAddress;
                  while ( 1 )
                  {
                    v67 = (unsigned __int64)&v64[v65];
                    if ( &v64[v65] < v64 )
                      break;
                    v68 = &v66[(unsigned int)v65];
                    v65 = (unsigned int)(v11 + v65);
                    memset64(v68, v67, v11 >> 3);
                    if ( (unsigned int)v65 >= v26 )
                    {
                      IceKey = FveFilteredEncrypt(
                                 3,
                                 (int)v146,
                                 (int)v64,
                                 -1,
                                 v26,
                                 (PUCHAR)VirtualAddress,
                                 (PUCHAR)Source2,
                                 0);
                      if ( IceKey < 0 )
                        goto LABEL_169;
                      v69 = 0;
                      while ( 1 )
                      {
                        v125 = v123 + v69;
                        v70 = v123 + v69 <= v26 ? v123 : v26 - v69;
                        v71 = v69;
                        *(_QWORD *)v130 = v69;
                        v72 = &v64[v69];
                        if ( v72 < v64 )
                          goto LABEL_168;
                        if ( v122 )
                        {
                          IceKey = FveFilteredEncrypt(
                                     3,
                                     (int)v146,
                                     (int)v72,
                                     -1,
                                     v70,
                                     (PUCHAR)VirtualAddress + v69,
                                     (PUCHAR)Source1 + v69,
                                     0);
                          if ( IceKey < 0 )
                            goto LABEL_169;
                          v73 = SourceMdl;
                          v74 = (char *)Source1;
                          v71 = *(_QWORD *)v130;
                        }
                        else
                        {
                          v73 = MemoryDescriptorList;
                          v74 = (char *)VirtualAddress;
                        }
                        IoBuildPartialMdl(v73, TargetMdl, &v74[v71], v70);
                        LODWORD(v118) = 0;
                        v117 = (int)v44;
                        v116 = 0;
                        Irp = v70;
                        v75 = (size_t)&v64[v71];
                        IceKey = FveInitPreallocatedIrp(v126, 4, 2, &v64[v71], Irp, TargetMdl);
                        if ( IceKey < 0 )
                          goto LABEL_169;
                        if ( !v122 )
                        {
                          v78 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                                v77,
                                                v76)
                              ? FveIceSetIrpExtensionSteelix(v44, P, v75, v126)
                              : FveIceSetIrpExtension(v44, P, v75 / *((unsigned int *)v126 + 327));
                          IceKey = v78;
                          if ( v78 < 0 )
                            goto LABEL_169;
                        }
                        --v44->CurrentLocation;
                        --v44->Tail.Overlay.CurrentStackLocation;
                        v79 = v126;
                        IoForwardIrpSynchronously((PDEVICE_OBJECT)v126[14], v44);
                        IceKey = v44->IoStatus.Status;
                        if ( IceKey < 0 )
                          goto LABEL_169;
                        v69 = v125;
                        if ( v125 >= v26 )
                        {
                          if ( v122 )
                          {
                            memset(Source1, 0, Size);
                          }
                          else
                          {
                            if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                                 v81,
                                                 v80) )
                              v82 = FveIceSetIrpExtensionSteelix(v44, 0, 0, v79);
                            else
                              v82 = FveIceSetIrpExtension(v44, 0, 0);
                            IceKey = v82;
                            if ( v82 < 0 )
                              goto LABEL_169;
                          }
                          IceKey = FveSendPreallocatedIrpEx(
                                     (int)v79,
                                     3,
                                     2,
                                     (int)v64,
                                     v26,
                                     (__int64)SourceMdl,
                                     0,
                                     v44,
                                     0);
                          if ( IceKey < 0 )
                            goto LABEL_169;
                          v83 = RtlCompareMemory(Source1, Source2, Size);
                          if ( v83 != Size )
                          {
                            v94 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                            {
                              v95 = 252;
LABEL_176:
                              v117 = v83 + (_DWORD)v64;
                              v116 = (PUCHAR)v83;
                              WPP_SF_iDDii(v94->AttachedDevice, v95, v83, v64, v11, v123);
                            }
                            goto LABEL_169;
                          }
                          v84 = 0;
                          while ( 1 )
                          {
                            v125 = v123 + v84;
                            v85 = v123 + (unsigned int)v84 <= v26 ? v123 : v26 - v84;
                            v86 = &v64[v84];
                            *(_QWORD *)v130 = v84;
                            if ( &v64[v84] < v64 )
                              goto LABEL_168;
                            v141 = (PUCHAR)Source1 + v84;
                            IoBuildPartialMdl(SourceMdl, TargetMdl, (char *)Source1 + v84, v85);
                            LODWORD(v118) = 0;
                            v117 = (int)v44;
                            v116 = 0;
                            IceKey = FveInitPreallocatedIrp(v126, 3, 2, v86, v85, TargetMdl);
                            if ( IceKey < 0 )
                              goto LABEL_169;
                            if ( !v122 )
                            {
                              v89 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                                    v88,
                                                    v87)
                                  ? FveIceSetIrpExtensionSteelix(v44, P, &v64[*(_QWORD *)v130], v126)
                                  : FveIceSetIrpExtension(
                                      v44,
                                      P,
                                      (unsigned __int64)&v64[*(_QWORD *)v130] / *((unsigned int *)v126 + 327));
                              IceKey = v89;
                              if ( v89 < 0 )
                                goto LABEL_169;
                            }
                            v90 = v126;
                            --v44->CurrentLocation;
                            --v44->Tail.Overlay.CurrentStackLocation;
                            IoForwardIrpSynchronously((PDEVICE_OBJECT)v90[14], v44);
                            IceKey = v44->IoStatus.Status;
                            if ( IceKey < 0 )
                              goto LABEL_169;
                            if ( v122 )
                            {
                              IceKey = FveFilteredDecrypt(3, (int)v146, (int)v64 + v130[0], -1, v85, v141, v141, 0);
                              if ( IceKey < 0 )
                                goto LABEL_169;
                            }
                            v84 = v125;
                            if ( v125 >= v26 )
                            {
                              v10 = v126;
                              v83 = RtlCompareMemory(Source1, VirtualAddress, Size);
                              if ( v83 == Size )
                              {
                                v60 = &v134[Size];
                                v91 = (size_t)&v134[Size + Size];
                                v134 += Size;
                                if ( v91 <= a8 )
                                  goto LABEL_115;
                                v62 = v123;
                                v63 = Size;
                                goto LABEL_163;
                              }
                              v94 = WPP_GLOBAL_Control;
                              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                              {
                                v95 = 253;
                                goto LABEL_176;
                              }
                              goto LABEL_169;
                            }
                          }
                        }
                      }
                    }
                  }
                }
                goto LABEL_168;
              }
            }
            else if ( !v18 )
            {
              goto LABEL_182;
            }
LABEL_165:
            if ( !(_DWORD)v61 )
            {
              v92 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v60, v61)
                  ? FveIceSetIrpExtensionSteelix(v44, 0, 0, v10)
                  : FveIceSetIrpExtension(v44, 0, 0);
              IceKey = v92;
              if ( v92 < 0 )
                goto LABEL_169;
            }
            v96 = a7;
            IceKey = FveSendPreallocatedIrpEx((int)v10, 3, 2, a7, v26, (__int64)MemoryDescriptorList, (int)v116, v44, 0);
            if ( IceKey < 0 )
              goto LABEL_169;
            IceKey = FveFilteredDecrypt(3, (int)v146, a7, -1, v26, (PUCHAR)VirtualAddress, (PUCHAR)VirtualAddress, 0);
            if ( IceKey < 0 )
              goto LABEL_169;
            v97 = TargetMdl;
            IoBuildPartialMdl(SourceMdl, TargetMdl, Source1, v11);
            LODWORD(v118) = 0;
            v117 = (int)v44;
            v116 = 0;
            IceKey = FveInitPreallocatedIrp(v10, 3, 2, a7, v11, v97);
            if ( IceKey < 0 )
              goto LABEL_169;
            if ( !v122 )
            {
              v100 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v99, v98)
                   ? FveIceSetIrpExtensionSteelix(v44, P, a7, v10)
                   : FveIceSetIrpExtension(v44, P, a7 / *((unsigned int *)v10 + 327));
              IceKey = v100;
              if ( v100 < 0 )
                goto LABEL_169;
            }
            --v44->CurrentLocation;
            --v44->Tail.Overlay.CurrentStackLocation;
            IoForwardIrpSynchronously((PDEVICE_OBJECT)v10[14], v44);
            IceKey = v44->IoStatus.Status;
            if ( IceKey < 0 )
              goto LABEL_169;
            v101 = (char *)Source1;
            if ( v122 )
            {
              IceKey = FveFilteredDecrypt(3, (int)v146, a7, -1, v11, (PUCHAR)Source1, (PUCHAR)Source1, 0);
              if ( IceKey < 0 )
                goto LABEL_169;
            }
            if ( (unsigned int)v11 < v26 )
            {
              v102 = v11 + a7;
              if ( v11 + a7 < a7 )
              {
LABEL_168:
                IceKey = -1073741675;
LABEL_169:
                v22 = 0;
LABEL_170:
                v93 = v120;
LABEL_171:
                ExFreePoolWithTag(VirtualAddress, 0x30455646u);
                v10 = v126;
LABEL_217:
                if ( Source1 )
                  ExFreePoolWithTag(Source1, 0x30455646u);
                if ( Source2 )
                  ExFreePoolWithTag(Source2, 0x30455646u);
                if ( v44 )
                  IoFreeIrp(v44);
                if ( MemoryDescriptorList )
                  IoFreeMdl(MemoryDescriptorList);
                if ( SourceMdl )
                  IoFreeMdl(SourceMdl);
                if ( TargetMdl )
                  IoFreeMdl(TargetMdl);
                if ( v135 )
                  FveDatumFree(v135);
                if ( v93 )
                  DeleteKey(v93);
                goto LABEL_27;
              }
              v103 = TargetMdl;
              v104 = &v101[v11];
              v105 = v26 - v11;
              IoBuildPartialMdl(SourceMdl, TargetMdl, v104, v105);
              LODWORD(v118) = 0;
              v117 = (int)v44;
              v116 = 0;
              IceKey = FveInitPreallocatedIrp(v126, 3, 2, v102, v105, v103);
              if ( IceKey < 0 )
                goto LABEL_169;
              if ( !v122 )
              {
                v108 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                       v107,
                                       v106)
                     ? FveIceSetIrpExtensionSteelix(v44, P, v102, v126)
                     : FveIceSetIrpExtension(v44, P, v102 / *((unsigned int *)v126 + 327));
                IceKey = v108;
                if ( v108 < 0 )
                  goto LABEL_169;
              }
              v109 = v126;
              --v44->CurrentLocation;
              --v44->Tail.Overlay.CurrentStackLocation;
              IoForwardIrpSynchronously((PDEVICE_OBJECT)v109[14], v44);
              IceKey = v44->IoStatus.Status;
              if ( IceKey < 0 )
                goto LABEL_169;
              if ( v122 )
              {
                IceKey = FveFilteredDecrypt(3, (int)v146, v102, -1, v105, (PUCHAR)v104, (PUCHAR)v104, 0);
                if ( IceKey < 0 )
                  goto LABEL_169;
              }
              v96 = a7;
            }
            v110 = RtlCompareMemory(Source1, VirtualAddress, Size);
            if ( v110 != Size )
            {
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
              {
                v116 = (PUCHAR)(v110 + v96);
                WPP_SF_iDii(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v110, v96, v11, v110);
              }
              goto LABEL_169;
            }
LABEL_182:
            v22 = 1;
            goto LABEL_170;
          }
LABEL_26:
          IceKey = -1073741275;
          v22 = 0;
LABEL_27:
          v12 = pusResult[0];
          goto LABEL_28;
        }
      }
    }
    else
    {
      if ( !v143 )
        goto LABEL_47;
      if ( !v140 )
        goto LABEL_47;
      v25 = v121;
      v20 = 4095;
      if ( (unsigned __int16)(v121 + 0x8000) > 0xFFFu || !(_DWORD)v11 || (((_DWORD)v11 - 1) & (unsigned int)v11) != 0 )
        goto LABEL_47;
      v26 = 0x10000;
      if ( (unsigned int)v11 <= 0x10000 )
      {
        v19 = 0x10000 % (unsigned int)v11;
        if ( !(0x10000 % (unsigned int)v11) && pusResult[0] <= 0x40u )
        {
          v19 = *(unsigned int *)(v143 + 12);
          v20 = 0;
          if ( (_DWORD)v19 )
          {
            v27 = v124;
            while ( 1 )
            {
              v28 = 32LL * (unsigned int)v20;
              if ( *(_DWORD *)(v28 + v143 + 32) == v124 )
              {
                v29 = a5;
                if ( *(_DWORD *)(v28 + v143 + 36) == a5 && *(_DWORD *)(v28 + v143 + 40) == a6 )
                  goto LABEL_65;
              }
              v20 = (unsigned int)(v20 + 1);
              if ( (unsigned int)v20 >= (unsigned int)v19 )
                goto LABEL_26;
            }
          }
          goto LABEL_26;
        }
      }
    }
    v12 = pusResult[0];
LABEL_47:
    IceKey = -1073741811;
LABEL_48:
    v22 = 0;
    goto LABEL_28;
  }
  IceKey = 0;
  v22 = 1;
LABEL_28:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v20, v19) && v138 )
  {
    FveDatumFree(v138);
    v138 = 0;
  }
  if ( P )
  {
    ExFreePoolWithTag(P, 0x656E6F4Eu);
    P = 0;
  }
  if ( hAlgorithm )
  {
    BCryptCloseAlgorithmProvider(hAlgorithm, 0);
    hAlgorithm = 0;
  }
  v32 = v22;
  if ( IceKey < 0 )
    v32 = 0;
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 34) = v32;
    *(_DWORD *)(Pool2 + 36) = IceKey;
  }
  if ( v140 )
    *v140 = IceKey;
  if ( !v32 )
  {
    v111 = *v10;
    LOBYTE(v31) = 1;
    *(_QWORD *)&v144 = FVE_ICE_HW_CRYPTO_VERIFY_FAILED;
    HIDWORD(v144) = IceKey;
    v145 = 0;
    FveLogEventEx(v111, &v144, 0, v31);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v33 = a6;
      v34 = a5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v35 = v121;
        LODWORD(v118) = v11;
        v117 = (unsigned __int16)v121;
        LODWORD(v116) = v12;
        WPP_SF_LLLLDLd(WPP_GLOBAL_Control->AttachedDevice, v12, v112, v124, a5, a6);
        goto LABEL_241;
      }
LABEL_240:
      v35 = v121;
      goto LABEL_241;
    }
LABEL_239:
    v34 = a5;
    v33 = a6;
    goto LABEL_240;
  }
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0 )
    goto LABEL_239;
  v33 = a6;
  v34 = a5;
  if ( BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
    goto LABEL_240;
  v35 = v121;
  LODWORD(v118) = v11;
  v117 = (unsigned __int16)v121;
  LODWORD(v116) = v12;
  WPP_SF_LLLLDL(WPP_GLOBAL_Control->AttachedDevice, v12, v30, v124, a5, a6);
LABEL_241:
  if ( (unsigned int)dword_140046040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140046040, 0x400000000000LL) )
  {
    v125 = v32;
    *(_QWORD *)&v146[8] = &v125;
    *(_QWORD *)&v146[12] = &v122;
    *(_QWORD *)&v146[10] = 4;
    v122 = IceKey;
    *(_QWORD *)&v146[14] = 4;
    if ( v142 )
      v113 = v142[6];
    else
      v113 = *(_DWORD *)(v143 + 16);
    v123 = v113;
    *(_QWORD *)&v146[18] = 4;
    *(_QWORD *)&v146[16] = &v123;
    *(_QWORD *)&v146[22] = 4;
    *(_QWORD *)&v146[20] = &v124;
    *(_QWORD *)&v146[24] = pusResult;
    *(_QWORD *)&v146[28] = &v121;
    LODWORD(Source1) = v12;
    *(_QWORD *)&v146[32] = &Source1;
    LODWORD(v126) = v35;
    *(_QWORD *)&v146[36] = &v126;
    *(_QWORD *)&v146[40] = &v120;
    *(_QWORD *)&v146[44] = &v141;
    *(_DWORD *)pusResult = v34;
    *(_QWORD *)&v146[26] = 4;
    v121 = v33;
    *(_QWORD *)&v146[30] = 4;
    *(_QWORD *)&v146[34] = 4;
    *(_QWORD *)&v146[38] = 4;
    LODWORD(v120) = v11;
    *(_QWORD *)&v146[42] = 4;
    v141 = (PUCHAR)0x1000000;
    *(_QWORD *)&v146[46] = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140046040, byte_14003C741, 0, 0, 12, v146, v116, v117, v118);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 257, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, v32, IceKey);
  }
  return v32;
}

```

## disassembly

```asm
0x1400af494  mov     [rsp-8+arg_8], rbx
0x1400af499  push    rbp
0x1400af49a  push    rsi
0x1400af49b  push    rdi
0x1400af49c  push    r12
0x1400af49e  push    r13
0x1400af4a0  push    r14
0x1400af4a2  push    r15
0x1400af4a4  lea     rbp, [rsp-180h]
0x1400af4ac  sub     rsp, 280h
0x1400af4b3  mov     rax, cs:__security_cookie
0x1400af4ba  xor     rax, rsp
0x1400af4bd  mov     [rbp+1B0h+var_40], rax
0x1400af4c4  mov     rax, [rbp+1B0h+arg_40]
0x1400af4cb  mov     dil, dl
0x1400af4ce  xor     edx, edx; Val
0x1400af4d0  mov     word ptr [rsp+2B0h+var_240], r8w
0x1400af4d6  mov     r12, rcx
0x1400af4d9  mov     [rbp+1B0h+var_228], rcx
0x1400af4dd  lea     rcx, [rbp+1B0h+pbBuffer]; void *
0x1400af4e4  mov     [rsp+2B0h+var_234], r9d
0x1400af4e9  mov     [rbp+1B0h+var_1B8], rax
0x1400af4ed  lea     r8d, [rdx+40h]; Size
0x1400af4f1  call    memset
0x1400af4f6  mov     esi, [r12+51Ch]
0x1400af4fe  xor     edx, edx; Val
0x1400af500  xor     eax, eax
0x1400af502  mov     [rbp+1B0h+var_1C8], rdx
0x1400af506  mov     [rbp+1B0h+var_188], rax
0x1400af50a  xorps   xmm0, xmm0
0x1400af50d  mov     rax, [r12+1280h]
0x1400af515  mov     r14d, edx
0x1400af518  mov     [rbp+1B0h+var_1A8], rax
0x1400af51c  mov     r13d, edx
0x1400af51f  mov     rax, [r12+1288h]
0x1400af527  mov     [rbp+1B0h+var_1A0], rax
0x1400af52b  mov     rax, [r12+8]
0x1400af530  mov     [rbp+1B0h+P], rdx
0x1400af534  mov     [rbp+1B0h+hAlgorithm], rdx
0x1400af538  movups  [rbp+1B0h+var_198], xmm0
0x1400af53c  mov     ecx, [rax+26C8h]
0x1400af542  mov     ebx, ecx
0x1400af544  and     ebx, 1000h
0x1400af54a  mov     [rbp+1B0h+var_1E0], rdx
0x1400af54e  mov     qword ptr [rbp+1B0h+var_208], rdx
0x1400af552  mov     [rsp+2B0h+var_248], rdx
0x1400af557  mov     [rbp+1B0h+var_1E8], rdx
0x1400af55b  mov     word ptr [rsp+2B0h+var_238], dx
0x1400af560  mov     [rsp+2B0h+pusResult], dx
0x1400af565  mov     [rsp+2B0h+var_23C], ecx
0x1400af569  test    dil, dil
0x1400af56c  jz      short loc_1400AF587
0x1400af56e  mov     r15d, ecx
0x1400af571  mov     edi, ecx
0x1400af573  shr     r15d, 0Ah
0x1400af577  shr     edi, 9
0x1400af57a  and     r15b, 1
0x1400af57e  and     dil, 1
0x1400af582  mov     [rbp+1B0h+var_230], edi
0x1400af585  jmp     short loc_1400AF59C
0x1400af587  mov     al, cl
0x1400af589  mov     r15b, cl
0x1400af58c  shr     al, 5
0x1400af58f  and     al, 1
0x1400af591  shr     r15b, 6
0x1400af595  mov     byte ptr [rbp+1B0h+var_230], al
0x1400af598  and     r15b, 1
0x1400af59c  mov     r8d, 100h; Size
0x1400af5a2  lea     rcx, [rbp+1B0h+var_180]; void *
0x1400af5a6  call    memset
0x1400af5ab  xorps   xmm0, xmm0
0x1400af5ae  mov     [rbp+1B0h+var_10C], esi
0x1400af5b4  xor     eax, eax
0x1400af5b6  movups  [rbp+1B0h+var_198], xmm0
0x1400af5ba  mov     [rbp+1B0h+var_188], rax
0x1400af5be  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af5c5  lea     rax, WPP_GLOBAL_Control
0x1400af5cc  cmp     rcx, rax
0x1400af5cf  jz      short loc_1400AF5F3
0x1400af5d1  mov     eax, [rcx+2Ch]
0x1400af5d4  test    al, 4
0x1400af5d6  jz      short loc_1400AF5F3
0x1400af5d8  cmp     byte ptr [rcx+29h], 5
0x1400af5dc  jb      short loc_1400AF5F3
0x1400af5de  mov     rcx, [rcx+18h]
0x1400af5e2  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400af5e9  mov     edx, 0FBh
0x1400af5ee  call    WPP_SF_
0x1400af5f3  test    ebx, ebx
0x1400af5f5  jz      short loc_1400AF601
0x1400af5f7  xor     edi, edi
0x1400af5f9  mov     r15b, 1
0x1400af5fc  jmp     loc_1400AF705
0x1400af601  mov     ebx, [rbp+1B0h+arg_28]
0x1400af607  mov     edx, ebx
0x1400af609  mov     ecx, [rbp+1B0h+arg_20]
0x1400af60f  mov     [rsp+2B0h+var_250], r13b
0x1400af614  call    FveIceAlgorithmBitSizeToKeySize
0x1400af619  mov     ecx, eax; ulOperand
0x1400af61b  lea     rdx, [rsp+2B0h+pusResult]; pusResult
0x1400af620  call    RtlULongToUShort
0x1400af625  mov     edi, eax
0x1400af627  test    eax, eax
0x1400af629  js      loc_1400B06A3
0x1400af62f  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400af634  movzx   r14d, [rsp+2B0h+pusResult]
0x1400af63a  mov     dword ptr [rsp+2B0h+pusResult], r14d
0x1400af63f  test    eax, eax
0x1400af641  jnz     loc_1400AF810
0x1400af647  mov     r11, [rbp+1B0h+var_1A0]
0x1400af64b  test    r11, r11
0x1400af64e  jz      loc_1400AF803
0x1400af654  cmp     [rbp+1B0h+var_1B8], r13
0x1400af658  jz      loc_1400AF803
0x1400af65e  movzx   r9d, word ptr [rsp+2B0h+var_240]
0x1400af664  mov     ecx, 8000h
0x1400af669  movzx   eax, r9w
0x1400af66d  sub     ax, cx
0x1400af670  mov     ecx, 0FFFh
0x1400af675  cmp     ax, cx
0x1400af678  ja      loc_1400AF803
0x1400af67e  test    esi, esi
0x1400af680  jz      loc_1400AF803
0x1400af686  lea     eax, [rsi-1]
0x1400af689  test    esi, eax
0x1400af68b  jnz     loc_1400AF803
0x1400af691  mov     r14d, 10000h
0x1400af697  cmp     esi, r14d
0x1400af69a  ja      loc_1400AF7FE
0x1400af6a0  xor     edx, edx
0x1400af6a2  mov     eax, r14d
0x1400af6a5  div     esi
0x1400af6a7  test    edx, edx
0x1400af6a9  jnz     loc_1400AF7FE
0x1400af6af  lea     eax, [rdx+40h]
0x1400af6b2  cmp     [rsp+2B0h+pusResult], ax
0x1400af6b7  ja      loc_1400AF7FE
0x1400af6bd  mov     edx, [r11+0Ch]
0x1400af6c1  xor     ecx, ecx
0x1400af6c3  test    edx, edx
0x1400af6c5  jz      short loc_1400AF6F8
0x1400af6c7  mov     r10d, [rsp+2B0h+var_234]
0x1400af6cc  mov     eax, ecx
0x1400af6ce  shl     rax, 5
0x1400af6d2  cmp     [rax+r11+20h], r10d
0x1400af6d7  jnz     short loc_1400AF6F2
0x1400af6d9  mov     r8d, [rbp+1B0h+arg_20]
0x1400af6e0  cmp     [rax+r11+24h], r8d
0x1400af6e5  jnz     short loc_1400AF6F2
0x1400af6e7  cmp     [rax+r11+28h], ebx
0x1400af6ec  jz      loc_1400AF8BA
0x1400af6f2  inc     ecx
0x1400af6f4  cmp     ecx, edx
0x1400af6f6  jb      short loc_1400AF6CC
0x1400af6f8  mov     edi, 0C0000225h
0x1400af6fd  mov     r15b, r13b
0x1400af700  mov     r14d, dword ptr [rsp+2B0h+pusResult]
0x1400af705  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400af70a  test    eax, eax
0x1400af70c  jz      short loc_1400AF724
0x1400af70e  mov     rcx, [rbp+1B0h+var_1C8]
0x1400af712  test    rcx, rcx
0x1400af715  jz      short loc_1400AF724
0x1400af717  call    FveDatumFree
0x1400af71c  mov     [rbp+1B0h+var_1C8], 0
0x1400af724  mov     rcx, [rbp+1B0h+P]; P
0x1400af728  test    rcx, rcx
0x1400af72b  jz      short loc_1400AF746
0x1400af72d  mov     edx, 656E6F4Eh; Tag
0x1400af732  call    cs:__imp_ExFreePoolWithTag
0x1400af739  nop     dword ptr [rax+rax+00h]
0x1400af73e  mov     [rbp+1B0h+P], 0
0x1400af746  mov     rcx, [rbp+1B0h+hAlgorithm]; hAlgorithm
0x1400af74a  test    rcx, rcx
0x1400af74d  jz      short loc_1400AF765
0x1400af74f  xor     edx, edx; dwFlags
0x1400af751  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400af758  nop     dword ptr [rax+rax+00h]
0x1400af75d  mov     [rbp+1B0h+hAlgorithm], 0
0x1400af765  xor     eax, eax
0x1400af767  movzx   ebx, r15b
0x1400af76b  test    edi, edi
0x1400af76d  cmovs   ebx, eax
0x1400af770  test    r13, r13
0x1400af773  jz      short loc_1400AF77D
0x1400af775  mov     [r13+22h], bl
0x1400af779  mov     [r13+24h], edi
0x1400af77d  mov     rax, [rbp+1B0h+var_1B8]
0x1400af781  test    rax, rax
0x1400af784  jz      short loc_1400AF788
0x1400af786  mov     [rax], edi
0x1400af788  test    bl, bl
0x1400af78a  jz      loc_1400B06AE
0x1400af790  mov     rcx, cs:WPP_GLOBAL_Control
0x1400af797  lea     rax, WPP_GLOBAL_Control
0x1400af79e  cmp     rcx, rax
0x1400af7a1  jz      loc_1400B073A
0x1400af7a7  mov     eax, [rcx+2Ch]
0x1400af7aa  test    al, 4
0x1400af7ac  jz      loc_1400B073A
0x1400af7b2  cmp     byte ptr [rcx+29h], 4
0x1400af7b6  mov     r15d, [rbp+1B0h+arg_28]
0x1400af7bd  mov     r12d, [rbp+1B0h+arg_20]
0x1400af7c4  jb      loc_1400B0748
0x1400af7ca  movzx   r13d, word ptr [rsp+2B0h+var_240]
0x1400af7d0  mov     r9d, [rsp+2B0h+var_234]
0x1400af7d5  mov     rcx, [rcx+18h]
0x1400af7d9  mov     dword ptr [rsp+2B0h+var_270], esi
0x1400af7dd  mov     dword ptr [rsp+2B0h+var_278], r13d
0x1400af7e2  movzx   edx, r14w
0x1400af7e6  mov     dword ptr [rsp+2B0h+var_280], edx
0x1400af7ea  mov     dword ptr [rsp+2B0h+var_288], r15d
0x1400af7ef  mov     dword ptr [rsp+2B0h+Irp], r12d
0x1400af7f4  call    WPP_SF_LLLLDL
0x1400af7f9  jmp     loc_1400B074E
0x1400af7fe  mov     r14d, dword ptr [rsp+2B0h+pusResult]
0x1400af803  mov     edi, 0C000000Dh
0x1400af808  mov     r15b, r13b
0x1400af80b  jmp     loc_1400AF705
0x1400af810  mov     r11, [rbp+1B0h+var_1A8]
0x1400af814  test    r11, r11
0x1400af817  jz      short loc_1400AF803
0x1400af819  cmp     [rbp+1B0h+var_1B8], r13
0x1400af81d  jz      short loc_1400AF803
0x1400af81f  movzx   eax, word ptr [rsp+2B0h+var_240]
0x1400af824  mov     ecx, 8000h
0x1400af829  sub     ax, cx
0x1400af82c  mov     ecx, 0FFFh
0x1400af831  cmp     ax, cx
0x1400af834  ja      short loc_1400AF803
0x1400af836  test    esi, esi
0x1400af838  jz      short loc_1400AF803
0x1400af83a  lea     eax, [rsi-1]
0x1400af83d  test    esi, eax
0x1400af83f  jnz     short loc_1400AF803
0x1400af841  mov     r14d, 10000h
0x1400af847  cmp     esi, r14d
0x1400af84a  ja      short loc_1400AF7FE
0x1400af84c  xor     edx, edx
0x1400af84e  mov     eax, r14d
0x1400af851  div     esi
0x1400af853  test    edx, edx
0x1400af855  jnz     short loc_1400AF7FE
0x1400af857  lea     eax, [rdx+40h]
0x1400af85a  cmp     [rsp+2B0h+pusResult], ax
0x1400af85f  ja      short loc_1400AF7FE
0x1400af861  mov     r8d, [r11+0Ch]
0x1400af865  test    r8d, r8d
0x1400af868  jz      loc_1400AF6F8
0x1400af86e  mov     r9d, [r11+10h]
0x1400af872  xor     ecx, ecx
0x1400af874  mov     r10d, [r11+14h]
0x1400af878  mov     eax, [rsp+2B0h+var_234]
0x1400af87c  mov     edx, r10d
0x1400af87f  imul    edx, ecx
0x1400af882  add     edx, r9d
0x1400af885  cmp     [rdx+r11+8], eax
0x1400af88a  jnz     short loc_1400AF8A0
0x1400af88c  mov     eax, [rbp+1B0h+arg_20]
0x1400af892  cmp     [rdx+r11+0Ch], eax
0x1400af897  jnz     short loc_1400AF8A0
0x1400af899  cmp     [rdx+r11+10h], ebx
0x1400af89e  jz      short loc_1400AF8AC
0x1400af8a0  inc     ecx
0x1400af8a2  cmp     ecx, r8d
0x1400af8a5  jb      short loc_1400AF878
0x1400af8a7  jmp     loc_1400AF6F8
0x1400af8ac  movzx   r9d, word ptr [rsp+2B0h+var_240]
0x1400af8b2  mov     r8d, eax
0x1400af8b5  mov     r10d, [rsp+2B0h+var_234]
0x1400af8ba  lea     rbx, [r12+12A8h]
0x1400af8c2  mov     rax, [rbx]
0x1400af8c5  cmp     rax, rbx
0x1400af8c8  jz      short loc_1400AF910
0x1400af8ca  mov     ecx, [rbp+1B0h+arg_28]
0x1400af8d0  cmp     [rax+14h], esi
0x1400af8d3  jnz     short loc_1400AF8F0
0x1400af8d5  cmp     [rax+20h], r9w
0x1400af8da  jnz     short loc_1400AF8F0
0x1400af8dc  cmp     [rax+18h], r8d
0x1400af8e0  jnz     short loc_1400AF8F0
0x1400af8e2  cmp     [rax+10h], r10d
0x1400af8e6  jnz     short loc_1400AF8F0
0x1400af8e8  mov     r13, rax
0x1400af8eb  cmp     [rax+1Ch], ecx
0x1400af8ee  jz      short loc_1400AF8FB
0x1400af8f0  mov     rax, [rax]
0x1400af8f3  xor     r13d, r13d
0x1400af8f6  cmp     rax, rbx
0x1400af8f9  jnz     short loc_1400AF8D0
0x1400af8fb  test    r13, r13
0x1400af8fe  jz      short loc_1400AF910
0x1400af900  cmp     dword ptr [r13+24h], 0
0x1400af905  jl      short loc_1400AF910
0x1400af907  mov     r15b, [r13+22h]
0x1400af90b  jmp     loc_1400AF700
0x1400af910  mov     rcx, [rbp+1B0h+arg_38]
0x1400af917  test    rcx, rcx
0x1400af91a  jz      loc_1400B069B
0x1400af920  cmp     byte ptr [rbp+1B0h+var_230], 0
  ... truncated ...
```
