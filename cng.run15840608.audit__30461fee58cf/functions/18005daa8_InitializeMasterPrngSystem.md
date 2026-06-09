# InitializeMasterPrngSystem

- ea: `0x18005daa8`
- end: `0x18005dd4e`
- name: `InitializeMasterPrngSystem`
- size: `678`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18005cec8`

## callees

- `0x18000743c`
- `0x180024a34`
- `0x18002dd60`
- `0x1800302f0`
- `0x18004c3d0`
- `0x180056414`
- `0x180056440`
- `0x180056480`
- `0x1800564c0`
- `0x180056f24`
- `0x180057048`
- `0x18005716c`
- `0x18005757c`
- `0x180057608`
- `0x18005d5a0`
- `0x18005d8ac`
- `0x18005daa8`
- `0x18005de30`
- `0x18009d820`

## import_xrefs

- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005dc2f`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005dc99`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005dc2f`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005dc99`

## string_xrefs

- `0x18005dc47`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`
- `0x18005dbf0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\krng.cxx`

## pseudocode

```c
__int64 __fastcall InitializeMasterPrngSystem(struct _DEVICE_OBJECT *DriverObject, _OWORD *a2)
{
  char TrustedEnvironment; // al
  int BootEntropy; // ebx
  char v6; // al
  NTSTATUS started; // eax
  __int64 v8; // r9
  __int64 v9; // rcx
  NTSTATUS v10; // eax
  char v11; // al
  char v12; // al
  PVOID NotificationEntry; // [rsp+40h] [rbp-68h] BYREF
  BYTE pbData[64]; // [rsp+50h] [rbp-58h] BYREF

  TrustedEnvironment = g_TrustedEnvironment;
  g_driverObject = DriverObject;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 2) == 0 )
    dword_1800CB744 = (int)McGenEventRegister_EtwRegister(
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
          BootEntropy = EntropyRegisterCallback((__int64)g_hRdrandSource, (__int64)RdrandCallback, 2316221);
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
      v11 = g_TrustedEnvironment;
      dword_1800CB748 = 1;
      if ( !g_TrustedEnvironment )
        v11 = GetTrustedEnvironment();
      if ( (v11 & 2) == 0 )
      {
        WriteSeedFile(1);
        EntropyPoolSetReseedTimer();
      }
    }
  }
LABEL_33:
  v12 = g_TrustedEnvironment;
  if ( !g_TrustedEnvironment )
    v12 = GetTrustedEnvironment();
  if ( (v12 & 2) == 0 && BootEntropy < 0 && dword_1800CB744 )
  {
    McGenEventUnregister_EtwUnregister();
    dword_1800CB744 = 0;
  }
  return (unsigned int)BootEntropy;
}

```

## disassembly

```asm
0x18005daa8  mov     [rsp+arg_10], rbx
0x18005daad  mov     [rsp+arg_18], rsi
0x18005dab2  push    rdi
0x18005dab3  sub     rsp, 0A0h
0x18005daba  mov     rax, cs:__security_cookie
0x18005dac1  xor     rax, rsp
0x18005dac4  mov     [rsp+0A8h+var_18], rax
0x18005dacc  mov     eax, cs:g_TrustedEnvironment
0x18005dad2  mov     rsi, rdx
0x18005dad5  mov     cs:g_driverObject, rcx
0x18005dadc  mov     rdi, rcx
0x18005dadf  test    eax, eax
0x18005dae1  jnz     short loc_18005DAE8
0x18005dae3  call    GetTrustedEnvironment
0x18005dae8  test    al, 2
0x18005daea  jnz     short loc_18005DB0D
0x18005daec  lea     r8, SYSTEM_RNG_ETW_PROVIDER_Context
0x18005daf3  mov     r9, r8
0x18005daf6  lea     rcx, SYSTEM_RNG_ETW_PROVIDER
0x18005dafd  call    McGenEventRegister_EtwRegister
0x18005db02  not     eax
0x18005db04  shr     eax, 1Fh
0x18005db07  mov     cs:dword_1800CB744, eax
0x18005db0d  call    EntropyPoolInit
0x18005db12  mov     ebx, eax
0x18005db14  test    eax, eax
0x18005db16  js      loc_18005DCF7
0x18005db1c  mov     rcx, rsi
0x18005db1f  call    GetBootEntropy
0x18005db24  mov     ebx, eax
0x18005db26  test    eax, eax
0x18005db28  js      loc_18005DCF7
0x18005db2e  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x18005db34  bt      eax, 9
0x18005db38  jnb     short loc_18005DB9B
0x18005db3a  bt      eax, 0Ah
0x18005db3e  jnb     short loc_18005DB9B
0x18005db40  xor     ebx, ebx
0x18005db42  mov     eax, cs:g_TrustedEnvironment
0x18005db48  test    eax, eax
0x18005db4a  jnz     short loc_18005DB51
0x18005db4c  call    GetTrustedEnvironment
0x18005db51  mov     esi, 1
0x18005db56  test    al, 2
0x18005db58  jnz     loc_18005DCCC
0x18005db5e  lea     rcx, [rsp+0A8h+pbData]
0x18005db63  call    HashFirmwareData
0x18005db68  lea     rdx, [rsp+0A8h+pbData]; pbData
0x18005db6d  lea     rcx, aMicrosoftWindo_2; "Microsoft Windows Firmware data"
0x18005db74  call    AddEntropyWithUniqueSource
0x18005db79  lea     edx, [rsi+3Fh]
0x18005db7c  lea     rcx, [rsp+0A8h+pbData]
0x18005db81  call    SymCryptWipeAsm
0x18005db86  call    InitializeInterruptTimingSource
0x18005db8b  mov     ebx, eax
0x18005db8d  test    eax, eax
0x18005db8f  jns     short loc_18005DC01
0x18005db91  mov     r9d, 1F0h
0x18005db97  mov     ecx, eax
0x18005db99  jmp     short loc_18005DBE9
0x18005db9b  lea     r8, aMicrosoftWindo_4; "Microsoft Windows Rdrand"
0x18005dba2  mov     edx, 3; entropySourceType
0x18005dba7  lea     rcx, g_hRdrandSource; phEntropySource
0x18005dbae  call    EntropyRegisterSource
0x18005dbb3  mov     ebx, eax
0x18005dbb5  test    eax, eax
0x18005dbb7  js      short loc_18005DBD9
0x18005dbb9  call    RdrandPushEntropy
0x18005dbbe  mov     rcx, cs:g_hRdrandSource
0x18005dbc5  lea     rdx, RdrandCallback
0x18005dbcc  mov     r8d, 2357BDh
0x18005dbd2  call    EntropyRegisterCallback
0x18005dbd7  mov     ebx, eax
0x18005dbd9  test    ebx, ebx
0x18005dbdb  jns     loc_18005DB42
0x18005dbe1  mov     r9d, 1E0h
0x18005dbe7  mov     ecx, ebx
0x18005dbe9  lea     rdx, aStatus_0; "status"
0x18005dbf0  lea     r8, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005dbf7  call    DebugTraceError
0x18005dbfc  jmp     loc_18005DCF7
0x18005dc01  lea     rax, g_pnpNotificationEntry
0x18005dc08  mov     r9, rdi; DriverObject
0x18005dc0b  mov     [rsp+0A8h+NotificationEntry], rax; NotificationEntry
0x18005dc10  lea     r8, GUID_DEVINTERFACE_VM_GENCOUNTER; EventCategoryData
0x18005dc17  lea     rax, VmIntegrationDeviceCategoryChange
0x18005dc1e  mov     [rsp+0A8h+Context], rdi; Context
0x18005dc23  mov     edx, esi; EventCategoryFlags
0x18005dc25  mov     [rsp+0A8h+CallbackRoutine], rax; CallbackRoutine
0x18005dc2a  mov     ecx, 2; EventCategory
0x18005dc2f  call    cs:__imp_IoRegisterPlugPlayNotification
0x18005dc36  nop     dword ptr [rax+rax+00h]
0x18005dc3b  mov     ebx, eax
0x18005dc3d  test    eax, eax
0x18005dc3f  jns     short loc_18005DC64
0x18005dc41  mov     r9d, 69h ; 'i'
0x18005dc47  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005dc4e  lea     rdx, aStatus_0; "status"
0x18005dc55  mov     ecx, eax
0x18005dc57  call    DebugTraceError
0x18005dc5c  mov     r9d, 1F7h
0x18005dc62  jmp     short loc_18005DBE7
0x18005dc64  mov     [rsp+0A8h+var_68], 0
0x18005dc6d  lea     rax, [rsp+0A8h+var_68]
0x18005dc72  mov     r9, rdi; DriverObject
0x18005dc75  mov     [rsp+0A8h+NotificationEntry], rax; NotificationEntry
0x18005dc7a  lea     r8, GUID_CNG_CHAT_HW_PROV_INTERFACE; EventCategoryData
0x18005dc81  lea     rax, HwProvDeviceCategoryChange
0x18005dc88  mov     [rsp+0A8h+Context], rdi; Context
0x18005dc8d  mov     edx, esi; EventCategoryFlags
0x18005dc8f  mov     [rsp+0A8h+CallbackRoutine], rax; CallbackRoutine
0x18005dc94  mov     ecx, 2; EventCategory
0x18005dc99  call    cs:__imp_IoRegisterPlugPlayNotification
0x18005dca0  nop     dword ptr [rax+rax+00h]
0x18005dca5  mov     ebx, eax
0x18005dca7  test    eax, eax
0x18005dca9  jns     short loc_18005DCB6
0x18005dcab  mov     r9d, 1FEh
0x18005dcb1  jmp     loc_18005DB97
0x18005dcb6  call    ExchangeVsmStartSource
0x18005dcbb  mov     ebx, eax
0x18005dcbd  test    eax, eax
0x18005dcbf  jns     short loc_18005DCD1
0x18005dcc1  mov     r9d, 20Ah
0x18005dcc7  jmp     loc_18005DB97
0x18005dccc  call    GatherVsmKeysEntropy
0x18005dcd1  mov     eax, cs:g_TrustedEnvironment
0x18005dcd7  mov     cs:dword_1800CB748, esi
0x18005dcdd  test    eax, eax
0x18005dcdf  jnz     short loc_18005DCE6
0x18005dce1  call    GetTrustedEnvironment
0x18005dce6  test    al, 2
0x18005dce8  jnz     short loc_18005DCF7
0x18005dcea  mov     cl, sil
0x18005dced  call    WriteSeedFile
0x18005dcf2  call    EntropyPoolSetReseedTimer
0x18005dcf7  mov     eax, cs:g_TrustedEnvironment
0x18005dcfd  test    eax, eax
0x18005dcff  jnz     short loc_18005DD06
0x18005dd01  call    GetTrustedEnvironment
0x18005dd06  test    al, 2
0x18005dd08  jnz     short loc_18005DD26
0x18005dd0a  test    ebx, ebx
0x18005dd0c  jns     short loc_18005DD26
0x18005dd0e  cmp     cs:dword_1800CB744, 0
0x18005dd15  jz      short loc_18005DD26
0x18005dd17  call    McGenEventUnregister_EtwUnregister
0x18005dd1c  mov     cs:dword_1800CB744, 0
0x18005dd26  mov     eax, ebx
0x18005dd28  mov     rcx, [rsp+0A8h+var_18]
0x18005dd30  xor     rcx, rsp; StackCookie
0x18005dd33  call    __security_check_cookie
0x18005dd38  lea     r11, [rsp+0A8h+var_8]
0x18005dd40  mov     rbx, [r11+20h]
0x18005dd44  mov     rsi, [r11+28h]
0x18005dd48  mov     rsp, r11
0x18005dd4b  pop     rdi
0x18005dd4c  retn
```
