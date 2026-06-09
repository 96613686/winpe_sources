# Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled(bool &)

- ea: `0x1800c6bd0`
- end: `0x1800c6d4d`
- name: `?IsEnabled@InstallMonTracer@InstallMon@Inventory@Compat@Windows@@UEAA_NAEA_N@Z`
- size: `381`
- prototype: `bool __fastcall(Windows::Compat::Inventory::InstallMon::InstallMonTracer *__hidden this, bool *)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180010b74`
- `0x1800152d0`
- `0x1800c6bd0`
- `0x1800c6eac`
- `0x1800d1010`

## string_xrefs

- `0x1800c6cb4`: `InstallMonTracer::IsEnabled - Test Mode Enabled`
- `0x1800c6d02`: `InstallMonTracer::IsEnabled - Install Monitoring Disabled`
- `0x1800c6bf0`: `Failed to initialize InstallMon APIs [%#x]`
- `0x1800c6c01`: `Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled`
- `0x1800c6cbe`: `Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled`
- `0x1800c6d0f`: `Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled`
- `0x1800c6d32`: `Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled`
- `0x1800c6d21`: `InstallMonTracer::IsEnabled returned: %d`
- `0x1800c6c2e`: `Install Monitoring - Feature_InstallTracingV2 is not enabled.`
- `0x1800c6c5e`: `Install Monitoring - Feature_InstallTracingV2 is not enabled.`
- `0x1800c6c37`: `Windows::Compat::Inventory::InstallMonApi::IsTestModeEnabled`
- `0x1800c6c99`: `Windows::Compat::Inventory::InstallMonApi::IsTestModeEnabled`
- `0x1800c6c69`: `Windows::Compat::Inventory::InstallMonApi::IsEnabled`
- `0x1800c6ceb`: `Windows::Compat::Inventory::InstallMonApi::IsEnabled`

## pseudocode

```c
unsigned __int8 __fastcall Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled(
        Windows::Compat::Inventory::InstallMon::InstallMonTracer *this,
        bool *a2)
{
  int v3; // eax
  unsigned __int8 v5; // di
  int v6; // ebx
  int v7; // ebx

  *a2 = 0;
  v3 = Windows::Compat::Inventory::InstallMonApi::InitializeApis((Windows::Compat::Inventory::InstallMonApi *)&Windows::Compat::Inventory::InstallMonApi::s_InstallMonApis);
  if ( v3 < 0 )
  {
    AslLogCallPrintf(
      1,
      "Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled",
      133,
      "Failed to initialize InstallMon APIs [%#x]",
      v3);
    return 0;
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
  {
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMonApi::IsTestModeEnabled",
      141,
      "Install Monitoring - Feature_InstallTracingV2 is not enabled.");
LABEL_5:
    v5 = 1;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl'::`2'::impl) )
    {
      v7 = ((__int64 (*)(void))qword_1800FF0F8)();
      AslLogCallPrintf(3, "Windows::Compat::Inventory::InstallMonApi::IsEnabled", 117, "IsEnabled returned: %d", v7);
      if ( !v7 )
      {
        v5 = 0;
        AslLogCallPrintf(
          3,
          "Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled",
          149,
          "InstallMonTracer::IsEnabled - Install Monitoring Disabled");
      }
    }
    else
    {
      AslLogCallPrintf(
        3,
        "Windows::Compat::Inventory::InstallMonApi::IsEnabled",
        111,
        "Install Monitoring - Feature_InstallTracingV2 is not enabled.");
    }
    AslLogCallPrintf(
      3,
      "Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled",
      152,
      "InstallMonTracer::IsEnabled returned: %d",
      v5);
    return v5;
  }
  v6 = ((__int64 (*)(void))qword_1800FF100)();
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InstallMonApi::IsTestModeEnabled",
    147,
    "IsTestModeEnabled returned: %d",
    v6);
  if ( !v6 )
    goto LABEL_5;
  v5 = 1;
  *a2 = 1;
  AslLogCallPrintf(
    3,
    "Windows::Compat::Inventory::InstallMon::InstallMonTracer::IsEnabled",
    141,
    "InstallMonTracer::IsEnabled - Test Mode Enabled");
  return v5;
}

```

## disassembly

```asm
0x1800c6bd0  push    rbx
0x1800c6bd2  push    rsi
0x1800c6bd3  push    rdi
0x1800c6bd4  push    r14
0x1800c6bd6  sub     rsp, 38h
0x1800c6bda  lea     rcx, ?s_InstallMonApis@InstallMonApi@Inventory@Compat@Windows@@0V1234@A; this
0x1800c6be1  mov     byte ptr [rdx], 0
0x1800c6be4  mov     r14, rdx
0x1800c6be7  call    ?InitializeApis@InstallMonApi@Inventory@Compat@Windows@@QEAAJXZ; Windows::Compat::Inventory::InstallMonApi::InitializeApis(void)
0x1800c6bec  test    eax, eax
0x1800c6bee  jns     short loc_1800C6C19
0x1800c6bf0  lea     r9, aFailedToInitia_0; "Failed to initialize InstallMon APIs [%"...
0x1800c6bf7  mov     [rsp+58h+var_38], eax
0x1800c6bfb  mov     r8d, 85h
0x1800c6c01  lea     rdx, aWindowsCompatI_33; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6c08  mov     ecx, 1
0x1800c6c0d  call    AslLogCallPrintf
0x1800c6c12  xor     al, al
0x1800c6c14  jmp     loc_1800C6D43
0x1800c6c19  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x1800c6c20  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x1800c6c25  test    al, al
0x1800c6c27  jnz     short loc_1800C6C75
0x1800c6c29  mov     esi, 3
0x1800c6c2e  lea     r9, aInstallMonitor; "Install Monitoring - Feature_InstallTra"...
0x1800c6c35  mov     ecx, esi
0x1800c6c37  lea     rdx, aWindowsCompatI_35; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6c3e  mov     r8d, 8Dh
0x1800c6c44  call    AslLogCallPrintf
0x1800c6c49  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallTracingV2@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2> `wil::Feature<__WilFeatureTraits_Feature_InstallTracingV2>::GetImpl(void)'::`2'::impl
0x1800c6c50  mov     edi, 1
0x1800c6c55  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallTracingV2@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallTracingV2>::__private_IsEnabled(void)
0x1800c6c5a  test    al, al
0x1800c6c5c  jnz     short loc_1800C6CCE
0x1800c6c5e  lea     r9, aInstallMonitor; "Install Monitoring - Feature_InstallTra"...
0x1800c6c65  lea     r8d, [rdi+6Eh]
0x1800c6c69  lea     rdx, aWindowsCompatI_16; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6c70  jmp     loc_1800C6D16
0x1800c6c75  mov     rax, cs:qword_1800FF100
0x1800c6c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6c81  mov     esi, 3
0x1800c6c86  mov     [rsp+58h+var_38], eax
0x1800c6c8a  mov     ecx, esi
0x1800c6c8c  lea     r9, aIstestmodeenab_0; "IsTestModeEnabled returned: %d"
0x1800c6c93  mov     r8d, 93h
0x1800c6c99  lea     rdx, aWindowsCompatI_35; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6ca0  mov     ebx, eax
0x1800c6ca2  call    AslLogCallPrintf
0x1800c6ca7  test    ebx, ebx
0x1800c6ca9  jz      short loc_1800C6C49
0x1800c6cab  lea     edi, [rsi-2]
0x1800c6cae  mov     r8d, 8Dh
0x1800c6cb4  lea     r9, aInstallmontrac; "InstallMonTracer::IsEnabled - Test Mode"...
0x1800c6cbb  mov     [r14], dil
0x1800c6cbe  lea     rdx, aWindowsCompatI_33; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6cc5  mov     ecx, esi
0x1800c6cc7  call    AslLogCallPrintf
0x1800c6ccc  jmp     short loc_1800C6D40
0x1800c6cce  mov     rax, cs:qword_1800FF0F8
0x1800c6cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c6cda  lea     r9, aIsenabledRetur; "IsEnabled returned: %d"
0x1800c6ce1  mov     [rsp+58h+var_38], eax
0x1800c6ce5  mov     r8d, 75h ; 'u'
0x1800c6ceb  lea     rdx, aWindowsCompatI_16; "Windows::Compat::Inventory::InstallMonA"...
0x1800c6cf2  mov     ecx, esi
0x1800c6cf4  mov     ebx, eax
0x1800c6cf6  call    AslLogCallPrintf
0x1800c6cfb  test    ebx, ebx
0x1800c6cfd  jnz     short loc_1800C6D1D
0x1800c6cff  xor     dil, dil
0x1800c6d02  lea     r9, aInstallmontrac_2; "InstallMonTracer::IsEnabled - Install M"...
0x1800c6d09  mov     r8d, 95h
0x1800c6d0f  lea     rdx, aWindowsCompatI_33; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6d16  mov     ecx, esi
0x1800c6d18  call    AslLogCallPrintf
0x1800c6d1d  movzx   eax, dil
0x1800c6d21  lea     r9, aInstallmontrac_1; "InstallMonTracer::IsEnabled returned: %"...
0x1800c6d28  mov     r8d, 98h
0x1800c6d2e  mov     [rsp+58h+var_38], eax
0x1800c6d32  lea     rdx, aWindowsCompatI_33; "Windows::Compat::Inventory::InstallMon:"...
0x1800c6d39  mov     ecx, esi
0x1800c6d3b  call    AslLogCallPrintf
0x1800c6d40  mov     al, dil
0x1800c6d43  add     rsp, 38h
0x1800c6d47  pop     r14
0x1800c6d49  pop     rdi
0x1800c6d4a  pop     rsi
0x1800c6d4b  pop     rbx
0x1800c6d4c  retn
```
