# MachineInfo::GetTelemetrySettingAuthority(void)

- ea: `0x18003ca20`
- end: `0x18003cafc`
- name: `?GetTelemetrySettingAuthority@MachineInfo@@AEBAIXZ`
- size: `220`
- prototype: `unsigned int __fastcall(MachineInfo *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18002a690`
- `0x18003ca20`
- `0x18003dc00`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003caa5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003caa5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cae9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003cae9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cac4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cac4`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x18003ca4e`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x18003ca4e`

## string_xrefs

- `0x18003ca9e`: `DiagnosticDataSettings.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MachineInfo::GetTelemetrySettingAuthority(MachineInfo *this)
{
  char IsEnabled; // al
  unsigned __int16 v2; // r8
  int active; // eax
  HMODULE Library; // rax
  HMODULE v6; // rbx
  FARPROC ProcAddress; // rax
  unsigned int v8; // edi
  unsigned int v9; // [rsp+48h] [rbp+10h] BYREF
  int v10; // [rsp+50h] [rbp+18h] BYREF
  HMODULE v11; // [rsp+58h] [rbp+20h]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::GetImpl'::`2'::impl);
  v10 = 0;
  v9 = 0;
  if ( IsEnabled )
  {
    active = TelEvaluateActiveSettingAuthority(&v10, &v9);
    if ( active >= 0 )
      return v9;
    AslLogCallPrintf(
      1,
      "MachineInfo::GetTelemetrySettingAuthority",
      807,
      "TelEvaluateActiveSettingAuthority failed [%#x]",
      active);
    return 0xFFFFFFFFLL;
  }
  if ( !IsWindowsVersionOrGreater(0xAu, 0, v2) )
    return 0xFFFFFFFFLL;
  Library = LoadLibraryExW(L"DiagnosticDataSettings.dll", 0, 0x800u);
  v6 = Library;
  v11 = Library;
  if ( !Library )
    return 0xFFFFFFFFLL;
  ProcAddress = GetProcAddress(Library, "TelEvaluateActiveSettingAuthority");
  if ( ((int (__fastcall *)(int *, unsigned int *))ProcAddress)(&v10, &v9) >= 0 )
    v8 = v9;
  else
    v8 = -1;
  FreeLibrary(v6);
  return v8;
}

```

## disassembly

```asm
0x18003ca20  mov     [rsp+arg_0], rbx
0x18003ca25  push    rdi
0x18003ca26  sub     rsp, 30h
0x18003ca2a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel> `wil::Feature<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::GetImpl(void)'::`2'::impl
0x18003ca31  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::__private_IsEnabled(void)
0x18003ca36  xor     edi, edi
0x18003ca38  mov     [rsp+38h+arg_10], edi
0x18003ca3c  mov     [rsp+38h+arg_8], edi
0x18003ca40  test    al, al
0x18003ca42  jz      short loc_18003CA88
0x18003ca44  lea     rdx, [rsp+38h+arg_8]
0x18003ca49  lea     rcx, [rsp+38h+arg_10]
0x18003ca4e  call    cs:__imp_TelEvaluateActiveSettingAuthority
0x18003ca54  test    eax, eax
0x18003ca56  js      short loc_18003CA61
0x18003ca58  mov     eax, [rsp+38h+arg_8]
0x18003ca5c  jmp     loc_18003CAF1
0x18003ca61  mov     [rsp+38h+var_18], eax
0x18003ca65  lea     r9, aTelevaluateact_0; "TelEvaluateActiveSettingAuthority faile"...
0x18003ca6c  mov     r8d, 327h
0x18003ca72  lea     rdx, aMachineinfoGet; "MachineInfo::GetTelemetrySettingAuthori"...
0x18003ca79  mov     ecx, 1
0x18003ca7e  call    AslLogCallPrintf
0x18003ca83  or      eax, 0FFFFFFFFh
0x18003ca86  jmp     short loc_18003CAF1
0x18003ca88  xor     edx, edx; unsigned __int16
0x18003ca8a  lea     ecx, [rdx+0Ah]; unsigned __int16
0x18003ca8d  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x18003ca92  test    al, al
0x18003ca94  jz      short loc_18003CA83
0x18003ca96  xor     edx, edx; hFile
0x18003ca98  mov     r8d, 800h; dwFlags
0x18003ca9e  lea     rcx, aDiagnosticdata_1; "DiagnosticDataSettings.dll"
0x18003caa5  call    cs:__imp_LoadLibraryExW
0x18003caab  mov     rbx, rax
0x18003caae  mov     [rsp+38h+arg_18], rax
0x18003cab3  test    rax, rax
0x18003cab6  jnz     short loc_18003CABA
0x18003cab8  jmp     short loc_18003CA83
0x18003caba  lea     rdx, aTelevaluateact_1; "TelEvaluateActiveSettingAuthority"
0x18003cac1  mov     rcx, rbx; hModule
0x18003cac4  call    cs:__imp_GetProcAddress
0x18003caca  lea     rdx, [rsp+38h+arg_8]
0x18003cacf  lea     rcx, [rsp+38h+arg_10]
0x18003cad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cad9  test    eax, eax
0x18003cadb  jns     short loc_18003CAE2
0x18003cadd  or      edi, 0FFFFFFFFh
0x18003cae0  jmp     short loc_18003CAE6
0x18003cae2  mov     edi, [rsp+38h+arg_8]
0x18003cae6  mov     rcx, rbx; hLibModule
0x18003cae9  call    cs:__imp_FreeLibrary
0x18003caef  mov     eax, edi
0x18003caf1  mov     rbx, [rsp+38h+arg_0]
0x18003caf6  add     rsp, 30h
0x18003cafa  pop     rdi
0x18003cafb  retn
```
