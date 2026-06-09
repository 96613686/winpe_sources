# I8xKeyboardServiceParameters

- ea: `0x1400183a4`
- end: `0x140018be9`
- name: `I8xKeyboardServiceParameters`
- size: `2117`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x1400198e0`

## callees

- `0x1400014e0`
- `0x140004530`
- `0x140007b10`
- `0x14000a7b8`
- `0x14000a8e8`
- `0x14000daa0`
- `0x14000de80`
- `0x1400183a4`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001846b`
- `ntoskrnl!ExAllocatePool2` at `0x14001846b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bc8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140018bc8`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001867a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400188e3`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001867a`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400188e3`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140018433`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x140018433`
- `ntoskrnl!RtlQueryRegistryValues` at `0x1400186a9`
- `ntoskrnl!RtlQueryRegistryValues` at `0x140018912`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001868a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400188f3`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001868a`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x1400188f3`
- `ntoskrnl!ZwClose` at `0x140018966`
- `ntoskrnl!ZwClose` at `0x140018bb2`
- `ntoskrnl!ZwClose` at `0x140018966`
- `ntoskrnl!ZwClose` at `0x140018bb2`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001878b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001878b`

## string_xrefs

- `0x14001865d`: `RtlQueryRegistryValuesEx`
- `0x1400188c6`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __fastcall I8xKeyboardServiceParameters(__int64 *a1)
{
  __int64 v1; // r13
  __int64 v3; // rcx
  __int64 v4; // r14
  int v5; // edx
  __int64 v6; // r9
  __int64 Pool2; // rax
  HANDLE v8; // rbx
  PVOID SystemRoutineAddress; // rax
  int v10; // eax
  int *v11; // r15
  char v12; // cl
  NTSTATUS v13; // eax
  int v14; // edx
  int v15; // r8d
  void *v16; // rbx
  PVOID v17; // rax
  int v18; // eax
  int v19; // edx
  int v20; // r9d
  int v21; // eax
  char v22; // al
  unsigned int v23; // eax
  int v24; // eax
  int v25; // [rsp+20h] [rbp-69h]
  int v26; // [rsp+28h] [rbp-61h]
  int v27; // [rsp+40h] [rbp-49h] BYREF
  int v28; // [rsp+44h] [rbp-45h] BYREF
  int v29; // [rsp+48h] [rbp-41h] BYREF
  int v30; // [rsp+4Ch] [rbp-3Dh] BYREF
  int v31; // [rsp+50h] [rbp-39h] BYREF
  int v32; // [rsp+54h] [rbp-35h] BYREF
  int v33; // [rsp+58h] [rbp-31h] BYREF
  int v34; // [rsp+5Ch] [rbp-2Dh] BYREF
  int v35; // [rsp+60h] [rbp-29h] BYREF
  int v36; // [rsp+64h] [rbp-25h] BYREF
  int v37; // [rsp+68h] [rbp-21h] BYREF
  int v38; // [rsp+6Ch] [rbp-1Dh] BYREF
  unsigned int v39; // [rsp+70h] [rbp-19h] BYREF
  int v40; // [rsp+74h] [rbp-15h] BYREF
  int v41; // [rsp+78h] [rbp-11h] BYREF
  int v42; // [rsp+7Ch] [rbp-Dh] BYREF
  void *DeviceRegKey; // [rsp+80h] [rbp-9h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp-1h]
  struct _UNICODE_STRING DestinationString; // [rsp+90h] [rbp+7h] BYREF
  unsigned int v46; // [rsp+F0h] [rbp+67h] BYREF
  int v47; // [rsp+F8h] [rbp+6Fh] BYREF
  int v48; // [rsp+100h] [rbp+77h] BYREF
  int v49; // [rsp+108h] [rbp+7Fh] BYREF

  v1 = *(_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels;
  Handle = 0;
  v31 = -1;
  v3 = *a1;
  v47 = -1;
  v29 = 1;
  v36 = 1;
  v27 = 100;
  v30 = 0;
  v4 = 0;
  v46 = 0;
  v48 = 0;
  v34 = 0;
  v49 = 0;
  DeviceRegKey = 0;
  v28 = 12000;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  v37 = 0;
  if ( (int)IoOpenDriverRegistryKey(*(_QWORD *)(v3 + 8), 0, 1, 0) >= 0 )
  {
    Pool2 = ExAllocatePool2(256, 560, 842281016, v6);
    v4 = Pool2;
    if ( Pool2 )
    {
      *(_DWORD *)(Pool2 + 32) = 67108868;
      *(_DWORD *)(Pool2 + 8) = 288;
      *(_DWORD *)(Pool2 + 48) = 4;
      *(_QWORD *)(Pool2 + 16) = L"KeyboardDataQueueSize";
      *(_QWORD *)(Pool2 + 24) = (char *)a1 + 700;
      *(_QWORD *)(Pool2 + 40) = &v27;
      *(_QWORD *)(Pool2 + 72) = L"OverrideKeyboardType";
      *(_QWORD *)(Pool2 + 80) = &v46;
      *(_QWORD *)(Pool2 + 96) = &v30;
      *(_DWORD *)(Pool2 + 64) = 288;
      *(_DWORD *)(Pool2 + 104) = 4;
      *(_DWORD *)(Pool2 + 88) = 67108868;
      *(_QWORD *)(Pool2 + 128) = L"OverrideKeyboardSubType";
      *(_QWORD *)(Pool2 + 136) = &v47;
      *(_QWORD *)(Pool2 + 152) = &v31;
      *(_DWORD *)(Pool2 + 120) = 288;
      *(_DWORD *)(Pool2 + 160) = 4;
      *(_DWORD *)(Pool2 + 144) = 67108868;
      *(_QWORD *)(Pool2 + 184) = L"PollStatusIterations";
      *(_QWORD *)(Pool2 + 192) = &v48;
      *(_QWORD *)(Pool2 + 208) = &v28;
      *(_DWORD *)(Pool2 + 176) = 288;
      *(_DWORD *)(Pool2 + 216) = 4;
      *(_DWORD *)(Pool2 + 200) = 67108868;
      *(_QWORD *)(Pool2 + 240) = L"PowerCapabilities";
      *(_QWORD *)(Pool2 + 248) = &v49;
      *(_QWORD *)(Pool2 + 264) = &v34;
      *(_DWORD *)(Pool2 + 232) = 288;
      *(_DWORD *)(Pool2 + 272) = 4;
      *(_DWORD *)(Pool2 + 256) = 67108868;
      *(_QWORD *)(Pool2 + 296) = L"CrashOnCtrlScroll";
      *(_QWORD *)(Pool2 + 304) = &v32;
      *(_QWORD *)(Pool2 + 320) = &v35;
      *(_DWORD *)(Pool2 + 288) = 288;
      *(_DWORD *)(Pool2 + 328) = 4;
      *(_DWORD *)(Pool2 + 312) = 67108868;
      *(_QWORD *)(Pool2 + 352) = L"KeyboardFailedReset";
      *(_QWORD *)(Pool2 + 360) = &v29;
      *(_QWORD *)(Pool2 + 376) = &v36;
      *(_DWORD *)(Pool2 + 344) = 288;
      *(_DWORD *)(Pool2 + 384) = 4;
      *(_DWORD *)(Pool2 + 368) = 67108868;
      *(_QWORD *)(Pool2 + 408) = L"KdEnableOnCtrlSysRq";
      *(_QWORD *)(Pool2 + 416) = &v33;
      *(_DWORD *)(Pool2 + 400) = 288;
      *(_DWORD *)(Pool2 + 440) = 4;
      *(_QWORD *)(Pool2 + 432) = &v37;
      *(_DWORD *)(Pool2 + 424) = 67108868;
      v8 = Handle;
      DestinationString = 0;
      RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
      SystemRoutineAddress = MmGetSystemRoutineAddress(&DestinationString);
      if ( !SystemRoutineAddress )
        SystemRoutineAddress = RtlQueryRegistryValues;
      v10 = ((__int64 (__fastcall *)(__int64, HANDLE, __int64, _QWORD, _QWORD))SystemRoutineAddress)(
              3221225472LL,
              v8,
              v4,
              0,
              0);
      if ( v10 >= 0 || WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        if ( v10 >= 0 )
        {
          v11 = (int *)a1 + 175;
          *(_WORD *)(v1 + 76) = v48;
          goto LABEL_13;
        }
      }
      else
      {
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v5,
          16,
          79,
          (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
          v10);
      }
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        17,
        78,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    }
  }
  v11 = (int *)a1 + 175;
  *(_WORD *)(v1 + 76) = v28;
  *((_DWORD *)a1 + 175) = v27;
LABEL_13:
  v12 = v29;
  if ( v29 && (unsigned int)(v29 - 1) >= 2 )
  {
    *((_BYTE *)a1 + 954) = 1;
    v12 = 1;
  }
  else
  {
    *((_BYTE *)a1 + 954) = v29;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      14,
      80,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      v12);
  v13 = IoOpenDeviceRegistryKey((PDEVICE_OBJECT)a1[4], 1u, 0x20000u, &DeviceRegKey);
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      goto LABEL_31;
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      17,
      82,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      v13);
  }
  else
  {
    v38 = *v11;
    v42 = v49;
    v39 = v46;
    v40 = v47;
    v41 = v48;
    memset((void *)v4, 0, 0x230u);
    *(_QWORD *)(v4 + 24) = v11;
    *(_QWORD *)(v4 + 16) = L"KeyboardDataQueueSize";
    *(_DWORD *)(v4 + 8) = 32;
    *(_QWORD *)(v4 + 40) = &v38;
    *(_DWORD *)(v4 + 32) = 67108868;
    *(_DWORD *)(v4 + 48) = 4;
    *(_QWORD *)(v4 + 72) = L"OverrideKeyboardType";
    *(_QWORD *)(v4 + 80) = &v46;
    *(_QWORD *)(v4 + 96) = &v39;
    *(_DWORD *)(v4 + 64) = 32;
    *(_DWORD *)(v4 + 104) = 4;
    *(_DWORD *)(v4 + 88) = 67108868;
    *(_QWORD *)(v4 + 128) = L"OverrideKeyboardSubType";
    *(_QWORD *)(v4 + 136) = &v47;
    *(_QWORD *)(v4 + 152) = &v40;
    *(_DWORD *)(v4 + 120) = 32;
    *(_DWORD *)(v4 + 160) = 4;
    *(_DWORD *)(v4 + 144) = 67108868;
    *(_QWORD *)(v4 + 184) = L"PollStatusIterations";
    *(_QWORD *)(v4 + 192) = &v48;
    *(_QWORD *)(v4 + 208) = &v41;
    *(_DWORD *)(v4 + 176) = 32;
    *(_DWORD *)(v4 + 216) = 4;
    *(_DWORD *)(v4 + 200) = 67108868;
    *(_QWORD *)(v4 + 240) = L"PowerCapabilities";
    *(_QWORD *)(v4 + 248) = &v49;
    *(_DWORD *)(v4 + 232) = 32;
    *(_DWORD *)(v4 + 272) = 4;
    *(_QWORD *)(v4 + 264) = &v42;
    *(_DWORD *)(v4 + 256) = 67108868;
    v16 = DeviceRegKey;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    v17 = MmGetSystemRoutineAddress(&DestinationString);
    if ( !v17 )
      v17 = RtlQueryRegistryValues;
    v18 = ((__int64 (__fastcall *)(__int64, void *, __int64, _QWORD, _QWORD))v17)(0x40000000, v16, v4, 0, 0);
    if ( v18 < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v19,
        16,
        81,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        v18);
    ZwClose(DeviceRegKey);
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      14,
      83,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_Sd(WPP_GLOBAL_Control->DeviceExtension, v14, v15, v20, v25, v26, *(_WORD *)(v1 + 76));
  }
LABEL_31:
  v21 = *v11;
  if ( !*v11 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_SD(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        v15,
        85,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        (__int64)L"KeyboardDataQueueSize",
        0);
    v21 = v27;
    *v11 = v27;
  }
  *v11 = 12 * v21;
  v22 = v49 & 7;
  *((_BYTE *)a1 + 584) = v49 & 7;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      14,
      86,
      (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
      v22);
  v23 = v46;
  if ( v46 != v30 )
  {
    if ( v46 > 8 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          14,
          88,
          (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
          v46);
        v23 = v46;
      }
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v14,
          14,
          87,
          (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
          v46);
        v23 = v46;
      }
      *((_BYTE *)a1 + 688) = v23;
    }
    *((_DWORD *)a1 + 179) = v23;
  }
  v24 = v47;
  if ( v47 != v31 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        14,
        89,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids,
        v47);
      v24 = v47;
    }
    *((_BYTE *)a1 + 689) = v24;
    *((_DWORD *)a1 + 180) = v24;
  }
  if ( v32 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        16,
        90,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    *((_DWORD *)a1 + 236) = 2;
    *((_WORD *)a1 + 476) = 70;
  }
  if ( v33 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        16,
        91,
        (__int64)WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids);
    *((_DWORD *)a1 + 239) = 2;
    *((_WORD *)a1 + 480) = 21687;
  }
  if ( Handle )
    ZwClose(Handle);
  if ( v4 )
    ExFreePoolWithTag((PVOID)v4, 0);
}

```

## disassembly

```asm
0x1400183a4  push    rbp
0x1400183a6  push    rbx
0x1400183a7  push    rsi
0x1400183a8  push    rdi
0x1400183a9  push    r12
0x1400183ab  push    r13
0x1400183ad  push    r14
0x1400183af  push    r15
0x1400183b1  lea     rbp, [rsp-1Fh]
0x1400183b6  sub     rsp, 0A8h
0x1400183bd  mov     r13, qword ptr cs:WPP_MAIN_CB.Queue+10h
0x1400183c4  xor     r12d, r12d
0x1400183c7  or      eax, 0FFFFFFFFh
0x1400183ca  mov     [rbp+57h+Handle], r12
0x1400183ce  mov     rdi, rcx
0x1400183d1  mov     [rbp+57h+var_90], eax
0x1400183d4  mov     rcx, [rcx]
0x1400183d7  xor     r9d, r9d
0x1400183da  lea     edx, [r12+1]
0x1400183df  mov     [rbp+57h+arg_8], eax
0x1400183e2  mov     [rbp+57h+var_98], edx
0x1400183e5  lea     rax, [rbp+57h+Handle]
0x1400183e9  mov     [rbp+57h+var_7C], edx
0x1400183ec  mov     r8d, edx
0x1400183ef  mov     [rbp+57h+var_A0], 64h ; 'd'
0x1400183f6  xor     edx, edx
0x1400183f8  mov     [rbp+57h+var_94], r12d
0x1400183fc  mov     r14d, r12d
0x1400183ff  mov     [rbp+57h+arg_0], r12d
0x140018403  mov     [rbp+57h+arg_10], r12d
0x140018407  mov     [rbp+57h+var_84], r12d
0x14001840b  mov     [rbp+57h+arg_18], r12d
0x14001840f  mov     [rbp+57h+DeviceRegKey], r12
0x140018413  mov     [rbp+57h+var_9C], 2EE0h
0x14001841a  mov     [rbp+57h+var_8C], r12d
0x14001841e  mov     [rbp+57h+var_80], r12d
0x140018422  mov     [rbp+57h+var_88], r12d
0x140018426  mov     [rbp+57h+var_78], r12d
0x14001842a  mov     rcx, [rcx+8]
0x14001842e  mov     [rsp+0E0h+var_C0], rax
0x140018433  call    cs:__imp_IoOpenDriverRegistryKey
0x14001843a  nop     dword ptr [rax+rax+00h]
0x14001843f  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140018446  mov     r15d, 4000004h
0x14001844c  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018453  test    eax, eax
0x140018455  js      loc_1400186FD
0x14001845b  mov     edx, 230h
0x140018460  mov     ecx, 100h
0x140018465  mov     r8d, 32343038h
0x14001846b  call    cs:__imp_ExAllocatePool2
0x140018472  nop     dword ptr [rax+rax+00h]
0x140018477  mov     r14, rax
0x14001847a  test    rax, rax
0x14001847d  jnz     short loc_1400184B7
0x14001847f  lea     rsi, WPP_RECORDER_INITIALIZED
0x140018486  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001848d  jz      loc_1400186FD
0x140018493  mov     rcx, cs:WPP_GLOBAL_Control
0x14001849a  lea     r9d, [r12+4Eh]
0x14001849f  lea     r8d, [r12+11h]
0x1400184a4  mov     [rsp+0E0h+var_C0], rbx
0x1400184a9  mov     rcx, [rcx+40h]
0x1400184ad  call    WPP_RECORDER_SF_
0x1400184b2  jmp     loc_1400186FD
0x1400184b7  mov     [r14+20h], r15d
0x1400184bb  mov     ecx, 120h
0x1400184c0  mov     [rax+8], ecx
0x1400184c3  mov     edx, 4
0x1400184c8  mov     [r14+30h], edx
0x1400184cc  lea     rax, aKeyboarddataqu; "KeyboardDataQueueSize"
0x1400184d3  mov     [r14+10h], rax
0x1400184d7  xorps   xmm0, xmm0
0x1400184da  lea     rax, [rdi+2BCh]
0x1400184e1  mov     [r14+18h], rax
0x1400184e5  lea     rax, [rbp+57h+var_A0]
0x1400184e9  mov     [r14+28h], rax
0x1400184ed  lea     rax, aOverridekeyboa; "OverrideKeyboardType"
0x1400184f4  mov     [r14+48h], rax
0x1400184f8  lea     rax, [rbp+57h+arg_0]
0x1400184fc  mov     [r14+50h], rax
0x140018500  lea     rax, [rbp+57h+var_94]
0x140018504  mov     [r14+60h], rax
0x140018508  lea     rax, aOverridekeyboa_0; "OverrideKeyboardSubType"
0x14001850f  mov     [r14+40h], ecx
0x140018513  mov     [r14+68h], edx
0x140018517  mov     [r14+58h], r15d
0x14001851b  mov     [r14+80h], rax
0x140018522  lea     rax, [rbp+57h+arg_8]
0x140018526  mov     [r14+88h], rax
0x14001852d  lea     rax, [rbp+57h+var_90]
0x140018531  mov     [r14+98h], rax
0x140018538  lea     rax, aPollstatusiter; "PollStatusIterations"
0x14001853f  mov     [r14+78h], ecx
0x140018543  mov     [r14+0A0h], edx
0x14001854a  mov     [r14+90h], r15d
0x140018551  mov     [r14+0B8h], rax
0x140018558  lea     rax, [rbp+57h+arg_10]
0x14001855c  mov     [r14+0C0h], rax
0x140018563  lea     rax, [rbp+57h+var_9C]
0x140018567  mov     [r14+0D0h], rax
0x14001856e  lea     rax, aPowercapabilit; "PowerCapabilities"
0x140018575  mov     [r14+0B0h], ecx
0x14001857c  mov     [r14+0D8h], edx
0x140018583  mov     [r14+0C8h], r15d
0x14001858a  mov     [r14+0F0h], rax
0x140018591  lea     rax, [rbp+57h+arg_18]
0x140018595  mov     [r14+0F8h], rax
0x14001859c  lea     rax, [rbp+57h+var_84]
0x1400185a0  mov     [r14+108h], rax
0x1400185a7  lea     rax, aCrashonctrlscr; "CrashOnCtrlScroll"
0x1400185ae  mov     [r14+0E8h], ecx
0x1400185b5  mov     [r14+110h], edx
0x1400185bc  mov     [r14+100h], r15d
0x1400185c3  mov     [r14+128h], rax
0x1400185ca  lea     rax, [rbp+57h+var_8C]
0x1400185ce  mov     [r14+130h], rax
0x1400185d5  lea     rax, [rbp+57h+var_80]
0x1400185d9  mov     [r14+140h], rax
0x1400185e0  lea     rax, aKeyboardfailed; "KeyboardFailedReset"
0x1400185e7  mov     [r14+120h], ecx
0x1400185ee  mov     [r14+148h], edx
0x1400185f5  mov     [r14+138h], r15d
0x1400185fc  mov     [r14+160h], rax
0x140018603  lea     rax, [rbp+57h+var_98]
0x140018607  mov     [r14+168h], rax
0x14001860e  lea     rax, [rbp+57h+var_7C]
0x140018612  mov     [r14+178h], rax
0x140018619  lea     rax, aKdenableonctrl; "KdEnableOnCtrlSysRq"
0x140018620  mov     [r14+158h], ecx
0x140018627  mov     [r14+180h], edx
0x14001862e  mov     [r14+170h], r15d
0x140018635  mov     [r14+198h], rax
0x14001863c  lea     rax, [rbp+57h+var_88]
0x140018640  mov     [r14+1A0h], rax
0x140018647  lea     rax, [rbp+57h+var_78]
0x14001864b  mov     [r14+190h], ecx
0x140018652  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140018656  mov     [r14+1B8h], edx
0x14001865d  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x140018664  mov     [r14+1B0h], rax
0x14001866b  mov     [r14+1A8h], r15d
0x140018672  mov     rbx, [rbp+57h+Handle]
0x140018676  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001867a  call    cs:__imp_RtlInitUnicodeString
0x140018681  nop     dword ptr [rax+rax+00h]
0x140018686  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14001868a  call    cs:__imp_MmGetSystemRoutineAddress
0x140018691  nop     dword ptr [rax+rax+00h]
0x140018696  mov     r8, r14
0x140018699  mov     [rsp+0E0h+var_C0], r12
0x14001869e  test    rax, rax
0x1400186a1  mov     rdx, rbx
0x1400186a4  mov     ecx, 0C0000000h
0x1400186a9  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x1400186b1  xor     r9d, r9d
0x1400186b4  call    _guard_dispatch_icall
0x1400186b9  test    eax, eax
0x1400186bb  jns     short loc_1400186F2
0x1400186bd  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400186c4  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x1400186cb  jz      short loc_1400186F9
0x1400186cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400186d4  mov     r9d, 4Fh ; 'O'
0x1400186da  mov     dword ptr [rsp+0E0h+var_B8], eax
0x1400186de  mov     [rsp+0E0h+var_C0], rbx
0x1400186e3  mov     rcx, [rcx+40h]
0x1400186e7  lea     r8d, [r9-3Fh]
0x1400186eb  call    WPP_RECORDER_SF_D
0x1400186f0  jmp     short loc_1400186FD
0x1400186f2  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x1400186f9  test    eax, eax
0x1400186fb  jns     short loc_140018715
0x1400186fd  movzx   eax, word ptr [rbp+57h+var_9C]
0x140018701  lea     r15, [rdi+2BCh]
0x140018708  mov     [r13+4Ch], ax
0x14001870d  mov     eax, [rbp+57h+var_A0]
0x140018710  mov     [r15], eax
0x140018713  jmp     short loc_140018725
0x140018715  movzx   eax, word ptr [rbp+57h+arg_10]
0x140018719  lea     r15, [rdi+2BCh]
0x140018720  mov     [r13+4Ch], ax
0x140018725  mov     ecx, [rbp+57h+var_98]
0x140018728  mov     eax, ecx
0x14001872a  test    ecx, ecx
0x14001872c  jz      short loc_140018743
0x14001872e  sub     eax, 1
0x140018731  jz      short loc_140018743
0x140018733  cmp     eax, 1
0x140018736  jz      short loc_140018743
0x140018738  mov     byte ptr [rdi+3BAh], 1
0x14001873f  mov     cl, 1
0x140018741  jmp     short loc_140018749
0x140018743  mov     [rdi+3BAh], cl
0x140018749  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x140018750  jz      short loc_140018778
0x140018752  movzx   eax, cl
0x140018755  mov     r9d, 50h ; 'P'
0x14001875b  mov     rcx, cs:WPP_GLOBAL_Control
0x140018762  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140018766  mov     [rsp+0E0h+var_C0], rbx
0x14001876b  lea     r8d, [r9-42h]
0x14001876f  mov     rcx, [rcx+40h]
0x140018773  call    WPP_RECORDER_SF_d
0x140018778  mov     rcx, [rdi+20h]; DeviceObject
0x14001877c  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x140018780  mov     edx, 1; DevInstKeyType
0x140018785  mov     r8d, 20000h; DesiredAccess
0x14001878b  call    cs:__imp_IoOpenDeviceRegistryKey
0x140018792  nop     dword ptr [rax+rax+00h]
0x140018797  test    eax, eax
0x140018799  js      loc_140018974
0x14001879f  mov     eax, [r15]
0x1400187a2  xor     edx, edx; Val
0x1400187a4  mov     [rbp+57h+var_74], eax
0x1400187a7  mov     r8d, 230h; Size
0x1400187ad  mov     eax, [rbp+57h+arg_18]
0x1400187b0  mov     rcx, r14; void *
0x1400187b3  mov     [rbp+57h+var_64], eax
0x1400187b6  mov     eax, [rbp+57h+arg_0]
0x1400187b9  mov     [rbp+57h+var_70], eax
0x1400187bc  mov     eax, [rbp+57h+arg_8]
0x1400187bf  mov     [rbp+57h+var_6C], eax
0x1400187c2  mov     eax, [rbp+57h+arg_10]
0x1400187c5  mov     [rbp+57h+var_68], eax
0x1400187c8  call    memset
0x1400187cd  mov     [r14+18h], r15
0x1400187d1  lea     rax, aKeyboarddataqu; "KeyboardDataQueueSize"
0x1400187d8  mov     [r14+10h], rax
0x1400187dc  mov     ecx, 20h ; ' '
0x1400187e1  mov     [r14+8], ecx
0x1400187e5  lea     rax, [rbp+57h+var_74]
0x1400187e9  mov     [r14+28h], rax
0x1400187ed  mov     r8d, 4000004h
0x1400187f3  mov     [r14+20h], r8d
0x1400187f7  lea     rax, aOverridekeyboa; "OverrideKeyboardType"
0x1400187fe  lea     edx, [rcx-1Ch]
0x140018801  xorps   xmm0, xmm0
0x140018804  mov     [r14+30h], edx
0x140018808  mov     [r14+48h], rax
0x14001880c  lea     rax, [rbp+57h+arg_0]
0x140018810  mov     [r14+50h], rax
0x140018814  lea     rax, [rbp+57h+var_70]
0x140018818  mov     [r14+60h], rax
0x14001881c  lea     rax, aOverridekeyboa_0; "OverrideKeyboardSubType"
0x140018823  mov     [r14+40h], ecx
0x140018827  mov     [r14+68h], edx
0x14001882b  mov     [r14+58h], r8d
0x14001882f  mov     [r14+80h], rax
0x140018836  lea     rax, [rbp+57h+arg_8]
0x14001883a  mov     [r14+88h], rax
0x140018841  lea     rax, [rbp+57h+var_6C]
0x140018845  mov     [r14+98h], rax
0x14001884c  lea     rax, aPollstatusiter; "PollStatusIterations"
0x140018853  mov     [r14+78h], ecx
0x140018857  mov     [r14+0A0h], edx
0x14001885e  mov     [r14+90h], r8d
0x140018865  mov     [r14+0B8h], rax
0x14001886c  lea     rax, [rbp+57h+arg_10]
0x140018870  mov     [r14+0C0h], rax
0x140018877  lea     rax, [rbp+57h+var_68]
0x14001887b  mov     [r14+0D0h], rax
0x140018882  lea     rax, aPowercapabilit; "PowerCapabilities"
0x140018889  mov     [r14+0B0h], ecx
0x140018890  mov     [r14+0D8h], edx
0x140018897  mov     [r14+0C8h], r8d
0x14001889e  mov     [r14+0F0h], rax
0x1400188a5  lea     rax, [rbp+57h+arg_18]
0x1400188a9  mov     [r14+0F8h], rax
0x1400188b0  lea     rax, [rbp+57h+var_64]
0x1400188b4  mov     [r14+0E8h], ecx
0x1400188bb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400188bf  mov     [r14+110h], edx
0x1400188c6  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x1400188cd  mov     [r14+108h], rax
0x1400188d4  mov     [r14+100h], r8d
0x1400188db  mov     rbx, [rbp+57h+DeviceRegKey]
0x1400188df  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x1400188e3  call    cs:__imp_RtlInitUnicodeString
0x1400188ea  nop     dword ptr [rax+rax+00h]
0x1400188ef  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x1400188f3  call    cs:__imp_MmGetSystemRoutineAddress
0x1400188fa  nop     dword ptr [rax+rax+00h]
0x1400188ff  mov     r8, r14
0x140018902  mov     [rsp+0E0h+var_C0], r12
0x140018907  test    rax, rax
0x14001890a  mov     rdx, rbx
0x14001890d  mov     ecx, 40000000h
0x140018912  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14001891a  xor     r9d, r9d
0x14001891d  call    _guard_dispatch_icall
0x140018922  test    eax, eax
0x140018924  jns     short loc_14001895B
0x140018926  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x14001892d  lea     rbx, WPP_4c5c8ccea6b037357f7765b1595ce456_Traceguids
0x140018934  jz      short loc_140018962
0x140018936  mov     rcx, cs:WPP_GLOBAL_Control
0x14001893d  mov     r9d, 51h ; 'Q'
0x140018943  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140018947  mov     [rsp+0E0h+var_C0], rbx
  ... truncated ...
```
