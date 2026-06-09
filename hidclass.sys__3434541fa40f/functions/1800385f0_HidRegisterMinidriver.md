# HidRegisterMinidriver

- ea: `0x1800385f0`
- end: `0x180038b49`
- name: `HidRegisterMinidriver`
- size: `1369`
- prototype: `NTSTATUS __stdcall(PHID_MINIDRIVER_REGISTRATION MinidriverRegistration)`
- caller_count: `0`
- callee_count: `19`
- tags: `registry_config, loader_planting`

## callees

- `0x18000ddc8`
- `0x18001b744`
- `0x18001d280`
- `0x18001d43c`
- `0x18001d550`
- `0x18001d6c8`
- `0x18001d7b4`
- `0x18001d86c`
- `0x180026e1c`
- `0x180028000`
- `0x180037614`
- `0x18003845c`
- `0x1800385f0`
- `0x180038c2c`
- `0x180038cf4`
- `0x18003d128`
- `0x180041cf0`
- `0x18004227c`
- `0x180045078`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1800387df`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x1800387df`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18003894a`
- `ntoskrnl!RtlCopyUnicodeString` at `0x18003894a`
- `ntoskrnl!ExAllocatePool2` at `0x1800388b4`
- `ntoskrnl!ExAllocatePool2` at `0x1800388b4`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x18003874c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Initialize` at `0x18003874c`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x180038b21`
- `ext-ms-win-sleepstudy-legacy-l1-1-0!SleepstudyHelper_Uninitialize` at `0x180038b21`

## pseudocode

```c
NTSTATUS __stdcall HidRegisterMinidriver(PHID_MINIDRIVER_REGISTRATION MinidriverRegistration)
{
  int v1; // r9d
  char v3; // bl
  PDRIVER_OBJECT *p_DriverObject; // rsi
  __int64 v5; // rdx
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  ULONG Revision; // edx
  int v10; // r14d
  PDEVICE_OBJECT v11; // rcx
  int v12; // eax
  int v13; // edx
  int v14; // r8d
  NTSTATUS v15; // eax
  __int64 v16; // rdx
  __int64 Timer_high; // rcx
  __int64 v18; // r8
  struct _UNICODE_STRING *v19; // r13
  __int64 v20; // rdx
  __int64 Pool2; // rax
  int v22; // edx
  int v23; // r8d
  PDRIVER_OBJECT v24; // rsi
  _OWORD *v25; // rax
  _DRIVER_EXTENSION *DriverExtension; // rdx
  int v27; // edx
  int v28; // r8d
  int v29; // r9d
  int v31; // [rsp+20h] [rbp-48h]
  int v32; // [rsp+28h] [rbp-40h]
  int v33; // [rsp+30h] [rbp-38h]
  int v34; // [rsp+38h] [rbp-30h]
  PVOID DriverObjectExtension; // [rsp+B0h] [rbp+48h] BYREF

  DriverObjectExtension = 0;
  v3 = 1;
  if ( _InterlockedExchange(&g_WppInitialized, 1) )
  {
    p_DriverObject = &MinidriverRegistration->DriverObject;
  }
  else
  {
    wil_InitializeFeatureStaging();
    *(_QWORD *)&WPP_MAIN_CB.Type = 0;
    WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_HidClassTraceGuid;
    WPP_MAIN_CB.NextDevice = 0;
    WPP_MAIN_CB.CurrentIrp = 0;
    WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
    WPP_MAIN_CB.DeviceExtension = 0;
    WPP_MAIN_CB.DeviceType = 0;
    WppLoadTracingSupport();
    WPP_MAIN_CB.CurrentIrp = 0;
    p_DriverObject = &MinidriverRegistration->DriverObject;
    WppInitKm(MinidriverRegistration->DriverObject, MinidriverRegistration->RegistryPath);
    AllocateGlobalRecorderLog();
    McGenEventRegister_EtwRegister();
    if ( (unsigned int)Feature_HCTI01__private_IsEnabledDeviceUsageNoInline(v6, v5, v7, v8) )
      TlgRegisterAggregateProviderEx();
    else
      TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_1800310D8);
    InitializeTelemetryAssertsKMByDriverObject(*p_DriverObject);
  }
  Revision = MinidriverRegistration->Revision;
  if ( MinidriverRegistration->Revision > 1 )
  {
    v10 = -1073741735;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
      || BYTE1(WPP_GLOBAL_Control->Timer) < 2u )
    {
      v3 = 0;
    }
    if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(Revision) = v3;
      WPP_RECORDER_AND_TRACE_SF_DDd(
        WPP_GLOBAL_Control->AttachedDevice,
        Revision,
        WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED,
        v1);
    }
    TraceLoggingRevisionMismatch(v11, MinidriverRegistration->Revision, MinidriverRegistration->RegistryPath);
LABEL_52:
    if ( _InterlockedExchange(&g_SleepstudyInitialized, 0) && g_SleepstudyLibraryHandle )
    {
      SleepstudyHelper_Uninitialize();
      g_SleepstudyLibraryHandle = 0;
    }
    return v10;
  }
  if ( !_InterlockedExchange(&g_SleepstudyInitialized, 1) )
  {
    v12 = SleepstudyHelper_Initialize(&g_SleepstudyLibraryHandle, *p_DriverObject);
    if ( v12 < 0 )
    {
      if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        || (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x400) == 0
        || (LOBYTE(v13) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 3u) )
      {
        LOBYTE(v13) = 0;
      }
      if ( (_BYTE)v13 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        LOBYTE(v14) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
        WPP_RECORDER_AND_TRACE_SF_qL(
          WPP_GLOBAL_Control->AttachedDevice,
          v13,
          v14,
          g_RecorderLog,
          3,
          11,
          11,
          (__int64)WPP_8843678a1e7d3f4e406f5fac720bd3f8_Traceguids,
          (char)MinidriverRegistration->DriverObject,
          v12);
      }
      p_DriverObject = &MinidriverRegistration->DriverObject;
    }
  }
  v15 = IoAllocateDriverObjectExtension(*p_DriverObject, "HIDCLASS", 0x130u, &DriverObjectExtension);
  v10 = v15;
  if ( v15 < 0 )
  {
    if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      || (Timer_high = HIDWORD(WPP_GLOBAL_Control->Timer), (Timer_high & 1) == 0)
      || (LOBYTE(v16) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
    {
      LOBYTE(v16) = 0;
    }
    LOBYTE(v18) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( (_BYTE)v16 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      WPP_RECORDER_AND_TRACE_SF_qL(
        WPP_GLOBAL_Control->AttachedDevice,
        v16,
        v18,
        g_RecorderLog,
        2,
        1,
        12,
        (__int64)WPP_8843678a1e7d3f4e406f5fac720bd3f8_Traceguids,
        (char)MinidriverRegistration->DriverObject,
        v15);
    TraceLoggingIoAllocateDriverObjectExtensionFailed(Timer_high, v16, v18);
    goto LABEL_52;
  }
  memset(DriverObjectExtension, 0, 0x130u);
  *(_QWORD *)DriverObjectExtension = *p_DriverObject;
  *((_DWORD *)DriverObjectExtension + 6) = MinidriverRegistration->DeviceExtensionSize;
  v19 = (struct _UNICODE_STRING *)((char *)DriverObjectExtension + 8);
  v20 = (unsigned __int16)(MinidriverRegistration->RegistryPath->Length + 2);
  *((_WORD *)DriverObjectExtension + 5) = v20;
  Pool2 = ExAllocatePool2(64, v20, 1130654024);
  v19->Buffer = (wchar_t *)Pool2;
  if ( !Pool2 )
  {
    v10 = -1073741670;
    LOBYTE(v22) = WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
               && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
               && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u;
    if ( (_BYTE)v22 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v23) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
      WPP_RECORDER_AND_TRACE_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        v22,
        v23,
        g_RecorderLog,
        3,
        1,
        13,
        (__int64)WPP_8843678a1e7d3f4e406f5fac720bd3f8_Traceguids,
        154);
    }
    goto LABEL_52;
  }
  RtlCopyUnicodeString(v19, MinidriverRegistration->RegistryPath);
  HidpGetFastResumeDisableState(DriverObjectExtension);
  v24 = *p_DriverObject;
  v25 = DriverObjectExtension;
  *((_OWORD *)DriverObjectExtension + 2) = *(_OWORD *)v24->MajorFunction;
  v25[3] = *(_OWORD *)&v24->MajorFunction[2];
  v25[4] = *(_OWORD *)&v24->MajorFunction[4];
  v25[5] = *(_OWORD *)&v24->MajorFunction[6];
  v25[6] = *(_OWORD *)&v24->MajorFunction[8];
  v25[7] = *(_OWORD *)&v24->MajorFunction[10];
  v25[8] = *(_OWORD *)&v24->MajorFunction[12];
  v25[9] = *(_OWORD *)&v24->MajorFunction[14];
  v25[10] = *(_OWORD *)&v24->MajorFunction[16];
  v25[11] = *(_OWORD *)&v24->MajorFunction[18];
  v25[12] = *(_OWORD *)&v24->MajorFunction[20];
  v25[13] = *(_OWORD *)&v24->MajorFunction[22];
  v25[14] = *(_OWORD *)&v24->MajorFunction[24];
  v25[15] = *(_OWORD *)&v24->MajorFunction[26];
  DriverExtension = v24->DriverExtension;
  *((_BYTE *)DriverObjectExtension + 296) = MinidriverRegistration->DevicesArePolled;
  v24->MajorFunction[23] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[4] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[3] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[22] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[27] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[15] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[14] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[0] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  v24->MajorFunction[2] = (int (__fastcall *)(_DEVICE_OBJECT *, _IRP *))HidpMajorHandler;
  *((_QWORD *)DriverObjectExtension + 32) = DriverExtension->AddDevice;
  DriverExtension->AddDevice = (int (__fastcall *)(_DRIVER_OBJECT *, _DEVICE_OBJECT *))HidpAddDevice;
  *((_QWORD *)DriverObjectExtension + 33) = v24->DriverUnload;
  v24->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))HidpDriverUnload;
  *((_DWORD *)DriverObjectExtension + 68) = 0;
  v10 = EnqueueDriverExt(DriverObjectExtension);
  if ( WPP_GLOBAL_Control == (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    || (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) == 0
    || BYTE1(WPP_GLOBAL_Control->Timer) < 4u )
  {
    v3 = 0;
  }
  if ( v3 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v27) = v3;
    LOBYTE(v28) = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    WPP_RECORDER_AND_TRACE_SF_dqZ(
      WPP_GLOBAL_Control->AttachedDevice,
      v27,
      v28,
      v29,
      v31,
      v32,
      v33,
      v34,
      v10,
      (char)v24,
      (__int64)v19);
  }
  if ( v10 < 0 )
    goto LABEL_52;
  return v10;
}

```

## disassembly

```asm
0x1800385f0  push    rbp
0x1800385f2  push    rbx
0x1800385f3  push    rsi
0x1800385f4  push    rdi
0x1800385f5  push    r12
0x1800385f7  push    r13
0x1800385f9  push    r14
0x1800385fb  push    r15
0x1800385fd  mov     rbp, rsp
0x180038600  sub     rsp, 68h
0x180038604  xor     r13d, r13d
0x180038607  mov     rdi, rcx
0x18003860a  mov     [rbp+DriverObjectExtension], r13
0x18003860e  lea     ebx, [r13+1]
0x180038612  mov     eax, ebx
0x180038614  xchg    eax, cs:g_WppInitialized
0x18003861a  test    eax, eax
0x18003861c  jnz     loc_1800386B0
0x180038622  call    wil_InitializeFeatureStaging
0x180038627  lea     rax, WPP_ThisDir_CTLGUID_HidClassTraceGuid
0x18003862e  mov     qword ptr cs:WPP_MAIN_CB.Type, r13
0x180038635  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x18003863c  mov     cs:WPP_MAIN_CB.NextDevice, r13
0x180038643  mov     cs:WPP_MAIN_CB.CurrentIrp, r13
0x18003864a  mov     cs:WPP_MAIN_CB.Timer, rbx
0x180038651  mov     cs:WPP_MAIN_CB.DeviceExtension, r13
0x180038658  mov     cs:WPP_MAIN_CB.DeviceType, r13d
0x18003865f  call    WppLoadTracingSupport
0x180038664  mov     cs:WPP_MAIN_CB.CurrentIrp, r13; __annotation("TMC:", "47c779cd-4efd-49d7-9b10-9f16e5c25d06", "HidClassTraceGuid", "TRACE_FLAG_DDI", "TRACE_FLAG_PNP", "TRACE_FLAG_REGISTRY", "TRACE_FLAG_DISPATCH", "TRACE_FLAG_READ", "TRACE_FLAG_WRITE", "TRACE_FLAG_WAKE", "TRACE_FLAG_HID", "TRACE_FLAG_POWER", "TRACE_FLAG_DEVICERESET", "TRACE_FLAG_SLEEPSTUDY", "TRACE_FLAG_DEVICEPRESENCE", "PUBLIC_TMF:")
0x18003866b  lea     rsi, [rdi+8]
0x18003866f  mov     rcx, [rsi]
0x180038672  mov     rdx, [rdi+10h]
0x180038676  call    WppInitKm
0x18003867b  call    AllocateGlobalRecorderLog
0x180038680  call    McGenEventRegister_EtwRegister
0x180038685  call    Feature_HCTI01__private_IsEnabledDeviceUsageNoInline
0x18003868a  test    eax, eax
0x18003868c  jz      short loc_180038695
0x18003868e  call    TlgRegisterAggregateProviderEx
0x180038693  jmp     short loc_1800386A6
0x180038695  xor     r8d, r8d
0x180038698  lea     rcx, dword_1800310D8; CallbackContext
0x18003869f  xor     edx, edx
0x1800386a1  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x1800386a6  mov     rcx, [rsi]
0x1800386a9  call    InitializeTelemetryAssertsKMByDriverObject
0x1800386ae  jmp     short loc_1800386B4
0x1800386b0  lea     rsi, [rcx+8]
0x1800386b4  mov     edx, [rdi]
0x1800386b6  cmp     edx, ebx
0x1800386b8  jbe     short loc_18003871D
0x1800386ba  mov     r14d, 0C0000059h
0x1800386c0  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800386c7  lea     r12, WPP_GLOBAL_Control
0x1800386ce  cmp     rcx, r12
0x1800386d1  jz      short loc_1800386E0
0x1800386d3  mov     eax, [rcx+2Ch]
0x1800386d6  test    bl, al
0x1800386d8  jz      short loc_1800386E0
0x1800386da  cmp     byte ptr [rcx+29h], 2
0x1800386de  jnb     short loc_1800386E3
0x1800386e0  mov     bl, r13b
0x1800386e3  lea     r15, WPP_RECORDER_INITIALIZED
0x1800386ea  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800386f1  setnz   r8b
0x1800386f5  test    bl, bl
0x1800386f7  jnz     short loc_1800386FE
0x1800386f9  test    r8b, r8b
0x1800386fc  jz      short loc_18003870D
0x1800386fe  mov     rcx, [rcx+18h]
0x180038702  mov     dword ptr [rsp+68h+var_20], edx
0x180038706  mov     dl, bl
0x180038708  call    WPP_RECORDER_AND_TRACE_SF_DDd
0x18003870d  mov     r8, [rdi+10h]
0x180038711  mov     edx, [rdi]
0x180038713  call    TraceLoggingRevisionMismatch
0x180038718  jmp     loc_180038B08
0x18003871d  mov     eax, ebx
0x18003871f  lea     r12, WPP_GLOBAL_Control
0x180038726  xchg    eax, cs:g_SleepstudyInitialized
0x18003872c  lea     r15, WPP_RECORDER_INITIALIZED
0x180038733  lea     r14, WPP_8843678a1e7d3f4e406f5fac720bd3f8_Traceguids
0x18003873a  test    eax, eax
0x18003873c  jnz     loc_1800387CB
0x180038742  mov     rdx, [rsi]
0x180038745  lea     rcx, g_SleepstudyLibraryHandle
0x18003874c  call    cs:__imp_SleepstudyHelper_Initialize
0x180038753  nop     dword ptr [rax+rax+00h]
0x180038758  test    eax, eax
0x18003875a  jns     short loc_1800387CB
0x18003875c  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180038763  cmp     r10, r12
0x180038766  jz      short loc_18003877B
0x180038768  test    dword ptr [r10+2Ch], 400h
0x180038770  jz      short loc_18003877B
0x180038772  cmp     byte ptr [r10+29h], 3
0x180038777  mov     dl, bl
0x180038779  jnb     short loc_18003877E
0x18003877b  mov     dl, r13b
0x18003877e  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180038785  setnz   r8b
0x180038789  test    dl, dl
0x18003878b  jnz     short loc_180038792
0x18003878d  test    r8b, r8b
0x180038790  jz      short loc_1800387C7
0x180038792  mov     r9, cs:g_RecorderLog
0x180038799  mov     ecx, 0Bh
0x18003879e  mov     dword ptr [rsp+68h+var_20], eax
0x1800387a2  mov     rax, [rdi+8]
0x1800387a6  mov     [rsp+68h+var_28], rax
0x1800387ab  mov     [rsp+68h+var_30], r14
0x1800387b0  mov     [rsp+68h+var_38], cx
0x1800387b5  mov     [rsp+68h+var_40], ecx
0x1800387b9  mov     rcx, [r10+18h]
0x1800387bd  mov     [rsp+68h+var_48], 3
0x1800387c2  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1800387c7  lea     rsi, [rdi+8]
0x1800387cb  mov     rcx, [rsi]; DriverObject
0x1800387ce  lea     r9, [rbp+DriverObjectExtension]; DriverObjectExtension
0x1800387d2  mov     r8d, 130h; DriverObjectExtensionSize
0x1800387d8  lea     rdx, aHidclass; "HIDCLASS"
0x1800387df  call    cs:__imp_IoAllocateDriverObjectExtension
0x1800387e6  nop     dword ptr [rax+rax+00h]
0x1800387eb  mov     r14d, eax
0x1800387ee  test    eax, eax
0x1800387f0  jns     short loc_180038869
0x1800387f2  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800387f9  cmp     r10, r12
0x1800387fc  jz      short loc_18003880F
0x1800387fe  mov     ecx, [r10+2Ch]
0x180038802  test    bl, cl
0x180038804  jz      short loc_18003880F
0x180038806  cmp     byte ptr [r10+29h], 2
0x18003880b  mov     dl, bl
0x18003880d  jnb     short loc_180038812
0x18003880f  mov     dl, r13b
0x180038812  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180038819  setnz   r8b
0x18003881d  test    dl, dl
0x18003881f  jnz     short loc_180038826
0x180038821  test    r8b, r8b
0x180038824  jz      short loc_18003885F
0x180038826  mov     rcx, [r10+18h]
0x18003882a  lea     r9, WPP_8843678a1e7d3f4e406f5fac720bd3f8_Traceguids
0x180038831  mov     dword ptr [rsp+68h+var_20], eax
0x180038835  mov     rax, [rdi+8]
0x180038839  mov     [rsp+68h+var_28], rax
0x18003883e  mov     [rsp+68h+var_30], r9
0x180038843  mov     r9, cs:g_RecorderLog
0x18003884a  mov     [rsp+68h+var_38], 0Ch
0x180038851  mov     [rsp+68h+var_40], ebx
0x180038855  mov     [rsp+68h+var_48], 2
0x18003885a  call    WPP_RECORDER_AND_TRACE_SF_qL
0x18003885f  call    TraceLoggingIoAllocateDriverObjectExtensionFailed
0x180038864  jmp     loc_180038B08
0x180038869  mov     rcx, [rbp+DriverObjectExtension]; void *
0x18003886d  xor     edx, edx; Val
0x18003886f  mov     r8d, 130h; Size
0x180038875  call    memset
0x18003887a  mov     rcx, [rsi]
0x18003887d  mov     r8d, 43646948h
0x180038883  mov     rax, [rbp+DriverObjectExtension]
0x180038887  mov     [rax], rcx
0x18003888a  mov     ecx, [rdi+18h]
0x18003888d  mov     rax, [rbp+DriverObjectExtension]
0x180038891  mov     [rax+18h], ecx
0x180038894  mov     rax, [rdi+10h]
0x180038898  mov     r13, [rbp+DriverObjectExtension]
0x18003889c  add     r13, 8
0x1800388a0  movzx   ecx, word ptr [rax]
0x1800388a3  add     cx, 2
0x1800388a7  movzx   edx, cx
0x1800388aa  mov     ecx, 40h ; '@'
0x1800388af  mov     [r13+2], dx
0x1800388b4  call    cs:__imp_ExAllocatePool2
0x1800388bb  nop     dword ptr [rax+rax+00h]
0x1800388c0  mov     [r13+8], rax
0x1800388c4  test    rax, rax
0x1800388c7  jnz     short loc_180038943
0x1800388c9  mov     r14d, 0C000009Ah
0x1800388cf  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800388d6  cmp     rcx, r12
0x1800388d9  jz      short loc_1800388EF
0x1800388db  mov     eax, [rcx+2Ch]
0x1800388de  test    bl, al
0x1800388e0  jz      short loc_1800388EF
0x1800388e2  cmp     byte ptr [rcx+29h], 3
0x1800388e6  jb      short loc_1800388EF
0x1800388e8  mov     dl, bl
0x1800388ea  xor     r13d, r13d
0x1800388ed  jmp     short loc_1800388F5
0x1800388ef  xor     r13d, r13d
0x1800388f2  mov     dl, r13b
0x1800388f5  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x1800388fc  setnz   r8b
0x180038900  test    dl, dl
0x180038902  jnz     short loc_18003890D
0x180038904  test    r8b, r8b
0x180038907  jz      loc_180038B08
0x18003890d  mov     rcx, [rcx+18h]
0x180038911  lea     r9, WPP_8843678a1e7d3f4e406f5fac720bd3f8_Traceguids
0x180038918  mov     dword ptr [rsp+68h+var_28], r14d
0x18003891d  mov     [rsp+68h+var_30], r9
0x180038922  mov     r9, cs:g_RecorderLog
0x180038929  mov     [rsp+68h+var_38], 0Dh
0x180038930  mov     [rsp+68h+var_40], ebx
0x180038934  mov     [rsp+68h+var_48], 3
0x180038939  call    WPP_RECORDER_AND_TRACE_SF_d
0x18003893e  jmp     loc_180038B08
0x180038943  mov     rdx, [rdi+10h]; SourceString
0x180038947  mov     rcx, r13; DestinationString
0x18003894a  call    cs:__imp_RtlCopyUnicodeString
0x180038951  nop     dword ptr [rax+rax+00h]
0x180038956  mov     rcx, [rbp+DriverObjectExtension]
0x18003895a  call    HidpGetFastResumeDisableState
0x18003895f  mov     rsi, [rsi]
0x180038962  mov     rax, [rbp+DriverObjectExtension]
0x180038966  movups  xmm0, xmmword ptr [rsi+70h]
0x18003896a  movups  xmmword ptr [rax+20h], xmm0
0x18003896e  movups  xmm1, xmmword ptr [rsi+80h]
0x180038975  movups  xmmword ptr [rax+30h], xmm1
0x180038979  movups  xmm0, xmmword ptr [rsi+90h]
0x180038980  movups  xmmword ptr [rax+40h], xmm0
0x180038984  movups  xmm1, xmmword ptr [rsi+0A0h]
0x18003898b  movups  xmmword ptr [rax+50h], xmm1
0x18003898f  movups  xmm0, xmmword ptr [rsi+0B0h]
0x180038996  movups  xmmword ptr [rax+60h], xmm0
0x18003899a  movups  xmm1, xmmword ptr [rsi+0C0h]
0x1800389a1  movups  xmmword ptr [rax+70h], xmm1
0x1800389a5  movups  xmm0, xmmword ptr [rsi+0D0h]
0x1800389ac  movups  xmmword ptr [rax+80h], xmm0
0x1800389b3  movups  xmm1, xmmword ptr [rsi+0E0h]
0x1800389ba  movups  xmmword ptr [rax+90h], xmm1
0x1800389c1  movups  xmm0, xmmword ptr [rsi+0F0h]
0x1800389c8  movups  xmmword ptr [rax+0A0h], xmm0
0x1800389cf  movups  xmm1, xmmword ptr [rsi+100h]
0x1800389d6  movups  xmmword ptr [rax+0B0h], xmm1
0x1800389dd  movups  xmm0, xmmword ptr [rsi+110h]
0x1800389e4  movups  xmmword ptr [rax+0C0h], xmm0
0x1800389eb  movups  xmm1, xmmword ptr [rsi+120h]
0x1800389f2  movups  xmmword ptr [rax+0D0h], xmm1
0x1800389f9  movups  xmm0, xmmword ptr [rsi+130h]
0x180038a00  movups  xmmword ptr [rax+0E0h], xmm0
0x180038a07  movups  xmm1, xmmword ptr [rsi+140h]
0x180038a0e  movups  xmmword ptr [rax+0F0h], xmm1
0x180038a15  mov     rax, [rbp+DriverObjectExtension]
0x180038a19  mov     cl, [rdi+1Ch]
0x180038a1c  mov     rdx, [rsi+30h]
0x180038a20  mov     [rax+128h], cl
0x180038a26  lea     rax, HidpMajorHandler
0x180038a2d  mov     [rsi+128h], rax
0x180038a34  mov     [rsi+90h], rax
0x180038a3b  mov     [rsi+88h], rax
0x180038a42  mov     [rsi+120h], rax
0x180038a49  mov     [rsi+148h], rax
0x180038a50  mov     [rsi+0E8h], rax
0x180038a57  mov     [rsi+0E0h], rax
0x180038a5e  mov     [rsi+70h], rax
0x180038a62  mov     [rsi+80h], rax
0x180038a69  mov     rax, [rbp+DriverObjectExtension]
0x180038a6d  mov     rcx, [rdx+8]
0x180038a71  mov     [rax+100h], rcx
0x180038a78  lea     rax, HidpAddDevice
0x180038a7f  mov     [rdx+8], rax
0x180038a83  mov     rax, [rbp+DriverObjectExtension]
0x180038a87  mov     rcx, [rsi+68h]
0x180038a8b  mov     [rax+108h], rcx
0x180038a92  lea     rax, HidpDriverUnload
0x180038a99  mov     [rsi+68h], rax
0x180038a9d  mov     rax, [rbp+DriverObjectExtension]
0x180038aa1  mov     dword ptr [rax+110h], 0
0x180038aab  mov     rcx, [rbp+DriverObjectExtension]
0x180038aaf  call    EnqueueDriverExt
0x180038ab4  mov     r14d, eax
0x180038ab7  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180038abe  cmp     rcx, r12
0x180038ac1  jz      short loc_180038AD0
0x180038ac3  mov     eax, [rcx+2Ch]
0x180038ac6  test    bl, al
0x180038ac8  jz      short loc_180038AD0
0x180038aca  cmp     byte ptr [rcx+29h], 4
0x180038ace  jnb     short loc_180038AD2
0x180038ad0  xor     bl, bl
0x180038ad2  cmp     cs:WPP_RECORDER_INITIALIZED, r15
0x180038ad9  setnz   r8b
0x180038add  test    bl, bl
0x180038adf  jnz     short loc_180038AE6
0x180038ae1  test    r8b, r8b
0x180038ae4  jz      short loc_180038B00
0x180038ae6  mov     rcx, [rcx+18h]
0x180038aea  mov     dl, bl
0x180038aec  mov     [rsp+68h+var_18], r13
0x180038af1  mov     [rsp+68h+var_20], rsi
0x180038af6  mov     dword ptr [rsp+68h+var_28], r14d
0x180038afb  call    WPP_RECORDER_AND_TRACE_SF_dqZ
0x180038b00  xor     r13d, r13d
0x180038b03  test    r14d, r14d
0x180038b06  jns     short loc_180038B34
0x180038b08  mov     eax, r13d
0x180038b0b  xchg    eax, cs:g_SleepstudyInitialized
  ... truncated ...
```
