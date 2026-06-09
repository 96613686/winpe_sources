# FveInitDriverExtension

- ea: `0x1400ebb70`
- end: `0x1400ebf4b`
- name: `FveInitDriverExtension`
- size: `987`
- prototype: `__int64 __fastcall(PVOID CallbackContext)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400eb6e0`

## callees

- `0x14000b870`
- `0x14000bfa4`
- `0x14000f014`
- `0x1400218c0`
- `0x140021d00`
- `0x1400626c8`
- `0x1400b5bc0`
- `0x1400ebb70`
- `0x1400ebf70`
- `0x1400ebfe0`
- `0x1400ec0a0`
- `0x1400ed374`
- `0x1400ed8b8`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ebc96`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400ebc96`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400ebe69`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400ebe69`
- `ntoskrnl!KeInitializeMutex` at `0x1400ebe1d`
- `ntoskrnl!KeInitializeMutex` at `0x1400ebe1d`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400ebbf8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400ebbf8`
- `ntoskrnl!KeRegisterBugCheckCallback` at `0x1400ebc49`
- `ntoskrnl!KeRegisterBugCheckCallback` at `0x1400ebc49`
- `ntoskrnl!ExCreateCallback` at `0x1400ebec2`
- `ntoskrnl!ExCreateCallback` at `0x1400ebec2`
- `ntoskrnl!ExRegisterCallback` at `0x1400ebee1`
- `ntoskrnl!ExRegisterCallback` at `0x1400ebee1`
- `ntoskrnl!ExAllocatePool2` at `0x1400ebc76`
- `ntoskrnl!ExAllocatePool2` at `0x1400ebcb1`
- `ntoskrnl!ExAllocatePool2` at `0x1400ebc76`
- `ntoskrnl!ExAllocatePool2` at `0x1400ebcb1`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrGetFirmwareInformation` at `0x1400ebe3d`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrGetFirmwareInformation` at `0x1400ebe3d`

## pseudocode

```c
__int64 __fastcall FveInitDriverExtension(char *CallbackContext, __int64 a2, const UNICODE_STRING *a3)
{
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned __int16 v7; // ax
  __int64 Pool2; // rax
  struct _UNICODE_STRING *v9; // rcx
  void *v10; // rax
  NTSTATUS v11; // ebx
  bool v12; // al
  PVOID v13; // rax
  char v15[8]; // [rsp+30h] [rbp-39h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-31h] BYREF
  __int64 v17; // [rsp+48h] [rbp-21h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-19h] BYREF
  __int128 SystemInformation; // [rsp+80h] [rbp+17h] BYREF
  __int128 v20; // [rsp+90h] [rbp+27h]

  v16[0] = 2883626;
  v17 = 0;
  v16[1] = L"\\Callback\\SoftRestart";
  v15[0] = 0;
  memset(&ObjectAttributes, 0, 44);
  SystemInformation = 0;
  v20 = 0;
  memset(CallbackContext, 0, 0x2958u);
  *(_QWORD *)CallbackContext = a2;
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    ExInitializeResourceLite((PERESOURCE)(CallbackContext + 10352));
    *((_QWORD *)CallbackContext + 1313) = CallbackContext + 10496;
    *((_QWORD *)CallbackContext + 1312) = CallbackContext + 10496;
  }
  IsEnabledDeviceUsageNoInline = Feature_BitLocker_Priority_Floor__private_IsEnabledDeviceUsageNoInline();
  CallbackContext[9760] = 0;
  CallbackContext[120] = IsEnabledDeviceUsageNoInline != 0;
  CallbackContext[9768] = KeRegisterBugCheckCallback(
                            (PKBUGCHECK_CALLBACK_RECORD)(CallbackContext + 9704),
                            FveBugcheckHandler,
                            CallbackContext,
                            0x2958u,
                            (PUCHAR)"fvevol");
  v7 = a3->Length + 2;
  *((_WORD *)CallbackContext + 29) = v7;
  Pool2 = ExAllocatePool2(256, v7, 809850438);
  *((_QWORD *)CallbackContext + 8) = Pool2;
  v9 = (struct _UNICODE_STRING *)(CallbackContext + 56);
  if ( !Pool2 )
  {
    v9->Length = 0;
    *((_WORD *)CallbackContext + 29) = 0;
    return (unsigned int)-1073741670;
  }
  RtlCopyUnicodeString(v9, a3);
  v10 = (void *)ExAllocatePool2(256, 64, 809850438);
  *((_QWORD *)CallbackContext + 1131) = v10;
  if ( !v10 )
    return (unsigned int)-1073741670;
  v11 = 0;
  memset(v10, 0, 0x40u);
  **((_QWORD **)CallbackContext + 1131) = FvePagedAllocCallback;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1131) + 8LL) = FveFreeCallback;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1131) + 16LL) = FveVolumeInitInfo;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1131) + 24LL) = FveVolumeCleanupInfo;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1131) + 32LL) = FveVolumeQueryBitmap;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1131) + 40LL) = FveFileSetSize;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1131) + 48LL) = FveFileMoveClusters;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1131) + 56LL) = FveFileQueryExtentsBuffer;
  FveLoadDriverTestConfig(CallbackContext);
  FveLoadDriverContainmentValues(CallbackContext);
  FveLoadDriverAuxConfig(CallbackContext);
  FveLockInitialize(CallbackContext + 9816);
  FveLockInitialize(CallbackContext + 9928);
  FveLockInitialize(CallbackContext + 10088);
  FveLockInitialize(CallbackContext + 10184);
  FveLockInitialize(CallbackContext + 688);
  *((_WORD *)CallbackContext + 388) = 0;
  *((_QWORD *)CallbackContext + 85) = 0;
  *((_QWORD *)CallbackContext + 84) = 0;
  CallbackContext[880] = 0;
  FveLockInitialize(CallbackContext + 792);
  CallbackContext[881] = 0;
  if ( (int)FveIsWinPEBoot(v15) >= 0 )
    CallbackContext[881] = v15[0];
  *((_QWORD *)CallbackContext + 1208) = 0;
  *((_DWORD *)CallbackContext + 2418) = 0;
  KeInitializeMutex((PRKMUTEX)(CallbackContext + 9608), 0);
  FveCreateOrRefDriverCdo(CallbackContext);
  FveCfgInitialize(CallbackContext);
  v12 = (int)KsrGetFirmwareInformation(&v17) >= 0;
  CallbackContext[9769] = v12;
  if ( !v12 )
  {
LABEL_14:
    if ( (unsigned int)Feature_BitLocker_PhysicalLayout__private_IsEnabledDeviceUsageNoInline() )
    {
      v11 = 0;
      CallbackContext[10512] = 0;
    }
    return (unsigned int)v11;
  }
  v11 = ZwQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  if ( v11 >= 0 )
  {
    if ( (BYTE8(v20) & 4) != 0 )
      CallbackContext[9770] = 1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = ExCreateCallback((PCALLBACK_OBJECT *)CallbackContext + 1222, &ObjectAttributes, 0, 0);
    if ( v11 >= 0 )
    {
      v13 = ExRegisterCallback(
              *((PCALLBACK_OBJECT *)CallbackContext + 1222),
              FveKsrNotifyCallbackRoutine,
              CallbackContext);
      *((_QWORD *)CallbackContext + 1223) = v13;
      if ( !v13 )
        return (unsigned int)-1073741823;
      goto LABEL_14;
    }
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1400ebb70  mov     [rsp-8+arg_8], rbx
0x1400ebb75  mov     [rsp-8+arg_18], rsi
0x1400ebb7a  push    rbp
0x1400ebb7b  push    rdi
0x1400ebb7c  push    r14
0x1400ebb7e  lea     rbp, [rsp-47h]
0x1400ebb83  sub     rsp, 0B0h
0x1400ebb8a  mov     rax, cs:__security_cookie
0x1400ebb91  xor     rax, rsp
0x1400ebb94  mov     [rbp+57h+var_20], rax
0x1400ebb98  xorps   xmm0, xmm0
0x1400ebb9b  mov     [rbp+57h+var_88], 2C002Ah
0x1400ebba3  xor     r14d, r14d
0x1400ebba6  xor     eax, eax
0x1400ebba8  lea     rax, aCallbackSoftre; "\\Callback\\SoftRestart"
0x1400ebbaf  mov     [rbp+57h+var_78], r14
0x1400ebbb3  mov     rsi, r8
0x1400ebbb6  mov     [rbp+57h+var_80], rax
0x1400ebbba  mov     rbx, rdx
0x1400ebbbd  mov     [rbp+57h+var_90], r14b
0x1400ebbc1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400ebbc5  xor     edx, edx; Val
0x1400ebbc7  mov     r8d, 2958h; Size
0x1400ebbcd  mov     rdi, rcx
0x1400ebbd0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400ebbd4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400ebbd8  movups  [rbp+57h+SystemInformation], xmm0
0x1400ebbdc  movups  [rbp+57h+var_30], xmm0
0x1400ebbe0  call    memset
0x1400ebbe5  mov     [rdi], rbx
0x1400ebbe8  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400ebbed  test    eax, eax
0x1400ebbef  jz      short loc_1400EBC12
0x1400ebbf1  lea     rcx, [rdi+2870h]; Resource
0x1400ebbf8  call    cs:__imp_ExInitializeResourceLite
0x1400ebbff  nop     dword ptr [rax+rax+00h]
0x1400ebc04  lea     rax, [rdi+2900h]
0x1400ebc0b  mov     [rax+8], rax
0x1400ebc0f  mov     [rax], rax
0x1400ebc12  call    Feature_BitLocker_Priority_Floor__private_IsEnabledDeviceUsageNoInline
0x1400ebc17  test    eax, eax
0x1400ebc19  mov     [rdi+2620h], r14b
0x1400ebc20  lea     rcx, [rdi+25E8h]; CallbackRecord
0x1400ebc27  mov     r9d, 2958h; Length
0x1400ebc2d  setnz   al
0x1400ebc30  lea     rdx, FveBugcheckHandler; CallbackRoutine
0x1400ebc37  mov     [rdi+78h], al
0x1400ebc3a  mov     r8, rdi; Buffer
0x1400ebc3d  lea     rax, Component; "fvevol"
0x1400ebc44  mov     [rsp+0C0h+Component], rax; Component
0x1400ebc49  call    cs:__imp_KeRegisterBugCheckCallback
0x1400ebc50  nop     dword ptr [rax+rax+00h]
0x1400ebc55  mov     [rdi+2628h], al
0x1400ebc5b  mov     ebx, 30455646h
0x1400ebc60  movzx   eax, word ptr [rsi]
0x1400ebc63  mov     ecx, 100h
0x1400ebc68  add     ax, 2
0x1400ebc6c  mov     r8d, ebx
0x1400ebc6f  movzx   edx, ax
0x1400ebc72  mov     [rdi+3Ah], dx
0x1400ebc76  call    cs:__imp_ExAllocatePool2
0x1400ebc7d  nop     dword ptr [rax+rax+00h]
0x1400ebc82  mov     [rdi+40h], rax
0x1400ebc86  lea     rcx, [rdi+38h]; DestinationString
0x1400ebc8a  test    rax, rax
0x1400ebc8d  jz      loc_1400EBF16
0x1400ebc93  mov     rdx, rsi; SourceString
0x1400ebc96  call    cs:__imp_RtlCopyUnicodeString
0x1400ebc9d  nop     dword ptr [rax+rax+00h]
0x1400ebca2  mov     esi, 40h ; '@'
0x1400ebca7  mov     r8d, ebx
0x1400ebcaa  mov     edx, esi
0x1400ebcac  mov     ecx, 100h
0x1400ebcb1  call    cs:__imp_ExAllocatePool2
0x1400ebcb8  nop     dword ptr [rax+rax+00h]
0x1400ebcbd  mov     [rdi+2358h], rax
0x1400ebcc4  test    rax, rax
0x1400ebcc7  jz      loc_1400EBF1F
0x1400ebccd  mov     r8d, esi; Size
0x1400ebcd0  xor     edx, edx; Val
0x1400ebcd2  mov     rcx, rax; void *
0x1400ebcd5  mov     ebx, r14d
0x1400ebcd8  call    memset
0x1400ebcdd  mov     rax, [rdi+2358h]
0x1400ebce4  lea     rcx, FvePagedAllocCallback
0x1400ebceb  mov     [rax], rcx
0x1400ebcee  lea     rcx, FveFreeCallback
0x1400ebcf5  mov     rax, [rdi+2358h]
0x1400ebcfc  mov     [rax+8], rcx
0x1400ebd00  lea     rcx, FveVolumeInitInfo
0x1400ebd07  mov     rax, [rdi+2358h]
0x1400ebd0e  mov     [rax+10h], rcx
0x1400ebd12  lea     rcx, FveVolumeCleanupInfo
0x1400ebd19  mov     rax, [rdi+2358h]
0x1400ebd20  mov     [rax+18h], rcx
0x1400ebd24  lea     rcx, FveVolumeQueryBitmap
0x1400ebd2b  mov     rax, [rdi+2358h]
0x1400ebd32  mov     [rax+20h], rcx
0x1400ebd36  lea     rcx, FveFileSetSize
0x1400ebd3d  mov     rax, [rdi+2358h]
0x1400ebd44  mov     [rax+28h], rcx
0x1400ebd48  lea     rcx, FveFileMoveClusters
0x1400ebd4f  mov     rax, [rdi+2358h]
0x1400ebd56  mov     [rax+30h], rcx
0x1400ebd5a  lea     rcx, FveFileQueryExtentsBuffer
0x1400ebd61  mov     rax, [rdi+2358h]
0x1400ebd68  mov     [rax+38h], rcx
0x1400ebd6c  mov     rcx, rdi
0x1400ebd6f  call    FveLoadDriverTestConfig
0x1400ebd74  mov     rcx, rdi
0x1400ebd77  call    FveLoadDriverContainmentValues
0x1400ebd7c  mov     rcx, rdi
0x1400ebd7f  call    FveLoadDriverAuxConfig
0x1400ebd84  lea     rcx, [rdi+2658h]
0x1400ebd8b  call    FveLockInitialize
0x1400ebd90  lea     rcx, [rdi+26C8h]
0x1400ebd97  call    FveLockInitialize
0x1400ebd9c  lea     rcx, [rdi+2768h]
0x1400ebda3  call    FveLockInitialize
0x1400ebda8  lea     rcx, [rdi+27C8h]
0x1400ebdaf  call    FveLockInitialize
0x1400ebdb4  lea     rcx, [rdi+2B0h]
0x1400ebdbb  call    FveLockInitialize
0x1400ebdc0  lea     rcx, [rdi+318h]
0x1400ebdc7  mov     [rdi+308h], r14w
0x1400ebdcf  mov     [rdi+2A8h], r14
0x1400ebdd6  mov     [rdi+2A0h], r14
0x1400ebddd  mov     [rdi+370h], r14b
0x1400ebde4  call    FveLockInitialize
0x1400ebde9  lea     rcx, [rbp+57h+var_90]
0x1400ebded  mov     [rdi+371h], r14b
0x1400ebdf4  call    FveIsWinPEBoot
0x1400ebdf9  test    eax, eax
0x1400ebdfb  js      short loc_1400EBE06
0x1400ebdfd  mov     al, [rbp+57h+var_90]
0x1400ebe00  mov     [rdi+371h], al
0x1400ebe06  lea     rcx, [rdi+2588h]; Mutex
0x1400ebe0d  mov     [rdi+25C0h], r14
0x1400ebe14  xor     edx, edx; Level
0x1400ebe16  mov     [rdi+25C8h], r14d
0x1400ebe1d  call    cs:__imp_KeInitializeMutex
0x1400ebe24  nop     dword ptr [rax+rax+00h]
0x1400ebe29  mov     rcx, rdi
0x1400ebe2c  call    FveCreateOrRefDriverCdo
0x1400ebe31  mov     rcx, rdi
0x1400ebe34  call    FveCfgInitialize
0x1400ebe39  lea     rcx, [rbp+57h+var_78]
0x1400ebe3d  call    cs:__imp_KsrGetFirmwareInformation
0x1400ebe44  nop     dword ptr [rax+rax+00h]
0x1400ebe49  shr     eax, 1Fh
0x1400ebe4c  xor     al, 1
0x1400ebe4e  mov     [rdi+2629h], al
0x1400ebe54  jz      loc_1400EBF00
0x1400ebe5a  xor     r9d, r9d; ReturnLength
0x1400ebe5d  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1400ebe61  lea     r8d, [r9+20h]; SystemInformationLength
0x1400ebe65  lea     ecx, [r9+5Ah]; SystemInformationClass
0x1400ebe69  call    cs:__imp_ZwQuerySystemInformation
0x1400ebe70  nop     dword ptr [rax+rax+00h]
0x1400ebe75  mov     ebx, eax
0x1400ebe77  test    eax, eax
0x1400ebe79  js      loc_1400EBF24
0x1400ebe7f  test    byte ptr [rbp+57h+var_30+8], 4
0x1400ebe83  jz      short loc_1400EBE8C
0x1400ebe85  mov     byte ptr [rdi+262Ah], 1
0x1400ebe8c  lea     rax, [rbp+57h+var_88]
0x1400ebe90  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400ebe97  xorps   xmm0, xmm0
0x1400ebe9a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1400ebe9e  lea     rsi, [rdi+2630h]
0x1400ebea5  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400ebeac  mov     rcx, rsi; CallbackObject
0x1400ebeaf  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400ebeb3  xor     r9d, r9d; AllowMultipleCallbacks
0x1400ebeb6  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400ebeba  xor     r8d, r8d; Create
0x1400ebebd  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400ebec2  call    cs:__imp_ExCreateCallback
0x1400ebec9  nop     dword ptr [rax+rax+00h]
0x1400ebece  mov     ebx, eax
0x1400ebed0  test    eax, eax
0x1400ebed2  js      short loc_1400EBF24
0x1400ebed4  mov     rcx, [rsi]; CallbackObject
0x1400ebed7  lea     rdx, FveKsrNotifyCallbackRoutine; CallbackFunction
0x1400ebede  mov     r8, rdi; CallbackContext
0x1400ebee1  call    cs:__imp_ExRegisterCallback
0x1400ebee8  nop     dword ptr [rax+rax+00h]
0x1400ebeed  mov     [rdi+2638h], rax
0x1400ebef4  test    rax, rax
0x1400ebef7  jnz     short loc_1400EBF00
0x1400ebef9  mov     ebx, 0C0000001h
0x1400ebefe  jmp     short loc_1400EBF24
0x1400ebf00  call    Feature_BitLocker_PhysicalLayout__private_IsEnabledDeviceUsageNoInline
0x1400ebf05  test    eax, eax
0x1400ebf07  jz      short loc_1400EBF24
0x1400ebf09  xor     eax, eax
0x1400ebf0b  mov     ebx, r14d
0x1400ebf0e  mov     [rdi+2910h], al
0x1400ebf14  jmp     short loc_1400EBF24
0x1400ebf16  mov     [rcx], r14w
0x1400ebf1a  mov     [rdi+3Ah], r14w
0x1400ebf1f  mov     ebx, 0C000009Ah
0x1400ebf24  mov     eax, ebx
0x1400ebf26  mov     rcx, [rbp+57h+var_20]
0x1400ebf2a  xor     rcx, rsp; StackCookie
0x1400ebf2d  call    __security_check_cookie
0x1400ebf32  lea     r11, [rsp+0C0h+var_10]
0x1400ebf3a  mov     rbx, [r11+28h]
0x1400ebf3e  mov     rsi, [r11+38h]
0x1400ebf42  mov     rsp, r11
0x1400ebf45  pop     r14
0x1400ebf47  pop     rdi
0x1400ebf48  pop     rbp
0x1400ebf49  retn
```
