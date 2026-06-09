# PtQueryEnhancedCapabilities(_ADAPT *)

- ea: `0x140013c8c`
- end: `0x1400140bc`
- name: `?PtQueryEnhancedCapabilities@@YAHPEAU_ADAPT@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(struct _ADAPT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14003cefc`

## callees

- `0x140013c8c`
- `0x140015b1c`
- `0x140020dc0`
- `0x140020f20`
- `0x14009a3d0`
- `0x14009a7c0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013e03`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013edd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013e03`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013edd`
- `ntoskrnl!ExAllocatePool2` at `0x140013ef5`
- `ntoskrnl!ExAllocatePool2` at `0x140013ef5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013e70`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014034`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013e70`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014034`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014045`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e85`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014045`

## pseudocode

```c
__int64 __fastcall PtQueryEnhancedCapabilities(struct _ADAPT *a1)
{
  unsigned int v2; // ebx
  __int64 v3; // rdx
  _DOT11_ADAPTER_CAPABILITIES *p_AdapterEnhancedCapabilities; // rcx
  _OWORD *v5; // rax
  __int128 v6; // xmm1
  __int128 v7; // xmm0
  __int128 v8; // xmm1
  __int128 v9; // xmm0
  __int128 v10; // xmm1
  __int128 v11; // xmm0
  __int128 v12; // xmm1
  __int128 v13; // xmm0
  struct _NPAGED_LOOKASIDE_LIST *p_WaitListHead; // rsi
  __int128 v15; // xmm1
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  __int64 v19; // rax
  char *v20; // rax
  ULONG *v21; // r14
  _DOT11_BAND_CAPABILITIES *v22; // rdi
  __int64 v23; // r9
  unsigned int v24; // r14d
  unsigned int v25; // eax
  char *Pool2; // rax
  PDEVICE_OBJECT v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  unsigned int v31; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v32[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v33[608]; // [rsp+40h] [rbp-C0h] BYREF

  v32[0] = 0;
  memset(v33, 0, 0x258u);
  v2 = PtQueryAdapterSyncEx(a1, 0xE010165u, v33, 0x258u, v32, &v31);
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v2);
    }
    return v2;
  }
  v3 = 4;
  p_AdapterEnhancedCapabilities = &a1->AdapterEnhancedCapabilities;
  v5 = v33;
  do
  {
    v6 = v5[1];
    *(_OWORD *)p_AdapterEnhancedCapabilities->FirmwareVersion = *v5;
    v7 = v5[2];
    *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[16] = v6;
    v8 = v5[3];
    *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[32] = v7;
    v9 = v5[4];
    *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[48] = v8;
    v10 = v5[5];
    *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[64] = v9;
    v11 = v5[6];
    *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[80] = v10;
    v12 = v5[7];
    v5 += 8;
    *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[96] = v11;
    *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[112] = v12;
    p_AdapterEnhancedCapabilities = (_DOT11_ADAPTER_CAPABILITIES *)((char *)p_AdapterEnhancedCapabilities + 128);
    --v3;
  }
  while ( v3 );
  v13 = *v5;
  p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  v31 = 96;
  v15 = v5[1];
  *(_OWORD *)p_AdapterEnhancedCapabilities->FirmwareVersion = v13;
  v16 = v5[2];
  *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[16] = v15;
  v17 = v5[3];
  *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[32] = v16;
  v18 = v5[4];
  v19 = *((_QWORD *)v5 + 10);
  *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[48] = v17;
  *(_OWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[64] = v18;
  *(_QWORD *)&p_AdapterEnhancedCapabilities->FirmwareVersion[80] = v19;
  LODWORD(v19) = a1->PmCapabilities.MediaSpecificWakeUpEvents & 1;
  a1->AdapterEnhancedCapabilities.Dx_StandbyNLOSupported = v19;
  a1->AdapterEnhancedCapabilities.InstantConnectSupported = v19;
  v20 = (char *)ExAllocateFromNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)&WPP_MAIN_CB.DeviceLock.Header.WaitListHead);
  v21 = (ULONG *)v20;
  if ( !v20 )
  {
    v2 = -1073741670;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control->Timer)
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
    {
      return v2;
    }
    v28 = 17;
    v29 = 96;
LABEL_50:
    WPP_SF_d(v27->AttachedDevice, v28, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v29);
    return v2;
  }
  v22 = (_DOT11_BAND_CAPABILITIES *)(v20 + 16);
  *(_QWORD *)v20 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  *((_DWORD *)v20 + 2) = 1718186871;
  v2 = PtQueryAdapterSyncEx(a1, 0xE010166u, v20 + 16, 0x60u, v32, &v31);
  if ( v2 == -2147483643 )
  {
    if ( v22 )
    {
      if ( *(_QWORD *)v21 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v21, v21);
      else
        ExFreePoolWithTag(v21, v21[2]);
    }
    v24 = v31;
    v25 = v31 + 16;
    if ( v31 >= 0xFFFFFFF0 )
    {
LABEL_31:
      v2 = -1073741670;
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control->Timer)
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
      {
        return v2;
      }
      v28 = 18;
      v29 = v24;
      goto LABEL_50;
    }
    if ( v25 > 0x40 )
    {
      if ( v25 > 0x100 )
      {
        if ( v25 > 0x400 )
        {
          if ( v25 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v25, 1718186871, v23);
LABEL_24:
            if ( Pool2 )
            {
              v22 = (_DOT11_BAND_CAPABILITIES *)(Pool2 + 16);
              *(_QWORD *)Pool2 = p_WaitListHead;
              *((_DWORD *)Pool2 + 2) = 1718186871;
              v2 = PtQueryAdapterSyncEx(a1, 0xE010166u, Pool2 + 16, v24, v32, &v31);
              goto LABEL_26;
            }
            goto LABEL_31;
          }
          p_WaitListHead = &stru_1400B0180;
        }
        else
        {
          p_WaitListHead = &Lookaside;
        }
      }
    }
    else
    {
      p_WaitListHead = (struct _NPAGED_LOOKASIDE_LIST *)&WPP_MAIN_CB.DeviceQueue;
    }
    Pool2 = (char *)ExAllocateFromNPagedLookasideList(p_WaitListHead);
    goto LABEL_24;
  }
LABEL_26:
  if ( v2 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v2);
    }
  }
  else
  {
    if ( v32[0] >= 8 )
    {
      a1->pBandCapabilities = v22;
      return v2;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v32[0], 8);
    }
    v2 = -1073741811;
  }
  if ( v22 )
  {
    if ( *(_QWORD *)&v22[-1].BandDescriptors[0].uChannelFrequenciesOffset )
      ExFreeToNPagedLookasideList(
        *(PNPAGED_LOOKASIDE_LIST *)&v22[-1].BandDescriptors[0].uChannelFrequenciesOffset,
        &v22[-1].BandDescriptors[0].uChannelFrequenciesOffset);
    else
      ExFreePoolWithTag(
        &v22[-1].BandDescriptors[0].uChannelFrequenciesOffset,
        v22[-1].BandDescriptors[0].uChannelWidthOffset);
  }
  return v2;
}

```

## disassembly

```asm
0x140013c8c  push    rbp
0x140013c8e  push    rbx
0x140013c8f  push    rsi
0x140013c90  push    rdi
0x140013c91  push    r14
0x140013c93  push    r15
0x140013c95  lea     rbp, [rsp-1B8h]
0x140013c9d  sub     rsp, 2B8h
0x140013ca4  mov     rax, cs:__security_cookie
0x140013cab  xor     rax, rsp
0x140013cae  mov     [rbp+1E0h+var_40], rax
0x140013cb5  mov     r15, rcx
0x140013cb8  mov     [rsp+2E0h+var_2AC], 0
0x140013cc0  mov     ebx, 258h
0x140013cc5  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x140013cca  mov     r8d, ebx; Size
0x140013ccd  xor     edx, edx; Val
0x140013ccf  call    memset
0x140013cd4  lea     rax, [rsp+2E0h+var_2B0]
0x140013cd9  mov     r9d, ebx; unsigned int
0x140013cdc  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x140013ce1  lea     r8, [rsp+2E0h+var_2A0]; void *
0x140013ce6  lea     rax, [rsp+2E0h+var_2AC]
0x140013ceb  mov     edx, 0E010165h; unsigned int
0x140013cf0  mov     rcx, r15; struct _ADAPT *
0x140013cf3  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x140013cf8  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140013cfd  mov     ebx, eax
0x140013cff  test    eax, eax
0x140013d01  jz      short loc_140013D4C
0x140013d03  mov     rcx, cs:WPP_GLOBAL_Control
0x140013d0a  lea     rax, WPP_GLOBAL_Control
0x140013d11  cmp     rcx, rax
0x140013d14  jz      loc_14001409A
0x140013d1a  cmp     byte ptr [rcx+29h], 1
0x140013d1e  jb      loc_14001409A
0x140013d24  mov     eax, [rcx+2Ch]
0x140013d27  test    al, 8
0x140013d29  jz      loc_14001409A
0x140013d2f  mov     rcx, [rcx+18h]
0x140013d33  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140013d3a  mov     edx, 10h
0x140013d3f  mov     r9d, ebx
0x140013d42  call    WPP_SF_d
0x140013d47  jmp     loc_14001409A
0x140013d4c  mov     edx, 4
0x140013d51  lea     rcx, [r15+438h]
0x140013d58  lea     rax, [rsp+2E0h+var_2A0]
0x140013d5d  lea     r8d, [rdx+7Ch]
0x140013d61  movups  xmm0, xmmword ptr [rax]
0x140013d64  movups  xmm1, xmmword ptr [rax+10h]
0x140013d68  movups  xmmword ptr [rcx], xmm0
0x140013d6b  movups  xmm0, xmmword ptr [rax+20h]
0x140013d6f  movups  xmmword ptr [rcx+10h], xmm1
0x140013d73  movups  xmm1, xmmword ptr [rax+30h]
0x140013d77  movups  xmmword ptr [rcx+20h], xmm0
0x140013d7b  movups  xmm0, xmmword ptr [rax+40h]
0x140013d7f  movups  xmmword ptr [rcx+30h], xmm1
0x140013d83  movups  xmm1, xmmword ptr [rax+50h]
0x140013d87  movups  xmmword ptr [rcx+40h], xmm0
0x140013d8b  movups  xmm0, xmmword ptr [rax+60h]
0x140013d8f  movups  xmmword ptr [rcx+50h], xmm1
0x140013d93  movups  xmm1, xmmword ptr [rax+70h]
0x140013d97  add     rax, r8
0x140013d9a  movups  xmmword ptr [rcx+60h], xmm0
0x140013d9e  movups  xmmword ptr [rcx+70h], xmm1
0x140013da2  add     rcx, r8
0x140013da5  sub     rdx, 1
0x140013da9  jnz     short loc_140013D61
0x140013dab  movups  xmm0, xmmword ptr [rax]
0x140013dae  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140013db5  mov     [rsp+2E0h+var_2B0], 60h ; '`'
0x140013dbd  movups  xmm1, xmmword ptr [rax+10h]
0x140013dc1  movups  xmmword ptr [rcx], xmm0
0x140013dc4  movups  xmm0, xmmword ptr [rax+20h]
0x140013dc8  movups  xmmword ptr [rcx+10h], xmm1
0x140013dcc  movups  xmm1, xmmword ptr [rax+30h]
0x140013dd0  movups  xmmword ptr [rcx+20h], xmm0
0x140013dd4  movups  xmm0, xmmword ptr [rax+40h]
0x140013dd8  mov     rax, [rax+50h]
0x140013ddc  movups  xmmword ptr [rcx+30h], xmm1
0x140013de0  movups  xmmword ptr [rcx+40h], xmm0
0x140013de4  mov     [rcx+50h], rax
0x140013de8  mov     rcx, rsi; Lookaside
0x140013deb  mov     eax, [r15+410h]
0x140013df2  and     eax, 1
0x140013df5  mov     [r15+5A4h], eax
0x140013dfc  mov     [r15+5A8h], eax
0x140013e03  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140013e0a  nop     dword ptr [rax+rax+00h]
0x140013e0f  mov     r14, rax
0x140013e12  test    rax, rax
0x140013e15  jz      loc_14001405C
0x140013e1b  lea     rdi, [rax+10h]
0x140013e1f  mov     [rax], rsi
0x140013e22  mov     dword ptr [rax+8], 66697377h
0x140013e29  mov     r9d, 60h ; '`'; unsigned int
0x140013e2f  lea     rax, [rsp+2E0h+var_2B0]
0x140013e34  mov     r8, rdi; void *
0x140013e37  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x140013e3c  mov     edx, 0E010166h; unsigned int
0x140013e41  lea     rax, [rsp+2E0h+var_2AC]
0x140013e46  mov     rcx, r15; struct _ADAPT *
0x140013e49  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x140013e4e  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140013e53  mov     ebx, eax
0x140013e55  cmp     eax, 80000005h
0x140013e5a  jnz     loc_140013F41
0x140013e60  test    rdi, rdi
0x140013e63  jz      short loc_140013E91
0x140013e65  mov     rcx, [r14]; Lookaside
0x140013e68  test    rcx, rcx
0x140013e6b  jz      short loc_140013E7E
0x140013e6d  mov     rdx, r14; Entry
0x140013e70  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013e77  nop     dword ptr [rax+rax+00h]
0x140013e7c  jmp     short loc_140013E91
0x140013e7e  mov     edx, [r14+8]; Tag
0x140013e82  mov     rcx, r14; P
0x140013e85  call    cs:__imp_ExFreePoolWithTag
0x140013e8c  nop     dword ptr [rax+rax+00h]
0x140013e91  mov     r14d, [rsp+2E0h+var_2B0]
0x140013e96  lea     eax, [r14+10h]
0x140013e9a  cmp     eax, 10h
0x140013e9d  jb      loc_140013F92
0x140013ea3  mov     ecx, 40h ; '@'
0x140013ea8  cmp     eax, ecx
0x140013eaa  ja      short loc_140013EB5
0x140013eac  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x140013eb3  jmp     short loc_140013EDA
0x140013eb5  cmp     eax, 100h
0x140013eba  jbe     short loc_140013EDA
0x140013ebc  cmp     eax, 400h
0x140013ec1  ja      short loc_140013ECC
0x140013ec3  lea     rsi, Lookaside
0x140013eca  jmp     short loc_140013EDA
0x140013ecc  cmp     eax, 800h
0x140013ed1  ja      short loc_140013EEB
0x140013ed3  lea     rsi, stru_1400B0180
0x140013eda  mov     rcx, rsi; Lookaside
0x140013edd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140013ee4  nop     dword ptr [rax+rax+00h]
0x140013ee9  jmp     short loc_140013F01
0x140013eeb  xor     esi, esi
0x140013eed  mov     edx, eax
0x140013eef  mov     r8d, 66697377h
0x140013ef5  call    cs:__imp_ExAllocatePool2
0x140013efc  nop     dword ptr [rax+rax+00h]
0x140013f01  test    rax, rax
0x140013f04  jz      loc_140013F92
0x140013f0a  lea     rdi, [rax+10h]
0x140013f0e  mov     [rax], rsi
0x140013f11  mov     dword ptr [rax+8], 66697377h
0x140013f18  mov     r9d, r14d; unsigned int
0x140013f1b  lea     rax, [rsp+2E0h+var_2B0]
0x140013f20  mov     r8, rdi; void *
0x140013f23  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x140013f28  mov     edx, 0E010166h; unsigned int
0x140013f2d  lea     rax, [rsp+2E0h+var_2AC]
0x140013f32  mov     rcx, r15; struct _ADAPT *
0x140013f35  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x140013f3a  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140013f3f  mov     ebx, eax
0x140013f41  test    ebx, ebx
0x140013f43  jz      loc_140013FD0
0x140013f49  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f50  lea     rax, WPP_GLOBAL_Control
0x140013f57  cmp     rcx, rax
0x140013f5a  jz      loc_14001401D
0x140013f60  cmp     byte ptr [rcx+29h], 1
0x140013f64  jb      loc_14001401D
0x140013f6a  mov     eax, [rcx+2Ch]
0x140013f6d  test    al, 8
0x140013f6f  jz      loc_14001401D
0x140013f75  mov     rcx, [rcx+18h]
0x140013f79  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140013f80  mov     edx, 13h
0x140013f85  mov     r9d, ebx
0x140013f88  call    WPP_SF_d
0x140013f8d  jmp     loc_14001401D
0x140013f92  mov     ebx, 0C000009Ah
0x140013f97  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f9e  lea     rax, WPP_GLOBAL_Control
0x140013fa5  cmp     rcx, rax
0x140013fa8  jz      loc_14001409A
0x140013fae  cmp     byte ptr [rcx+29h], 1
0x140013fb2  jb      loc_14001409A
0x140013fb8  mov     eax, [rcx+2Ch]
0x140013fbb  test    al, 8
0x140013fbd  jz      loc_14001409A
0x140013fc3  mov     edx, 12h
0x140013fc8  mov     r9d, r14d
0x140013fcb  jmp     loc_14001408A
0x140013fd0  mov     r9d, [rsp+2E0h+var_2AC]
0x140013fd5  cmp     r9d, 8
0x140013fd9  jnb     short loc_140014053
0x140013fdb  mov     rcx, cs:WPP_GLOBAL_Control
0x140013fe2  lea     rax, WPP_GLOBAL_Control
0x140013fe9  cmp     rcx, rax
0x140013fec  jz      short loc_140014018
0x140013fee  cmp     byte ptr [rcx+29h], 1
0x140013ff2  jb      short loc_140014018
0x140013ff4  mov     eax, [rcx+2Ch]
0x140013ff7  test    al, 8
0x140013ff9  jz      short loc_140014018
0x140013ffb  mov     rcx, [rcx+18h]
0x140013fff  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140014006  mov     edx, 14h
0x14001400b  mov     dword ptr [rsp+2E0h+var_2C0], 8
0x140014013  call    WPP_SF_Dd
0x140014018  mov     ebx, 0C000000Dh
0x14001401d  test    rdi, rdi
0x140014020  jz      short loc_14001409A
0x140014022  lea     rcx, [rdi-10h]; P
0x140014026  mov     rax, [rcx]
0x140014029  test    rax, rax
0x14001402c  jz      short loc_140014042
0x14001402e  mov     rdx, rcx; Entry
0x140014031  mov     rcx, rax; Lookaside
0x140014034  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001403b  nop     dword ptr [rax+rax+00h]
0x140014040  jmp     short loc_14001409A
0x140014042  mov     edx, [rcx+8]; Tag
0x140014045  call    cs:__imp_ExFreePoolWithTag
0x14001404c  nop     dword ptr [rax+rax+00h]
0x140014051  jmp     short loc_14001409A
0x140014053  mov     [r15+690h], rdi
0x14001405a  jmp     short loc_14001409A
0x14001405c  mov     ebx, 0C000009Ah
0x140014061  mov     rcx, cs:WPP_GLOBAL_Control
0x140014068  lea     rax, WPP_GLOBAL_Control
0x14001406f  cmp     rcx, rax
0x140014072  jz      short loc_14001409A
0x140014074  cmp     byte ptr [rcx+29h], 1
0x140014078  jb      short loc_14001409A
0x14001407a  mov     eax, [rcx+2Ch]
0x14001407d  test    al, 8
0x14001407f  jz      short loc_14001409A
0x140014081  mov     edx, 11h
0x140014086  lea     r9d, [rdx+4Fh]
0x14001408a  mov     rcx, [rcx+18h]
0x14001408e  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140014095  call    WPP_SF_d
0x14001409a  mov     eax, ebx
0x14001409c  mov     rcx, [rbp+1E0h+var_40]
0x1400140a3  xor     rcx, rsp; StackCookie
0x1400140a6  call    __security_check_cookie
0x1400140ab  add     rsp, 2B8h
0x1400140b2  pop     r15
0x1400140b4  pop     r14
0x1400140b6  pop     rdi
0x1400140b7  pop     rsi
0x1400140b8  pop     rbx
0x1400140b9  pop     rbp
0x1400140ba  retn
```
