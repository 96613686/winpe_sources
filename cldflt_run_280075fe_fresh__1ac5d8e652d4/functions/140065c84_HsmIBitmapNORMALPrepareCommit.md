# HsmIBitmapNORMALPrepareCommit

- ea: `0x140065c84`
- end: `0x140067609`
- name: `HsmIBitmapNORMALPrepareCommit`
- size: `6533`
- prototype: `__int64 __usercall@<rax>(int@<ecx>, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `broker_com_uri`

## callers

- `0x140067854`

## callees

- `0x140003c50`
- `0x140008b74`
- `0x140009c7c`
- `0x140009d14`
- `0x14000a120`
- `0x14000d95c`
- `0x14001886c`
- `0x1400189dc`
- `0x140018e90`
- `0x140019280`
- `0x1400196f4`
- `0x140019d04`
- `0x140019f10`
- `0x14001b85c`
- `0x14001e280`
- `0x14001e580`
- `0x140036400`
- `0x140065130`
- `0x140065c84`
- `0x140067610`
- `0x1400676bc`
- `0x1400677b4`
- `0x140071bb8`
- `0x140072eec`
- `0x140075f34`
- `0x140078c58`
- `0x140085144`

## import_xrefs

- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140066506`
- `ntoskrnl!FsRtlGetNextBaseMcbEntry` at `0x140066506`
- `ntoskrnl!RtlComputeCrc32` at `0x14006603a`
- `ntoskrnl!RtlComputeCrc32` at `0x140066f8d`
- `ntoskrnl!RtlComputeCrc32` at `0x14006603a`
- `ntoskrnl!RtlComputeCrc32` at `0x140066f8d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006758f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400675ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400675c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140066c09`
- `ntoskrnl!ExFreePoolWithTag` at `0x14006758f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400675ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400675c2`
- `ntoskrnl!ExAllocatePool2` at `0x140065d8d`
- `ntoskrnl!ExAllocatePool2` at `0x140065e0c`
- `ntoskrnl!ExAllocatePool2` at `0x140065d8d`
- `ntoskrnl!ExAllocatePool2` at `0x140065e0c`
- `FLTMGR!FltReleasePushLockEx` at `0x140065fcf`
- `FLTMGR!FltReleasePushLockEx` at `0x140067576`
- `FLTMGR!FltReleasePushLockEx` at `0x140065fcf`
- `FLTMGR!FltReleasePushLockEx` at `0x140067576`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140065f47`
- `FLTMGR!FltAcquirePushLockSharedEx` at `0x140065f47`

## pseudocode

```c
__int64 __fastcall HsmIBitmapNORMALPrepareCommit(__int64 a1, __int64 a2, char a3, __int64 a4, _DWORD *a5)
{
  _OWORD *Pool2; // r13
  __int64 v9; // rbx
  int v10; // r8d
  UCHAR *v11; // r15
  __int64 *v12; // rcx
  unsigned int v13; // r15d
  unsigned int v14; // r15d
  __int64 v15; // rax
  __int64 v16; // rbx
  int v17; // r8d
  int v18; // r8d
  PUCHAR v19; // rbx
  unsigned int v20; // r8d
  __int64 i; // rcx
  __int64 v22; // rcx
  ULONG v23; // eax
  PUCHAR v24; // rcx
  int v25; // eax
  _DWORD *v26; // rdx
  unsigned int v27; // r8d
  char v28; // r9
  unsigned __int64 v29; // rax
  __int64 v30; // rdx
  unsigned int v31; // ecx
  int v32; // r8d
  unsigned __int64 v33; // rax
  unsigned __int64 v34; // rax
  int v35; // edx
  __int64 v36; // r8
  __int64 v37; // rax
  unsigned __int64 v38; // rax
  __int64 v39; // r9
  __int64 v40; // r8
  __int64 v41; // rax
  _DWORD *v42; // r10
  _DWORD *v43; // rdx
  _DWORD *v44; // rcx
  unsigned __int64 v45; // rax
  size_t v46; // r8
  size_t v47; // r9
  __int64 v48; // r10
  __int64 v49; // rcx
  _DWORD *v50; // rcx
  PUCHAR v51; // rax
  PDEVICE_OBJECT v52; // rcx
  char v53; // cl
  PVOID v54; // rdi
  int v56; // eax
  BASE_MCB *v57; // rcx
  ULONG v58; // eax
  __int64 v59; // rcx
  int v60; // r8d
  char v61; // dl
  __int64 v62; // r8
  __int64 v63; // rax
  unsigned int v64; // r10d
  unsigned int v65; // r11d
  __int64 v66; // rax
  int v67; // r10d
  PDEVICE_OBJECT v68; // rcx
  int v69; // r8d
  int v70; // edx
  PDEVICE_OBJECT v71; // rcx
  PDEVICE_OBJECT v72; // r8
  int v73; // edx
  __int64 v74; // rcx
  int v75; // edx
  void *v76; // rcx
  int v77; // r8d
  int v78; // edx
  int v79; // edx
  _DWORD *v80; // rax
  unsigned int v81; // ecx
  PDEVICE_OBJECT v82; // rcx
  int v83; // edx
  void *v84; // rcx
  char v85; // [rsp+30h] [rbp-158h]
  PUCHAR Buffer; // [rsp+60h] [rbp-128h]
  _BYTE v87[4]; // [rsp+68h] [rbp-120h] BYREF
  int v88; // [rsp+6Ch] [rbp-11Ch] BYREF
  char v89; // [rsp+70h] [rbp-118h] BYREF
  _BYTE v90[7]; // [rsp+71h] [rbp-117h] BYREF
  _QWORD *v91; // [rsp+78h] [rbp-110h]
  PVOID P; // [rsp+80h] [rbp-108h]
  unsigned int v93; // [rsp+88h] [rbp-100h]
  unsigned int v94; // [rsp+8Ch] [rbp-FCh]
  __int64 v95; // [rsp+90h] [rbp-F8h] BYREF
  PVOID Address; // [rsp+98h] [rbp-F0h] BYREF
  _DWORD *v97; // [rsp+A0h] [rbp-E8h]
  int v98; // [rsp+A8h] [rbp-E0h]
  __int64 v99; // [rsp+B0h] [rbp-D8h] BYREF
  __int64 SectorCount; // [rsp+B8h] [rbp-D0h] BYREF
  __int64 Vbn; // [rsp+C0h] [rbp-C8h] BYREF
  __int64 Lbn; // [rsp+C8h] [rbp-C0h] BYREF
  __int64 v103; // [rsp+D0h] [rbp-B8h] BYREF
  __int64 *v104; // [rsp+D8h] [rbp-B0h]
  __int64 v105; // [rsp+E0h] [rbp-A8h] BYREF
  __int128 v106; // [rsp+F0h] [rbp-98h] BYREF
  __int128 v107; // [rsp+100h] [rbp-88h] BYREF
  char *v108; // [rsp+110h] [rbp-78h]
  __int64 Parameter; // [rsp+118h] [rbp-70h] BYREF
  __int64 *v110; // [rsp+120h] [rbp-68h]
  int v111[2]; // [rsp+128h] [rbp-60h] BYREF
  PVOID *v112; // [rsp+130h] [rbp-58h]
  int v113[2]; // [rsp+138h] [rbp-50h] BYREF
  __int64 v114; // [rsp+190h] [rbp+8h] BYREF
  __int64 v115; // [rsp+198h] [rbp+10h]
  char v116; // [rsp+1A0h] [rbp+18h]
  __int64 v117; // [rsp+1A8h] [rbp+20h]

  v117 = a4;
  v116 = a3;
  v115 = a2;
  v114 = a1;
  v99 = 0;
  Buffer = 0;
  Address = 0;
  v106 = 0u;
  LOWORD(v88) = 0;
  BYTE2(v88) = 0;
  v87[0] = 0;
  v89 = 0;
  v112 = (PVOID *)(a1 + 152);
  Pool2 = *(_OWORD **)(a1 + 152);
  P = Pool2;
  Lbn = (__int64)Pool2;
  *(_QWORD *)(a1 + 152) = 0;
  LODWORD(v9) = *(_DWORD *)(a1 + 24);
  if ( (int)v9 < 0 )
  {
    v74 = (unsigned int)v9;
LABEL_171:
    HsmDbgBreakOnStatus(v74);
    goto LABEL_145;
  }
  v97 = (_DWORD *)(a1 + 16);
  if ( a2 > 535822848LL * (unsigned int)(1 << ((*(_DWORD *)(a1 + 16) >> 6) & 0x3F)) || *a5 < 0x38u )
  {
    v74 = 3221225701LL;
    LODWORD(v9) = -1073741595;
    goto LABEL_171;
  }
  v9 = (unsigned int)HsmIBitmapNORMALMayContainDirtyRange(a1, a2, &v89);
  HsmDbgBreakOnStatus(v9);
  if ( (int)v9 < 0 )
  {
    v71 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_145;
    }
    v75 = 125;
LABEL_176:
    WPP_SF_qisd(v71->AttachedDevice, v75, v10, a1, *(_QWORD *)a1, a1 + 32, v9);
    goto LABEL_145;
  }
  if ( Pool2 )
  {
    v76 = (void *)*((_QWORD *)Pool2 + 2);
    if ( v76 )
      ExFreePoolWithTag(v76, 0x6D427348u);
  }
  else
  {
    Pool2 = (_OWORD *)ExAllocatePool2(258, 32, 1665299272);
    P = Pool2;
    Lbn = (__int64)Pool2;
  }
  if ( !Pool2 )
  {
    LODWORD(v9) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 126, v77, a1, *(_QWORD *)a1, a1 + 32, 154);
    }
    goto LABEL_145;
  }
  v103 = a1 + 16;
  v91 = (_QWORD *)a1;
  *Pool2 = 0;
  Pool2[1] = 0;
  if ( !v89 )
  {
    LOWORD(v88) = 257;
    v9 = (unsigned int)HsmiBitmapNORMALPrepareMcbsForCommit(a1, &v88);
    HsmDbgBreakOnStatus(v9);
    if ( (int)v9 >= 0 )
    {
      *(_QWORD *)Pool2 = a2;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 128, v69, a1, *(_QWORD *)a1, a1 + 32);
      }
LABEL_31:
      *(_QWORD *)a4 = 1884451906;
      *(_DWORD *)(a4 + 8) = 56;
      *(_DWORD *)(a4 + 12) = 327680;
      *(_OWORD *)(a4 + 16) = 0;
      *(_OWORD *)(a4 + 32) = 0;
      *(_QWORD *)(a4 + 48) = 0;
      v29 = (unsigned int)*a5;
      if ( (unsigned int)v29 < 0x18 || (v30 = *(unsigned int *)(a4 + 8), ((v30 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v29) )
      {
        LODWORD(v9) = -1073741789;
      }
      else
      {
        v31 = (v30 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(a4 + 8) = v31;
        *(_DWORD *)(a4 + 16) = 65543;
        *(_DWORD *)(a4 + 20) = v31;
        *(_BYTE *)(v31 + a4) = 1;
        ++*(_DWORD *)(a4 + 8);
        LODWORD(v9) = 0;
      }
      HsmDbgBreakOnStatus((unsigned int)v9);
      if ( (int)v9 < 0 )
      {
        v68 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_136;
        }
        v70 = 151;
        goto LABEL_265;
      }
      v33 = (unsigned int)*a5;
      if ( (unsigned int)v33 < 0x18 )
        goto LABEL_36;
      v61 = (*v97 >> 6) & 0x3F;
      if ( *(_WORD *)(a4 + 14) <= 1u )
      {
        LODWORD(v9) = -1073741811;
      }
      else
      {
        if ( (unsigned int)v33 < 0x20
          || (v62 = *(unsigned int *)(a4 + 8), ((v62 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 > v33) )
        {
LABEL_36:
          LODWORD(v9) = -1073741789;
          goto LABEL_37;
        }
        v63 = ((_DWORD)v62 + 3) & 0xFFFFFFFC;
        *(_DWORD *)(a4 + 8) = v63;
        if ( *(_WORD *)(a4 + 24) )
          *(_WORD *)(a4 + 12) |= 1u;
        *(_DWORD *)(a4 + 24) = 65543;
        *(_DWORD *)(a4 + 28) = v63;
        *(_BYTE *)(v63 + a4) = v61;
        ++*(_DWORD *)(a4 + 8);
        LODWORD(v9) = 0;
      }
LABEL_37:
      HsmDbgBreakOnStatus((unsigned int)v9);
      if ( (int)v9 < 0 )
      {
        v68 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_136;
        }
        v70 = 152;
        goto LABEL_265;
      }
      v34 = (unsigned int)*a5;
      if ( (unsigned int)v34 >= 0x18 )
      {
        v35 = (int)(*((_DWORD *)P + 6) << 29) >> 29;
        if ( *(_WORD *)(a4 + 14) <= 2u )
        {
          LODWORD(v9) = -1073741811;
          goto LABEL_45;
        }
        if ( (unsigned int)v34 >= 0x28 )
        {
          v36 = *(unsigned int *)(a4 + 8);
          if ( ((v36 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 1 <= v34 )
          {
            v37 = ((_DWORD)v36 + 3) & 0xFFFFFFFC;
            *(_DWORD *)(a4 + 8) = v37;
            if ( *(_WORD *)(a4 + 32) )
              *(_WORD *)(a4 + 12) |= 1u;
            *(_DWORD *)(a4 + 32) = 65543;
            *(_DWORD *)(a4 + 36) = v37;
            *(_BYTE *)(v37 + a4) = v35;
            ++*(_DWORD *)(a4 + 8);
            LODWORD(v9) = 0;
LABEL_45:
            HsmDbgBreakOnStatus((unsigned int)v9);
            if ( (int)v9 < 0 )
            {
              v68 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
              {
                goto LABEL_136;
              }
              v70 = 153;
              goto LABEL_265;
            }
            v38 = (unsigned int)*a5;
            if ( (unsigned int)v38 >= 0x18 )
            {
              v39 = *((_QWORD *)P + 1);
              if ( *(_WORD *)(a4 + 14) <= 3u )
              {
                LODWORD(v9) = -1073741811;
                goto LABEL_53;
              }
              if ( (unsigned int)v38 >= 0x30 )
              {
                v40 = *(unsigned int *)(a4 + 8);
                if ( ((v40 + 3) & 0xFFFFFFFFFFFFFFFCuLL) + 8 <= v38 )
                {
                  v41 = ((_DWORD)v40 + 3) & 0xFFFFFFFC;
                  *(_DWORD *)(a4 + 8) = v41;
                  if ( *(_WORD *)(a4 + 40) )
                    *(_WORD *)(a4 + 12) |= 1u;
                  *(_DWORD *)(a4 + 40) = 524294;
                  *(_DWORD *)(a4 + 44) = v41;
                  *(_QWORD *)(v41 + a4) = v39;
                  *(_DWORD *)(a4 + 8) += 8;
                  LODWORD(v9) = 0;
LABEL_53:
                  HsmDbgBreakOnStatus((unsigned int)v9);
                  if ( (int)v9 < 0 )
                  {
                    v68 = WPP_GLOBAL_Control;
                    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                    {
                      goto LABEL_136;
                    }
                    v70 = 154;
                    goto LABEL_265;
                  }
                  v42 = P;
                  v43 = (_DWORD *)*((_QWORD *)P + 2);
                  if ( !v43 )
                    goto LABEL_69;
                  v44 = v43 + 1023;
                  if ( v43 + 1023 >= v43 )
                  {
                    do
                    {
                      v45 = (unsigned __int64)(v44 - 1);
                      if ( *(v44 - 1) != v43[1022] )
                        break;
                      --v44;
                    }
                    while ( v45 > (unsigned __int64)v43 );
                  }
                  v46 = (unsigned int)*a5;
                  if ( (unsigned int)v46 >= 0x18 )
                  {
                    if ( *(_WORD *)(a4 + 14) <= 4u )
                    {
                      LODWORD(v9) = -1073741811;
                      goto LABEL_67;
                    }
                    if ( (unsigned int)v46 >= 0x38 )
                    {
                      v47 = (unsigned __int16)((_WORD)v44 - *((_WORD *)P + 8) + 4);
                      v48 = *(unsigned int *)(a4 + 8);
                      if ( v47 + ((v48 + 3) & 0xFFFFFFFFFFFFFFFCuLL) <= v46 )
                      {
                        if ( *(_WORD *)(a4 + 48) )
                          *(_WORD *)(a4 + 12) |= 1u;
                        v49 = ((_DWORD)v48 + 3) & 0xFFFFFFFC;
                        *(_DWORD *)(a4 + 8) = v49;
                        *(_WORD *)(a4 + 48) = 17;
                        *(_WORD *)(a4 + 50) = v47;
                        *(_DWORD *)(a4 + 52) = v49;
                        v50 = (_DWORD *)(a4 + v49);
                        if ( v50 != v43 )
                          memmove(v50, v43, v47);
                        *(_DWORD *)(a4 + 8) += *(unsigned __int16 *)(a4 + 50);
                        LODWORD(v9) = 0;
                        goto LABEL_67;
                      }
                    }
                  }
                  LODWORD(v9) = -1073741789;
LABEL_67:
                  HsmDbgBreakOnStatus((unsigned int)v9);
                  if ( (int)v9 >= 0 )
                  {
                    v42 = P;
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
                        (int)(v42[6] << 29) >> 29,
                        a1,
                        *v91,
                        a1 + 32,
                        (*v97 >> 6) & 0x3F,
                        *(_QWORD *)(a1 + 144),
                        *((_QWORD *)v42 + 1),
                        (*v97 >> 12) & 7,
                        (int)(v42[6] << 29) >> 29);
                    }
                    *v112 = P;
                    P = 0;
                    v51 = 0;
                    Buffer = 0;
                    goto LABEL_79;
                  }
                  v68 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
                    || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
                  {
LABEL_136:
                    v51 = 0;
                    goto LABEL_81;
                  }
                  v70 = 155;
LABEL_265:
                  WPP_SF_qisd(v68->AttachedDevice, v70, v32, a1, *v91, a1 + 32, v9);
                  goto LABEL_136;
                }
              }
            }
            LODWORD(v9) = -1073741789;
            goto LABEL_53;
          }
        }
      }
      LODWORD(v9) = -1073741789;
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
    v51 = 0;
    goto LABEL_79;
  }
  v9 = (unsigned int)HsmiBitmapNORMALPrepareMcbsForCommit(a1, &v88);
  HsmDbgBreakOnStatus(v9);
  if ( (int)v9 < 0 )
  {
    v71 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_145;
    }
    v75 = 129;
    goto LABEL_176;
  }
  v11 = (UCHAR *)ExAllocatePool2(256, 4096, 1833071432);
  Buffer = v11;
  v105 = (__int64)v11;
  if ( !v11 )
  {
    LODWORD(v9) = -1073741670;
    HsmDbgBreakOnStatus(3221225626LL);
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_78;
      v78 = 130;
      v85 = -102;
      goto LABEL_198;
    }
    goto LABEL_110;
  }
  v12 = (__int64 *)(a1 + 8);
  v110 = (__int64 *)(a1 + 8);
  if ( *(__int64 *)(a1 + 8) > 0 && (*(_DWORD *)(a1 + 16) & 0x10) == 0 )
  {
    v95 = 0;
    v9 = (unsigned int)HsmIBitmapNORMALQueryRangeEx(a1, 7, (unsigned int)&v95, (int)a1 + 8, (__int64)v87, (__int64)&v99);
    HsmDbgBreakOnStatus(v9);
    if ( (int)v9 >= 0 )
    {
      v12 = v110;
      goto LABEL_13;
    }
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        goto LABEL_78;
      v78 = 131;
LABEL_197:
      v85 = v9;
LABEL_198:
      WPP_SF_qisd(v52->AttachedDevice, v78, v17, a1, *(_QWORD *)a1, a1 + 32, v85);
      goto LABEL_78;
    }
LABEL_110:
    v51 = v11;
    goto LABEL_79;
  }
  v87[0] = 1;
  v99 = 0;
LABEL_13:
  v104 = v12;
  if ( v87[0] && v99 == *v12 )
  {
    v88 = 0;
    *((_DWORD *)Pool2 + 6) |= 8u;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 132, 7, a1, *(_QWORD *)a1, a1 + 32);
    }
    memset(v11, 255, 0x1000u);
LABEL_28:
    v23 = RtlComputeCrc32(0, Buffer, 0xFFCu);
    v24 = Buffer;
    *((_DWORD *)Buffer + 1023) = v23;
    v25 = v88;
    if ( !v88 )
    {
      *((_QWORD *)P + 1) = 0;
LABEL_30:
      v26 = P;
      *((_QWORD *)P + 2) = v24;
      v27 = v25 ^ (v26[6] ^ v25) & 0xFFFFFFF8;
      v26[6] = v27;
      v28 = v115;
      *(_QWORD *)v26 = v115;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_qisddi(
          WPP_GLOBAL_Control->AttachedDevice,
          (*v97 >> 6) & 0x3F,
          (int)(v27 << 29) >> 29,
          a1,
          *v91,
          a1 + 32,
          (*v97 >> 6) & 0x3F,
          (int)(v27 << 29) >> 29,
          v28);
      }
      goto LABEL_31;
    }
    Parameter = 0;
    *(_QWORD *)&v107 = a1;
    *((_QWORD *)&v107 + 1) = (unsigned int)v88;
    v108 = (char *)P + 8;
    v9 = (unsigned int)HsmExpandKernelStackAndCallout(HsmiBitmapNORMALFlushBitmapOnDiskCallout, &Parameter);
    HsmDbgBreakOnStatus(v9);
    if ( (int)v9 >= 0 )
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
          *v91,
          a1 + 32,
          (*v97 >> 6) & 0x3F,
          *((_QWORD *)P + 1));
      }
      v24 = Buffer;
      v25 = v88;
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
    v51 = Buffer;
    goto LABEL_81;
  }
  v13 = *(_DWORD *)(a1 + 16);
  v94 = 1 << ((v13 >> 6) & 0x3F);
  v14 = (v13 >> 12) & 7;
  v88 = v14;
  v93 = v14;
  v15 = HsmiBitmapNORMALComputeMaxUserFileSize(v14);
  v16 = v115;
  if ( v15 < v115 )
  {
    do
      v93 = ++v14;
    while ( HsmiBitmapNORMALComputeMaxUserFileSize(v14) < v16 );
    v88 = v14;
  }
  Parameter = 0;
  *(_QWORD *)&v107 = a1;
  DWORD2(v107) = v14;
  HIDWORD(v107) = HsmiBitmapNORMALGetNumberOfPlexCopies(a1);
  v108 = (char *)v16;
  v9 = (unsigned int)HsmExpandKernelStackAndCallout(HsmiBitmapNORMALOpenOnDiskCallout, &Parameter);
  HsmDbgBreakOnStatus(v9);
  if ( (int)v9 < 0 )
  {
    v52 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      goto LABEL_78;
    }
    v78 = 133;
    goto LABEL_197;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qisdi(WPP_GLOBAL_Control->AttachedDevice, 134, v115, a1, *(_QWORD *)a1, a1 + 32, v14, v115);
  }
  if ( v14 != -1 )
  {
    v64 = 0;
    v65 = 1 << ((*(_DWORD *)(a1 + 16) >> 6) & 0x3F);
    do
    {
      v66 = HsmiBitmapNORMALComputeGranularity(v64, v65);
      *(_QWORD *)&v113[2 * v67] = v66;
      v64 = v67 + 1;
    }
    while ( v64 < v14 + 1 );
  }
  v95 = a1 + 48;
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
        WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 135, v18, a1, *(_QWORD *)a1, a1 + 32);
      }
      v19 = Buffer;
      memmove(Buffer, *(const void **)(a1 + 56), 0x1000u);
      goto LABEL_23;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 136, v18, a1, *(_QWORD *)a1, a1 + 32);
    }
    v79 = 255;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 137, v18, a1, *(_QWORD *)a1, a1 + 32);
    }
    v79 = 0;
  }
  v19 = Buffer;
  memset(Buffer, v79, 0x1000u);
LABEL_23:
  if ( *(_QWORD *)SectorCount )
  {
    v20 = (*(_DWORD *)(a1 + 16) >> 12) & 7;
    if ( v14 > v20 )
    {
      v116 = 1;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qisdd(WPP_GLOBAL_Control->AttachedDevice, 138, v20, a1, *(_QWORD *)a1, a1 + 32, v20, v14);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
      {
        WPP_SF_qis(WPP_GLOBAL_Control->AttachedDevice, 139, v20, a1, *(_QWORD *)a1, a1 + 32);
      }
      HsmiBitmapNORMALSetNextLevelBlockState(0, v19, 0, 1);
      *((_DWORD *)v19 + 1023) = RtlComputeCrc32(0, v19, 0xFFCu);
      v80 = (_DWORD *)(a1 + 16);
      v81 = (*(_DWORD *)(a1 + 16) >> 12) & 7;
      while ( 1 )
      {
        *(_DWORD *)&v90[3] = v81;
        if ( v81 >= v14 )
          goto LABEL_25;
        Vbn = v81 == ((*v80 >> 12) & 7) ? *(_QWORD *)SectorCount : (__int64)v19;
        LODWORD(v9) = HsmiBitmapNORMALPrepareBlockForWrite(a1, v81, 0, 0, 4, (__int64)&Address, (__int64)&v106);
        v98 = v9;
        HsmDbgBreakOnStatus((unsigned int)v9);
        if ( (int)v9 < 0 )
          break;
        memmove(Address, (const void *)Vbn, 0x1000u);
        v9 = (unsigned int)HsmpFileCacheSetAddressRangeModified(Address);
        HsmDbgBreakOnStatus(v9);
        if ( (int)v9 < 0 )
        {
          v82 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v83 = 142;
LABEL_239:
            WPP_SF_qisdd(v82->AttachedDevice, v83, *(_DWORD *)&v90[3], a1, *v91, a1 + 32, v90[3], v9);
          }
LABEL_240:
          v51 = Buffer;
          v53 = v116;
          goto LABEL_80;
        }
        v107 = v106;
        HsmIBitmapNORMALUnpinBlock(&v107);
        LODWORD(v106) = 0;
        Address = 0;
        v81 = *(_DWORD *)&v90[3] + 1;
        v19 = Buffer;
        v80 = v97;
      }
      v82 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v83 = 140;
        goto LABEL_239;
      }
      goto LABEL_240;
    }
  }
LABEL_25:
  FltReleasePushLockEx(v95, 0);
  *(_QWORD *)v111 = -1;
  v90[0] = -1;
  for ( i = *(_QWORD *)(a1 + 136); ; i = *(_QWORD *)(i + 8) )
  {
    v95 = i;
    if ( i == a1 + 128 )
    {
      v22 = *v104;
      if ( v115 > *v104 )
      {
        v103 = 0;
        v114 = 0;
        *(_QWORD *)&v107 = ~(v94 - 1LL);
        v95 = v22 & v107;
        if ( (v22 & (unsigned __int64)v107) != v22 )
        {
          v9 = (unsigned int)HsmIBitmapNORMALQueryRangeEx(
                               a1,
                               7,
                               (unsigned int)&v95,
                               (_DWORD)v110,
                               (__int64)v87,
                               (__int64)&v99);
          HsmDbgBreakOnStatus(v9);
          if ( (int)v9 < 0 )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
            {
              WPP_SF_qisd(WPP_GLOBAL_Control->AttachedDevice, 145, v60, a1, *v91, a1 + 32, v9);
            }
            goto LABEL_78;
          }
          if ( !v87[0] || v99 < *v104 )
          {
LABEL_117:
            LODWORD(v9) = -1073741595;
            HsmDbgBreakOnStatus(3221225701LL);
            goto LABEL_78;
          }
        }
        v114 = v107 & (v115 - 1 + v94);
        v9 = (unsigned int)HsmiBitmapNORMALMarkBitmapOnDisk(
                             a1,
                             (int)v113,
                             (int)v111,
                             (int)v90,
                             v88,
                             (__int64)&v103,
                             Buffer,
                             (__int64)&v95,
                             (__int64)&v114,
                             1);
        HsmDbgBreakOnStatus(v9);
        if ( (int)v9 < 0 )
        {
          v72 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            v73 = 146;
LABEL_247:
            WPP_SF_qisdd(v72->AttachedDevice, v73, (_DWORD)v72, a1, *v91, a1 + 32, v88, v9);
          }
          goto LABEL_78;
        }
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qisdiic(WPP_GLOBAL_Control->AttachedDevice, 147, a1 + 32, a1, *v91, a1 + 32, v88, *v104, v115, 1);
        }
      }
      goto LABEL_28;
    }
    v56 = 0;
LABEL_88:
    *(_DWORD *)&v90[3] = v56;
    if ( v56 < 3 )
      break;
  }
  Vbn = 0;
  Lbn = 0;
  SectorCount = 0;
  v57 = *(BASE_MCB **)(i + 8LL * v56 + 16);
  *(_QWORD *)&v107 = v57;
  v58 = 0;
  while ( 2 )
  {
    v93 = v58;
    if ( !v57 || !FsRtlGetNextBaseMcbEntry(v57, v58, &Vbn, &Lbn, &SectorCount) )
    {
      v56 = *(_DWORD *)&v90[3] + 1;
      i = v95;
      goto LABEL_88;
    }
    v103 = 0;
    if ( Lbn == -1 )
    {
LABEL_101:
      v58 = v93 + 1;
      v19 = Buffer;
      v57 = (BASE_MCB *)v107;
      continue;
    }
    break;
  }
  v105 = Vbn * v94;
  Address = (PVOID)(v105 + SectorCount * v94);
  v59 = v115;
  if ( *v104 > v115 )
    v59 = *v104;
  if ( v105 + SectorCount * v94 > (-(__int64)v94 & (v59 + v94 - 1LL)) )
    goto LABEL_117;
  LOBYTE(v114) = *(_DWORD *)&v90[3] != 2;
  v9 = (unsigned int)HsmiBitmapNORMALMarkBitmapOnDisk(
                       a1,
                       (int)v113,
                       (int)v111,
                       (int)v90,
                       v88,
                       (__int64)&v103,
                       v19,
                       (__int64)&v105,
                       (__int64)&Address,
                       *(_DWORD *)&v90[3] != 2);
  HsmDbgBreakOnStatus(v9);
  if ( (int)v9 >= 0 )
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
        *v91,
        a1 + 32,
        v88,
        v105,
        (char)Address,
        v114);
    }
    goto LABEL_101;
  }
  v72 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    v73 = 143;
    goto LABEL_247;
  }
LABEL_78:
  v51 = Buffer;
LABEL_79:
  v53 = 0;
LABEL_80:
  if ( v53 )
  {
    FltReleasePushLockEx(a1 + 48, 0);
    goto LABEL_106;
  }
LABEL_81:
  if ( v51 )
    ExFreePoolWithTag(v51, 0x6D427348u);
  v54 = P;
  if ( P )
  {
    v84 = (void *)*((_QWORD *)P + 2);
    if ( v84 )
      ExFreePoolWithTag(v84, 0x6D427348u);
    ExFreePoolWithTag(v54, 0x63427348u);
  }
  if ( (_DWORD)v106 )
    HsmIBitmapNORMALUnpinBlock(&v106);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140065c84  mov     r11, rsp
0x140065c87  mov     [r11+20h], r9
0x140065c8b  mov     [r11+18h], r8b
0x140065c8f  mov     [r11+10h], rdx
0x140065c93  mov     [r11+8], rcx
0x140065c97  push    rbx
0x140065c98  push    rsi
0x140065c99  push    rdi
0x140065c9a  push    r12
0x140065c9c  push    r13
0x140065c9e  push    r14
0x140065ca0  push    r15
0x140065ca2  sub     rsp, 150h
0x140065ca9  mov     r12, r9
0x140065cac  mov     r15, rdx
0x140065caf  mov     rdi, rcx
0x140065cb2  xor     esi, esi
0x140065cb4  mov     [r11-0D8h], rsi
0x140065cbb  mov     [rsp+188h+Buffer], rsi
0x140065cc0  mov     [r11-0F0h], rsi
0x140065cc7  mov     [r11-98h], rsi
0x140065cce  xor     eax, eax
0x140065cd0  mov     [r11-90h], rax
0x140065cd7  mov     word ptr [rsp+188h+var_11C], ax
0x140065cdc  mov     byte ptr [rsp+188h+var_11C+2], al
0x140065ce0  mov     [rsp+188h+var_120], sil
0x140065ce5  mov     [rsp+188h+var_118], sil
0x140065cea  lea     rax, [rcx+98h]
0x140065cf1  mov     [rsp+188h+var_58], rax
0x140065cf9  mov     r13, [rax]
0x140065cfc  mov     [rsp+188h+P], r13
0x140065d04  mov     [rsp+188h+Lbn], r13
0x140065d0c  mov     [rax], rsi
0x140065d0f  mov     ebx, [rcx+18h]
0x140065d12  test    ebx, ebx
0x140065d14  js      loc_140066B72
0x140065d1a  lea     rax, [rcx+10h]
0x140065d1e  mov     [rsp+188h+var_E8], rax
0x140065d26  mov     ecx, [rax]
0x140065d28  shr     ecx, 6
0x140065d2b  and     ecx, 3Fh
0x140065d2e  lea     r14d, [rsi+1]
0x140065d32  mov     eax, r14d
0x140065d35  shl     eax, cl
0x140065d37  imul    rcx, rax, 1FF00200h
0x140065d3e  cmp     rdx, rcx
0x140065d41  jg      loc_140066B76
0x140065d47  mov     rcx, [rsp+188h+arg_20]
0x140065d4f  cmp     dword ptr [rcx], 38h ; '8'
0x140065d52  jb      loc_140066B76
0x140065d58  lea     r8, [rsp+188h+var_118]
0x140065d5d  mov     rcx, rdi
0x140065d60  call    HsmIBitmapNORMALMayContainDirtyRange
0x140065d65  mov     ebx, eax
0x140065d67  mov     ecx, eax
0x140065d69  call    HsmDbgBreakOnStatus
0x140065d6e  test    ebx, ebx
0x140065d70  js      loc_140066B87
0x140065d76  test    r13, r13
0x140065d79  jnz     loc_140066BF7
0x140065d7f  lea     edx, [rsi+20h]
0x140065d82  mov     ecx, 102h
0x140065d87  mov     r8d, 63427348h
0x140065d8d  call    cs:__imp_ExAllocatePool2
0x140065d94  nop     dword ptr [rax+rax+00h]
0x140065d99  mov     r13, rax
0x140065d9c  mov     [rsp+188h+P], rax
0x140065da4  mov     [rsp+188h+Lbn], rax
0x140065dac  test    r13, r13
0x140065daf  jz      loc_140066C1A
0x140065db5  lea     rax, [rdi+10h]
0x140065db9  mov     [rsp+188h+var_B8], rax
0x140065dc1  mov     [rsp+188h+var_110], rdi
0x140065dc6  xorps   xmm0, xmm0
0x140065dc9  movups  xmmword ptr [r13+0], xmm0
0x140065dce  movups  xmmword ptr [r13+10h], xmm0
0x140065dd3  lea     rdx, [rsp+188h+var_11C]
0x140065dd8  mov     rcx, rdi
0x140065ddb  cmp     [rsp+188h+var_118], sil
0x140065de0  jz      loc_1400669C3
0x140065de6  call    HsmiBitmapNORMALPrepareMcbsForCommit
0x140065deb  mov     ebx, eax
0x140065ded  mov     ecx, eax
0x140065def  call    HsmDbgBreakOnStatus
0x140065df4  test    ebx, ebx
0x140065df6  js      loc_140066A2D
0x140065dfc  mov     edx, 1000h
0x140065e01  mov     ecx, 100h
0x140065e06  mov     r8d, 6D427348h
0x140065e0c  call    cs:__imp_ExAllocatePool2
0x140065e13  nop     dword ptr [rax+rax+00h]
0x140065e18  mov     r15, rax
0x140065e1b  mov     [rsp+188h+Buffer], rax
0x140065e20  mov     [rsp+188h+var_A8], rax
0x140065e28  test    rax, rax
0x140065e2b  jz      loc_140066D10
0x140065e31  lea     rcx, [rdi+8]
0x140065e35  mov     [rsp+188h+var_68], rcx
0x140065e3d  cmp     [rcx], rsi
0x140065e40  jg      loc_1400663EA
0x140065e46  mov     [rsp+188h+var_120], r14b
0x140065e4b  mov     [rsp+188h+var_D8], rsi
0x140065e53  mov     r8d, 7
0x140065e59  mov     [rsp+188h+var_B0], rcx
0x140065e61  cmp     [rsp+188h+var_120], sil
0x140065e66  jz      short loc_140065E79
0x140065e68  mov     rax, [rcx]
0x140065e6b  cmp     [rsp+188h+var_D8], rax
0x140065e73  jz      loc_1400666CA
0x140065e79  mov     r15d, [rdi+10h]
0x140065e7d  mov     ecx, r15d
0x140065e80  shr     ecx, 6
0x140065e83  and     ecx, 3Fh
0x140065e86  mov     edx, r14d
0x140065e89  shl     edx, cl
0x140065e8b  mov     [rsp+188h+var_FC], edx
0x140065e92  shr     r15d, 0Ch
0x140065e96  and     r15d, r8d
0x140065e99  mov     [rsp+188h+var_11C], r15d
0x140065e9e  mov     [rsp+188h+var_100], r15d
0x140065ea6  mov     ecx, r15d
0x140065ea9  call    HsmiBitmapNORMALComputeMaxUserFileSize
0x140065eae  mov     rbx, [rsp+188h+arg_8]
0x140065eb6  cmp     rax, rbx
0x140065eb9  jl      loc_140066E02
0x140065ebf  mov     [rsp+188h+Parameter], rsi
0x140065ec7  mov     qword ptr [rsp+188h+var_88], rdi
0x140065ecf  mov     dword ptr [rsp+188h+var_88+8], r15d
0x140065ed7  mov     rcx, rdi
0x140065eda  call    HsmiBitmapNORMALGetNumberOfPlexCopies
0x140065edf  mov     dword ptr [rsp+188h+var_88+0Ch], eax
0x140065ee6  mov     [rsp+188h+var_78], rbx
0x140065eee  lea     rdx, [rsp+188h+Parameter]; Parameter
0x140065ef6  lea     rcx, HsmiBitmapNORMALOpenOnDiskCallout; Callout
0x140065efd  call    HsmExpandKernelStackAndCallout
0x140065f02  mov     ebx, eax
0x140065f04  mov     ecx, eax
0x140065f06  call    HsmDbgBreakOnStatus
0x140065f0b  test    ebx, ebx
0x140065f0d  js      loc_14006644A
0x140065f13  lea     r13, WPP_GLOBAL_Control
0x140065f1a  mov     rcx, cs:WPP_GLOBAL_Control
0x140065f21  cmp     rcx, r13
0x140065f24  jnz     loc_1400668BC
0x140065f2a  lea     ebx, [r15+1]
0x140065f2e  test    ebx, ebx
0x140065f30  jnz     loc_140066975
0x140065f36  lea     rax, [rdi+30h]
0x140065f3a  mov     [rsp+188h+var_F8], rax
0x140065f42  xor     edx, edx
0x140065f44  mov     rcx, rax
0x140065f47  call    cs:__imp_FltAcquirePushLockSharedEx
0x140065f4e  nop     dword ptr [rax+rax+00h]
0x140065f53  lea     rbx, [rdi+38h]
0x140065f57  mov     [rsp+188h+var_D0], rbx
0x140065f5f  mov     rcx, [rbx]
0x140065f62  test    rcx, rcx
0x140065f65  jz      loc_140066E92
0x140065f6b  mov     eax, [rdi+10h]
0x140065f6e  shr     eax, 0Ch
0x140065f71  and     eax, 7
0x140065f74  cmp     eax, r15d
0x140065f77  jnz     loc_140066E4A
0x140065f7d  mov     rcx, cs:WPP_GLOBAL_Control
0x140065f84  cmp     rcx, r13
0x140065f87  jnz     loc_140066A7D
0x140065f8d  mov     r8d, 1000h; Size
0x140065f93  mov     rdx, [rbx]; Src
0x140065f96  mov     rbx, [rsp+188h+Buffer]
0x140065f9b  mov     rcx, rbx; void *
0x140065f9e  call    memmove
0x140065fa3  mov     rax, [rsp+188h+var_D0]
0x140065fab  cmp     [rax], rsi
0x140065fae  jz      short loc_140065FC5
0x140065fb0  mov     r8d, [rdi+10h]
0x140065fb4  shr     r8d, 0Ch
0x140065fb8  and     r8d, 7
0x140065fbc  cmp     r15d, r8d
0x140065fbf  ja      loc_140066EE8
0x140065fc5  xor     edx, edx
0x140065fc7  mov     rcx, [rsp+188h+var_F8]
0x140065fcf  call    cs:__imp_FltReleasePushLockEx
0x140065fd6  nop     dword ptr [rax+rax+00h]
0x140065fdb  mov     qword ptr [rsp+188h+var_60], 0FFFFFFFFFFFFFFFFh
0x140065fe7  mov     [rsp+188h+var_117], 0FFh
0x140065fec  mov     rcx, [rdi+88h]
0x140065ff3  mov     edx, 3
0x140065ff8  lea     r15d, [rdx-1]
0x140065ffc  lea     rax, [rdi+80h]
0x140066003  mov     [rsp+188h+var_F8], rcx
0x14006600b  cmp     rcx, rax
0x14006600e  jnz     loc_1400664A0
0x140066014  mov     rax, [rsp+188h+var_B0]
0x14006601c  mov     rcx, [rax]
0x14006601f  cmp     [rsp+188h+arg_8], rcx
0x140066027  jg      loc_140066789
0x14006602d  mov     r8d, 0FFCh; Length
0x140066033  mov     rdx, [rsp+188h+Buffer]; Buffer
0x140066038  xor     ecx, ecx; InitialCrc
0x14006603a  call    cs:__imp_RtlComputeCrc32
0x140066041  nop     dword ptr [rax+rax+00h]
0x140066046  mov     rcx, [rsp+188h+Buffer]
0x14006604b  mov     [rcx+0FFCh], eax
0x140066051  mov     rdx, [rsp+188h+P]
0x140066059  add     rdx, 8
0x14006605d  mov     eax, [rsp+188h+var_11C]
0x140066061  test    eax, eax
0x140066063  jnz     loc_140066665
0x140066069  mov     [rdx], rsi
0x14006606c  lea     ebx, [rax+5]
0x14006606f  mov     rdx, [rsp+188h+P]
0x140066077  mov     [rdx+10h], rcx
0x14006607b  mov     r8d, eax
0x14006607e  xor     r8d, [rdx+18h]
0x140066082  and     r8d, 0FFFFFFF8h
0x140066086  xor     r8d, eax
0x140066089  mov     [rdx+18h], r8d
0x14006608d  mov     r9, [rsp+188h+arg_8]
0x140066095  mov     [rdx], r9
0x140066098  mov     rcx, cs:WPP_GLOBAL_Control
0x14006609f  cmp     rcx, r13
0x1400660a2  jnz     loc_140066727
0x1400660a8  mov     r8d, 3
0x1400660ae  mov     qword ptr [r12], 70527442h
0x1400660b6  mov     dword ptr [r12+8], 38h ; '8'
0x1400660bf  mov     dword ptr [r12+0Ch], 50000h
0x1400660c8  xorps   xmm0, xmm0
0x1400660cb  xor     eax, eax
0x1400660cd  movups  xmmword ptr [r12+10h], xmm0
0x1400660d3  movups  xmmword ptr [r12+20h], xmm0
0x1400660d9  mov     [r12+30h], rax
0x1400660de  mov     rax, [rsp+188h+arg_20]
0x1400660e6  mov     eax, [rax]
0x1400660e8  cmp     eax, 18h
0x1400660eb  jb      loc_140066AEA
0x1400660f1  cmp     si, bx
0x1400660f4  jnb     loc_140067479
0x1400660fa  mov     edx, [r12+8]
0x1400660ff  lea     rcx, [r8+rdx]
0x140066103  and     rcx, 0FFFFFFFFFFFFFFFCh
0x140066107  add     rcx, r14
0x14006610a  cmp     rcx, rax
0x14006610d  ja      loc_140066AEA
0x140066113  lea     eax, [rdx+3]
0x140066116  and     eax, 0FFFFFFFCh
0x140066119  mov     ecx, eax
0x14006611b  mov     [r12+8], ecx
0x140066120  mov     dword ptr [r12+10h], 10007h
0x140066129  mov     [r12+14h], ecx
0x14006612e  mov     [rax+r12], r14b
0x140066132  add     [r12+8], r14d
0x140066137  mov     ebx, esi
0x140066139  mov     ecx, ebx
0x14006613b  call    HsmDbgBreakOnStatus
0x140066140  test    ebx, ebx
0x140066142  js      loc_140066A09
0x140066148  mov     rax, [rsp+188h+arg_20]
0x140066150  mov     eax, [rax]
0x140066152  cmp     eax, 18h
0x140066155  jnb     loc_140066846
0x14006615b  mov     ebx, 0C0000023h
0x140066160  mov     ecx, ebx
0x140066162  call    HsmDbgBreakOnStatus
0x140066167  test    ebx, ebx
0x140066169  js      loc_140066B08
0x14006616f  mov     rax, [rsp+188h+arg_20]
0x140066177  mov     eax, [rax]
0x140066179  cmp     eax, 18h
0x14006617c  jb      loc_140066AF4
0x140066182  mov     rdx, [rsp+188h+P]
0x14006618a  mov     edx, [rdx+18h]
0x14006618d  shl     edx, 1Dh
0x140066190  sar     edx, 1Dh
0x140066193  cmp     r15w, [r12+0Eh]
0x140066199  jnb     loc_1400674BD
0x14006619f  cmp     eax, 28h ; '('
0x1400661a2  jb      loc_140066AF4
0x1400661a8  mov     r8d, [r12+8]
0x1400661ad  lea     rcx, [r8+3]
0x1400661b1  and     rcx, 0FFFFFFFFFFFFFFFCh
0x1400661b5  add     rcx, r14
0x1400661b8  cmp     rcx, rax
0x1400661bb  ja      loc_140066AF4
0x1400661c1  lea     eax, [r8+3]
0x1400661c5  and     eax, 0FFFFFFFCh
0x1400661c8  mov     [r12+8], eax
0x1400661cd  cmp     [r12+20h], si
0x1400661d3  jz      short loc_1400661DB
0x1400661d5  or      [r12+0Ch], r14w
0x1400661db  mov     dword ptr [r12+20h], 10007h
0x1400661e4  mov     [r12+24h], eax
0x1400661e9  mov     [rax+r12], dl
0x1400661ed  add     [r12+8], r14d
0x1400661f2  mov     ebx, esi
0x1400661f4  mov     ecx, ebx
0x1400661f6  call    HsmDbgBreakOnStatus
0x1400661fb  test    ebx, ebx
0x1400661fd  js      loc_140066B38
0x140066203  mov     rax, [rsp+188h+arg_20]
0x14006620b  mov     eax, [rax]
  ... truncated ...
```
