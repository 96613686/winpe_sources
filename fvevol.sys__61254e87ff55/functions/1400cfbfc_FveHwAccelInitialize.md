# FveHwAccelInitialize

- ea: `0x1400cfbfc`
- end: `0x1400d03ff`
- name: `FveHwAccelInitialize`
- size: `2051`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400cf1d4`

## callees

- `0x140008e80`
- `0x140008f04`
- `0x14000c9ec`
- `0x14000d690`
- `0x140012350`
- `0x1400223bc`
- `0x140023040`
- `0x1400cfbfc`

## import_xrefs

- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400d01c0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400d021b`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400d01c0`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x1400d021b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400d033b`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x1400d033b`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d00f3`
- `ntoskrnl!KeGetRecommendedSharedDataAlignment` at `0x1400d00f3`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cfead`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0327`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d034f`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400cfead`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d0327`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400d034f`
- `ntoskrnl!ExAllocatePool2` at `0x1400cfd61`
- `ntoskrnl!ExAllocatePool2` at `0x1400cfec3`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0143`
- `ntoskrnl!ExAllocatePool2` at `0x1400d01d7`
- `ntoskrnl!ExAllocatePool2` at `0x1400cfd61`
- `ntoskrnl!ExAllocatePool2` at `0x1400cfec3`
- `ntoskrnl!ExAllocatePool2` at `0x1400d0143`
- `ntoskrnl!ExAllocatePool2` at `0x1400d01d7`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeOffloadWorkspace` at `0x1400cfcf8`
- `ext-ms-win-accel-api-km-l1-1-1!AccelInitializeOffloadWorkspace` at `0x1400cfcf8`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400d030e`
- `ext-ms-win-accel-api-km-l1-1-1!AccelDestroyOffloadWorkspace` at `0x1400d030e`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400d02ee`
- `ext-ms-win-accel-api-km-l1-1-1!AccelCloseResource` at `0x1400d02ee`
- `ext-ms-win-accel-api-km-l1-1-1!AccelQueryDescriptorSize` at `0x1400d0096`
- `ext-ms-win-accel-api-km-l1-1-1!AccelQueryDescriptorSize` at `0x1400d0096`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cfe2d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cffe6`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cfe2d`
- `ext-ms-win-accel-api-km-l1-1-1!AccelAcquireResourcesSync` at `0x1400cffe6`

## pseudocode

```c
__int64 __fastcall FveHwAccelInitialize(__int64 a1)
{
  struct _NPAGED_LOOKASIDE_LIST *v3; // r12
  unsigned __int8 v4; // di
  int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  int v9; // ebx
  void *Pool2; // r15
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // ebx
  bool v15; // zf
  __int64 v16; // r13
  int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // edi
  PDEVICE_OBJECT v20; // rcx
  __int64 v21; // rdi
  PDEVICE_OBJECT v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  int v25; // eax
  int v26; // eax
  ULONG RecommendedSharedDataAlignment; // eax
  int v28; // r8d
  struct _NPAGED_LOOKASIDE_LIST *v29; // rax
  struct _NPAGED_LOOKASIDE_LIST *v30; // r14
  __int64 v31; // r8
  __int64 v32; // rax
  __int64 v33; // rdx
  __int64 *v34; // r8
  int Size; // [rsp+20h] [rbp-99h]
  __int128 v36; // [rsp+40h] [rbp-79h] BYREF
  __int128 v37; // [rsp+50h] [rbp-69h]
  __int128 v38; // [rsp+60h] [rbp-59h] BYREF
  __int128 v39; // [rsp+70h] [rbp-49h]
  _QWORD v40[18]; // [rsp+80h] [rbp-39h] BYREF
  SIZE_T v41; // [rsp+128h] [rbp+6Fh] BYREF
  __int64 v42; // [rsp+130h] [rbp+77h] BYREF

  v38 = 0;
  v39 = 0;
  memset(v40, 0, 0x58u);
  v36 = 0;
  v42 = 0;
  v37 = 0;
  LODWORD(v41) = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
  }
  if ( !*(_BYTE *)(a1 + 10704) )
  {
    *(_QWORD *)&v38 = 2097153;
    *(_BYTE *)(a1 + 10704) = 1;
    *(_QWORD *)&v39 = 0;
    *((_QWORD *)&v38 + 1) = &GUID_FVE_HW_OFFLOAD_WORKSPACE;
    v3 = 0;
    *((_QWORD *)&v39 + 1) = *(_QWORD *)a1;
    v4 = 0;
    v5 = AccelInitializeOffloadWorkspace(&v38, &v42);
    v9 = v5;
    if ( v5 < 0 )
    {
      Pool2 = 0;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v12 = 22;
        v13 = (unsigned int)v5;
LABEL_16:
        WPP_SF_d(v11->AttachedDevice, v12, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v13);
        goto LABEL_90;
      }
      goto LABEL_90;
    }
    v14 = 8;
    Pool2 = (void *)ExAllocatePool2(64, 8, 1749374534);
    if ( !Pool2 )
    {
      v7 = 3221225626LL;
      v9 = -1073741670;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v12 = 23;
        v13 = 3221225626LL;
        goto LABEL_16;
      }
LABEL_90:
      if ( v42 )
        AccelDestroyOffloadWorkspace(v42, v6, v7, v8, Size);
      if ( Pool2 )
        ExFreePoolWithTag(Pool2, 0x68455646u);
      if ( v3 )
      {
        ExDeleteNPagedLookasideList(v3);
        ExFreePoolWithTag(v3, 0x68455646u);
      }
      if ( v9 < 0 )
      {
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
          return (unsigned int)v9;
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_LLL(
            WPP_GLOBAL_Control->AttachedDevice,
            32,
            WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
            (unsigned int)v9,
            v4,
            (*(_DWORD *)(a1 + 9928) >> 23) & 1);
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(
          WPP_GLOBAL_Control->AttachedDevice,
          33,
          WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
          (unsigned int)v9);
      }
      return (unsigned int)v9;
    }
    v15 = (*(_DWORD *)(a1 + 9928) & 0x800000) == 0;
    v16 = 0;
    v40[1] = v42;
    v40[2] = &GUID_ACCELERATOR_TYPE_CRYPTO;
    v40[5] = FveHwAccelNotifyCallback;
    v40[0] = 5767169;
    v40[7] = 0x10000;
    v40[6] = a1;
    v40[3] = 0x100000001LL;
    v40[4] = 0;
    memset(&v40[8], 0, 24);
    v36 = 0x200001u;
    *((_QWORD *)&v37 + 1) = 8;
    *(_QWORD *)&v37 = Pool2;
    if ( v15 )
    {
      v17 = AccelAcquireResourcesSync(v40, &v36);
      v9 = v17;
      if ( v17 == -1073741632 )
      {
        v9 = 0;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
        }
        goto LABEL_90;
      }
      if ( v17 != -1073741789 )
        goto LABEL_49;
      v14 = DWORD2(v37);
    }
    ExFreePoolWithTag(Pool2, 0x68455646u);
    v18 = ExAllocatePool2(64, v14, 1749374534);
    Pool2 = (void *)v18;
    if ( !v18 )
    {
      v9 = -1073741670;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            25,
            WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
            3221225626LL);
        goto LABEL_50;
      }
LABEL_84:
      v34 = FVE_HW_ACCEL_CRYPTO_INITIALIZED;
      if ( v9 < 0 )
        v34 = FVE_HW_ACCEL_CRYPTO_INITIALIZED_FAILED;
      Size = v41;
      FveLogStatusEventWithData(a1, 0, v34);
      if ( v16 && (*(_DWORD *)(a1 + 9928) & 0x800000) == 0 )
        AccelCloseResource(v16);
      v4 = 1;
      goto LABEL_90;
    }
    v15 = (*(_DWORD *)(a1 + 9928) & 0x800000) == 0;
    v36 = 0x200001u;
    *(_QWORD *)&v37 = v18;
    *((_QWORD *)&v37 + 1) = v14;
    if ( !v15 )
    {
      v9 = 0;
      goto LABEL_38;
    }
    v9 = AccelAcquireResourcesSync(v40, &v36);
LABEL_49:
    if ( v9 < 0 )
    {
LABEL_50:
      v22 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
        || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
      {
        goto LABEL_84;
      }
      v23 = 26;
      v24 = (unsigned int)v9;
      goto LABEL_54;
    }
LABEL_38:
    v19 = DWORD2(v36);
    if ( (*(_DWORD *)(a1 + 9928) & 0x800000) != 0 )
      v19 = 1;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v19);
    }
    if ( v19 <= 1 )
    {
      if ( !v19 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            28,
            WPP_7f5e3a43786933c00401282694ab6ced_Traceguids,
            (unsigned int)v9);
        }
        v9 = -1073741667;
        goto LABEL_84;
      }
    }
    else
    {
      MicrosoftTelemetryAssertTriggeredArgsMsgKM(v20, v19);
    }
    v21 = *(_QWORD *)v37;
    v16 = *(_QWORD *)v37;
    if ( (*(_DWORD *)(a1 + 9928) & 0x800000) != 0 )
    {
      v9 = 0;
    }
    else
    {
      v25 = AccelQueryDescriptorSize(*(_QWORD *)v37, &v41);
      v9 = v25;
      if ( v25 < 0 )
      {
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_84;
        }
        v23 = 29;
        v24 = (unsigned int)v25;
        goto LABEL_54;
      }
      v26 = v41;
      if ( (unsigned int)v41 > 8 )
      {
LABEL_68:
        LODWORD(v41) = v26;
        RecommendedSharedDataAlignment = KeGetRecommendedSharedDataAlignment();
        if ( ((RecommendedSharedDataAlignment - 1) & RecommendedSharedDataAlignment) != 0
          || !RecommendedSharedDataAlignment )
        {
          v28 = v41;
          if ( (unsigned int)v41 % RecommendedSharedDataAlignment )
            v28 = RecommendedSharedDataAlignment - (unsigned int)v41 % RecommendedSharedDataAlignment + v41;
        }
        else
        {
          v28 = ~(RecommendedSharedDataAlignment - 1) & (RecommendedSharedDataAlignment + v41 - 1);
        }
        LODWORD(v41) = v28;
        v29 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 1749374534);
        v3 = v29;
        if ( v29 )
        {
          ExInitializeNPagedLookasideList(v29, 0, 0, 0x200u, (unsigned int)v41, 0x68455646u, 0);
          v30 = (struct _NPAGED_LOOKASIDE_LIST *)ExAllocatePool2(64, 128, 1749374534);
          if ( v30 )
          {
            ExInitializeNPagedLookasideList(v30, 0, 0, 0x200u, 0xA0u, 0x68455646u, 0);
            v32 = v42;
            v16 = 0;
            v33 = (unsigned int)v41;
            *(_QWORD *)(a1 + 10712) = v3;
            v3 = 0;
            *(_QWORD *)(a1 + 10728) = v32;
            v42 = 0;
            *(_QWORD *)(a1 + 10736) = v21;
            *(_QWORD *)(a1 + 10720) = v30;
            *(_DWORD *)(a1 + 10744) = v33;
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
              && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
            {
              WPP_SF_qLd(WPP_GLOBAL_Control->AttachedDevice, v33, v31, v21, v33, (*(_DWORD *)(a1 + 9928) >> 23) & 1);
            }
          }
          else
          {
            v9 = -1073741670;
          }
          goto LABEL_84;
        }
        v9 = -1073741670;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) == 0
          || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
        {
          goto LABEL_84;
        }
        v23 = 30;
        v24 = 3221225626LL;
LABEL_54:
        WPP_SF_d(v22->AttachedDevice, v23, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids, v24);
        goto LABEL_84;
      }
    }
    v26 = 8;
    goto LABEL_68;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1400cfbfc  mov     [rsp-8+arg_18], rbx
0x1400cfc01  push    rbp
0x1400cfc02  push    rsi
0x1400cfc03  push    rdi
0x1400cfc04  push    r12
0x1400cfc06  push    r13
0x1400cfc08  push    r14
0x1400cfc0a  push    r15
0x1400cfc0c  lea     rbp, [rsp-27h]
0x1400cfc11  sub     rsp, 0E0h
0x1400cfc18  xorps   xmm0, xmm0
0x1400cfc1b  xor     edx, edx; Val
0x1400cfc1d  mov     rsi, rcx
0x1400cfc20  lea     rcx, [rbp+57h+var_90]; void *
0x1400cfc24  movups  [rbp+57h+var_B0], xmm0
0x1400cfc28  lea     r8d, [rdx+58h]; Size
0x1400cfc2c  movups  [rbp+57h+var_A0], xmm0
0x1400cfc30  call    memset
0x1400cfc35  xorps   xmm0, xmm0
0x1400cfc38  xor     r14d, r14d
0x1400cfc3b  movups  [rbp+57h+var_D0], xmm0
0x1400cfc3f  mov     [rbp+57h+arg_10], r14
0x1400cfc43  movups  [rbp+57h+var_C0], xmm0
0x1400cfc47  mov     dword ptr [rbp+57h+arg_8], r14d
0x1400cfc4b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfc52  lea     r13, WPP_GLOBAL_Control
0x1400cfc59  cmp     rcx, r13
0x1400cfc5c  jz      short loc_1400CFC81
0x1400cfc5e  test    dword ptr [rcx+2Ch], 400000h
0x1400cfc65  jz      short loc_1400CFC81
0x1400cfc67  cmp     byte ptr [rcx+29h], 5
0x1400cfc6b  jb      short loc_1400CFC81
0x1400cfc6d  mov     rcx, [rcx+18h]
0x1400cfc71  lea     edx, [r14+14h]
0x1400cfc75  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cfc7c  call    WPP_SF_
0x1400cfc81  cmp     [rsi+29D0h], r14b
0x1400cfc88  jz      short loc_1400CFCC1
0x1400cfc8a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfc91  cmp     rcx, r13
0x1400cfc94  jz      short loc_1400CFCBA
0x1400cfc96  test    dword ptr [rcx+2Ch], 400000h
0x1400cfc9d  jz      short loc_1400CFCBA
0x1400cfc9f  cmp     byte ptr [rcx+29h], 4
0x1400cfca3  jb      short loc_1400CFCBA
0x1400cfca5  mov     rcx, [rcx+18h]
0x1400cfca9  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cfcb0  mov     edx, 15h
0x1400cfcb5  call    WPP_SF_
0x1400cfcba  xor     eax, eax
0x1400cfcbc  jmp     loc_1400D03E3
0x1400cfcc1  mov     eax, 1
0x1400cfcc6  mov     qword ptr [rbp+57h+var_B0], 200001h
0x1400cfcce  mov     [rsi+29D0h], al
0x1400cfcd4  lea     rdx, [rbp+57h+arg_10]
0x1400cfcd8  lea     rax, GUID_FVE_HW_OFFLOAD_WORKSPACE
0x1400cfcdf  mov     qword ptr [rbp+57h+var_A0], r14
0x1400cfce3  mov     qword ptr [rbp+57h+var_B0+8], rax
0x1400cfce7  lea     rcx, [rbp+57h+var_B0]
0x1400cfceb  mov     rax, [rsi]
0x1400cfcee  mov     r12, r14
0x1400cfcf1  mov     qword ptr [rbp+57h+var_A0+8], rax
0x1400cfcf5  mov     dil, r14b
0x1400cfcf8  call    cs:__imp_AccelInitializeOffloadWorkspace
0x1400cfcff  nop     dword ptr [rax+rax+00h]
0x1400cfd04  mov     ebx, eax
0x1400cfd06  test    eax, eax
0x1400cfd08  jns     short loc_1400CFD51
0x1400cfd0a  mov     r15, r14
0x1400cfd0d  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfd14  cmp     rcx, r13
0x1400cfd17  jz      loc_1400D0305
0x1400cfd1d  test    dword ptr [rcx+2Ch], 400000h
0x1400cfd24  jz      loc_1400D0305
0x1400cfd2a  cmp     byte ptr [rcx+29h], 2
0x1400cfd2e  jb      loc_1400D0305
0x1400cfd34  mov     edx, 16h
0x1400cfd39  mov     r9d, eax
0x1400cfd3c  mov     rcx, [rcx+18h]
0x1400cfd40  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cfd47  call    WPP_SF_d
0x1400cfd4c  jmp     loc_1400D0305
0x1400cfd51  mov     ebx, 8
0x1400cfd56  mov     r8d, 68455646h
0x1400cfd5c  mov     edx, ebx
0x1400cfd5e  lea     ecx, [rbx+38h]
0x1400cfd61  call    cs:__imp_ExAllocatePool2
0x1400cfd68  nop     dword ptr [rax+rax+00h]
0x1400cfd6d  mov     r15, rax
0x1400cfd70  test    rax, rax
0x1400cfd73  jnz     short loc_1400CFDAD
0x1400cfd75  mov     r8d, 0C000009Ah
0x1400cfd7b  mov     ebx, r8d
0x1400cfd7e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfd85  cmp     rcx, r13
0x1400cfd88  jz      loc_1400D0305
0x1400cfd8e  test    dword ptr [rcx+2Ch], 400000h
0x1400cfd95  jz      loc_1400D0305
0x1400cfd9b  cmp     byte ptr [rcx+29h], 2
0x1400cfd9f  jb      loc_1400D0305
0x1400cfda5  lea     edx, [rax+17h]
0x1400cfda8  mov     r9d, r8d
0x1400cfdab  jmp     short loc_1400CFD3C
0x1400cfdad  test    dword ptr [rsi+26C8h], 800000h
0x1400cfdb7  mov     ecx, 1
0x1400cfdbc  mov     rax, [rbp+57h+arg_10]
0x1400cfdc0  mov     r13, r14
0x1400cfdc3  mov     [rbp+57h+var_88], rax
0x1400cfdc7  lea     rax, GUID_ACCELERATOR_TYPE_CRYPTO
0x1400cfdce  mov     [rbp+57h+var_80], rax
0x1400cfdd2  lea     rax, FveHwAccelNotifyCallback
0x1400cfdd9  mov     [rbp+57h+var_68], rax
0x1400cfddd  mov     [rbp+57h+var_90], 580001h
0x1400cfde5  mov     [rbp+57h+var_58], 10000h
0x1400cfded  mov     [rbp+57h+var_60], rsi
0x1400cfdf1  mov     [rbp+57h+var_78], ecx
0x1400cfdf4  mov     [rbp+57h+var_74], ecx
0x1400cfdf7  mov     [rbp+57h+var_70], r14
0x1400cfdfb  mov     [rbp+57h+var_50], r14
0x1400cfdff  mov     [rbp+57h+var_48], r14
0x1400cfe03  mov     [rbp+57h+var_40], r14
0x1400cfe07  mov     qword ptr [rbp+57h+var_D0+4], r14
0x1400cfe0b  mov     dword ptr [rbp+57h+var_D0+0Ch], r14d
0x1400cfe0f  mov     qword ptr [rbp+57h+var_C0+8], rbx
0x1400cfe13  mov     dword ptr [rbp+57h+var_D0], 200001h
0x1400cfe1a  mov     qword ptr [rbp+57h+var_C0], r15
0x1400cfe1e  jz      short loc_1400CFE25
0x1400cfe20  mov     [rbp+57h+arg_0], cl
0x1400cfe23  jmp     short loc_1400CFEA3
0x1400cfe25  lea     rdx, [rbp+57h+var_D0]
0x1400cfe29  lea     rcx, [rbp+57h+var_90]
0x1400cfe2d  call    cs:__imp_AccelAcquireResourcesSync
0x1400cfe34  nop     dword ptr [rax+rax+00h]
0x1400cfe39  mov     ebx, eax
0x1400cfe3b  cmp     eax, 0C00000C0h
0x1400cfe40  jnz     short loc_1400CFE8D
0x1400cfe42  mov     ebx, r14d
0x1400cfe45  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfe4c  lea     r13, WPP_GLOBAL_Control
0x1400cfe53  cmp     rcx, r13
0x1400cfe56  jz      loc_1400D0305
0x1400cfe5c  test    dword ptr [rcx+2Ch], 400000h
0x1400cfe63  jz      loc_1400D0305
0x1400cfe69  cmp     byte ptr [rcx+29h], 4
0x1400cfe6d  jb      loc_1400D0305
0x1400cfe73  mov     rcx, [rcx+18h]
0x1400cfe77  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cfe7e  mov     edx, 18h
0x1400cfe83  call    WPP_SF_
0x1400cfe88  jmp     loc_1400D0305
0x1400cfe8d  mov     ecx, 1
0x1400cfe92  mov     [rbp+57h+arg_0], cl
0x1400cfe95  cmp     eax, 0C0000023h
0x1400cfe9a  jnz     loc_1400CFFF9
0x1400cfea0  mov     ebx, dword ptr [rbp+57h+var_C0+8]
0x1400cfea3  mov     edi, 68455646h
0x1400cfea8  mov     rcx, r15; P
0x1400cfeab  mov     edx, edi; Tag
0x1400cfead  call    cs:__imp_ExFreePoolWithTag
0x1400cfeb4  nop     dword ptr [rax+rax+00h]
0x1400cfeb9  mov     edx, ebx
0x1400cfebb  mov     r8d, edi
0x1400cfebe  mov     ecx, 40h ; '@'
0x1400cfec3  call    cs:__imp_ExAllocatePool2
0x1400cfeca  nop     dword ptr [rax+rax+00h]
0x1400cfecf  mov     r15, rax
0x1400cfed2  test    rax, rax
0x1400cfed5  jnz     short loc_1400CFF29
0x1400cfed7  mov     r8d, 0C000009Ah
0x1400cfedd  mov     ebx, r8d
0x1400cfee0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cfee7  lea     rdi, WPP_GLOBAL_Control
0x1400cfeee  cmp     rcx, rdi
0x1400cfef1  jz      loc_1400D02A3
0x1400cfef7  test    dword ptr [rcx+2Ch], 400000h
0x1400cfefe  jz      loc_1400D0008
0x1400cff04  cmp     byte ptr [rcx+29h], 2
0x1400cff08  jb      loc_1400D0008
0x1400cff0e  mov     rcx, [rcx+18h]
0x1400cff12  lea     edx, [rax+19h]
0x1400cff15  mov     r9d, r8d
0x1400cff18  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cff1f  call    WPP_SF_d
0x1400cff24  jmp     loc_1400D0008
0x1400cff29  test    dword ptr [rsi+26C8h], 800000h
0x1400cff33  mov     ecx, 1
0x1400cff38  mov     qword ptr [rbp+57h+var_D0+4], r14
0x1400cff3c  mov     dword ptr [rbp+57h+var_D0+0Ch], r14d
0x1400cff40  mov     dword ptr [rbp+57h+var_C0+0Ch], r14d
0x1400cff44  mov     dword ptr [rbp+57h+var_D0], 200001h
0x1400cff4b  mov     qword ptr [rbp+57h+var_C0], rax
0x1400cff4f  mov     dword ptr [rbp+57h+var_C0+8], ebx
0x1400cff52  jz      loc_1400CFFDE
0x1400cff58  mov     ebx, r14d
0x1400cff5b  test    dword ptr [rsi+26C8h], 800000h
0x1400cff65  mov     edi, dword ptr [rbp+57h+var_D0+8]
0x1400cff68  cmovnz  edi, ecx
0x1400cff6b  mov     rcx, cs:WPP_GLOBAL_Control
0x1400cff72  lea     rax, WPP_GLOBAL_Control
0x1400cff79  cmp     rcx, rax
0x1400cff7c  jz      short loc_1400CFFAC
0x1400cff7e  test    dword ptr [rcx+2Ch], 400000h
0x1400cff85  jz      short loc_1400CFFA5
0x1400cff87  cmp     byte ptr [rcx+29h], 4
0x1400cff8b  jb      short loc_1400CFFA5
0x1400cff8d  mov     rcx, [rcx+18h]
0x1400cff91  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400cff98  mov     edx, 1Bh
0x1400cff9d  mov     r9d, edi
0x1400cffa0  call    WPP_SF_d
0x1400cffa5  lea     rax, WPP_GLOBAL_Control
0x1400cffac  cmp     edi, 1
0x1400cffaf  jbe     loc_1400D004C
0x1400cffb5  mov     edx, edi
0x1400cffb7  call    MicrosoftTelemetryAssertTriggeredArgsMsgKM
0x1400cffbc  test    dword ptr [rsi+26C8h], 800000h
0x1400cffc6  mov     rax, qword ptr [rbp+57h+var_C0]
0x1400cffca  mov     rdi, [rax]
0x1400cffcd  mov     r13, rdi
0x1400cffd0  jz      loc_1400D008F
0x1400cffd6  mov     ebx, r14d
0x1400cffd9  jmp     loc_1400D00EB
0x1400cffde  lea     rdx, [rbp+57h+var_D0]
0x1400cffe2  lea     rcx, [rbp+57h+var_90]
0x1400cffe6  call    cs:__imp_AccelAcquireResourcesSync
0x1400cffed  nop     dword ptr [rax+rax+00h]
0x1400cfff2  mov     ebx, eax
0x1400cfff4  mov     ecx, 1
0x1400cfff9  test    ebx, ebx
0x1400cfffb  jns     loc_1400CFF5B
0x1400d0001  lea     rdi, WPP_GLOBAL_Control
0x1400d0008  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d000f  cmp     rcx, rdi
0x1400d0012  jz      loc_1400D02A3
0x1400d0018  test    dword ptr [rcx+2Ch], 400000h
0x1400d001f  jz      loc_1400D02A3
0x1400d0025  cmp     byte ptr [rcx+29h], 2
0x1400d0029  jb      loc_1400D02A3
0x1400d002f  mov     edx, 1Ah
0x1400d0034  mov     r9d, ebx
0x1400d0037  mov     rcx, [rcx+18h]
0x1400d003b  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d0042  call    WPP_SF_d
0x1400d0047  jmp     loc_1400D02A3
0x1400d004c  test    edi, edi
0x1400d004e  jnz     loc_1400CFFBC
0x1400d0054  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d005b  cmp     rcx, rax
0x1400d005e  jz      short loc_1400D0085
0x1400d0060  test    dword ptr [rcx+2Ch], 400000h
0x1400d0067  jz      short loc_1400D0085
0x1400d0069  cmp     byte ptr [rcx+29h], 2
0x1400d006d  jb      short loc_1400D0085
0x1400d006f  mov     rcx, [rcx+18h]
0x1400d0073  lea     edx, [rdi+1Ch]
0x1400d0076  mov     r9d, ebx
0x1400d0079  lea     r8, WPP_7f5e3a43786933c00401282694ab6ced_Traceguids
0x1400d0080  call    WPP_SF_d
0x1400d0085  mov     ebx, 0C000009Dh
0x1400d008a  jmp     loc_1400D02A3
0x1400d008f  lea     rdx, [rbp+57h+arg_8]
0x1400d0093  mov     rcx, rdi
0x1400d0096  call    cs:__imp_AccelQueryDescriptorSize
0x1400d009d  nop     dword ptr [rax+rax+00h]
0x1400d00a2  mov     ebx, eax
0x1400d00a4  test    eax, eax
0x1400d00a6  jns     short loc_1400D00E3
0x1400d00a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400d00af  lea     rdi, WPP_GLOBAL_Control
0x1400d00b6  cmp     rcx, rdi
0x1400d00b9  jz      loc_1400D02A3
0x1400d00bf  test    dword ptr [rcx+2Ch], 400000h
0x1400d00c6  jz      loc_1400D02A3
0x1400d00cc  cmp     byte ptr [rcx+29h], 2
0x1400d00d0  jb      loc_1400D02A3
0x1400d00d6  mov     edx, 1Dh
0x1400d00db  mov     r9d, eax
0x1400d00de  jmp     loc_1400D0037
0x1400d00e3  mov     eax, dword ptr [rbp+57h+arg_8]
0x1400d00e6  cmp     eax, 8
0x1400d00e9  ja      short loc_1400D00F0
0x1400d00eb  mov     eax, 8
0x1400d00f0  mov     dword ptr [rbp+57h+arg_8], eax
0x1400d00f3  call    cs:__imp_KeGetRecommendedSharedDataAlignment
0x1400d00fa  nop     dword ptr [rax+rax+00h]
0x1400d00ff  mov     ecx, eax
0x1400d0101  lea     edx, [rax-1]
0x1400d0104  test    eax, edx
0x1400d0106  jnz     short loc_1400D011D
0x1400d0108  test    eax, eax
0x1400d010a  jz      short loc_1400D011D
0x1400d010c  mov     r8d, dword ptr [rbp+57h+arg_8]
0x1400d0110  not     edx
0x1400d0112  dec     r8d
0x1400d0115  add     r8d, eax
0x1400d0118  and     r8d, edx
0x1400d011b  jmp     short loc_1400D0131
0x1400d011d  mov     r8d, dword ptr [rbp+57h+arg_8]
0x1400d0121  xor     edx, edx
0x1400d0123  mov     eax, r8d
  ... truncated ...
```
