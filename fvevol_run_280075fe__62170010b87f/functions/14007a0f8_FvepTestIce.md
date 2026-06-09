# FvepTestIce

- ea: `0x14007a0f8`
- end: `0x14007afbb`
- name: `FvepTestIce`
- size: `3779`
- prototype: `__int64 __fastcall(int, int, int, int, int, __int64, void *Src, size_t Size, PVOID VirtualAddress, size_t, __int64)`
- caller_count: `1`
- callee_count: `17`
- tags: `loader_planting`

## callers

- `0x14007972c`

## callees

- `0x140005e50`
- `0x140007ce8`
- `0x140008288`
- `0x140008e44`
- `0x14000aef4`
- `0x14000c050`
- `0x14000c85c`
- `0x1400104f8`
- `0x140010560`
- `0x1400105d0`
- `0x140010674`
- `0x1400143d0`
- `0x140021a00`
- `0x140021d00`
- `0x14007a0f8`
- `0x1400a7704`
- `0x1400df568`

## import_xrefs

- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007aa21`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007aac8`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007aa21`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x14007aac8`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007aa35`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007aadc`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007aa35`
- `ntoskrnl!MmMdlPageContentsState` at `0x14007aadc`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007aaf8`
- `ntoskrnl!IoAllocateIrpEx` at `0x14007aaf8`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ac1b`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ad9f`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ac1b`
- `ntoskrnl!IoSetAdapterCryptoEngineExtension` at `0x14007ad9f`
- `ntoskrnl!IoFreeIrp` at `0x14007ac72`
- `ntoskrnl!IoFreeIrp` at `0x14007ac72`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007acc3`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007adfb`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007acc3`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x14007adfb`
- `ntoskrnl!IoFreeMdl` at `0x14007ac88`
- `ntoskrnl!IoFreeMdl` at `0x14007aca0`
- `ntoskrnl!IoFreeMdl` at `0x14007ac88`
- `ntoskrnl!IoFreeMdl` at `0x14007aca0`
- `ntoskrnl!IoAllocateMdl` at `0x14007a9c2`
- `ntoskrnl!IoAllocateMdl` at `0x14007aa5a`
- `ntoskrnl!IoAllocateMdl` at `0x14007a9c2`
- `ntoskrnl!IoAllocateMdl` at `0x14007aa5a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a36b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a399`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a36b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007a399`
- `ntoskrnl!ExAllocatePool2` at `0x14007a2e3`
- `ntoskrnl!ExAllocatePool2` at `0x14007a2e3`

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
  __int64 v33; // rcx
  __int64 v34; // r8
  unsigned int *v35; // rcx
  PDEVICE_OBJECT v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // r9
  _DWORD *v40; // rdi
  PDEVICE_OBJECT v41; // rcx
  __int64 v42; // rdx
  PDEVICE_OBJECT v43; // rcx
  __int64 v44; // rdx
  unsigned int v45; // r14d
  unsigned int v46; // edi
  __int64 v47; // rcx
  __int64 v48; // rdi
  unsigned __int16 v49; // r13
  PDEVICE_OBJECT v50; // rcx
  __int64 v51; // rdx
  PDEVICE_OBJECT v52; // rcx
  __int64 v53; // rdx
  ULONG v54; // eax
  NTSTATUS v55; // eax
  struct _DEVICE_OBJECT *v56; // r11
  int v57; // eax
  unsigned int v58; // r9d
  int IceKey; // eax
  struct _MDL *Mdl; // rax
  struct _MDL *v61; // r12
  struct _MDL *v62; // rax
  struct _MDL *v63; // r14
  __int64 v64; // rdx
  IRP *Irp; // rdi
  int v66; // r13d
  __int128 *v67; // rdx
  PDEVICE_OBJECT v68; // rcx
  __int64 v69; // rdx
  int v70; // r13d
  __int128 *v71; // rdx
  PDEVICE_OBJECT v72; // rcx
  __int64 v73; // rdx
  __int64 v74; // r9
  PDEVICE_OBJECT v75; // rcx
  __int64 v76; // rdx
  int v77; // [rsp+30h] [rbp-71h]
  int v78; // [rsp+30h] [rbp-71h]
  char *v79; // [rsp+68h] [rbp-39h]
  __int64 v80; // [rsp+70h] [rbp-31h] BYREF
  PVOID P; // [rsp+78h] [rbp-29h] BYREF
  __int128 v82; // [rsp+80h] [rbp-21h] BYREF
  _OWORD v83[4]; // [rsp+90h] [rbp-11h] BYREF
  USHORT pusResult; // [rsp+E8h] [rbp+47h] BYREF
  int v85; // [rsp+F8h] [rbp+57h]
  unsigned __int64 v86; // [rsp+100h] [rbp+5Fh]

  v86 = a4;
  v85 = a3;
  P = 0;
  v11 = 0;
  pusResult = 0;
  v80 = 0;
  v12 = 0;
  v83[0] = 0;
  v13 = a4;
  v14 = a2;
  v82 = 0;
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
      LODWORD(a3) = v85;
      v13 = v86;
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
        v72 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_36;
        }
        v73 = 102;
      }
      else
      {
        v26 = v24 + v25;
        if ( v24 + v25 >= v25 )
        {
          Pool2 = (char *)ExAllocatePool2(64, v26, 809850438);
          v79 = Pool2;
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
          v12[1] = v85;
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
          if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v33) )
          {
            v35 = *(unsigned int **)(a1 + 4720);
            if ( !v35 )
            {
              inited = -1073741637;
              v36 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v37 = 105;
              goto LABEL_54;
            }
            v38 = v35[3];
            v39 = 0;
            if ( (_DWORD)v38 )
            {
              v34 = v35[5];
              do
              {
                v40 = (unsigned int *)((char *)v35 + v35[4] + (_DWORD)v39 * (_DWORD)v34);
                if ( v40[2] == v14 )
                  break;
                v39 = (unsigned int)(v39 + 1);
              }
              while ( (unsigned int)v39 < (unsigned int)v38 );
            }
            else
            {
              v40 = 0;
            }
            if ( (unsigned int)v39 >= *(_DWORD *)(*(_QWORD *)(a1 + 4728) + 12LL) )
            {
              inited = -1073741637;
              v41 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v42 = 106;
              goto LABEL_66;
            }
            if ( (v32 & v40[5]) == 0 )
            {
              inited = -1073741637;
              v43 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v44 = 107;
              goto LABEL_72;
            }
            v45 = v40[3];
            v46 = v40[4];
          }
          else
          {
            v47 = *(_QWORD *)(a1 + 4728);
            if ( !v47 )
            {
              inited = -1073741637;
              v36 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v37 = 108;
LABEL_54:
              WPP_SF_d(v36->AttachedDevice, v37, WPP_0402621850d7386c9463338bd238830d_Traceguids, 3221225659LL);
              goto LABEL_36;
            }
            v38 = *(unsigned int *)(v47 + 12);
            v34 = 0;
            if ( (_DWORD)v38 )
            {
              while ( *(_DWORD *)(32 * ((unsigned int)v34 + 1LL) + v47) != v14 )
              {
                v34 = (unsigned int)(v34 + 1);
                if ( (unsigned int)v34 >= (unsigned int)v38 )
                  goto LABEL_82;
              }
            }
            else
            {
LABEL_82:
              if ( (unsigned int)v34 >= (unsigned int)v38 )
              {
                inited = -1073741637;
                v41 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_36;
                }
                v42 = 109;
                v39 = (unsigned int)v34;
LABEL_66:
                WPP_SF_Dd(v41->AttachedDevice, v42, WPP_0402621850d7386c9463338bd238830d_Traceguids, v39, -1073741637);
                goto LABEL_36;
              }
            }
            v48 = 32LL * (unsigned int)v34;
            if ( (v32 & *(_DWORD *)(v48 + v47 + 44)) == 0 )
            {
              inited = -1073741637;
              v43 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_36;
              }
              v44 = 110;
LABEL_72:
              WPP_SF_LDd(v43->AttachedDevice, v44, v34, v14, *(_DWORD *)(a1 + 1308));
              goto LABEL_36;
            }
            v45 = *(_DWORD *)(v48 + v47 + 36);
            v46 = *(_DWORD *)(v48 + v47 + 40);
          }
          if ( v45 == 2 )
          {
            if ( v46 == 1 )
            {
              v49 = -32766;
              v50 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                v51 = 111;
                v77 = 1;
LABEL_99:
                WPP_SF_LLL(v50->AttachedDevice, v51, WPP_0402621850d7386c9463338bd238830d_Traceguids, v14, 2, v77);
                goto LABEL_117;
              }
              goto LABEL_117;
            }
            if ( v46 == 3 )
            {
              v49 = -32765;
              v50 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                v51 = 112;
                v77 = 3;
                goto LABEL_99;
              }
LABEL_117:
              v54 = FveIceAlgorithmBitSizeToKeySize(v45, v46);
              v55 = RtlULongToUShort(v54, &pusResult);
              inited = v55;
              if ( v55 < 0 )
              {
                if ( WPP_GLOBAL_Control != v56
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    116,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)v55);
                }
LABEL_35:
                v12 = v79;
LABEL_36:
                v11 = v80;
                goto LABEL_37;
              }
              if ( (_DWORD)Size != pusResult )
              {
                inited = -1073741811;
                if ( WPP_GLOBAL_Control != v56
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_DDd(WPP_GLOBAL_Control->AttachedDevice, 117, pusResult, pusResult, Size, -1073741811);
                }
                goto LABEL_35;
              }
              v57 = FveDatumKeyCreate(v49, Src, pusResult, &v80);
              inited = v57;
              if ( v57 < 0 )
              {
                if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
                  && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
                {
                  WPP_SF_d(
                    WPP_GLOBAL_Control->AttachedDevice,
                    118,
                    WPP_0402621850d7386c9463338bd238830d_Traceguids,
                    (unsigned int)v57);
                }
                v12 = v79;
                goto LABEL_36;
              }
              v58 = v45;
              v11 = v80;
              IceKey = FveCreateIceKey(a1, v80, v14, v58, v46, (unsigned int **)&P);
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
                v12 = v79;
                goto LABEL_37;
              }
              Mdl = IoAllocateMdl(VirtualAddress, v16, 0, 0, 0);
              v61 = Mdl;
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
              MmMdlPageContentsState(v61, 1);
              v12 = v79;
              v62 = IoAllocateMdl(&v79[*((unsigned int *)v79 + 10)], v16, 0, 0, 0);
              v63 = v62;
              if ( !v62 )
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
              MmBuildMdlForNonPagedPool(v62);
              MmMdlPageContentsState(v63, 1);
              LOBYTE(v64) = *(_BYTE *)(*(_QWORD *)(a1 + 112) + 76LL) + 1;
              Irp = (IRP *)IoAllocateIrpEx(-1, v64, 0);
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
              *(_QWORD *)&v82 = a6;
              v83[0] = 0u;
              *((_QWORD *)&v82 + 1) = P;
              inited = FveInitPreallocatedIrp(a1, 4, 2, v86, v16, v61);
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
              v66 = v85;
              if ( v85 == 1 )
              {
                v67 = &v82;
              }
              else
              {
                if ( v85 != 2 )
                {
                  inited = -1073741637;
                  goto LABEL_166;
                }
                v67 = v83;
              }
              inited = IoSetAdapterCryptoEngineExtension(Irp, v67);
              if ( inited < 0 )
              {
LABEL_166:
                v68 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_171;
                }
                v69 = 124;
                goto LABEL_170;
              }
              --Irp->CurrentLocation;
              --Irp->Tail.Overlay.CurrentStackLocation;
              IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(a1 + 112), Irp);
              inited = Irp->IoStatus.Status;
              if ( inited < 0 )
              {
                v68 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_171;
                }
                v69 = 125;
                goto LABEL_170;
              }
              inited = FveInitPreallocatedIrp(a1, 3, 2, v86, v16, v63);
              if ( inited < 0 )
              {
                v68 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
                  goto LABEL_171;
                }
                v69 = 126;
                goto LABEL_170;
              }
              v70 = v66 - 1;
              if ( v70 )
              {
                if ( v70 != 1 )
                {
                  inited = -1073741637;
                  goto LABEL_191;
                }
                v71 = &v82;
              }
              else
              {
                v71 = v83;
              }
              inited = IoSetAdapterCryptoEngineExtension(Irp, v71);
              if ( inited >= 0 )
              {
                --Irp->CurrentLocation;
                --Irp->Tail.Overlay.CurrentStackLocation;
                IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(a1 + 112), Irp);
                inited = Irp->IoStatus.Status;
                if ( inited >= 0 )
                {
                  v12 = 0;
                  *a11 = v79;
                  goto LABEL_172;
                }
                v68 = WPP_GLOBAL_Control;
                if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                  || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                  || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                {
LABEL_171:
                  v12 = v79;
LABEL_172:
                  IoFreeIrp(Irp);
LABEL_173:
                  IoFreeMdl(v61);
                  if ( v63 )
                    IoFreeMdl(v63);
                  goto LABEL_36;
                }
                v69 = 128;
LABEL_170:
                WPP_SF_d(
                  v68->AttachedDevice,
                  v69,
                  WPP_0402621850d7386c9463338bd238830d_Traceguids,
                  (unsigned int)inited);
                goto LABEL_171;
              }
LABEL_191:
              v68 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_171;
              }
              v69 = 127;
              goto LABEL_170;
            }
          }
          else if ( v45 == 1 )
          {
            if ( v46 == 1 )
            {
              v49 = -32764;
              v52 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              {
                goto LABEL_117;
              }
              v53 = 113;
              v78 = 1;
            }
            else
            {
              if ( v46 != 3 )
                goto LABEL_201;
              v49 = -32763;
              v52 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
              {
                goto LABEL_117;
              }
              v53 = 114;
              v78 = 3;
            }
            WPP_SF_LLL(v52->AttachedDevice, v53, WPP_0402621850d7386c9463338bd238830d_Traceguids, v14, 1, v78);
            goto LABEL_117;
          }
LABEL_201:
          inited = -1073741637;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_LLLd(WPP_GLOBAL_Control->AttachedDevice, v38, 3, v14, v45, v46);
          }
          goto LABEL_36;
        }
        inited = -1073741675;
        v72 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_36;
        }
        v73 = 103;
      }
      WPP_SF_d(v72->AttachedDevice, v73, WPP_0402621850d7386c9463338bd238830d_Traceguids, 3221225621LL);
      goto LABEL_36;
    }
    v74 = 3221225621LL;
    inited = -1073741675;
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v76 = 101;
LABEL_218:
      WPP_SF_d(v75->AttachedDevice, v76, WPP_0402621850d7386c9463338bd238830d_Traceguids, v74);
    }
  }
  else
  {
    v74 = 3221225485LL;
    inited = -1073741811;
    v75 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v76 = 100;
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
0x14007a0f8  mov     rax, rsp
0x14007a0fb  mov     [rax+10h], rbx
0x14007a0ff  mov     [rax+20h], r9
0x14007a103  mov     [rax+18h], r8d
0x14007a107  push    rbp
0x14007a108  push    rsi
0x14007a109  push    rdi
0x14007a10a  push    r12
0x14007a10c  push    r13
0x14007a10e  push    r14
0x14007a110  push    r15
0x14007a112  lea     rbp, [rax-3Fh]
0x14007a116  sub     rsp, 0A0h
0x14007a11d  xor     eax, eax
0x14007a11f  mov     [rbp+37h+P], 0
0x14007a127  xor     r14d, r14d
0x14007a12a  mov     [rbp+37h+pusResult], ax
0x14007a12e  xorps   xmm0, xmm0
0x14007a131  mov     [rbp+37h+var_68], r14
0x14007a135  xorps   xmm1, xmm1
0x14007a138  xor     r13d, r13d
0x14007a13b  movups  [rbp+37h+var_48], xmm0
0x14007a13f  mov     r10, r9
0x14007a142  mov     r12d, edx
0x14007a145  movups  [rbp+37h+var_58], xmm1
0x14007a149  mov     rsi, rcx
0x14007a14c  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a153  lea     rax, WPP_GLOBAL_Control
0x14007a15a  mov     r15d, dword ptr [rbp+37h+arg_48]
0x14007a161  mov     r11d, 2000h
0x14007a167  mov     ebx, [rbp+37h+arg_20]
0x14007a16a  cmp     rcx, rax
0x14007a16d  jz      short loc_14007A1BA
0x14007a16f  test    [rcx+2Ch], r11d
0x14007a173  jz      short loc_14007A1BA
0x14007a175  cmp     byte ptr [rcx+29h], 5
0x14007a179  mov     edi, dword ptr [rbp+37h+Size]
0x14007a17c  jb      short loc_14007A1BD
0x14007a17e  mov     rax, [rbp+37h+arg_28]
0x14007a182  mov     rcx, [rcx+18h]
0x14007a186  mov     dword ptr [rsp+0D0h+var_88], r15d
0x14007a18b  mov     [rsp+0D0h+var_90], ebx
0x14007a18f  mov     qword ptr [rsp+0D0h+var_98], r9
0x14007a194  mov     r9d, edx
0x14007a197  mov     [rsp+0D0h+var_A0], rax
0x14007a19c  mov     dword ptr [rsp+0D0h+var_A8], edi
0x14007a1a0  mov     dword ptr [rsp+0D0h+Irp], r8d
0x14007a1a5  call    WPP_SF_LLDiiDD
0x14007a1aa  mov     r8d, [rbp+37h+arg_10]
0x14007a1ae  mov     r11d, 2000h
0x14007a1b4  mov     r10, [rbp+37h+arg_18]
0x14007a1b8  jmp     short loc_14007A1BD
0x14007a1ba  mov     edi, dword ptr [rbp+37h+Size]
0x14007a1bd  test    rsi, rsi
0x14007a1c0  jz      loc_14007AF80
0x14007a1c6  mov     ecx, [rsi+51Ch]
0x14007a1cc  test    ecx, ecx
0x14007a1ce  jz      loc_14007AF80
0x14007a1d4  lea     r9d, [rcx-1]
0x14007a1d8  test    ecx, r9d
0x14007a1db  jnz     loc_14007AF80
0x14007a1e1  lea     eax, [r8-1]
0x14007a1e5  cmp     eax, 1
0x14007a1e8  ja      loc_14007AF80
0x14007a1ee  test    r10, r10
0x14007a1f1  jz      loc_14007AF80
0x14007a1f7  mov     rdx, [rsi+418h]
0x14007a1fe  cmp     r10, rdx
0x14007a201  jnb     loc_14007AF80
0x14007a207  lea     r8, [r10+rbx]
0x14007a20b  cmp     r8, r10
0x14007a20e  jbe     loc_14007AF80
0x14007a214  cmp     r8, rdx
0x14007a217  jnb     loc_14007AF80
0x14007a21d  lea     rax, [rcx-1]
0x14007a221  mov     r8d, ecx
0x14007a224  test    rax, rcx
0x14007a227  jnz     short loc_14007A22E
0x14007a229  test    r10, rax
0x14007a22c  jmp     short loc_14007A239
0x14007a22e  xor     edx, edx
0x14007a230  mov     rax, r10
0x14007a233  div     r8
0x14007a236  test    rdx, rdx
0x14007a239  jnz     loc_14007AF80
0x14007a23f  test    ebx, r9d
0x14007a242  jnz     loc_14007AF80
0x14007a248  cmp     [rbp+37h+Src], r13
0x14007a24c  jz      loc_14007AF80
0x14007a252  lea     eax, [rdi-1]
0x14007a255  cmp     eax, 3Fh ; '?'
0x14007a258  ja      loc_14007AF80
0x14007a25e  test    dil, 0Fh
0x14007a262  jnz     loc_14007AF80
0x14007a268  cmp     [rbp+37h+VirtualAddress], r13
0x14007a26f  jz      loc_14007AF80
0x14007a275  test    r15d, r15d
0x14007a278  jz      loc_14007AF80
0x14007a27e  cmp     r15d, ebx
0x14007a281  ja      loc_14007AF80
0x14007a287  test    r15d, r9d
0x14007a28a  jnz     loc_14007AF80
0x14007a290  cmp     [rbp+37h+arg_50], r13
0x14007a297  jz      loc_14007AF80
0x14007a29d  lea     ebx, [rdi+0Fh]
0x14007a2a0  mov     ecx, 0FFFFFFF0h
0x14007a2a5  and     ebx, ecx
0x14007a2a7  add     ebx, 30h ; '0'
0x14007a2aa  cmp     ebx, 30h ; '0'
0x14007a2ad  jb      loc_14007AF32
0x14007a2b3  lea     eax, [r15+0Fh]
0x14007a2b7  and     eax, ecx
0x14007a2b9  lea     r14d, [rax+rbx]
0x14007a2bd  cmp     r14d, ebx
0x14007a2c0  jb      loc_14007AEF7
0x14007a2c6  lea     edi, [rax+r14]
0x14007a2ca  cmp     edi, r14d
0x14007a2cd  jb      loc_14007AEA9
0x14007a2d3  mov     r8d, 30455646h
0x14007a2d9  mov     edx, edi
0x14007a2db  mov     ecx, 40h ; '@'
0x14007a2e0  mov     r13d, edi
0x14007a2e3  call    cs:__imp_ExAllocatePool2
0x14007a2ea  nop     dword ptr [rax+rax+00h]
0x14007a2ef  mov     [rbp+37h+var_70], rax
0x14007a2f3  test    rax, rax
0x14007a2f6  jnz     loc_14007A3F6
0x14007a2fc  mov     r9d, 0C000009Ah
0x14007a302  mov     ebx, r9d
0x14007a305  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a30c  lea     r11, WPP_GLOBAL_Control
0x14007a313  cmp     rcx, r11
0x14007a316  jz      loc_14007A8D9
0x14007a31c  test    dword ptr [rcx+2Ch], 2000h
0x14007a323  jz      loc_14007A8D9
0x14007a329  cmp     byte ptr [rcx+29h], 2
0x14007a32d  jb      loc_14007A8D9
0x14007a333  mov     rcx, [rcx+18h]
0x14007a337  lea     edx, [rax+68h]
0x14007a33a  mov     dword ptr [rsp+0D0h+Irp], r9d
0x14007a33f  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007a346  mov     r9d, edi
0x14007a349  call    WPP_SF_Dd
0x14007a34e  mov     r13, [rbp+37h+var_70]
0x14007a352  lea     rdi, WPP_GLOBAL_Control
0x14007a359  mov     r14, [rbp+37h+var_68]
0x14007a35d  mov     rcx, [rbp+37h+P]; P
0x14007a361  test    rcx, rcx
0x14007a364  jz      short loc_14007A37F
0x14007a366  mov     edx, 656E6F4Eh; Tag
0x14007a36b  call    cs:__imp_ExFreePoolWithTag
0x14007a372  nop     dword ptr [rax+rax+00h]
0x14007a377  mov     [rbp+37h+P], 0
0x14007a37f  test    r14, r14
0x14007a382  jz      short loc_14007A38C
0x14007a384  mov     rcx, r14
0x14007a387  call    FveDatumFree
0x14007a38c  test    r13, r13
0x14007a38f  jz      short loc_14007A3A5
0x14007a391  mov     edx, 30455646h; Tag
0x14007a396  mov     rcx, r13; P
0x14007a399  call    cs:__imp_ExFreePoolWithTag
0x14007a3a0  nop     dword ptr [rax+rax+00h]
0x14007a3a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a3ac  cmp     rcx, rdi
0x14007a3af  jz      short loc_14007A3D8
0x14007a3b1  test    dword ptr [rcx+2Ch], 2000h
0x14007a3b8  jz      short loc_14007A3D8
0x14007a3ba  cmp     byte ptr [rcx+29h], 5
0x14007a3be  jb      short loc_14007A3D8
0x14007a3c0  mov     rcx, [rcx+18h]
0x14007a3c4  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007a3cb  mov     edx, 81h
0x14007a3d0  mov     r9d, ebx
0x14007a3d3  call    WPP_SF_d
0x14007a3d8  mov     eax, ebx
0x14007a3da  mov     rbx, [rsp+0D0h+arg_8]
0x14007a3e2  add     rsp, 0A0h
0x14007a3e9  pop     r15
0x14007a3eb  pop     r14
0x14007a3ed  pop     r13
0x14007a3ef  pop     r12
0x14007a3f1  pop     rdi
0x14007a3f2  pop     rsi
0x14007a3f3  pop     rbp
0x14007a3f4  retn
0x14007a3f6  mov     r8, r13; Size
0x14007a3f9  xor     edx, edx; Val
0x14007a3fb  mov     rcx, rax; void *
0x14007a3fe  mov     r13, rax
0x14007a401  call    memset
0x14007a406  mov     eax, [rbp+37h+arg_10]
0x14007a409  mov     ecx, 30h ; '0'
0x14007a40e  mov     rdx, [rbp+37h+Src]; Src
0x14007a412  mov     [r13+2], ax
0x14007a417  mov     rax, [rbp+37h+arg_28]
0x14007a41b  mov     [r13+10h], rax
0x14007a41f  mov     eax, dword ptr [rbp+37h+Size]
0x14007a422  mov     [r13+0], cx
0x14007a427  mov     r8d, eax; Size
0x14007a42a  mov     [r13+18h], ecx
0x14007a42e  lea     rcx, [r13+30h]; void *
0x14007a432  mov     [r13+4], edi
0x14007a436  mov     [r13+8], r12d
0x14007a43a  mov     [r13+0Ch], r15d
0x14007a43e  mov     [r13+1Ch], eax
0x14007a442  mov     [r13+20h], ebx
0x14007a446  mov     [r13+24h], r15d
0x14007a44a  mov     [r13+28h], r14d
0x14007a44e  mov     [r13+2Ch], r15d
0x14007a452  call    memmove
0x14007a457  mov     ecx, [r13+20h]
0x14007a45b  mov     r8, r15; Size
0x14007a45e  mov     rdx, [rbp+37h+VirtualAddress]; Src
0x14007a465  add     rcx, r13; void *
0x14007a468  call    memmove
0x14007a46d  mov     ebx, [rsi+51Ch]
0x14007a473  shr     ebx, 9
0x14007a476  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x14007a47b  test    eax, eax
0x14007a47d  jz      loc_14007A5D4
0x14007a483  mov     rcx, [rsi+1270h]
0x14007a48a  test    rcx, rcx
0x14007a48d  jnz     short loc_14007A4DF
0x14007a48f  mov     ebx, 0C00000BBh
0x14007a494  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a49b  lea     rax, WPP_GLOBAL_Control
0x14007a4a2  cmp     rcx, rax
0x14007a4a5  jz      loc_14007A352
0x14007a4ab  test    dword ptr [rcx+2Ch], 2000h
0x14007a4b2  jz      loc_14007A352
0x14007a4b8  cmp     byte ptr [rcx+29h], 2
0x14007a4bc  jb      loc_14007A352
0x14007a4c2  mov     edx, 69h ; 'i'
0x14007a4c7  mov     rcx, [rcx+18h]
0x14007a4cb  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007a4d2  mov     r9d, ebx
0x14007a4d5  call    WPP_SF_d
0x14007a4da  jmp     loc_14007A352
0x14007a4df  mov     edx, [rcx+0Ch]
0x14007a4e2  xor     r9d, r9d
0x14007a4e5  test    edx, edx
0x14007a4e7  jz      short loc_14007A510
0x14007a4e9  mov     r8d, [rcx+14h]
0x14007a4ed  mov     r10d, [rcx+10h]
0x14007a4f1  mov     eax, r8d
0x14007a4f4  imul    eax, r9d
0x14007a4f8  add     eax, r10d
0x14007a4fb  lea     rdi, [rcx+rax]
0x14007a4ff  cmp     [rcx+rax+8], r12d
0x14007a504  jz      short loc_14007A512
0x14007a506  inc     r9d
0x14007a509  cmp     r9d, edx
0x14007a50c  jb      short loc_14007A4F1
0x14007a50e  jmp     short loc_14007A512
0x14007a510  xor     edi, edi
0x14007a512  mov     rax, [rsi+1278h]
0x14007a519  cmp     r9d, [rax+0Ch]
0x14007a51d  jb      short loc_14007A570
0x14007a51f  mov     ebx, 0C00000BBh
0x14007a524  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a52b  lea     rax, WPP_GLOBAL_Control
0x14007a532  cmp     rcx, rax
0x14007a535  jz      loc_14007A352
0x14007a53b  test    dword ptr [rcx+2Ch], 2000h
0x14007a542  jz      loc_14007A352
0x14007a548  cmp     byte ptr [rcx+29h], 2
0x14007a54c  jb      loc_14007A352
0x14007a552  mov     edx, 6Ah ; 'j'
0x14007a557  mov     rcx, [rcx+18h]
0x14007a55b  lea     r8, WPP_0402621850d7386c9463338bd238830d_Traceguids
0x14007a562  mov     dword ptr [rsp+0D0h+Irp], ebx
0x14007a566  call    WPP_SF_Dd
0x14007a56b  jmp     loc_14007A352
0x14007a570  test    [rdi+14h], ebx
0x14007a573  jnz     short loc_14007A5C8
0x14007a575  mov     ebx, 0C00000BBh
0x14007a57a  mov     rcx, cs:WPP_GLOBAL_Control
0x14007a581  lea     rax, WPP_GLOBAL_Control
0x14007a588  cmp     rcx, rax
0x14007a58b  jz      loc_14007A352
0x14007a591  test    dword ptr [rcx+2Ch], 2000h
0x14007a598  jz      loc_14007A352
0x14007a59e  cmp     byte ptr [rcx+29h], 2
0x14007a5a2  jb      loc_14007A352
0x14007a5a8  mov     edx, 6Bh ; 'k'
0x14007a5ad  mov     eax, [rsi+51Ch]
0x14007a5b3  mov     r9d, r12d
0x14007a5b6  mov     rcx, [rcx+18h]
0x14007a5ba  mov     dword ptr [rsp+0D0h+Irp], eax
0x14007a5be  call    WPP_SF_LDd
0x14007a5c3  jmp     loc_14007A352
0x14007a5c8  mov     r14d, [rdi+0Ch]
0x14007a5cc  mov     edi, [rdi+10h]
0x14007a5cf  jmp     loc_14007A6D7
0x14007a5d4  mov     rcx, [rsi+1278h]
0x14007a5db  test    rcx, rcx
0x14007a5de  jnz     short loc_14007A61D
0x14007a5e0  mov     ebx, 0C00000BBh
0x14007a5e5  mov     rcx, cs:WPP_GLOBAL_Control
  ... truncated ...
```
