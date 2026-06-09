# ReadLocationPrivacySetting(int,int *)

- ea: `0x180098df0`
- end: `0x1800991bd`
- name: `?ReadLocationPrivacySetting@@YAJHPEAH@Z`
- size: `973`
- prototype: `__int64 __fastcall(int, int *)`
- caller_count: `2`
- callee_count: `13`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180098c00`
- `0x18009923c`

## callees

- `0x180003470`
- `0x18000395c`
- `0x180008524`
- `0x180008544`
- `0x180019140`
- `0x18001ad08`
- `0x180031ff0`
- `0x180040898`
- `0x180042068`
- `0x180046450`
- `0x180094c9c`
- `0x180098df0`
- `0x1800c4010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009904d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18009904d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180098f23`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x180098f23`

## string_xrefs

- `0x180098f04`: `Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager`
- `0x180098e5f`: `Software\Microsoft\Windows\PrivacySettingsBeforeCreatorsUpdate\LocationPlatform`
- `0x180098e82`: `Software\Microsoft\Windows\PrivacySettingsBeforeCreatorsUpdate\SensorPermission`
- `0x180098ea0`: `Software\Microsoft\Windows\PrivacySettingsBeforeCreatorsUpdate\SensorPermission`
- `0x180098e26`: `shell\oobe\machine\plugins\adapters\inc\OobePrivacyHelpers.h`
- `0x180098f36`: `shell\oobe\machine\plugins\adapters\inc\OobePrivacyHelpers.h`
- `0x180098f90`: `shell\oobe\machine\plugins\adapters\inc\OobePrivacyHelpers.h`
- `0x180098fcd`: `shell\oobe\machine\plugins\adapters\inc\OobePrivacyHelpers.h`
- `0x180099066`: `shell\oobe\machine\plugins\adapters\inc\OobePrivacyHelpers.h`
- `0x180099107`: `shell\oobe\machine\plugins\adapters\inc\OobePrivacyHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall ReadLocationPrivacySetting(int a1, int *a2)
{
  unsigned int LastError; // ebx
  __int64 v4; // rdx
  int DWORD; // ebx
  int v7; // r14d
  int v8; // eax
  int v9; // edi
  bool v10; // zf
  int ActivationFactory; // eax
  char v12; // r8
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, PVOID, __int64 **); // rbx
  HSTRING_HEADER *v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rdx
  int v21; // edi
  BOOL v22; // ebx
  char v23; // r8
  const char *v24; // r9
  __int64 *v25; // rbx
  __int64 (__fastcall *v26)(__int64 *, PVOID, unsigned int *); // r14
  __int64 v27; // rcx
  HSTRING_HEADER *v28; // rax
  int v29; // eax
  __int64 v30; // rdx
  void *v31; // rcx
  void *v32; // rcx
  unsigned int v33[2]; // [rsp+20h] [rbp-39h] BYREF
  unsigned int v34; // [rsp+28h] [rbp-31h] BYREF
  unsigned int v35; // [rsp+2Ch] [rbp-2Dh] BYREF
  __int64 *v36; // [rsp+30h] [rbp-29h] BYREF
  void *Block; // [rsp+38h] [rbp-21h] BYREF
  const WCHAR *v38; // [rsp+40h] [rbp-19h] BYREF
  __int64 v39; // [rsp+48h] [rbp-11h] BYREF
  const WCHAR *v40; // [rsp+50h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-1h] BYREF
  __int64 v42; // [rsp+70h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  if ( !a2 )
  {
    LastError = -2147024809;
    v4 = 119;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\OobePrivacyHelpers.h",
      (const char *)LastError,
      v33[0]);
    return LastError;
  }
  if ( !a1 )
  {
    v39 = 0;
    v42 = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      &hstringHeader,
      L"Windows.Internal.CapabilityAccess.Management.CapabilityConsentManager",
      0x46u,
      0x45u);
    ActivationFactory = RoGetActivationFactory(v42, &GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e, &v39);
    LastError = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\OobePrivacyHelpers.h",
        (const char *)(unsigned int)ActivationFactory,
        v33[0]);
LABEL_44:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v39);
      return LastError;
    }
    v36 = 0;
    v13 = v39;
    v14 = *(__int64 (__fastcall **)(__int64, PVOID, __int64 **))(*(_QWORD *)v39 + 48LL);
    v36 = 0;
    v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
            &hstringHeader,
            (const WCHAR **)&c_szCapabilityLocation,
            v12);
    v16 = v14(v13, v15[1].Reserved.Reserved1, &v36);
    LastError = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA6,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\OobePrivacyHelpers.h",
        (const char *)(unsigned int)v16,
        v33[0]);
LABEL_43:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v36);
      goto LABEL_44;
    }
    *(_QWORD *)v33 = 0;
    v17 = *v36;
    *(_QWORD *)v33 = 0;
    v18 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(v17 + 48))(v36, v33);
    LastError = v18;
    if ( v18 < 0 )
    {
      v19 = 169;
LABEL_24:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v19,
        (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\OobePrivacyHelpers.h",
        (const char *)(unsigned int)v18,
        v33[0]);
LABEL_42:
      wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v33);
      goto LABEL_43;
    }
    v34 = 2;
    if ( !*(_QWORD *)v33 )
      goto LABEL_50;
    v18 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v33 + 88LL))(*(_QWORD *)v33, &v34);
    LastError = v18;
    if ( v18 < 0 )
    {
      v19 = 176;
      goto LABEL_24;
    }
    v21 = 1;
    if ( v34 == 1 )
    {
      v38 = 0;
      wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, v20);
      hstringHeader.Reserved.Reserved1 = &v38;
      *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = 0;
      hstringHeader.Reserved.Reserved2[16] = 1;
      v22 = ConvertSidToStringSidW(*(PSID *)Block, (LPWSTR *)&hstringHeader.Reserved.Reserved2[8]);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(&hstringHeader);
      if ( !v22 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xB8,
                      (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\OobePrivacyHelpers.h",
                      v24);
LABEL_39:
        v31 = Block;
        Block = 0;
        if ( v31 )
          operator delete(v31);
        wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(&v38);
        goto LABEL_42;
      }
      v25 = v36;
      v26 = *(__int64 (__fastcall **)(__int64 *, PVOID, unsigned int *))(*v36 + 56);
      v27 = *(_QWORD *)v33;
      *(_QWORD *)v33 = 0;
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v40 = v38;
      v28 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&hstringHeader, &v40, v23);
      v29 = v26(v25, v28[1].Reserved.Reserved1, v33);
      LastError = v29;
      if ( v29 < 0 )
      {
        v30 = 185;
LABEL_38:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v30,
          (unsigned int)"shell\\oobe\\machine\\plugins\\adapters\\inc\\OobePrivacyHelpers.h",
          (const char *)(unsigned int)v29,
          v33[0]);
        goto LABEL_39;
      }
      v35 = 2;
      if ( !*(_QWORD *)v33 )
        goto LABEL_46;
      v29 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**(_QWORD **)v33 + 88LL))(*(_QWORD *)v33, &v35);
      LastError = v29;
      if ( v29 < 0 )
      {
        v30 = 192;
        goto LABEL_38;
      }
      if ( v35 != 1 )
LABEL_46:
        v21 = 0;
      *a2 = v21;
      v32 = Block;
      Block = 0;
      if ( v32 )
        operator delete(v32);
      wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(&v38);
    }
    else
    {
LABEL_50:
      *a2 = 0;
    }
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(v33);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v36);
    wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(&v39);
    return 0;
  }
  v33[0] = 0;
  v35 = 0;
  v34 = 0;
  DWORD = SHRegGetDWORD(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows\\PrivacySettingsBeforeCreatorsUpdate\\LocationPlatform",
            L"Status",
            v33);
  v7 = SHRegGetDWORD(
         HKEY_CURRENT_USER,
         L"Software\\Microsoft\\Windows\\PrivacySettingsBeforeCreatorsUpdate\\SensorPermission",
         L"SensorPermissionState",
         &v35);
  v8 = SHRegGetDWORD(
         HKEY_LOCAL_MACHINE,
         L"Software\\Microsoft\\Windows\\PrivacySettingsBeforeCreatorsUpdate\\SensorPermission",
         L"SensorPermissionState",
         &v34);
  if ( DWORD < 0 )
  {
    if ( v7 < 0 && v8 < 0 )
    {
      LastError = -2147467260;
      v4 = 143;
      goto LABEL_3;
    }
    goto LABEL_16;
  }
  v9 = 1;
  if ( v33[0] != 1 )
    goto LABEL_16;
  if ( v7 >= 0 )
  {
    v10 = v35 == 1;
    goto LABEL_15;
  }
  if ( v8 < 0 )
  {
LABEL_16:
    v9 = 0;
    goto LABEL_17;
  }
  v10 = v34 == 1;
LABEL_15:
  if ( !v10 )
    goto LABEL_16;
LABEL_17:
  *a2 = v9;
  return 0;
}

```

## disassembly

```asm
0x180098df0  push    rbp
0x180098df2  push    rbx
0x180098df3  push    rsi
0x180098df4  push    rdi
0x180098df5  push    r14
0x180098df7  push    r15
0x180098df9  lea     rbp, [rsp-2Fh]
0x180098dfe  sub     rsp, 88h
0x180098e05  mov     rax, cs:__security_cookie
0x180098e0c  xor     rax, rsp
0x180098e0f  mov     [rbp+57h+var_38], rax
0x180098e13  mov     rsi, rdx
0x180098e16  xor     r15d, r15d
0x180098e19  test    rdx, rdx
0x180098e1c  jnz     short loc_180098E40
0x180098e1e  mov     ebx, 80070057h
0x180098e23  lea     edx, [rsi+77h]; void *
0x180098e26  lea     r8, aShellOobeMachi_39; "shell\\oobe\\machine\\plugins\\adapters"...
0x180098e2d  mov     r9d, ebx; char *
0x180098e30  mov     rcx, [rbp+5Fh]; this
0x180098e34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098e39  mov     eax, ebx
0x180098e3b  jmp     loc_1800991A1
0x180098e40  test    ecx, ecx
0x180098e42  jz      loc_180098EF2
0x180098e48  mov     [rbp+57h+var_90], r15d
0x180098e4c  mov     [rbp+57h+var_84], r15d
0x180098e50  mov     [rbp+57h+var_88], r15d
0x180098e54  lea     r9, [rbp+57h+var_90]; unsigned int *
0x180098e58  lea     r8, aStatus; "Status"
0x180098e5f  lea     rdx, aSoftwareMicros_37; "Software\\Microsoft\\Windows\\PrivacySe"...
0x180098e66  mov     rdi, 0FFFFFFFF80000002h
0x180098e6d  mov     rcx, rdi; HKEY
0x180098e70  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180098e75  mov     ebx, eax
0x180098e77  lea     r9, [rbp+57h+var_84]; unsigned int *
0x180098e7b  lea     r8, aSensorpermissi; "SensorPermissionState"
0x180098e82  lea     rdx, aSoftwareMicros_23; "Software\\Microsoft\\Windows\\PrivacySe"...
0x180098e89  lea     rcx, [rdi-1]; HKEY
0x180098e8d  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180098e92  mov     r14d, eax
0x180098e95  lea     r9, [rbp+57h+var_88]; unsigned int *
0x180098e99  lea     r8, aSensorpermissi; "SensorPermissionState"
0x180098ea0  lea     rdx, aSoftwareMicros_23; "Software\\Microsoft\\Windows\\PrivacySe"...
0x180098ea7  mov     rcx, rdi; HKEY
0x180098eaa  call    ?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z; SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)
0x180098eaf  test    ebx, ebx
0x180098eb1  jns     short loc_180098ECB
0x180098eb3  test    r14d, r14d
0x180098eb6  jns     short loc_180098EE8
0x180098eb8  test    eax, eax
0x180098eba  jns     short loc_180098EE8
0x180098ebc  mov     ebx, 80004004h
0x180098ec1  mov     edx, 8Fh
0x180098ec6  jmp     loc_180098E26
0x180098ecb  mov     edi, 1
0x180098ed0  cmp     [rbp+57h+var_90], edi
0x180098ed3  jnz     short loc_180098EE8
0x180098ed5  test    r14d, r14d
0x180098ed8  js      short loc_180098EDF
0x180098eda  cmp     [rbp+57h+var_84], edi
0x180098edd  jmp     short loc_180098EE6
0x180098edf  test    eax, eax
0x180098ee1  js      short loc_180098EE8
0x180098ee3  cmp     [rbp+57h+var_88], edi
0x180098ee6  jz      short loc_180098EEB
0x180098ee8  mov     edi, r15d
0x180098eeb  mov     [rsi], edi
0x180098eed  jmp     loc_18009919F
0x180098ef2  mov     [rbp+57h+var_68], r15
0x180098ef6  mov     [rbp+57h+var_40], r15
0x180098efa  mov     r9d, 45h ; 'E'; unsigned int
0x180098f00  lea     r8d, [r9+1]; unsigned int
0x180098f04  lea     rdx, ?RuntimeClass_Windows_Internal_CapabilityAccess_Management_CapabilityConsentManager@@3QBGB; "Windows.Internal.CapabilityAccess.Manag"...
0x180098f0b  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180098f0f  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180098f14  lea     r8, [rbp+57h+var_68]
0x180098f18  lea     rdx, _GUID_ef1a89c8_29b1_4ab0_94a7_851b33527a2e
0x180098f1f  mov     rcx, [rbp+57h+var_40]
0x180098f23  call    cs:__imp_RoGetActivationFactory
0x180098f29  mov     ebx, eax
0x180098f2b  test    eax, eax
0x180098f2d  jns     short loc_180098F4C
0x180098f2f  mov     rcx, [rbp+5Fh]; this
0x180098f33  mov     r9d, eax; char *
0x180098f36  lea     r8, aShellOobeMachi_39; "shell\\oobe\\machine\\plugins\\adapters"...
0x180098f3d  mov     edx, 0A3h; void *
0x180098f42  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098f47  jmp     loc_180099149
0x180098f4c  mov     [rbp+57h+var_80], r15
0x180098f50  mov     rdi, [rbp+57h+var_68]
0x180098f54  mov     rax, [rdi]
0x180098f57  mov     rbx, [rax+30h]
0x180098f5b  mov     [rbp+57h+var_80], r15
0x180098f5f  lea     rdx, ?c_szCapabilityLocation@@3QEBGEB; ushort const * const c_szCapabilityLocation
0x180098f66  lea     rcx, [rbp+57h+hstringHeader]
0x180098f6a  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x180098f6f  nop
0x180098f70  lea     r8, [rbp+57h+var_80]
0x180098f74  mov     rdx, [rax+18h]
0x180098f78  mov     rcx, rdi
0x180098f7b  mov     rax, rbx
0x180098f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098f83  mov     ebx, eax
0x180098f85  test    eax, eax
0x180098f87  jns     short loc_180098FA6
0x180098f89  mov     rcx, [rbp+5Fh]; this
0x180098f8d  mov     r9d, eax; char *
0x180098f90  lea     r8, aShellOobeMachi_39; "shell\\oobe\\machine\\plugins\\adapters"...
0x180098f97  mov     edx, 0A6h; void *
0x180098f9c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098fa1  jmp     loc_18009913F
0x180098fa6  mov     qword ptr [rbp+57h+var_90], r15
0x180098faa  mov     rcx, [rbp+57h+var_80]
0x180098fae  mov     rax, [rcx]
0x180098fb1  mov     qword ptr [rbp+57h+var_90], r15
0x180098fb5  lea     rdx, [rbp+57h+var_90]
0x180098fb9  mov     rax, [rax+30h]
0x180098fbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180098fc2  mov     ebx, eax
0x180098fc4  test    eax, eax
0x180098fc6  jns     short loc_180098FE5
0x180098fc8  mov     edx, 0A9h; void *
0x180098fcd  lea     r8, aShellOobeMachi_39; "shell\\oobe\\machine\\plugins\\adapters"...
0x180098fd4  mov     r9d, eax; char *
0x180098fd7  mov     rcx, [rbp+5Fh]; this
0x180098fdb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180098fe0  jmp     loc_180099135
0x180098fe5  mov     [rbp+57h+var_88], 2
0x180098fec  mov     rcx, qword ptr [rbp+57h+var_90]
0x180098ff0  test    rcx, rcx
0x180098ff3  jz      loc_18009917F
0x180098ff9  mov     rax, [rcx]
0x180098ffc  lea     rdx, [rbp+57h+var_88]
0x180099000  mov     rax, [rax+58h]
0x180099004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099009  mov     ebx, eax
0x18009900b  test    eax, eax
0x18009900d  jns     short loc_180099016
0x18009900f  mov     edx, 0B0h
0x180099014  jmp     short loc_180098FCD
0x180099016  mov     edi, 1
0x18009901b  cmp     [rbp+57h+var_88], edi
0x18009901e  jnz     loc_18009917F
0x180099024  mov     [rbp+57h+var_70], r15
0x180099028  lea     rcx, [rbp+57h+Block]
0x18009902c  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x180099031  nop
0x180099032  lea     rax, [rbp+57h+var_70]
0x180099036  mov     qword ptr [rbp+57h+hstringHeader.Reserved], rax
0x18009903a  mov     qword ptr [rbp+57h+hstringHeader.Reserved+8], r15
0x18009903e  mov     byte ptr [rbp+57h+hstringHeader.Reserved+10h], dil
0x180099042  lea     rdx, [rbp+57h+hstringHeader.Reserved+8]; StringSid
0x180099046  mov     rcx, [rbp+57h+Block]
0x18009904a  mov     rcx, [rcx]; Sid
0x18009904d  call    cs:__imp_ConvertSidToStringSidW
0x180099053  mov     ebx, eax
0x180099055  lea     rcx, [rbp+57h+hstringHeader]
0x180099059  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18009905e  test    ebx, ebx
0x180099060  jnz     short loc_18009907E
0x180099062  mov     rcx, [rbp+5Fh]; this
0x180099066  lea     r8, aShellOobeMachi_39; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009906d  mov     edx, 0B8h; void *
0x180099072  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180099077  mov     ebx, eax
0x180099079  jmp     loc_180099118
0x18009907e  mov     rbx, [rbp+57h+var_80]
0x180099082  mov     rax, [rbx]
0x180099085  mov     r14, [rax+38h]
0x180099089  mov     rcx, qword ptr [rbp+57h+var_90]
0x18009908d  mov     qword ptr [rbp+57h+var_90], r15
0x180099091  test    rcx, rcx
0x180099094  jz      short loc_1800990A3
0x180099096  mov     rax, [rcx]
0x180099099  mov     rax, [rax+10h]
0x18009909d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800990a2  nop
0x1800990a3  mov     rdx, [rbp+57h+var_70]
0x1800990a7  mov     [rbp+57h+var_60], rdx
0x1800990ab  lea     rdx, [rbp+57h+var_60]
0x1800990af  lea     rcx, [rbp+57h+hstringHeader]
0x1800990b3  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800990b8  nop
0x1800990b9  lea     r8, [rbp+57h+var_90]
0x1800990bd  mov     rdx, [rax+18h]
0x1800990c1  mov     rcx, rbx
0x1800990c4  mov     rax, r14
0x1800990c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800990cc  mov     ebx, eax
0x1800990ce  test    eax, eax
0x1800990d0  jns     short loc_1800990D9
0x1800990d2  mov     edx, 0B9h
0x1800990d7  jmp     short loc_180099104
0x1800990d9  mov     [rbp+57h+var_84], 2
0x1800990e0  mov     rcx, qword ptr [rbp+57h+var_90]
0x1800990e4  test    rcx, rcx
0x1800990e7  jz      short loc_18009915C
0x1800990e9  mov     rax, [rcx]
0x1800990ec  lea     rdx, [rbp+57h+var_84]
0x1800990f0  mov     rax, [rax+58h]
0x1800990f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800990f9  mov     ebx, eax
0x1800990fb  test    eax, eax
0x1800990fd  jns     short loc_180099157
0x1800990ff  mov     edx, 0C0h; void *
0x180099104  mov     r9d, eax; char *
0x180099107  lea     r8, aShellOobeMachi_39; "shell\\oobe\\machine\\plugins\\adapters"...
0x18009910e  mov     rcx, [rbp+5Fh]; this
0x180099112  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180099117  nop
0x180099118  mov     rcx, [rbp+57h+Block]; Block
0x18009911c  mov     [rbp+57h+Block], r15
0x180099120  test    rcx, rcx
0x180099123  jz      short loc_18009912B
0x180099125  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18009912a  nop
0x18009912b  lea     rcx, [rbp+57h+var_70]
0x18009912f  call    ??1?$unique_storage@U?$resource_policy@PEAU_STORAGE_DEVICE_DESCRIPTOR@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x180099134  nop
0x180099135  lea     rcx, [rbp+57h+var_90]
0x180099139  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18009913e  nop
0x18009913f  lea     rcx, [rbp+57h+var_80]
0x180099143  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180099148  nop
0x180099149  lea     rcx, [rbp+57h+var_68]
0x18009914d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180099152  jmp     loc_180098E39
0x180099157  cmp     [rbp+57h+var_84], edi
0x18009915a  jz      short loc_18009915F
0x18009915c  mov     edi, r15d
0x18009915f  mov     [rsi], edi
0x180099161  mov     rcx, [rbp+57h+Block]; Block
0x180099165  mov     [rbp+57h+Block], r15
0x180099169  test    rcx, rcx
0x18009916c  jz      short loc_180099174
0x18009916e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180099173  nop
0x180099174  lea     rcx, [rbp+57h+var_70]
0x180099178  call    ??1?$unique_storage@U?$resource_policy@PEAU_STORAGE_DEVICE_DESCRIPTOR@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_STORAGE_DEVICE_DESCRIPTOR *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,_STORAGE_DEVICE_DESCRIPTOR *,_STORAGE_DEVICE_DESCRIPTOR *,0,std::nullptr_t>>(void)
0x18009917d  jmp     short loc_180099182
0x18009917f  mov     [rsi], r15d
0x180099182  lea     rcx, [rbp+57h+var_90]
0x180099186  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18009918b  nop
0x18009918c  lea     rcx, [rbp+57h+var_80]
0x180099190  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180099195  nop
0x180099196  lea     rcx, [rbp+57h+var_68]
0x18009919a  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x18009919f  xor     eax, eax
0x1800991a1  mov     rcx, [rbp+57h+var_38]
0x1800991a5  xor     rcx, rsp; StackCookie
0x1800991a8  call    __security_check_cookie
0x1800991ad  add     rsp, 88h
0x1800991b4  pop     r15
0x1800991b6  pop     r14
0x1800991b8  pop     rdi
0x1800991b9  pop     rsi
0x1800991ba  pop     rbx
0x1800991bb  pop     rbp
0x1800991bc  retn
```
