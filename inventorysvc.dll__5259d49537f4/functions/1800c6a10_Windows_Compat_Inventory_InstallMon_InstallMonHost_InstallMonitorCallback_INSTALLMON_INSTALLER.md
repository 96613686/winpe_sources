# Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback(_INSTALLMON_INSTALLER *)

- ea: `0x1800c6a10`
- end: `0x1800c6bc5`
- name: `?InstallMonitorCallback@InstallMonHost@InstallMon@Inventory@Compat@Windows@@SAXPEAU_INSTALLMON_INSTALLER@@@Z`
- size: `437`
- prototype: `void __fastcall(struct _INSTALLMON_INSTALLER *)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010b74`
- `0x1800152d0`
- `0x1800c6a10`
- `0x1800d1010`

## string_xrefs

- `0x1800c6a2e`: `Invalid installer callback. installer is NULL. Unable to continue.`
- `0x1800c6acc`: `Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback`
- `0x1800c6aeb`: `Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback`
- `0x1800c6b86`: `Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback`
- `0x1800c6ba9`: `Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback`
- `0x1800c6b7f`: `Failed to free installer monitoring callback [%#x]`
- `0x1800c6b9e`: `Successfully freed installer monitoring callback`
- `0x1800c6ac5`: `Failed to update installer inventory cache [%#x]`
- `0x1800c6ae4`: `Successfully updated installer inventory cache`
- `0x1800c6a4f`: `Install Monitoring - Feature_InstallTracingV2 is not enabled.`
- `0x1800c6b0b`: `Install Monitoring - Feature_InstallTracingV2 is not enabled.`
- `0x1800c6b4f`: `FreeInstallMonitoringCallback [%#x]`
- `0x1800c6a5c`: `Windows::Compat::Inventory::InstallMonApi::UpdateInstallerInventoryCache`
- `0x1800c6aa6`: `Windows::Compat::Inventory::InstallMonApi::UpdateInstallerInventoryCache`
- `0x1800c6b18`: `Windows::Compat::Inventory::InstallMonApi::FreeInstallMonitoringCallback`
- `0x1800c6b60`: `Windows::Compat::Inventory::InstallMonApi::FreeInstallMonitoringCallback`
- `0x1800c6a95`: `UpdateInstallerInventoryCache [%#x]`

## pseudocode

```c
void __fastcall Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback(
        struct _INSTALLMON_INSTALLER *a1)
{
  int v2; // ebx
  int v3; // esi

  if ( !a1 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback",
      87,
      "Invalid installer callback. installer is NULL. Unable to continue.");
    return;
  }
  v2 = -2147467263;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMonApi::UpdateInstallerInventoryCache",
      288,
      "Install Monitoring - Feature_InstallTracingV2 is not enabled.");
    v3 = -2147467263;
LABEL_9:
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback",
      96,
      "Failed to update installer inventory cache [%#x]",
      v3);
    goto LABEL_11;
  }
  v3 = -2147467262;
  if ( qword_1800FF120 && byte_1800FF128 )
    v3 = qword_1800FF120(a1);
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InstallMonApi::UpdateInstallerInventoryCache",
    298,
    "UpdateInstallerInventoryCache [%#x]",
    v3);
  if ( v3 < 0 )
    goto LABEL_9;
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback",
    101,
    "Successfully updated installer inventory cache");
LABEL_11:
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMonApi::FreeInstallMonitoringCallback",
      254,
      "Install Monitoring - Feature_InstallTracingV2 is not enabled.");
LABEL_17:
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback",
      107,
      "Failed to free installer monitoring callback [%#x]",
      v2);
    return;
  }
  v2 = -2147467262;
  if ( qword_1800FF118 )
  {
    if ( byte_1800FF128 )
      v2 = qword_1800FF118(a1);
  }
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InstallMonApi::FreeInstallMonitoringCallback",
    264,
    "FreeInstallMonitoringCallback [%#x]",
    v2);
  if ( v2 < 0 )
    goto LABEL_17;
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InstallMon::InstallMonHost::InstallMonitorCallback",
    111,
    "Successfully freed installer monitoring callback");
}

```

## disassembly

```asm
0x1800c6a10  mov     [rsp+arg_0], rbx
0x1800c6a15  mov     [rsp+arg_8], rbp
0x1800c6a1a  push    rsi
0x1800c6a1b  sub     rsp, 30h
0x1800c6a1f  mov     rbp, rcx
0x1800c6a22  test    rcx, rcx
0x1800c6a25  jnz     short loc_1800C6A3A
0x1800c6a27  lea     r8d, [rcx+57h]
0x1800c6a2b  lea     ecx, [rbp+1]
0x1800c6a2e  lea     r9, aInvalidInstall; "Invalid installer callback. installer i"...
0x1800c6a35  jmp     loc_1800C6BA9
0x1800c6a3a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x1800c6a41  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x1800c6a46  mov     ebx, 80004001h
0x1800c6a4b  test    al, al
0x1800c6a4d  jnz     short loc_1800C6A71
0x1800c6a4f  lea     r9, aInstallMonitor; "Install Monitoring - Feature_InstallTra"...
0x1800c6a56  mov     r8d, 120h
0x1800c6a5c  lea     rdx, aWindowsCompatI_59; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6a63  mov     ecx, 3
0x1800c6a68  call    AslLogCallPrintf
0x1800c6a6d  mov     esi, ebx
0x1800c6a6f  jmp     short loc_1800C6ABB
0x1800c6a71  mov     rax, cs:qword_1800FF120
0x1800c6a78  mov     esi, 80004002h
0x1800c6a7d  test    rax, rax
0x1800c6a80  jz      short loc_1800C6A95
0x1800c6a82  cmp     cs:byte_1800FF128, 0
0x1800c6a89  jz      short loc_1800C6A95
0x1800c6a8b  mov     rcx, rbp
0x1800c6a8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6a93  mov     esi, eax
0x1800c6a95  lea     r9, aUpdateinstalle_0; "UpdateInstallerInventoryCache [%#x]"
0x1800c6a9c  mov     [rsp+38h+var_18], esi
0x1800c6aa0  mov     r8d, 12Ah
0x1800c6aa6  lea     rdx, aWindowsCompatI_59; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6aad  mov     ecx, 3
0x1800c6ab2  call    AslLogCallPrintf
0x1800c6ab7  test    esi, esi
0x1800c6ab9  jns     short loc_1800C6ADE
0x1800c6abb  mov     r8d, 60h ; '`'
0x1800c6ac1  mov     [rsp+38h+var_18], esi
0x1800c6ac5  lea     r9, aFailedToUpdate; "Failed to update installer inventory ca"...
0x1800c6acc  lea     rdx, aWindowsCompatI_15; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6ad3  lea     ecx, [r8-5Fh]
0x1800c6ad7  call    AslLogCallPrintf
0x1800c6adc  jmp     short loc_1800C6AFB
0x1800c6ade  mov     r8d, 65h ; 'e'
0x1800c6ae4  lea     r9, aSuccessfullyUp; "Successfully updated installer inventor"...
0x1800c6aeb  lea     rdx, aWindowsCompatI_15; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6af2  lea     ecx, [r8-62h]
0x1800c6af6  call    AslLogCallPrintf
0x1800c6afb  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x1800c6b02  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x1800c6b07  test    al, al
0x1800c6b09  jnz     short loc_1800C6B2B
0x1800c6b0b  lea     r9, aInstallMonitor; "Install Monitoring - Feature_InstallTra"...
0x1800c6b12  mov     r8d, 0FEh
0x1800c6b18  lea     rdx, aWindowsCompatI_32; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6b1f  mov     ecx, 3
0x1800c6b24  call    AslLogCallPrintf
0x1800c6b29  jmp     short loc_1800C6B75
0x1800c6b2b  mov     rax, cs:qword_1800FF118
0x1800c6b32  mov     ebx, 80004002h
0x1800c6b37  test    rax, rax
0x1800c6b3a  jz      short loc_1800C6B4F
0x1800c6b3c  cmp     cs:byte_1800FF128, 0
0x1800c6b43  jz      short loc_1800C6B4F
0x1800c6b45  mov     rcx, rbp
0x1800c6b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6b4d  mov     ebx, eax
0x1800c6b4f  lea     r9, aFreeinstallmon; "FreeInstallMonitoringCallback [%#x]"
0x1800c6b56  mov     [rsp+38h+var_18], ebx
0x1800c6b5a  mov     r8d, 108h
0x1800c6b60  lea     rdx, aWindowsCompatI_32; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6b67  mov     ecx, 3
0x1800c6b6c  call    AslLogCallPrintf
0x1800c6b71  test    ebx, ebx
0x1800c6b73  jns     short loc_1800C6B98
0x1800c6b75  mov     r8d, 6Bh ; 'k'
0x1800c6b7b  mov     [rsp+38h+var_18], ebx
0x1800c6b7f  lea     r9, aFailedToFreeIn; "Failed to free installer monitoring cal"...
0x1800c6b86  lea     rdx, aWindowsCompatI_15; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6b8d  lea     ecx, [r8-6Ah]
0x1800c6b91  call    AslLogCallPrintf
0x1800c6b96  jmp     short loc_1800C6BB5
0x1800c6b98  mov     r8d, 6Fh ; 'o'
0x1800c6b9e  lea     r9, aSuccessfullyFr; "Successfully freed installer monitoring"...
0x1800c6ba5  lea     ecx, [r8-6Ch]
0x1800c6ba9  lea     rdx, aWindowsCompatI_15; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6bb0  call    AslLogCallPrintf
0x1800c6bb5  mov     rbx, [rsp+38h+arg_0]
0x1800c6bba  mov     rbp, [rsp+38h+arg_8]
0x1800c6bbf  add     rsp, 30h
0x1800c6bc3  pop     rsi
0x1800c6bc4  retn
```
