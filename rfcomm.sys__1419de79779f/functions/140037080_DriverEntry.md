# DriverEntry

- ea: `0x140037080`
- end: `0x1400373ae`
- name: `DriverEntry`
- size: `814`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140037010`

## callees

- `0x140003cb4`
- `0x140005050`
- `0x1400051b4`
- `0x14001bfa8`
- `0x14001e8a0`
- `0x14001efd8`
- `0x14001f2f4`
- `0x14001f988`
- `0x14001fd40`
- `0x140032010`
- `0x1400326f8`
- `0x140032da0`
- `0x140032e68`
- `0x140037080`
- `0x1400373b4`

## import_xrefs

- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x140037186`
- `ntoskrnl!IoAllocateDriverObjectExtension` at `0x140037186`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037223`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037265`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037278`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037223`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037265`
- `ntoskrnl!KeInitializeSpinLock` at `0x140037278`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x1400372c3`
- `ntoskrnl!ExSubscribeWnfStateChange` at `0x1400372c3`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  int PolicyRegistryLocation; // eax
  int v5; // edx
  int v6; // ebx
  int v7; // r9d
  _OWORD *v8; // rax
  int RegSettings; // eax
  int v10; // edx
  _QWORD *v11; // rax
  void *DeviceExtension; // rdi
  const char *v13; // rax
  int v14; // edx
  void *v15; // rdi
  const char *v16; // rax
  int v17; // edx
  PVOID DriverObjectExtension; // [rsp+90h] [rbp+18h] BYREF

  DriverObjectExtension = 0;
  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (_DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_RfCommTraceGuid;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.DeviceType = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (struct _IO_TIMER *)1;
  WPP_MAIN_CB.DeviceExtension = 0;
  WppLoadTracingSupport();
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm(DriverObject, RegistryPath);
  PolicyRegistryLocation = wil_InitializeFeatureStaging();
  v6 = PolicyRegistryLocation;
  if ( PolicyRegistryLocation >= 0 )
  {
    RefObj_GlobalsInit();
    DriverObject->DriverExtension->AddDevice = (int (__fastcall *)(_DRIVER_OBJECT *, _DEVICE_OBJECT *))RfcommAddDevice;
    DriverObject->DriverUnload = (void (__fastcall *)(_DRIVER_OBJECT *))DriverUnload;
    memset64(DriverObject->MajorFunction, (unsigned __int64)RfcommDispatch, 0x1Cu);
    v6 = IoAllocateDriverObjectExtension(DriverObject, DriverEntry, 0x38u, &DriverObjectExtension);
    if ( v6 < 0 )
      goto LABEL_17;
    v8 = DriverObjectExtension;
    *(_OWORD *)DriverObjectExtension = 0;
    v8[1] = 0;
    v8[2] = 0;
    *((_QWORD *)v8 + 6) = 0;
    *((_QWORD *)DriverObjectExtension + 5) = DriverObject;
    *((_BYTE *)DriverObjectExtension + 48) = 0;
    *((_BYTE *)DriverObjectExtension + 49) = 0;
    RegSettings = RfcommGetRegSettings((__int64)DriverObjectExtension);
    v6 = RegSettings;
    if ( RegSettings < 0 )
    {
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        WPP_RECORDER_SF_d(
          WPP_GLOBAL_Control->DeviceExtension,
          v10,
          19,
          11,
          (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
          RegSettings);
      v6 = 0;
    }
    KeInitializeSpinLock((PKSPIN_LOCK)DriverObjectExtension);
    v11 = (char *)DriverObjectExtension + 24;
    *((_QWORD *)DriverObjectExtension + 4) = (char *)DriverObjectExtension + 24;
    *v11 = v11;
    memset(&g_Policies, 0, 0x50u);
    g_PolicyStorePath = 0;
    KeInitializeSpinLock(&g_PolicyLock);
    KeInitializeSpinLock(&g_CallbackLock);
    PolicyRegistryLocation = BthGetPolicyRegistryLocation(&g_PolicyStorePath);
    if ( PolicyRegistryLocation < 0
      || (McGenEventRegister_EtwRegister(),
          PolicyRegistryLocation = ExSubscribeWnfStateChange(
                                     &qword_14002D288,
                                     &WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED,
                                     1),
          PolicyRegistryLocation < 0) )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 13;
    }
    else
    {
      PolicyRegistryLocation = BthSyncWithPolicyStore();
      if ( PolicyRegistryLocation >= 0 )
        goto LABEL_17;
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v6;
      v7 = 12;
    }
LABEL_16:
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v5,
      3,
      v7,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
      PolicyRegistryLocation);
LABEL_17:
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      DeviceExtension = WPP_GLOBAL_Control->DeviceExtension;
      v13 = NtStatusTxt(v6);
      WPP_RECORDER_SF_s(
        (_DWORD)DeviceExtension,
        v14,
        3,
        14,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        (__int64)v13);
    }
    goto LABEL_19;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    v7 = 10;
    goto LABEL_16;
  }
LABEL_19:
  if ( v6 < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v15 = WPP_GLOBAL_Control->DeviceExtension;
      v16 = NtStatusTxt(v6);
      WPP_RECORDER_SF_qs(
        (_DWORD)v15,
        v17,
        3,
        15,
        (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids,
        (char)DriverObject,
        (__int64)v16);
    }
    DriverUnload(DriverObject);
  }
  return v6;
}

```

## disassembly

```asm
0x140037080  mov     rax, rsp
0x140037083  push    rbx
0x140037084  push    rsi
0x140037085  push    rdi
0x140037086  push    r12
0x140037088  push    r14
0x14003708a  push    r15
0x14003708c  sub     rsp, 48h
0x140037090  mov     qword ptr [rax+18h], 0
0x140037098  mov     rdi, rdx
0x14003709b  lea     rax, WPP_ThisDir_CTLGUID_RfCommTraceGuid
0x1400370a2  mov     qword ptr cs:WPP_MAIN_CB.Type, 0
0x1400370ad  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x1400370b4  mov     rsi, rcx
0x1400370b7  xor     eax, eax
0x1400370b9  mov     cs:WPP_MAIN_CB.NextDevice, 0
0x1400370c4  mov     cs:WPP_MAIN_CB.DeviceType, eax
0x1400370ca  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400370d5  mov     cs:WPP_MAIN_CB.Timer, 1
0x1400370e0  mov     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1400370eb  call    WppLoadTracingSupport
0x1400370f0  mov     rdx, rdi
0x1400370f3  mov     cs:WPP_MAIN_CB.CurrentIrp, 0
0x1400370fe  mov     rcx, rsi
0x140037101  call    WppInitKm
0x140037106  call    wil_InitializeFeatureStaging
0x14003710b  lea     r14, WPP_RECORDER_INITIALIZED
0x140037112  mov     ebx, eax
0x140037114  lea     r15, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14003711b  mov     r12d, 3
0x140037121  test    eax, eax
0x140037123  jns     short loc_14003713C
0x140037125  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x14003712c  jz      loc_140037356
0x140037132  lea     r9d, [r12+7]
0x140037137  jmp     loc_140037304
0x14003713c  call    RefObj_GlobalsInit
0x140037141  mov     rax, [rsi+30h]
0x140037145  lea     rcx, RfcommAddDevice
0x14003714c  lea     rdi, [rsi+70h]
0x140037150  mov     r8d, 38h ; '8'; DriverObjectExtensionSize
0x140037156  lea     r9, [rsp+78h+DriverObjectExtension]; DriverObjectExtension
0x14003715e  lea     rdx, DriverEntry; ClientIdentificationAddress
0x140037165  mov     [rax+8], rcx
0x140037169  lea     rax, DriverUnload
0x140037170  mov     [rsi+68h], rax
0x140037174  mov     ecx, 1Ch
0x140037179  lea     rax, RfcommDispatch
0x140037180  rep stosq
0x140037183  mov     rcx, rsi; DriverObject
0x140037186  call    cs:__imp_IoAllocateDriverObjectExtension
0x14003718d  nop     dword ptr [rax+rax+00h]
0x140037192  mov     ebx, eax
0x140037194  test    eax, eax
0x140037196  js      loc_140037320
0x14003719c  mov     rax, [rsp+78h+DriverObjectExtension]
0x1400371a4  xor     ecx, ecx
0x1400371a6  xorps   xmm0, xmm0
0x1400371a9  movups  xmmword ptr [rax], xmm0
0x1400371ac  movups  xmmword ptr [rax+10h], xmm0
0x1400371b0  movups  xmmword ptr [rax+20h], xmm0
0x1400371b4  mov     [rax+30h], rcx
0x1400371b8  mov     rax, [rsp+78h+DriverObjectExtension]
0x1400371c0  mov     [rax+28h], rsi
0x1400371c4  mov     rax, [rsp+78h+DriverObjectExtension]
0x1400371cc  mov     [rax+30h], cl
0x1400371cf  mov     rax, [rsp+78h+DriverObjectExtension]
0x1400371d7  mov     [rax+31h], cl
0x1400371da  mov     rcx, [rsp+78h+DriverObjectExtension]
0x1400371e2  call    RfcommGetRegSettings
0x1400371e7  mov     ebx, eax
0x1400371e9  test    eax, eax
0x1400371eb  jns     short loc_14003721B
0x1400371ed  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400371f4  jz      short loc_140037219
0x1400371f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400371fd  mov     r9d, 0Bh
0x140037203  mov     dword ptr [rsp+78h+var_50], eax
0x140037207  mov     [rsp+78h+var_58], r15
0x14003720c  mov     rcx, [rcx+40h]
0x140037210  lea     r8d, [r9+8]
0x140037214  call    WPP_RECORDER_SF_d
0x140037219  xor     ebx, ebx
0x14003721b  mov     rcx, [rsp+78h+DriverObjectExtension]; SpinLock
0x140037223  call    cs:__imp_KeInitializeSpinLock
0x14003722a  nop     dword ptr [rax+rax+00h]
0x14003722f  mov     rax, [rsp+78h+DriverObjectExtension]
0x140037237  lea     rcx, ?g_Policies@@3UPolicies@@A; void *
0x14003723e  add     rax, 18h
0x140037242  xor     edx, edx; Val
0x140037244  lea     r8d, [rdx+50h]; Size
0x140037248  mov     [rax+8], rax
0x14003724c  mov     [rax], rax
0x14003724f  call    memset
0x140037254  xorps   xmm0, xmm0
0x140037257  lea     rcx, ?g_PolicyLock@@3_KA; SpinLock
0x14003725e  movups  xmmword ptr cs:?g_PolicyStorePath@@3U_UNICODE_STRING@@A.Length, xmm0; _UNICODE_STRING g_PolicyStorePath ...
0x140037265  call    cs:__imp_KeInitializeSpinLock
0x14003726c  nop     dword ptr [rax+rax+00h]
0x140037271  lea     rcx, ?g_CallbackLock@@3_KA; SpinLock
0x140037278  call    cs:__imp_KeInitializeSpinLock
0x14003727f  nop     dword ptr [rax+rax+00h]
0x140037284  lea     rcx, ?g_PolicyStorePath@@3U_UNICODE_STRING@@A; DestinationString
0x14003728b  call    BthGetPolicyRegistryLocation
0x140037290  test    eax, eax
0x140037292  js      short loc_1400372F1
0x140037294  call    McGenEventRegister_EtwRegister
0x140037299  xor     r9d, r9d
0x14003729c  mov     [rsp+78h+var_50], 0
0x1400372a5  lea     rax, ?CallbackInternal@@YAJPEAU_EX_WNF_SUBSCRIPTION@@PEBU_WNF_STATE_NAME@@KKPEBU_WNF_TYPE_ID@@PEAX@Z; CallbackInternal(_EX_WNF_SUBSCRIPTION *,_WNF_STATE_NAME const *,ulong,ulong,_WNF_TYPE_ID const *,void *)
0x1400372ac  lea     rdx, WNF_ENTR_BLUETOOTH_POLICY_VALUE_CHANGED
0x1400372b3  mov     [rsp+78h+var_58], rax
0x1400372b8  lea     rcx, qword_14002D288
0x1400372bf  lea     r8d, [r9+1]
0x1400372c3  call    cs:__imp_ExSubscribeWnfStateChange
0x1400372ca  nop     dword ptr [rax+rax+00h]
0x1400372cf  test    eax, eax
0x1400372d1  js      short loc_1400372F1
0x1400372d3  call    BthSyncWithPolicyStore
0x1400372d8  test    eax, eax
0x1400372da  jns     short loc_140037320
0x1400372dc  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400372e3  jz      loc_14003739D
0x1400372e9  mov     r9d, 0Ch
0x1400372ef  jmp     short loc_140037304
0x1400372f1  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x1400372f8  jz      loc_14003739D
0x1400372fe  mov     r9d, 0Dh
0x140037304  mov     rcx, cs:WPP_GLOBAL_Control
0x14003730b  mov     r8d, r12d
0x14003730e  mov     dword ptr [rsp+78h+var_50], eax
0x140037312  mov     [rsp+78h+var_58], r15
0x140037317  mov     rcx, [rcx+40h]
0x14003731b  call    WPP_RECORDER_SF_d
0x140037320  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140037327  jz      short loc_140037356
0x140037329  mov     rax, cs:WPP_GLOBAL_Control
0x140037330  mov     ecx, ebx
0x140037332  mov     rdi, [rax+40h]
0x140037336  call    NtStatusTxt
0x14003733b  mov     [rsp+78h+var_50], rax
0x140037340  mov     r9d, 0Eh
0x140037346  mov     r8d, r12d
0x140037349  mov     [rsp+78h+var_58], r15
0x14003734e  mov     rcx, rdi
0x140037351  call    WPP_RECORDER_SF_s
0x140037356  test    ebx, ebx
0x140037358  jns     short loc_14003739D
0x14003735a  cmp     cs:WPP_RECORDER_INITIALIZED, r14
0x140037361  jz      short loc_140037395
0x140037363  mov     rax, cs:WPP_GLOBAL_Control
0x14003736a  mov     ecx, ebx
0x14003736c  mov     rdi, [rax+40h]
0x140037370  call    NtStatusTxt
0x140037375  mov     [rsp+78h+var_48], rax
0x14003737a  mov     r9d, 0Fh
0x140037380  mov     [rsp+78h+var_50], rsi
0x140037385  mov     r8d, r12d
0x140037388  mov     rcx, rdi
0x14003738b  mov     [rsp+78h+var_58], r15
0x140037390  call    WPP_RECORDER_SF_qs
0x140037395  mov     rcx, rsi
0x140037398  call    DriverUnload
0x14003739d  mov     eax, ebx
0x14003739f  add     rsp, 48h
0x1400373a3  pop     r15
0x1400373a5  pop     r14
0x1400373a7  pop     r12
0x1400373a9  pop     rdi
0x1400373aa  pop     rsi
0x1400373ab  pop     rbx
0x1400373ac  retn
```
