# DriverEntry

- ea: `0x14002bd4c`
- end: `0x14002c10a`
- name: `DriverEntry`
- size: `958`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140059010`

## callees

- `0x140029764`
- `0x140029c14`
- `0x14002a9ac`
- `0x14002bd4c`
- `0x14002c54c`
- `0x14002c58c`
- `0x140051c00`
- `0x140051c84`
- `0x140051d18`
- `0x140054860`
- `0x1400549a0`
- `0x140059078`

## import_xrefs

- `ntoskrnl!EtwRegister` at `0x14002be71`
- `ntoskrnl!EtwRegister` at `0x14002be71`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14002bdae`
- `ntoskrnl!KeQueryTimeIncrement` at `0x14002bdae`
- `ntoskrnl!EtwUnregister` at `0x14002c0d8`
- `ntoskrnl!EtwUnregister` at `0x14002c0d8`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002bfb5`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002bff9`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002c038`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002c073`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002c0af`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002bfb5`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002bff9`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002c038`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002c073`
- `mrxsmb!MRxSmbRegisterDialect` at `0x14002c0af`
- `mrxsmb!MRxSmbRegisterSubRedirector` at `0x14002bf67`
- `mrxsmb!MRxSmbRegisterSubRedirector` at `0x14002bf67`
- `mrxsmb!SmbCryptoKeyedHashInitialize` at `0x14002bf14`
- `mrxsmb!SmbCryptoKeyedHashInitialize` at `0x14002bf14`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002bf4f`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002bf7d`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002bfe4`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002c005`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002c044`
- `mrxsmb!MRxSmbDeviceObject` at `0x14002c07f`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  ULONG TimeIncrement; // eax
  unsigned __int64 v4; // rdx
  PDEVICE_OBJECT v5; // rcx
  unsigned int v6; // eax
  unsigned int v7; // eax
  NTSTATUS v8; // edi
  int v10; // [rsp+20h] [rbp-58h]
  int v11; // [rsp+20h] [rbp-58h]
  int v12; // [rsp+20h] [rbp-58h]
  int v13; // [rsp+20h] [rbp-58h]
  int v14; // [rsp+20h] [rbp-58h]
  int v15; // [rsp+28h] [rbp-50h]
  int v16; // [rsp+28h] [rbp-50h]
  int v17; // [rsp+28h] [rbp-50h]
  int v18; // [rsp+28h] [rbp-50h]
  int v19; // [rsp+38h] [rbp-40h]
  int v20; // [rsp+38h] [rbp-40h]
  int v21; // [rsp+38h] [rbp-40h]
  int v22; // [rsp+38h] [rbp-40h]

  *(_QWORD *)&WPP_MAIN_CB.Type = 0;
  WPP_MAIN_CB.DriverObject = (struct _DRIVER_OBJECT *)WPP_ThisDir_CTLGUID_Smb20Log;
  WPP_MAIN_CB.NextDevice = 0;
  WPP_MAIN_CB.CurrentIrp = 0;
  WPP_MAIN_CB.Timer = (PIO_TIMER)1;
  WppLoadTracingSupport(DriverObject, RegistryPath);
  WPP_MAIN_CB.CurrentIrp = 0;
  WppInitKm();
  wil_InitializeFeatureStaging();
  TlgRegisterAggregateProvider();
  WPP_MAIN_CB.Queue.ListEntry.Flink = 0;
  TimeIncrement = KeQueryTimeIncrement();
  v4 = 0xC92A69C000uLL % TimeIncrement;
  WPP_MAIN_CB.Queue.ListEntry.Blink = (struct _LIST_ENTRY *)(0xC92A69C000uLL / TimeIncrement);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qZ(
      WPP_GLOBAL_Control->AttachedDevice,
      13,
      (unsigned int)WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids,
      (_DWORD)DriverObject,
      (__int64)&DriverObject->DriverName);
  }
  v6 = McGenEventRegister_EtwRegister(v5, v4);
  if ( v6
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids, v6);
  }
  if ( Microsoft_Windows_Networking_CorrelationHandle
    || (v7 = EtwRegister(
               &Microsoft_Windows_Networking_CorrelationId,
               Microsoft_Windows_Networking_Correlation_EtwEnableCallback,
               0,
               &Microsoft_Windows_Networking_CorrelationHandle)) == 0 )
  {
    Microsoft_Windows_Networking_ProviderId = (__int128)REMOTEFS_SMB;
  }
  else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
         && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
         && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids, v7);
  }
  Smb2FileAbeStatusCacheLock = 0;
  qword_140046378 = (__int64)&GlobalDirCacheObjectList;
  GlobalDirCacheObjectList = (__int64)&GlobalDirCacheObjectList;
  Smb2FileIdentityCacheLock = 0;
  Smb2FileInfoCacheLock = 0;
  Smb2FileNotFoundCacheLock = 0;
  Smb2VolumeInfoCacheLock = 0;
  Smb2VolumeFeatureSupportCacheLock = 0;
  Smb2GlobalFilePropertyCacheLock = 0;
  Smb2DirCacheLock = 0;
  GlobalDirCacheObjectListLock = 0;
  if ( (int)SmbCryptoKeyedHashInitialize() < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids);
  }
  v8 = MRxSmbRegisterSubRedirector(MRxSmbDeviceObject, qword_14003E7C0, &WPP_MAIN_CB.DeviceExtension);
  if ( v8 >= 0 )
  {
    LOWORD(v10) = 0;
    MRxSmbRegisterDialect(MRxSmbDeviceObject, WPP_MAIN_CB.DeviceExtension, 6, 2, v10, 2, "SMB 2.002", 514);
    LOWORD(v19) = 528;
    LOWORD(v15) = 0;
    LOWORD(v11) = 1;
    MRxSmbRegisterDialect(MRxSmbDeviceObject, WPP_MAIN_CB.DeviceExtension, 7, 2, v11, v15, "SMB 2.???", v19);
    LOWORD(v20) = 768;
    LOWORD(v16) = 0;
    LOWORD(v12) = 0;
    MRxSmbRegisterDialect(MRxSmbDeviceObject, WPP_MAIN_CB.DeviceExtension, 8, 3, v12, v16, 0, v20);
    LOWORD(v21) = 770;
    LOWORD(v17) = 2;
    LOWORD(v13) = 0;
    MRxSmbRegisterDialect(MRxSmbDeviceObject, WPP_MAIN_CB.DeviceExtension, 9, 3, v13, v17, 0, v21);
    LOWORD(v22) = 785;
    LOWORD(v18) = 1;
    LOWORD(v14) = 1;
    MRxSmbRegisterDialect(MRxSmbDeviceObject, WPP_MAIN_CB.DeviceExtension, 10, 3, v14, v18, 0, v22);
  }
  MRxSmb20DriverObject = (__int64)DriverObject;
  DriverObject->DriverUnload = (PDRIVER_UNLOAD)MRxSmb20Unload;
  if ( v8 < 0 )
  {
    EtwUnregister(Microsoft_Windows_Networking_CorrelationHandle);
    Microsoft_Windows_Networking_CorrelationHandle = 0;
    McGenEventUnregister_EtwUnregister();
    TlgUnregisterAggregateProvider();
    WppCleanupKm();
  }
  return v8;
}

```

## disassembly

```asm
0x14002bd4c  push    rbx
0x14002bd4e  push    rbp
0x14002bd4f  push    rsi
0x14002bd50  push    rdi
0x14002bd51  push    r12
0x14002bd53  push    r14
0x14002bd55  sub     rsp, 48h
0x14002bd59  xor     ebp, ebp
0x14002bd5b  lea     rax, WPP_ThisDir_CTLGUID_Smb20Log
0x14002bd62  mov     rbx, rcx
0x14002bd65  mov     qword ptr cs:WPP_MAIN_CB.Type, rbp
0x14002bd6c  mov     cs:WPP_MAIN_CB.DriverObject, rax
0x14002bd73  mov     cs:WPP_MAIN_CB.NextDevice, rbp
0x14002bd7a  lea     r12d, [rbp+1]
0x14002bd7e  mov     cs:WPP_MAIN_CB.CurrentIrp, rbp
0x14002bd85  mov     cs:WPP_MAIN_CB.Timer, r12
0x14002bd8c  call    WppLoadTracingSupport
0x14002bd91  mov     cs:WPP_MAIN_CB.CurrentIrp, rbp; __annotation("TMC:", "e4ad554c-63b2-441b-9f86-fe66d8084963", "Smb20Log", "SMB20_TRACE_TYPE_ERROR", "SMB20_TRACE_TYPE_MISC", "SMB20_TRACE_TYPE_NETWORK", "SMB20_TRACE_TYPE_SECURITY", "SMB20_TRACE_TYPE_EXCHANGE", "SMB20_TRACE_TYPE_IO", "SMB20_TRACE_TYPE_HANDLE", "SMB20_TRACE_TYPE_INFOCACHE", "SMB20_TRACE_TYPE_DIRCACHE", "SMB20_TRACE_TYPE_OPLOCK", "SMB20_TRACE_TYPE_PREAUTH_INTEGRITY", "SMB20_TRACE_TYPE_COMPRESSION", "PUBLIC_TMF:")
0x14002bd98  call    WppInitKm
0x14002bd9d  call    wil_InitializeFeatureStaging
0x14002bda2  call    TlgRegisterAggregateProvider
0x14002bda7  mov     qword ptr cs:WPP_MAIN_CB.Queue, rbp
0x14002bdae  call    cs:__imp_KeQueryTimeIncrement
0x14002bdb5  nop     dword ptr [rax+rax+00h]
0x14002bdba  mov     ecx, eax
0x14002bdbc  xor     edx, edx
0x14002bdbe  mov     rax, 0C92A69C000h
0x14002bdc8  div     rcx
0x14002bdcb  mov     qword ptr cs:WPP_MAIN_CB.Queue+8, rax
0x14002bdd2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002bdd9  lea     rdi, WPP_GLOBAL_Control
0x14002bde0  lea     rsi, WPP_e15cc368ef4a3858d7f125a132a18f72_Traceguids
0x14002bde7  lea     r14d, [rbp+2]
0x14002bdeb  cmp     rcx, rdi
0x14002bdee  jz      short loc_14002BE19
0x14002bdf0  mov     eax, [rcx+2Ch]
0x14002bdf3  test    r14b, al
0x14002bdf6  jz      short loc_14002BE19
0x14002bdf8  cmp     byte ptr [rcx+29h], 4
0x14002bdfc  jb      short loc_14002BE19
0x14002bdfe  mov     rcx, [rcx+18h]
0x14002be02  lea     rax, [rbx+38h]
0x14002be06  lea     edx, [rbp+0Dh]
0x14002be09  mov     [rsp+78h+var_58], rax
0x14002be0e  mov     r9, rbx
0x14002be11  mov     r8, rsi
0x14002be14  call    WPP_SF_qZ
0x14002be19  call    McGenEventRegister_EtwRegister
0x14002be1e  test    eax, eax
0x14002be20  jz      short loc_14002BE50
0x14002be22  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002be29  cmp     rcx, rdi
0x14002be2c  jz      short loc_14002BE50
0x14002be2e  mov     edx, [rcx+2Ch]
0x14002be31  test    r14b, dl
0x14002be34  jz      short loc_14002BE50
0x14002be36  cmp     byte ptr [rcx+29h], 4
0x14002be3a  jb      short loc_14002BE50
0x14002be3c  mov     rcx, [rcx+18h]
0x14002be40  mov     edx, 0Eh
0x14002be45  mov     r9d, eax
0x14002be48  mov     r8, rsi
0x14002be4b  call    WPP_SF_d
0x14002be50  cmp     cs:Microsoft_Windows_Networking_CorrelationHandle, rbp
0x14002be57  jnz     short loc_14002BEB1
0x14002be59  lea     r9, Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14002be60  xor     r8d, r8d; CallbackContext
0x14002be63  lea     rdx, Microsoft_Windows_Networking_Correlation_EtwEnableCallback; EnableCallback
0x14002be6a  lea     rcx, Microsoft_Windows_Networking_CorrelationId; ProviderId
0x14002be71  call    cs:__imp_EtwRegister
0x14002be78  nop     dword ptr [rax+rax+00h]
0x14002be7d  test    eax, eax
0x14002be7f  jz      short loc_14002BEB1
0x14002be81  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002be88  cmp     rcx, rdi
0x14002be8b  jz      short loc_14002BEC0
0x14002be8d  mov     edx, [rcx+2Ch]
0x14002be90  test    r14b, dl
0x14002be93  jz      short loc_14002BEC0
0x14002be95  cmp     byte ptr [rcx+29h], 4
0x14002be99  jb      short loc_14002BEC0
0x14002be9b  mov     rcx, [rcx+18h]
0x14002be9f  mov     edx, 0Fh
0x14002bea4  mov     r9d, eax
0x14002bea7  mov     r8, rsi
0x14002beaa  call    WPP_SF_d
0x14002beaf  jmp     short loc_14002BEC0
0x14002beb1  movups  xmm0, xmmword ptr cs:REMOTEFS_SMB.Data1
0x14002beb8  movdqu  cs:Microsoft_Windows_Networking_ProviderId, xmm0
0x14002bec0  lea     rax, GlobalDirCacheObjectList
0x14002bec7  mov     cs:Smb2FileAbeStatusCacheLock, rbp
0x14002bece  mov     cs:qword_140046378, rax
0x14002bed5  mov     cs:GlobalDirCacheObjectList, rax
0x14002bedc  mov     cs:Smb2FileIdentityCacheLock, rbp
0x14002bee3  mov     cs:Smb2FileInfoCacheLock, rbp
0x14002beea  mov     cs:Smb2FileNotFoundCacheLock, rbp
0x14002bef1  mov     cs:Smb2VolumeInfoCacheLock, rbp
0x14002bef8  mov     cs:Smb2VolumeFeatureSupportCacheLock, rbp
0x14002beff  mov     cs:Smb2GlobalFilePropertyCacheLock, rbp
0x14002bf06  mov     cs:Smb2DirCacheLock, rbp
0x14002bf0d  mov     cs:GlobalDirCacheObjectListLock, rbp
0x14002bf14  call    cs:__imp_SmbCryptoKeyedHashInitialize
0x14002bf1b  nop     dword ptr [rax+rax+00h]
0x14002bf20  test    eax, eax
0x14002bf22  jns     short loc_14002BF4F
0x14002bf24  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14002bf2b  cmp     rcx, rdi
0x14002bf2e  jz      short loc_14002BF4F
0x14002bf30  mov     eax, [rcx+2Ch]
0x14002bf33  test    r12b, al
0x14002bf36  jz      short loc_14002BF4F
0x14002bf38  cmp     [rcx+29h], r12b
0x14002bf3c  jb      short loc_14002BF4F
0x14002bf3e  mov     rcx, [rcx+18h]
0x14002bf42  mov     edx, 10h
0x14002bf47  mov     r8, rsi
0x14002bf4a  call    WPP_SF_
0x14002bf4f  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14002bf56  lea     r8, WPP_MAIN_CB.DeviceExtension
0x14002bf5d  lea     rdx, qword_14003E7C0
0x14002bf64  mov     rcx, [rcx]
0x14002bf67  call    cs:__imp_MRxSmbRegisterSubRedirector
0x14002bf6e  nop     dword ptr [rax+rax+00h]
0x14002bf73  mov     edi, eax
0x14002bf75  test    eax, eax
0x14002bf77  js      loc_14002C0BB
0x14002bf7d  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14002bf84  lea     rax, aSmb2002; "SMB 2.002"
0x14002bf8b  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x14002bf92  mov     r9d, r14d
0x14002bf95  mov     word ptr [rsp+78h+var_40], 202h
0x14002bf9c  mov     r8d, 6
0x14002bfa2  mov     [rsp+78h+var_48], rax
0x14002bfa7  mov     rcx, [rcx]
0x14002bfaa  mov     [rsp+78h+var_50], r14w
0x14002bfb0  mov     word ptr [rsp+78h+var_58], bp
0x14002bfb5  call    cs:__imp_MRxSmbRegisterDialect
0x14002bfbc  nop     dword ptr [rax+rax+00h]
0x14002bfc1  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x14002bfc8  lea     rcx, aSmb2; "SMB 2.???"
0x14002bfcf  mov     word ptr [rsp+78h+var_40], 210h
0x14002bfd6  mov     r9d, r14d
0x14002bfd9  mov     [rsp+78h+var_48], rcx
0x14002bfde  mov     r8d, 7
0x14002bfe4  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14002bfeb  mov     [rsp+78h+var_50], bp
0x14002bff0  mov     word ptr [rsp+78h+var_58], r12w
0x14002bff6  mov     rcx, [rcx]
0x14002bff9  call    cs:__imp_MRxSmbRegisterDialect
0x14002c000  nop     dword ptr [rax+rax+00h]
0x14002c005  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14002c00c  mov     esi, 3
0x14002c011  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x14002c018  mov     r9d, esi
0x14002c01b  mov     word ptr [rsp+78h+var_40], 300h
0x14002c022  mov     [rsp+78h+var_48], rbp
0x14002c027  mov     rcx, [rcx]
0x14002c02a  lea     r8d, [rsi+5]
0x14002c02e  mov     [rsp+78h+var_50], bp
0x14002c033  mov     word ptr [rsp+78h+var_58], bp
0x14002c038  call    cs:__imp_MRxSmbRegisterDialect
0x14002c03f  nop     dword ptr [rax+rax+00h]
0x14002c044  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14002c04b  lea     r8d, [rsi+6]
0x14002c04f  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x14002c056  mov     r9d, esi
0x14002c059  mov     word ptr [rsp+78h+var_40], 302h
0x14002c060  mov     [rsp+78h+var_48], rbp
0x14002c065  mov     rcx, [rcx]
0x14002c068  mov     [rsp+78h+var_50], r14w
0x14002c06e  mov     word ptr [rsp+78h+var_58], bp
0x14002c073  call    cs:__imp_MRxSmbRegisterDialect
0x14002c07a  nop     dword ptr [rax+rax+00h]
0x14002c07f  mov     rcx, cs:__imp_MRxSmbDeviceObject
0x14002c086  lea     r8d, [rsi+7]
0x14002c08a  mov     rdx, cs:WPP_MAIN_CB.DeviceExtension
0x14002c091  mov     r9d, esi
0x14002c094  mov     word ptr [rsp+78h+var_40], 311h
0x14002c09b  mov     [rsp+78h+var_48], rbp
0x14002c0a0  mov     rcx, [rcx]
0x14002c0a3  mov     [rsp+78h+var_50], r12w
0x14002c0a9  mov     word ptr [rsp+78h+var_58], r12w
0x14002c0af  call    cs:__imp_MRxSmbRegisterDialect
0x14002c0b6  nop     dword ptr [rax+rax+00h]
0x14002c0bb  mov     cs:MRxSmb20DriverObject, rbx
0x14002c0c2  lea     rax, MRxSmb20Unload
0x14002c0c9  mov     [rbx+68h], rax
0x14002c0cd  test    edi, edi
0x14002c0cf  jns     short loc_14002C0FA
0x14002c0d1  mov     rcx, cs:Microsoft_Windows_Networking_CorrelationHandle; RegHandle
0x14002c0d8  call    cs:__imp_EtwUnregister
0x14002c0df  nop     dword ptr [rax+rax+00h]
0x14002c0e4  mov     cs:Microsoft_Windows_Networking_CorrelationHandle, rbp
0x14002c0eb  call    McGenEventUnregister_EtwUnregister
0x14002c0f0  call    TlgUnregisterAggregateProvider
0x14002c0f5  call    WppCleanupKm
0x14002c0fa  mov     eax, edi
0x14002c0fc  add     rsp, 48h
0x14002c100  pop     r14
0x14002c102  pop     r12
0x14002c104  pop     rdi
0x14002c105  pop     rsi
0x14002c106  pop     rbp
0x14002c107  pop     rbx
0x14002c108  retn
```
