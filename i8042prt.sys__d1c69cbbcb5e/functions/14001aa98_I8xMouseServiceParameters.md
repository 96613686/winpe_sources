# I8xMouseServiceParameters

- ea: `0x14001aa98`
- end: `0x14001b56d`
- name: `I8xMouseServiceParameters`
- size: `2773`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x14001c068`

## callees

- `0x1400014e0`
- `0x140004530`
- `0x140007b10`
- `0x14000a7b8`
- `0x14000bd6c`
- `0x14000bef4`
- `0x14000daa0`
- `0x14001aa98`
- `0x14001b830`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14001ab63`
- `ntoskrnl!ExAllocatePool2` at `0x14001ab63`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b54c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14001b54c`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ad5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001aeab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001b0ca`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001ad5f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001aeab`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001b0ca`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14001ab2a`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14001ab2a`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14001ad92`
- `ntoskrnl!RtlQueryRegistryValues` at `0x14001b0fd`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001ad6f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001b0da`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001ad6f`
- `ntoskrnl!MmGetSystemRoutineAddress` at `0x14001b0da`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001b46a`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001b4ea`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001b46a`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14001b4ea`
- `ntoskrnl!ZwClose` at `0x14001b1b0`
- `ntoskrnl!ZwClose` at `0x14001b536`
- `ntoskrnl!ZwClose` at `0x14001b1b0`
- `ntoskrnl!ZwClose` at `0x14001b536`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001ae7c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14001ae7c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001b20c`
- `ntoskrnl!RtlFreeUnicodeString` at `0x14001b20c`

## string_xrefs

- `0x14001ad38`: `RtlQueryRegistryValuesEx`
- `0x14001b09c`: `RtlQueryRegistryValuesEx`

## pseudocode

```c
void __fastcall I8xMouseServiceParameters(__int64 *a1)
{
  char v2; // r13
  __int64 v3; // rcx
  __int64 v4; // rdi
  int v5; // edx
  int v6; // r8d
  __int64 v7; // r9
  __int64 Pool2; // rax
  int *v9; // r14
  int *v10; // r15
  HANDLE v11; // rbx
  __int64 (__fastcall *SystemRoutineAddress)(__int64, HANDLE, __int64, _QWORD); // rax
  int v13; // eax
  int *v14; // r12
  NTSTATUS v15; // eax
  int v16; // edx
  int v17; // eax
  void *v18; // rbx
  __int64 (__fastcall *v19)(__int64, void *, __int64, _QWORD); // rax
  int v20; // eax
  int v21; // edx
  int v22; // r8d
  int v23; // r9d
  int v24; // r8d
  _UNKNOWN **v25; // rdx
  int v26; // eax
  int v27; // ecx
  __int16 v28; // ax
  char v29; // al
  char v30; // al
  int v31; // edx
  int v32; // ebx
  ULONG TimeIncrement; // eax
  unsigned int v34; // eax
  unsigned int v35; // edx
  unsigned int v36; // et2
  unsigned int v37; // ebx
  ULONG v38; // eax
  int v39; // eax
  int v40; // edx
  HANDLE *p_Handle; // [rsp+20h] [rbp-B9h]
  int v42; // [rsp+70h] [rbp-69h] BYREF
  int v43; // [rsp+74h] [rbp-65h] BYREF
  int v44; // [rsp+78h] [rbp-61h] BYREF
  int v45; // [rsp+7Ch] [rbp-5Dh] BYREF
  int v46; // [rsp+80h] [rbp-59h] BYREF
  int v47; // [rsp+84h] [rbp-55h] BYREF
  int v48; // [rsp+88h] [rbp-51h] BYREF
  int v49; // [rsp+8Ch] [rbp-4Dh] BYREF
  int v50; // [rsp+90h] [rbp-49h] BYREF
  int v51; // [rsp+94h] [rbp-45h] BYREF
  int v52; // [rsp+98h] [rbp-41h] BYREF
  int v53; // [rsp+9Ch] [rbp-3Dh] BYREF
  int v54; // [rsp+A0h] [rbp-39h] BYREF
  int v55; // [rsp+A4h] [rbp-35h] BYREF
  int v56; // [rsp+A8h] [rbp-31h] BYREF
  int v57; // [rsp+ACh] [rbp-2Dh] BYREF
  int v58; // [rsp+B0h] [rbp-29h] BYREF
  int v59; // [rsp+B4h] [rbp-25h] BYREF
  void *DeviceRegKey; // [rsp+B8h] [rbp-21h] BYREF
  HANDLE Handle; // [rsp+C0h] [rbp-19h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C8h] [rbp-11h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+D8h] [rbp-1h] BYREF
  int v64; // [rsp+140h] [rbp+67h] BYREF
  int v65; // [rsp+148h] [rbp+6Fh] BYREF
  int v66; // [rsp+150h] [rbp+77h] BYREF
  int v67; // [rsp+158h] [rbp+7Fh] BYREF

  v43 = 100;
  Handle = 0;
  DeviceRegKey = 0;
  v44 = 10000000;
  v53 = 0;
  v45 = 1;
  v54 = 60;
  v67 = 60;
  v2 = 2;
  v3 = *a1;
  v55 = 3;
  v4 = 0;
  v42 = 3;
  v65 = 1;
  v59 = 1500;
  v56 = 0;
  v66 = 2;
  v64 = 0;
  v57 = 1000;
  v58 = 0;
  UnicodeString = 0;
  p_Handle = &Handle;
  if ( (int)IoOpenDriverRegistryKey(*(_QWORD *)(v3 + 8), 0, 1, 0) < 0 )
  {
LABEL_10:
    v9 = (int *)(a1 + 74);
    *((_DWORD *)a1 + 148) = v43;
    v10 = (int *)(a1 + 128);
    *((_BYTE *)a1 + 1106) = v45;
    *((_DWORD *)a1 + 256) = v44;
    goto LABEL_11;
  }
  Pool2 = ExAllocatePool2(256, 616, 842281016, v7);
  v4 = Pool2;
  if ( !Pool2 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        17,
        96,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    goto LABEL_10;
  }
  *(_QWORD *)(Pool2 + 16) = L"MouseDataQueueSize";
  v9 = (int *)(a1 + 74);
  *(_QWORD *)(Pool2 + 24) = a1 + 74;
  v10 = (int *)(a1 + 128);
  *(_DWORD *)(Pool2 + 8) = 288;
  *(_DWORD *)(Pool2 + 32) = 67108868;
  *(_DWORD *)(Pool2 + 48) = 4;
  *(_QWORD *)(Pool2 + 40) = &v43;
  *(_QWORD *)(Pool2 + 72) = L"NumberOfButtons";
  *(_QWORD *)(Pool2 + 80) = &v66;
  *(_QWORD *)(Pool2 + 96) = &v53;
  *(_DWORD *)(Pool2 + 64) = 288;
  *(_DWORD *)(Pool2 + 104) = 4;
  *(_DWORD *)(Pool2 + 88) = 67108868;
  *(_QWORD *)(Pool2 + 128) = L"SampleRate";
  *(_QWORD *)(Pool2 + 136) = &v67;
  *(_QWORD *)(Pool2 + 152) = &v54;
  *(_DWORD *)(Pool2 + 120) = 288;
  *(_DWORD *)(Pool2 + 160) = 4;
  *(_DWORD *)(Pool2 + 144) = 67108868;
  *(_QWORD *)(Pool2 + 184) = L"MouseResolution";
  *(_QWORD *)(Pool2 + 192) = &v42;
  *(_QWORD *)(Pool2 + 208) = &v55;
  *(_DWORD *)(Pool2 + 176) = 288;
  *(_DWORD *)(Pool2 + 216) = 4;
  *(_DWORD *)(Pool2 + 200) = 67108868;
  *(_QWORD *)(Pool2 + 240) = L"MouseSynchIn100ns";
  *(_QWORD *)(Pool2 + 264) = &v44;
  *(_DWORD *)(Pool2 + 232) = 288;
  *(_DWORD *)(Pool2 + 272) = 4;
  *(_QWORD *)(Pool2 + 248) = a1 + 128;
  *(_DWORD *)(Pool2 + 256) = 67108868;
  *(_QWORD *)(Pool2 + 296) = L"EnableWheelDetection";
  *(_QWORD *)(Pool2 + 304) = &v65;
  *(_QWORD *)(Pool2 + 320) = &v45;
  *(_DWORD *)(Pool2 + 288) = 288;
  *(_DWORD *)(Pool2 + 328) = 4;
  *(_DWORD *)(Pool2 + 312) = 67108868;
  *(_QWORD *)(Pool2 + 352) = L"MouseInitializePolled";
  *(_QWORD *)(Pool2 + 360) = &v64;
  *(_QWORD *)(Pool2 + 376) = &v56;
  *(_DWORD *)(Pool2 + 344) = 288;
  *(_DWORD *)(Pool2 + 384) = 4;
  *(_DWORD *)(Pool2 + 368) = 67108868;
  *(_QWORD *)(Pool2 + 408) = L"MouseResendStallTime";
  *(_QWORD *)(Pool2 + 416) = a1 + 137;
  *(_DWORD *)(Pool2 + 400) = 288;
  *(_DWORD *)(Pool2 + 440) = 4;
  *(_QWORD *)(Pool2 + 432) = &v57;
  *(_DWORD *)(Pool2 + 424) = 67108868;
  v11 = Handle;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
  SystemRoutineAddress = (__int64 (__fastcall *)(__int64, HANDLE, __int64, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
  LODWORD(p_Handle) = 0;
  if ( !SystemRoutineAddress )
    SystemRoutineAddress = (__int64 (__fastcall *)(__int64, HANDLE, __int64, _QWORD))RtlQueryRegistryValues;
  v13 = SystemRoutineAddress(3221225472LL, v11, v4, 0);
  if ( v13 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v5,
        16,
        97,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v13);
    goto LABEL_10;
  }
LABEL_11:
  v14 = (int *)a1 + 257;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_ddddddddd(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      v6,
      v7,
      (_DWORD)p_Handle,
      *v9,
      v66,
      v67,
      v42,
      *v10,
      v65,
      *v14,
      v64,
      *((_DWORD *)a1 + 274));
  v15 = IoOpenDeviceRegistryKey((PDEVICE_OBJECT)a1[4], 1u, 0x20000u, &DeviceRegKey);
  if ( v15 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        v16,
        17,
        101,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        v15);
  }
  else
  {
    v46 = 0;
    v47 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    RtlInitUnicodeString(&UnicodeString, 0);
    v46 = *v9;
    v47 = v66;
    v48 = v67;
    v49 = v42;
    v50 = *v10;
    v51 = v65;
    v17 = v64;
    *(_DWORD *)(v4 + 8) = 288;
    *(_QWORD *)(v4 + 24) = v9;
    *(_DWORD *)(v4 + 32) = 67108868;
    *(_DWORD *)(v4 + 48) = 4;
    v52 = v17;
    *(_QWORD *)(v4 + 16) = L"MouseDataQueueSize";
    *(_QWORD *)(v4 + 40) = &v46;
    *(_QWORD *)(v4 + 72) = L"NumberOfButtons";
    *(_QWORD *)(v4 + 80) = &v66;
    *(_QWORD *)(v4 + 96) = &v47;
    *(_DWORD *)(v4 + 64) = 288;
    *(_DWORD *)(v4 + 88) = 67108868;
    *(_DWORD *)(v4 + 104) = 4;
    *(_QWORD *)(v4 + 128) = L"SampleRate";
    *(_QWORD *)(v4 + 136) = &v67;
    *(_QWORD *)(v4 + 152) = &v48;
    *(_DWORD *)(v4 + 120) = 288;
    *(_DWORD *)(v4 + 144) = 67108868;
    *(_DWORD *)(v4 + 160) = 4;
    *(_QWORD *)(v4 + 184) = L"MouseResolution";
    *(_QWORD *)(v4 + 192) = &v42;
    *(_QWORD *)(v4 + 208) = &v49;
    *(_DWORD *)(v4 + 176) = 288;
    *(_DWORD *)(v4 + 200) = 67108868;
    *(_DWORD *)(v4 + 216) = 4;
    *(_QWORD *)(v4 + 240) = L"MouseSynchIn100ns";
    *(_QWORD *)(v4 + 264) = &v50;
    *(_DWORD *)(v4 + 232) = 288;
    *(_QWORD *)(v4 + 248) = v10;
    *(_DWORD *)(v4 + 256) = 67108868;
    *(_DWORD *)(v4 + 272) = 4;
    *(_QWORD *)(v4 + 296) = L"EnableWheelDetection";
    *(_QWORD *)(v4 + 304) = &v65;
    *(_QWORD *)(v4 + 320) = &v51;
    *(_DWORD *)(v4 + 288) = 288;
    *(_DWORD *)(v4 + 312) = 67108868;
    *(_DWORD *)(v4 + 328) = 4;
    *(_DWORD *)(v4 + 344) = 288;
    *(_QWORD *)(v4 + 352) = L"MouseInitializePolled";
    *(_DWORD *)(v4 + 384) = 4;
    *(_QWORD *)(v4 + 360) = &v64;
    *(_QWORD *)(v4 + 376) = &v52;
    *(_DWORD *)(v4 + 368) = 67108868;
    *(_QWORD *)(v4 + 408) = L"WheelDetectIDs";
    *(_QWORD *)(v4 + 416) = &UnicodeString;
    *(_QWORD *)(v4 + 432) = &v58;
    *(_DWORD *)(v4 + 440) = 4;
    *(_DWORD *)(v4 + 400) = 304;
    *(_DWORD *)(v4 + 424) = 117440519;
    *(_QWORD *)(v4 + 464) = L"WheelDetectionTimeout";
    *(_DWORD *)(v4 + 456) = 288;
    *(_DWORD *)(v4 + 496) = 4;
    *(_QWORD *)(v4 + 488) = &v59;
    *(_QWORD *)(v4 + 472) = v14;
    *(_DWORD *)(v4 + 480) = 67108868;
    v18 = DeviceRegKey;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"RtlQueryRegistryValuesEx");
    v19 = (__int64 (__fastcall *)(__int64, void *, __int64, _QWORD))MmGetSystemRoutineAddress(&DestinationString);
    if ( !v19 )
      v19 = (__int64 (__fastcall *)(__int64, void *, __int64, _QWORD))RtlQueryRegistryValues;
    v20 = v19(0x40000000, v18, v4, 0);
    if ( v20 < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_D(
          WPP_GLOBAL_Control->DeviceExtension,
          v21,
          17,
          100,
          (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
          v20);
    }
    else if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_dddddddd(
        WPP_GLOBAL_Control->DeviceExtension,
        v21,
        v22,
        v23,
        0,
        *v9,
        v66,
        v67,
        v42,
        *v10,
        v65,
        v64,
        *v14);
    }
    ZwClose(DeviceRegKey);
  }
  MouseCopyWheelIDs(a1 + 129, &UnicodeString);
  RtlFreeUnicodeString(&UnicodeString);
  v25 = &WPP_RECORDER_INITIALIZED;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      14,
      102,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    v25 = &WPP_RECORDER_INITIALIZED;
  }
  v26 = *v9;
  if ( !*v9 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      WPP_RECORDER_SF_SD(
        WPP_GLOBAL_Control->DeviceExtension,
        (unsigned int)&WPP_RECORDER_INITIALIZED,
        v24,
        103,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        (__int64)L"MouseDataQueueSize",
        0);
      v25 = &WPP_RECORDER_INITIALIZED;
    }
    v26 = v43;
    *v9 = v43;
  }
  v27 = v65;
  *v9 = 24 * v26;
  *((_BYTE *)a1 + 1108) = v64;
  if ( v27 == 1 || v27 == 2 )
  {
    *((_BYTE *)a1 + 1106) = v27;
  }
  else
  {
    *((_BYTE *)a1 + 1106) = 0;
    LOBYTE(v27) = 0;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      (unsigned int)&WPP_RECORDER_INITIALIZED,
      14,
      104,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v27);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_D(
        WPP_GLOBAL_Control->DeviceExtension,
        (_DWORD)v25,
        14,
        105,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        *v9);
  }
  v28 = v66;
  if ( v66 )
  {
    *((_BYTE *)a1 + 1107) = v66;
    v2 = v28;
    *((_WORD *)a1 + 293) = v28;
  }
  else
  {
    *((_BYTE *)a1 + 1107) = 0;
    *((_WORD *)a1 + 293) = 2;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v25,
      14,
      106,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v2);
  v29 = v67;
  *((_WORD *)a1 + 294) = v67;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v25,
      14,
      107,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v29);
  v30 = v42;
  *((_BYTE *)a1 + 1105) = v42;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v25,
      14,
      108,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v30);
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_d(
        WPP_GLOBAL_Control->DeviceExtension,
        v31,
        14,
        109,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
        *((_DWORD *)a1 + 274));
  }
  if ( (unsigned int)*v14 <= 0xFA0 )
  {
    v32 = *v14;
  }
  else
  {
    v32 = 1500;
    *v14 = 1500;
  }
  TimeIncrement = KeQueryTimeIncrement();
  v36 = 10000 * v32 % TimeIncrement;
  v34 = 10000 * v32 / TimeIncrement;
  v35 = v36;
  *v14 = v34;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v35,
      14,
      110,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v34);
  if ( !*v10 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_SF_(
        WPP_GLOBAL_Control->DeviceExtension,
        v35,
        17,
        111,
        (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids);
    *v10 = v44;
  }
  v37 = *v10;
  v38 = KeQueryTimeIncrement();
  v40 = v37 % v38;
  v39 = v37 / v38;
  *v10 = v39;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_D(
      WPP_GLOBAL_Control->DeviceExtension,
      v40,
      14,
      112,
      (__int64)WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids,
      v39);
  if ( Handle )
    ZwClose(Handle);
  if ( v4 )
    ExFreePoolWithTag((PVOID)v4, 0);
}

```

## disassembly

```asm
0x14001aa98  push    rbp
0x14001aa9a  push    rbx
0x14001aa9b  push    rsi
0x14001aa9c  push    rdi
0x14001aa9d  push    r12
0x14001aa9f  push    r13
0x14001aaa1  push    r14
0x14001aaa3  push    r15
0x14001aaa5  lea     rbp, [rsp-1Fh]
0x14001aaaa  sub     rsp, 0F8h
0x14001aab1  xor     ebx, ebx
0x14001aab3  mov     [rbp+57h+var_BC], 64h ; 'd'
0x14001aaba  mov     rsi, rcx
0x14001aabd  mov     [rbp+57h+Handle], rbx
0x14001aac1  xorps   xmm0, xmm0
0x14001aac4  mov     [rbp+57h+DeviceRegKey], rbx
0x14001aac8  mov     [rbp+57h+var_B8], 989680h
0x14001aacf  xor     r9d, r9d
0x14001aad2  lea     edx, [rbx+1]
0x14001aad5  mov     [rbp+57h+var_94], ebx
0x14001aad8  lea     ecx, [rbx+3Ch]
0x14001aadb  mov     [rbp+57h+var_B4], edx
0x14001aade  mov     [rbp+57h+var_90], ecx
0x14001aae1  lea     eax, [rbx+3]
0x14001aae4  mov     [rbp+57h+arg_18], ecx
0x14001aae7  lea     r13d, [rbx+2]
0x14001aaeb  mov     rcx, [rsi]
0x14001aaee  mov     r8d, edx
0x14001aaf1  mov     [rbp+57h+var_8C], eax
0x14001aaf4  mov     edi, ebx
0x14001aaf6  mov     [rbp+57h+var_C0], eax
0x14001aaf9  lea     rax, [rbp+57h+Handle]
0x14001aafd  mov     [rbp+57h+arg_8], edx
0x14001ab00  xor     edx, edx
0x14001ab02  mov     [rbp+57h+var_7C], 5DCh
0x14001ab09  mov     [rbp+57h+var_88], ebx
0x14001ab0c  mov     [rbp+57h+arg_10], r13d
0x14001ab10  mov     [rbp+57h+arg_0], ebx
0x14001ab13  mov     [rbp+57h+var_84], 3E8h
0x14001ab1a  mov     [rbp+57h+var_80], ebx
0x14001ab1d  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x14001ab21  mov     rcx, [rcx+8]
0x14001ab25  mov     [rsp+130h+var_110], rax
0x14001ab2a  call    cs:__imp_IoOpenDriverRegistryKey
0x14001ab31  nop     dword ptr [rax+rax+00h]
0x14001ab36  lea     r12, WPP_RECORDER_INITIALIZED
0x14001ab3d  lea     r14, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001ab44  lea     r15, aMousedataqueue; "MouseDataQueueSize"
0x14001ab4b  test    eax, eax
0x14001ab4d  js      loc_14001ADD9
0x14001ab53  mov     edx, 268h
0x14001ab58  mov     ecx, 100h
0x14001ab5d  mov     r8d, 32343038h
0x14001ab63  call    cs:__imp_ExAllocatePool2
0x14001ab6a  nop     dword ptr [rax+rax+00h]
0x14001ab6f  mov     rdi, rax
0x14001ab72  test    rax, rax
0x14001ab75  jnz     short loc_14001ABA6
0x14001ab77  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001ab7e  jz      loc_14001ADD9
0x14001ab84  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ab8b  lea     r9d, [rbx+60h]
0x14001ab8f  lea     r8d, [rbx+11h]
0x14001ab93  mov     [rsp+130h+var_110], r14
0x14001ab98  mov     rcx, [rcx+40h]
0x14001ab9c  call    WPP_RECORDER_SF_
0x14001aba1  jmp     loc_14001ADD9
0x14001aba6  mov     [rax+10h], r15
0x14001abaa  lea     r14, [rsi+250h]
0x14001abb1  mov     [rax+18h], r14
0x14001abb5  lea     r15, [rsi+400h]
0x14001abbc  mov     edx, 120h
0x14001abc1  mov     r8d, 4000004h
0x14001abc7  mov     [rax+8], edx
0x14001abca  mov     ecx, 4
0x14001abcf  mov     [rax+20h], r8d
0x14001abd3  xorps   xmm0, xmm0
0x14001abd6  mov     [rdi+30h], ecx
0x14001abd9  lea     rax, [rbp+57h+var_BC]
0x14001abdd  mov     [rdi+28h], rax
0x14001abe1  lea     rax, aNumberofbutton; "NumberOfButtons"
0x14001abe8  mov     [rdi+48h], rax
0x14001abec  lea     rax, [rbp+57h+arg_10]
0x14001abf0  mov     [rdi+50h], rax
0x14001abf4  lea     rax, [rbp+57h+var_94]
0x14001abf8  mov     [rdi+60h], rax
0x14001abfc  lea     rax, aSamplerate; "SampleRate"
0x14001ac03  mov     [rdi+40h], edx
0x14001ac06  mov     [rdi+68h], ecx
0x14001ac09  mov     [rdi+58h], r8d
0x14001ac0d  mov     [rdi+80h], rax
0x14001ac14  lea     rax, [rbp+57h+arg_18]
0x14001ac18  mov     [rdi+88h], rax
0x14001ac1f  lea     rax, [rbp+57h+var_90]
0x14001ac23  mov     [rdi+98h], rax
0x14001ac2a  lea     rax, aMouseresolutio; "MouseResolution"
0x14001ac31  mov     [rdi+78h], edx
0x14001ac34  mov     [rdi+0A0h], ecx
0x14001ac3a  mov     [rdi+90h], r8d
0x14001ac41  mov     [rdi+0B8h], rax
0x14001ac48  lea     rax, [rbp+57h+var_C0]
0x14001ac4c  mov     [rdi+0C0h], rax
0x14001ac53  lea     rax, [rbp+57h+var_8C]
0x14001ac57  mov     [rdi+0D0h], rax
0x14001ac5e  lea     rax, aMousesynchin10; "MouseSynchIn100ns"
0x14001ac65  mov     [rdi+0B0h], edx
0x14001ac6b  mov     [rdi+0D8h], ecx
0x14001ac71  mov     [rdi+0C8h], r8d
0x14001ac78  mov     [rdi+0F0h], rax
0x14001ac7f  lea     rax, [rbp+57h+var_B8]
0x14001ac83  mov     [rdi+108h], rax
0x14001ac8a  lea     rax, aEnablewheeldet; "EnableWheelDetection"
0x14001ac91  mov     [rdi+0E8h], edx
0x14001ac97  mov     [rdi+110h], ecx
0x14001ac9d  mov     [rdi+0F8h], r15
0x14001aca4  mov     [rdi+100h], r8d
0x14001acab  mov     [rdi+128h], rax
0x14001acb2  lea     rax, [rbp+57h+arg_8]
0x14001acb6  mov     [rdi+130h], rax
0x14001acbd  lea     rax, [rbp+57h+var_B4]
0x14001acc1  mov     [rdi+140h], rax
0x14001acc8  lea     rax, aMouseinitializ; "MouseInitializePolled"
0x14001accf  mov     [rdi+120h], edx
0x14001acd5  mov     [rdi+148h], ecx
0x14001acdb  mov     [rdi+138h], r8d
0x14001ace2  mov     [rdi+160h], rax
0x14001ace9  lea     rax, [rbp+57h+arg_0]
0x14001aced  mov     [rdi+168h], rax
0x14001acf4  lea     rax, [rbp+57h+var_88]
0x14001acf8  mov     [rdi+178h], rax
0x14001acff  lea     rax, aMouseresendsta; "MouseResendStallTime"
0x14001ad06  mov     [rdi+158h], edx
0x14001ad0c  mov     [rdi+180h], ecx
0x14001ad12  mov     [rdi+170h], r8d
0x14001ad19  mov     [rdi+198h], rax
0x14001ad20  lea     rax, [rsi+448h]
0x14001ad27  mov     [rdi+1A0h], rax
0x14001ad2e  lea     rax, [rbp+57h+var_84]
0x14001ad32  mov     [rdi+190h], edx
0x14001ad38  lea     rdx, aRtlqueryregist; "RtlQueryRegistryValuesEx"
0x14001ad3f  mov     [rdi+1B8h], ecx
0x14001ad45  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x14001ad49  mov     [rdi+1B0h], rax
0x14001ad50  mov     [rdi+1A8h], r8d
0x14001ad57  mov     rbx, [rbp+57h+Handle]
0x14001ad5b  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x14001ad5f  call    cs:__imp_RtlInitUnicodeString
0x14001ad66  nop     dword ptr [rax+rax+00h]
0x14001ad6b  lea     rcx, [rbp+57h+DestinationString]; SystemRoutineName
0x14001ad6f  call    cs:__imp_MmGetSystemRoutineAddress
0x14001ad76  nop     dword ptr [rax+rax+00h]
0x14001ad7b  mov     r8, rdi
0x14001ad7e  mov     [rsp+130h+var_110], 0
0x14001ad87  test    rax, rax
0x14001ad8a  mov     rdx, rbx
0x14001ad8d  mov     ecx, 0C0000000h
0x14001ad92  cmovz   rax, cs:__imp_RtlQueryRegistryValues
0x14001ad9a  xor     r9d, r9d
0x14001ad9d  call    _guard_dispatch_icall
0x14001ada2  xor     ebx, ebx
0x14001ada4  test    eax, eax
0x14001ada6  jns     short loc_14001ADFC
0x14001ada8  cmp     cs:WPP_RECORDER_INITIALIZED, r12
0x14001adaf  jz      short loc_14001ADD9
0x14001adb1  mov     rcx, cs:WPP_GLOBAL_Control
0x14001adb8  lea     r9d, [rbx+61h]
0x14001adbc  mov     dword ptr [rsp+130h+var_108], eax
0x14001adc0  lea     r8d, [rbx+10h]
0x14001adc4  lea     rax, WPP_3ba0d2ffedf6348d39b9a2efcc80fb77_Traceguids
0x14001adcb  mov     [rsp+130h+var_110], rax
0x14001add0  mov     rcx, [rcx+40h]
0x14001add4  call    WPP_RECORDER_SF_D
0x14001add9  mov     eax, [rbp+57h+var_BC]
0x14001addc  lea     r14, [rsi+250h]
0x14001ade3  mov     [r14], eax
0x14001ade6  lea     r15, [rsi+400h]
0x14001aded  mov     al, byte ptr [rbp+57h+var_B4]
0x14001adf0  mov     [rsi+452h], al
0x14001adf6  mov     eax, [rbp+57h+var_B8]
0x14001adf9  mov     [r15], eax
0x14001adfc  lea     rax, [rsi+448h]
0x14001ae03  lea     rcx, WPP_RECORDER_INITIALIZED
0x14001ae0a  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x14001ae11  lea     r12, [rsi+404h]
0x14001ae18  jz      short loc_14001AE69
0x14001ae1a  mov     eax, [rax]
0x14001ae1c  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ae23  mov     [rsp+130h+var_C8], eax
0x14001ae27  mov     eax, [rbp+57h+arg_0]
0x14001ae2a  mov     [rsp+130h+var_D0], eax
0x14001ae2e  mov     eax, [r12]
0x14001ae32  mov     rcx, [rcx+40h]
0x14001ae36  mov     [rsp+130h+var_D8], eax
0x14001ae3a  mov     eax, [rbp+57h+arg_8]
0x14001ae3d  mov     [rsp+130h+var_E0], eax
0x14001ae41  mov     eax, [r15]
0x14001ae44  mov     [rsp+130h+var_E8], eax
0x14001ae48  mov     eax, [rbp+57h+var_C0]
0x14001ae4b  mov     [rsp+130h+var_F0], eax
0x14001ae4f  mov     eax, [rbp+57h+arg_18]
0x14001ae52  mov     [rsp+130h+var_F8], eax
0x14001ae56  mov     eax, [rbp+57h+arg_10]
0x14001ae59  mov     [rsp+130h+var_100], eax
0x14001ae5d  mov     eax, [r14]
0x14001ae60  mov     dword ptr [rsp+130h+var_108], eax
0x14001ae64  call    WPP_RECORDER_SF_ddddddddd
0x14001ae69  mov     rcx, [rsi+20h]; DeviceObject
0x14001ae6d  lea     r9, [rbp+57h+DeviceRegKey]; DeviceRegKey
0x14001ae71  mov     edx, 1; DevInstKeyType
0x14001ae76  mov     r8d, 20000h; DesiredAccess
0x14001ae7c  call    cs:__imp_IoOpenDeviceRegistryKey
0x14001ae83  nop     dword ptr [rax+rax+00h]
0x14001ae88  test    eax, eax
0x14001ae8a  js      loc_14001B1BE
0x14001ae90  xor     edx, edx; SourceString
0x14001ae92  mov     [rbp+57h+var_B0], ebx
0x14001ae95  lea     rcx, [rbp+57h+UnicodeString]; DestinationString
0x14001ae99  mov     [rbp+57h+var_AC], ebx
0x14001ae9c  mov     [rbp+57h+var_A8], ebx
0x14001ae9f  mov     [rbp+57h+var_A4], ebx
0x14001aea2  mov     [rbp+57h+var_A0], ebx
0x14001aea5  mov     [rbp+57h+var_9C], ebx
0x14001aea8  mov     [rbp+57h+var_98], ebx
0x14001aeab  call    cs:__imp_RtlInitUnicodeString
0x14001aeb2  nop     dword ptr [rax+rax+00h]
0x14001aeb7  mov     eax, [r14]
0x14001aeba  mov     edx, 120h
0x14001aebf  mov     [rbp+57h+var_B0], eax
0x14001aec2  mov     r8d, 4000004h
0x14001aec8  mov     eax, [rbp+57h+arg_10]
0x14001aecb  mov     ecx, 4
0x14001aed0  mov     [rbp+57h+var_AC], eax
0x14001aed3  mov     eax, [rbp+57h+arg_18]
0x14001aed6  mov     [rbp+57h+var_A8], eax
0x14001aed9  mov     eax, [rbp+57h+var_C0]
0x14001aedc  mov     [rbp+57h+var_A4], eax
0x14001aedf  mov     eax, [r15]
0x14001aee2  mov     [rbp+57h+var_A0], eax
0x14001aee5  mov     eax, [rbp+57h+arg_8]
0x14001aee8  mov     [rbp+57h+var_9C], eax
0x14001aeeb  mov     eax, [rbp+57h+arg_0]
0x14001aeee  mov     [rdi+8], edx
0x14001aef1  mov     [rdi+18h], r14
0x14001aef5  mov     [rdi+20h], r8d
0x14001aef9  mov     [rdi+30h], ecx
0x14001aefc  mov     [rbp+57h+var_98], eax
0x14001aeff  lea     rax, aMousedataqueue; "MouseDataQueueSize"
0x14001af06  mov     [rdi+10h], rax
0x14001af0a  lea     rax, [rbp+57h+var_B0]
0x14001af0e  mov     [rdi+28h], rax
0x14001af12  lea     rax, aNumberofbutton; "NumberOfButtons"
0x14001af19  mov     [rdi+48h], rax
0x14001af1d  lea     rax, [rbp+57h+arg_10]
0x14001af21  mov     [rdi+50h], rax
0x14001af25  lea     rax, [rbp+57h+var_AC]
0x14001af29  mov     [rdi+60h], rax
0x14001af2d  lea     rax, aSamplerate; "SampleRate"
0x14001af34  mov     [rdi+40h], edx
0x14001af37  mov     [rdi+58h], r8d
0x14001af3b  mov     [rdi+68h], ecx
0x14001af3e  mov     [rdi+80h], rax
0x14001af45  lea     rax, [rbp+57h+arg_18]
0x14001af49  mov     [rdi+88h], rax
0x14001af50  lea     rax, [rbp+57h+var_A8]
0x14001af54  mov     [rdi+98h], rax
0x14001af5b  lea     rax, aMouseresolutio; "MouseResolution"
0x14001af62  mov     [rdi+78h], edx
0x14001af65  mov     [rdi+90h], r8d
0x14001af6c  mov     [rdi+0A0h], ecx
0x14001af72  mov     [rdi+0B8h], rax
0x14001af79  lea     rax, [rbp+57h+var_C0]
0x14001af7d  mov     [rdi+0C0h], rax
0x14001af84  lea     rax, [rbp+57h+var_A4]
0x14001af88  mov     [rdi+0D0h], rax
0x14001af8f  lea     rax, aMousesynchin10; "MouseSynchIn100ns"
0x14001af96  mov     [rdi+0B0h], edx
0x14001af9c  mov     [rdi+0C8h], r8d
0x14001afa3  mov     [rdi+0D8h], ecx
0x14001afa9  mov     [rdi+0F0h], rax
0x14001afb0  lea     rax, [rbp+57h+var_A0]
0x14001afb4  mov     [rdi+108h], rax
0x14001afbb  lea     rax, aEnablewheeldet; "EnableWheelDetection"
0x14001afc2  mov     [rdi+0E8h], edx
0x14001afc8  mov     [rdi+0F8h], r15
0x14001afcf  mov     [rdi+100h], r8d
0x14001afd6  mov     [rdi+110h], ecx
0x14001afdc  mov     [rdi+128h], rax
0x14001afe3  lea     rax, [rbp+57h+arg_8]
0x14001afe7  mov     [rdi+130h], rax
0x14001afee  lea     rax, [rbp+57h+var_9C]
0x14001aff2  mov     [rdi+140h], rax
0x14001aff9  lea     rax, aMouseinitializ; "MouseInitializePolled"
0x14001b000  mov     [rdi+120h], edx
0x14001b006  mov     [rdi+138h], r8d
0x14001b00d  mov     [rdi+148h], ecx
0x14001b013  mov     [rdi+158h], edx
0x14001b019  mov     [rdi+160h], rax
0x14001b020  xorps   xmm0, xmm0
0x14001b023  mov     [rdi+180h], ecx
0x14001b029  lea     rax, [rbp+57h+arg_0]
  ... truncated ...
```
