# FvepTestIce

- ea: `0x14007c19c`
- end: `0x14007d05f`
- name: `FvepTestIce`
- size: `3779`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, void *Src, size_t Size, PVOID VirtualAddress, size_t, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x14007b75c`

## callees

- `0x140005e60`
- `0x140007da8`
- `0x140008348`
- `0x140008f04`
- `0x14000afb4`
- `0x14000c1e0`
- `0x14000c9ec`
- `0x1400108f4`
- `0x14001095c`
- `0x1400109cc`
- `0x140010a70`
- `0x140014d88`
- `0x140022d40`
- `0x140023040`
- `0x14007c19c`
- `0x1400a865c`
- `0x1400e1d84`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007cac5`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007cb6c`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007cac5`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007cb6c`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007cad9`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007cb80`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007cad9`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007cb80`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007cb9c`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007cb9c`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ccbf`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ce43`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ccbf`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ce43`
- `ntoskrnl!IoFreeIrp` at `0x14007cd16`
- `ntoskrnl!IoFreeIrp` at `0x14007cd16`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007cd67`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007ce9f`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007cd67`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007ce9f`
- `ntoskrnl!IoFreeMdl` at `0x14007cd2c`
- `ntoskrnl!IoFreeMdl` at `0x14007cd44`
- `ntoskrnl!IoFreeMdl` at `0x14007cd2c`
- `ntoskrnl!IoFreeMdl` at `0x14007cd44`
- `ntoskrnl!IoAllocateMdl` at `0x14007ca66`
- `ntoskrnl!IoAllocateMdl` at `0x14007cafe`
- `ntoskrnl!IoAllocateMdl` at `0x14007ca66`
- `ntoskrnl!IoAllocateMdl` at `0x14007cafe`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c40f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c43d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c40f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007c43d`
- `ntoskrnl!ExAllocatePool2` at `0x14007c387`
- `ntoskrnl!ExAllocatePool2` at `0x14007c387`

## pseudocode

```c
__int64 __fastcall FvepTestIce(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned __int64 a4,
        unsigned int a5,
        __int64 a6,
        void *Src,
        size_t Size,
        PVOID VirtualAddress,
        size_t a10,
        _QWORD *a11)
{
  __int64 v11; // r14
  _WORD *v12; // r13
  unsigned __int64 v13; // r10
  unsigned int v14; // r12d
  size_t v16; // r15
  __int64 v17; // rbx
  int v18; // edi
  __int64 v19; // rcx
  int v20; // r9d
  unsigned __int64 v21; // rdx
  bool v22; // zf
  unsigned int v23; // ebx
  int v24; // eax
  unsigned int v25; // r14d
  unsigned int v26; // edi
  char *Pool2; // rax
  int inited; // ebx
  const void *v30; // rdx
  unsigned int v31; // eax
  int v32; // ebx
  __int64 v33; // rdx
  __int64 v34; // rcx
  __int64 v35; // r8
  unsigned int *v36; // rcx
  PDEVICE_OBJECT v37; // rcx
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // r9
  _DWORD *v41; // rdi
  PDEVICE_OBJECT v42; // rcx
  __int64 v43; // rdx
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  unsigned int v46; // r14d
  unsigned int v47; // edi
  __int64 v48; // rcx
  __int64 v49; // rdi
  unsigned __int16 v50; // r13
  PDEVICE_OBJECT v51; // rcx
  __int64 v52; // rdx
  PDEVICE_OBJECT v53; // rcx
  __int64 v54; // rdx
  ULONG v55; // eax
  NTSTATUS v56; // eax
  struct _DEVICE_OBJECT *v57; // r11
  int v58; // eax
  unsigned int v59; // r9d
  int IceKey; // eax
  struct _MDL *Mdl; // rax
  struct _MDL *v62; // r12
  struct _MDL *v63; // rax
  struct _MDL *v64; // r14
  __int64 v65; // rdx
  IRP *Irp; // rdi
  int v67; // r13d
  __int128 *v68; // rdx
  PDEVICE_OBJECT v69; // rcx
  __int64 v70; // rdx
  int v71; // r13d
  __int128 *v72; // rdx
  PDEVICE_OBJECT v73; // rcx
  __int64 v74; // rdx
  __int64 v75; // r9
  PDEVICE_OBJECT v76; // rcx
  __int64 v77; // rdx
  int v78; // [rsp+30h] [rbp-71h]
  int v79; // [rsp+30h] [rbp-71h]
  char *v80; // [rsp+68h] [rbp-39h]
  __int64 v81; // [rsp+70h] [rbp-31h] BYREF
  PVOID P; // [rsp+78h] [rbp-29h] BYREF
  __int128 v83; // [rsp+80h] [rbp-21h] BYREF
  _OWORD v84[4]; // [rsp+90h] [rbp-11h] BYREF
  USHORT pusResult; // [rsp+E8h] [rbp+47h] BYREF
  int v86; // [rsp+F8h] [rbp+57h]
  unsigned __int64 v87; // [rsp+100h] [rbp+5Fh]

  v87 = a4;
  v86 = a3;
  P = 0;
  v11 = 0;
  pusResult = 0;
  v81 = 0;
  v12 = 0;
  v84[0] = 0;
  v13 = a4;
  v14 = a2;
  v83 = 0;
  v16 = (unsigned int)a10;
  v17 = a5;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0 )
  {
    v18 = Size;
  }
  else
  {
    v18 = Size;
    if ( BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_LLDiiDD(WPP_GLOBAL_Control->AttachedDevice, a2, a3, (unsigned int)a2, a3, Size, a6, a4, a5, a10);
      LODWORD(a3) = v86;
      v13 = v87;
    }
  }
  if ( a1
    && (v19 = *(unsigned int *)(a1 + 1308), (_DWORD)v19)
    && (v20 = v19 - 1, (((_DWORD)v19 - 1) & (unsigned int)v19) == 0)
    && (unsigned int)(a3 - 1) <= 1
    && v13
    && (v21 = *(_QWORD *)(a1 + 1048), v13 < v21)
    && v13 + v17 > v13
    && v13 + v17 < v21
    && ((v19 & (v19 - 1)) != 0 ? (v22 = v13 % (unsigned int)v19 == 0) : (v22 = ((v19 - 1) & v13) == 0),
        v22
     && (v20 & (unsigned int)v17) == 0
     && Src
     && (unsigned int)(v18 - 1) <= 0x3F
     && (v18 & 0xF) == 0
     && VirtualAddress
     && (_DWORD)v16
     && (unsigned int)v16 <= (unsigned int)v17
     && (v20 & (unsigned int)v16) == 0
     && a11) )
  {
    v23 = ((v18 + 15) & 0xFFFFFFF0) + 48;
    if ( ((v18 + 15) & 0xFFFFFFF0) < 0xFFFFFFD0 )
    {
      v24 = (v16 + 15) & 0xFFFFFFF0;
      v25 = v24 + v23;
      if ( v24 + v23 < v23 )
      {
        inited = -1073741675;
        v73 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_36;
        }
        v74 = 102;
      }
      else
      {
        v26 = v24 + v25;
        if ( v24 + v25 >= v25 )
        {
          Pool2 = (char *)ExAllocatePool2(64, v26, 809850438);
          v80 = Pool2;
          if ( !Pool2 )
          {
            inited = -1073741670;
            if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
              || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
            {
              v12 = 0;
              goto LABEL_36;
            }
            WPP_SF_Dd(
              WPP_GLOBAL_Control->AttachedDevice,
              104,
              WPP_0402621850d7386c9463338bd238830d_Traceguids,
              v26,
              -1073741670);
            goto LABEL_35;
          }
          v12 = Pool2;
          memset(Pool2, 0, v26);
          v30 = Src;
          v12[1] = v86;
          *((_QWORD *)v12 + 2) = a6;
          v31 = Size;
          *v12 = 48;
          *((_DWORD *)v12 + 6) = 48;
          *((_DWORD *)v12 + 1) = v26;
          *((_DWORD *)v12 + 2) = v14;
          *((_DWORD *)v12 + 3) = v16;
          *((_DWORD *)v12 + 7) = v31;
          *((_DWORD *)v12 + 8) = v23;
          *((_DWORD *)v12 + 9) = v16;
          *((_DWORD *)v12 + 10) = v25;
          *((_DWORD *)v12 + 11) = v16;
          memmove(v12 + 24, v30, v31);
          memmove((char *)v12 + *((unsigned int *)v12 + 8), VirtualAddress, v16);
          v32 = *(_DWORD *)(a1 + 1308) >> 9;
          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v34, v33) )
          {
            v36 = *(unsigned int **)(a1 + 4736);
            if ( !v36 )
            {
              inited = -1073741637;
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v38 = 105;
              goto LABEL_54;
            }
            v39 = v36[3];
            v40 = 0;
            if ( (_DWORD)v39 )
            {
              v35 = v36[5];
              do
              {
                v41 = (unsigned int *)((char *)v36 + v36[4] + (_DWORD)v40 * (_DWORD)v35);
                if ( v41[2] == v14 )
                  break;
                v40 = (unsigned int)(v40 + 1);
              }
              while ( (unsigned int)v40 < (unsigned int)v39 );
            }
            else
            {
              v41 = 0;
            }
            if ( (unsigned int)v40 >= *(_DWORD *)(*(_QWORD *)(a1 + 4744) + 12LL) )
            {
              inited = -1073741637;
              v42 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v43 = 106;
              goto LABEL_66;
            }
            if ( (v32 & v41[5]) == 0 )
            {
              inited = -1073741637;
              v44 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v45 = 107;
              goto LABEL_72;
            }
            v46 = v41[3];
            v47 = v41[4];
          }
          else
          {
            v48 = *(_QWORD *)(a1 + 4744);
            if ( !v48 )
            {
              inited = -1073741637;
              v37 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v38 = 108;
LABEL_54:
              WPP_SF_d(v37->AttachedDevice, v38, WPP_0402621850d7386c9463338bd238830d_Traceguids, 3221225659LL);
              goto LABEL_36;
            }
            v39 = *(unsigned int *)(v48 + 12);
            v35 = 0;
            if ( (_DWORD)v39 )
            {
              while ( *(_DWORD *)(32 * ((unsigned int)v35 + 1LL) + v48) != v14 )
              {
                v35 = (unsigned int)(v35 + 1);
                if ( (unsigned int)v35 >= (unsigned int)v39 )
                  goto LABEL_82;
              }
            }
            else
            {
LABEL_82:
              if ( (unsigned int)v35 >= (unsigned int)v39 )
              {
                inited = -1073741637;
                v42 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_36;
                }
                v43 = 109;
                v40 = (unsigned int)v35;
LABEL_66:
                WPP_SF_Dd(v42->AttachedDevice, v43, WPP_0402621850d7386c9463338bd238830d_Traceguids, v40, -1073741637);
                goto LABEL_36;
              }
            }
            v49 = 32LL * (unsigned int)v35;
            if ( (v32 & *(_DWORD *)(v49 + v48 + 44)) == 0 )
            {
              inited = -1073741637;
              v44 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v45 = 110;
LABEL_72:
              WPP_SF_LDd(v44->AttachedDevice, v45, v35, v14, *(_DWORD *)(a1 + 1308));
              goto LABEL_36;
            }
            v46 = *(_DWORD *)(v49 + v48 + 36);
            v47 = *(_DWORD *)(v49 + v48 + 40);
          }
          if ( v46 == 2 )
          {
            if ( v47 == 1 )
            {
              v50 = -32766;
              v51 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                v52 = 111;
                v78 = 1;
LABEL_99:
                WPP_SF_LLL(v51->AttachedDevice, v52, WPP_0402621850d7386c9463338bd238830d_Traceguids, v14, 2, v78);
                goto LABEL_117;
              }
              goto LABEL_117;
            }
            if ( v47 == 3 )
            {
              v50 = -32765;
              v51 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                v52 = 112;
                v78 = 3;
                goto LABEL_99;
              }
LABEL_117:
              v55 = FveIceAlgorithmBitSizeToKeySize(v46, v47);
              v56 = RtlULongToUShort(v55, &pusResult);
              inited = v56;
              if ( v56 < 0 )
              {
                if ( WPP_GLOBAL_Control != v57
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    116,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)v56);
                }
LABEL_35:
                v12 = v80;
LABEL_36:
                v11 = v81;
                goto LABEL_37;
              }
              if ( (_DWORD)Size != pusResult )
              {
                inited = -1073741811;
                if ( WPP_GLOBAL_Control != v57
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 117, pusResult, pusResult, Size, -1073741811);
                }
                goto LABEL_35;
              }
              v58 = FveDatumKeyCreate(v50, Src, pusResult, &v81);
              inited = v58;
              if ( v58 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    118,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)v58);
                }
                v12 = v80;
                goto LABEL_36;
              }
              v59 = v46;
              v11 = v81;
              IceKey = FveCreateIceKey(a1, v81, v14, v59, v47, (unsigned int **)&P);
              inited = IceKey;
              if ( IceKey < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    119,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)IceKey);
                }
LABEL_139:
                v12 = v80;
                goto LABEL_37;
              }
              Mdl = IoAllocateMdl(VirtualAddress, v16, 0, 0, 0);
              v62 = Mdl;
              if ( !Mdl )
              {
                inited = -1073741670;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    120,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)v16,
                    -1073741670);
                }
                goto LABEL_139;
              }
              MmBuildMdlForNonPagedPool(Mdl);
              MmMdlPageContentsState(v62, 1);
              v12 = v80;
              v63 = IoAllocateMdl(&v80[*((unsigned int *)v80 + 10)], v16, 0, 0, 0);
              v64 = v63;
              if ( !v63 )
              {
                inited = -1073741670;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_Dd(
                    WPP_GLOBAL_Control->AttachedDevice,
                    121,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)v16,
                    -1073741670);
                }
                goto LABEL_173;
              }
              MmBuildMdlForNonPagedPool(v63);
              MmMdlPageContentsState(v64, 1);
              LOBYTE(v65) = *(_BYTE *)(*(_QWORD *)(a1 + 112) + 76LL) + 1;
              Irp = (IRP *)IoAllocateIrpEx(-1, v65, 0);
              if ( !Irp )
              {
                inited = -1073741670;
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    122,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    3221225626LL);
                }
                goto LABEL_173;
              }
              *(_QWORD *)&v83 = a6;
              v84[0] = 0u;
              *((_QWORD *)&v83 + 1) = P;
              inited = FveInitPreallocatedIrp(a1, 4, 2, v87, v16, v62);
              if ( inited < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    123,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)inited);
                }
                goto LABEL_172;
              }
              v67 = v86;
              if ( v86 == 1 )
              {
                v68 = &v83;
              }
              else
              {
                if ( v86 != 2 )
                {
                  inited = -1073741637;
                  goto LABEL_166;
                }
                v68 = v84;
              }
              inited = IoSetAdapterCryptoEngineExtension(Irp, v68);
              if ( inited < 0 )
              {
LABEL_166:
                v69 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_171;
                }
                v70 = 124;
                goto LABEL_170;
              }
              --Irp->CurrentLocation;
              --Irp->Tail.Overlay.CurrentStackLocation;
              IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(a1 + 112), Irp);
              inited = Irp->IoStatus.Status;
              if ( inited < 0 )
              {
                v69 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_171;
                }
                v70 = 125;
                goto LABEL_170;
              }
              inited = FveInitPreallocatedIrp(a1, 3, 2, v87, v16, v64);
              if ( inited < 0 )
              {
                v69 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_171;
                }
                v70 = 126;
                goto LABEL_170;
              }
              v71 = v67 - 1;
              if ( v71 )
              {
                if ( v71 != 1 )
                {
                  inited = -1073741637;
                  goto LABEL_191;
                }
                v72 = &v83;
              }
              else
              {
                v72 = v84;
              }
              inited = IoSetAdapterCryptoEngineExtension(Irp, v72);
              if ( inited >= 0 )
              {
                --Irp->CurrentLocation;
                --Irp->Tail.Overlay.CurrentStackLocation;
                IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(a1 + 112), Irp);
                inited = Irp->IoStatus.Status;
                if ( inited >= 0 )
                {
                  v12 = 0;
                  *a11 = v80;
                  goto LABEL_172;
                }
                v69 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
LABEL_171:
                  v12 = v80;
LABEL_172:
                  IoFreeIrp(Irp);
LABEL_173:
                  IoFreeMdl(v62);
                  if ( v64 )
                    IoFreeMdl(v64);
                  goto LABEL_36;
                }
                v70 = 128;
LABEL_170:
                WPP_SF_d(
                  v69->AttachedDevice,
                  v70,
                  WPP_0402621850d7386c9463338bd238830d_Traceguids,
                  (unsigned int)inited);
                goto LABEL_171;
              }
LABEL_191:
              v69 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_171;
              }
              v70 = 127;
              goto LABEL_170;
            }
          }
          else if ( v46 == 1 )
          {
            if ( v47 == 1 )
            {
              v50 = -32764;
              v53 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              {
                goto LABEL_117;
              }
              v54 = 113;
              v79 = 1;
            }
            else
            {
              if ( v47 != 3 )
                goto LABEL_201;
              v50 = -32763;
              v53 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              {
                goto LABEL_117;
              }
              v54 = 114;
              v79 = 3;
            }
            WPP_SF_LLL(v53->AttachedDevice, v54, WPP_0402621850d7386c9463338bd238830d_Traceguids, v14, 1, v79);
            goto LABEL_117;
          }
LABEL_201:
          inited = -1073741637;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_LLLd(WPP_GLOBAL_Control->AttachedDevice, v39, 3, v14, v46, v47);
          }
          goto LABEL_36;
        }
        inited = -1073741675;
        v73 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_36;
        }
        v74 = 103;
      }
      WPP_SF_d(v73->AttachedDevice, v74, WPP_0402621850d7386c9463338bd238830d_Traceguids, 3221225621LL);
      goto LABEL_36;
    }
    v75 = 3221225621LL;
    inited = -1073741675;
    v76 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v77 = 101;
LABEL_218:
      WPP_SF_d(v76->AttachedDevice, v77, WPP_0402621850d7386c9463338bd238830d_Traceguids, v75);
    }
  }
  else
  {
    v75 = 3221225485LL;
    inited = -1073741811;
    v76 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v77 = 100;
      goto LABEL_218;
    }
  }
LABEL_37:
  if ( P )
  {
    ExFreePoolWithTag(P, 0x656E6F4Eu);
    P = 0;
  }
  if ( v11 )
    FveDatumFree(v11);
  if ( v12 )
    ExFreePoolWithTag(v12, 0x30455646u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      129,
      WPP_0402621850d7386c9463338bd238830d_Traceguids,
      (unsigned int)inited);
  }
  return (unsigned int)inited;
}

```

## disassembly

```asm
0x14007c19c  mov     rax, rsp
0x14007c19f  mov     [rax+10h], rbx
0x14007c1a3  mov     [rax+20h], r9
0x14007c1a7  mov     [rax+18h], r8d
0x14007c1ab  push    rbp
0x14007c1ac  push    rsi
0x14007c1ad  push    rdi
0x14007c1ae  push    r12
0x14007c1b0  push    r13
0x14007c1b2  push    r14
0x14007c1b4  push    r15
0x14007c1b6  lea     rbp, [rax-3Fh]
0x14007c1ba  sub     rsp, 0A0h
0x14007c1c1  xor     eax, eax
0x14007c1c3  mov     [rbp+37h+P], 0
0x14007c1cb  xor     r14d, r14d
0x14007c1ce  mov     [rbp+37h+pusResult], ax
0x14007c1d2  xorps   xmm0, xmm0
0x14007c1d5  mov     [rbp+37h+var_68], r14
0x14007c1d9  xorps   xmm1, xmm1
0x14007c1dc  xor     r13d, r13d
0x14007c1df  movups  [rbp+37h+var_48], xmm0
0x14007c1e3  mov     r10, r9
0x14007c1e6  mov     r12d, edx
0x14007c1e9  movups  [rbp+37h+var_58], xmm1
0x14007c1ed  mov     rsi, rcx
0x14007c1f0  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c1f7  lea     rax, WPP_GLOBAL_Control
0x14007c1fe  mov     r15d, dword ptr [rbp+37h+arg_48]
0x14007c205  mov     r11d, 2000h
0x14007c20b  mov     ebx, [rbp+37h+arg_20]
0x14007c20e  cmp     rcx, rax
0x14007c211  jz      short loc_14007C25E
0x14007c213  test    [rcx+2Ch], r11d
0x14007c217  jz      short loc_14007C25E
0x14007c219  cmp     byte ptr [rcx+29h], 5
0x14007c21d  mov     edi, dword ptr [rbp+37h+Size]
0x14007c220  jb      short loc_14007C261
0x14007c222  mov     rax, [rbp+37h+arg_28]
0x14007c226  mov     rcx, [rcx+18h]
0x14007c22a  mov     dword ptr [rsp+0D0h+var_88], r15d
0x14007c22f  mov     [rsp+0D0h+var_90], ebx
0x14007c233  mov     qword ptr [rsp+0D0h+var_98], r9
0x14007c238  mov     r9d, edx
0x14007c23b  mov     [rsp+0D0h+var_A0], rax
0x14007c240  mov     dword ptr [rsp+0D0h+var_A8], edi
0x14007c244  mov     dword ptr [rsp+0D0h+Irp], r8d
0x14007c249  call    WPP_SF_LLDiiDD
0x14007c24e  mov     r8d, [rbp+37h+arg_10]
0x14007c252  mov     r11d, 2000h
0x14007c258  mov     r10, [rbp+37h+arg_18]
0x14007c25c  jmp     short loc_14007C261
0x14007c25e  mov     edi, dword ptr [rbp+37h+Size]
0x14007c261  test    rsi, rsi
0x14007c264  jz      loc_14007D024
0x14007c26a  mov     ecx, [rsi+51Ch]
0x14007c270  test    ecx, ecx
0x14007c272  jz      loc_14007D024
0x14007c278  lea     r9d, [rcx-1]
0x14007c27c  test    ecx, r9d
0x14007c27f  jnz     loc_14007D024
0x14007c285  lea     eax, [r8-1]
0x14007c289  cmp     eax, 1
0x14007c28c  ja      loc_14007D024
0x14007c292  test    r10, r10
0x14007c295  jz      loc_14007D024
0x14007c29b  mov     rdx, [rsi+418h]
0x14007c2a2  cmp     r10, rdx
0x14007c2a5  jnb     loc_14007D024
0x14007c2ab  lea     r8, [r10+rbx]
0x14007c2af  cmp     r8, r10
0x14007c2b2  jbe     loc_14007D024
0x14007c2b8  cmp     r8, rdx
0x14007c2bb  jnb     loc_14007D024
0x14007c2c1  lea     rax, [rcx-1]
0x14007c2c5  mov     r8d, ecx
0x14007c2c8  test    rax, rcx
0x14007c2cb  jnz     short loc_14007C2D2
0x14007c2cd  test    r10, rax
0x14007c2d0  jmp     short loc_14007C2DD
0x14007c2d2  xor     edx, edx
0x14007c2d4  mov     rax, r10
0x14007c2d7  div     r8
0x14007c2da  test    rdx, rdx
0x14007c2dd  jnz     loc_14007D024
0x14007c2e3  test    ebx, r9d
0x14007c2e6  jnz     loc_14007D024
0x14007c2ec  cmp     [rbp+37h+Src], r13
0x14007c2f0  jz      loc_14007D024
0x14007c2f6  lea     eax, [rdi-1]
0x14007c2f9  cmp     eax, 3Fh ; '?'
0x14007c2fc  ja      loc_14007D024
0x14007c302  test    dil, 0Fh
0x14007c306  jnz     loc_14007D024
0x14007c30c  cmp     [rbp+37h+VirtualAddress], r13
0x14007c313  jz      loc_14007D024
0x14007c319  test    r15d, r15d
0x14007c31c  jz      loc_14007D024
0x14007c322  cmp     r15d, ebx
0x14007c325  ja      loc_14007D024
0x14007c32b  test    r15d, r9d
0x14007c32e  jnz     loc_14007D024
0x14007c334  cmp     [rbp+37h+arg_50], r13
0x14007c33b  jz      loc_14007D024
0x14007c341  lea     ebx, [rdi+0Fh]
0x14007c344  mov     ecx, 0FFFFFFF0h
0x14007c349  and     ebx, ecx
0x14007c34b  add     ebx, 30h ; '0'
0x14007c34e  cmp     ebx, 30h ; '0'
0x14007c351  jb      loc_14007CFD6
0x14007c357  lea     eax, [r15+0Fh]
0x14007c35b  and     eax, ecx
0x14007c35d  lea     r14d, [rax+rbx]
0x14007c361  cmp     r14d, ebx
0x14007c364  jb      loc_14007CF9B
0x14007c36a  lea     edi, [rax+r14]
0x14007c36e  cmp     edi, r14d
0x14007c371  jb      loc_14007CF4D
0x14007c377  mov     r8d, 30455646h
0x14007c37d  mov     edx, edi
0x14007c37f  mov     ecx, 40h ; '@'
0x14007c384  mov     r13d, edi
0x14007c387  call    cs:__imp_ExAllocatePool2
0x14007c38e  nop     dword ptr [rax+rax+00h]
0x14007c393  mov     [rbp+37h+var_70], rax
0x14007c397  test    rax, rax
0x14007c39a  jnz     loc_14007C49A
0x14007c3a0  mov     r9d, 0C000009Ah
0x14007c3a6  mov     ebx, r9d
0x14007c3a9  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c3b0  lea     r11, WPP_GLOBAL_Control
0x14007c3b7  cmp     rcx, r11
0x14007c3ba  jz      loc_14007C97D
0x14007c3c0  test    dword ptr [rcx+2Ch], 2000h
0x14007c3c7  jz      loc_14007C97D
0x14007c3cd  cmp     byte ptr [rcx+29h], 2
0x14007c3d1  jb      loc_14007C97D
0x14007c3d7  mov     rcx, [rcx+18h]
0x14007c3db  lea     edx, [rax+68h]
0x14007c3de  mov     dword ptr [rsp+0D0h+Irp], r9d
0x14007c3e3  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007c3ea  mov     r9d, edi
0x14007c3ed  call    WPP_SF_Dd
0x14007c3f2  mov     r13, [rbp+37h+var_70]
0x14007c3f6  lea     rdi, WPP_GLOBAL_Control
0x14007c3fd  mov     r14, [rbp+37h+var_68]
0x14007c401  mov     rcx, [rbp+37h+P]; P
0x14007c405  test    rcx, rcx
0x14007c408  jz      short loc_14007C423
0x14007c40a  mov     edx, 656E6F4Eh; Tag
0x14007c40f  call    cs:__imp_ExFreePoolWithTag
0x14007c416  nop     dword ptr [rax+rax+00h]
0x14007c41b  mov     [rbp+37h+P], 0
0x14007c423  test    r14, r14
0x14007c426  jz      short loc_14007C430
0x14007c428  mov     rcx, r14
0x14007c42b  call    FveDatumFree
0x14007c430  test    r13, r13
0x14007c433  jz      short loc_14007C449
0x14007c435  mov     edx, 30455646h; Tag
0x14007c43a  mov     rcx, r13; P
0x14007c43d  call    cs:__imp_ExFreePoolWithTag
0x14007c444  nop     dword ptr [rax+rax+00h]
0x14007c449  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c450  cmp     rcx, rdi
0x14007c453  jz      short loc_14007C47C
0x14007c455  test    dword ptr [rcx+2Ch], 2000h
0x14007c45c  jz      short loc_14007C47C
0x14007c45e  cmp     byte ptr [rcx+29h], 5
0x14007c462  jb      short loc_14007C47C
0x14007c464  mov     rcx, [rcx+18h]
0x14007c468  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007c46f  mov     edx, 81h
0x14007c474  mov     r9d, ebx
0x14007c477  call    WPP_SF_d
0x14007c47c  mov     eax, ebx
0x14007c47e  mov     rbx, [rsp+0D0h+arg_8]
0x14007c486  add     rsp, 0A0h
0x14007c48d  pop     r15
0x14007c48f  pop     r14
0x14007c491  pop     r13
0x14007c493  pop     r12
0x14007c495  pop     rdi
0x14007c496  pop     rsi
0x14007c497  pop     rbp
0x14007c498  retn
0x14007c49a  mov     r8, r13; Size
0x14007c49d  xor     edx, edx; Val
0x14007c49f  mov     rcx, rax; void *
0x14007c4a2  mov     r13, rax
0x14007c4a5  call    memset
0x14007c4aa  mov     eax, [rbp+37h+arg_10]
0x14007c4ad  mov     ecx, 30h ; '0'
0x14007c4b2  mov     rdx, [rbp+37h+Src]; Src
0x14007c4b6  mov     [r13+2], ax
0x14007c4bb  mov     rax, [rbp+37h+arg_28]
0x14007c4bf  mov     [r13+10h], rax
0x14007c4c3  mov     eax, dword ptr [rbp+37h+Size]
0x14007c4c6  mov     [r13+0], cx
0x14007c4cb  mov     r8d, eax; Size
0x14007c4ce  mov     [r13+18h], ecx
0x14007c4d2  lea     rcx, [r13+30h]; void *
0x14007c4d6  mov     [r13+4], edi
0x14007c4da  mov     [r13+8], r12d
0x14007c4de  mov     [r13+0Ch], r15d
0x14007c4e2  mov     [r13+1Ch], eax
0x14007c4e6  mov     [r13+20h], ebx
0x14007c4ea  mov     [r13+24h], r15d
0x14007c4ee  mov     [r13+28h], r14d
0x14007c4f2  mov     [r13+2Ch], r15d
0x14007c4f6  call    memmove
0x14007c4fb  mov     ecx, [r13+20h]
0x14007c4ff  mov     r8, r15; Size
0x14007c502  mov     rdx, [rbp+37h+VirtualAddress]; Src
0x14007c509  add     rcx, r13; void *
0x14007c50c  call    memmove
0x14007c511  mov     ebx, [rsi+51Ch]
0x14007c517  shr     ebx, 9
0x14007c51a  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x14007c51f  test    eax, eax
0x14007c521  jz      loc_14007C678
0x14007c527  mov     rcx, [rsi+1280h]
0x14007c52e  test    rcx, rcx
0x14007c531  jnz     short loc_14007C583
0x14007c533  mov     ebx, 0C00000BBh
0x14007c538  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c53f  lea     rax, WPP_GLOBAL_Control
0x14007c546  cmp     rcx, rax
0x14007c549  jz      loc_14007C3F6
0x14007c54f  test    dword ptr [rcx+2Ch], 2000h
0x14007c556  jz      loc_14007C3F6
0x14007c55c  cmp     byte ptr [rcx+29h], 2
0x14007c560  jb      loc_14007C3F6
0x14007c566  mov     edx, 69h ; 'i'
0x14007c56b  mov     rcx, [rcx+18h]
0x14007c56f  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007c576  mov     r9d, ebx
0x14007c579  call    WPP_SF_d
0x14007c57e  jmp     loc_14007C3F6
0x14007c583  mov     edx, [rcx+0Ch]
0x14007c586  xor     r9d, r9d
0x14007c589  test    edx, edx
0x14007c58b  jz      short loc_14007C5B4
0x14007c58d  mov     r8d, [rcx+14h]
0x14007c591  mov     r10d, [rcx+10h]
0x14007c595  mov     eax, r8d
0x14007c598  imul    eax, r9d
0x14007c59c  add     eax, r10d
0x14007c59f  lea     rdi, [rcx+rax]
0x14007c5a3  cmp     [rcx+rax+8], r12d
0x14007c5a8  jz      short loc_14007C5B6
0x14007c5aa  inc     r9d
0x14007c5ad  cmp     r9d, edx
0x14007c5b0  jb      short loc_14007C595
0x14007c5b2  jmp     short loc_14007C5B6
0x14007c5b4  xor     edi, edi
0x14007c5b6  mov     rax, [rsi+1288h]
0x14007c5bd  cmp     r9d, [rax+0Ch]
0x14007c5c1  jb      short loc_14007C614
0x14007c5c3  mov     ebx, 0C00000BBh
0x14007c5c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c5cf  lea     rax, WPP_GLOBAL_Control
0x14007c5d6  cmp     rcx, rax
0x14007c5d9  jz      loc_14007C3F6
0x14007c5df  test    dword ptr [rcx+2Ch], 2000h
0x14007c5e6  jz      loc_14007C3F6
0x14007c5ec  cmp     byte ptr [rcx+29h], 2
0x14007c5f0  jb      loc_14007C3F6
0x14007c5f6  mov     edx, 6Ah ; 'j'
0x14007c5fb  mov     rcx, [rcx+18h]
0x14007c5ff  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007c606  mov     dword ptr [rsp+0D0h+Irp], ebx
0x14007c60a  call    WPP_SF_Dd
0x14007c60f  jmp     loc_14007C3F6
0x14007c614  test    [rdi+14h], ebx
0x14007c617  jnz     short loc_14007C66C
0x14007c619  mov     ebx, 0C00000BBh
0x14007c61e  mov     rcx, cs:WPP_GLOBAL_Control
0x14007c625  lea     rax, WPP_GLOBAL_Control
0x14007c62c  cmp     rcx, rax
0x14007c62f  jz      loc_14007C3F6
0x14007c635  test    dword ptr [rcx+2Ch], 2000h
0x14007c63c  jz      loc_14007C3F6
0x14007c642  cmp     byte ptr [rcx+29h], 2
0x14007c646  jb      loc_14007C3F6
0x14007c64c  mov     edx, 6Bh ; 'k'
0x14007c651  mov     eax, [rsi+51Ch]
0x14007c657  mov     r9d, r12d
0x14007c65a  mov     rcx, [rcx+18h]
0x14007c65e  mov     dword ptr [rsp+0D0h+Irp], eax
0x14007c662  call    WPP_SF_LDd
0x14007c667  jmp     loc_14007C3F6
0x14007c66c  mov     r14d, [rdi+0Ch]
0x14007c670  mov     edi, [rdi+10h]
0x14007c673  jmp     loc_14007C77B
0x14007c678  mov     rcx, [rsi+1288h]
0x14007c67f  test    rcx, rcx
0x14007c682  jnz     short loc_14007C6C1
0x14007c684  mov     ebx, 0C00000BBh
0x14007c689  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
