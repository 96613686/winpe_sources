# PatchDb_GetPatchSdbSettings(ulong &,ulong &,ulong &,ushort * &,ushort * &,ushort * &,int &,int &,int &)

- ea: `0x18002f8f4`
- end: `0x18002fec6`
- name: `?PatchDb_GetPatchSdbSettings@@YAKAEAK00AEAPEAG11AEAH22@Z`
- size: `1490`
- prototype: `__int64 __fastcall(unsigned int *, unsigned int *, unsigned int *, unsigned __int16 **, unsigned __int16 **, unsigned __int16 **, int *, int *, int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18002eff8`

## callees

- `0x180007020`
- `0x18000d530`
- `0x180012920`
- `0x18002a8e4`
- `0x18002dfbc`
- `0x18002e040`
- `0x18002f8f4`
- `0x18002fecc`
- `0x180030128`
- `0x1800302c0`
- `0x180030388`
- `0x18003dfcc`
- `0x180055840`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18002fe73`
- `msvcrt!??3@YAXPEAX@Z` at `0x18002fe73`
- `ntdll!RtlFreeHeap` at `0x18002fe90`
- `ntdll!RtlFreeHeap` at `0x18002fead`
- `ntdll!RtlFreeHeap` at `0x18002fe90`
- `ntdll!RtlFreeHeap` at `0x18002fead`
- `ntdll!RtlAllocateHeap` at `0x18002fc1e`
- `ntdll!RtlAllocateHeap` at `0x18002fce3`
- `ntdll!RtlAllocateHeap` at `0x18002fd94`
- `ntdll!RtlAllocateHeap` at `0x18002fc1e`
- `ntdll!RtlAllocateHeap` at `0x18002fce3`
- `ntdll!RtlAllocateHeap` at `0x18002fd94`

## string_xrefs

- `0x18002fa14`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18002fb0f`: `SOFTWARE\Microsoft\Windows NT\CurrentVersion\AppCompatFlags`
- `0x18002fa54`: `Onesettings failed to get DeviceId from registry: 0x%x`
- `0x18002fb40`: `settings-ppe.data.microsoft.com`
- `0x18002fb5b`: `settings-win.data.microsoft.com`
- `0x18002fc36`: `PatchSdbLink`
- `0x18002fc5e`: `Onesetting failed to query app patch link: 0x%x`
- `0x18002fcfb`: `DrvPatchSdbLink`
- `0x18002fd23`: `Onesetting failed to query drv patch link: 0x%x`
- `0x18002fdac`: `MergeSdbLink`
- `0x18002fdd0`: `Onesetting failed to query merge SDB link: 0x%x`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall PatchDb_GetPatchSdbSettings(
        unsigned int *a1,
        unsigned int *a2,
        unsigned int *a3,
        unsigned __int16 **a4,
        unsigned __int16 **a5,
        unsigned __int16 **a6,
        int *a7,
        int *a8,
        int *a9)
{
  int *v10; // r15
  unsigned __int16 *v11; // r12
  unsigned int RegistrySTRING; // ebx
  unsigned __int16 *v13; // rsi
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // rdx
  const unsigned __int16 *v16; // r8
  const unsigned __int16 *v17; // r9
  unsigned __int64 *v18; // r14
  int v19; // eax
  const char *v20; // r9
  int v21; // r8d
  const unsigned __int16 *v22; // rdx
  __int64 v23; // rax
  int v24; // eax
  bool v25; // r8
  const unsigned __int16 *v26; // r9
  const unsigned __int16 *v27; // rdx
  int v28; // eax
  int SettingDword; // eax
  unsigned __int16 *Heap; // rax
  int Setting; // eax
  unsigned int *v32; // rsi
  int v33; // eax
  const char *v34; // r9
  int v35; // r8d
  unsigned __int16 *v36; // rax
  int v37; // eax
  unsigned int *v38; // rsi
  int v39; // eax
  unsigned __int16 *v40; // rax
  int v41; // eax
  struct _SECURITY_ATTRIBUTES *v43; // [rsp+20h] [rbp-38h]
  struct _SECURITY_ATTRIBUTES *v44; // [rsp+20h] [rbp-38h]
  unsigned int v45; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int16 *v46[4]; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v47; // [rsp+A0h] [rbp+48h] BYREF
  unsigned int *v48; // [rsp+A8h] [rbp+50h]
  unsigned int *v49; // [rsp+B0h] [rbp+58h]
  unsigned __int16 **v50; // [rsp+B8h] [rbp+60h]

  v50 = a4;
  v49 = a3;
  v48 = a2;
  *a1 = 0;
  *a4 = 0;
  *a2 = 0;
  *a5 = 0;
  v10 = a7;
  *a7 = 0;
  *a8 = 0;
  *a9 = 0;
  v11 = 0;
  v46[0] = 0;
  LODWORD(a7) = 0;
  v47 = 0;
  v45 = 0;
  if ( !Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore((bool)a1) )
  {
    RegistrySTRING = 5;
    AslLogCallPrintf(
      1,
      (unsigned int)"PatchDb_GetPatchSdbSettings",
      1176,
      (unsigned int)"Onesettings core telemetry is not allowed %d");
    return RegistrySTRING;
  }
  v13 = 0;
  v14 = (unsigned __int16 *)operator new(0x750u);
  v46[1] = v14;
  if ( v14 )
    v18 = (unsigned __int64 *)OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(
                                (OneCore::Base::Telemetry::OneSettingsQuery *)v14,
                                v15,
                                v16,
                                v17,
                                (const unsigned __int16 *)v43);
  else
    v18 = 0;
  if ( v18 )
  {
    v19 = OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(
            (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
            (bool)v15);
    RegistrySTRING = v19;
    if ( v19 < 0 )
    {
      if ( (v19 & 0x1FFF0000) == 0x70000 )
        RegistrySTRING = (unsigned __int16)v19;
      v20 = "Onesettings failed to AddParameterOsVer: 0x%x";
      v21 = 1195;
      goto LABEL_76;
    }
    RegistrySTRING = PcaUtilityGetRegistrySTRING(
                       HKEY_LOCAL_MACHINE,
                       L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
                       L"PatchDbTestOneSettingsDevice",
                       v46);
    if ( RegistrySTRING )
    {
      RegistrySTRING = PcaUtilityGetRegistrySTRING(
                         HKEY_LOCAL_MACHINE,
                         L"SOFTWARE\\Microsoft\\SQMClient",
                         L"MachineId",
                         v46);
      if ( RegistrySTRING )
      {
        AslLogCallPrintf(
          1,
          (unsigned int)"PatchDb_GetPatchSdbSettings",
          1215,
          (unsigned int)"Onesettings failed to get DeviceId from registry: 0x%x");
        v11 = v46[0];
LABEL_77:
        OneCore::Base::Telemetry::OneSettingsQuery::~OneSettingsQuery((OneCore::Base::Telemetry::OneSettingsQuery *)v18);
        operator delete(v18);
        goto LABEL_78;
      }
    }
    v11 = v46[0];
    AslLogCallPrintf(3, (unsigned int)"PatchDb_GetPatchSdbSettings", 1219, (unsigned int)"OneSetting DeviceId is [%ws]");
    if ( !v11 )
      goto LABEL_73;
    v23 = -1;
    do
      ++v23;
    while ( v11[v23] );
    if ( !v23 )
    {
LABEL_73:
      LOWORD(v24) = 87;
      goto LABEL_74;
    }
    v24 = RtlNameValueArray::Insert((RtlNameValueArray *)(v18 + 207), v22, L"deviceid", v11, v18[209]);
    if ( v24 < 0 )
    {
      if ( (v24 & 0x1FFF0000) != 0x70000 )
      {
        RegistrySTRING = v24;
LABEL_75:
        v20 = "Onesettings failed to AddParameterDeviceId: 0x%x";
        v21 = 1225;
LABEL_76:
        AslLogCallPrintf(1, (unsigned int)"PatchDb_GetPatchSdbSettings", v21, (_DWORD)v20);
        goto LABEL_77;
      }
LABEL_74:
      RegistrySTRING = (unsigned __int16)v24;
      goto LABEL_75;
    }
    if ( PcaUtilityGetRegistryDWORD(
           HKEY_LOCAL_MACHINE,
           L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\AppCompatFlags",
           L"PatchDbUseTestOneSettings",
           0) )
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"PatchDb_GetPatchSdbSettings",
        1237,
        (unsigned int)"Onesettings querying PPE server");
      v27 = L"settings-ppe.data.microsoft.com";
    }
    else
    {
      AslLogCallPrintf(
        3,
        (unsigned int)"PatchDb_GetPatchSdbSettings",
        1241,
        (unsigned int)"Onesettings querying production server");
      v27 = L"settings-win.data.microsoft.com";
    }
    v28 = OneCore::Base::Telemetry::OneSettingsQuery::Query(
            (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
            v27,
            v25,
            v26,
            v44);
    if ( v28 < 0 )
    {
      RegistrySTRING = (unsigned __int16)v28;
      if ( (v28 & 0x1FFF0000) != 0x70000 )
        RegistrySTRING = v28;
      v20 = "Onesettings failed to Query Onesettings: 0x%x";
      v21 = 1247;
      goto LABEL_76;
    }
    if ( (int)OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(
                (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
                L"ResetPatchSdb",
                (unsigned int *)&a7) >= 0 )
    {
      if ( (_DWORD)a7 )
      {
        *v10 = 1;
        goto LABEL_77;
      }
      *v10 = 0;
    }
    SettingDword = OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(
                     (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
                     L"PatchSdbRevision",
                     a1);
    RegistrySTRING = SettingDword;
    if ( SettingDword < 0 )
    {
      if ( (SettingDword & 0x1FFF0000) == 0x70000 )
        RegistrySTRING = (unsigned __int16)SettingDword;
      v20 = "Onesetting failed to query app patch revision : 0x%x";
      v21 = 1271;
      goto LABEL_76;
    }
    RegistrySTRING = 8;
    if ( *a1 )
    {
      Heap = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1040u);
      v13 = Heap;
      if ( !Heap )
        goto LABEL_77;
      Setting = OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(
                  (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
                  L"PatchSdbLink",
                  Heap,
                  0x1040u);
      if ( Setting < 0 )
      {
        RegistrySTRING = (unsigned __int16)Setting;
        if ( (Setting & 0x1FFF0000) != 0x70000 )
          RegistrySTRING = Setting;
        v20 = "Onesetting failed to query app patch link: 0x%x";
        v21 = 1285;
        goto LABEL_76;
      }
      *v50 = v13;
    }
    v32 = v48;
    v33 = OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(
            (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
            L"DrvPatchSdbRevision",
            v48);
    if ( v33 >= 0 )
    {
      if ( *v32 )
      {
        v36 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1040u);
        v13 = v36;
        if ( !v36 )
          goto LABEL_77;
        v37 = OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(
                (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
                L"DrvPatchSdbLink",
                v36,
                0x1040u);
        if ( v37 < 0 )
        {
          RegistrySTRING = (unsigned __int16)v37;
          if ( (v37 & 0x1FFF0000) != 0x70000 )
            RegistrySTRING = v37;
          v20 = "Onesetting failed to query drv patch link: 0x%x";
          v21 = 1310;
          goto LABEL_76;
        }
        *a5 = v13;
      }
      v38 = v49;
      v39 = OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(
              (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
              L"MergeSdbRevision",
              v49);
      if ( v39 >= 0 )
      {
        if ( *v38 )
        {
          v40 = (unsigned __int16 *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x1040u);
          v13 = v40;
          if ( !v40 )
            goto LABEL_77;
          v41 = OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(
                  (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
                  L"MergeSdbLink",
                  v40,
                  0x1040u);
          RegistrySTRING = v41;
          if ( v41 < 0 )
          {
            if ( (v41 & 0x1FFF0000) == 0x70000 )
              RegistrySTRING = (unsigned __int16)v41;
            v20 = "Onesetting failed to query merge SDB link: 0x%x";
            v21 = 1335;
            goto LABEL_76;
          }
          *a6 = v13;
        }
        if ( (int)OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(
                    (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
                    L"DisableMergeSdbs",
                    &v47) >= 0 )
          *a8 = v47 != 0;
        if ( (int)OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(
                    (OneCore::Base::Telemetry::OneSettingsQuery *)v18,
                    L"DisableDoubleQuerySdbs",
                    &v45) >= 0 )
          *a9 = v45 != 0;
        RegistrySTRING = 0;
        goto LABEL_49;
      }
      RegistrySTRING = (unsigned __int16)v39;
      if ( (v39 & 0x1FFF0000) != 0x70000 )
        RegistrySTRING = v39;
      v34 = "Onesetting failed to query merge SDB revision : 0x%x";
      v35 = 1321;
    }
    else
    {
      RegistrySTRING = (unsigned __int16)v33;
      if ( (v33 & 0x1FFF0000) != 0x70000 )
        RegistrySTRING = v33;
      v34 = "Onesetting failed to query drv patch revision : 0x%x";
      v35 = 1296;
    }
    AslLogCallPrintf(1, (unsigned int)"PatchDb_GetPatchSdbSettings", v35, (_DWORD)v34);
LABEL_49:
    v13 = 0;
    goto LABEL_77;
  }
  RegistrySTRING = 8;
  AslLogCallPrintf(
    1,
    (unsigned int)"PatchDb_GetPatchSdbSettings",
    1184,
    (unsigned int)"Failed to initialize onesettings");
LABEL_78:
  if ( v11 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v11);
  if ( v13 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v13);
  return RegistrySTRING;
}

```

## disassembly

```asm
0x18002f8f4  mov     [rsp-40h+arg_18], r9
0x18002f8f9  mov     [rsp-40h+arg_10], r8
0x18002f8fe  mov     [rsp-40h+arg_8], rdx
0x18002f903  push    rbp
0x18002f904  push    rbx
0x18002f905  push    rsi
0x18002f906  push    rdi
0x18002f907  push    r12
0x18002f909  push    r13
0x18002f90b  push    r14
0x18002f90d  push    r15
0x18002f90f  mov     rbp, rsp
0x18002f912  sub     rsp, 58h
0x18002f916  mov     r13, rcx
0x18002f919  xor     edi, edi
0x18002f91b  mov     [rcx], edi
0x18002f91d  mov     [r9], rdi
0x18002f920  mov     [rdx], edi
0x18002f922  mov     rax, [rbp+arg_20]
0x18002f926  mov     [rax], rdi
0x18002f929  mov     r15, [rbp+arg_30]
0x18002f92d  mov     [r15], edi
0x18002f930  mov     rax, [rbp+arg_38]
0x18002f937  mov     [rax], edi
0x18002f939  mov     rax, [rbp+arg_40]
0x18002f940  mov     [rax], edi
0x18002f942  mov     r12d, edi
0x18002f945  mov     [rbp+var_20], rdi
0x18002f949  mov     dword ptr [rbp+arg_30], edi
0x18002f94c  mov     [rbp+arg_0], edi
0x18002f94f  mov     [rbp+var_28], edi
0x18002f952  call    ?IsOptedIntoCore@PermissionsHelper@Telemetry@Shared@Compat@Windows@@SA_N_N@Z; Windows::Compat::Shared::Telemetry::PermissionsHelper::IsOptedIntoCore(bool)
0x18002f957  test    al, al
0x18002f959  jnz     short loc_18002F983
0x18002f95b  lea     ebx, [rdi+5]
0x18002f95e  mov     dword ptr [rsp+58h+var_38], ebx
0x18002f962  lea     r9, aOnesettingsCor; "Onesettings core telemetry is not allow"...
0x18002f969  mov     r8d, 498h
0x18002f96f  lea     rdx, aPatchdbGetpatc; "PatchDb_GetPatchSdbSettings"
0x18002f976  lea     ecx, [rdi+1]
0x18002f979  call    AslLogCallPrintf
0x18002f97e  jmp     loc_18002FEB3
0x18002f983  mov     rsi, rdi
0x18002f986  mov     ecx, 750h; Size
0x18002f98b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002f990  mov     [rbp+var_18], rax
0x18002f994  test    rax, rax
0x18002f997  jz      short loc_18002F9A6
0x18002f999  mov     rcx, rax; this
0x18002f99c  call    ??0OneSettingsQuery@Telemetry@Base@OneCore@@QEAA@PEBG000@Z; OneCore::Base::Telemetry::OneSettingsQuery::OneSettingsQuery(ushort const *,ushort const *,ushort const *,ushort const *)
0x18002f9a1  mov     r14, rax
0x18002f9a4  jmp     short loc_18002F9A9
0x18002f9a6  mov     r14, rdi
0x18002f9a9  test    r14, r14
0x18002f9ac  jnz     short loc_18002F9D3
0x18002f9ae  lea     ebx, [r14+8]
0x18002f9b2  lea     r9, aFailedToInitia_27; "Failed to initialize onesettings"
0x18002f9b9  mov     r8d, 4A0h
0x18002f9bf  lea     rdx, aPatchdbGetpatc; "PatchDb_GetPatchSdbSettings"
0x18002f9c6  lea     ecx, [rbx-7]
0x18002f9c9  call    AslLogCallPrintf
0x18002f9ce  jmp     loc_18002FE79
0x18002f9d3  mov     rcx, r14; this
0x18002f9d6  call    ?AddParameterOsVer@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJ_N@Z; OneCore::Base::Telemetry::OneSettingsQuery::AddParameterOsVer(bool)
0x18002f9db  mov     ebx, eax
0x18002f9dd  test    eax, eax
0x18002f9df  jns     short loc_18002FA09
0x18002f9e1  and     eax, 1FFF0000h
0x18002f9e6  cmp     eax, 70000h
0x18002f9eb  jnz     short loc_18002F9F0
0x18002f9ed  movzx   ebx, bx
0x18002f9f0  lea     r9, aOnesettingsFai_2; "Onesettings failed to AddParameterOsVer"...
0x18002f9f7  mov     r8d, 4ABh
0x18002f9fd  lea     rdx, aPatchdbGetpatc; "PatchDb_GetPatchSdbSettings"
0x18002fa04  jmp     loc_18002FE5A
0x18002fa09  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18002fa0d  lea     r8, aPatchdbtestone; "PatchDbTestOneSettingsDevice"
0x18002fa14  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002fa1b  mov     r12, 0FFFFFFFF80000002h
0x18002fa22  mov     rcx, r12; hkey
0x18002fa25  call    ?PcaUtilityGetRegistrySTRING@@YAKPEAUHKEY__@@PEBG1PEAPEAG@Z; PcaUtilityGetRegistrySTRING(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18002fa2a  mov     ebx, eax
0x18002fa2c  test    eax, eax
0x18002fa2e  jz      short loc_18002FA7B
0x18002fa30  lea     r9, [rbp+var_20]; unsigned __int16 **
0x18002fa34  lea     r8, aMachineid; "MachineId"
0x18002fa3b  lea     rdx, aSoftwareMicros_7; "SOFTWARE\\Microsoft\\SQMClient"
0x18002fa42  mov     rcx, r12; hkey
0x18002fa45  call    ?PcaUtilityGetRegistrySTRING@@YAKPEAUHKEY__@@PEBG1PEAPEAG@Z; PcaUtilityGetRegistrySTRING(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18002fa4a  mov     ebx, eax
0x18002fa4c  test    eax, eax
0x18002fa4e  jz      short loc_18002FA7B
0x18002fa50  mov     dword ptr [rsp+58h+var_38], eax
0x18002fa54  lea     r9, aOnesettingsFai; "Onesettings failed to get DeviceId from"...
0x18002fa5b  mov     r8d, 4BFh
0x18002fa61  lea     rdx, aPatchdbGetpatc; "PatchDb_GetPatchSdbSettings"
0x18002fa68  mov     ecx, 1
0x18002fa6d  call    AslLogCallPrintf
0x18002fa72  mov     r12, [rbp+var_20]
0x18002fa76  jmp     loc_18002FE68
0x18002fa7b  mov     r12, [rbp+var_20]
0x18002fa7f  mov     [rsp+58h+var_38], r12
0x18002fa84  lea     r9, aOnesettingDevi; "OneSetting DeviceId is [%ws]"
0x18002fa8b  mov     r8d, 4C3h
0x18002fa91  lea     rdi, aPatchdbGetpatc; "PatchDb_GetPatchSdbSettings"
0x18002fa98  mov     rdx, rdi
0x18002fa9b  mov     ecx, 3
0x18002faa0  call    AslLogCallPrintf
0x18002faa5  xor     ecx, ecx
0x18002faa7  test    r12, r12
0x18002faaa  jz      loc_18002FE42
0x18002fab0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002fab4  inc     rax
0x18002fab7  cmp     [r12+rax*2], cx
0x18002fabc  jnz     short loc_18002FAB4
0x18002fabe  test    rax, rax
0x18002fac1  jz      loc_18002FE42
0x18002fac7  lea     rcx, [r14+678h]; this
0x18002face  mov     rax, [rcx+10h]
0x18002fad2  mov     [rsp+58h+var_38], rax; struct _SECURITY_ATTRIBUTES *
0x18002fad7  mov     r9, r12; unsigned __int16 *
0x18002fada  lea     r8, aDeviceid; "deviceid"
0x18002fae1  call    ?Insert@RtlNameValueArray@@QEAAJPEBG00_K@Z; RtlNameValueArray::Insert(ushort const *,ushort const *,ushort const *,unsigned __int64)
0x18002fae6  test    eax, eax
0x18002fae8  jns     short loc_18002FB05
0x18002faea  mov     ecx, eax
0x18002faec  and     ecx, 1FFF0000h
0x18002faf2  cmp     ecx, 70000h
0x18002faf8  jz      loc_18002FE47
0x18002fafe  mov     ebx, eax
0x18002fb00  jmp     loc_18002FE4A
0x18002fb05  xor     r9d, r9d; unsigned int
0x18002fb08  lea     r8, aPatchdbusetest; "PatchDbUseTestOneSettings"
0x18002fb0f  lea     rdx, aSoftwareMicros_6; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002fb16  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x18002fb1d  call    ?PcaUtilityGetRegistryDWORD@@YAKPEAUHKEY__@@PEBG1K@Z; PcaUtilityGetRegistryDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18002fb22  mov     rdx, rdi
0x18002fb25  mov     ecx, 3
0x18002fb2a  test    eax, eax
0x18002fb2c  jz      short loc_18002FB49
0x18002fb2e  lea     r9, aOnesettingsQue; "Onesettings querying PPE server"
0x18002fb35  mov     r8d, 4D5h
0x18002fb3b  call    AslLogCallPrintf
0x18002fb40  lea     rdx, aSettingsPpeDat; "settings-ppe.data.microsoft.com"
0x18002fb47  jmp     short loc_18002FB62
0x18002fb49  lea     r9, aOnesettingsQue_0; "Onesettings querying production server"
0x18002fb50  mov     r8d, 4D9h
0x18002fb56  call    AslLogCallPrintf
0x18002fb5b  lea     rdx, aSettingsWinDat; "settings-win.data.microsoft.com"
0x18002fb62  mov     rcx, r14; this
0x18002fb65  call    ?Query@OneSettingsQuery@Telemetry@Base@OneCore@@QEAAJPEBG_N0PEAU_SECURITY_ATTRIBUTES@@@Z; OneCore::Base::Telemetry::OneSettingsQuery::Query(ushort const *,bool,ushort const *,_SECURITY_ATTRIBUTES *)
0x18002fb6a  mov     ecx, eax
0x18002fb6c  test    eax, eax
0x18002fb6e  jns     short loc_18002FB92
0x18002fb70  and     eax, 1FFF0000h
0x18002fb75  movzx   ebx, cx
0x18002fb78  cmp     eax, 70000h
0x18002fb7d  cmovnz  ebx, ecx
0x18002fb80  lea     r9, aOnesettingsFai_0; "Onesettings failed to Query Onesettings"...
0x18002fb87  mov     r8d, 4DFh
0x18002fb8d  jmp     loc_18002FE57
0x18002fb92  lea     r8, [rbp+arg_30]; unsigned int *
0x18002fb96  lea     rdx, aResetpatchsdb; "ResetPatchSdb"
0x18002fb9d  mov     rcx, r14; this
0x18002fba0  call    ?GetSettingDword@OneSettingsQuery@Telemetry@Base@OneCore@@QEBAJPEBGAEAK@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(ushort const *,ulong &)
0x18002fba5  xor     ecx, ecx
0x18002fba7  test    eax, eax
0x18002fba9  js      short loc_18002FBBF
0x18002fbab  cmp     dword ptr [rbp+arg_30], ecx
0x18002fbae  jz      short loc_18002FBBC
0x18002fbb0  mov     dword ptr [r15], 1
0x18002fbb7  jmp     loc_18002FE68
0x18002fbbc  mov     [r15], ecx
0x18002fbbf  mov     r8, r13; unsigned int *
0x18002fbc2  lea     rdx, aPatchsdbrevisi; "PatchSdbRevision"
0x18002fbc9  mov     rcx, r14; this
0x18002fbcc  call    ?GetSettingDword@OneSettingsQuery@Telemetry@Base@OneCore@@QEBAJPEBGAEAK@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(ushort const *,ulong &)
0x18002fbd1  mov     ebx, eax
0x18002fbd3  xor     r15d, r15d
0x18002fbd6  test    eax, eax
0x18002fbd8  jns     short loc_18002FBFB
0x18002fbda  and     eax, 1FFF0000h
0x18002fbdf  cmp     eax, 70000h
0x18002fbe4  jnz     short loc_18002FBE9
0x18002fbe6  movzx   ebx, bx
0x18002fbe9  lea     r9, aOnesettingFail_4; "Onesetting failed to query app patch re"...
0x18002fbf0  mov     r8d, 4F7h
0x18002fbf6  jmp     loc_18002FE57
0x18002fbfb  mov     ebx, 8
0x18002fc00  cmp     [r13+0], r15d
0x18002fc04  mov     r13d, 1040h
0x18002fc0a  jbe     short loc_18002FC77
0x18002fc0c  mov     rcx, gs:60h
0x18002fc15  mov     r8d, r13d; Size
0x18002fc18  mov     edx, ebx; Flags
0x18002fc1a  mov     rcx, [rcx+30h]; HeapHandle
0x18002fc1e  call    cs:__imp_RtlAllocateHeap
0x18002fc24  mov     rsi, rax
0x18002fc27  test    rax, rax
0x18002fc2a  jz      loc_18002FE68
0x18002fc30  mov     r9d, r13d; unsigned int
0x18002fc33  mov     r8, rax; unsigned __int16 *
0x18002fc36  lea     rdx, aPatchsdblink; "PatchSdbLink"
0x18002fc3d  mov     rcx, r14; this
0x18002fc40  call    ?GetSetting@OneSettingsQuery@Telemetry@Base@OneCore@@QEBAJPEBGPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(ushort const *,ushort *,ulong)
0x18002fc45  test    eax, eax
0x18002fc47  jns     short loc_18002FC70
0x18002fc49  mov     ecx, eax
0x18002fc4b  and     ecx, 1FFF0000h
0x18002fc51  cmp     ecx, 70000h
0x18002fc57  movzx   ebx, ax
0x18002fc5a  jz      short loc_18002FC5E
0x18002fc5c  mov     ebx, eax
0x18002fc5e  lea     r9, aOnesettingFail_3; "Onesetting failed to query app patch li"...
0x18002fc65  mov     r8d, 505h
0x18002fc6b  jmp     loc_18002FE57
0x18002fc70  mov     rax, [rbp+arg_18]
0x18002fc74  mov     [rax], rsi
0x18002fc77  mov     rsi, [rbp+arg_8]
0x18002fc7b  mov     r8, rsi; unsigned int *
0x18002fc7e  lea     rdx, aDrvpatchsdbrev; "DrvPatchSdbRevision"
0x18002fc85  mov     rcx, r14; this
0x18002fc88  call    ?GetSettingDword@OneSettingsQuery@Telemetry@Base@OneCore@@QEBAJPEBGAEAK@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(ushort const *,ulong &)
0x18002fc8d  test    eax, eax
0x18002fc8f  jns     short loc_18002FCCC
0x18002fc91  mov     ecx, eax
0x18002fc93  and     ecx, 1FFF0000h
0x18002fc99  cmp     ecx, 70000h
0x18002fc9f  movzx   ebx, ax
0x18002fca2  jz      short loc_18002FCA6
0x18002fca4  mov     ebx, eax
0x18002fca6  lea     r9, aOnesettingFail_1; "Onesetting failed to query drv patch re"...
0x18002fcad  mov     r8d, 510h
0x18002fcb3  mov     dword ptr [rsp+58h+var_38], ebx
0x18002fcb7  mov     rdx, rdi
0x18002fcba  mov     ecx, 1
0x18002fcbf  call    AslLogCallPrintf
0x18002fcc4  mov     rsi, r15
0x18002fcc7  jmp     loc_18002FE68
0x18002fccc  cmp     [rsi], r15d
0x18002fccf  jbe     short loc_18002FD3C
0x18002fcd1  mov     rcx, gs:60h
0x18002fcda  mov     r8, r13; Size
0x18002fcdd  mov     edx, ebx; Flags
0x18002fcdf  mov     rcx, [rcx+30h]; HeapHandle
0x18002fce3  call    cs:__imp_RtlAllocateHeap
0x18002fce9  mov     rsi, rax
0x18002fcec  test    rax, rax
0x18002fcef  jz      loc_18002FE68
0x18002fcf5  mov     r9d, r13d; unsigned int
0x18002fcf8  mov     r8, rax; unsigned __int16 *
0x18002fcfb  lea     rdx, aDrvpatchsdblin; "DrvPatchSdbLink"
0x18002fd02  mov     rcx, r14; this
0x18002fd05  call    ?GetSetting@OneSettingsQuery@Telemetry@Base@OneCore@@QEBAJPEBGPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(ushort const *,ushort *,ulong)
0x18002fd0a  test    eax, eax
0x18002fd0c  jns     short loc_18002FD35
0x18002fd0e  mov     ecx, eax
0x18002fd10  and     ecx, 1FFF0000h
0x18002fd16  cmp     ecx, 70000h
0x18002fd1c  movzx   ebx, ax
0x18002fd1f  jz      short loc_18002FD23
0x18002fd21  mov     ebx, eax
0x18002fd23  lea     r9, aOnesettingFail_2; "Onesetting failed to query drv patch li"...
0x18002fd2a  mov     r8d, 51Eh
0x18002fd30  jmp     loc_18002FE57
0x18002fd35  mov     rax, [rbp+arg_20]
0x18002fd39  mov     [rax], rsi
0x18002fd3c  mov     rsi, [rbp+arg_10]
0x18002fd40  mov     r8, rsi; unsigned int *
0x18002fd43  lea     rdx, aMergesdbrevisi; "MergeSdbRevision"
0x18002fd4a  mov     rcx, r14; this
0x18002fd4d  call    ?GetSettingDword@OneSettingsQuery@Telemetry@Base@OneCore@@QEBAJPEBGAEAK@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetSettingDword(ushort const *,ulong &)
0x18002fd52  test    eax, eax
0x18002fd54  jns     short loc_18002FD7D
0x18002fd56  mov     ecx, eax
0x18002fd58  and     ecx, 1FFF0000h
0x18002fd5e  cmp     ecx, 70000h
0x18002fd64  movzx   ebx, ax
0x18002fd67  jz      short loc_18002FD6B
0x18002fd69  mov     ebx, eax
0x18002fd6b  lea     r9, aOnesettingFail; "Onesetting failed to query merge SDB re"...
0x18002fd72  mov     r8d, 529h
0x18002fd78  jmp     loc_18002FCB3
0x18002fd7d  cmp     [rsi], r15d
0x18002fd80  jbe     short loc_18002FDE6
0x18002fd82  mov     rcx, gs:60h
0x18002fd8b  mov     r8, r13; Size
0x18002fd8e  mov     edx, ebx; Flags
0x18002fd90  mov     rcx, [rcx+30h]; HeapHandle
0x18002fd94  call    cs:__imp_RtlAllocateHeap
0x18002fd9a  mov     rsi, rax
0x18002fd9d  test    rax, rax
0x18002fda0  jz      loc_18002FE68
0x18002fda6  mov     r9d, r13d; unsigned int
0x18002fda9  mov     r8, rax; unsigned __int16 *
0x18002fdac  lea     rdx, aMergesdblink; "MergeSdbLink"
0x18002fdb3  mov     rcx, r14; this
0x18002fdb6  call    ?GetSetting@OneSettingsQuery@Telemetry@Base@OneCore@@QEBAJPEBGPEAGK@Z; OneCore::Base::Telemetry::OneSettingsQuery::GetSetting(ushort const *,ushort *,ulong)
0x18002fdbb  mov     ebx, eax
0x18002fdbd  test    eax, eax
  ... truncated ...
```
