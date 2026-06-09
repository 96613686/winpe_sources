# PtQueryEnhancedCapabilities(_ADAPT *)

- ea: `0x140013c7c`
- end: `0x1400140ac`
- name: `?PtQueryEnhancedCapabilities@@YAHPEAU_ADAPT@@@Z`
- size: `1072`
- prototype: `__int64 __fastcall(struct _ADAPT *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14003d11c`

## callees

- `0x140013c7c`
- `0x140015b0c`
- `0x140020dc0`
- `0x140020f20`
- `0x14009bbb0`
- `0x14009bfc0`

## import_xrefs

- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013df3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013ecd`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013df3`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x140013ecd`
- `ntoskrnl!ExAllocatePool2` at `0x140013ee5`
- `ntoskrnl!ExAllocatePool2` at `0x140013ee5`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013e60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014024`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140013e60`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140014024`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014035`
- `ntoskrnl!ExFreePoolWithTag` at `0x140013e75`
- `ntoskrnl!ExFreePoolWithTag` at `0x140014035`

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
  unsigned int v23; // r14d
  unsigned int v24; // eax
  char *Pool2; // rax
  PDEVICE_OBJECT v26; // rcx
  __int64 v27; // rdx
  __int64 v28; // r9
  unsigned int v30; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v31[3]; // [rsp+34h] [rbp-CCh] BYREF
  _BYTE v32[608]; // [rsp+40h] [rbp-C0h] BYREF

  v31[0] = 0;
  memset(v32, 0, 0x258u);
  v2 = PtQueryAdapterSyncEx(a1, 0xE010165u, v32, 0x258u, v31, &v30);
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
  v5 = v32;
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
  v30 = 96;
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
    v26 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || !BYTE1(WPP_GLOBAL_Control->Timer)
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
    {
      return v2;
    }
    v27 = 17;
    v28 = 96;
LABEL_50:
    WPP_SF_d(v26->AttachedDevice, v27, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v28);
    return v2;
  }
  v22 = (_DOT11_BAND_CAPABILITIES *)(v20 + 16);
  *(_QWORD *)v20 = &WPP_MAIN_CB.DeviceLock.Header.WaitListHead;
  *((_DWORD *)v20 + 2) = 1718186871;
  v2 = PtQueryAdapterSyncEx(a1, 0xE010166u, v20 + 16, 0x60u, v31, &v30);
  if ( v2 == -2147483643 )
  {
    if ( v22 )
    {
      if ( *(_QWORD *)v21 )
        ExFreeToNPagedLookasideList(*(PNPAGED_LOOKASIDE_LIST *)v21, v21);
      else
        ExFreePoolWithTag(v21, v21[2]);
    }
    v23 = v30;
    v24 = v30 + 16;
    if ( v30 >= 0xFFFFFFF0 )
    {
LABEL_31:
      v2 = -1073741670;
      v26 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || !BYTE1(WPP_GLOBAL_Control->Timer)
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 )
      {
        return v2;
      }
      v27 = 18;
      v28 = v23;
      goto LABEL_50;
    }
    if ( v24 > 0x40 )
    {
      if ( v24 > 0x100 )
      {
        if ( v24 > 0x400 )
        {
          if ( v24 > 0x800 )
          {
            p_WaitListHead = 0;
            Pool2 = (char *)ExAllocatePool2(64, v24, 1718186871);
LABEL_24:
            if ( Pool2 )
            {
              v22 = (_DOT11_BAND_CAPABILITIES *)(Pool2 + 16);
              *(_QWORD *)Pool2 = p_WaitListHead;
              *((_DWORD *)Pool2 + 2) = 1718186871;
              v2 = PtQueryAdapterSyncEx(a1, 0xE010166u, Pool2 + 16, v23, v31, &v30);
              goto LABEL_26;
            }
            goto LABEL_31;
          }
          p_WaitListHead = &stru_1400B31C0;
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
    if ( v31[0] >= 8 )
    {
      a1->pBandCapabilities = v22;
      return v2;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer)
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids, v31[0], 8);
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
0x140013c7c  push    rbp
0x140013c7e  push    rbx
0x140013c7f  push    rsi
0x140013c80  push    rdi
0x140013c81  push    r14
0x140013c83  push    r15
0x140013c85  lea     rbp, [rsp-1B8h]
0x140013c8d  sub     rsp, 2B8h
0x140013c94  mov     rax, cs:__security_cookie
0x140013c9b  xor     rax, rsp
0x140013c9e  mov     [rbp+1E0h+var_40], rax
0x140013ca5  mov     r15, rcx
0x140013ca8  mov     [rsp+2E0h+var_2AC], 0
0x140013cb0  mov     ebx, 258h
0x140013cb5  lea     rcx, [rsp+2E0h+var_2A0]; void *
0x140013cba  mov     r8d, ebx; Size
0x140013cbd  xor     edx, edx; Val
0x140013cbf  call    memset
0x140013cc4  lea     rax, [rsp+2E0h+var_2B0]
0x140013cc9  mov     r9d, ebx; unsigned int
0x140013ccc  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x140013cd1  lea     r8, [rsp+2E0h+var_2A0]; void *
0x140013cd6  lea     rax, [rsp+2E0h+var_2AC]
0x140013cdb  mov     edx, 0E010165h; unsigned int
0x140013ce0  mov     rcx, r15; struct _ADAPT *
0x140013ce3  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x140013ce8  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140013ced  mov     ebx, eax
0x140013cef  test    eax, eax
0x140013cf1  jz      short loc_140013D3C
0x140013cf3  mov     rcx, cs:WPP_GLOBAL_Control
0x140013cfa  lea     rax, WPP_GLOBAL_Control
0x140013d01  cmp     rcx, rax
0x140013d04  jz      loc_14001408A
0x140013d0a  cmp     byte ptr [rcx+29h], 1
0x140013d0e  jb      loc_14001408A
0x140013d14  mov     eax, [rcx+2Ch]
0x140013d17  test    al, 8
0x140013d19  jz      loc_14001408A
0x140013d1f  mov     rcx, [rcx+18h]
0x140013d23  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140013d2a  mov     edx, 10h
0x140013d2f  mov     r9d, ebx
0x140013d32  call    WPP_SF_d
0x140013d37  jmp     loc_14001408A
0x140013d3c  mov     edx, 4
0x140013d41  lea     rcx, [r15+438h]
0x140013d48  lea     rax, [rsp+2E0h+var_2A0]
0x140013d4d  lea     r8d, [rdx+7Ch]
0x140013d51  movups  xmm0, xmmword ptr [rax]
0x140013d54  movups  xmm1, xmmword ptr [rax+10h]
0x140013d58  movups  xmmword ptr [rcx], xmm0
0x140013d5b  movups  xmm0, xmmword ptr [rax+20h]
0x140013d5f  movups  xmmword ptr [rcx+10h], xmm1
0x140013d63  movups  xmm1, xmmword ptr [rax+30h]
0x140013d67  movups  xmmword ptr [rcx+20h], xmm0
0x140013d6b  movups  xmm0, xmmword ptr [rax+40h]
0x140013d6f  movups  xmmword ptr [rcx+30h], xmm1
0x140013d73  movups  xmm1, xmmword ptr [rax+50h]
0x140013d77  movups  xmmword ptr [rcx+40h], xmm0
0x140013d7b  movups  xmm0, xmmword ptr [rax+60h]
0x140013d7f  movups  xmmword ptr [rcx+50h], xmm1
0x140013d83  movups  xmm1, xmmword ptr [rax+70h]
0x140013d87  add     rax, r8
0x140013d8a  movups  xmmword ptr [rcx+60h], xmm0
0x140013d8e  movups  xmmword ptr [rcx+70h], xmm1
0x140013d92  add     rcx, r8
0x140013d95  sub     rdx, 1
0x140013d99  jnz     short loc_140013D51
0x140013d9b  movups  xmm0, xmmword ptr [rax]
0x140013d9e  lea     rsi, WPP_MAIN_CB.DeviceLock.Header.WaitListHead
0x140013da5  mov     [rsp+2E0h+var_2B0], 60h ; '`'
0x140013dad  movups  xmm1, xmmword ptr [rax+10h]
0x140013db1  movups  xmmword ptr [rcx], xmm0
0x140013db4  movups  xmm0, xmmword ptr [rax+20h]
0x140013db8  movups  xmmword ptr [rcx+10h], xmm1
0x140013dbc  movups  xmm1, xmmword ptr [rax+30h]
0x140013dc0  movups  xmmword ptr [rcx+20h], xmm0
0x140013dc4  movups  xmm0, xmmword ptr [rax+40h]
0x140013dc8  mov     rax, [rax+50h]
0x140013dcc  movups  xmmword ptr [rcx+30h], xmm1
0x140013dd0  movups  xmmword ptr [rcx+40h], xmm0
0x140013dd4  mov     [rcx+50h], rax
0x140013dd8  mov     rcx, rsi; Lookaside
0x140013ddb  mov     eax, [r15+410h]
0x140013de2  and     eax, 1
0x140013de5  mov     [r15+5A4h], eax
0x140013dec  mov     [r15+5A8h], eax
0x140013df3  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140013dfa  nop     dword ptr [rax+rax+00h]
0x140013dff  mov     r14, rax
0x140013e02  test    rax, rax
0x140013e05  jz      loc_14001404C
0x140013e0b  lea     rdi, [rax+10h]
0x140013e0f  mov     [rax], rsi
0x140013e12  mov     dword ptr [rax+8], 66697377h
0x140013e19  mov     r9d, 60h ; '`'; unsigned int
0x140013e1f  lea     rax, [rsp+2E0h+var_2B0]
0x140013e24  mov     r8, rdi; void *
0x140013e27  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x140013e2c  mov     edx, 0E010166h; unsigned int
0x140013e31  lea     rax, [rsp+2E0h+var_2AC]
0x140013e36  mov     rcx, r15; struct _ADAPT *
0x140013e39  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x140013e3e  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140013e43  mov     ebx, eax
0x140013e45  cmp     eax, 80000005h
0x140013e4a  jnz     loc_140013F31
0x140013e50  test    rdi, rdi
0x140013e53  jz      short loc_140013E81
0x140013e55  mov     rcx, [r14]; Lookaside
0x140013e58  test    rcx, rcx
0x140013e5b  jz      short loc_140013E6E
0x140013e5d  mov     rdx, r14; Entry
0x140013e60  call    cs:__imp_ExFreeToNPagedLookasideList
0x140013e67  nop     dword ptr [rax+rax+00h]
0x140013e6c  jmp     short loc_140013E81
0x140013e6e  mov     edx, [r14+8]; Tag
0x140013e72  mov     rcx, r14; P
0x140013e75  call    cs:__imp_ExFreePoolWithTag
0x140013e7c  nop     dword ptr [rax+rax+00h]
0x140013e81  mov     r14d, [rsp+2E0h+var_2B0]
0x140013e86  lea     eax, [r14+10h]
0x140013e8a  cmp     eax, 10h
0x140013e8d  jb      loc_140013F82
0x140013e93  mov     ecx, 40h ; '@'
0x140013e98  cmp     eax, ecx
0x140013e9a  ja      short loc_140013EA5
0x140013e9c  lea     rsi, WPP_MAIN_CB.DeviceQueue
0x140013ea3  jmp     short loc_140013ECA
0x140013ea5  cmp     eax, 100h
0x140013eaa  jbe     short loc_140013ECA
0x140013eac  cmp     eax, 400h
0x140013eb1  ja      short loc_140013EBC
0x140013eb3  lea     rsi, Lookaside
0x140013eba  jmp     short loc_140013ECA
0x140013ebc  cmp     eax, 800h
0x140013ec1  ja      short loc_140013EDB
0x140013ec3  lea     rsi, stru_1400B31C0
0x140013eca  mov     rcx, rsi; Lookaside
0x140013ecd  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x140013ed4  nop     dword ptr [rax+rax+00h]
0x140013ed9  jmp     short loc_140013EF1
0x140013edb  xor     esi, esi
0x140013edd  mov     edx, eax
0x140013edf  mov     r8d, 66697377h
0x140013ee5  call    cs:__imp_ExAllocatePool2
0x140013eec  nop     dword ptr [rax+rax+00h]
0x140013ef1  test    rax, rax
0x140013ef4  jz      loc_140013F82
0x140013efa  lea     rdi, [rax+10h]
0x140013efe  mov     [rax], rsi
0x140013f01  mov     dword ptr [rax+8], 66697377h
0x140013f08  mov     r9d, r14d; unsigned int
0x140013f0b  lea     rax, [rsp+2E0h+var_2B0]
0x140013f10  mov     r8, rdi; void *
0x140013f13  mov     [rsp+2E0h+var_2B8], rax; unsigned int *
0x140013f18  mov     edx, 0E010166h; unsigned int
0x140013f1d  lea     rax, [rsp+2E0h+var_2AC]
0x140013f22  mov     rcx, r15; struct _ADAPT *
0x140013f25  mov     [rsp+2E0h+var_2C0], rax; unsigned int *
0x140013f2a  call    ?PtQueryAdapterSyncEx@@YAHPEAU_ADAPT@@KPEAXKPEAK2@Z; PtQueryAdapterSyncEx(_ADAPT *,ulong,void *,ulong,ulong *,ulong *)
0x140013f2f  mov     ebx, eax
0x140013f31  test    ebx, ebx
0x140013f33  jz      loc_140013FC0
0x140013f39  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f40  lea     rax, WPP_GLOBAL_Control
0x140013f47  cmp     rcx, rax
0x140013f4a  jz      loc_14001400D
0x140013f50  cmp     byte ptr [rcx+29h], 1
0x140013f54  jb      loc_14001400D
0x140013f5a  mov     eax, [rcx+2Ch]
0x140013f5d  test    al, 8
0x140013f5f  jz      loc_14001400D
0x140013f65  mov     rcx, [rcx+18h]
0x140013f69  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140013f70  mov     edx, 13h
0x140013f75  mov     r9d, ebx
0x140013f78  call    WPP_SF_d
0x140013f7d  jmp     loc_14001400D
0x140013f82  mov     ebx, 0C000009Ah
0x140013f87  mov     rcx, cs:WPP_GLOBAL_Control
0x140013f8e  lea     rax, WPP_GLOBAL_Control
0x140013f95  cmp     rcx, rax
0x140013f98  jz      loc_14001408A
0x140013f9e  cmp     byte ptr [rcx+29h], 1
0x140013fa2  jb      loc_14001408A
0x140013fa8  mov     eax, [rcx+2Ch]
0x140013fab  test    al, 8
0x140013fad  jz      loc_14001408A
0x140013fb3  mov     edx, 12h
0x140013fb8  mov     r9d, r14d
0x140013fbb  jmp     loc_14001407A
0x140013fc0  mov     r9d, [rsp+2E0h+var_2AC]
0x140013fc5  cmp     r9d, 8
0x140013fc9  jnb     short loc_140014043
0x140013fcb  mov     rcx, cs:WPP_GLOBAL_Control
0x140013fd2  lea     rax, WPP_GLOBAL_Control
0x140013fd9  cmp     rcx, rax
0x140013fdc  jz      short loc_140014008
0x140013fde  cmp     byte ptr [rcx+29h], 1
0x140013fe2  jb      short loc_140014008
0x140013fe4  mov     eax, [rcx+2Ch]
0x140013fe7  test    al, 8
0x140013fe9  jz      short loc_140014008
0x140013feb  mov     rcx, [rcx+18h]
0x140013fef  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140013ff6  mov     edx, 14h
0x140013ffb  mov     dword ptr [rsp+2E0h+var_2C0], 8
0x140014003  call    WPP_SF_Dd
0x140014008  mov     ebx, 0C000000Dh
0x14001400d  test    rdi, rdi
0x140014010  jz      short loc_14001408A
0x140014012  lea     rcx, [rdi-10h]; P
0x140014016  mov     rax, [rcx]
0x140014019  test    rax, rax
0x14001401c  jz      short loc_140014032
0x14001401e  mov     rdx, rcx; Entry
0x140014021  mov     rcx, rax; Lookaside
0x140014024  call    cs:__imp_ExFreeToNPagedLookasideList
0x14001402b  nop     dword ptr [rax+rax+00h]
0x140014030  jmp     short loc_14001408A
0x140014032  mov     edx, [rcx+8]; Tag
0x140014035  call    cs:__imp_ExFreePoolWithTag
0x14001403c  nop     dword ptr [rax+rax+00h]
0x140014041  jmp     short loc_14001408A
0x140014043  mov     [r15+690h], rdi
0x14001404a  jmp     short loc_14001408A
0x14001404c  mov     ebx, 0C000009Ah
0x140014051  mov     rcx, cs:WPP_GLOBAL_Control
0x140014058  lea     rax, WPP_GLOBAL_Control
0x14001405f  cmp     rcx, rax
0x140014062  jz      short loc_14001408A
0x140014064  cmp     byte ptr [rcx+29h], 1
0x140014068  jb      short loc_14001408A
0x14001406a  mov     eax, [rcx+2Ch]
0x14001406d  test    al, 8
0x14001406f  jz      short loc_14001408A
0x140014071  mov     edx, 11h
0x140014076  lea     r9d, [rdx+4Fh]
0x14001407a  mov     rcx, [rcx+18h]
0x14001407e  lea     r8, WPP_4f70633c889d3d5ba5e904434b809e78_Traceguids
0x140014085  call    WPP_SF_d
0x14001408a  mov     eax, ebx
0x14001408c  mov     rcx, [rbp+1E0h+var_40]
0x140014093  xor     rcx, rsp; StackCookie
0x140014096  call    __security_check_cookie
0x14001409b  add     rsp, 2B8h
0x1400140a2  pop     r15
0x1400140a4  pop     r14
0x1400140a6  pop     rdi
0x1400140a7  pop     rsi
0x1400140a8  pop     rbx
0x1400140a9  pop     rbp
0x1400140aa  retn
```
