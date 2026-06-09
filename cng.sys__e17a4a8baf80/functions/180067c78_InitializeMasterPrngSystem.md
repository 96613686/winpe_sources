# InitializeMasterPrngSystem

- ea: `0x180067c78`
- end: `0x180067f1e`
- name: `InitializeMasterPrngSystem`
- size: `678`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x180067098`

## callees

- `0x18001155c`
- `0x18002eb64`
- `0x180037e90`
- `0x18003a420`
- `0x1800564d0`
- `0x1800605e4`
- `0x180060610`
- `0x180060650`
- `0x180060690`
- `0x1800610f4`
- `0x180061218`
- `0x18006133c`
- `0x18006174c`
- `0x1800617d8`
- `0x180067770`
- `0x180067a7c`
- `0x180067c78`
- `0x180068000`
- `0x1800a4260`

## import_xrefs

- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x180067dff`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x180067e69`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x180067dff`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x180067e69`

## string_xrefs

- `0x180067e17`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`
- `0x180067dc0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\krng.cxx`

## pseudocode

```c
__int64 __fastcall InitializeMasterPrngSystem(struct _DEVICE_OBJECT *DriverObject, __int64 a2)
{
  char TrustedEnvironment; // al
  NTSTATUS BootEntropy; // ebx
  char v6; // al
  NTSTATUS started; // eax
  __int64 v8; // r9
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  __int64 v11; // rcx
  char v12; // al
  char v13; // al
  PVOID NotificationEntry; // [rsp+40h] [rbp-68h] BYREF
  BYTE pbData[64]; // [rsp+50h] [rbp-58h] BYREF

  TrustedEnvironment = g_TrustedEnvironment;
  g_driverObject = DriverObject;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 2) == 0 )
    dword_1800D3784 = (int)McGenEventRegister_EtwRegister(
                             SYSTEM_RNG_ETW_PROVIDER,
                             a2,
                             &SYSTEM_RNG_ETW_PROVIDER_Context,
                             &SYSTEM_RNG_ETW_PROVIDER_Context) >= 0;
  BootEntropy = EntropyPoolInit();
  if ( BootEntropy >= 0 )
  {
    BootEntropy = GetBootEntropy(a2);
    if ( BootEntropy >= 0 )
    {
      if ( (g_SymCryptCpuFeaturesNotPresent & 0x200) != 0 && (g_SymCryptCpuFeaturesNotPresent & 0x400) != 0 )
      {
        BootEntropy = 0;
      }
      else
      {
        BootEntropy = EntropyRegisterSource(
                        &g_hRdrandSource,
                        ENTROPY_SOURCE_TYPE_HIGH_PULL,
                        L"Microsoft Windows Rdrand");
        if ( BootEntropy >= 0 )
        {
          RdrandPushEntropy();
          BootEntropy = EntropyRegisterCallback(g_hRdrandSource, RdrandCallback, 2316221);
        }
        if ( BootEntropy < 0 )
        {
          v8 = 480;
LABEL_20:
          v9 = (unsigned int)BootEntropy;
          goto LABEL_21;
        }
      }
      v6 = g_TrustedEnvironment;
      if ( !g_TrustedEnvironment )
        v6 = GetTrustedEnvironment();
      if ( (v6 & 2) != 0 )
      {
        GatherVsmKeysEntropy();
      }
      else
      {
        HashFirmwareData(pbData);
        AddEntropyWithUniqueSource(L"Microsoft Windows Firmware data", pbData);
        SymCryptWipeAsm(pbData, 64);
        started = InitializeInterruptTimingSource();
        BootEntropy = started;
        if ( started < 0 )
        {
          v8 = 496;
LABEL_15:
          v9 = (unsigned int)started;
LABEL_21:
          DebugTraceError(v9, "status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\krng.cxx", v8);
          goto LABEL_33;
        }
        v10 = IoRegisterPlugPlayNotification(
                EventCategoryDeviceInterfaceChange,
                1u,
                &GUID_DEVINTERFACE_VM_GENCOUNTER,
                (PDRIVER_OBJECT)DriverObject,
                VmIntegrationDeviceCategoryChange,
                DriverObject,
                &g_pnpNotificationEntry);
        BootEntropy = v10;
        if ( v10 < 0 )
        {
          DebugTraceError(
            (unsigned int)v10,
            "status",
            "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\kernel\\staterewind.c",
            105);
          v8 = 503;
          goto LABEL_20;
        }
        NotificationEntry = 0;
        started = IoRegisterPlugPlayNotification(
                    EventCategoryDeviceInterfaceChange,
                    1u,
                    &GUID_CNG_CHAT_HW_PROV_INTERFACE,
                    (PDRIVER_OBJECT)DriverObject,
                    HwProvDeviceCategoryChange,
                    DriverObject,
                    &NotificationEntry);
        BootEntropy = started;
        if ( started < 0 )
        {
          v8 = 510;
          goto LABEL_15;
        }
        started = ExchangeVsmStartSource();
        BootEntropy = started;
        if ( started < 0 )
        {
          v8 = 522;
          goto LABEL_15;
        }
      }
      v12 = g_TrustedEnvironment;
      dword_1800D3788 = 1;
      if ( !g_TrustedEnvironment )
        v12 = GetTrustedEnvironment();
      if ( (v12 & 2) == 0 )
      {
        LOBYTE(v11) = 1;
        WriteSeedFile(v11);
        EntropyPoolSetReseedTimer();
      }
    }
  }
LABEL_33:
  v13 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v13 = GetTrustedEnvironment();
  if ( (v13 & 2) == 0 && BootEntropy < 0 && dword_1800D3784 )
  {
    McGenEventUnregister_EtwUnregister();
    dword_1800D3784 = 0;
  }
  return (unsigned int)BootEntropy;
}

```

## disassembly

```asm
0x180067c78  mov     [rsp+arg_10], rbx
0x180067c7d  mov     [rsp+arg_18], rsi
0x180067c82  push    rdi
0x180067c83  sub     rsp, 0A0h
0x180067c8a  mov     rax, cs:__security_cookie
0x180067c91  xor     rax, rsp
0x180067c94  mov     [rsp+0A8h+var_18], rax
0x180067c9c  mov     eax, cs:g_TrustedEnvironment
0x180067ca2  mov     rsi, rdx
0x180067ca5  mov     cs:g_driverObject, rcx
0x180067cac  mov     rdi, rcx
0x180067caf  test    eax, eax
0x180067cb1  jnz     short loc_180067CB8
0x180067cb3  call    GetTrustedEnvironment
0x180067cb8  test    al, 2
0x180067cba  jnz     short loc_180067CDD
0x180067cbc  lea     r8, SYSTEM_RNG_ETW_PROVIDER_Context
0x180067cc3  mov     r9, r8
0x180067cc6  lea     rcx, SYSTEM_RNG_ETW_PROVIDER
0x180067ccd  call    McGenEventRegister_EtwRegister
0x180067cd2  not     eax
0x180067cd4  shr     eax, 1Fh
0x180067cd7  mov     cs:dword_1800D3784, eax
0x180067cdd  call    EntropyPoolInit
0x180067ce2  mov     ebx, eax
0x180067ce4  test    eax, eax
0x180067ce6  js      loc_180067EC7
0x180067cec  mov     rcx, rsi
0x180067cef  call    GetBootEntropy
0x180067cf4  mov     ebx, eax
0x180067cf6  test    eax, eax
0x180067cf8  js      loc_180067EC7
0x180067cfe  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x180067d04  bt      eax, 9
0x180067d08  jnb     short loc_180067D6B
0x180067d0a  bt      eax, 0Ah
0x180067d0e  jnb     short loc_180067D6B
0x180067d10  xor     ebx, ebx
0x180067d12  mov     eax, cs:g_TrustedEnvironment
0x180067d18  test    eax, eax
0x180067d1a  jnz     short loc_180067D21
0x180067d1c  call    GetTrustedEnvironment
0x180067d21  mov     esi, 1
0x180067d26  test    al, 2
0x180067d28  jnz     loc_180067E9C
0x180067d2e  lea     rcx, [rsp+0A8h+pbData]
0x180067d33  call    HashFirmwareData
0x180067d38  lea     rdx, [rsp+0A8h+pbData]; pbData
0x180067d3d  lea     rcx, aMicrosoftWindo_2; "Microsoft Windows Firmware data"
0x180067d44  call    AddEntropyWithUniqueSource
0x180067d49  lea     edx, [rsi+3Fh]
0x180067d4c  lea     rcx, [rsp+0A8h+pbData]
0x180067d51  call    SymCryptWipeAsm
0x180067d56  call    InitializeInterruptTimingSource
0x180067d5b  mov     ebx, eax
0x180067d5d  test    eax, eax
0x180067d5f  jns     short loc_180067DD1
0x180067d61  mov     r9d, 1F0h
0x180067d67  mov     ecx, eax
0x180067d69  jmp     short loc_180067DB9
0x180067d6b  lea     r8, aMicrosoftWindo_4; "Microsoft Windows Rdrand"
0x180067d72  mov     edx, 3; entropySourceType
0x180067d77  lea     rcx, g_hRdrandSource; phEntropySource
0x180067d7e  call    EntropyRegisterSource
0x180067d83  mov     ebx, eax
0x180067d85  test    eax, eax
0x180067d87  js      short loc_180067DA9
0x180067d89  call    RdrandPushEntropy
0x180067d8e  mov     rcx, cs:g_hRdrandSource
0x180067d95  lea     rdx, RdrandCallback
0x180067d9c  mov     r8d, 2357BDh
0x180067da2  call    EntropyRegisterCallback
0x180067da7  mov     ebx, eax
0x180067da9  test    ebx, ebx
0x180067dab  jns     loc_180067D12
0x180067db1  mov     r9d, 1E0h
0x180067db7  mov     ecx, ebx
0x180067db9  lea     rdx, aStatus_0; "status"
0x180067dc0  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067dc7  call    DebugTraceError
0x180067dcc  jmp     loc_180067EC7
0x180067dd1  lea     rax, g_pnpNotificationEntry
0x180067dd8  mov     r9, rdi; DriverObject
0x180067ddb  mov     [rsp+0A8h+NotificationEntry], rax; NotificationEntry
0x180067de0  lea     r8, GUID_DEVINTERFACE_VM_GENCOUNTER; EventCategoryData
0x180067de7  lea     rax, VmIntegrationDeviceCategoryChange
0x180067dee  mov     [rsp+0A8h+Context], rdi; Context
0x180067df3  mov     edx, esi; EventCategoryFlags
0x180067df5  mov     [rsp+0A8h+CallbackRoutine], rax; CallbackRoutine
0x180067dfa  mov     ecx, 2; EventCategory
0x180067dff  call    cs:__imp_IoRegisterPlugPlayNotification
0x180067e06  nop     dword ptr [rax+rax+00h]
0x180067e0b  mov     ebx, eax
0x180067e0d  test    eax, eax
0x180067e0f  jns     short loc_180067E34
0x180067e11  mov     r9d, 69h ; 'i'
0x180067e17  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x180067e1e  lea     rdx, aStatus_0; "status"
0x180067e25  mov     ecx, eax
0x180067e27  call    DebugTraceError
0x180067e2c  mov     r9d, 1F7h
0x180067e32  jmp     short loc_180067DB7
0x180067e34  mov     [rsp+0A8h+var_68], 0
0x180067e3d  lea     rax, [rsp+0A8h+var_68]
0x180067e42  mov     r9, rdi; DriverObject
0x180067e45  mov     [rsp+0A8h+NotificationEntry], rax; NotificationEntry
0x180067e4a  lea     r8, GUID_CNG_CHAT_HW_PROV_INTERFACE; EventCategoryData
0x180067e51  lea     rax, HwProvDeviceCategoryChange
0x180067e58  mov     [rsp+0A8h+Context], rdi; Context
0x180067e5d  mov     edx, esi; EventCategoryFlags
0x180067e5f  mov     [rsp+0A8h+CallbackRoutine], rax; CallbackRoutine
0x180067e64  mov     ecx, 2; EventCategory
0x180067e69  call    cs:__imp_IoRegisterPlugPlayNotification
0x180067e70  nop     dword ptr [rax+rax+00h]
0x180067e75  mov     ebx, eax
0x180067e77  test    eax, eax
0x180067e79  jns     short loc_180067E86
0x180067e7b  mov     r9d, 1FEh
0x180067e81  jmp     loc_180067D67
0x180067e86  call    ExchangeVsmStartSource
0x180067e8b  mov     ebx, eax
0x180067e8d  test    eax, eax
0x180067e8f  jns     short loc_180067EA1
0x180067e91  mov     r9d, 20Ah
0x180067e97  jmp     loc_180067D67
0x180067e9c  call    GatherVsmKeysEntropy
0x180067ea1  mov     eax, cs:g_TrustedEnvironment
0x180067ea7  mov     cs:dword_1800D3788, esi
0x180067ead  test    eax, eax
0x180067eaf  jnz     short loc_180067EB6
0x180067eb1  call    GetTrustedEnvironment
0x180067eb6  test    al, 2
0x180067eb8  jnz     short loc_180067EC7
0x180067eba  mov     cl, sil
0x180067ebd  call    WriteSeedFile
0x180067ec2  call    EntropyPoolSetReseedTimer
0x180067ec7  mov     eax, cs:g_TrustedEnvironment
0x180067ecd  test    eax, eax
0x180067ecf  jnz     short loc_180067ED6
0x180067ed1  call    GetTrustedEnvironment
0x180067ed6  test    al, 2
0x180067ed8  jnz     short loc_180067EF6
0x180067eda  test    ebx, ebx
0x180067edc  jns     short loc_180067EF6
0x180067ede  cmp     cs:dword_1800D3784, 0
0x180067ee5  jz      short loc_180067EF6
0x180067ee7  call    McGenEventUnregister_EtwUnregister
0x180067eec  mov     cs:dword_1800D3784, 0
0x180067ef6  mov     eax, ebx
0x180067ef8  mov     rcx, [rsp+0A8h+var_18]
0x180067f00  xor     rcx, rsp; StackCookie
0x180067f03  call    __security_check_cookie
0x180067f08  lea     r11, [rsp+0A8h+var_8]
0x180067f10  mov     rbx, [r11+20h]
0x180067f14  mov     rsi, [r11+28h]
0x180067f18  mov     rsp, r11
0x180067f1b  pop     rdi
0x180067f1c  retn
```
