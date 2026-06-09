# FveInitDriverExtension

- ea: `0x1400f0b60`
- end: `0x1400f0f3b`
- name: `FveInitDriverExtension`
- size: `987`
- prototype: `__int64 __fastcall(PVOID CallbackContext)`
- caller_count: `1`
- callee_count: `13`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1400f06e0`

## callees

- `0x14000b998`
- `0x14000c130`
- `0x14000f1fc`
- `0x140022bf0`
- `0x140023040`
- `0x140064748`
- `0x1400b6ebc`
- `0x1400f0b60`
- `0x1400f0f60`
- `0x1400f0fd0`
- `0x1400f1090`
- `0x1400f23e0`
- `0x1400f2924`

## import_xrefs

- `ntoskrnl!RtlCopyUnicodeString` at `0x1400f0c86`
- `ntoskrnl!RtlCopyUnicodeString` at `0x1400f0c86`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400f0e59`
- `ntoskrnl!ZwQuerySystemInformation` at `0x1400f0e59`
- `ntoskrnl!KeInitializeMutex` at `0x1400f0e0d`
- `ntoskrnl!KeInitializeMutex` at `0x1400f0e0d`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400f0be8`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400f0be8`
- `ntoskrnl!KeRegisterBugCheckCallback` at `0x1400f0c39`
- `ntoskrnl!KeRegisterBugCheckCallback` at `0x1400f0c39`
- `ntoskrnl!ExCreateCallback` at `0x1400f0eb2`
- `ntoskrnl!ExCreateCallback` at `0x1400f0eb2`
- `ntoskrnl!ExRegisterCallback` at `0x1400f0ed1`
- `ntoskrnl!ExRegisterCallback` at `0x1400f0ed1`
- `ntoskrnl!ExAllocatePool2` at `0x1400f0c66`
- `ntoskrnl!ExAllocatePool2` at `0x1400f0ca1`
- `ntoskrnl!ExAllocatePool2` at `0x1400f0c66`
- `ntoskrnl!ExAllocatePool2` at `0x1400f0ca1`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrGetFirmwareInformation` at `0x1400f0e2d`
- `ext-ms-win-ntos-ksr-l1-1-1!KsrGetFirmwareInformation` at `0x1400f0e2d`

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
  memset(CallbackContext, 0, 0x2A60u);
  *(_QWORD *)CallbackContext = a2;
  if ( (unsigned int)Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline() )
  {
    ExInitializeResourceLite((PERESOURCE)(CallbackContext + 10600));
    *((_QWORD *)CallbackContext + 1346) = CallbackContext + 10760;
    *((_QWORD *)CallbackContext + 1345) = CallbackContext + 10760;
  }
  IsEnabledDeviceUsageNoInline = Feature_BitLocker_Priority_Floor__private_IsEnabledDeviceUsageNoInline();
  CallbackContext[10008] = 0;
  CallbackContext[120] = IsEnabledDeviceUsageNoInline != 0;
  CallbackContext[10016] = KeRegisterBugCheckCallback(
                             (PKBUGCHECK_CALLBACK_RECORD)(CallbackContext + 9952),
                             FveBugcheckHandler,
                             CallbackContext,
                             0x2A60u,
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
  *((_QWORD *)CallbackContext + 1162) = v10;
  if ( !v10 )
    return (unsigned int)-1073741670;
  v11 = 0;
  memset(v10, 0, 0x40u);
  **((_QWORD **)CallbackContext + 1162) = FvePagedAllocCallback;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1162) + 8LL) = FveFreeCallback;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1162) + 16LL) = FveVolumeInitInfo;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1162) + 24LL) = FveVolumeCleanupInfo;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1162) + 32LL) = FveVolumeQueryBitmap;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1162) + 40LL) = FveFileSetSize;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1162) + 48LL) = FveFileMoveClusters;
  *(_QWORD *)(*((_QWORD *)CallbackContext + 1162) + 56LL) = FveFileQueryExtentsBuffer;
  FveLoadDriverTestConfig(CallbackContext);
  FveLoadDriverContainmentValues(CallbackContext);
  FveLoadDriverAuxConfig(CallbackContext);
  FveLockInitialize(CallbackContext + 10064);
  FveLockInitialize(CallbackContext + 10176);
  FveLockInitialize(CallbackContext + 10336);
  FveLockInitialize(CallbackContext + 10432);
  FveLockInitialize(CallbackContext + 688);
  *((_WORD *)CallbackContext + 388) = 0;
  *((_QWORD *)CallbackContext + 85) = 0;
  *((_QWORD *)CallbackContext + 84) = 0;
  CallbackContext[880] = 0;
  FveLockInitialize(CallbackContext + 792);
  CallbackContext[881] = 0;
  if ( (int)FveIsWinPEBoot(v15) >= 0 )
    CallbackContext[881] = v15[0];
  *((_QWORD *)CallbackContext + 1239) = 0;
  *((_DWORD *)CallbackContext + 2480) = 0;
  KeInitializeMutex((PRKMUTEX)CallbackContext + 176, 0);
  FveCreateOrRefDriverCdo(CallbackContext);
  FveCfgInitialize(CallbackContext);
  v12 = (int)KsrGetFirmwareInformation(&v17) >= 0;
  CallbackContext[10017] = v12;
  if ( !v12 )
  {
LABEL_14:
    if ( (unsigned int)Feature_BitLocker_PhysicalLayout__private_IsEnabledDeviceUsageNoInline() )
    {
      v11 = 0;
      CallbackContext[10776] = 0;
    }
    return (unsigned int)v11;
  }
  v11 = ZwQuerySystemInformation(SystemBootEnvironmentInformation, &SystemInformation, 0x20u, 0);
  if ( v11 >= 0 )
  {
    if ( (BYTE8(v20) & 4) != 0 )
      CallbackContext[10018] = 1;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 576;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)v16;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v11 = ExCreateCallback((PCALLBACK_OBJECT *)CallbackContext + 1253, &ObjectAttributes, 0, 0);
    if ( v11 >= 0 )
    {
      v13 = ExRegisterCallback(
              *((PCALLBACK_OBJECT *)CallbackContext + 1253),
              FveKsrNotifyCallbackRoutine,
              CallbackContext);
      *((_QWORD *)CallbackContext + 1254) = v13;
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
0x1400f0b60  mov     [rsp-8+arg_8], rbx
0x1400f0b65  mov     [rsp-8+arg_18], rsi
0x1400f0b6a  push    rbp
0x1400f0b6b  push    rdi
0x1400f0b6c  push    r14
0x1400f0b6e  lea     rbp, [rsp-47h]
0x1400f0b73  sub     rsp, 0B0h
0x1400f0b7a  mov     rax, cs:__security_cookie
0x1400f0b81  xor     rax, rsp
0x1400f0b84  mov     [rbp+57h+var_20], rax
0x1400f0b88  xorps   xmm0, xmm0
0x1400f0b8b  mov     [rbp+57h+var_88], 2C002Ah
0x1400f0b93  xor     r14d, r14d
0x1400f0b96  xor     eax, eax
0x1400f0b98  lea     rax, aCallbackSoftre; "\\Callback\\SoftRestart"
0x1400f0b9f  mov     [rbp+57h+var_78], r14
0x1400f0ba3  mov     rsi, r8
0x1400f0ba6  mov     [rbp+57h+var_80], rax
0x1400f0baa  mov     rbx, rdx
0x1400f0bad  mov     [rbp+57h+var_90], r14b
0x1400f0bb1  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1400f0bb5  xor     edx, edx; Val
0x1400f0bb7  mov     r8d, 2A60h; Size
0x1400f0bbd  mov     rdi, rcx
0x1400f0bc0  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1400f0bc4  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x1400f0bc8  movups  [rbp+57h+SystemInformation], xmm0
0x1400f0bcc  movups  [rbp+57h+var_30], xmm0
0x1400f0bd0  call    memset
0x1400f0bd5  mov     [rdi], rbx
0x1400f0bd8  call    Feature_BitLockerHwAccelCryptoSupport__private_IsEnabledDeviceUsageNoInline
0x1400f0bdd  test    eax, eax
0x1400f0bdf  jz      short loc_1400F0C02
0x1400f0be1  lea     rcx, [rdi+2968h]; Resource
0x1400f0be8  call    cs:__imp_ExInitializeResourceLite
0x1400f0bef  nop     dword ptr [rax+rax+00h]
0x1400f0bf4  lea     rax, [rdi+2A08h]
0x1400f0bfb  mov     [rax+8], rax
0x1400f0bff  mov     [rax], rax
0x1400f0c02  call    Feature_BitLocker_Priority_Floor__private_IsEnabledDeviceUsageNoInline
0x1400f0c07  test    eax, eax
0x1400f0c09  mov     [rdi+2718h], r14b
0x1400f0c10  lea     rcx, [rdi+26E0h]; CallbackRecord
0x1400f0c17  mov     r9d, 2A60h; Length
0x1400f0c1d  setnz   al
0x1400f0c20  lea     rdx, FveBugcheckHandler; CallbackRoutine
0x1400f0c27  mov     [rdi+78h], al
0x1400f0c2a  mov     r8, rdi; Buffer
0x1400f0c2d  lea     rax, Component; "fvevol"
0x1400f0c34  mov     [rsp+0C0h+Component], rax; Component
0x1400f0c39  call    cs:__imp_KeRegisterBugCheckCallback
0x1400f0c40  nop     dword ptr [rax+rax+00h]
0x1400f0c45  mov     [rdi+2720h], al
0x1400f0c4b  mov     ebx, 30455646h
0x1400f0c50  movzx   eax, word ptr [rsi]
0x1400f0c53  mov     ecx, 100h
0x1400f0c58  add     ax, 2
0x1400f0c5c  mov     r8d, ebx
0x1400f0c5f  movzx   edx, ax
0x1400f0c62  mov     [rdi+3Ah], dx
0x1400f0c66  call    cs:__imp_ExAllocatePool2
0x1400f0c6d  nop     dword ptr [rax+rax+00h]
0x1400f0c72  mov     [rdi+40h], rax
0x1400f0c76  lea     rcx, [rdi+38h]; DestinationString
0x1400f0c7a  test    rax, rax
0x1400f0c7d  jz      loc_1400F0F06
0x1400f0c83  mov     rdx, rsi; SourceString
0x1400f0c86  call    cs:__imp_RtlCopyUnicodeString
0x1400f0c8d  nop     dword ptr [rax+rax+00h]
0x1400f0c92  mov     esi, 40h ; '@'
0x1400f0c97  mov     r8d, ebx
0x1400f0c9a  mov     edx, esi
0x1400f0c9c  mov     ecx, 100h
0x1400f0ca1  call    cs:__imp_ExAllocatePool2
0x1400f0ca8  nop     dword ptr [rax+rax+00h]
0x1400f0cad  mov     [rdi+2450h], rax
0x1400f0cb4  test    rax, rax
0x1400f0cb7  jz      loc_1400F0F0F
0x1400f0cbd  mov     r8d, esi; Size
0x1400f0cc0  xor     edx, edx; Val
0x1400f0cc2  mov     rcx, rax; void *
0x1400f0cc5  mov     ebx, r14d
0x1400f0cc8  call    memset
0x1400f0ccd  mov     rax, [rdi+2450h]
0x1400f0cd4  lea     rcx, FvePagedAllocCallback
0x1400f0cdb  mov     [rax], rcx
0x1400f0cde  lea     rcx, FveFreeCallback
0x1400f0ce5  mov     rax, [rdi+2450h]
0x1400f0cec  mov     [rax+8], rcx
0x1400f0cf0  lea     rcx, FveVolumeInitInfo
0x1400f0cf7  mov     rax, [rdi+2450h]
0x1400f0cfe  mov     [rax+10h], rcx
0x1400f0d02  lea     rcx, FveVolumeCleanupInfo
0x1400f0d09  mov     rax, [rdi+2450h]
0x1400f0d10  mov     [rax+18h], rcx
0x1400f0d14  lea     rcx, FveVolumeQueryBitmap
0x1400f0d1b  mov     rax, [rdi+2450h]
0x1400f0d22  mov     [rax+20h], rcx
0x1400f0d26  lea     rcx, FveFileSetSize
0x1400f0d2d  mov     rax, [rdi+2450h]
0x1400f0d34  mov     [rax+28h], rcx
0x1400f0d38  lea     rcx, FveFileMoveClusters
0x1400f0d3f  mov     rax, [rdi+2450h]
0x1400f0d46  mov     [rax+30h], rcx
0x1400f0d4a  lea     rcx, FveFileQueryExtentsBuffer
0x1400f0d51  mov     rax, [rdi+2450h]
0x1400f0d58  mov     [rax+38h], rcx
0x1400f0d5c  mov     rcx, rdi
0x1400f0d5f  call    FveLoadDriverTestConfig
0x1400f0d64  mov     rcx, rdi
0x1400f0d67  call    FveLoadDriverContainmentValues
0x1400f0d6c  mov     rcx, rdi
0x1400f0d6f  call    FveLoadDriverAuxConfig
0x1400f0d74  lea     rcx, [rdi+2750h]
0x1400f0d7b  call    FveLockInitialize
0x1400f0d80  lea     rcx, [rdi+27C0h]
0x1400f0d87  call    FveLockInitialize
0x1400f0d8c  lea     rcx, [rdi+2860h]
0x1400f0d93  call    FveLockInitialize
0x1400f0d98  lea     rcx, [rdi+28C0h]
0x1400f0d9f  call    FveLockInitialize
0x1400f0da4  lea     rcx, [rdi+2B0h]
0x1400f0dab  call    FveLockInitialize
0x1400f0db0  lea     rcx, [rdi+318h]
0x1400f0db7  mov     [rdi+308h], r14w
0x1400f0dbf  mov     [rdi+2A8h], r14
0x1400f0dc6  mov     [rdi+2A0h], r14
0x1400f0dcd  mov     [rdi+370h], r14b
0x1400f0dd4  call    FveLockInitialize
0x1400f0dd9  lea     rcx, [rbp+57h+var_90]
0x1400f0ddd  mov     [rdi+371h], r14b
0x1400f0de4  call    FveIsWinPEBoot
0x1400f0de9  test    eax, eax
0x1400f0deb  js      short loc_1400F0DF6
0x1400f0ded  mov     al, [rbp+57h+var_90]
0x1400f0df0  mov     [rdi+371h], al
0x1400f0df6  lea     rcx, [rdi+2680h]; Mutex
0x1400f0dfd  mov     [rdi+26B8h], r14
0x1400f0e04  xor     edx, edx; Level
0x1400f0e06  mov     [rdi+26C0h], r14d
0x1400f0e0d  call    cs:__imp_KeInitializeMutex
0x1400f0e14  nop     dword ptr [rax+rax+00h]
0x1400f0e19  mov     rcx, rdi
0x1400f0e1c  call    FveCreateOrRefDriverCdo
0x1400f0e21  mov     rcx, rdi
0x1400f0e24  call    FveCfgInitialize
0x1400f0e29  lea     rcx, [rbp+57h+var_78]
0x1400f0e2d  call    cs:__imp_KsrGetFirmwareInformation
0x1400f0e34  nop     dword ptr [rax+rax+00h]
0x1400f0e39  shr     eax, 1Fh
0x1400f0e3c  xor     al, 1
0x1400f0e3e  mov     [rdi+2721h], al
0x1400f0e44  jz      loc_1400F0EF0
0x1400f0e4a  xor     r9d, r9d; ReturnLength
0x1400f0e4d  lea     rdx, [rbp+57h+SystemInformation]; SystemInformation
0x1400f0e51  lea     r8d, [r9+20h]; SystemInformationLength
0x1400f0e55  lea     ecx, [r9+5Ah]; SystemInformationClass
0x1400f0e59  call    cs:__imp_ZwQuerySystemInformation
0x1400f0e60  nop     dword ptr [rax+rax+00h]
0x1400f0e65  mov     ebx, eax
0x1400f0e67  test    eax, eax
0x1400f0e69  js      loc_1400F0F14
0x1400f0e6f  test    byte ptr [rbp+57h+var_30+8], 4
0x1400f0e73  jz      short loc_1400F0E7C
0x1400f0e75  mov     byte ptr [rdi+2722h], 1
0x1400f0e7c  lea     rax, [rbp+57h+var_88]
0x1400f0e80  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400f0e87  xorps   xmm0, xmm0
0x1400f0e8a  mov     [rbp+57h+ObjectAttributes.RootDirectory], r14
0x1400f0e8e  lea     rsi, [rdi+2728h]
0x1400f0e95  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x1400f0e9c  mov     rcx, rsi; CallbackObject
0x1400f0e9f  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1400f0ea3  xor     r9d, r9d; AllowMultipleCallbacks
0x1400f0ea6  lea     rdx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1400f0eaa  xor     r8d, r8d; Create
0x1400f0ead  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400f0eb2  call    cs:__imp_ExCreateCallback
0x1400f0eb9  nop     dword ptr [rax+rax+00h]
0x1400f0ebe  mov     ebx, eax
0x1400f0ec0  test    eax, eax
0x1400f0ec2  js      short loc_1400F0F14
0x1400f0ec4  mov     rcx, [rsi]; CallbackObject
0x1400f0ec7  lea     rdx, FveKsrNotifyCallbackRoutine; CallbackFunction
0x1400f0ece  mov     r8, rdi; CallbackContext
0x1400f0ed1  call    cs:__imp_ExRegisterCallback
0x1400f0ed8  nop     dword ptr [rax+rax+00h]
0x1400f0edd  mov     [rdi+2730h], rax
0x1400f0ee4  test    rax, rax
0x1400f0ee7  jnz     short loc_1400F0EF0
0x1400f0ee9  mov     ebx, 0C0000001h
0x1400f0eee  jmp     short loc_1400F0F14
0x1400f0ef0  call    Feature_BitLocker_PhysicalLayout__private_IsEnabledDeviceUsageNoInline
0x1400f0ef5  test    eax, eax
0x1400f0ef7  jz      short loc_1400F0F14
0x1400f0ef9  xor     eax, eax
0x1400f0efb  mov     ebx, r14d
0x1400f0efe  mov     [rdi+2A18h], al
0x1400f0f04  jmp     short loc_1400F0F14
0x1400f0f06  mov     [rcx], r14w
0x1400f0f0a  mov     [rdi+3Ah], r14w
0x1400f0f0f  mov     ebx, 0C000009Ah
0x1400f0f14  mov     eax, ebx
0x1400f0f16  mov     rcx, [rbp+57h+var_20]
0x1400f0f1a  xor     rcx, rsp; StackCookie
0x1400f0f1d  call    __security_check_cookie
0x1400f0f22  lea     r11, [rsp+0C0h+var_10]
0x1400f0f2a  mov     rbx, [r11+28h]
0x1400f0f2e  mov     rsi, [r11+38h]
0x1400f0f32  mov     rsp, r11
0x1400f0f35  pop     r14
0x1400f0f37  pop     rdi
0x1400f0f38  pop     rbp
0x1400f0f39  retn
```
