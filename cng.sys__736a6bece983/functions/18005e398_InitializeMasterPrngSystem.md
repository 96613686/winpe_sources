# InitializeMasterPrngSystem

- ea: `0x18005e398`
- end: `0x18005e63e`
- name: `InitializeMasterPrngSystem`
- size: `678`
- prototype: `__int64 __fastcall(PDRIVER_OBJECT DriverObject)`
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18005d7b8`

## callees

- `0x18000743c`
- `0x180021af4`
- `0x18002e860`
- `0x180030df0`
- `0x18004cc10`
- `0x180056d04`
- `0x180056d30`
- `0x180056d70`
- `0x180056db0`
- `0x180057814`
- `0x180057938`
- `0x180057a5c`
- `0x180057e6c`
- `0x180057ef8`
- `0x18005de90`
- `0x18005e19c`
- `0x18005e398`
- `0x18005e720`
- `0x18009f650`

## import_xrefs

- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005e51f`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005e589`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005e51f`
- `ntoskrnl!IoRegisterPlugPlayNotification` at `0x18005e589`

## string_xrefs

- `0x18005e537`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\staterewind.c`
- `0x18005e4e0`: `onecore\ds\security\cryptoapi\ncrypt\crypt\kernel\krng.cxx`

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
  char v11; // al
  char v12; // al
  PVOID NotificationEntry; // [rsp+40h] [rbp-68h] BYREF
  BYTE pbData[64]; // [rsp+50h] [rbp-58h] BYREF

  TrustedEnvironment = g_TrustedEnvironment;
  g_driverObject = DriverObject;
  if ( !g_TrustedEnvironment )
    TrustedEnvironment = GetTrustedEnvironment();
  if ( (TrustedEnvironment & 2) == 0 )
    dword_1800CD784 = (int)McGenEventRegister_EtwRegister(
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
      v11 = g_TrustedEnvironment;
      dword_1800CD788 = 1;
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
  if ( (v12 & 2) == 0 && BootEntropy < 0 && dword_1800CD784 )
  {
    McGenEventUnregister_EtwUnregister();
    dword_1800CD784 = 0;
  }
  return (unsigned int)BootEntropy;
}

```

## disassembly

```asm
0x18005e398  mov     [rsp+arg_10], rbx
0x18005e39d  mov     [rsp+arg_18], rsi
0x18005e3a2  push    rdi
0x18005e3a3  sub     rsp, 0A0h
0x18005e3aa  mov     rax, cs:__security_cookie
0x18005e3b1  xor     rax, rsp
0x18005e3b4  mov     [rsp+0A8h+var_18], rax
0x18005e3bc  mov     eax, cs:g_TrustedEnvironment
0x18005e3c2  mov     rsi, rdx
0x18005e3c5  mov     cs:g_driverObject, rcx
0x18005e3cc  mov     rdi, rcx
0x18005e3cf  test    eax, eax
0x18005e3d1  jnz     short loc_18005E3D8
0x18005e3d3  call    GetTrustedEnvironment
0x18005e3d8  test    al, 2
0x18005e3da  jnz     short loc_18005E3FD
0x18005e3dc  lea     r8, SYSTEM_RNG_ETW_PROVIDER_Context
0x18005e3e3  mov     r9, r8
0x18005e3e6  lea     rcx, SYSTEM_RNG_ETW_PROVIDER
0x18005e3ed  call    McGenEventRegister_EtwRegister
0x18005e3f2  not     eax
0x18005e3f4  shr     eax, 1Fh
0x18005e3f7  mov     cs:dword_1800CD784, eax
0x18005e3fd  call    EntropyPoolInit
0x18005e402  mov     ebx, eax
0x18005e404  test    eax, eax
0x18005e406  js      loc_18005E5E7
0x18005e40c  mov     rcx, rsi
0x18005e40f  call    GetBootEntropy
0x18005e414  mov     ebx, eax
0x18005e416  test    eax, eax
0x18005e418  js      loc_18005E5E7
0x18005e41e  mov     eax, cs:g_SymCryptCpuFeaturesNotPresent
0x18005e424  bt      eax, 9
0x18005e428  jnb     short loc_18005E48B
0x18005e42a  bt      eax, 0Ah
0x18005e42e  jnb     short loc_18005E48B
0x18005e430  xor     ebx, ebx
0x18005e432  mov     eax, cs:g_TrustedEnvironment
0x18005e438  test    eax, eax
0x18005e43a  jnz     short loc_18005E441
0x18005e43c  call    GetTrustedEnvironment
0x18005e441  mov     esi, 1
0x18005e446  test    al, 2
0x18005e448  jnz     loc_18005E5BC
0x18005e44e  lea     rcx, [rsp+0A8h+pbData]
0x18005e453  call    HashFirmwareData
0x18005e458  lea     rdx, [rsp+0A8h+pbData]; pbData
0x18005e45d  lea     rcx, aMicrosoftWindo_2; "Microsoft Windows Firmware data"
0x18005e464  call    AddEntropyWithUniqueSource
0x18005e469  lea     edx, [rsi+3Fh]
0x18005e46c  lea     rcx, [rsp+0A8h+pbData]
0x18005e471  call    SymCryptWipeAsm
0x18005e476  call    InitializeInterruptTimingSource
0x18005e47b  mov     ebx, eax
0x18005e47d  test    eax, eax
0x18005e47f  jns     short loc_18005E4F1
0x18005e481  mov     r9d, 1F0h
0x18005e487  mov     ecx, eax
0x18005e489  jmp     short loc_18005E4D9
0x18005e48b  lea     r8, aMicrosoftWindo_4; "Microsoft Windows Rdrand"
0x18005e492  mov     edx, 3; entropySourceType
0x18005e497  lea     rcx, g_hRdrandSource; phEntropySource
0x18005e49e  call    EntropyRegisterSource
0x18005e4a3  mov     ebx, eax
0x18005e4a5  test    eax, eax
0x18005e4a7  js      short loc_18005E4C9
0x18005e4a9  call    RdrandPushEntropy
0x18005e4ae  mov     rcx, cs:g_hRdrandSource
0x18005e4b5  lea     rdx, RdrandCallback
0x18005e4bc  mov     r8d, 2357BDh
0x18005e4c2  call    EntropyRegisterCallback
0x18005e4c7  mov     ebx, eax
0x18005e4c9  test    ebx, ebx
0x18005e4cb  jns     loc_18005E432
0x18005e4d1  mov     r9d, 1E0h
0x18005e4d7  mov     ecx, ebx
0x18005e4d9  lea     rdx, aStatus_0; "status"
0x18005e4e0  lea     r8, aOnecoreDsSecur_17; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005e4e7  call    DebugTraceError
0x18005e4ec  jmp     loc_18005E5E7
0x18005e4f1  lea     rax, g_pnpNotificationEntry
0x18005e4f8  mov     r9, rdi; DriverObject
0x18005e4fb  mov     [rsp+0A8h+NotificationEntry], rax; NotificationEntry
0x18005e500  lea     r8, GUID_DEVINTERFACE_VM_GENCOUNTER; EventCategoryData
0x18005e507  lea     rax, VmIntegrationDeviceCategoryChange
0x18005e50e  mov     [rsp+0A8h+Context], rdi; Context
0x18005e513  mov     edx, esi; EventCategoryFlags
0x18005e515  mov     [rsp+0A8h+CallbackRoutine], rax; CallbackRoutine
0x18005e51a  mov     ecx, 2; EventCategory
0x18005e51f  call    cs:__imp_IoRegisterPlugPlayNotification
0x18005e526  nop     dword ptr [rax+rax+00h]
0x18005e52b  mov     ebx, eax
0x18005e52d  test    eax, eax
0x18005e52f  jns     short loc_18005E554
0x18005e531  mov     r9d, 69h ; 'i'
0x18005e537  lea     r8, aOnecoreDsSecur_39; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18005e53e  lea     rdx, aStatus_0; "status"
0x18005e545  mov     ecx, eax
0x18005e547  call    DebugTraceError
0x18005e54c  mov     r9d, 1F7h
0x18005e552  jmp     short loc_18005E4D7
0x18005e554  mov     [rsp+0A8h+var_68], 0
0x18005e55d  lea     rax, [rsp+0A8h+var_68]
0x18005e562  mov     r9, rdi; DriverObject
0x18005e565  mov     [rsp+0A8h+NotificationEntry], rax; NotificationEntry
0x18005e56a  lea     r8, GUID_CNG_CHAT_HW_PROV_INTERFACE; EventCategoryData
0x18005e571  lea     rax, HwProvDeviceCategoryChange
0x18005e578  mov     [rsp+0A8h+Context], rdi; Context
0x18005e57d  mov     edx, esi; EventCategoryFlags
0x18005e57f  mov     [rsp+0A8h+CallbackRoutine], rax; CallbackRoutine
0x18005e584  mov     ecx, 2; EventCategory
0x18005e589  call    cs:__imp_IoRegisterPlugPlayNotification
0x18005e590  nop     dword ptr [rax+rax+00h]
0x18005e595  mov     ebx, eax
0x18005e597  test    eax, eax
0x18005e599  jns     short loc_18005E5A6
0x18005e59b  mov     r9d, 1FEh
0x18005e5a1  jmp     loc_18005E487
0x18005e5a6  call    ExchangeVsmStartSource
0x18005e5ab  mov     ebx, eax
0x18005e5ad  test    eax, eax
0x18005e5af  jns     short loc_18005E5C1
0x18005e5b1  mov     r9d, 20Ah
0x18005e5b7  jmp     loc_18005E487
0x18005e5bc  call    GatherVsmKeysEntropy
0x18005e5c1  mov     eax, cs:g_TrustedEnvironment
0x18005e5c7  mov     cs:dword_1800CD788, esi
0x18005e5cd  test    eax, eax
0x18005e5cf  jnz     short loc_18005E5D6
0x18005e5d1  call    GetTrustedEnvironment
0x18005e5d6  test    al, 2
0x18005e5d8  jnz     short loc_18005E5E7
0x18005e5da  mov     cl, sil
0x18005e5dd  call    WriteSeedFile
0x18005e5e2  call    EntropyPoolSetReseedTimer
0x18005e5e7  mov     eax, cs:g_TrustedEnvironment
0x18005e5ed  test    eax, eax
0x18005e5ef  jnz     short loc_18005E5F6
0x18005e5f1  call    GetTrustedEnvironment
0x18005e5f6  test    al, 2
0x18005e5f8  jnz     short loc_18005E616
0x18005e5fa  test    ebx, ebx
0x18005e5fc  jns     short loc_18005E616
0x18005e5fe  cmp     cs:dword_1800CD784, 0
0x18005e605  jz      short loc_18005E616
0x18005e607  call    McGenEventUnregister_EtwUnregister
0x18005e60c  mov     cs:dword_1800CD784, 0
0x18005e616  mov     eax, ebx
0x18005e618  mov     rcx, [rsp+0A8h+var_18]
0x18005e620  xor     rcx, rsp; StackCookie
0x18005e623  call    __security_check_cookie
0x18005e628  lea     r11, [rsp+0A8h+var_8]
0x18005e630  mov     rbx, [r11+20h]
0x18005e634  mov     rsi, [r11+28h]
0x18005e638  mov     rsp, r11
0x18005e63b  pop     rdi
0x18005e63c  retn
```
