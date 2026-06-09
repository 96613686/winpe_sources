# FvepWriteBootSectors

- ea: `0x1400b20c4`
- end: `0x1400b2b5e`
- name: `FvepWriteBootSectors`
- size: `2714`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14000c2c4`

## callees

- `0x140001580`
- `0x140006730`
- `0x140006a80`
- `0x140006b10`
- `0x140008348`
- `0x140008e80`
- `0x140008f04`
- `0x140009cb4`
- `0x14000afb4`
- `0x14000b9f0`
- `0x140013e10`
- `0x140013e70`
- `0x140022bf0`
- `0x140023040`
- `0x14009edc4`
- `0x1400b20c4`
- `0x1400b6f14`
- `0x1400d8170`
- `0x1400dbd00`
- `0x1400e1690`
- `0x1400e859c`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b2a55`
- `ntoskrnl!RtlCompareMemory` at `0x1400b2a55`
- `ntoskrnl!KeBugCheckEx` at `0x1400b2b51`
- `ntoskrnl!KeBugCheckEx` at `0x1400b2b51`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2af5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2b14`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2af5`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b2b14`
- `ntoskrnl!ExAllocatePool2` at `0x1400b21bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400b274c`
- `ntoskrnl!ExAllocatePool2` at `0x1400b276f`
- `ntoskrnl!ExAllocatePool2` at `0x1400b21bf`
- `ntoskrnl!ExAllocatePool2` at `0x1400b274c`
- `ntoskrnl!ExAllocatePool2` at `0x1400b276f`

## pseudocode

```c
__int64 __fastcall FvepWriteBootSectors(
        __int64 a1,
        __int64 a2,
        unsigned __int64 a3,
        __int64 a4,
        __int64 a5,
        int a6,
        int a7)
{
  __int64 v9; // rdx
  PDEVICE_OBJECT v10; // rcx
  __int64 v11; // rdx
  __int64 v12; // rcx
  PVOID v13; // rsi
  unsigned __int8 *v14; // rax
  __int64 Pool2; // rsi
  int v16; // ebx
  struct _DEVICE_OBJECT *v18; // rdx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r8
  __int64 v22; // r9
  __int64 i; // rdx
  __int64 v24; // rdx
  __int64 v25; // rcx
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 GuidRecognition; // rax
  __int64 v29; // rcx
  __int64 j; // rdx
  __int64 v31; // rdx
  __int64 v32; // rcx
  __int64 v33; // r8
  __int64 v34; // r9
  __int64 v35; // r13
  __int64 v36; // rax
  unsigned int v37; // r15d
  ULONG *v38; // rbx
  __int64 v39; // rcx
  __int64 v40; // rcx
  __int64 v41; // rax
  _DWORD *v42; // rdx
  PDEVICE_OBJECT v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // rax
  __int64 v46; // rdx
  __int64 v47; // rcx
  __int64 v48; // rbx
  __int64 v49; // r8
  __int64 v50; // r9
  unsigned int v51; // ebx
  __int64 *v52; // rax
  int v53; // eax
  __int64 v54; // r9
  __int64 v55; // rcx
  __int64 v56; // rax
  __int64 v57; // rax
  unsigned __int64 v58; // r15
  unsigned int v59; // eax
  unsigned int v60; // ebx
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r13
  __int64 v64; // rax
  __int64 v65; // rdx
  unsigned __int64 v66; // r12
  unsigned int v67; // eax
  SIZE_T v68; // r8
  unsigned __int64 v69; // rax
  struct _DEVICE_OBJECT *v70; // rdx
  __int64 v71; // rdx
  __int64 v72; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v74; // r8
  __int64 v75; // rax
  int v76; // eax
  __int64 v77; // r13
  __int64 v78; // rcx
  __int128 v79; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v80; // [rsp+50h] [rbp-B0h]
  unsigned __int64 v81; // [rsp+58h] [rbp-A8h]
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  SIZE_T Length; // [rsp+68h] [rbp-98h]
  __int64 v84; // [rsp+70h] [rbp-90h]
  void *Source2; // [rsp+78h] [rbp-88h]
  SIZE_T v86; // [rsp+80h] [rbp-80h]
  _QWORD v87[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v88[32]; // [rsp+A0h] [rbp-60h] BYREF

  v81 = a3;
  v84 = a4;
  v80 = 0;
  v79 = 0;
  memset(v88, 0, sizeof(v88));
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
  }
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v10, v9)
    && (*(_BYTE *)(a1 + 4419) & 0x18) == 8 )
  {
    goto LABEL_144;
  }
  P = 0;
  v80 = 0;
  v13 = 0;
  v79 = 0;
  if ( (a6 & 0xFFFFFFFC) != 0 )
  {
    if ( a6 != 1 )
    {
      v16 = -1073741811;
      goto LABEL_12;
    }
    goto LABEL_85;
  }
  if ( a6 == 1 )
  {
LABEL_85:
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v12, v11)
      && (*(_BYTE *)(a1 + 4419) & 8) != 0
      || (v56 = *(_QWORD *)(a1 + 976), *(_WORD *)(v56 + 10) == 1) )
    {
      v57 = 0;
    }
    else
    {
      v57 = *(unsigned int *)(v56 + 28);
      if ( !(_DWORD)v57 )
        v57 = 1;
    }
    v58 = v57 * *(unsigned int *)(a1 + 1308);
    v59 = 0x100000;
    if ( v58 <= 0x100000 )
      v59 = v58;
    v60 = v59;
    v86 = v59;
    Pool2 = ExAllocatePool2(72, v59, 809850438);
    if ( !Pool2 )
      goto LABEL_10;
    Source2 = (void *)ExAllocatePool2(72, v60, 809850438);
    if ( !Source2 )
    {
      v16 = -1073741670;
      goto LABEL_140;
    }
    v16 = 0;
    v63 = 0x2000;
    if ( v58 < 0x2000 )
      v63 = v58;
    if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v62, v61) )
      goto LABEL_112;
    if ( (*(_DWORD *)(a1 + 808) & 2) != 0 )
      goto LABEL_112;
    v64 = *(_QWORD *)(a1 + 4752);
    if ( !v64 || !*(_DWORD *)(v64 + 88) )
      goto LABEL_112;
    if ( !*(_QWORD *)(a1 + 1008) )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
      }
      v16 = ExtractFvek(*(_QWORD *)(a1 + 976) + 64LL, *(_QWORD *)(a1 + 1016), *(unsigned int *)(a1 + 1308), &P);
      if ( v16 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            107,
            WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids,
            (unsigned int)v16);
        }
        goto LABEL_140;
      }
LABEL_112:
      v65 = 0x2000;
      v66 = v58 - v63;
      v81 = 0x2000;
      v67 = 0;
      LODWORD(v84) = 0;
      while ( !v66 )
      {
LABEL_130:
        v65 = 0;
        v66 = 0x2000;
        v81 = 0;
        if ( v58 < 0x2000 )
          v66 = v58;
        LODWORD(v84) = ++v67;
        if ( v67 >= 2 )
          goto LABEL_140;
      }
      while ( 1 )
      {
        v68 = v66;
        if ( v86 < v66 )
          v68 = v86;
        v69 = v65 + *(_QWORD *)(*(_QWORD *)(a1 + 976) + 56LL);
        v70 = *(struct _DEVICE_OBJECT **)(a1 + 112);
        Length = v68;
        v16 = FveRawIoSynchronous(a1, v70, 3u, a7, 0, v69, v68, (unsigned __int8 *)Pool2);
        if ( v16 < 0 )
          goto LABEL_136;
        IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(
                                         v72,
                                         v71);
        LOBYTE(v74) = 1;
        if ( IsEnabledDeviceUsageNoInline )
          InitializeFilterData(a1, v88, v74, 0, 0, P);
        else
          InitializeFilterData(a1, v88, v74, 0, 0, 0);
        v75 = *(_QWORD *)(*(_QWORD *)(a1 + 976) + 56LL);
        v88[12] = Pool2;
        v88[2] = v81 + v75;
        LODWORD(v88[14]) = Length;
        v88[11] = FveFilteredRead;
        v88[13] = Pool2;
        v16 = FveParseBlockAndFilter(v88);
        DeInitializeFilterData(a1, v88);
        if ( v16 < 0 )
          goto LABEL_136;
        v16 = FveRawIoSynchronous(
                a1,
                *(struct _DEVICE_OBJECT **)(a1 + 112),
                4u,
                a7,
                0,
                v81,
                Length,
                (unsigned __int8 *)Pool2);
        if ( v16 < 0 )
        {
          v52 = FVE_METADATA_FAILED_COMMIT;
          v80 = 0;
          goto LABEL_138;
        }
        v76 = FveRawIoSynchronous(a1, *(struct _DEVICE_OBJECT **)(a1 + 112), 9u, a7, 0, 0, 0, 0);
        v16 = v76;
        if ( v76 != -1073741822 && v76 != -1073741808 && v76 != -1073741637 && v76 < 0 )
        {
          v52 = FVE_METADATA_DISK_FAILED_FLUSH_ERROR;
          goto LABEL_137;
        }
        v16 = FveRawIoSynchronous(
                a1,
                *(struct _DEVICE_OBJECT **)(a1 + 112),
                3u,
                a7,
                0,
                v81,
                Length,
                (unsigned __int8 *)Source2);
        if ( v16 < 0 )
          goto LABEL_136;
        v77 = (unsigned int)Length;
        if ( RtlCompareMemory((const void *)Pool2, Source2, (unsigned int)Length) != v77 )
        {
          v16 = -1073741823;
          goto LABEL_136;
        }
        v65 = v77 + v81;
        v81 += v77;
        v66 -= v77;
        if ( !v66 )
        {
          v67 = v84;
          goto LABEL_130;
        }
      }
    }
LABEL_144:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  v14 = (unsigned __int8 *)ExAllocatePool2(72, 0x2000, 809850438);
  Pool2 = (__int64)v14;
  if ( v14 )
  {
    v18 = *(struct _DEVICE_OBJECT **)(a1 + 112);
    Source2 = 0;
    v16 = FveRawIoSynchronous(a1, v18, 3u, a7, 0, 0, 0x2000u, v14);
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v20, v19) )
    {
      if ( v16 < 0 )
        goto LABEL_136;
      if ( (*(_BYTE *)(a1 + 4419) & 0x10) == 0 )
        goto LABEL_25;
      LOBYTE(v21) = 1;
      InitializeFilterData(a1, v88, v21, 0, 0, 0);
      v88[2] = 0;
      v88[11] = FveFilteredRead;
      LODWORD(v88[14]) = 0x2000;
      v88[12] = Pool2;
      v88[13] = Pool2;
      v16 = FveParseBlockAndFilter(v88);
      DeInitializeFilterData(a1, v88);
    }
    if ( v16 >= 0 )
    {
LABEL_25:
      if ( a6 == 2 )
      {
        if ( !a2 )
        {
LABEL_27:
          v16 = -1073741811;
          goto LABEL_140;
        }
        for ( i = 0; i != 3; ++i )
          v87[i] = *(_QWORD *)(a2 + 24 * i);
        FveBuildBootSector(Pool2, 3, v87);
        if ( !(unsigned int)Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline(v25, v24, v26, v27) )
          goto LABEL_76;
        GuidRecognition = FveFindGuidRecognition(Pool2, 0x2000);
        if ( !GuidRecognition )
          goto LABEL_76;
        v29 = (unsigned int)(GuidRecognition - Pool2 + 56);
        if ( (unsigned int)(GuidRecognition - Pool2 + 128) > 0x2000 )
          goto LABEL_76;
LABEL_75:
        memset((void *)(Pool2 + v29), 0, 0x48u);
LABEL_76:
        v16 = FveRawIoSynchronous(
                a1,
                *(struct _DEVICE_OBJECT **)(a1 + 112),
                4u,
                a7,
                0,
                0,
                0x2000u,
                (unsigned __int8 *)Pool2);
        if ( v16 >= 0 )
        {
          v53 = FveRawIoSynchronous(a1, *(struct _DEVICE_OBJECT **)(a1 + 112), 9u, a7, 0, 0, 0, 0);
          v16 = v53;
          if ( v53 != -1073741822 && v53 != -1073741808 && v53 != -1073741637 )
          {
            if ( v53 >= 0 )
              goto LABEL_140;
            v55 = *(_QWORD *)a1;
            LOBYTE(v54) = 1;
            *(_QWORD *)&v79 = FVE_METADATA_DISK_FAILED_FLUSH_ERROR;
            DWORD2(v79) = -1;
            HIDWORD(v79) = v53;
            v80 = 0;
            FveLogEventEx(v55, &v79, 0, v54);
          }
          v16 = 0;
LABEL_140:
          ExFreePoolWithTag((PVOID)Pool2, 0x30455646u);
          if ( Source2 )
            ExFreePoolWithTag(Source2, 0x30455646u);
          goto LABEL_11;
        }
        v52 = FVE_METADATA_FAILED_COMMIT;
        v80 = 0;
        LOBYTE(v22) = 1;
LABEL_139:
        v78 = *(_QWORD *)a1;
        HIDWORD(v79) = v16;
        DWORD2(v79) = -1;
        *(_QWORD *)&v79 = v52;
        FveLogEventEx(v78, &v79, 0, v22);
        goto LABEL_140;
      }
      if ( a6 != 3 )
      {
        *(_QWORD *)Pool2 = 0;
        *(_WORD *)(Pool2 + 8) = 0;
        *(_BYTE *)(Pool2 + 10) = 0;
        v45 = FveFindGuidRecognition(Pool2, 0x2000);
        if ( v45 )
        {
          *(_OWORD *)v45 = 0;
          *(_OWORD *)(v45 + 16) = 0;
          *(_QWORD *)(v45 + 32) = 0;
        }
        v48 = FveEowFindGuidRecognition(Pool2, 0x2000);
        if ( !v48 )
          goto LABEL_76;
        *(_OWORD *)v48 = 0;
        *(_OWORD *)(v48 + 16) = 0;
        *(_OWORD *)(v48 + 32) = 0;
        *(_QWORD *)(v48 + 48) = 0;
        if ( !(unsigned int)Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline(v47, v46, v49, v50) )
          goto LABEL_76;
        v51 = v48 - Pool2 + 56;
        if ( v51 + 72 > 0x2000 )
          goto LABEL_76;
        v29 = v51;
        goto LABEL_75;
      }
      if ( !a2 || !v81 )
        goto LABEL_27;
      for ( j = 0; j != 3; ++j )
        v87[j] = *(_QWORD *)(a2 + 24 * j);
      FveEowBuildBootSector(Pool2, 3, v87, v81);
      if ( !(unsigned int)Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline(v32, v31, v33, v34) )
        goto LABEL_76;
      v35 = v84;
      if ( !v84 )
        goto LABEL_76;
      v36 = FveEowFindGuidRecognition(Pool2, 0x2000);
      if ( !v36 )
        goto LABEL_76;
      v37 = v36 - Pool2 + 56;
      if ( (unsigned int)(v36 - Pool2 + 128) > 0x2000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids,
            v37,
            0x2000);
        }
        goto LABEL_76;
      }
      v38 = (ULONG *)(Pool2 + v37);
      memset(v38, 0, 0x48u);
      v39 = 0;
      *(_OWORD *)v38 = FVE_V3_RECOGNITION_GUID;
      do
      {
        *(_QWORD *)&v38[2 * v39 + 8] = *(_QWORD *)(v35 + 8 * v39);
        ++v39;
      }
      while ( v39 != 2 );
      v40 = a5;
      if ( a5 || (v40 = *(_QWORD *)(a1 + 976)) != 0 )
      {
        *((_QWORD *)v38 + 6) = *(_QWORD *)(v40 + 56);
        if ( *(_WORD *)(v40 + 10) == 1 )
        {
          v41 = 0;
        }
        else
        {
          v41 = *(unsigned int *)(v40 + 28);
          if ( !(_DWORD)v41 )
            v41 = 1;
        }
        if ( RtlULongLongToULong(v41 * *(unsigned int *)(a1 + 1308), v38 + 16) >= 0 )
          goto LABEL_61;
        *v42 = 0;
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_61;
        }
        v44 = 102;
      }
      else
      {
        *((_QWORD *)v38 + 6) = 0;
        v38[16] = 0;
        v43 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
LABEL_61:
          *((_QWORD *)v38 + 7) = *(_QWORD *)(a1 + 1256);
          v38[17] = *(_DWORD *)(a1 + 1264);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids, v37);
          }
          goto LABEL_76;
        }
        v44 = 103;
      }
      WPP_SF_(v43->AttachedDevice, v44, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids);
      goto LABEL_61;
    }
LABEL_136:
    v52 = FVE_METADATA_DISK_FAILED_READBACK_ERROR;
LABEL_137:
    v80 = 0;
LABEL_138:
    LOBYTE(v22) = 1;
    goto LABEL_139;
  }
LABEL_10:
  v16 = -1073741670;
LABEL_11:
  v13 = P;
LABEL_12:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v12, v11) && v13 )
    DeleteKey(v13);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      108,
      WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids,
      (unsigned int)v16);
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400b20c4  push    rbp
0x1400b20c6  push    rbx
0x1400b20c7  push    rsi
0x1400b20c8  push    rdi
0x1400b20c9  push    r12
0x1400b20cb  push    r13
0x1400b20cd  push    r14
0x1400b20cf  push    r15
0x1400b20d1  lea     rbp, [rsp-0B8h]
0x1400b20d9  sub     rsp, 1B8h
0x1400b20e0  mov     rax, cs:__security_cookie
0x1400b20e7  xor     rax, rsp
0x1400b20ea  mov     [rbp+0F0h+var_50], rax
0x1400b20f1  mov     [rsp+1F0h+var_198], r8
0x1400b20f6  mov     r13, rdx
0x1400b20f9  mov     rdi, rcx
0x1400b20fc  mov     [rsp+1F0h+var_180], r9
0x1400b2101  xorps   xmm0, xmm0
0x1400b2104  lea     rcx, [rbp+0F0h+var_150]; void *
0x1400b2108  xor     eax, eax
0x1400b210a  xor     edx, edx; Val
0x1400b210c  mov     r8d, 100h; Size
0x1400b2112  mov     [rsp+1F0h+var_1A0], rax
0x1400b2117  movups  [rsp+1F0h+var_1B0], xmm0
0x1400b211c  call    memset
0x1400b2121  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2128  lea     r12, WPP_GLOBAL_Control
0x1400b212f  cmp     rcx, r12
0x1400b2132  jz      short loc_1400B2156
0x1400b2134  mov     eax, [rcx+2Ch]
0x1400b2137  test    al, 4
0x1400b2139  jz      short loc_1400B2156
0x1400b213b  cmp     byte ptr [rcx+29h], 5
0x1400b213f  jb      short loc_1400B2156
0x1400b2141  mov     rcx, [rcx+18h]
0x1400b2145  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400b214c  mov     edx, 65h ; 'e'
0x1400b2151  call    WPP_SF_
0x1400b2156  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400b215b  xor     ebx, ebx
0x1400b215d  test    eax, eax
0x1400b215f  jz      short loc_1400B2171
0x1400b2161  mov     al, [rdi+1143h]
0x1400b2167  and     al, 18h
0x1400b2169  cmp     al, 8
0x1400b216b  jz      loc_1400B2B3D
0x1400b2171  mov     r15d, [rbp+0F0h+arg_28]
0x1400b2178  xor     eax, eax
0x1400b217a  mov     [rsp+1F0h+P], rbx
0x1400b217f  xorps   xmm0, xmm0
0x1400b2182  mov     [rsp+1F0h+var_1A0], rax
0x1400b2187  mov     rsi, rbx
0x1400b218a  movups  [rsp+1F0h+var_1B0], xmm0
0x1400b218f  lea     r14d, [rax+1]
0x1400b2193  test    r15d, 0FFFFFFFCh
0x1400b219a  jnz     loc_1400B26E7
0x1400b21a0  cmp     r15d, r14d
0x1400b21a3  jz      loc_1400B26F0
0x1400b21a9  lea     r12d, [rax+48h]
0x1400b21ad  mov     r14d, 2000h
0x1400b21b3  mov     edx, r14d
0x1400b21b6  mov     ecx, r12d
0x1400b21b9  mov     r8d, 30455646h
0x1400b21bf  call    cs:__imp_ExAllocatePool2
0x1400b21c6  nop     dword ptr [rax+rax+00h]
0x1400b21cb  mov     rsi, rax
0x1400b21ce  test    rax, rax
0x1400b21d1  jnz     short loc_1400B2251
0x1400b21d3  mov     ebx, 0C000009Ah
0x1400b21d8  lea     r12, WPP_GLOBAL_Control
0x1400b21df  mov     rsi, [rsp+1F0h+P]
0x1400b21e4  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400b21e9  test    eax, eax
0x1400b21eb  jz      short loc_1400B21FA
0x1400b21ed  test    rsi, rsi
0x1400b21f0  jz      short loc_1400B21FA
0x1400b21f2  mov     rcx, rsi; P
0x1400b21f5  call    DeleteKey
0x1400b21fa  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2201  cmp     rcx, r12
0x1400b2204  jz      short loc_1400B222B
0x1400b2206  mov     eax, [rcx+2Ch]
0x1400b2209  test    al, 4
0x1400b220b  jz      short loc_1400B222B
0x1400b220d  cmp     byte ptr [rcx+29h], 5
0x1400b2211  jb      short loc_1400B222B
0x1400b2213  mov     rcx, [rcx+18h]
0x1400b2217  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400b221e  mov     edx, 6Ch ; 'l'
0x1400b2223  mov     r9d, ebx
0x1400b2226  call    WPP_SF_d
0x1400b222b  mov     eax, ebx
0x1400b222d  mov     rcx, [rbp+0F0h+var_50]
0x1400b2234  xor     rcx, rsp; StackCookie
0x1400b2237  call    __security_check_cookie
0x1400b223c  add     rsp, 1B8h
0x1400b2243  pop     r15
0x1400b2245  pop     r14
0x1400b2247  pop     r13
0x1400b2249  pop     r12
0x1400b224b  pop     rdi
0x1400b224c  pop     rsi
0x1400b224d  pop     rbx
0x1400b224e  pop     rbp
0x1400b224f  retn
0x1400b2251  mov     r9d, [rbp+0F0h+arg_30]
0x1400b2258  mov     r8d, 3
0x1400b225e  mov     rdx, [rdi+70h]
0x1400b2262  mov     rcx, rdi
0x1400b2265  mov     [rsp+1F0h+var_1B8], rsi
0x1400b226a  mov     [rsp+1F0h+var_1C0], r14d
0x1400b226f  mov     [rsp+1F0h+var_1C8], rbx
0x1400b2274  mov     [rsp+1F0h+BugCheckParameter4], rbx
0x1400b2279  mov     [rsp+1F0h+Source2], rbx
0x1400b227e  call    FveRawIoSynchronous
0x1400b2283  mov     ebx, eax
0x1400b2285  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400b228a  test    eax, eax
0x1400b228c  jz      short loc_1400B22F9
0x1400b228e  test    ebx, ebx
0x1400b2290  js      loc_1400B2AB0
0x1400b2296  test    byte ptr [rdi+1143h], 10h
0x1400b229d  jz      short loc_1400B2301
0x1400b229f  mov     [rsp+1F0h+var_1C8], 0
0x1400b22a8  lea     rdx, [rbp+0F0h+var_150]
0x1400b22ac  xor     r9d, r9d
0x1400b22af  mov     [rsp+1F0h+BugCheckParameter4], 0
0x1400b22b8  mov     r8b, 1
0x1400b22bb  mov     rcx, rdi
0x1400b22be  call    InitializeFilterData
0x1400b22c3  lea     rax, FveFilteredRead
0x1400b22ca  mov     [rbp+0F0h+var_140], 0
0x1400b22d2  lea     rcx, [rbp+0F0h+var_150]
0x1400b22d6  mov     [rbp+0F0h+var_F8], rax
0x1400b22da  mov     [rbp+0F0h+var_E0], r14d
0x1400b22de  mov     [rbp+0F0h+var_F0], rsi
0x1400b22e2  mov     [rbp+0F0h+var_E8], rsi
0x1400b22e6  call    FveParseBlockAndFilter
0x1400b22eb  lea     rdx, [rbp+0F0h+var_150]
0x1400b22ef  mov     rcx, rdi
0x1400b22f2  mov     ebx, eax
0x1400b22f4  call    DeInitializeFilterData
0x1400b22f9  test    ebx, ebx
0x1400b22fb  js      loc_1400B2AB0
0x1400b2301  cmp     r15d, 2
0x1400b2305  jnz     short loc_1400B2372
0x1400b2307  test    r13, r13
0x1400b230a  jnz     short loc_1400B2316
0x1400b230c  mov     ebx, 0C000000Dh
0x1400b2311  jmp     loc_1400B2AE4
0x1400b2316  xor     edx, edx
0x1400b2318  lea     rax, [rdx+rdx*2]
0x1400b231c  mov     rcx, [r13+rax*8+0]
0x1400b2321  mov     [rbp+rdx*8+0F0h+var_168], rcx
0x1400b2326  inc     rdx
0x1400b2329  cmp     rdx, 3
0x1400b232d  jnz     short loc_1400B2318
0x1400b232f  lea     r8, [rbp+0F0h+var_168]
0x1400b2333  mov     rcx, rsi
0x1400b2336  call    FveBuildBootSector
0x1400b233b  call    Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline
0x1400b2340  test    eax, eax
0x1400b2342  jz      loc_1400B260A
0x1400b2348  mov     edx, r14d
0x1400b234b  mov     rcx, rsi
0x1400b234e  call    FveFindGuidRecognition
0x1400b2353  test    rax, rax
0x1400b2356  jz      loc_1400B260A
0x1400b235c  sub     eax, esi
0x1400b235e  lea     ecx, [rax+38h]
0x1400b2361  lea     eax, [rcx+48h]
0x1400b2364  cmp     eax, r14d
0x1400b2367  ja      loc_1400B260A
0x1400b236d  jmp     loc_1400B25FD
0x1400b2372  cmp     r15d, 3
0x1400b2376  jnz     loc_1400B2592
0x1400b237c  test    r13, r13
0x1400b237f  jz      short loc_1400B230C
0x1400b2381  cmp     [rsp+1F0h+var_198], 0
0x1400b2387  jz      short loc_1400B230C
0x1400b2389  xor     edx, edx
0x1400b238b  lea     rax, [rdx+rdx*2]
0x1400b238f  mov     rcx, [r13+rax*8+0]
0x1400b2394  mov     [rbp+rdx*8+0F0h+var_168], rcx
0x1400b2399  inc     rdx
0x1400b239c  cmp     rdx, 3
0x1400b23a0  jnz     short loc_1400B238B
0x1400b23a2  mov     r9, [rsp+1F0h+var_198]
0x1400b23a7  lea     r8, [rbp+0F0h+var_168]
0x1400b23ab  mov     rcx, rsi
0x1400b23ae  call    FveEowBuildBootSector
0x1400b23b3  call    Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline
0x1400b23b8  test    eax, eax
0x1400b23ba  jz      loc_1400B260A
0x1400b23c0  mov     r13, [rsp+1F0h+var_180]
0x1400b23c5  test    r13, r13
0x1400b23c8  jz      loc_1400B260A
0x1400b23ce  mov     edx, r14d
0x1400b23d1  mov     rcx, rsi
0x1400b23d4  call    FveEowFindGuidRecognition
0x1400b23d9  test    rax, rax
0x1400b23dc  jz      loc_1400B260A
0x1400b23e2  sub     eax, esi
0x1400b23e4  lea     r15d, [rax+38h]
0x1400b23e8  lea     eax, [r15+48h]
0x1400b23ec  cmp     eax, r14d
0x1400b23ef  ja      loc_1400B2547
0x1400b23f5  mov     ebx, r15d
0x1400b23f8  mov     r8, r12; Size
0x1400b23fb  add     rbx, rsi
0x1400b23fe  xor     edx, edx; Val
0x1400b2400  mov     rcx, rbx; void *
0x1400b2403  call    memset
0x1400b2408  movups  xmm0, cs:FVE_V3_RECOGNITION_GUID
0x1400b240f  xor     ecx, ecx
0x1400b2411  movdqu  xmmword ptr [rbx], xmm0
0x1400b2415  lea     r12d, [rcx+1]
0x1400b2419  mov     rax, [r13+rcx*8+0]
0x1400b241e  mov     [rbx+rcx*8+20h], rax
0x1400b2423  add     rcx, r12
0x1400b2426  cmp     rcx, 2
0x1400b242a  jnz     short loc_1400B2419
0x1400b242c  mov     rcx, [rbp+0F0h+arg_20]
0x1400b2433  test    rcx, rcx
0x1400b2436  jnz     short loc_1400B2444
0x1400b2438  mov     rcx, [rdi+3D0h]
0x1400b243f  test    rcx, rcx
0x1400b2442  jz      short loc_1400B24B4
0x1400b2444  mov     rax, [rcx+38h]
0x1400b2448  mov     [rbx+30h], rax
0x1400b244c  cmp     [rcx+0Ah], r12w
0x1400b2451  jnz     short loc_1400B2457
0x1400b2453  xor     eax, eax
0x1400b2455  jmp     short loc_1400B2460
0x1400b2457  mov     eax, [rcx+1Ch]
0x1400b245a  test    eax, eax
0x1400b245c  cmovz   eax, r12d
0x1400b2460  mov     ecx, [rdi+51Ch]
0x1400b2466  lea     rdx, [rbx+40h]; pulResult
0x1400b246a  imul    rcx, rax; ullOperand
0x1400b246e  call    RtlULongLongToULong
0x1400b2473  test    eax, eax
0x1400b2475  jns     short loc_1400B24EA
0x1400b2477  mov     dword ptr [rdx], 0
0x1400b247d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b2484  lea     r13, WPP_GLOBAL_Control
0x1400b248b  cmp     rcx, r13
0x1400b248e  jz      short loc_1400B24F1
0x1400b2490  mov     eax, [rcx+2Ch]
0x1400b2493  test    al, 4
0x1400b2495  jz      short loc_1400B24F1
0x1400b2497  cmp     byte ptr [rcx+29h], 2
0x1400b249b  jb      short loc_1400B24F1
0x1400b249d  mov     edx, 66h ; 'f'
0x1400b24a2  mov     rcx, [rcx+18h]
0x1400b24a6  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400b24ad  call    WPP_SF_
0x1400b24b2  jmp     short loc_1400B24F1
0x1400b24b4  mov     qword ptr [rbx+30h], 0
0x1400b24bc  mov     dword ptr [rbx+40h], 0
0x1400b24c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b24ca  lea     r13, WPP_GLOBAL_Control
0x1400b24d1  cmp     rcx, r13
0x1400b24d4  jz      short loc_1400B24F1
0x1400b24d6  mov     eax, [rcx+2Ch]
0x1400b24d9  test    al, 4
0x1400b24db  jz      short loc_1400B24F1
0x1400b24dd  cmp     byte ptr [rcx+29h], 2
0x1400b24e1  jb      short loc_1400B24F1
0x1400b24e3  mov     edx, 67h ; 'g'
0x1400b24e8  jmp     short loc_1400B24A2
0x1400b24ea  lea     r13, WPP_GLOBAL_Control
0x1400b24f1  mov     rax, [rdi+4E8h]
0x1400b24f8  mov     [rbx+38h], rax
0x1400b24fc  mov     eax, [rdi+4F0h]
0x1400b2502  mov     [rbx+44h], eax
0x1400b2505  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b250c  cmp     rcx, r13
0x1400b250f  jz      loc_1400B2610
0x1400b2515  mov     eax, [rcx+2Ch]
0x1400b2518  test    al, 4
0x1400b251a  jz      loc_1400B2610
0x1400b2520  cmp     byte ptr [rcx+29h], 5
0x1400b2524  jb      loc_1400B2610
0x1400b252a  mov     rcx, [rcx+18h]
0x1400b252e  lea     r8, WPP_23a49b7e03fe3bc03477b373fdbee1bb_Traceguids
0x1400b2535  mov     edx, 68h ; 'h'
0x1400b253a  mov     r9d, r15d
0x1400b253d  call    WPP_SF_d
0x1400b2542  jmp     loc_1400B2610
0x1400b2547  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b254e  lea     r13, WPP_GLOBAL_Control
0x1400b2555  cmp     rcx, r13
0x1400b2558  jz      loc_1400B260A
0x1400b255e  mov     eax, [rcx+2Ch]
0x1400b2561  test    al, 4
0x1400b2563  jz      loc_1400B260A
0x1400b2569  cmp     byte ptr [rcx+29h], 3
0x1400b256d  jb      loc_1400B260A
0x1400b2573  mov     rcx, [rcx+18h]
  ... truncated ...
```
