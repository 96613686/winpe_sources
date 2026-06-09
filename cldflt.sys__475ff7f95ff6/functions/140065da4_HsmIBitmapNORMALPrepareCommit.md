# HsmIBitmapNORMALPrepareCommit

- ea: `0x140065da4`
- end: `0x140067729`
- name: `HsmIBitmapNORMALPrepareCommit`
- size: `6533`
- prototype: `__int64 __fastcall(__int64, __int64, char, __int64, _DWORD *)`
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x140067974`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009c7c`
- `0x140009d14`
- `0x14000a120`
- `0x14000d95c`
- `0x1400188ec`
- `0x140018a5c`
- `0x140018f10`
- `0x140019300`
- `0x140019774`
- `0x140019d84`
- `0x140019f90`
- `0x14001b8dc`
- `0x14001e300`
- `0x14001e600`
- `0x140036400`
- `0x140065250`
- `0x140065da4`
- `0x140067730`
- `0x1400677dc`
- `0x1400678d4`
- `0x140071cd8`
- `0x14007300c`
- `0x140076054`
- `0x140078d98`
- `0x140085304`

## import_xrefs

- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140066626`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140066626`
- `ntoskrnl!RtlComputeCrc32` at `0x14006615a`
- `ntoskrnl!RtlComputeCrc32` at `0x1400670ad`
- `ntoskrnl!RtlComputeCrc32` at `0x14006615a`
- `ntoskrnl!RtlComputeCrc32` at `0x1400670ad`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066d29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400676af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400676ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400676e2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066d29`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400676af`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400676ce`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400676e2`
- `ntoskrnl!ExAllocatePool2` at `0x140065ead`
- `ntoskrnl!ExAllocatePool2` at `0x140065f2c`
- `ntoskrnl!ExAllocatePool2` at `0x140065ead`
- `ntoskrnl!ExAllocatePool2` at `0x140065f2c`
- `FLTMGR!FltReleasePushLockEx` at `0x1400660ef`
- `FLTMGR!FltReleasePushLockEx` at `0x140067696`
- `FLTMGR!FltReleasePushLockEx` at `0x1400660ef`
- `FLTMGR!FltReleasePushLockEx` at `0x140067696`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140066067`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140066067`

## pseudocode

```c
__int64 __fastcall HsmIBitmapNORMALPrepareCommit(__int64 a1, __int64 a2, char a3, __int64 a4, _DWORD *a5)
{
  _OWORD *Pool2; // r13
  int v9; // ebx
  int v10; // r8d
  UCHAR *v11; // r15
  signed __int64 *v12; // rcx
  unsigned int v13; // r15d
  unsigned int v14; // r15d
  signed __int64 v15; // rax
  unsigned int v16; // edx
  signed __int64 v17; // rbx
  int v18; // r8d
  int v19; // r8d
  PUCHAR v20; // rbx
  unsigned int v21; // r8d
  __int64 i; // rcx
  signed __int64 v23; // rcx
  ULONG v24; // eax
  PUCHAR v25; // rcx
  int v26; // eax
  _DWORD *v27; // rdx
  unsigned int v28; // r8d
  char v29; // r9
  unsigned __int64 v30; // rax
  __int64 v31; // rdx
  unsigned int v32; // ecx
  int v33; // r8d
  unsigned __int64 v34; // rax
  unsigned __int64 v35; // rax
  int v36; // edx
  __int64 v37; // r8
  __int64 v38; // rax
  unsigned __int64 v39; // rax
  __int64 v40; // r9
  __int64 v41; // r8
  __int64 v42; // rax
  _DWORD *v43; // r10
  _DWORD *v44; // rdx
  _DWORD *v45; // rcx
  unsigned __int64 v46; // rax
  size_t v47; // r8
  size_t v48; // r9
  __int64 v49; // r10
  __int64 v50; // rcx
  _DWORD *v51; // rcx
  PUCHAR v52; // rax
  PDEVICE_OBJECT v53; // rcx
  char v54; // cl
  PVOID v55; // rdi
  int v57; // eax
  BASE_MCB *v58; // rcx
  ULONG v59; // eax
  signed __int64 v60; // rcx
  int v61; // r8d
  char v62; // dl
  __int64 v63; // r8
  __int64 v64; // rax
  unsigned int v65; // r10d
  unsigned int v66; // r11d
  __int64 v67; // rax
  int v68; // r10d
  PDEVICE_OBJECT v69; // rcx
  int v70; // r8d
  int v71; // edx
  PDEVICE_OBJECT v72; // rcx
  PDEVICE_OBJECT v73; // r8
  int v74; // edx
  int v75; // ecx
  int v76; // edx
  void *v77; // rcx
  int v78; // r8d
  int v79; // edx
  int v80; // edx
  _DWORD *v81; // rax
  unsigned int v82; // ecx
  PDEVICE_OBJECT v83; // rcx
  int v84; // edx
  void *v85; // rcx
  char v86; // [rsp+30h] [rbp-158h]
  PUCHAR Buffer; // [rsp+60h] [rbp-128h]
  _BYTE v88[4]; // [rsp+68h] [rbp-120h] BYREF
  int v89; // [rsp+6Ch] [rbp-11Ch] BYREF
  char v90; // [rsp+70h] [rbp-118h] BYREF
  _BYTE v91[7]; // [rsp+71h] [rbp-117h] BYREF
  _QWORD *v92; // [rsp+78h] [rbp-110h]
  PVOID P; // [rsp+80h] [rbp-108h]
  unsigned int v94; // [rsp+88h] [rbp-100h]
  unsigned int v95; // [rsp+8Ch] [rbp-FCh]
  __int64 v96; // [rsp+90h] [rbp-F8h] BYREF
  PVOID Address; // [rsp+98h] [rbp-F0h] BYREF
  _DWORD *v98; // [rsp+A0h] [rbp-E8h]
  int v99; // [rsp+A8h] [rbp-E0h]
  signed __int64 v100; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 SectorCount; // [rsp+B8h] [rbp-D0h] BYREF
  __int64 Vbn; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 Lbn; // [rsp+C8h] [rbp-C0h] BYREF
  __int64 v104; // [rsp+D0h] [rbp-B8h] BYREF
  signed __int64 *v105; // [rsp+D8h] [rbp-B0h]
  __int64 v106; // [rsp+E0h] [rbp-A8h] BYREF
  __int128 v107; // [rsp+F0h] [rbp-98h] BYREF
  __int128 v108; // [rsp+100h] [rbp-88h] BYREF
  char *v109; // [rsp+110h] [rbp-78h]
  __int64 Parameter; // [rsp+118h] [rbp-70h] BYREF
  signed __int64 *v111; // [rsp+120h] [rbp-68h]
  int v112[2]; // [rsp+128h] [rbp-60h] BYREF
  PVOID *v113; // [rsp+130h] [rbp-58h]
  int v114[2]; // [rsp+138h] [rbp-50h] BYREF
  __int64 v115; // [rsp+190h] [rbp+8h] BYREF
  signed __int64 v116; // [rsp+198h] [rbp+10h]
  char v117; // [rsp+1A0h] [rbp+18h]
  __int64 v118; // [rsp+1A8h] [rbp+20h]

  v118 = a4;
  v117 = a3;
  v116 = a2;
  v115 = a1;
  v100 = 0;
  Buffer = 0;
  Address = 0;
  v107 = 0u;
  LOWORD(v89) = 0;
  BYTE2(v89) = 0;
  v88[0] = 0;
  v90 = 0;
  v113 = (PVOID *)(a1 + 152);
  Pool2 = *(_OWORD **)(a1 + 152);
  P = Pool2;
  Lbn = (__int64)Pool2;
  *(_QWORD *)(a1 + 152) = 0;
  v9 = *(_DWORD *)(a1 + 24);
  if ( v9 < 0 )
  {
    v75 = *(_DWORD *)(a1 + 24);
LABEL_171:
    HsmDbgBreakOnStatus(v75);
    goto LABEL_145;
  }
  v98 = (_DWORD *)(a1 + 16);
  if ( a2 > 535822848LL * (unsigned int)(1 << ((*(_DWORD *)(a1 + 16) >> 6) & 0x3F)) || *a5 < 0x38u )
  {
    v75 = -1073741595;
    v9 = -1073741595;
    goto LABEL_171;
  }
  v9 = HsmIBitmapNORMALMayContainDirtyRange(a1, a2, &v90);
  HsmDbgBreakOnStatus(v9);
  if ( v9 < 0 )
  {
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_145;
    }
    v76 = 125;
LABEL_176:
    WPP_SF_qisd(v72->AttachedDevice, v76, v10, a1, *(_QWORD *)a1, a1 + 32, v9);
    goto LABEL_145;
  }
  if ( Pool2 )
  {
    v77 = (void *)*((_QWORD *)Pool2 + 2);
    if ( v77 )
      ExFreePoolWithTag(v77, 0x6D427348u);
  }
  else
  {
    Pool2 = (_OWORD *)ExAllocatePool2(258, 32, 1665299272);
    P = Pool2;
    Lbn = (__int64)Pool2;
  }
  if ( !Pool2 )
  {
    v9 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 126, v78, a1, *(_QWORD *)a1, a1 + 32, 154);
    }
    goto LABEL_145;
  }
  v104 = a1 + 16;
  v92 = (_QWORD *)a1;
  *Pool2 = 0;
  Pool2[1] = 0;
  if ( !v90 )
  {
    LOWORD(v89) = 257;
    v9 = HsmiBitmapNORMALPrepareMcbsForCommit(a1, &v89);
    HsmDbgBreakOnStatus(v9);
    if ( v9 >= 0 )
    {
      *(_QWORD *)Pool2 = a2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 128, v70, a1, *(_QWORD *)a1, a1 + 32);
      }
LABEL_31:
      *(_QWORD *)a4 = 1884451906;
      *(_DWORD *)(a4 + 8) = 56;
      *(_DWORD *)(a4 + 12) = 327680;
      *(_OWORD *)(a4 + 16) = 0;
      *(_OWORD *)(a4 + 32) = 0;
      *(_QWORD *)(a4 + 48) = 0;
      v30 = (unsigned int)*a5;
      if ( (unsigned int)v30 < 0x18 || (v31 = *(unsigned int *)(a4 + 8), ((v31 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v30) )
      {
        v9 = -1073741789;
      }
      else
      {
        v32 = (v31 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(a4 + 8) = v32;
        *(_DWORD *)(a4 + 16) = 65543;
        *(_DWORD *)(a4 + 20) = v32;
        *(_BYTE *)(v32 + a4) = 1;
        ++*(_DWORD *)(a4 + 8);
        v9 = 0;
      }
      HsmDbgBreakOnStatus(v9);
      if ( v9 < 0 )
      {
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_136;
        }
        v71 = 151;
        goto LABEL_265;
      }
      v34 = (unsigned int)*a5;
      if ( (unsigned int)v34 < 0x18 )
        goto LABEL_36;
      v62 = (*v98 >> 6) & 0x3F;
      if ( *(_WORD *)(a4 + 14) <= 1u )
      {
        v9 = -1073741811;
      }
      else
      {
        if ( (unsigned int)v34 < 0x20
          || (v63 = *(unsigned int *)(a4 + 8), ((v63 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v34) )
        {
LABEL_36:
          v9 = -1073741789;
          goto LABEL_37;
        }
        v64 = ((_DWORD)v63 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(a4 + 8) = v64;
        if ( *(_WORD *)(a4 + 24) )
          *(_WORD *)(a4 + 12) |= 1u;
        *(_DWORD *)(a4 + 24) = 65543;
        *(_DWORD *)(a4 + 28) = v64;
        *(_BYTE *)(v64 + a4) = v62;
        ++*(_DWORD *)(a4 + 8);
        v9 = 0;
      }
LABEL_37:
      HsmDbgBreakOnStatus(v9);
      if ( v9 < 0 )
      {
        v69 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_136;
        }
        v71 = 152;
        goto LABEL_265;
      }
      v35 = (unsigned int)*a5;
      if ( (unsigned int)v35 >= 0x18 )
      {
        v36 = (int)(*((_DWORD *)P + 6) << 29) >> 29;
        if ( *(_WORD *)(a4 + 14) <= 2u )
        {
          v9 = -1073741811;
          goto LABEL_45;
        }
        if ( (unsigned int)v35 >= 0x28 )
        {
          v37 = *(unsigned int *)(a4 + 8);
          if ( ((v37 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= v35 )
          {
            v38 = ((_DWORD)v37 + 3) & 0xFFFFFFFC;
            *(_DWORD *)(a4 + 8) = v38;
            if ( *(_WORD *)(a4 + 32) )
              *(_WORD *)(a4 + 12) |= 1u;
            *(_DWORD *)(a4 + 32) = 65543;
            *(_DWORD *)(a4 + 36) = v38;
            *(_BYTE *)(v38 + a4) = v36;
            ++*(_DWORD *)(a4 + 8);
            v9 = 0;
LABEL_45:
            HsmDbgBreakOnStatus(v9);
            if ( v9 < 0 )
            {
              v69 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_136;
              }
              v71 = 153;
              goto LABEL_265;
            }
            v39 = (unsigned int)*a5;
            if ( (unsigned int)v39 >= 0x18 )
            {
              v40 = *((_QWORD *)P + 1);
              if ( *(_WORD *)(a4 + 14) <= 3u )
              {
                v9 = -1073741811;
                goto LABEL_53;
              }
              if ( (unsigned int)v39 >= 0x30 )
              {
                v41 = *(unsigned int *)(a4 + 8);
                if ( ((v41 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v39 )
                {
                  v42 = ((_DWORD)v41 + 3) & 0xFFFFFFFC;
                  *(_DWORD *)(a4 + 8) = v42;
                  if ( *(_WORD *)(a4 + 40) )
                    *(_WORD *)(a4 + 12) |= 1u;
                  *(_DWORD *)(a4 + 40) = 524294;
                  *(_DWORD *)(a4 + 44) = v42;
                  *(_QWORD *)(v42 + a4) = v40;
                  *(_DWORD *)(a4 + 8) += 8;
                  v9 = 0;
LABEL_53:
                  HsmDbgBreakOnStatus(v9);
                  if ( v9 < 0 )
                  {
                    v69 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_136;
                    }
                    v71 = 154;
                    goto LABEL_265;
                  }
                  v43 = P;
                  v44 = (_DWORD *)*((_QWORD *)P + 2);
                  if ( !v44 )
                    goto LABEL_69;
                  v45 = v44 + 1023;
                  if ( v44 + 1023 >= v44 )
                  {
                    do
                    {
                      v46 = (unsigned __int64)(v45 - 1);
                      if ( *(v45 - 1) != v44[1022] )
                        break;
                      --v45;
                    }
                    while ( v46 > (unsigned __int64)v44 );
                  }
                  v47 = (unsigned int)*a5;
                  if ( (unsigned int)v47 >= 0x18 )
                  {
                    if ( *(_WORD *)(a4 + 14) <= 4u )
                    {
                      v9 = -1073741811;
                      goto LABEL_67;
                    }
                    if ( (unsigned int)v47 >= 0x38 )
                    {
                      v48 = (unsigned __int16)((_WORD)v45 - *((_WORD *)P + 8) + 4);
                      v49 = *(unsigned int *)(a4 + 8);
                      if ( v48 + ((v49 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v47 )
                      {
                        if ( *(_WORD *)(a4 + 48) )
                          *(_WORD *)(a4 + 12) |= 1u;
                        v50 = ((_DWORD)v49 + 3) & 0xFFFFFFFC;
                        *(_DWORD *)(a4 + 8) = v50;
                        *(_WORD *)(a4 + 48) = 17;
                        *(_WORD *)(a4 + 50) = v48;
                        *(_DWORD *)(a4 + 52) = v50;
                        v51 = (_DWORD *)(a4 + v50);
                        if ( v51 != v44 )
                          memmove(v51, v44, v48);
                        *(_DWORD *)(a4 + 8) += *(unsigned __int16 *)(a4 + 50);
                        v9 = 0;
                        goto LABEL_67;
                      }
                    }
                  }
                  v9 = -1073741789;
LABEL_67:
                  HsmDbgBreakOnStatus(v9);
                  if ( v9 >= 0 )
                  {
                    v43 = P;
LABEL_69:
                    *(_WORD *)(a4 + 12) &= ~2u;
                    *(_DWORD *)(a4 + 4) = 0;
                    *a5 = *(_DWORD *)(a4 + 8);
                    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
                      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
                    {
                      WPP_SF_qisdiidd(
                        WPP_GLOBAL_Control->AttachedDevice,
                        a1 + 32,
                        (int)(v43[6] << 29) >> 29,
                        a1,
                        *v92,
                        a1 + 32,
                        (*v98 >> 6) & 0x3F,
                        *(_QWORD *)(a1 + 144),
                        *((_QWORD *)v43 + 1),
                        (*v98 >> 12) & 7,
                        (int)(v43[6] << 29) >> 29);
                    }
                    *v113 = P;
                    P = 0;
                    v52 = 0;
                    Buffer = 0;
                    goto LABEL_79;
                  }
                  v69 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  {
LABEL_136:
                    v52 = 0;
                    goto LABEL_81;
                  }
                  v71 = 155;
LABEL_265:
                  WPP_SF_qisd(v69->AttachedDevice, v71, v33, a1, *v92, a1 + 32, v9);
                  goto LABEL_136;
                }
              }
            }
            v9 = -1073741789;
            goto LABEL_53;
          }
        }
      }
      v9 = -1073741789;
      goto LABEL_45;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        127,
        WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
        (unsigned int)v9);
    }
LABEL_145:
    v52 = 0;
    goto LABEL_79;
  }
  v9 = HsmiBitmapNORMALPrepareMcbsForCommit(a1, &v89);
  HsmDbgBreakOnStatus(v9);
  if ( v9 < 0 )
  {
    v72 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_145;
    }
    v76 = 129;
    goto LABEL_176;
  }
  v11 = (UCHAR *)ExAllocatePool2(256, 4096, 1833071432);
  Buffer = v11;
  v106 = (__int64)v11;
  if ( !v11 )
  {
    v9 = -1073741670;
    HsmDbgBreakOnStatus(-1073741670);
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_78;
      v79 = 130;
      v86 = -102;
      goto LABEL_198;
    }
    goto LABEL_110;
  }
  v12 = (signed __int64 *)(a1 + 8);
  v111 = (signed __int64 *)(a1 + 8);
  if ( *(__int64 *)(a1 + 8) > 0 && (*(_DWORD *)(a1 + 16) & 0x10) == 0 )
  {
    v96 = 0;
    v9 = HsmIBitmapNORMALQueryRangeEx(a1, 7, (unsigned int)&v96, (int)a1 + 8, (__int64)v88, (__int64)&v100);
    HsmDbgBreakOnStatus(v9);
    if ( v9 >= 0 )
    {
      v12 = v111;
      goto LABEL_13;
    }
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_78;
      v79 = 131;
LABEL_197:
      v86 = v9;
LABEL_198:
      WPP_SF_qisd(v53->AttachedDevice, v79, v18, a1, *(_QWORD *)a1, a1 + 32, v86);
      goto LABEL_78;
    }
LABEL_110:
    v52 = v11;
    goto LABEL_79;
  }
  v88[0] = 1;
  v100 = 0;
LABEL_13:
  v105 = v12;
  if ( v88[0] && v100 == *v12 )
  {
    v89 = 0;
    *((_DWORD *)Pool2 + 6) |= 8u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 132, 7, a1, *(_QWORD *)a1, a1 + 32);
    }
    memset(v11, 255, 0x1000u);
LABEL_28:
    v24 = RtlComputeCrc32(0, Buffer, 0xFFCu);
    v25 = Buffer;
    *((_DWORD *)Buffer + 1023) = v24;
    v26 = v89;
    if ( !v89 )
    {
      *((_QWORD *)P + 1) = 0;
LABEL_30:
      v27 = P;
      *((_QWORD *)P + 2) = v25;
      v28 = v26 ^ (v27[6] ^ v26) & 0xFFFFFFF8;
      v27[6] = v28;
      v29 = v116;
      *(_QWORD *)v27 = v116;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_qisddi(
          WPP_GLOBAL_Control->AttachedDevice,
          (*v98 >> 6) & 0x3F,
          (int)(v28 << 29) >> 29,
          a1,
          *v92,
          a1 + 32,
          (*v98 >> 6) & 0x3F,
          (int)(v28 << 29) >> 29,
          v29);
      }
      goto LABEL_31;
    }
    Parameter = 0;
    *(_QWORD *)&v108 = a1;
    *((_QWORD *)&v108 + 1) = (unsigned int)v89;
    v109 = (char *)P + 8;
    v9 = HsmExpandKernelStackAndCallout(HsmiBitmapNORMALFlushBitmapOnDiskCallout, (NTSTATUS *)&Parameter);
    HsmDbgBreakOnStatus(v9);
    if ( v9 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_qisdi(
          WPP_GLOBAL_Control->AttachedDevice,
          149,
          a1 + 32,
          a1,
          *v92,
          a1 + 32,
          (*v98 >> 6) & 0x3F,
          *((_QWORD *)P + 1));
      }
      v25 = Buffer;
      v26 = v89;
      goto LABEL_30;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        148,
        WPP_bfb53edd803c34b7e21dabd1716d08d4_Traceguids,
        (unsigned int)v9);
    }
LABEL_106:
    v52 = Buffer;
    goto LABEL_81;
  }
  v13 = *(_DWORD *)(a1 + 16);
  v95 = 1 << ((v13 >> 6) & 0x3F);
  v14 = (v13 >> 12) & 7;
  v89 = v14;
  v94 = v14;
  v15 = HsmiBitmapNORMALComputeMaxUserFileSize(v14, v95);
  v17 = v116;
  if ( v15 < v116 )
  {
    do
      v94 = ++v14;
    while ( (__int64)HsmiBitmapNORMALComputeMaxUserFileSize(v14, v16) < v17 );
    v89 = v14;
  }
  Parameter = 0;
  *(_QWORD *)&v108 = a1;
  DWORD2(v108) = v14;
  HIDWORD(v108) = HsmiBitmapNORMALGetNumberOfPlexCopies(a1);
  v109 = (char *)v17;
  v9 = HsmExpandKernelStackAndCallout((PEXPAND_STACK_CALLOUT)HsmiBitmapNORMALOpenOnDiskCallout, (NTSTATUS *)&Parameter);
  HsmDbgBreakOnStatus(v9);
  if ( v9 < 0 )
  {
    v53 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_78;
    }
    v79 = 133;
    goto LABEL_197;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qisdi(WPP_GLOBAL_Control->AttachedDevice, 134, v116, a1, *(_QWORD *)a1, a1 + 32, v14, v116);
  }
  if ( v14 != -1 )
  {
    v65 = 0;
    v66 = 1 << ((*(_DWORD *)(a1 + 16) >> 6) & 0x3F);
    do
    {
      v67 = HsmiBitmapNORMALComputeGranularity(v65, v66);
      *(_QWORD *)&v114[2 * v68] = v67;
      v65 = v68 + 1;
    }
    while ( v65 < v14 + 1 );
  }
  v96 = a1 + 48;
  FltAcquirePushLockSharedEx(a1 + 48, 0);
  SectorCount = a1 + 56;
  if ( *(_QWORD *)(a1 + 56) )
  {
    if ( ((*(_DWORD *)(a1 + 16) >> 12) & 7) == v14 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 135, v19, a1, *(_QWORD *)a1, a1 + 32);
      }
      v20 = Buffer;
      memmove(Buffer, *(const void **)(a1 + 56), 0x1000u);
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 136, v19, a1, *(_QWORD *)a1, a1 + 32);
    }
    v80 = 255;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 137, v19, a1, *(_QWORD *)a1, a1 + 32);
    }
    v80 = 0;
  }
  v20 = Buffer;
  memset(Buffer, v80, 0x1000u);
LABEL_23:
  if ( *(_QWORD *)SectorCount )
  {
    v21 = (*(_DWORD *)(a1 + 16) >> 12) & 7;
    if ( v14 > v21 )
    {
      v117 = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qisdd(WPP_GLOBAL_Control->AttachedDevice, 138, v21, a1, *(_QWORD *)a1, a1 + 32, v21, v14);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 139, v21, a1, *(_QWORD *)a1, a1 + 32);
      }
      HsmiBitmapNORMALSetNextLevelBlockState(0, v20, 0, 1);
      *((_DWORD *)v20 + 1023) = RtlComputeCrc32(0, v20, 0xFFCu);
      v81 = (_DWORD *)(a1 + 16);
      v82 = (*(_DWORD *)(a1 + 16) >> 12) & 7;
      while ( 1 )
      {
        *(_DWORD *)&v91[3] = v82;
        if ( v82 >= v14 )
          goto LABEL_25;
        Vbn = v82 == ((*v81 >> 12) & 7) ? *(_QWORD *)SectorCount : (__int64)v20;
        v9 = HsmiBitmapNORMALPrepareBlockForWrite((_QWORD *)a1, v82, 0, 0, 4, &Address, &v107);
        v99 = v9;
        HsmDbgBreakOnStatus(v9);
        if ( v9 < 0 )
          break;
        memmove(Address, (const void *)Vbn, 0x1000u);
        v9 = HsmpFileCacheSetAddressRangeModified(Address);
        HsmDbgBreakOnStatus(v9);
        if ( v9 < 0 )
        {
          v83 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v84 = 142;
LABEL_239:
            WPP_SF_qisdd(v83->AttachedDevice, v84, *(_DWORD *)&v91[3], a1, *v92, a1 + 32, v91[3], v9);
          }
LABEL_240:
          v52 = Buffer;
          v54 = v117;
          goto LABEL_80;
        }
        v108 = v107;
        HsmIBitmapNORMALUnpinBlock(&v108);
        LODWORD(v107) = 0;
        Address = 0;
        v82 = *(_DWORD *)&v91[3] + 1;
        v20 = Buffer;
        v81 = v98;
      }
      v83 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v84 = 140;
        goto LABEL_239;
      }
      goto LABEL_240;
    }
  }
LABEL_25:
  FltReleasePushLockEx(v96, 0);
  *(_QWORD *)v112 = -1;
  v91[0] = -1;
  for ( i = *(_QWORD *)(a1 + 136); ; i = *(_QWORD *)(i + 8) )
  {
    v96 = i;
    if ( i == a1 + 128 )
    {
      v23 = *v105;
      if ( v116 > *v105 )
      {
        v104 = 0;
        v115 = 0;
        *(_QWORD *)&v108 = ~(v95 - 1LL);
        v96 = v23 & v108;
        if ( (v23 & (unsigned __int64)v108) != v23 )
        {
          v9 = HsmIBitmapNORMALQueryRangeEx(a1, 7, (unsigned int)&v96, (_DWORD)v111, (__int64)v88, (__int64)&v100);
          HsmDbgBreakOnStatus(v9);
          if ( v9 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 145, v61, a1, *v92, a1 + 32, v9);
            }
            goto LABEL_78;
          }
          if ( !v88[0] || v100 < *v105 )
          {
LABEL_117:
            v9 = -1073741595;
            HsmDbgBreakOnStatus(-1073741595);
            goto LABEL_78;
          }
        }
        v115 = v108 & (v116 - 1 + v95);
        v9 = HsmiBitmapNORMALMarkBitmapOnDisk(
               a1,
               (__int64)v114,
               (__int64)v112,
               (__int64)v91,
               v89,
               &v104,
               Buffer,
               &v96,
               &v115,
               1);
        HsmDbgBreakOnStatus(v9);
        if ( v9 < 0 )
        {
          v73 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v74 = 146;
LABEL_247:
            WPP_SF_qisdd(v73->AttachedDevice, v74, (_DWORD)v73, a1, *v92, a1 + 32, v89, v9);
          }
          goto LABEL_78;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qisdiic(WPP_GLOBAL_Control->AttachedDevice, 147, a1 + 32, a1, *v92, a1 + 32, v89, *v105, v116, 1);
        }
      }
      goto LABEL_28;
    }
    v57 = 0;
LABEL_88:
    *(_DWORD *)&v91[3] = v57;
    if ( v57 < 3 )
      break;
  }
  Vbn = 0;
  Lbn = 0;
  SectorCount = 0;
  v58 = *(BASE_MCB **)(i + 8LL * v57 + 16);
  *(_QWORD *)&v108 = v58;
  v59 = 0;
  while ( 2 )
  {
    v94 = v59;
    if ( !v58 || !FsRtlGetNextBaseMcbEntry(v58, v59, &Vbn, &Lbn, &SectorCount) )
    {
      v57 = *(_DWORD *)&v91[3] + 1;
      i = v96;
      goto LABEL_88;
    }
    v104 = 0;
    if ( Lbn == -1 )
    {
LABEL_101:
      v59 = v94 + 1;
      v20 = Buffer;
      v58 = (BASE_MCB *)v108;
      continue;
    }
    break;
  }
  v106 = Vbn * v95;
  Address = (PVOID)(v106 + SectorCount * v95);
  v60 = v116;
  if ( *v105 > v116 )
    v60 = *v105;
  if ( v106 + SectorCount * v95 > (-(__int64)v95 & (v60 + v95 - 1LL)) )
    goto LABEL_117;
  LOBYTE(v115) = *(_DWORD *)&v91[3] != 2;
  v9 = HsmiBitmapNORMALMarkBitmapOnDisk(
         a1,
         (__int64)v114,
         (__int64)v112,
         (__int64)v91,
         v89,
         &v104,
         v20,
         &v106,
         (__int64 *)&Address,
         *(_DWORD *)&v91[3] != 2);
  HsmDbgBreakOnStatus(v9);
  if ( v9 >= 0 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qisdiic(
        WPP_GLOBAL_Control->AttachedDevice,
        144,
        a1 + 32,
        a1,
        *v92,
        a1 + 32,
        v89,
        v106,
        (char)Address,
        v115);
    }
    goto LABEL_101;
  }
  v73 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v74 = 143;
    goto LABEL_247;
  }
LABEL_78:
  v52 = Buffer;
LABEL_79:
  v54 = 0;
LABEL_80:
  if ( v54 )
  {
    FltReleasePushLockEx(a1 + 48, 0);
    goto LABEL_106;
  }
LABEL_81:
  if ( v52 )
    ExFreePoolWithTag(v52, 0x6D427348u);
  v55 = P;
  if ( P )
  {
    v85 = (void *)*((_QWORD *)P + 2);
    if ( v85 )
      ExFreePoolWithTag(v85, 0x6D427348u);
    ExFreePoolWithTag(v55, 0x63427348u);
  }
  if ( (_DWORD)v107 )
    HsmIBitmapNORMALUnpinBlock(&v107);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140065da4  mov     r11, rsp
0x140065da7  mov     [r11+20h], r9
0x140065dab  mov     [r11+18h], r8b
0x140065daf  mov     [r11+10h], rdx
0x140065db3  mov     [r11+8], rcx
0x140065db7  push    rbx
0x140065db8  push    rsi
0x140065db9  push    rdi
0x140065dba  push    r12
0x140065dbc  push    r13
0x140065dbe  push    r14
0x140065dc0  push    r15
0x140065dc2  sub     rsp, 150h
0x140065dc9  mov     r12, r9
0x140065dcc  mov     r15, rdx
0x140065dcf  mov     rdi, rcx
0x140065dd2  xor     esi, esi
0x140065dd4  mov     [r11-0D8h], rsi
0x140065ddb  mov     [rsp+188h+Buffer], rsi
0x140065de0  mov     [r11-0F0h], rsi
0x140065de7  mov     [r11-98h], rsi
0x140065dee  xor     eax, eax
0x140065df0  mov     [r11-90h], rax
0x140065df7  mov     word ptr [rsp+188h+var_11C], ax
0x140065dfc  mov     byte ptr [rsp+188h+var_11C+2], al
0x140065e00  mov     [rsp+188h+var_120], sil
0x140065e05  mov     [rsp+188h+var_118], sil
0x140065e0a  lea     rax, [rcx+98h]
0x140065e11  mov     [rsp+188h+var_58], rax
0x140065e19  mov     r13, [rax]
0x140065e1c  mov     [rsp+188h+P], r13
0x140065e24  mov     [rsp+188h+Lbn], r13
0x140065e2c  mov     [rax], rsi
0x140065e2f  mov     ebx, [rcx+18h]
0x140065e32  test    ebx, ebx
0x140065e34  js      loc_140066C92
0x140065e3a  lea     rax, [rcx+10h]
0x140065e3e  mov     [rsp+188h+var_E8], rax
0x140065e46  mov     ecx, [rax]
0x140065e48  shr     ecx, 6
0x140065e4b  and     ecx, 3Fh
0x140065e4e  lea     r14d, [rsi+1]
0x140065e52  mov     eax, r14d
0x140065e55  shl     eax, cl
0x140065e57  imul    rcx, rax, 1FF00200h
0x140065e5e  cmp     rdx, rcx
0x140065e61  jg      loc_140066C96
0x140065e67  mov     rcx, [rsp+188h+arg_20]
0x140065e6f  cmp     dword ptr [rcx], 38h ; '8'
0x140065e72  jb      loc_140066C96
0x140065e78  lea     r8, [rsp+188h+var_118]
0x140065e7d  mov     rcx, rdi
0x140065e80  call    HsmIBitmapNORMALMayContainDirtyRange
0x140065e85  mov     ebx, eax
0x140065e87  mov     ecx, eax
0x140065e89  call    HsmDbgBreakOnStatus
0x140065e8e  test    ebx, ebx
0x140065e90  js      loc_140066CA7
0x140065e96  test    r13, r13
0x140065e99  jnz     loc_140066D17
0x140065e9f  lea     edx, [rsi+20h]
0x140065ea2  mov     ecx, 102h
0x140065ea7  mov     r8d, 63427348h
0x140065ead  call    cs:__imp_ExAllocatePool2
0x140065eb4  nop     dword ptr [rax+rax+00h]
0x140065eb9  mov     r13, rax
0x140065ebc  mov     [rsp+188h+P], rax
0x140065ec4  mov     [rsp+188h+Lbn], rax
0x140065ecc  test    r13, r13
0x140065ecf  jz      loc_140066D3A
0x140065ed5  lea     rax, [rdi+10h]
0x140065ed9  mov     [rsp+188h+var_B8], rax
0x140065ee1  mov     [rsp+188h+var_110], rdi
0x140065ee6  xorps   xmm0, xmm0
0x140065ee9  movups  xmmword ptr [r13+0], xmm0
0x140065eee  movups  xmmword ptr [r13+10h], xmm0
0x140065ef3  lea     rdx, [rsp+188h+var_11C]
0x140065ef8  mov     rcx, rdi
0x140065efb  cmp     [rsp+188h+var_118], sil
0x140065f00  jz      loc_140066AE3
0x140065f06  call    HsmiBitmapNORMALPrepareMcbsForCommit
0x140065f0b  mov     ebx, eax
0x140065f0d  mov     ecx, eax
0x140065f0f  call    HsmDbgBreakOnStatus
0x140065f14  test    ebx, ebx
0x140065f16  js      loc_140066B4D
0x140065f1c  mov     edx, 1000h
0x140065f21  mov     ecx, 100h
0x140065f26  mov     r8d, 6D427348h
0x140065f2c  call    cs:__imp_ExAllocatePool2
0x140065f33  nop     dword ptr [rax+rax+00h]
0x140065f38  mov     r15, rax
0x140065f3b  mov     [rsp+188h+Buffer], rax
0x140065f40  mov     [rsp+188h+var_A8], rax
0x140065f48  test    rax, rax
0x140065f4b  jz      loc_140066E30
0x140065f51  lea     rcx, [rdi+8]
0x140065f55  mov     [rsp+188h+var_68], rcx
0x140065f5d  cmp     [rcx], rsi
0x140065f60  jg      loc_14006650A
0x140065f66  mov     [rsp+188h+var_120], r14b
0x140065f6b  mov     [rsp+188h+var_D8], rsi
0x140065f73  mov     r8d, 7
0x140065f79  mov     [rsp+188h+var_B0], rcx
0x140065f81  cmp     [rsp+188h+var_120], sil
0x140065f86  jz      short loc_140065F99
0x140065f88  mov     rax, [rcx]
0x140065f8b  cmp     [rsp+188h+var_D8], rax
0x140065f93  jz      loc_1400667EA
0x140065f99  mov     r15d, [rdi+10h]
0x140065f9d  mov     ecx, r15d
0x140065fa0  shr     ecx, 6
0x140065fa3  and     ecx, 3Fh
0x140065fa6  mov     edx, r14d
0x140065fa9  shl     edx, cl
0x140065fab  mov     [rsp+188h+var_FC], edx
0x140065fb2  shr     r15d, 0Ch
0x140065fb6  and     r15d, r8d
0x140065fb9  mov     [rsp+188h+var_11C], r15d
0x140065fbe  mov     [rsp+188h+var_100], r15d
0x140065fc6  mov     ecx, r15d
0x140065fc9  call    HsmiBitmapNORMALComputeMaxUserFileSize
0x140065fce  mov     rbx, [rsp+188h+arg_8]
0x140065fd6  cmp     rax, rbx
0x140065fd9  jl      loc_140066F22
0x140065fdf  mov     [rsp+188h+Parameter], rsi
0x140065fe7  mov     qword ptr [rsp+188h+var_88], rdi
0x140065fef  mov     dword ptr [rsp+188h+var_88+8], r15d
0x140065ff7  mov     rcx, rdi
0x140065ffa  call    HsmiBitmapNORMALGetNumberOfPlexCopies
0x140065fff  mov     dword ptr [rsp+188h+var_88+0Ch], eax
0x140066006  mov     [rsp+188h+var_78], rbx
0x14006600e  lea     rdx, [rsp+188h+Parameter]; Parameter
0x140066016  lea     rcx, HsmiBitmapNORMALOpenOnDiskCallout; Callout
0x14006601d  call    HsmExpandKernelStackAndCallout
0x140066022  mov     ebx, eax
0x140066024  mov     ecx, eax
0x140066026  call    HsmDbgBreakOnStatus
0x14006602b  test    ebx, ebx
0x14006602d  js      loc_14006656A
0x140066033  lea     r13, WPP_GLOBAL_Control
0x14006603a  mov     rcx, cs:WPP_GLOBAL_Control
0x140066041  cmp     rcx, r13
0x140066044  jnz     loc_1400669DC
0x14006604a  lea     ebx, [r15+1]
0x14006604e  test    ebx, ebx
0x140066050  jnz     loc_140066A95
0x140066056  lea     rax, [rdi+30h]
0x14006605a  mov     [rsp+188h+var_F8], rax
0x140066062  xor     edx, edx
0x140066064  mov     rcx, rax
0x140066067  call    cs:__imp_FltAcquirePushLockSharedEx
0x14006606e  nop     dword ptr [rax+rax+00h]
0x140066073  lea     rbx, [rdi+38h]
0x140066077  mov     [rsp+188h+var_D0], rbx
0x14006607f  mov     rcx, [rbx]
0x140066082  test    rcx, rcx
0x140066085  jz      loc_140066FB2
0x14006608b  mov     eax, [rdi+10h]
0x14006608e  shr     eax, 0Ch
0x140066091  and     eax, 7
0x140066094  cmp     eax, r15d
0x140066097  jnz     loc_140066F6A
0x14006609d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400660a4  cmp     rcx, r13
0x1400660a7  jnz     loc_140066B9D
0x1400660ad  mov     r8d, 1000h; Size
0x1400660b3  mov     rdx, [rbx]; Src
0x1400660b6  mov     rbx, [rsp+188h+Buffer]
0x1400660bb  mov     rcx, rbx; void *
0x1400660be  call    memmove
0x1400660c3  mov     rax, [rsp+188h+var_D0]
0x1400660cb  cmp     [rax], rsi
0x1400660ce  jz      short loc_1400660E5
0x1400660d0  mov     r8d, [rdi+10h]
0x1400660d4  shr     r8d, 0Ch
0x1400660d8  and     r8d, 7
0x1400660dc  cmp     r15d, r8d
0x1400660df  ja      loc_140067008
0x1400660e5  xor     edx, edx
0x1400660e7  mov     rcx, [rsp+188h+var_F8]
0x1400660ef  call    cs:__imp_FltReleasePushLockEx
0x1400660f6  nop     dword ptr [rax+rax+00h]
0x1400660fb  mov     qword ptr [rsp+188h+var_60], 0FFFFFFFFFFFFFFFFh
0x140066107  mov     [rsp+188h+var_117], 0FFh
0x14006610c  mov     rcx, [rdi+88h]
0x140066113  mov     edx, 3
0x140066118  lea     r15d, [rdx-1]
0x14006611c  lea     rax, [rdi+80h]
0x140066123  mov     [rsp+188h+var_F8], rcx
0x14006612b  cmp     rcx, rax
0x14006612e  jnz     loc_1400665C0
0x140066134  mov     rax, [rsp+188h+var_B0]
0x14006613c  mov     rcx, [rax]
0x14006613f  cmp     [rsp+188h+arg_8], rcx
0x140066147  jg      loc_1400668A9
0x14006614d  mov     r8d, 0FFCh; Length
0x140066153  mov     rdx, [rsp+188h+Buffer]; Buffer
0x140066158  xor     ecx, ecx; InitialCrc
0x14006615a  call    cs:__imp_RtlComputeCrc32
0x140066161  nop     dword ptr [rax+rax+00h]
0x140066166  mov     rcx, [rsp+188h+Buffer]
0x14006616b  mov     [rcx+0FFCh], eax
0x140066171  mov     rdx, [rsp+188h+P]
0x140066179  add     rdx, 8
0x14006617d  mov     eax, [rsp+188h+var_11C]
0x140066181  test    eax, eax
0x140066183  jnz     loc_140066785
0x140066189  mov     [rdx], rsi
0x14006618c  lea     ebx, [rax+5]
0x14006618f  mov     rdx, [rsp+188h+P]
0x140066197  mov     [rdx+10h], rcx
0x14006619b  mov     r8d, eax
0x14006619e  xor     r8d, [rdx+18h]
0x1400661a2  and     r8d, 0FFFFFFF8h
0x1400661a6  xor     r8d, eax
0x1400661a9  mov     [rdx+18h], r8d
0x1400661ad  mov     r9, [rsp+188h+arg_8]
0x1400661b5  mov     [rdx], r9
0x1400661b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400661bf  cmp     rcx, r13
0x1400661c2  jnz     loc_140066847
0x1400661c8  mov     r8d, 3
0x1400661ce  mov     qword ptr [r12], 70527442h
0x1400661d6  mov     dword ptr [r12+8], 38h ; '8'
0x1400661df  mov     dword ptr [r12+0Ch], 50000h
0x1400661e8  xorps   xmm0, xmm0
0x1400661eb  xor     eax, eax
0x1400661ed  movups  xmmword ptr [r12+10h], xmm0
0x1400661f3  movups  xmmword ptr [r12+20h], xmm0
0x1400661f9  mov     [r12+30h], rax
0x1400661fe  mov     rax, [rsp+188h+arg_20]
0x140066206  mov     eax, [rax]
0x140066208  cmp     eax, 18h
0x14006620b  jb      loc_140066C0A
0x140066211  cmp     si, bx
0x140066214  jnb     loc_140067599
0x14006621a  mov     edx, [r12+8]
0x14006621f  lea     rcx, [r8+rdx]
0x140066223  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140066227  add     rcx, r14
0x14006622a  cmp     rcx, rax
0x14006622d  ja      loc_140066C0A
0x140066233  lea     eax, [rdx+3]
0x140066236  and     eax, 0FFFFFFFCh
0x140066239  mov     ecx, eax
0x14006623b  mov     [r12+8], ecx
0x140066240  mov     dword ptr [r12+10h], 10007h
0x140066249  mov     [r12+14h], ecx
0x14006624e  mov     [rax+r12], r14b
0x140066252  add     [r12+8], r14d
0x140066257  mov     ebx, esi
0x140066259  mov     ecx, ebx
0x14006625b  call    HsmDbgBreakOnStatus
0x140066260  test    ebx, ebx
0x140066262  js      loc_140066B29
0x140066268  mov     rax, [rsp+188h+arg_20]
0x140066270  mov     eax, [rax]
0x140066272  cmp     eax, 18h
0x140066275  jnb     loc_140066966
0x14006627b  mov     ebx, 0C0000023h
0x140066280  mov     ecx, ebx
0x140066282  call    HsmDbgBreakOnStatus
0x140066287  test    ebx, ebx
0x140066289  js      loc_140066C28
0x14006628f  mov     rax, [rsp+188h+arg_20]
0x140066297  mov     eax, [rax]
0x140066299  cmp     eax, 18h
0x14006629c  jb      loc_140066C14
0x1400662a2  mov     rdx, [rsp+188h+P]
0x1400662aa  mov     edx, [rdx+18h]
0x1400662ad  shl     edx, 1Dh
0x1400662b0  sar     edx, 1Dh
0x1400662b3  cmp     r15w, [r12+0Eh]
0x1400662b9  jnb     loc_1400675DD
0x1400662bf  cmp     eax, 28h ; '('
0x1400662c2  jb      loc_140066C14
0x1400662c8  mov     r8d, [r12+8]
0x1400662cd  lea     rcx, [r8+3]
0x1400662d1  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400662d5  add     rcx, r14
0x1400662d8  cmp     rcx, rax
0x1400662db  ja      loc_140066C14
0x1400662e1  lea     eax, [r8+3]
0x1400662e5  and     eax, 0FFFFFFFCh
0x1400662e8  mov     [r12+8], eax
0x1400662ed  cmp     [r12+20h], si
0x1400662f3  jz      short loc_1400662FB
0x1400662f5  or      [r12+0Ch], r14w
0x1400662fb  mov     dword ptr [r12+20h], 10007h
0x140066304  mov     [r12+24h], eax
0x140066309  mov     [rax+r12], dl
0x14006630d  add     [r12+8], r14d
0x140066312  mov     ebx, esi
0x140066314  mov     ecx, ebx
0x140066316  call    HsmDbgBreakOnStatus
0x14006631b  test    ebx, ebx
0x14006631d  js      loc_140066C58
0x140066323  mov     rax, [rsp+188h+arg_20]
0x14006632b  mov     eax, [rax]
  ... truncated ...
```
