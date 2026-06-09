# FvepWriteBootSectors

- ea: `0x1400b0e3c`
- end: `0x1400b18d6`
- name: `FvepWriteBootSectors`
- size: `2714`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `broker_com_uri`

## callers

- `0x14000c134`

## callees

- `0x140001570`
- `0x140006670`
- `0x1400069c0`
- `0x140006a50`
- `0x140008288`
- `0x140008dc0`
- `0x140008e44`
- `0x140009bf4`
- `0x14000aef4`
- `0x14000b8c8`
- `0x140013458`
- `0x1400134b8`
- `0x1400218c0`
- `0x140021d00`
- `0x14009de84`
- `0x1400b0e3c`
- `0x1400b5c18`
- `0x1400d8584`
- `0x1400d9620`
- `0x1400def70`
- `0x1400e5cec`

## import_xrefs

- `ntoskrnl!RtlCompareMemory` at `0x1400b17cd`
- `ntoskrnl!RtlCompareMemory` at `0x1400b17cd`
- `ntoskrnl!KeBugCheckEx` at `0x1400b18c9`
- `ntoskrnl!KeBugCheckEx` at `0x1400b18c9`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b186d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b188c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b186d`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400b188c`
- `ntoskrnl!ExAllocatePool2` at `0x1400b0f37`
- `ntoskrnl!ExAllocatePool2` at `0x1400b14c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400b14e7`
- `ntoskrnl!ExAllocatePool2` at `0x1400b0f37`
- `ntoskrnl!ExAllocatePool2` at `0x1400b14c4`
- `ntoskrnl!ExAllocatePool2` at `0x1400b14e7`

## pseudocode

```c
__int64 __fastcall FvepWriteBootSectors(__int64 *a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, int a7)
{
  PDEVICE_OBJECT v9; // rcx
  __int64 v10; // rcx
  PVOID v11; // rsi
  __int64 v12; // rax
  _QWORD *Pool2; // rsi
  int v14; // ebx
  __int64 v16; // rdx
  __int64 v17; // rcx
  __int64 v18; // r8
  __int64 v19; // r9
  __int64 i; // rdx
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  __int64 v24; // r9
  __int64 GuidRecognition; // rax
  __int64 v26; // rcx
  __int64 j; // rdx
  __int64 v28; // rdx
  __int64 v29; // rcx
  __int64 v30; // r8
  __int64 v31; // r9
  __int64 v32; // r13
  __int64 v33; // rax
  unsigned int v34; // r15d
  ULONG *v35; // rbx
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  _DWORD *v39; // rdx
  PDEVICE_OBJECT v40; // rcx
  __int64 v41; // rdx
  __int64 v42; // rax
  __int64 v43; // rdx
  __int64 v44; // rcx
  __int64 v45; // rbx
  __int64 v46; // r8
  __int64 v47; // r9
  unsigned int v48; // ebx
  __int64 *v49; // rax
  int v50; // eax
  __int64 v51; // r9
  __int64 v52; // rcx
  __int64 v53; // rax
  __int64 v54; // rax
  unsigned __int64 v55; // r15
  unsigned int v56; // eax
  unsigned int v57; // ebx
  __int64 v58; // rcx
  __int64 v59; // r13
  __int64 v60; // rax
  __int64 v61; // rdx
  unsigned __int64 v62; // r12
  unsigned int v63; // eax
  SIZE_T v64; // r8
  __int64 v65; // rax
  __int64 v66; // rdx
  __int64 v67; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  __int64 v69; // r8
  __int64 v70; // rax
  int v71; // eax
  __int64 v72; // r13
  __int64 v73; // rcx
  __int128 v74; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v75; // [rsp+50h] [rbp-B0h]
  __int64 v76; // [rsp+58h] [rbp-A8h]
  PVOID P; // [rsp+60h] [rbp-A0h] BYREF
  SIZE_T Length; // [rsp+68h] [rbp-98h]
  __int64 v79; // [rsp+70h] [rbp-90h]
  void *Source2; // [rsp+78h] [rbp-88h]
  SIZE_T v81; // [rsp+80h] [rbp-80h]
  _QWORD v82[3]; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v83[32]; // [rsp+A0h] [rbp-60h] BYREF

  v76 = a3;
  v79 = a4;
  v75 = 0;
  v74 = 0;
  memset(v83, 0, sizeof(v83));
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 101, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
  }
  if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v9)
    && (*((_BYTE *)a1 + 4403) & 0x18) == 8 )
  {
    goto LABEL_144;
  }
  P = 0;
  v75 = 0;
  v11 = 0;
  v74 = 0;
  if ( (a6 & 0xFFFFFFFC) != 0 )
  {
    if ( a6 != 1 )
    {
      v14 = -1073741811;
      goto LABEL_12;
    }
    goto LABEL_85;
  }
  if ( a6 == 1 )
  {
LABEL_85:
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v10)
      && (*((_BYTE *)a1 + 4403) & 8) != 0
      || (v53 = a1[122], *(_WORD *)(v53 + 10) == 1) )
    {
      v54 = 0;
    }
    else
    {
      v54 = *(unsigned int *)(v53 + 28);
      if ( !(_DWORD)v54 )
        v54 = 1;
    }
    v55 = v54 * *((unsigned int *)a1 + 327);
    v56 = 0x100000;
    if ( v55 <= 0x100000 )
      v56 = v55;
    v57 = v56;
    v81 = v56;
    Pool2 = (_QWORD *)ExAllocatePool2(72, v56, 809850438);
    if ( !Pool2 )
      goto LABEL_10;
    Source2 = (void *)ExAllocatePool2(72, v57, 809850438);
    if ( !Source2 )
    {
      v14 = -1073741670;
      goto LABEL_140;
    }
    v14 = 0;
    v59 = 0x2000;
    if ( v55 < 0x2000 )
      v59 = v55;
    if ( !(unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v58) )
      goto LABEL_112;
    if ( (a1[101] & 2) != 0 )
      goto LABEL_112;
    v60 = a1[592];
    if ( !v60 || !*(_DWORD *)(v60 + 88) )
      goto LABEL_112;
    if ( !a1[126] )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
      }
      v14 = ExtractFvek(a1[122] + 64, a1[127], *((unsigned int *)a1 + 327), &P);
      if ( v14 < 0 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            107,
            WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids,
            (unsigned int)v14);
        }
        goto LABEL_140;
      }
LABEL_112:
      v61 = 0x2000;
      v62 = v55 - v59;
      v76 = 0x2000;
      v63 = 0;
      LODWORD(v79) = 0;
      while ( !v62 )
      {
LABEL_130:
        v61 = 0;
        v62 = 0x2000;
        v76 = 0;
        if ( v55 < 0x2000 )
          v62 = v55;
        LODWORD(v79) = ++v63;
        if ( v63 >= 2 )
          goto LABEL_140;
      }
      while ( 1 )
      {
        v64 = v62;
        if ( v81 < v62 )
          v64 = v81;
        v65 = v61 + *(_QWORD *)(a1[122] + 56);
        v66 = a1[14];
        Length = v64;
        v14 = FveRawIoSynchronous((_DWORD)a1, v66, 3, a7, 0, v65, v64, (__int64)Pool2);
        if ( v14 < 0 )
          goto LABEL_136;
        IsEnabledDeviceUsageNoInline = Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v67);
        LOBYTE(v69) = 1;
        if ( IsEnabledDeviceUsageNoInline )
          InitializeFilterData(a1, v83, v69, 0, 0, P);
        else
          InitializeFilterData(a1, v83, v69, 0, 0, 0);
        v70 = *(_QWORD *)(a1[122] + 56);
        v83[12] = Pool2;
        v83[2] = v76 + v70;
        LODWORD(v83[14]) = Length;
        v83[11] = FveFilteredRead;
        v83[13] = Pool2;
        v14 = FveParseBlockAndFilter(v83);
        DeInitializeFilterData(a1, v83);
        if ( v14 < 0 )
          goto LABEL_136;
        v14 = FveRawIoSynchronous((_DWORD)a1, a1[14], 4, a7, 0, v76, Length, (__int64)Pool2);
        if ( v14 < 0 )
        {
          v49 = FVE_METADATA_FAILED_COMMIT;
          v75 = 0;
          goto LABEL_138;
        }
        v71 = FveRawIoSynchronous((_DWORD)a1, a1[14], 9, a7, 0, 0, 0, 0);
        v14 = v71;
        if ( v71 != -1073741822 && v71 != -1073741808 && v71 != -1073741637 && v71 < 0 )
        {
          v49 = FVE_METADATA_DISK_FAILED_FLUSH_ERROR;
          goto LABEL_137;
        }
        v14 = FveRawIoSynchronous((_DWORD)a1, a1[14], 3, a7, 0, v76, Length, (__int64)Source2);
        if ( v14 < 0 )
          goto LABEL_136;
        v72 = (unsigned int)Length;
        if ( RtlCompareMemory(Pool2, Source2, (unsigned int)Length) != v72 )
        {
          v14 = -1073741823;
          goto LABEL_136;
        }
        v61 = v72 + v76;
        v76 += v72;
        v62 -= v72;
        if ( !v62 )
        {
          v63 = v79;
          goto LABEL_130;
        }
      }
    }
LABEL_144:
    KeBugCheckEx(0x120u, 0xCu, 0, 0, 0);
  }
  v12 = ExAllocatePool2(72, 0x2000, 809850438);
  Pool2 = (_QWORD *)v12;
  if ( v12 )
  {
    v16 = a1[14];
    Source2 = 0;
    v14 = FveRawIoSynchronous((_DWORD)a1, v16, 3, a7, 0, 0, 0x2000, v12);
    if ( (unsigned int)Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline(v17) )
    {
      if ( v14 < 0 )
        goto LABEL_136;
      if ( (*((_BYTE *)a1 + 4403) & 0x10) == 0 )
        goto LABEL_25;
      LOBYTE(v18) = 1;
      InitializeFilterData(a1, v83, v18, 0, 0, 0);
      v83[2] = 0;
      v83[11] = FveFilteredRead;
      LODWORD(v83[14]) = 0x2000;
      v83[12] = Pool2;
      v83[13] = Pool2;
      v14 = FveParseBlockAndFilter(v83);
      DeInitializeFilterData(a1, v83);
    }
    if ( v14 >= 0 )
    {
LABEL_25:
      if ( a6 == 2 )
      {
        if ( !a2 )
        {
LABEL_27:
          v14 = -1073741811;
          goto LABEL_140;
        }
        for ( i = 0; i != 3; ++i )
          v82[i] = *(_QWORD *)(a2 + 24 * i);
        FveBuildBootSector(Pool2, 3, v82);
        if ( !(unsigned int)Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline(v22, v21, v23, v24) )
          goto LABEL_76;
        GuidRecognition = FveFindGuidRecognition(Pool2, 0x2000);
        if ( !GuidRecognition )
          goto LABEL_76;
        v26 = (unsigned int)(GuidRecognition - (_DWORD)Pool2 + 56);
        if ( (unsigned int)(GuidRecognition - (_DWORD)Pool2 + 128) > 0x2000 )
          goto LABEL_76;
LABEL_75:
        memset((char *)Pool2 + v26, 0, 0x48u);
LABEL_76:
        v14 = FveRawIoSynchronous((_DWORD)a1, a1[14], 4, a7, 0, 0, 0x2000, (__int64)Pool2);
        if ( v14 >= 0 )
        {
          v50 = FveRawIoSynchronous((_DWORD)a1, a1[14], 9, a7, 0, 0, 0, 0);
          v14 = v50;
          if ( v50 != -1073741822 && v50 != -1073741808 && v50 != -1073741637 )
          {
            if ( v50 >= 0 )
              goto LABEL_140;
            v52 = *a1;
            LOBYTE(v51) = 1;
            *(_QWORD *)&v74 = FVE_METADATA_DISK_FAILED_FLUSH_ERROR;
            DWORD2(v74) = -1;
            HIDWORD(v74) = v50;
            v75 = 0;
            FveLogEventEx(v52, &v74, 0, v51);
          }
          v14 = 0;
LABEL_140:
          ExFreePoolWithTag(Pool2, 0x30455646u);
          if ( Source2 )
            ExFreePoolWithTag(Source2, 0x30455646u);
          goto LABEL_11;
        }
        v49 = FVE_METADATA_FAILED_COMMIT;
        v75 = 0;
        LOBYTE(v19) = 1;
LABEL_139:
        v73 = *a1;
        HIDWORD(v74) = v14;
        DWORD2(v74) = -1;
        *(_QWORD *)&v74 = v49;
        FveLogEventEx(v73, &v74, 0, v19);
        goto LABEL_140;
      }
      if ( a6 != 3 )
      {
        *Pool2 = 0;
        *((_WORD *)Pool2 + 4) = 0;
        *((_BYTE *)Pool2 + 10) = 0;
        v42 = FveFindGuidRecognition(Pool2, 0x2000);
        if ( v42 )
        {
          *(_OWORD *)v42 = 0;
          *(_OWORD *)(v42 + 16) = 0;
          *(_QWORD *)(v42 + 32) = 0;
        }
        v45 = FveEowFindGuidRecognition(Pool2, 0x2000);
        if ( !v45 )
          goto LABEL_76;
        *(_OWORD *)v45 = 0;
        *(_OWORD *)(v45 + 16) = 0;
        *(_OWORD *)(v45 + 32) = 0;
        *(_QWORD *)(v45 + 48) = 0;
        if ( !(unsigned int)Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline(v44, v43, v46, v47) )
          goto LABEL_76;
        v48 = v45 - (_DWORD)Pool2 + 56;
        if ( v48 + 72 > 0x2000 )
          goto LABEL_76;
        v26 = v48;
        goto LABEL_75;
      }
      if ( !a2 || !v76 )
        goto LABEL_27;
      for ( j = 0; j != 3; ++j )
        v82[j] = *(_QWORD *)(a2 + 24 * j);
      FveEowBuildBootSector(Pool2, 3, v82, v76);
      if ( !(unsigned int)Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline(v29, v28, v30, v31) )
        goto LABEL_76;
      v32 = v79;
      if ( !v79 )
        goto LABEL_76;
      v33 = FveEowFindGuidRecognition(Pool2, 0x2000);
      if ( !v33 )
        goto LABEL_76;
      v34 = v33 - (_DWORD)Pool2 + 56;
      if ( (unsigned int)(v33 - (_DWORD)Pool2 + 128) > 0x2000 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u )
        {
          WPP_SF_Dd(
            WPP_GLOBAL_Control->AttachedDevice,
            105,
            WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids,
            v34,
            0x2000);
        }
        goto LABEL_76;
      }
      v35 = (ULONG *)((char *)Pool2 + v34);
      memset(v35, 0, 0x48u);
      v36 = 0;
      *(_OWORD *)v35 = FVE_V3_RECOGNITION_GUID;
      do
      {
        *(_QWORD *)&v35[2 * v36 + 8] = *(_QWORD *)(v32 + 8 * v36);
        ++v36;
      }
      while ( v36 != 2 );
      v37 = a5;
      if ( a5 || (v37 = a1[122]) != 0 )
      {
        *((_QWORD *)v35 + 6) = *(_QWORD *)(v37 + 56);
        if ( *(_WORD *)(v37 + 10) == 1 )
        {
          v38 = 0;
        }
        else
        {
          v38 = *(unsigned int *)(v37 + 28);
          if ( !(_DWORD)v38 )
            v38 = 1;
        }
        if ( RtlULongLongToULong(v38 * *((unsigned int *)a1 + 327), v35 + 16) >= 0 )
          goto LABEL_61;
        *v39 = 0;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_61;
        }
        v41 = 102;
      }
      else
      {
        *((_QWORD *)v35 + 6) = 0;
        v35[16] = 0;
        v40 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
LABEL_61:
          *((_QWORD *)v35 + 7) = a1[157];
          v35[17] = *((_DWORD *)a1 + 316);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids, v34);
          }
          goto LABEL_76;
        }
        v41 = 103;
      }
      WPP_SF_(v40->AttachedDevice, v41, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids);
      goto LABEL_61;
    }
LABEL_136:
    v49 = FVE_METADATA_DISK_FAILED_READBACK_ERROR;
LABEL_137:
    v75 = 0;
LABEL_138:
    LOBYTE(v19) = 1;
    goto LABEL_139;
  }
LABEL_10:
  v14 = -1073741670;
LABEL_11:
  v11 = P;
LABEL_12:
  if ( (unsigned int)Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline(v10) && v11 )
    DeleteKey(v11);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      108,
      WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids,
      (unsigned int)v14);
  }
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400b0e3c  push    rbp
0x1400b0e3e  push    rbx
0x1400b0e3f  push    rsi
0x1400b0e40  push    rdi
0x1400b0e41  push    r12
0x1400b0e43  push    r13
0x1400b0e45  push    r14
0x1400b0e47  push    r15
0x1400b0e49  lea     rbp, [rsp-0B8h]
0x1400b0e51  sub     rsp, 1B8h
0x1400b0e58  mov     rax, cs:__security_cookie
0x1400b0e5f  xor     rax, rsp
0x1400b0e62  mov     [rbp+0F0h+var_50], rax
0x1400b0e69  mov     [rsp+1F0h+var_198], r8
0x1400b0e6e  mov     r13, rdx
0x1400b0e71  mov     rdi, rcx
0x1400b0e74  mov     [rsp+1F0h+var_180], r9
0x1400b0e79  xorps   xmm0, xmm0
0x1400b0e7c  lea     rcx, [rbp+0F0h+var_150]; void *
0x1400b0e80  xor     eax, eax
0x1400b0e82  xor     edx, edx; Val
0x1400b0e84  mov     r8d, 100h; Size
0x1400b0e8a  mov     [rsp+1F0h+var_1A0], rax
0x1400b0e8f  movups  [rsp+1F0h+var_1B0], xmm0
0x1400b0e94  call    memset
0x1400b0e99  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0ea0  lea     r12, WPP_GLOBAL_Control
0x1400b0ea7  cmp     rcx, r12
0x1400b0eaa  jz      short loc_1400B0ECE
0x1400b0eac  mov     eax, [rcx+2Ch]
0x1400b0eaf  test    al, 4
0x1400b0eb1  jz      short loc_1400B0ECE
0x1400b0eb3  cmp     byte ptr [rcx+29h], 5
0x1400b0eb7  jb      short loc_1400B0ECE
0x1400b0eb9  mov     rcx, [rcx+18h]
0x1400b0ebd  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400b0ec4  mov     edx, 65h ; 'e'
0x1400b0ec9  call    WPP_SF_
0x1400b0ece  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400b0ed3  xor     ebx, ebx
0x1400b0ed5  test    eax, eax
0x1400b0ed7  jz      short loc_1400B0EE9
0x1400b0ed9  mov     al, [rdi+1133h]
0x1400b0edf  and     al, 18h
0x1400b0ee1  cmp     al, 8
0x1400b0ee3  jz      loc_1400B18B5
0x1400b0ee9  mov     r15d, [rbp+0F0h+arg_28]
0x1400b0ef0  xor     eax, eax
0x1400b0ef2  mov     [rsp+1F0h+P], rbx
0x1400b0ef7  xorps   xmm0, xmm0
0x1400b0efa  mov     [rsp+1F0h+var_1A0], rax
0x1400b0eff  mov     rsi, rbx
0x1400b0f02  movups  [rsp+1F0h+var_1B0], xmm0
0x1400b0f07  lea     r14d, [rax+1]
0x1400b0f0b  test    r15d, 0FFFFFFFCh
0x1400b0f12  jnz     loc_1400B145F
0x1400b0f18  cmp     r15d, r14d
0x1400b0f1b  jz      loc_1400B1468
0x1400b0f21  lea     r12d, [rax+48h]
0x1400b0f25  mov     r14d, 2000h
0x1400b0f2b  mov     edx, r14d
0x1400b0f2e  mov     ecx, r12d
0x1400b0f31  mov     r8d, 30455646h
0x1400b0f37  call    cs:__imp_ExAllocatePool2
0x1400b0f3e  nop     dword ptr [rax+rax+00h]
0x1400b0f43  mov     rsi, rax
0x1400b0f46  test    rax, rax
0x1400b0f49  jnz     short loc_1400B0FC9
0x1400b0f4b  mov     ebx, 0C000009Ah
0x1400b0f50  lea     r12, WPP_GLOBAL_Control
0x1400b0f57  mov     rsi, [rsp+1F0h+P]
0x1400b0f5c  call    Feature_SteelixInlineNvmeCryptoEngine__private_IsEnabledDeviceUsageNoInline
0x1400b0f61  test    eax, eax
0x1400b0f63  jz      short loc_1400B0F72
0x1400b0f65  test    rsi, rsi
0x1400b0f68  jz      short loc_1400B0F72
0x1400b0f6a  mov     rcx, rsi; P
0x1400b0f6d  call    DeleteKey
0x1400b0f72  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b0f79  cmp     rcx, r12
0x1400b0f7c  jz      short loc_1400B0FA3
0x1400b0f7e  mov     eax, [rcx+2Ch]
0x1400b0f81  test    al, 4
0x1400b0f83  jz      short loc_1400B0FA3
0x1400b0f85  cmp     byte ptr [rcx+29h], 5
0x1400b0f89  jb      short loc_1400B0FA3
0x1400b0f8b  mov     rcx, [rcx+18h]
0x1400b0f8f  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400b0f96  mov     edx, 6Ch ; 'l'
0x1400b0f9b  mov     r9d, ebx
0x1400b0f9e  call    WPP_SF_d
0x1400b0fa3  mov     eax, ebx
0x1400b0fa5  mov     rcx, [rbp+0F0h+var_50]
0x1400b0fac  xor     rcx, rsp; StackCookie
0x1400b0faf  call    __security_check_cookie
0x1400b0fb4  add     rsp, 1B8h
0x1400b0fbb  pop     r15
0x1400b0fbd  pop     r14
0x1400b0fbf  pop     r13
0x1400b0fc1  pop     r12
0x1400b0fc3  pop     rdi
0x1400b0fc4  pop     rsi
0x1400b0fc5  pop     rbx
0x1400b0fc6  pop     rbp
0x1400b0fc7  retn
0x1400b0fc9  mov     r9d, [rbp+0F0h+arg_30]
0x1400b0fd0  mov     r8d, 3
0x1400b0fd6  mov     rdx, [rdi+70h]
0x1400b0fda  mov     rcx, rdi
0x1400b0fdd  mov     [rsp+1F0h+var_1B8], rsi
0x1400b0fe2  mov     [rsp+1F0h+var_1C0], r14d
0x1400b0fe7  mov     [rsp+1F0h+var_1C8], rbx
0x1400b0fec  mov     [rsp+1F0h+BugCheckParameter4], rbx
0x1400b0ff1  mov     [rsp+1F0h+Source2], rbx
0x1400b0ff6  call    FveRawIoSynchronous
0x1400b0ffb  mov     ebx, eax
0x1400b0ffd  call    Feature_BitLockerEphemeralVolumeSupport__private_IsEnabledDeviceUsageNoInline
0x1400b1002  test    eax, eax
0x1400b1004  jz      short loc_1400B1071
0x1400b1006  test    ebx, ebx
0x1400b1008  js      loc_1400B1828
0x1400b100e  test    byte ptr [rdi+1133h], 10h
0x1400b1015  jz      short loc_1400B1079
0x1400b1017  mov     [rsp+1F0h+var_1C8], 0
0x1400b1020  lea     rdx, [rbp+0F0h+var_150]
0x1400b1024  xor     r9d, r9d
0x1400b1027  mov     [rsp+1F0h+BugCheckParameter4], 0
0x1400b1030  mov     r8b, 1
0x1400b1033  mov     rcx, rdi
0x1400b1036  call    InitializeFilterData
0x1400b103b  lea     rax, FveFilteredRead
0x1400b1042  mov     [rbp+0F0h+var_140], 0
0x1400b104a  lea     rcx, [rbp+0F0h+var_150]
0x1400b104e  mov     [rbp+0F0h+var_F8], rax
0x1400b1052  mov     [rbp+0F0h+var_E0], r14d
0x1400b1056  mov     [rbp+0F0h+var_F0], rsi
0x1400b105a  mov     [rbp+0F0h+var_E8], rsi
0x1400b105e  call    FveParseBlockAndFilter
0x1400b1063  lea     rdx, [rbp+0F0h+var_150]
0x1400b1067  mov     rcx, rdi
0x1400b106a  mov     ebx, eax
0x1400b106c  call    DeInitializeFilterData
0x1400b1071  test    ebx, ebx
0x1400b1073  js      loc_1400B1828
0x1400b1079  cmp     r15d, 2
0x1400b107d  jnz     short loc_1400B10EA
0x1400b107f  test    r13, r13
0x1400b1082  jnz     short loc_1400B108E
0x1400b1084  mov     ebx, 0C000000Dh
0x1400b1089  jmp     loc_1400B185C
0x1400b108e  xor     edx, edx
0x1400b1090  lea     rax, [rdx+rdx*2]
0x1400b1094  mov     rcx, [r13+rax*8+0]
0x1400b1099  mov     [rbp+rdx*8+0F0h+var_168], rcx
0x1400b109e  inc     rdx
0x1400b10a1  cmp     rdx, 3
0x1400b10a5  jnz     short loc_1400B1090
0x1400b10a7  lea     r8, [rbp+0F0h+var_168]
0x1400b10ab  mov     rcx, rsi
0x1400b10ae  call    FveBuildBootSector
0x1400b10b3  call    Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline
0x1400b10b8  test    eax, eax
0x1400b10ba  jz      loc_1400B1382
0x1400b10c0  mov     edx, r14d
0x1400b10c3  mov     rcx, rsi
0x1400b10c6  call    FveFindGuidRecognition
0x1400b10cb  test    rax, rax
0x1400b10ce  jz      loc_1400B1382
0x1400b10d4  sub     eax, esi
0x1400b10d6  lea     ecx, [rax+38h]
0x1400b10d9  lea     eax, [rcx+48h]
0x1400b10dc  cmp     eax, r14d
0x1400b10df  ja      loc_1400B1382
0x1400b10e5  jmp     loc_1400B1375
0x1400b10ea  cmp     r15d, 3
0x1400b10ee  jnz     loc_1400B130A
0x1400b10f4  test    r13, r13
0x1400b10f7  jz      short loc_1400B1084
0x1400b10f9  cmp     [rsp+1F0h+var_198], 0
0x1400b10ff  jz      short loc_1400B1084
0x1400b1101  xor     edx, edx
0x1400b1103  lea     rax, [rdx+rdx*2]
0x1400b1107  mov     rcx, [r13+rax*8+0]
0x1400b110c  mov     [rbp+rdx*8+0F0h+var_168], rcx
0x1400b1111  inc     rdx
0x1400b1114  cmp     rdx, 3
0x1400b1118  jnz     short loc_1400B1103
0x1400b111a  mov     r9, [rsp+1F0h+var_198]
0x1400b111f  lea     r8, [rbp+0F0h+var_168]
0x1400b1123  mov     rcx, rsi
0x1400b1126  call    FveEowBuildBootSector
0x1400b112b  call    Feature_BitLocker_MetadataV3Shadow__private_IsEnabledDeviceUsageNoInline
0x1400b1130  test    eax, eax
0x1400b1132  jz      loc_1400B1382
0x1400b1138  mov     r13, [rsp+1F0h+var_180]
0x1400b113d  test    r13, r13
0x1400b1140  jz      loc_1400B1382
0x1400b1146  mov     edx, r14d
0x1400b1149  mov     rcx, rsi
0x1400b114c  call    FveEowFindGuidRecognition
0x1400b1151  test    rax, rax
0x1400b1154  jz      loc_1400B1382
0x1400b115a  sub     eax, esi
0x1400b115c  lea     r15d, [rax+38h]
0x1400b1160  lea     eax, [r15+48h]
0x1400b1164  cmp     eax, r14d
0x1400b1167  ja      loc_1400B12BF
0x1400b116d  mov     ebx, r15d
0x1400b1170  mov     r8, r12; Size
0x1400b1173  add     rbx, rsi
0x1400b1176  xor     edx, edx; Val
0x1400b1178  mov     rcx, rbx; void *
0x1400b117b  call    memset
0x1400b1180  movups  xmm0, cs:FVE_V3_RECOGNITION_GUID
0x1400b1187  xor     ecx, ecx
0x1400b1189  movdqu  xmmword ptr [rbx], xmm0
0x1400b118d  lea     r12d, [rcx+1]
0x1400b1191  mov     rax, [r13+rcx*8+0]
0x1400b1196  mov     [rbx+rcx*8+20h], rax
0x1400b119b  add     rcx, r12
0x1400b119e  cmp     rcx, 2
0x1400b11a2  jnz     short loc_1400B1191
0x1400b11a4  mov     rcx, [rbp+0F0h+arg_20]
0x1400b11ab  test    rcx, rcx
0x1400b11ae  jnz     short loc_1400B11BC
0x1400b11b0  mov     rcx, [rdi+3D0h]
0x1400b11b7  test    rcx, rcx
0x1400b11ba  jz      short loc_1400B122C
0x1400b11bc  mov     rax, [rcx+38h]
0x1400b11c0  mov     [rbx+30h], rax
0x1400b11c4  cmp     [rcx+0Ah], r12w
0x1400b11c9  jnz     short loc_1400B11CF
0x1400b11cb  xor     eax, eax
0x1400b11cd  jmp     short loc_1400B11D8
0x1400b11cf  mov     eax, [rcx+1Ch]
0x1400b11d2  test    eax, eax
0x1400b11d4  cmovz   eax, r12d
0x1400b11d8  mov     ecx, [rdi+51Ch]
0x1400b11de  lea     rdx, [rbx+40h]; pulResult
0x1400b11e2  imul    rcx, rax; ullOperand
0x1400b11e6  call    RtlULongLongToULong
0x1400b11eb  test    eax, eax
0x1400b11ed  jns     short loc_1400B1262
0x1400b11ef  mov     dword ptr [rdx], 0
0x1400b11f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b11fc  lea     r13, WPP_GLOBAL_Control
0x1400b1203  cmp     rcx, r13
0x1400b1206  jz      short loc_1400B1269
0x1400b1208  mov     eax, [rcx+2Ch]
0x1400b120b  test    al, 4
0x1400b120d  jz      short loc_1400B1269
0x1400b120f  cmp     byte ptr [rcx+29h], 2
0x1400b1213  jb      short loc_1400B1269
0x1400b1215  mov     edx, 66h ; 'f'
0x1400b121a  mov     rcx, [rcx+18h]
0x1400b121e  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400b1225  call    WPP_SF_
0x1400b122a  jmp     short loc_1400B1269
0x1400b122c  mov     qword ptr [rbx+30h], 0
0x1400b1234  mov     dword ptr [rbx+40h], 0
0x1400b123b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1242  lea     r13, WPP_GLOBAL_Control
0x1400b1249  cmp     rcx, r13
0x1400b124c  jz      short loc_1400B1269
0x1400b124e  mov     eax, [rcx+2Ch]
0x1400b1251  test    al, 4
0x1400b1253  jz      short loc_1400B1269
0x1400b1255  cmp     byte ptr [rcx+29h], 2
0x1400b1259  jb      short loc_1400B1269
0x1400b125b  mov     edx, 67h ; 'g'
0x1400b1260  jmp     short loc_1400B121A
0x1400b1262  lea     r13, WPP_GLOBAL_Control
0x1400b1269  mov     rax, [rdi+4E8h]
0x1400b1270  mov     [rbx+38h], rax
0x1400b1274  mov     eax, [rdi+4F0h]
0x1400b127a  mov     [rbx+44h], eax
0x1400b127d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b1284  cmp     rcx, r13
0x1400b1287  jz      loc_1400B1388
0x1400b128d  mov     eax, [rcx+2Ch]
0x1400b1290  test    al, 4
0x1400b1292  jz      loc_1400B1388
0x1400b1298  cmp     byte ptr [rcx+29h], 5
0x1400b129c  jb      loc_1400B1388
0x1400b12a2  mov     rcx, [rcx+18h]
0x1400b12a6  lea     r8, WPP_e9aaac2b238d37cd29946d0a13c61cb1_Traceguids
0x1400b12ad  mov     edx, 68h ; 'h'
0x1400b12b2  mov     r9d, r15d
0x1400b12b5  call    WPP_SF_d
0x1400b12ba  jmp     loc_1400B1388
0x1400b12bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b12c6  lea     r13, WPP_GLOBAL_Control
0x1400b12cd  cmp     rcx, r13
0x1400b12d0  jz      loc_1400B1382
0x1400b12d6  mov     eax, [rcx+2Ch]
0x1400b12d9  test    al, 4
0x1400b12db  jz      loc_1400B1382
0x1400b12e1  cmp     byte ptr [rcx+29h], 3
0x1400b12e5  jb      loc_1400B1382
0x1400b12eb  mov     rcx, [rcx+18h]
  ... truncated ...
```
