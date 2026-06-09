# FveManageDataSetAttributes

- ea: `0x140025b9c`
- end: `0x140026fa4`
- name: `FveManageDataSetAttributes`
- size: `5128`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140030430`

## callees

- `0x140006730`
- `0x140007868`
- `0x140008bc0`
- `0x140008e80`
- `0x140008eb0`
- `0x140008f04`
- `0x1400091fc`
- `0x1400092d8`
- `0x14000949c`
- `0x140009cb4`
- `0x140022bf0`
- `0x140022d40`
- `0x140023040`
- `0x140025040`
- `0x140025b9c`
- `0x14002945c`
- `0x14002a4e4`
- `0x14002b9a8`
- `0x1400dce00`
- `0x1400dd144`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140026e6a`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140026f08`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140026e6a`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140026f08`
- `ntoskrnl!IofCompleteRequest` at `0x140026f21`
- `ntoskrnl!IofCompleteRequest` at `0x140026f21`
- `ntoskrnl!KeBugCheckEx` at `0x1400269d3`
- `ntoskrnl!KeBugCheckEx` at `0x1400269d3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026e08`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026e08`
- `ntoskrnl!ExAllocatePool2` at `0x140026a13`
- `ntoskrnl!ExAllocatePool2` at `0x140026a13`

## pseudocode

```c
__int64 __fastcall FveManageDataSetAttributes(__int64 a1, __int64 a2)
{
  __int64 v2; // rsi
  __int64 v4; // r8
  __int64 v5; // rbx
  char v6; // r12
  char v7; // di
  unsigned int v8; // r15d
  char v9; // bl
  __int64 v10; // rdx
  __int64 v11; // rax
  unsigned int v12; // r13d
  unsigned int *v13; // r14
  __int64 v14; // r9
  PDEVICE_OBJECT v15; // rcx
  __int64 v16; // rdx
  PDEVICE_OBJECT v17; // rcx
  __int64 v18; // rdx
  PDEVICE_OBJECT v19; // rcx
  __int64 v20; // rdx
  char v21; // al
  unsigned int v22; // r8d
  unsigned int v23; // r11d
  unsigned int v24; // eax
  unsigned int v25; // ecx
  unsigned int v26; // edx
  bool v27; // cc
  __int64 v28; // rax
  char *v29; // r13
  unsigned int v30; // eax
  ULONG v31; // r11d
  __int64 v32; // r9
  unsigned int v33; // edx
  PDEVICE_OBJECT v34; // rcx
  __int64 v35; // rdx
  __int64 v36; // r9
  __int64 v37; // r14
  __int64 v38; // r10
  __int64 v39; // r11
  __int64 v40; // rbx
  __int64 v41; // rdi
  __int64 v42; // rsi
  __int64 v43; // rax
  PDEVICE_OBJECT v44; // rcx
  __int64 v45; // rdx
  unsigned int updated; // edi
  unsigned int v47; // esi
  __int64 *v48; // rbx
  PDEVICE_OBJECT v49; // rcx
  __int64 v50; // rdx
  __int64 v51; // rax
  __int64 v52; // rax
  __int64 v53; // rax
  bool v54; // zf
  unsigned int v55; // r13d
  __int64 *v56; // rdi
  __int64 v57; // r14
  unsigned __int64 i; // rsi
  unsigned int v59; // ecx
  unsigned int v60; // ebx
  unsigned int v61; // edx
  unsigned int v62; // ebx
  int v63; // eax
  __int64 v64; // rax
  __int64 v65; // rax
  char *v66; // rdx
  unsigned __int64 v67; // rcx
  unsigned __int64 v68; // r9
  ULONGLONG v69; // r10
  ULONGLONG v70; // r8
  unsigned int v71; // r9d
  signed __int64 v72; // r13
  __int64 v73; // rax
  unsigned int v74; // edi
  __int64 v75; // rax
  ULONGLONG v76; // rsi
  ULONGLONG v77; // r14
  __int64 v78; // rbx
  int v79; // esi
  signed __int64 *v80; // rdi
  ULONG j; // r14d
  ULONGLONG v82; // rbx
  unsigned int v83; // r14d
  ULONGLONG v84; // r8
  ULONGLONG v85; // r10
  unsigned __int64 v86; // r9
  unsigned int v87; // eax
  _DWORD *v88; // r14
  unsigned int v89; // esi
  size_t v90; // rdi
  int *Pool2; // rax
  int *v92; // rbx
  unsigned int v93; // eax
  int v94; // ecx
  __int64 v95; // rdx
  int v96; // eax
  __int64 v97; // rdi
  signed __int64 *v98; // rdi
  ULONG v99; // r9d
  __int64 *v100; // r8
  int v101; // eax
  bool v102; // sf
  unsigned int v103; // r11d
  unsigned int v104; // r13d
  unsigned int k; // esi
  __int64 v106; // rdx
  ULONGLONG v107; // r8
  __int64 v108; // r14
  ULONGLONG v109; // rcx
  ULONGLONG v110; // rax
  __int64 v111; // rax
  int v112; // r11d
  __int64 v113; // rcx
  __int64 v114; // rdx
  signed __int64 v115; // r13
  unsigned int v116; // r14d
  signed __int64 v117; // rsi
  signed __int64 v118; // r10
  ULONGLONG v119; // rdx
  ULONGLONG v120; // rax
  ULONGLONG v121; // rdx
  __int64 v122; // r13
  unsigned __int8 v123; // r8
  unsigned int v124; // eax
  unsigned int v125; // eax
  char v127; // [rsp+70h] [rbp-90h]
  char v128; // [rsp+72h] [rbp-8Eh]
  char v129; // [rsp+72h] [rbp-8Eh]
  unsigned int v130; // [rsp+74h] [rbp-8Ch]
  int v131; // [rsp+74h] [rbp-8Ch]
  __int64 v133; // [rsp+80h] [rbp-80h]
  unsigned __int8 v134; // [rsp+88h] [rbp-78h]
  ULONG pulResult; // [rsp+8Ch] [rbp-74h] BYREF
  int v136; // [rsp+90h] [rbp-70h]
  unsigned int v137; // [rsp+94h] [rbp-6Ch]
  ULONGLONG v138; // [rsp+98h] [rbp-68h]
  __int64 v139; // [rsp+A0h] [rbp-60h]
  int v140; // [rsp+A8h] [rbp-58h]
  unsigned int v141; // [rsp+ACh] [rbp-54h]
  void *v142; // [rsp+B0h] [rbp-50h]
  ULONGLONG pullResult; // [rsp+B8h] [rbp-48h] BYREF
  size_t Size; // [rsp+C0h] [rbp-40h]
  ULONGLONG v145; // [rsp+C8h] [rbp-38h]
  PDEVICE_OBJECT v146; // [rsp+D0h] [rbp-30h]
  unsigned int v147; // [rsp+D8h] [rbp-28h]
  __int64 v148; // [rsp+E0h] [rbp-20h]
  _BYTE v149[144]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int64 v150; // [rsp+180h] [rbp+80h] BYREF
  ULONGLONG v151; // [rsp+188h] [rbp+88h]
  unsigned __int64 v152; // [rsp+190h] [rbp+90h]
  ULONGLONG v153; // [rsp+198h] [rbp+98h]
  __int64 v154; // [rsp+1D0h] [rbp+D0h] BYREF
  _QWORD v155[11]; // [rsp+1D8h] [rbp+D8h] BYREF

  v2 = a2;
  memset(v149, 0, sizeof(v149));
  pullResult = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
  }
  v5 = *(_QWORD *)(a1 + 64);
  v6 = 1;
  v133 = v5;
  LOBYTE(v4) = 1;
  v140 = 0;
  v7 = 0;
  FvepAcquireDevFveLock(v5, v149, v4);
  v127 = 1;
  *(_OWORD *)(v2 + 120) = 0;
  v137 = 2;
  *(_OWORD *)(v2 + 136) = 0;
  v8 = FvepAcquireRundownProtectionOrHold(v5, (_QWORD *)v2, 2u);
  if ( v8 )
  {
    v21 = 1;
    goto LABEL_318;
  }
  v9 = 0;
  LOBYTE(v2) = 0;
  v128 = 0;
  v136 = v2;
  v10 = *(unsigned int *)(v133 + 808);
  v140 = (unsigned __int8)BYTE1(*(_DWORD *)(a2 + 120));
  if ( (v10 & 0x17F) != 0 && (v10 & 0x40) == 0 )
  {
    v9 = 1;
    v128 = 1;
    LOBYTE(v2) = *(_WORD *)(*(_QWORD *)(v133 + 976) + 10LL) > 1u;
    v136 = (unsigned __int8)v2;
  }
  v11 = *(_QWORD *)(a2 + 184);
  v148 = v11;
  v12 = *(_DWORD *)(v11 + 16);
  v147 = v12;
  if ( v12 < 0x1C || (v13 = *(unsigned int **)(a2 + 24), v142 = v13, *v13 < 0x1C) )
  {
    v8 = -1073741811;
    v2 = a2;
    v5 = v133;
    goto LABEL_320;
  }
  v14 = v13[1];
  v7 = 1;
  LODWORD(Size) = *(_DWORD *)(v11 + 8);
  switch ( (_DWORD)v14 )
  {
    case 0:
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_59;
      }
      v16 = 15;
LABEL_58:
      WPP_SF_(v15->AttachedDevice, v16, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
      goto LABEL_59;
    case 1:
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_59;
      }
      v16 = 17;
      goto LABEL_58;
    case 4:
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v20 = 20;
        goto LABEL_37;
      }
LABEL_38:
      v6 = v9;
      if ( v9 )
        v8 = -1073741637;
      goto LABEL_40;
    case 0x80000002:
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_59;
      }
      v16 = 18;
      goto LABEL_58;
    case 0x80000003:
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v20 = 19;
LABEL_37:
        WPP_SF_(v19->AttachedDevice, v20, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
        goto LABEL_38;
      }
      goto LABEL_38;
    case 0x80000005:
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_31;
      }
      v18 = 21;
      goto LABEL_30;
    case 0x8000000C:
      v15 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
      {
        goto LABEL_59;
      }
      v16 = 16;
      goto LABEL_58;
  }
  v15 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v14);
  }
LABEL_59:
  if ( (v13[1] & 0x80000000) == 0 )
  {
    v15 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
    }
  }
  if ( v9 && (v13[2] & 1) != 0 )
  {
    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v15, v10);
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_31;
    }
    v18 = 24;
LABEL_30:
    WPP_SF_(v17->AttachedDevice, v18, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
LABEL_31:
    v6 = 0;
LABEL_32:
    v2 = a2;
    v5 = v133;
    goto LABEL_320;
  }
  v22 = v13[6];
  if ( !v22 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_31;
    }
    v18 = 25;
    goto LABEL_30;
  }
  v23 = v13[4];
  v24 = v23 + 28;
  if ( v23 >= 0xFFFFFFE4 || v24 + v22 < v24 )
  {
LABEL_171:
    v8 = -1073741675;
    goto LABEL_32;
  }
  pulResult = v24 + v22;
  if ( v12 < v24 + v22 || v23 && v13[3] >= v12 || v13[5] >= v12 )
    goto LABEL_78;
  if ( v23 )
  {
    v25 = v13[3];
    v26 = v13[5];
    if ( v26 <= v25 )
    {
      if ( v26 >= v25 )
        goto LABEL_78;
      v27 = v26 + v22 <= v25;
    }
    else
    {
      v27 = v25 + v23 <= v26;
    }
    if ( !v27 )
    {
LABEL_78:
      v8 = -1073741811;
      goto LABEL_32;
    }
  }
  v8 = 0;
  if ( v13[1] != -2147483646 )
    goto LABEL_173;
  if ( !v23 )
    goto LABEL_78;
  v28 = v13[3];
  if ( !(_DWORD)v28 )
    goto LABEL_78;
  v29 = (char *)v13 + v28;
  v30 = *(unsigned int *)((char *)v13 + v28);
  if ( v30 < 0x1C || v30 > v23 )
    goto LABEL_78;
  v8 = RtlULongLongToULong(16LL * *((unsigned int *)v29 + 2), &pulResult);
  if ( (v8 & 0x80000000) != 0 )
  {
LABEL_40:
    v5 = v133;
    goto LABEL_41;
  }
  if ( pulResult + 12 < pulResult )
    goto LABEL_171;
  if ( pulResult + 12 > v31 )
    goto LABEL_78;
  v32 = *((unsigned int *)v29 + 1);
  v33 = 0;
  v8 = 0;
  v130 = 0;
  v141 = 0;
  if ( (_DWORD)v32 == 1 )
  {
    v134 = 1;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_112;
    }
    v35 = 26;
LABEL_110:
    WPP_SF_(v34->AttachedDevice, v35, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
    goto LABEL_111;
  }
  if ( (_DWORD)v32 == 2 )
  {
    v134 = 0;
    v34 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
    {
      goto LABEL_112;
    }
    v35 = 27;
    goto LABEL_110;
  }
  v134 = 1;
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 5u )
  {
    goto LABEL_112;
  }
  WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v32);
LABEL_111:
  v33 = 0;
LABEL_112:
  if ( !*((_DWORD *)v29 + 2) )
    goto LABEL_173;
  v36 = *(_QWORD *)FILE_TYPE_NOTIFICATION_GUID_PAGE_FILE.Data4;
  v37 = *(_QWORD *)&FILE_TYPE_NOTIFICATION_GUID_PAGE_FILE.Data1;
  v38 = *(_QWORD *)FILE_TYPE_NOTIFICATION_GUID_HIBERNATION_FILE.Data4;
  v39 = *(_QWORD *)&FILE_TYPE_NOTIFICATION_GUID_HIBERNATION_FILE.Data1;
  v40 = *(_QWORD *)FILE_TYPE_NOTIFICATION_GUID_CRASHDUMP_FILE.Data4;
  v41 = *(_QWORD *)&FILE_TYPE_NOTIFICATION_GUID_CRASHDUMP_FILE.Data1;
  v42 = FVE_TEST_RANGE_TYPE_NOTIFICATION_GUID;
  do
  {
    v43 = *(_QWORD *)&v29[16 * v8 + 12] - v37;
    if ( !v43 )
      v43 = *(_QWORD *)&v29[16 * v8 + 20] - v36;
    if ( v43 )
    {
      v51 = *(_QWORD *)&v29[16 * v8 + 12] - v39;
      if ( !v51 )
        v51 = *(_QWORD *)&v29[16 * v8 + 20] - v38;
      if ( v51 )
      {
        v52 = *(_QWORD *)&v29[16 * v8 + 12] - v41;
        if ( !v52 )
          v52 = *(_QWORD *)&v29[16 * v8 + 20] - v40;
        if ( v52 )
        {
          v53 = *(_QWORD *)&v29[16 * v8 + 12] - v42;
          if ( !v53 )
            v53 = *(_QWORD *)&v29[16 * v8 + 20] - 0x64F2A121132489A1LL;
          if ( v53 )
          {
            v146 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
            {
              if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
              {
                WPP_SF_DDDDDDDDDDD(
                  v146->AttachedDevice,
                  (unsigned __int8)v29[16 * v8 + 26],
                  (unsigned __int8)v29[16 * v8 + 25],
                  *(_DWORD *)&v29[16 * v8 + 12],
                  *(_WORD *)&v29[16 * v8 + 16],
                  *(_WORD *)&v29[16 * v8 + 18],
                  v29[16 * v8 + 20],
                  v29[16 * v8 + 21],
                  v29[16 * v8 + 22],
                  v29[16 * v8 + 23],
                  v29[16 * v8 + 24],
                  v29[16 * v8 + 25],
                  v29[16 * v8 + 26],
                  v29[16 * v8 + 27]);
                goto LABEL_122;
              }
LABEL_123:
              v33 = v130;
              goto LABEL_124;
            }
            v33 = v130;
          }
          else
          {
            v33 |= 0x10u;
            v130 = v33;
            v44 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
            {
              v45 = 32;
LABEL_121:
              WPP_SF_(v44->AttachedDevice, v45, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
LABEL_122:
              v36 = *(_QWORD *)FILE_TYPE_NOTIFICATION_GUID_PAGE_FILE.Data4;
              v37 = *(_QWORD *)&FILE_TYPE_NOTIFICATION_GUID_PAGE_FILE.Data1;
              v38 = *(_QWORD *)FILE_TYPE_NOTIFICATION_GUID_HIBERNATION_FILE.Data4;
              v39 = *(_QWORD *)&FILE_TYPE_NOTIFICATION_GUID_HIBERNATION_FILE.Data1;
              v40 = *(_QWORD *)FILE_TYPE_NOTIFICATION_GUID_CRASHDUMP_FILE.Data4;
              v41 = *(_QWORD *)&FILE_TYPE_NOTIFICATION_GUID_CRASHDUMP_FILE.Data1;
              v42 = FVE_TEST_RANGE_TYPE_NOTIFICATION_GUID;
              goto LABEL_123;
            }
          }
        }
        else
        {
          v33 |= 4u;
          v130 = v33;
          v44 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            v45 = 31;
            goto LABEL_121;
          }
        }
      }
      else
      {
        v33 |= 2u;
        v130 = v33;
        v44 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v45 = 30;
          goto LABEL_121;
        }
      }
    }
    else
    {
      v33 |= 1u;
      v130 = v33;
      v44 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        v45 = 29;
        goto LABEL_121;
      }
    }
LABEL_124:
    ++v8;
  }
  while ( v8 < *((_DWORD *)v29 + 2) );
  v8 = v141;
  v13 = (unsigned int *)v142;
  if ( !v33 )
    goto LABEL_172;
  updated = 0;
  v47 = *((_DWORD *)v142 + 6);
  v48 = (__int64 *)((char *)v142 + *((unsigned int *)v142 + 5));
  while ( 2 )
  {
    if ( v47 >= 0x10 )
    {
      if ( v134 )
      {
        v49 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v50 = 34;
          goto LABEL_163;
        }
      }
      else
      {
        v49 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          v50 = 35;
LABEL_163:
          WPP_SF_iii(v49->AttachedDevice, v50, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
        }
      }
      v8 = FvepAcquireRundownProtectionOrHold(v133, (_QWORD *)a2, 2u);
      if ( v8 )
      {
LABEL_315:
        v5 = v133;
LABEL_316:
        v7 = 1;
LABEL_41:
        v2 = a2;
        v21 = 1;
        goto LABEL_318;
      }
      updated = FveUpdateSpecialRange(v133, v134, v130, *v48, v48[1], a2);
      if ( updated == 259 )
        updated = 0;
      else
        FvepInformRundownFinishedWithDisk(v133, a2, 2u);
      v48 += 2;
      v47 -= 16;
      continue;
    }
    break;
  }
  if ( v130 == 16 )
  {
    v8 = updated;
    goto LABEL_32;
  }
LABEL_172:
  LOBYTE(v2) = v136;
  v7 = 1;
  v9 = v128;
LABEL_173:
  v54 = v9 == 0;
  v5 = v133;
  if ( v54 )
  {
    v2 = a2;
    v6 = 0;
    v21 = 1;
    goto LABEL_318;
  }
  if ( *(_DWORD *)(v133 + 1492) )
  {
    v55 = v13[6];
    v56 = (__int64 *)((char *)v13 + v13[5]);
    while ( v55 >= 0x10 )
    {
      v57 = *v56;
      for ( i = v56[1]; i; i -= v64 )
      {
        v59 = *(_DWORD *)(v5 + 1308);
        v60 = v59 - 1;
        if ( (v59 & (v59 - 1)) != 0 || !v59 )
          v61 = 0xFFFFFFFF % v59;
        else
          v61 = v59 - 1;
        if ( i <= ~v61 )
        {
          v62 = i;
        }
        else
        {
          if ( (v59 & (v59 - 1)) != 0 )
            v60 = 0xFFFFFFFF % v59;
          v62 = ~v60;
        }
        v63 = FveProtectedNoOverlapWithConvOrHold(v133, a2, v57, v62);
        v8 = v63;
        if ( v63 < 0 )
          goto LABEL_315;
        if ( v63 == 259 )
          goto LABEL_328;
        v64 = v62;
        v5 = v133;
        v57 += v64;
      }
      v56 += 2;
      v55 -= 16;
    }
    v13 = (unsigned int *)v142;
    LOBYTE(v2) = v136;
  }
  if ( !(_BYTE)v2 )
  {
LABEL_195:
    v7 = 1;
    v6 = 0;
    goto LABEL_41;
  }
  v65 = *(_QWORD *)(v5 + 976);
  v146 = *(PDEVICE_OBJECT *)(v65 + 56);
  if ( (unsigned __int64)v146 > 0x7FFFFFFFFFFFFFFFLL )
    goto LABEL_314;
  v8 = RtlULongLongMult(*(unsigned int *)(v65 + 28), *(unsigned int *)(v5 + 1308), &pullResult);
  if ( (v8 & 0x80000000) != 0 )
    goto LABEL_316;
  v70 = pullResult;
  v145 = pullResult;
  if ( pullResult > v69 )
  {
LABEL_314:
    v2 = a2;
    v8 = -1073741675;
    goto LABEL_320;
  }
  if ( (v13[1] & 0x80000000) == 0 )
  {
    v73 = *(_QWORD *)(v5 + 976);
    v8 = 0;
    v67 = 2;
    if ( *(_WORD *)(v73 + 12) == 2 )
    {
      v67 = *(_QWORD *)(v73 + 16);
      v66 = (char *)*(unsigned int *)(v73 + 24);
      if ( v67 >= *(_QWORD *)(v73 + 56) )
      {
        v150 = v68;
        v151 = pullResult;
        v152 = v67;
        v153 = (ULONGLONG)v66;
      }
      else
      {
        v150 = *(_QWORD *)(v73 + 16);
        v151 = (ULONGLONG)v66;
        v152 = v68;
        v153 = pullResult;
      }
      v71 = 2;
    }
    else
    {
      v150 = v68;
      v71 = 1;
      v151 = pullResult;
      v137 = 1;
    }
    v74 = 0;
    v138 = pullResult;
    v72 = pullResult;
    while ( v74 < 3 )
    {
      v75 = v74 + 44LL;
      v76 = *(_QWORD *)(v5 + 24 * v75);
      if ( v76 > v69 )
        goto LABEL_314;
      v77 = *(unsigned int *)(v5 + 24 * v75 + 8);
      v67 = 0;
      v8 = 0;
      while ( 1 )
      {
        v78 = 16LL * (unsigned int)v67;
        if ( (unsigned int)v67 >= v71 )
          break;
        v66 = (char *)&v150 + v78;
        if ( *(__int64 *)((char *)&v150 + v78) > (__int64)v76 )
        {
          memmove(v66 + 16, v66, 16LL * (v71 - (unsigned int)v67));
          v71 = v137;
          v69 = 0x7FFFFFFFFFFFFFFFLL;
          break;
        }
        v67 = (unsigned int)(v67 + 1);
      }
      ++v71;
      *(unsigned __int64 *)((char *)&v150 + v78) = v76;
      *(ULONGLONG *)((char *)&v151 + v78) = v77;
      ++v74;
      v5 = v133;
      v137 = v71;
    }
    v13 = (unsigned int *)v142;
    v70 = v72;
  }
  else
  {
    v71 = 0;
    v138 = pullResult;
    v137 = 0;
    v8 = 0;
    v72 = pullResult;
  }
  v79 = 0;
  v80 = (signed __int64 *)((char *)v13 + v13[5]);
  v129 = 0;
  for ( j = v13[6]; ; j -= 16 )
  {
    pulResult = j;
    if ( j < 0x10 )
      break;
    v82 = *v80 + v80[1];
    if ( v82 < *v80 )
      goto LABEL_171;
    v138 = v72;
    if ( *((int *)v142 + 1) >= 0 )
    {
      v83 = 0;
      v138 = v72;
      while ( 1 )
      {
        v8 = 0;
        if ( v83 >= v71 )
          break;
        v84 = *(&v150 + 2 * v83);
        v85 = v84 + *(&v151 + 2 * v83);
        if ( v85 < v84 )
          goto LABEL_171;
        v86 = *v80;
        v138 = v72;
        if ( v86 < v85 && v82 > v84 )
        {
          v129 = 1;
          ++v79;
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_iiii(WPP_GLOBAL_Control->AttachedDevice, 36, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
          }
        }
        v71 = v137;
        ++v83;
      }
      j = pulResult;
      v70 = v145;
    }
    else
    {
      v8 = 0;
    }
    if ( *v80 >= v72 )
    {
      v67 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_ii(WPP_GLOBAL_Control->AttachedDevice, 38, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, *v80, v82);
        v70 = v145;
      }
    }
    else
    {
      v129 = 1;
      v67 = (unsigned __int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_iii(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
        v70 = v145;
      }
      if ( v82 > v70 )
        ++v79;
    }
    v71 = v137;
    ++v79;
    v80 += 2;
  }
  if ( !v129 )
  {
    v5 = v133;
    goto LABEL_195;
  }
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v67, v66)
    && (*(_BYTE *)(v133 + 4419) & 8) != 0 )
  {
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  v87 = Size;
  v88 = v142;
  v89 = 16 * v79;
  v141 = v89 + ((*((_DWORD *)v142 + 4) + 39) & 0xFFFFFFF8);
  if ( v141 > (unsigned int)Size )
    v87 = v141;
  v90 = v87;
  Pool2 = (int *)ExAllocatePool2(72, v87, 809850438);
  v92 = Pool2;
  if ( !Pool2 )
  {
    v8 = -1073741670;
    goto LABEL_32;
  }
  memset(Pool2, 0, v90);
  *v92 = 28;
  v92[1] = v88[1];
  v92[2] = v88[2];
  v93 = v88[4];
  if ( v93 )
  {
    v92[4] = v93;
    v92[3] = 32;
    memmove(v92 + 8, (char *)v88 + (unsigned int)v88[3], v93);
  }
  v94 = v92[4];
  LODWORD(v95) = v89;
  v139 = v89;
  v92[6] = v89;
  if ( v94 )
    v96 = v94 + v92[3];
  else
    v96 = *v92;
  v97 = (v96 + 7) & 0xFFFFFFF8;
  v92[5] = v97;
  v98 = (signed __int64 *)((char *)v92 + v97);
  v99 = v88[6];
  v100 = (__int64 *)((char *)v88 + (unsigned int)v88[5]);
  v101 = 0;
  pullResult = (ULONGLONG)v100;
  v131 = 0;
  pulResult = v99;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 39, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids);
      LODWORD(v95) = v139;
      v100 = (__int64 *)pullResult;
      v99 = pulResult;
    }
    v101 = 0;
  }
LABEL_264:
  if ( v99 < 0x10 || (unsigned int)v95 < 0x10 )
  {
    v2 = a2;
    if ( v101 )
    {
      v122 = v148;
      v123 = v140;
      v92[6] = 16 * v101;
      v124 = v141;
      *(_QWORD *)(a2 + 24) = v92;
      *(_DWORD *)(v122 + 16) = v124;
      FvepInformRundownFinishedWithDisk(v133, a2, v123);
      FvepReleaseDevFveLock(v149);
      v127 = 0;
      IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v133 + 112), (PIRP)a2);
      v8 = *(_DWORD *)(a2 + 48);
      if ( (_DWORD)Size )
        memmove(v88, v92, (unsigned int)Size);
      v125 = v147;
      *(_QWORD *)(a2 + 24) = v88;
      *(_DWORD *)(v122 + 16) = v125;
    }
    else
    {
      v127 = 1;
    }
    goto LABEL_308;
  }
  v102 = (int)v88[1] < 0;
  v103 = 1;
  v154 = *v100;
  v155[0] = v100[1];
  v136 = 1;
  if ( v102 )
    goto LABEL_284;
  v104 = 0;
  for ( k = 0; ; ++k )
  {
    if ( k >= v103 )
    {
      LODWORD(v95) = v139;
LABEL_284:
      v115 = v138;
      v116 = 0;
      v101 = v131;
      while ( 1 )
      {
        if ( v116 >= v103 )
        {
LABEL_305:
          v100 = (__int64 *)(pullResult + 16);
          v88 = v142;
          v99 = pulResult - 16;
          pulResult -= 16;
          pullResult += 16LL;
          goto LABEL_264;
        }
        v117 = v155[2 * v116 - 1];
        v118 = v155[2 * v116];
        if ( v117 >= v115 )
          break;
        v119 = v118 + v117;
        if ( v118 + v117 < (unsigned __int64)v117 )
          goto LABEL_306;
        v120 = v145;
        if ( v119 <= v145 )
        {
          v8 = RtlLongLongAdd(v155[2 * v116 - 1], v146);
          if ( (v8 & 0x80000000) != 0 )
            goto LABEL_307;
          LODWORD(v95) = v139;
          goto LABEL_299;
        }
        v8 = 0;
        *v98 = v115;
        v121 = v119 - v120;
        v98[1] = v121;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_ii(
            WPP_GLOBAL_Control->AttachedDevice,
            40,
            WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
            v115,
            v121 + v115);
        }
        v98 += 2;
        v101 = v131 + 1;
        v95 = (unsigned int)(v139 - 16);
        ++v131;
        v139 = v95;
        if ( (unsigned int)v95 < 0x10 )
          goto LABEL_305;
        v8 = RtlLongLongAdd(v117, v146);
        if ( (v8 & 0x80000000) != 0 )
          goto LABEL_307;
        LODWORD(v95) = v139;
        v98[1] = v115 - v117;
LABEL_300:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_ii(
            WPP_GLOBAL_Control->AttachedDevice,
            41,
            WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids,
            *v98,
            *v98 + v98[1]);
          LODWORD(v95) = v139;
        }
        v95 = (unsigned int)(v95 - 16);
        v103 = v136;
        v101 = v131 + 1;
        v98 += 2;
        ++v131;
        ++v116;
        v139 = v95;
      }
      *v98 = v117;
LABEL_299:
      v98[1] = v118;
      goto LABEL_300;
    }
    v106 = v155[2 * k - 1];
    v107 = v106 + v155[2 * k];
    if ( v107 < v106 )
      break;
    while ( 1 )
    {
      v8 = 0;
      if ( v104 >= v137 )
        break;
      v108 = *(&v150 + 2 * v104);
      v109 = v108 + *(&v151 + 2 * v104);
      if ( v109 < v108 )
        goto LABEL_306;
      v110 = v138;
      if ( v107 > v108 && v106 < v109 )
      {
        if ( v106 >= v108 && v107 <= v109 )
        {
          --v103;
LABEL_281:
          v138 = v110;
          v8 = 0;
          v136 = v103;
          break;
        }
        v111 = 2LL * k;
        if ( v106 < v108 )
        {
          memmove(&v155[2 * k + 1], &v155[v111 - 1], 16LL * (v103 - k));
          v112 = v136;
          v113 = 2LL * (k + 1);
          v155[v113 - 1] = v108;
          v114 = v108 - v155[2 * k - 1];
          v155[v113] -= v114;
          v103 = v112 + 1;
          v155[2 * k] = v114;
          v110 = v138;
          goto LABEL_281;
        }
        v155[v111 - 1] = v109;
        v106 = v109;
        v155[2 * k] = v107 - v109;
      }
      ++v104;
    }
  }
LABEL_306:
  v8 = -1073741675;
LABEL_307:
  v2 = a2;
LABEL_308:
  ExFreePoolWithTag(v92, 0x30455646u);
  v21 = v127;
  v5 = v133;
  v7 = v127;
LABEL_318:
  if ( v8 != 259 )
  {
    if ( v7 )
LABEL_320:
      FvepInformRundownFinishedWithDisk(v5, v2, v140);
    if ( v127 )
    {
      FvepReleaseDevFveLock(v149);
      v127 = 0;
    }
    if ( (v8 & 0x80000000) == 0 && !v6 )
    {
      IoForwardIrpSynchronously(*(PDEVICE_OBJECT *)(v5 + 112), (PIRP)v2);
      v8 = *(_DWORD *)(v2 + 48);
    }
    *(_DWORD *)(v2 + 48) = v8;
    IofCompleteRequest((PIRP)v2, 0);
    v21 = v127;
  }
  if ( v21 )
LABEL_328:
    FvepReleaseDevFveLock(v149);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 42, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids, v8);
  }
  return v8;
}

```

## disassembly

```asm
0x140025b9c  mov     [rsp-8+arg_10], rbx
0x140025ba1  push    rbp
0x140025ba2  push    rsi
0x140025ba3  push    rdi
0x140025ba4  push    r12
0x140025ba6  push    r13
0x140025ba8  push    r14
0x140025baa  push    r15
0x140025bac  lea     rbp, [rsp-140h]
0x140025bb4  sub     rsp, 240h
0x140025bbb  mov     rax, cs:__security_cookie
0x140025bc2  xor     rax, rsp
0x140025bc5  mov     [rbp+170h+var_40], rax
0x140025bcc  mov     rsi, rdx
0x140025bcf  mov     [rsp+270h+Irp], rdx
0x140025bd4  mov     rbx, rcx
0x140025bd7  xor     edx, edx; Val
0x140025bd9  lea     rcx, [rbp+170h+var_180]; void *
0x140025bdd  mov     r8d, 90h; Size
0x140025be3  call    memset
0x140025be8  mov     [rbp+170h+pullResult], 0
0x140025bf0  mov     rcx, cs:WPP_GLOBAL_Control
0x140025bf7  lea     rax, WPP_GLOBAL_Control
0x140025bfe  cmp     rcx, rax
0x140025c01  jz      short loc_140025C25
0x140025c03  mov     eax, [rcx+2Ch]
0x140025c06  test    al, 40h
0x140025c08  jz      short loc_140025C25
0x140025c0a  cmp     byte ptr [rcx+29h], 5
0x140025c0e  jb      short loc_140025C25
0x140025c10  mov     rcx, [rcx+18h]
0x140025c14  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140025c1b  mov     edx, 0Eh
0x140025c20  call    WPP_SF_
0x140025c25  mov     rbx, [rbx+40h]
0x140025c29  lea     rdx, [rbp+170h+var_180]
0x140025c2d  mov     r12d, 1
0x140025c33  mov     [rbp+170h+var_1F0], rbx
0x140025c37  mov     r8b, r12b
0x140025c3a  mov     [rbp+170h+var_1C8], 0
0x140025c41  mov     rcx, rbx
0x140025c44  xor     dil, dil
0x140025c47  call    FvepAcquireDevFveLock
0x140025c4c  xorps   xmm0, xmm0
0x140025c4f  mov     [rsp+270h+var_200], r12b
0x140025c54  lea     eax, [r12+1]
0x140025c59  mov     rdx, rsi
0x140025c5c  movups  xmmword ptr [rsi+78h], xmm0
0x140025c60  mov     r8b, al
0x140025c63  mov     [rbp+170h+var_1DC], eax
0x140025c66  mov     rcx, rbx
0x140025c69  movups  xmmword ptr [rsi+88h], xmm0
0x140025c70  call    FvepAcquireRundownProtectionOrHold
0x140025c75  mov     r15d, eax
0x140025c78  test    eax, eax
0x140025c7a  jnz     loc_140026EC2
0x140025c80  mov     r8, [rsp+270h+Irp]
0x140025c85  xor     bl, bl
0x140025c87  mov     r9, [rbp+170h+var_1F0]
0x140025c8b  xor     sil, sil
0x140025c8e  mov     [rsp+270h+var_1FE], bl
0x140025c92  mov     [rbp+170h+var_1E0], esi
0x140025c95  mov     ecx, [r8+78h]
0x140025c99  mov     edx, [r9+328h]
0x140025ca0  shr     rcx, 8
0x140025ca4  test    edx, 17Fh
0x140025caa  movzx   eax, cl
0x140025cad  mov     [rbp+170h+var_1C8], eax
0x140025cb0  setnz   cl
0x140025cb3  test    dl, 40h
0x140025cb6  setz    al
0x140025cb9  test    al, cl
0x140025cbb  jz      short loc_140025CDB
0x140025cbd  mov     rax, [r9+3D0h]
0x140025cc4  mov     bl, r12b
0x140025cc7  movzx   esi, sil
0x140025ccb  mov     [rsp+270h+var_1FE], bl
0x140025ccf  cmp     [rax+0Ah], r12w
0x140025cd4  cmova   esi, r12d
0x140025cd8  mov     [rbp+170h+var_1E0], esi
0x140025cdb  mov     rax, [r8+0B8h]
0x140025ce2  mov     [rbp+170h+var_190], rax
0x140025ce6  mov     r13d, [rax+10h]
0x140025cea  mov     [rbp+170h+var_198], r13d
0x140025cee  cmp     r13d, 1Ch
0x140025cf2  jnb     short loc_140025D05
0x140025cf4  mov     r15d, 0C000000Dh
0x140025cfa  mov     rsi, r8
0x140025cfd  mov     rbx, r9
0x140025d00  jmp     loc_140026ED3
0x140025d05  mov     r14, [r8+18h]
0x140025d09  mov     [rbp+170h+var_1C0], r14
0x140025d0d  cmp     dword ptr [r14], 1Ch
0x140025d11  jb      short loc_140025CF4
0x140025d13  mov     r9d, [r14+4]
0x140025d17  mov     dil, r12b
0x140025d1a  mov     eax, [rax+8]
0x140025d1d  mov     [rsp+270h+var_1FF], r12b
0x140025d22  mov     dword ptr [rbp+170h+Size], eax
0x140025d25  test    r9d, r9d
0x140025d28  jz      loc_140025F0B
0x140025d2e  cmp     r9d, r12d
0x140025d31  jz      loc_140025EE4
0x140025d37  cmp     r9d, 4
0x140025d3b  jz      loc_140025EBA
0x140025d41  cmp     r9d, 80000002h
0x140025d48  jz      loc_140025E87
0x140025d4e  cmp     r9d, 80000003h
0x140025d55  jz      loc_140025E33
0x140025d5b  cmp     r9d, 80000005h
0x140025d62  jz      loc_140025DED
0x140025d68  cmp     r9d, 8000000Ch
0x140025d6f  jz      short loc_140025DB7
0x140025d71  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d78  lea     rax, WPP_GLOBAL_Control
0x140025d7f  cmp     rcx, rax
0x140025d82  jz      loc_140025F47
0x140025d88  mov     eax, [rcx+2Ch]
0x140025d8b  test    al, 40h
0x140025d8d  jz      loc_140025F40
0x140025d93  cmp     byte ptr [rcx+29h], 5
0x140025d97  jb      loc_140025F40
0x140025d9d  mov     rcx, [rcx+18h]
0x140025da1  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140025da8  mov     edx, 16h
0x140025dad  call    WPP_SF_d
0x140025db2  jmp     loc_140025F40
0x140025db7  mov     rcx, cs:WPP_GLOBAL_Control
0x140025dbe  lea     rax, WPP_GLOBAL_Control
0x140025dc5  cmp     rcx, rax
0x140025dc8  jz      loc_140025F47
0x140025dce  mov     eax, [rcx+2Ch]
0x140025dd1  test    al, 40h
0x140025dd3  jz      loc_140025F40
0x140025dd9  cmp     byte ptr [rcx+29h], 5
0x140025ddd  jb      loc_140025F40
0x140025de3  mov     edx, 10h
0x140025de8  jmp     loc_140025F30
0x140025ded  mov     rcx, cs:WPP_GLOBAL_Control
0x140025df4  lea     r10, WPP_GLOBAL_Control
0x140025dfb  cmp     rcx, r10
0x140025dfe  jz      short loc_140025E22
0x140025e00  mov     eax, [rcx+2Ch]
0x140025e03  test    al, 40h
0x140025e05  jz      short loc_140025E22
0x140025e07  cmp     byte ptr [rcx+29h], 5
0x140025e0b  jb      short loc_140025E22
0x140025e0d  mov     edx, 15h
0x140025e12  mov     rcx, [rcx+18h]
0x140025e16  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140025e1d  call    WPP_SF_
0x140025e22  xor     r12b, r12b
0x140025e25  mov     rsi, [rsp+270h+Irp]
0x140025e2a  mov     rbx, [rbp+170h+var_1F0]
0x140025e2e  jmp     loc_140026ED3
0x140025e33  mov     rcx, cs:WPP_GLOBAL_Control
0x140025e3a  lea     r10, WPP_GLOBAL_Control
0x140025e41  cmp     rcx, r10
0x140025e44  jz      short loc_140025E68
0x140025e46  mov     eax, [rcx+2Ch]
0x140025e49  test    al, 40h
0x140025e4b  jz      short loc_140025E68
0x140025e4d  cmp     byte ptr [rcx+29h], 5
0x140025e51  jb      short loc_140025E68
0x140025e53  mov     edx, 13h
0x140025e58  mov     rcx, [rcx+18h]
0x140025e5c  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140025e63  call    WPP_SF_
0x140025e68  test    bl, bl
0x140025e6a  mov     eax, 0C00000BBh
0x140025e6f  mov     r12b, bl
0x140025e72  cmovnz  r15d, eax
0x140025e76  mov     rbx, [rbp+170h+var_1F0]
0x140025e7a  mov     rsi, [rsp+270h+Irp]
0x140025e7f  mov     al, dil
0x140025e82  jmp     loc_140026EC5
0x140025e87  mov     rcx, cs:WPP_GLOBAL_Control
0x140025e8e  lea     rax, WPP_GLOBAL_Control
0x140025e95  cmp     rcx, rax
0x140025e98  jz      loc_140025F47
0x140025e9e  mov     eax, [rcx+2Ch]
0x140025ea1  test    al, 40h
0x140025ea3  jz      loc_140025F40
0x140025ea9  cmp     byte ptr [rcx+29h], 5
0x140025ead  jb      loc_140025F40
0x140025eb3  mov     edx, 12h
0x140025eb8  jmp     short loc_140025F30
0x140025eba  mov     rcx, cs:WPP_GLOBAL_Control
0x140025ec1  lea     r10, WPP_GLOBAL_Control
0x140025ec8  cmp     rcx, r10
0x140025ecb  jz      short loc_140025E68
0x140025ecd  mov     eax, [rcx+2Ch]
0x140025ed0  test    al, 40h
0x140025ed2  jz      short loc_140025E68
0x140025ed4  cmp     byte ptr [rcx+29h], 5
0x140025ed8  jb      short loc_140025E68
0x140025eda  mov     edx, 14h
0x140025edf  jmp     loc_140025E58
0x140025ee4  mov     rcx, cs:WPP_GLOBAL_Control
0x140025eeb  lea     rax, WPP_GLOBAL_Control
0x140025ef2  cmp     rcx, rax
0x140025ef5  jz      short loc_140025F47
0x140025ef7  mov     eax, [rcx+2Ch]
0x140025efa  test    al, 40h
0x140025efc  jz      short loc_140025F40
0x140025efe  cmp     byte ptr [rcx+29h], 5
0x140025f02  jb      short loc_140025F40
0x140025f04  mov     edx, 11h
0x140025f09  jmp     short loc_140025F30
0x140025f0b  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f12  lea     rax, WPP_GLOBAL_Control
0x140025f19  cmp     rcx, rax
0x140025f1c  jz      short loc_140025F47
0x140025f1e  mov     eax, [rcx+2Ch]
0x140025f21  test    al, 40h
0x140025f23  jz      short loc_140025F40
0x140025f25  cmp     byte ptr [rcx+29h], 5
0x140025f29  jb      short loc_140025F40
0x140025f2b  mov     edx, 0Fh
0x140025f30  mov     rcx, [rcx+18h]
0x140025f34  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140025f3b  call    WPP_SF_
0x140025f40  lea     rax, WPP_GLOBAL_Control
0x140025f47  cmp     dword ptr [r14+4], 0
0x140025f4c  jl      short loc_140025F7C
0x140025f4e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f55  cmp     rcx, rax
0x140025f58  jz      short loc_140025F7C
0x140025f5a  mov     eax, [rcx+2Ch]
0x140025f5d  test    al, 40h
0x140025f5f  jz      short loc_140025F7C
0x140025f61  cmp     byte ptr [rcx+29h], 5
0x140025f65  jb      short loc_140025F7C
0x140025f67  mov     rcx, [rcx+18h]
0x140025f6b  lea     r8, WPP_aaa266bfceb734b8e3c20e313abc0333_Traceguids
0x140025f72  mov     edx, 17h
0x140025f77  call    WPP_SF_
0x140025f7c  test    bl, bl
0x140025f7e  jz      short loc_140025FC4
0x140025f80  mov     eax, [r14+8]
0x140025f84  test    r12b, al
0x140025f87  jz      short loc_140025FC4
0x140025f89  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x140025f8e  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f95  lea     r10, WPP_GLOBAL_Control
0x140025f9c  cmp     rcx, r10
0x140025f9f  jz      loc_140025E22
0x140025fa5  mov     eax, [rcx+2Ch]
0x140025fa8  test    al, 40h
0x140025faa  jz      loc_140025E22
0x140025fb0  cmp     byte ptr [rcx+29h], 5
0x140025fb4  jb      loc_140025E22
0x140025fba  mov     edx, 18h
0x140025fbf  jmp     loc_140025E12
0x140025fc4  mov     r8d, [r14+18h]
0x140025fc8  test    r8d, r8d
0x140025fcb  jnz     short loc_140026002
0x140025fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140025fd4  lea     r10, WPP_GLOBAL_Control
0x140025fdb  cmp     rcx, r10
0x140025fde  jz      loc_140025E22
0x140025fe4  mov     eax, [rcx+2Ch]
0x140025fe7  test    al, 40h
0x140025fe9  jz      loc_140025E22
0x140025fef  cmp     byte ptr [rcx+29h], 5
0x140025ff3  jb      loc_140025E22
0x140025ff9  lea     edx, [r8+19h]
0x140025ffd  jmp     loc_140025E12
0x140026002  mov     r11d, [r14+10h]
0x140026006  lea     eax, [r11+1Ch]
0x14002600a  cmp     eax, 1Ch
0x14002600d  jb      loc_14002657E
0x140026013  lea     ecx, [rax+r8]
0x140026017  cmp     ecx, eax
0x140026019  jb      loc_14002657E
0x14002601f  mov     [rbp+170h+pulResult], ecx
0x140026022  cmp     r13d, ecx
0x140026025  jnb     short loc_140026032
0x140026027  mov     r15d, 0C000000Dh
0x14002602d  jmp     loc_140025E25
0x140026032  test    r11d, r11d
0x140026035  jz      short loc_14002603D
0x140026037  cmp     [r14+0Ch], r13d
0x14002603b  jnb     short loc_140026027
0x14002603d  cmp     [r14+14h], r13d
0x140026041  jnb     short loc_140026027
0x140026043  test    r11d, r11d
0x140026046  jz      short loc_140026060
0x140026048  mov     ecx, [r14+0Ch]
0x14002604c  mov     edx, [r14+14h]
0x140026050  cmp     edx, ecx
0x140026052  jbe     loc_14002612B
0x140026058  lea     eax, [rcx+r11]
0x14002605c  cmp     eax, edx
0x14002605e  ja      short loc_140026027
0x140026060  xor     r15d, r15d
0x140026063  cmp     dword ptr [r14+4], 80000002h
0x14002606b  jnz     loc_140026593
0x140026071  test    r11d, r11d
0x140026074  jz      short loc_140026027
  ... truncated ...
```
