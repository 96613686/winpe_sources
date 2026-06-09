# FveVerifyIceCrypto

- ea: `0x1400ae214`
- end: `0x1400af6a8`
- name: `FveVerifyIceCrypto`
- size: `5268`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, int, int, int, __int64, __int64)`
- caller_count: `3`
- callee_count: `30`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14009c540`
- `0x1400a82cc`
- `0x1400acd3c`

## callees

- `0x140001008`
- `0x1400010ac`
- `0x140005e50`
- `0x140007ce8`
- `0x140008288`
- `0x140008c10`
- `0x140008c60`
- `0x140008ca8`
- `0x140008dc0`
- `0x14000aef4`
- `0x14000c050`
- `0x14000c094`
- `0x14000c678`
- `0x14000c70c`
- `0x14000cc18`
- `0x14000cd88`
- `0x1400143d0`
- `0x140017024`
- `0x140017040`
- `0x1400218c0`
- `0x140021d00`
- `0x140061b54`
- `0x14009df90`
- `0x1400a7704`
- `0x1400adf28`
- `0x1400ae214`
- `0x1400b5c18`
- `0x1400c7558`
- `0x1400def70`
- `0x1400df568`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ae8aa`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ae8b9`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ae8aa`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x1400ae8b9`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ae8d0`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ae8e2`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ae8d0`
- `ntoskrnl!MmMdlPageContentsState` at `0x1400ae8e2`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400ae7db`
- `ntoskrnl!IoAllocateIrpEx` at `0x1400ae7db`
- `ntoskrnl!IoFreeIrp` at `0x1400af3a0`
- `ntoskrnl!IoFreeIrp` at `0x1400af3a0`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400aec5e`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400aee2c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400af122`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400af25d`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400aec5e`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400aee2c`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400af122`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x1400af25d`
- `ntoskrnl!RtlCompareMemory` at `0x1400aed08`
- `ntoskrnl!RtlCompareMemory` at `0x1400aeea4`
- `ntoskrnl!RtlCompareMemory` at `0x1400af2c4`
- `ntoskrnl!RtlCompareMemory` at `0x1400aed08`
- `ntoskrnl!RtlCompareMemory` at `0x1400aeea4`
- `ntoskrnl!RtlCompareMemory` at `0x1400af2c4`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400aeba2`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400aed6d`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400af079`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400af1ac`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400aeba2`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400aed6d`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400af079`
- `ntoskrnl!IoBuildPartialMdl` at `0x1400af1ac`
- `ntoskrnl!IoFreeMdl` at `0x1400af3b8`
- `ntoskrnl!IoFreeMdl` at `0x1400af3d0`
- `ntoskrnl!IoFreeMdl` at `0x1400af3e8`
- `ntoskrnl!IoFreeMdl` at `0x1400af3b8`
- `ntoskrnl!IoFreeMdl` at `0x1400af3d0`
- `ntoskrnl!IoFreeMdl` at `0x1400af3e8`
- `ntoskrnl!IoAllocateMdl` at `0x1400ae800`
- `ntoskrnl!IoAllocateMdl` at `0x1400ae825`
- `ntoskrnl!IoAllocateMdl` at `0x1400ae84d`
- `ntoskrnl!IoAllocateMdl` at `0x1400ae800`
- `ntoskrnl!IoAllocateMdl` at `0x1400ae825`
- `ntoskrnl!IoAllocateMdl` at `0x1400ae84d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae4b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aef35`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af36f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af38c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400ae4b2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400aef35`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af36f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400af38c`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae6ed`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae77e`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae799`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae7ba`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae6ed`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae77e`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae799`
- `ntoskrnl!ExAllocatePool2` at `0x1400ae7ba`
- `ksecdd!BCryptGenRandom` at `0x1400ae927`
- `ksecdd!BCryptGenRandom` at `0x1400ae927`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400ae4d1`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x1400ae4d1`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400ae8ff`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x1400ae8ff`

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
  unsigned __int64 v19; // rcx
  NTSTATUS IceKey; // edi
  char v21; // r15
  ULONG v22; // eax
  int IsEnabledDeviceUsageNoInline; // eax
  __int16 v24; // r9
  unsigned int v25; // r14d
  unsigned int v26; // edx
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
  __int64 v37; // rdx
  __int64 *v38; // rbx
  __int64 v39; // rax
  __int64 *v40; // rax
  void *v41; // rdi
  void *v42; // rax
  __int64 v43; // rcx
  __int64 v44; // rdx
  IRP *v45; // rbx
  struct _MDL *Mdl; // rax
  struct _MDL *v47; // rdi
  __int64 v48; // rcx
  int v49; // eax
  __int64 v50; // rcx
  char v51; // al
  __int64 v52; // rcx
  int v53; // edi
  int v54; // eax
  __int64 v55; // rcx
  __int64 v56; // rcx
  char *v57; // rcx
  int v58; // edx
  unsigned int v59; // eax
  size_t v60; // rdx
  char *v61; // r15
  __int64 v62; // rdx
  char *v63; // r8
  unsigned __int64 v64; // rax
  char *v65; // rdi
  unsigned int v66; // eax
  ULONG v67; // r12d
  __int64 v68; // rdi
  char *v69; // rdx
  struct _MDL *v70; // rcx
  char *v71; // rax
  size_t v72; // r12
  __int64 v73; // rcx
  int v74; // eax
  __int64 *v75; // r12
  __int64 v76; // rcx
  int v77; // eax
  SIZE_T v78; // r8
  __int64 v79; // rax
  ULONG v80; // r12d
  char *v81; // rdi
  __int64 v82; // rcx
  int v83; // eax
  __int64 *v84; // rax
  size_t v85; // rax
  int v86; // eax
  PVOID v87; // r14
  PDEVICE_OBJECT v88; // rcx
  __int64 v89; // rdx
  unsigned __int64 v90; // r15
  PMDL v91; // rdi
  __int64 v92; // rcx
  int v93; // eax
  char *v94; // r12
  unsigned __int64 v95; // r15
  PMDL v96; // rdi
  char *v97; // r12
  ULONG v98; // r14d
  __int64 v99; // rcx
  int v100; // eax
  __int64 *v101; // rax
  SIZE_T v102; // r8
  __int64 v103; // rcx
  __int64 v104; // r8
  __int64 v105; // rcx
  unsigned int v106; // eax
  ULONG Irp; // [rsp+20h] [rbp-E0h]
  PUCHAR v109; // [rsp+30h] [rbp-D0h]
  PIRP v110; // [rsp+38h] [rbp-C8h]
  USHORT pusResult[2]; // [rsp+64h] [rbp-9Ch] BYREF
  PVOID v112; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v113; // [rsp+70h] [rbp-90h] BYREF
  int v114; // [rsp+74h] [rbp-8Ch] BYREF
  unsigned int v115; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v116; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v117; // [rsp+80h] [rbp-80h] BYREF
  __int64 *v118; // [rsp+88h] [rbp-78h] BYREF
  void *Source1; // [rsp+90h] [rbp-70h] BYREF
  PVOID P; // [rsp+98h] [rbp-68h] BYREF
  PVOID VirtualAddress; // [rsp+A0h] [rbp-60h]
  int v122[2]; // [rsp+A8h] [rbp-58h] BYREF
  size_t Size; // [rsp+B0h] [rbp-50h]
  PMDL SourceMdl; // [rsp+B8h] [rbp-48h]
  PMDL TargetMdl; // [rsp+C0h] [rbp-40h]
  char *v126; // [rsp+C8h] [rbp-38h]
  __int64 v127; // [rsp+D0h] [rbp-30h]
  PMDL MemoryDescriptorList; // [rsp+D8h] [rbp-28h]
  void *Source2; // [rsp+E0h] [rbp-20h]
  __int64 v130; // [rsp+E8h] [rbp-18h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+F0h] [rbp-10h] BYREF
  NTSTATUS *v132; // [rsp+F8h] [rbp-8h]
  PUCHAR v133; // [rsp+100h] [rbp+0h] BYREF
  _DWORD *v134; // [rsp+108h] [rbp+8h]
  __int64 v135; // [rsp+110h] [rbp+10h]
  __int128 v136; // [rsp+118h] [rbp+18h] BYREF
  __int64 v137; // [rsp+128h] [rbp+28h]
  int v138[64]; // [rsp+130h] [rbp+30h] BYREF
  UCHAR pbBuffer[64]; // [rsp+230h] [rbp+130h] BYREF

  LOWORD(v113) = a3;
  v10 = a1;
  v118 = a1;
  v116 = a4;
  v132 = a9;
  memset(pbBuffer, 0, sizeof(pbBuffer));
  v11 = *((unsigned int *)v10 + 327);
  v130 = 0;
  v137 = 0;
  v12 = 0;
  v134 = (_DWORD *)v10[590];
  Pool2 = 0;
  v135 = v10[591];
  v14 = v10[1];
  P = 0;
  hAlgorithm = 0;
  v136 = 0;
  v15 = *(_DWORD *)(v14 + 9680);
  v16 = v15 & 0x1000;
  v127 = 0;
  *(_QWORD *)v122 = 0;
  v112 = 0;
  v126 = 0;
  LOWORD(v115) = 0;
  pusResult[0] = 0;
  v114 = v15;
  if ( a2 )
  {
    v17 = v15 >> 9;
    v18 = (v15 & 0x400) != 0;
    LOBYTE(v17) = (v15 & 0x200) != 0;
    v117 = v17;
  }
  else
  {
    LOBYTE(v117) = (v15 & 0x20) != 0;
    v18 = (v15 & 0x40) != 0;
  }
  memset(v138, 0, sizeof(v138));
  v138[29] = v11;
  v136 = 0;
  v137 = 0;
  v19 = (unsigned __int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 251, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
  }
  if ( !v16 )
  {
    v22 = FveIceAlgorithmBitSizeToKeySize(a5, a6);
    IceKey = RtlULongToUShort(v22, pusResult);
    if ( IceKey < 0 )
    {
      v12 = pusResult[0];
      goto LABEL_48;
    }
    IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v19);
    v12 = pusResult[0];
    *(_DWORD *)pusResult = pusResult[0];
    if ( IsEnabledDeviceUsageNoInline )
    {
      if ( !v134 )
        goto LABEL_47;
      if ( !v132 )
        goto LABEL_47;
      v19 = 4095;
      if ( (unsigned __int16)(v113 + 0x8000) > 0xFFFu || !(_DWORD)v11 || (((_DWORD)v11 - 1) & (unsigned int)v11) != 0 )
        goto LABEL_47;
      v25 = 0x10000;
      if ( (unsigned int)v11 <= 0x10000 && !(0x10000 % (unsigned int)v11) && pusResult[0] <= 0x40u )
      {
        v36 = v134[3];
        if ( v36 )
        {
          LODWORD(v19) = 0;
          while ( 1 )
          {
            v37 = (unsigned int)(v134[4] + v19 * v134[5]);
            if ( *(_DWORD *)((char *)v134 + v37 + 8) == v116
              && *(_DWORD *)((char *)v134 + v37 + 12) == a5
              && *(_DWORD *)((char *)v134 + v37 + 16) == a6 )
            {
              break;
            }
            v19 = (unsigned int)(v19 + 1);
            if ( (unsigned int)v19 >= v36 )
              goto LABEL_26;
          }
          v24 = v113;
          v29 = a5;
          v27 = v116;
LABEL_65:
          v38 = v10 + 595;
          v39 = v10[595];
          if ( (__int64 *)v39 != v10 + 595 )
          {
            v19 = a6;
            do
            {
              if ( *(_DWORD *)(v39 + 20) == (_DWORD)v11
                && *(_WORD *)(v39 + 32) == v24
                && *(_DWORD *)(v39 + 24) == v29
                && *(_DWORD *)(v39 + 16) == v27 )
              {
                Pool2 = v39;
                if ( *(_DWORD *)(v39 + 28) == a6 )
                  break;
              }
              v39 = *(_QWORD *)v39;
              Pool2 = 0;
            }
            while ( (__int64 *)v39 != v38 );
            if ( Pool2 && *(int *)(Pool2 + 36) >= 0 )
            {
              v21 = *(_BYTE *)(Pool2 + 34);
              goto LABEL_27;
            }
          }
          v19 = a8;
          if ( !a8 || !(_BYTE)v117 && !v18 )
          {
            v21 = 1;
            goto LABEL_27;
          }
          if ( a8 < v11 )
          {
LABEL_80:
            v21 = 0;
            IceKey = -1073741811;
            goto LABEL_27;
          }
          if ( a8 < 0x10000 )
          {
            if ( (unsigned int)a8 % (unsigned int)v11 )
              goto LABEL_80;
            v25 = a8;
          }
          if ( !Pool2 )
          {
            Pool2 = ExAllocatePool2(64, 40, 809850438);
            if ( !Pool2 )
            {
              IceKey = -1073741670;
              v21 = 0;
              goto LABEL_27;
            }
            *(_QWORD *)Pool2 = 0;
            *(_QWORD *)(Pool2 + 8) = 0;
            *(_DWORD *)(Pool2 + 34) = 0;
            *(_WORD *)(Pool2 + 38) = 0;
            *(_WORD *)(Pool2 + 32) = v113;
            *(_DWORD *)(Pool2 + 24) = a5;
            *(_DWORD *)(Pool2 + 16) = v116;
            *(_DWORD *)(Pool2 + 28) = a6;
            *(_DWORD *)(Pool2 + 20) = v11;
            v40 = (__int64 *)v10[596];
            if ( (__int64 *)*v40 != v38 )
              __fastfail(3u);
            *(_QWORD *)Pool2 = v38;
            *(_QWORD *)(Pool2 + 8) = v40;
            *v40 = Pool2;
            v10[596] = Pool2;
          }
          Size = v25;
          VirtualAddress = (PVOID)ExAllocatePool2(72, v25, 809850438);
          Source1 = (void *)ExAllocatePool2(72, v25, 809850438);
          v41 = Source1;
          v42 = (void *)ExAllocatePool2(72, v25, 809850438);
          v43 = v10[14];
          Source2 = v42;
          LOBYTE(v44) = *(_BYTE *)(v43 + 76) + 1;
          v45 = (IRP *)IoAllocateIrpEx(-1, v44, 0);
          MemoryDescriptorList = IoAllocateMdl(VirtualAddress, v25, 0, 0, 0);
          SourceMdl = IoAllocateMdl(v41, v25, 0, 0, 0);
          Mdl = IoAllocateMdl(0, v25 + 4096, 0, 0, 0);
          TargetMdl = Mdl;
          if ( !VirtualAddress
            || !v41
            || !Source2
            || !v45
            || (v19 = (unsigned __int64)MemoryDescriptorList) == 0
            || (v47 = SourceMdl) == 0
            || !Mdl )
          {
            v21 = 0;
            IceKey = -1073741670;
            if ( !VirtualAddress )
            {
              v87 = v112;
              goto LABEL_217;
            }
            goto LABEL_170;
          }
          MmBuildMdlForNonPagedPool(MemoryDescriptorList);
          MmBuildMdlForNonPagedPool(v47);
          MmMdlPageContentsState(MemoryDescriptorList, 1);
          MmMdlPageContentsState(SourceMdl, 1);
          IceKey = BCryptOpenAlgorithmProvider(&hAlgorithm, L"RNG", 0, 1u);
          if ( IceKey < 0 )
            goto LABEL_169;
          IceKey = BCryptGenRandom(hAlgorithm, pbBuffer, 0x40u, 0);
          if ( IceKey < 0 )
            goto LABEL_169;
          v49 = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v48);
          v50 = (unsigned __int16)v113;
          if ( v49 )
          {
            v51 = FveMapHwWrappedToNonHwWrappedKeyType((unsigned __int16)v113, &v115);
            v50 = (unsigned __int16)v115;
            if ( !v51 )
              LOWORD(v50) = v113;
          }
          IceKey = FveDatumKeyCreate(v50, pbBuffer, pusResult[0], v122);
          if ( IceKey < 0 )
          {
            v127 = *(_QWORD *)v122;
            goto LABEL_169;
          }
          v53 = v122[0];
          v127 = *(_QWORD *)v122;
          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v52) )
            v54 = FveFvekDataFromFvekDatum2(v11, v53);
          else
            v54 = FveFvekDataFromFvekDatum(v11, v53);
          IceKey = v54;
          if ( v54 < 0 )
          {
            v87 = v126;
            v21 = 0;
            goto LABEL_171;
          }
          v112 = v126;
          *(_QWORD *)&v138[16] = v126;
          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v55) )
          {
            if ( (unsigned __int8)FveIsHwWrappedKeyType((unsigned __int16)v113) )
            {
              IceKey = FveIceHwWrapFvek(v10, 1, v127, &v130);
              if ( IceKey < 0 )
                goto LABEL_169;
            }
          }
          Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v56);
          IceKey = FveCreateIceKey((int)v10, a6, (__int64)&P);
          if ( IceKey < 0 )
            goto LABEL_169;
          v58 = v114 & 2;
          v114 = v58;
          if ( (_BYTE)v117 )
          {
            v59 = v11;
            v115 = v11;
            if ( (unsigned int)v11 <= v25 )
            {
              v60 = Size;
              while ( 1 )
              {
                v57 = 0;
                v126 = 0;
                if ( v60 <= a8 )
                  break;
LABEL_163:
                v59 += v11;
                v115 = v59;
                if ( v59 > v25 )
                {
                  v58 = v114;
                  goto LABEL_165;
                }
              }
LABEL_115:
              v61 = &v57[a7];
              if ( &v57[a7] >= v57 )
              {
                v62 = 0;
                v63 = (char *)VirtualAddress;
                while ( 1 )
                {
                  v64 = (unsigned __int64)&v61[v62];
                  if ( &v61[v62] < v61 )
                    break;
                  v65 = &v63[(unsigned int)v62];
                  v62 = (unsigned int)(v11 + v62);
                  memset64(v65, v64, v11 >> 3);
                  if ( (unsigned int)v62 >= v25 )
                  {
                    IceKey = FveFilteredEncrypt(
                               3,
                               (int)v138,
                               (int)v61,
                               -1,
                               v25,
                               (PUCHAR)VirtualAddress,
                               (PUCHAR)Source2,
                               0);
                    if ( IceKey < 0 )
                      goto LABEL_169;
                    v66 = 0;
                    while ( 1 )
                    {
                      v117 = v115 + v66;
                      v67 = v115 + v66 <= v25 ? v115 : v25 - v66;
                      v68 = v66;
                      *(_QWORD *)v122 = v66;
                      v69 = &v61[v66];
                      if ( v69 < v61 )
                        goto LABEL_168;
                      if ( v114 )
                      {
                        IceKey = FveFilteredEncrypt(
                                   3,
                                   (int)v138,
                                   (int)v69,
                                   -1,
                                   v67,
                                   (PUCHAR)VirtualAddress + v66,
                                   (PUCHAR)Source1 + v66,
                                   0);
                        if ( IceKey < 0 )
                          goto LABEL_169;
                        v70 = SourceMdl;
                        v71 = (char *)Source1;
                        v68 = *(_QWORD *)v122;
                      }
                      else
                      {
                        v70 = MemoryDescriptorList;
                        v71 = (char *)VirtualAddress;
                      }
                      IoBuildPartialMdl(v70, TargetMdl, &v71[v68], v67);
                      HIDWORD(v110) = HIDWORD(v45);
                      HIDWORD(v109) = 0;
                      Irp = v67;
                      v72 = (size_t)&v61[v68];
                      IceKey = FveInitPreallocatedIrp(v118, 4, 2, &v61[v68], Irp, TargetMdl);
                      if ( IceKey < 0 )
                        goto LABEL_169;
                      if ( !v114 )
                      {
                        v74 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v73)
                            ? FveIceSetIrpExtensionSteelix(v45, P, v72, v118)
                            : FveIceSetIrpExtension(v45, P, v72 / *((unsigned int *)v118 + 327));
                        IceKey = v74;
                        if ( v74 < 0 )
                          goto LABEL_169;
                      }
                      --v45->CurrentLocation;
                      --v45->Tail.Overlay.CurrentStackLocation;
                      v75 = v118;
                      IoForwardIrpSynchronously((PDEVICE_OBJECT)v118[14], v45);
                      IceKey = v45->IoStatus.Status;
                      if ( IceKey < 0 )
                        goto LABEL_169;
                      v66 = v117;
                      if ( v117 >= v25 )
                      {
                        if ( v114 )
                        {
                          memset(Source1, 0, Size);
                        }
                        else
                        {
                          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v76) )
                            v77 = FveIceSetIrpExtensionSteelix(v45, 0, 0, v75);
                          else
                            v77 = FveIceSetIrpExtension(v45, 0, 0);
                          IceKey = v77;
                          if ( v77 < 0 )
                            goto LABEL_169;
                        }
                        IceKey = FveSendPreallocatedIrpEx((int)v75, 3, 2, (int)v61, v25, (__int64)SourceMdl, 0, v45, 0);
                        if ( IceKey < 0 )
                          goto LABEL_169;
                        v78 = RtlCompareMemory(Source1, Source2, Size);
                        if ( v78 != Size )
                        {
                          v88 = WPP_GLOBAL_Control;
                          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                          {
                            v89 = 252;
LABEL_176:
                            WPP_SF_iDDii(v88->AttachedDevice, v89, v78, v61, v11, v115, v78, &v61[v78]);
                          }
                          goto LABEL_169;
                        }
                        v79 = 0;
                        while ( 1 )
                        {
                          v117 = v115 + v79;
                          v80 = v115 + (unsigned int)v79 <= v25 ? v115 : v25 - v79;
                          v81 = &v61[v79];
                          *(_QWORD *)v122 = v79;
                          if ( &v61[v79] < v61 )
                            goto LABEL_168;
                          v133 = (PUCHAR)Source1 + v79;
                          IoBuildPartialMdl(SourceMdl, TargetMdl, (char *)Source1 + v79, v80);
                          HIDWORD(v110) = HIDWORD(v45);
                          v109 = 0;
                          IceKey = FveInitPreallocatedIrp(v118, 3, 2, v81, v80, TargetMdl);
                          if ( IceKey < 0 )
                            goto LABEL_169;
                          if ( !v114 )
                          {
                            v83 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v82)
                                ? FveIceSetIrpExtensionSteelix(v45, P, &v61[*(_QWORD *)v122], v118)
                                : FveIceSetIrpExtension(
                                    v45,
                                    P,
                                    (unsigned __int64)&v61[*(_QWORD *)v122] / *((unsigned int *)v118 + 327));
                            IceKey = v83;
                            if ( v83 < 0 )
                              goto LABEL_169;
                          }
                          v84 = v118;
                          --v45->CurrentLocation;
                          --v45->Tail.Overlay.CurrentStackLocation;
                          IoForwardIrpSynchronously((PDEVICE_OBJECT)v84[14], v45);
                          IceKey = v45->IoStatus.Status;
                          if ( IceKey < 0 )
                            goto LABEL_169;
                          if ( v114 )
                          {
                            IceKey = FveFilteredDecrypt(3, (int)v138, (int)v61 + v122[0], -1, v80, v133, v133, 0);
                            if ( IceKey < 0 )
                              goto LABEL_169;
                          }
                          v79 = v117;
                          if ( v117 >= v25 )
                          {
                            v10 = v118;
                            v78 = RtlCompareMemory(Source1, VirtualAddress, Size);
                            if ( v78 == Size )
                            {
                              v57 = &v126[Size];
                              v85 = (size_t)&v126[Size + Size];
                              v126 += Size;
                              if ( v85 <= a8 )
                                goto LABEL_115;
                              v59 = v115;
                              v60 = Size;
                              goto LABEL_163;
                            }
                            v88 = WPP_GLOBAL_Control;
                            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
                              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                            {
                              v89 = 253;
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
          if ( !v58 )
          {
            v86 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v57)
                ? FveIceSetIrpExtensionSteelix(v45, 0, 0, v10)
                : FveIceSetIrpExtension(v45, 0, 0);
            IceKey = v86;
            if ( v86 < 0 )
              goto LABEL_169;
          }
          v90 = a7;
          IceKey = FveSendPreallocatedIrpEx((int)v10, 3, 2, a7, v25, (__int64)MemoryDescriptorList, (int)v109, v45, 0);
          if ( IceKey < 0 )
            goto LABEL_169;
          IceKey = FveFilteredDecrypt(3, (int)v138, a7, -1, v25, (PUCHAR)VirtualAddress, (PUCHAR)VirtualAddress, 0);
          if ( IceKey < 0 )
            goto LABEL_169;
          v91 = TargetMdl;
          IoBuildPartialMdl(SourceMdl, TargetMdl, Source1, v11);
          HIDWORD(v110) = HIDWORD(v45);
          HIDWORD(v109) = 0;
          IceKey = FveInitPreallocatedIrp(v10, 3, 2, a7, v11, v91);
          if ( IceKey < 0 )
            goto LABEL_169;
          if ( !v114 )
          {
            v93 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v92)
                ? FveIceSetIrpExtensionSteelix(v45, P, a7, v10)
                : FveIceSetIrpExtension(v45, P, a7 / *((unsigned int *)v10 + 327));
            IceKey = v93;
            if ( v93 < 0 )
              goto LABEL_169;
          }
          --v45->CurrentLocation;
          --v45->Tail.Overlay.CurrentStackLocation;
          IoForwardIrpSynchronously((PDEVICE_OBJECT)v10[14], v45);
          IceKey = v45->IoStatus.Status;
          if ( IceKey < 0 )
            goto LABEL_169;
          v94 = (char *)Source1;
          if ( v114 )
          {
            IceKey = FveFilteredDecrypt(3, (int)v138, a7, -1, v11, (PUCHAR)Source1, (PUCHAR)Source1, 0);
            if ( IceKey < 0 )
              goto LABEL_169;
          }
          if ( (unsigned int)v11 < v25 )
          {
            v95 = v11 + a7;
            if ( v11 + a7 < a7 )
            {
LABEL_168:
              IceKey = -1073741675;
LABEL_169:
              v21 = 0;
LABEL_170:
              v87 = v112;
LABEL_171:
              ExFreePoolWithTag(VirtualAddress, 0x30455646u);
              v10 = v118;
LABEL_217:
              if ( Source1 )
                ExFreePoolWithTag(Source1, 0x30455646u);
              if ( Source2 )
                ExFreePoolWithTag(Source2, 0x30455646u);
              if ( v45 )
                IoFreeIrp(v45);
              if ( MemoryDescriptorList )
                IoFreeMdl(MemoryDescriptorList);
              if ( SourceMdl )
                IoFreeMdl(SourceMdl);
              if ( TargetMdl )
                IoFreeMdl(TargetMdl);
              if ( v127 )
                FveDatumFree(v127);
              if ( v87 )
                DeleteKey(v87);
              goto LABEL_27;
            }
            v96 = TargetMdl;
            v97 = &v94[v11];
            v98 = v25 - v11;
            IoBuildPartialMdl(SourceMdl, TargetMdl, v97, v98);
            HIDWORD(v110) = HIDWORD(v45);
            HIDWORD(v109) = 0;
            IceKey = FveInitPreallocatedIrp(v118, 3, 2, v95, v98, v96);
            if ( IceKey < 0 )
              goto LABEL_169;
            if ( !v114 )
            {
              v100 = (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v99)
                   ? FveIceSetIrpExtensionSteelix(v45, P, v95, v118)
                   : FveIceSetIrpExtension(v45, P, v95 / *((unsigned int *)v118 + 327));
              IceKey = v100;
              if ( v100 < 0 )
                goto LABEL_169;
            }
            v101 = v118;
            --v45->CurrentLocation;
            --v45->Tail.Overlay.CurrentStackLocation;
            IoForwardIrpSynchronously((PDEVICE_OBJECT)v101[14], v45);
            IceKey = v45->IoStatus.Status;
            if ( IceKey < 0 )
              goto LABEL_169;
            if ( v114 )
            {
              IceKey = FveFilteredDecrypt(3, (int)v138, v95, -1, v98, (PUCHAR)v97, (PUCHAR)v97, 0);
              if ( IceKey < 0 )
                goto LABEL_169;
            }
            v90 = a7;
          }
          v102 = RtlCompareMemory(Source1, VirtualAddress, Size);
          if ( v102 != Size )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_iDii(WPP_GLOBAL_Control->AttachedDevice, WPP_GLOBAL_Control, v102, v90, v11, v102, v102 + v90);
            }
            goto LABEL_169;
          }
LABEL_182:
          v21 = 1;
          goto LABEL_170;
        }
LABEL_26:
        IceKey = -1073741275;
        v21 = 0;
LABEL_27:
        v12 = pusResult[0];
        goto LABEL_28;
      }
    }
    else
    {
      if ( !v135 )
        goto LABEL_47;
      if ( !v132 )
        goto LABEL_47;
      v24 = v113;
      v19 = 4095;
      if ( (unsigned __int16)(v113 + 0x8000) > 0xFFFu || !(_DWORD)v11 || (((_DWORD)v11 - 1) & (unsigned int)v11) != 0 )
        goto LABEL_47;
      v25 = 0x10000;
      if ( (unsigned int)v11 <= 0x10000 && !(0x10000 % (unsigned int)v11) && pusResult[0] <= 0x40u )
      {
        v26 = *(_DWORD *)(v135 + 12);
        v19 = 0;
        if ( v26 )
        {
          v27 = v116;
          while ( 1 )
          {
            v28 = 32LL * (unsigned int)v19;
            if ( *(_DWORD *)(v28 + v135 + 32) == v116 )
            {
              v29 = a5;
              if ( *(_DWORD *)(v28 + v135 + 36) == a5 && *(_DWORD *)(v28 + v135 + 40) == a6 )
                goto LABEL_65;
            }
            v19 = (unsigned int)(v19 + 1);
            if ( (unsigned int)v19 >= v26 )
              goto LABEL_26;
          }
        }
        goto LABEL_26;
      }
    }
    v12 = pusResult[0];
LABEL_47:
    IceKey = -1073741811;
LABEL_48:
    v21 = 0;
    goto LABEL_28;
  }
  IceKey = 0;
  v21 = 1;
LABEL_28:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v19) && v130 )
  {
    FveDatumFree(v130);
    v130 = 0;
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
  v32 = v21;
  if ( IceKey < 0 )
    v32 = 0;
  if ( Pool2 )
  {
    *(_BYTE *)(Pool2 + 34) = v32;
    *(_DWORD *)(Pool2 + 36) = IceKey;
  }
  if ( v132 )
    *v132 = IceKey;
  if ( !v32 )
  {
    v103 = *v10;
    LOBYTE(v31) = 1;
    *(_QWORD *)&v136 = FVE_ICE_HW_CRYPTO_VERIFY_FAILED;
    HIDWORD(v136) = IceKey;
    v137 = 0;
    FveLogEventEx(v103, &v136, 0, v31);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
    {
      v33 = a6;
      v34 = a5;
      if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v35 = v113;
        LODWORD(v110) = (unsigned __int16)v113;
        LODWORD(v109) = v12;
        WPP_SF_LLLLDLd(WPP_GLOBAL_Control->AttachedDevice, v12, v104, v116, a5, a6, v109, v110, v11, IceKey);
        goto LABEL_241;
      }
LABEL_240:
      v35 = v113;
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
  v35 = v113;
  LODWORD(v110) = (unsigned __int16)v113;
  LODWORD(v109) = v12;
  WPP_SF_LLLLDL(WPP_GLOBAL_Control->AttachedDevice, v12, v30, v116, a5, a6, v109, v110, v11);
LABEL_241:
  if ( (unsigned int)dword_140045040 > 4 && (unsigned __int8)tlgKeywordOn(&dword_140045040, 0x400000000000LL) )
  {
    v117 = v32;
    *(_QWORD *)&v138[8] = &v117;
    *(_QWORD *)&v138[12] = &v114;
    *(_QWORD *)&v138[10] = 4;
    v114 = IceKey;
    *(_QWORD *)&v138[14] = 4;
    if ( v134 )
      v106 = v134[6];
    else
      v106 = *(_DWORD *)(v135 + 16);
    v115 = v106;
    *(_QWORD *)&v138[18] = 4;
    *(_QWORD *)&v138[16] = &v115;
    *(_QWORD *)&v138[20] = &v116;
    *(_QWORD *)&v138[24] = pusResult;
    *(_QWORD *)&v138[28] = &v113;
    LODWORD(Source1) = v12;
    *(_QWORD *)&v138[32] = &Source1;
    LODWORD(v118) = v35;
    *(_QWORD *)&v138[36] = &v118;
    *(_QWORD *)&v138[40] = &v112;
    *(_QWORD *)&v138[44] = &v133;
    *(_QWORD *)&v138[22] = 4;
    *(_DWORD *)pusResult = v34;
    *(_QWORD *)&v138[26] = 4;
    v113 = v33;
    *(_QWORD *)&v138[30] = 4;
    *(_QWORD *)&v138[34] = 4;
    *(_QWORD *)&v138[38] = 4;
    LODWORD(v112) = v11;
    *(_QWORD *)&v138[42] = 4;
    v133 = (PUCHAR)0x1000000;
    *(_QWORD *)&v138[46] = 8;
    tlgWriteTransfer_EtwWriteTransfer(v105, byte_14003B6C1, 0, 0, 12, v138);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 257, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, v32, IceKey);
  }
  return v32;
}

```

## disassembly

```asm
0x1400ae214  mov     [rsp-8+arg_8], rbx
0x1400ae219  push    rbp
0x1400ae21a  push    rsi
0x1400ae21b  push    rdi
0x1400ae21c  push    r12
0x1400ae21e  push    r13
0x1400ae220  push    r14
0x1400ae222  push    r15
0x1400ae224  lea     rbp, [rsp-180h]
0x1400ae22c  sub     rsp, 280h
0x1400ae233  mov     rax, cs:__security_cookie
0x1400ae23a  xor     rax, rsp
0x1400ae23d  mov     [rbp+1B0h+var_40], rax
0x1400ae244  mov     rax, [rbp+1B0h+arg_40]
0x1400ae24b  mov     dil, dl
0x1400ae24e  xor     edx, edx; Val
0x1400ae250  mov     word ptr [rsp+2B0h+var_240], r8w
0x1400ae256  mov     r12, rcx
0x1400ae259  mov     [rbp+1B0h+var_228], rcx
0x1400ae25d  lea     rcx, [rbp+1B0h+pbBuffer]; void *
0x1400ae264  mov     [rsp+2B0h+var_234], r9d
0x1400ae269  mov     [rbp+1B0h+var_1B8], rax
0x1400ae26d  lea     r8d, [rdx+40h]; Size
0x1400ae271  call    memset
0x1400ae276  mov     esi, [r12+51Ch]
0x1400ae27e  xor     edx, edx; Val
0x1400ae280  xor     eax, eax
0x1400ae282  mov     [rbp+1B0h+var_1C8], rdx
0x1400ae286  mov     [rbp+1B0h+var_188], rax
0x1400ae28a  xorps   xmm0, xmm0
0x1400ae28d  mov     rax, [r12+1270h]
0x1400ae295  mov     r14d, edx
0x1400ae298  mov     [rbp+1B0h+var_1A8], rax
0x1400ae29c  mov     r13d, edx
0x1400ae29f  mov     rax, [r12+1278h]
0x1400ae2a7  mov     [rbp+1B0h+var_1A0], rax
0x1400ae2ab  mov     rax, [r12+8]
0x1400ae2b0  mov     [rbp+1B0h+P], rdx
0x1400ae2b4  mov     [rbp+1B0h+hAlgorithm], rdx
0x1400ae2b8  movups  [rbp+1B0h+var_198], xmm0
0x1400ae2bc  mov     ecx, [rax+25D0h]
0x1400ae2c2  mov     ebx, ecx
0x1400ae2c4  and     ebx, 1000h
0x1400ae2ca  mov     [rbp+1B0h+var_1E0], rdx
0x1400ae2ce  mov     qword ptr [rbp+1B0h+var_208], rdx
0x1400ae2d2  mov     [rsp+2B0h+var_248], rdx
0x1400ae2d7  mov     [rbp+1B0h+var_1E8], rdx
0x1400ae2db  mov     word ptr [rsp+2B0h+var_238], dx
0x1400ae2e0  mov     [rsp+2B0h+pusResult], dx
0x1400ae2e5  mov     [rsp+2B0h+var_23C], ecx
0x1400ae2e9  test    dil, dil
0x1400ae2ec  jz      short loc_1400AE307
0x1400ae2ee  mov     r15d, ecx
0x1400ae2f1  mov     edi, ecx
0x1400ae2f3  shr     r15d, 0Ah
0x1400ae2f7  shr     edi, 9
0x1400ae2fa  and     r15b, 1
0x1400ae2fe  and     dil, 1
0x1400ae302  mov     [rbp+1B0h+var_230], edi
0x1400ae305  jmp     short loc_1400AE31C
0x1400ae307  mov     al, cl
0x1400ae309  mov     r15b, cl
0x1400ae30c  shr     al, 5
0x1400ae30f  and     al, 1
0x1400ae311  shr     r15b, 6
0x1400ae315  mov     byte ptr [rbp+1B0h+var_230], al
0x1400ae318  and     r15b, 1
0x1400ae31c  mov     r8d, 100h; Size
0x1400ae322  lea     rcx, [rbp+1B0h+var_180]; void *
0x1400ae326  call    memset
0x1400ae32b  xorps   xmm0, xmm0
0x1400ae32e  mov     [rbp+1B0h+var_10C], esi
0x1400ae334  xor     eax, eax
0x1400ae336  movups  [rbp+1B0h+var_198], xmm0
0x1400ae33a  mov     [rbp+1B0h+var_188], rax
0x1400ae33e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae345  lea     rax, WPP_GLOBAL_Control
0x1400ae34c  cmp     rcx, rax
0x1400ae34f  jz      short loc_1400AE373
0x1400ae351  mov     eax, [rcx+2Ch]
0x1400ae354  test    al, 4
0x1400ae356  jz      short loc_1400AE373
0x1400ae358  cmp     byte ptr [rcx+29h], 5
0x1400ae35c  jb      short loc_1400AE373
0x1400ae35e  mov     rcx, [rcx+18h]
0x1400ae362  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400ae369  mov     edx, 0FBh
0x1400ae36e  call    WPP_SF_
0x1400ae373  test    ebx, ebx
0x1400ae375  jz      short loc_1400AE381
0x1400ae377  xor     edi, edi
0x1400ae379  mov     r15b, 1
0x1400ae37c  jmp     loc_1400AE485
0x1400ae381  mov     ebx, [rbp+1B0h+arg_28]
0x1400ae387  mov     edx, ebx
0x1400ae389  mov     ecx, [rbp+1B0h+arg_20]
0x1400ae38f  mov     [rsp+2B0h+var_250], r13b
0x1400ae394  call    FveIceAlgorithmBitSizeToKeySize
0x1400ae399  mov     ecx, eax; ulOperand
0x1400ae39b  lea     rdx, [rsp+2B0h+pusResult]; pusResult
0x1400ae3a0  call    RtlULongToUShort
0x1400ae3a5  mov     edi, eax
0x1400ae3a7  test    eax, eax
0x1400ae3a9  js      loc_1400AF423
0x1400ae3af  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ae3b4  movzx   r14d, [rsp+2B0h+pusResult]
0x1400ae3ba  mov     dword ptr [rsp+2B0h+pusResult], r14d
0x1400ae3bf  test    eax, eax
0x1400ae3c1  jnz     loc_1400AE590
0x1400ae3c7  mov     r11, [rbp+1B0h+var_1A0]
0x1400ae3cb  test    r11, r11
0x1400ae3ce  jz      loc_1400AE583
0x1400ae3d4  cmp     [rbp+1B0h+var_1B8], r13
0x1400ae3d8  jz      loc_1400AE583
0x1400ae3de  movzx   r9d, word ptr [rsp+2B0h+var_240]
0x1400ae3e4  mov     ecx, 8000h
0x1400ae3e9  movzx   eax, r9w
0x1400ae3ed  sub     ax, cx
0x1400ae3f0  mov     ecx, 0FFFh
0x1400ae3f5  cmp     ax, cx
0x1400ae3f8  ja      loc_1400AE583
0x1400ae3fe  test    esi, esi
0x1400ae400  jz      loc_1400AE583
0x1400ae406  lea     eax, [rsi-1]
0x1400ae409  test    esi, eax
0x1400ae40b  jnz     loc_1400AE583
0x1400ae411  mov     r14d, 10000h
0x1400ae417  cmp     esi, r14d
0x1400ae41a  ja      loc_1400AE57E
0x1400ae420  xor     edx, edx
0x1400ae422  mov     eax, r14d
0x1400ae425  div     esi
0x1400ae427  test    edx, edx
0x1400ae429  jnz     loc_1400AE57E
0x1400ae42f  lea     eax, [rdx+40h]
0x1400ae432  cmp     [rsp+2B0h+pusResult], ax
0x1400ae437  ja      loc_1400AE57E
0x1400ae43d  mov     edx, [r11+0Ch]
0x1400ae441  xor     ecx, ecx
0x1400ae443  test    edx, edx
0x1400ae445  jz      short loc_1400AE478
0x1400ae447  mov     r10d, [rsp+2B0h+var_234]
0x1400ae44c  mov     eax, ecx
0x1400ae44e  shl     rax, 5
0x1400ae452  cmp     [rax+r11+20h], r10d
0x1400ae457  jnz     short loc_1400AE472
0x1400ae459  mov     r8d, [rbp+1B0h+arg_20]
0x1400ae460  cmp     [rax+r11+24h], r8d
0x1400ae465  jnz     short loc_1400AE472
0x1400ae467  cmp     [rax+r11+28h], ebx
0x1400ae46c  jz      loc_1400AE63A
0x1400ae472  inc     ecx
0x1400ae474  cmp     ecx, edx
0x1400ae476  jb      short loc_1400AE44C
0x1400ae478  mov     edi, 0C0000225h
0x1400ae47d  mov     r15b, r13b
0x1400ae480  mov     r14d, dword ptr [rsp+2B0h+pusResult]
0x1400ae485  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400ae48a  test    eax, eax
0x1400ae48c  jz      short loc_1400AE4A4
0x1400ae48e  mov     rcx, [rbp+1B0h+var_1C8]
0x1400ae492  test    rcx, rcx
0x1400ae495  jz      short loc_1400AE4A4
0x1400ae497  call    FveDatumFree
0x1400ae49c  mov     [rbp+1B0h+var_1C8], 0
0x1400ae4a4  mov     rcx, [rbp+1B0h+P]; P
0x1400ae4a8  test    rcx, rcx
0x1400ae4ab  jz      short loc_1400AE4C6
0x1400ae4ad  mov     edx, 656E6F4Eh; Tag
0x1400ae4b2  call    cs:__imp_ExFreePoolWithTag
0x1400ae4b9  nop     dword ptr [rax+rax+00h]
0x1400ae4be  mov     [rbp+1B0h+P], 0
0x1400ae4c6  mov     rcx, [rbp+1B0h+hAlgorithm]; hAlgorithm
0x1400ae4ca  test    rcx, rcx
0x1400ae4cd  jz      short loc_1400AE4E5
0x1400ae4cf  xor     edx, edx; dwFlags
0x1400ae4d1  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1400ae4d8  nop     dword ptr [rax+rax+00h]
0x1400ae4dd  mov     [rbp+1B0h+hAlgorithm], 0
0x1400ae4e5  xor     eax, eax
0x1400ae4e7  movzx   ebx, r15b
0x1400ae4eb  test    edi, edi
0x1400ae4ed  cmovs   ebx, eax
0x1400ae4f0  test    r13, r13
0x1400ae4f3  jz      short loc_1400AE4FD
0x1400ae4f5  mov     [r13+22h], bl
0x1400ae4f9  mov     [r13+24h], edi
0x1400ae4fd  mov     rax, [rbp+1B0h+var_1B8]
0x1400ae501  test    rax, rax
0x1400ae504  jz      short loc_1400AE508
0x1400ae506  mov     [rax], edi
0x1400ae508  test    bl, bl
0x1400ae50a  jz      loc_1400AF42E
0x1400ae510  mov     rcx, cs:WPP_GLOBAL_Control
0x1400ae517  lea     rax, WPP_GLOBAL_Control
0x1400ae51e  cmp     rcx, rax
0x1400ae521  jz      loc_1400AF4BA
0x1400ae527  mov     eax, [rcx+2Ch]
0x1400ae52a  test    al, 4
0x1400ae52c  jz      loc_1400AF4BA
0x1400ae532  cmp     byte ptr [rcx+29h], 4
0x1400ae536  mov     r15d, [rbp+1B0h+arg_28]
0x1400ae53d  mov     r12d, [rbp+1B0h+arg_20]
0x1400ae544  jb      loc_1400AF4C8
0x1400ae54a  movzx   r13d, word ptr [rsp+2B0h+var_240]
0x1400ae550  mov     r9d, [rsp+2B0h+var_234]
0x1400ae555  mov     rcx, [rcx+18h]
0x1400ae559  mov     [rsp+2B0h+var_270], esi
0x1400ae55d  mov     dword ptr [rsp+2B0h+var_278], r13d
0x1400ae562  movzx   edx, r14w
0x1400ae566  mov     dword ptr [rsp+2B0h+var_280], edx
0x1400ae56a  mov     dword ptr [rsp+2B0h+var_288], r15d
0x1400ae56f  mov     dword ptr [rsp+2B0h+Irp], r12d
0x1400ae574  call    WPP_SF_LLLLDL
0x1400ae579  jmp     loc_1400AF4CE
0x1400ae57e  mov     r14d, dword ptr [rsp+2B0h+pusResult]
0x1400ae583  mov     edi, 0C000000Dh
0x1400ae588  mov     r15b, r13b
0x1400ae58b  jmp     loc_1400AE485
0x1400ae590  mov     r11, [rbp+1B0h+var_1A8]
0x1400ae594  test    r11, r11
0x1400ae597  jz      short loc_1400AE583
0x1400ae599  cmp     [rbp+1B0h+var_1B8], r13
0x1400ae59d  jz      short loc_1400AE583
0x1400ae59f  movzx   eax, word ptr [rsp+2B0h+var_240]
0x1400ae5a4  mov     ecx, 8000h
0x1400ae5a9  sub     ax, cx
0x1400ae5ac  mov     ecx, 0FFFh
0x1400ae5b1  cmp     ax, cx
0x1400ae5b4  ja      short loc_1400AE583
0x1400ae5b6  test    esi, esi
0x1400ae5b8  jz      short loc_1400AE583
0x1400ae5ba  lea     eax, [rsi-1]
0x1400ae5bd  test    esi, eax
0x1400ae5bf  jnz     short loc_1400AE583
0x1400ae5c1  mov     r14d, 10000h
0x1400ae5c7  cmp     esi, r14d
0x1400ae5ca  ja      short loc_1400AE57E
0x1400ae5cc  xor     edx, edx
0x1400ae5ce  mov     eax, r14d
0x1400ae5d1  div     esi
0x1400ae5d3  test    edx, edx
0x1400ae5d5  jnz     short loc_1400AE57E
0x1400ae5d7  lea     eax, [rdx+40h]
0x1400ae5da  cmp     [rsp+2B0h+pusResult], ax
0x1400ae5df  ja      short loc_1400AE57E
0x1400ae5e1  mov     r8d, [r11+0Ch]
0x1400ae5e5  test    r8d, r8d
0x1400ae5e8  jz      loc_1400AE478
0x1400ae5ee  mov     r9d, [r11+10h]
0x1400ae5f2  xor     ecx, ecx
0x1400ae5f4  mov     r10d, [r11+14h]
0x1400ae5f8  mov     eax, [rsp+2B0h+var_234]
0x1400ae5fc  mov     edx, r10d
0x1400ae5ff  imul    edx, ecx
0x1400ae602  add     edx, r9d
0x1400ae605  cmp     [rdx+r11+8], eax
0x1400ae60a  jnz     short loc_1400AE620
0x1400ae60c  mov     eax, [rbp+1B0h+arg_20]
0x1400ae612  cmp     [rdx+r11+0Ch], eax
0x1400ae617  jnz     short loc_1400AE620
0x1400ae619  cmp     [rdx+r11+10h], ebx
0x1400ae61e  jz      short loc_1400AE62C
0x1400ae620  inc     ecx
0x1400ae622  cmp     ecx, r8d
0x1400ae625  jb      short loc_1400AE5F8
0x1400ae627  jmp     loc_1400AE478
0x1400ae62c  movzx   r9d, word ptr [rsp+2B0h+var_240]
0x1400ae632  mov     r8d, eax
0x1400ae635  mov     r10d, [rsp+2B0h+var_234]
0x1400ae63a  lea     rbx, [r12+1298h]
0x1400ae642  mov     rax, [rbx]
0x1400ae645  cmp     rax, rbx
0x1400ae648  jz      short loc_1400AE690
0x1400ae64a  mov     ecx, [rbp+1B0h+arg_28]
0x1400ae650  cmp     [rax+14h], esi
0x1400ae653  jnz     short loc_1400AE670
0x1400ae655  cmp     [rax+20h], r9w
0x1400ae65a  jnz     short loc_1400AE670
0x1400ae65c  cmp     [rax+18h], r8d
0x1400ae660  jnz     short loc_1400AE670
0x1400ae662  cmp     [rax+10h], r10d
0x1400ae666  jnz     short loc_1400AE670
0x1400ae668  mov     r13, rax
0x1400ae66b  cmp     [rax+1Ch], ecx
0x1400ae66e  jz      short loc_1400AE67B
0x1400ae670  mov     rax, [rax]
0x1400ae673  xor     r13d, r13d
0x1400ae676  cmp     rax, rbx
0x1400ae679  jnz     short loc_1400AE650
0x1400ae67b  test    r13, r13
0x1400ae67e  jz      short loc_1400AE690
0x1400ae680  cmp     dword ptr [r13+24h], 0
0x1400ae685  jl      short loc_1400AE690
0x1400ae687  mov     r15b, [r13+22h]
0x1400ae68b  jmp     loc_1400AE480
0x1400ae690  mov     rcx, [rbp+1B0h+arg_38]
0x1400ae697  test    rcx, rcx
0x1400ae69a  jz      loc_1400AF41B
0x1400ae6a0  cmp     byte ptr [rbp+1B0h+var_230], 0
  ... truncated ...
```
