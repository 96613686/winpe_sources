# DriverUnload

- ea: `0x140032010`
- end: `0x140032142`
- name: `DriverUnload`
- size: `306`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140037080`

## callees

- `0x140003bf4`
- `0x14001beb4`
- `0x14001f0e8`
- `0x14001fc70`
- `0x140032010`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400320eb`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x1400320eb`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400320c8`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x1400320c8`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14003208c`
- `ntoskrnl!IoWMIRegistrationControl` at `0x14003208c`
- `WppRecorder!WppAutoLogStop` at `0x1400320a2`
- `WppRecorder!WppAutoLogStop` at `0x1400320a2`

## pseudocode

```c
__int64 __fastcall DriverUnload(__int64 a1, int a2)
{
  __int64 result; // rax
  PDEVICE_OBJECT v4; // rbx

  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      a2,
      4,
      96,
      (__int64)WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids);
  BthPolicyDestroy();
  result = BthLib_Unload();
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    if ( WPPTraceSuite == 4 )
    {
      while ( v4 )
      {
        if ( v4->Vpb )
        {
          ((void (*)(void))pfnEtwUnregister)();
          v4->Vpb = 0;
        }
        v4 = v4->NextDevice;
      }
    }
    else if ( WPPTraceSuite == 2 )
    {
      IoWMIRegistrationControl(WPP_GLOBAL_Control, 0x80000002);
    }
    result = WppAutoLogStop(WPP_GLOBAL_Control, a1);
    WPP_RECORDER_INITIALIZED = &WPP_RECORDER_INITIALIZED;
    WPP_GLOBAL_Control = (PDEVICE_OBJECT)&WPP_GLOBAL_Control;
  }
  if ( WPP_MAIN_CB.Dpc.DeferredRoutine )
  {
    result = RtlUnregisterFeatureConfigurationChangeNotification();
    WPP_MAIN_CB.Dpc.DeferredRoutine = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    result = RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  LODWORD(WPP_MAIN_CB.Dpc.DeferredContext) = 0;
  return result;
}

```

## disassembly

```asm
0x140032010  push    rbx
0x140032012  push    rbp
0x140032013  push    rdi
0x140032014  push    r14
0x140032016  sub     rsp, 38h
0x14003201a  mov     rdi, rcx
0x14003201d  lea     rbp, WPP_RECORDER_INITIALIZED
0x140032024  cmp     cs:WPP_RECORDER_INITIALIZED, rbp
0x14003202b  jz      short loc_140032053
0x14003202d  mov     rcx, cs:WPP_GLOBAL_Control
0x140032034  lea     rax, WPP_4e0ed08500ad342dfe09456766c7c5f2_Traceguids
0x14003203b  mov     r9d, 60h ; '`'
0x140032041  mov     [rsp+58h+var_38], rax
0x140032046  mov     rcx, [rcx+40h]
0x14003204a  lea     r8d, [r9-5Ch]
0x14003204e  call    WPP_RECORDER_SF_
0x140032053  call    BthPolicyDestroy
0x140032058  call    BthLib_Unload
0x14003205d  mov     rbx, cs:WPP_GLOBAL_Control
0x140032064  lea     r14, WPP_GLOBAL_Control
0x14003206b  cmp     rbx, r14
0x14003206e  jz      short loc_1400320BC
0x140032070  mov     eax, cs:WPPTraceSuite
0x140032076  cmp     eax, 4
0x140032079  jz      loc_140032138
0x14003207f  cmp     eax, 2
0x140032082  jnz     short loc_140032098
0x140032084  mov     edx, 80000002h; Action
0x140032089  mov     rcx, rbx; DeviceObject
0x14003208c  call    cs:__imp_IoWMIRegistrationControl
0x140032093  nop     dword ptr [rax+rax+00h]
0x140032098  mov     rcx, cs:WPP_GLOBAL_Control
0x14003209f  mov     rdx, rdi
0x1400320a2  call    cs:__imp_WppAutoLogStop
0x1400320a9  nop     dword ptr [rax+rax+00h]
0x1400320ae  mov     cs:WPP_RECORDER_INITIALIZED, rbp
0x1400320b5  mov     cs:WPP_GLOBAL_Control, r14
0x1400320bc  mov     rcx, cs:WPP_MAIN_CB.Dpc.DeferredRoutine
0x1400320c3  test    rcx, rcx
0x1400320c6  jz      short loc_1400320DF
0x1400320c8  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x1400320cf  nop     dword ptr [rax+rax+00h]
0x1400320d4  mov     cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 0
0x1400320df  mov     rcx, cs:g_wil_details_featureUsageProvider
0x1400320e6  test    rcx, rcx
0x1400320e9  jz      short loc_140032102
0x1400320eb  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x1400320f2  nop     dword ptr [rax+rax+00h]
0x1400320f7  mov     cs:g_wil_details_featureUsageProvider, 0
0x140032102  mov     dword ptr cs:WPP_MAIN_CB.Dpc.DeferredContext, 0
0x14003210c  add     rsp, 38h
0x140032110  pop     r14
0x140032112  pop     rdi
0x140032113  pop     rbp
0x140032114  pop     rbx
0x140032115  retn
0x140032117  mov     rcx, [rbx+38h]
0x14003211b  test    rcx, rcx
0x14003211e  jz      short loc_140032134
0x140032120  mov     rax, cs:pfnEtwUnregister
0x140032127  call    _guard_dispatch_icall
0x14003212c  mov     qword ptr [rbx+38h], 0
0x140032134  mov     rbx, [rbx+10h]
0x140032138  test    rbx, rbx
0x14003213b  jnz     short loc_140032117
0x14003213d  jmp     loc_140032098
```
