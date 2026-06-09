# CMachineInfoV2::GetTelemetrySettingAuthority(void)

- ea: `0x1800b0a90`
- end: `0x1800b0b6c`
- name: `?GetTelemetrySettingAuthority@CMachineInfoV2@@QEBAIXZ`
- size: `220`
- prototype: `unsigned int __fastcall(CMachineInfoV2 *__hidden this)`
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callees

- `0x18002a690`
- `0x18003dc00`
- `0x1800b0a90`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0b15`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0b15`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0b59`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0b59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0b34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0b34`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x1800b0abe`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x1800b0abe`

## string_xrefs

- `0x1800b0b0e`: `DiagnosticDataSettings.dll`

## pseudocode

```c
__int64 __fastcall CMachineInfoV2::GetTelemetrySettingAuthority(CMachineInfoV2 *this)
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
      "CMachineInfoV2::GetTelemetrySettingAuthority",
      822,
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
0x1800b0a90  mov     [rsp+arg_0], rbx
0x1800b0a95  push    rdi
0x1800b0a96  sub     rsp, 30h
0x1800b0a9a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel> `wil::Feature<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::GetImpl(void)'::`2'::impl
0x1800b0aa1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::__private_IsEnabled(void)
0x1800b0aa6  xor     edi, edi
0x1800b0aa8  mov     [rsp+38h+arg_10], edi
0x1800b0aac  mov     [rsp+38h+arg_8], edi
0x1800b0ab0  test    al, al
0x1800b0ab2  jz      short loc_1800B0AF8
0x1800b0ab4  lea     rdx, [rsp+38h+arg_8]
0x1800b0ab9  lea     rcx, [rsp+38h+arg_10]
0x1800b0abe  call    cs:__imp_TelEvaluateActiveSettingAuthority
0x1800b0ac4  test    eax, eax
0x1800b0ac6  js      short loc_1800B0AD1
0x1800b0ac8  mov     eax, [rsp+38h+arg_8]
0x1800b0acc  jmp     loc_1800B0B61
0x1800b0ad1  mov     [rsp+38h+var_18], eax
0x1800b0ad5  lea     r9, aTelevaluateact_0; "TelEvaluateActiveSettingAuthority faile"...
0x1800b0adc  mov     r8d, 336h
0x1800b0ae2  lea     rdx, aCmachineinfov2; "CMachineInfoV2::GetTelemetrySettingAuth"...
0x1800b0ae9  mov     ecx, 1
0x1800b0aee  call    AslLogCallPrintf
0x1800b0af3  or      eax, 0FFFFFFFFh
0x1800b0af6  jmp     short loc_1800B0B61
0x1800b0af8  xor     edx, edx; unsigned __int16
0x1800b0afa  lea     ecx, [rdx+0Ah]; unsigned __int16
0x1800b0afd  call    ?IsWindowsVersionOrGreater@@YA_NGGG@Z; IsWindowsVersionOrGreater(ushort,ushort,ushort)
0x1800b0b02  test    al, al
0x1800b0b04  jz      short loc_1800B0AF3
0x1800b0b06  xor     edx, edx; hFile
0x1800b0b08  mov     r8d, 800h; dwFlags
0x1800b0b0e  lea     rcx, aDiagnosticdata_1; "DiagnosticDataSettings.dll"
0x1800b0b15  call    cs:__imp_LoadLibraryExW
0x1800b0b1b  mov     rbx, rax
0x1800b0b1e  mov     [rsp+38h+arg_18], rax
0x1800b0b23  test    rax, rax
0x1800b0b26  jnz     short loc_1800B0B2A
0x1800b0b28  jmp     short loc_1800B0AF3
0x1800b0b2a  lea     rdx, aTelevaluateact_1; "TelEvaluateActiveSettingAuthority"
0x1800b0b31  mov     rcx, rbx; hModule
0x1800b0b34  call    cs:__imp_GetProcAddress
0x1800b0b3a  lea     rdx, [rsp+38h+arg_8]
0x1800b0b3f  lea     rcx, [rsp+38h+arg_10]
0x1800b0b44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0b49  test    eax, eax
0x1800b0b4b  jns     short loc_1800B0B52
0x1800b0b4d  or      edi, 0FFFFFFFFh
0x1800b0b50  jmp     short loc_1800B0B56
0x1800b0b52  mov     edi, [rsp+38h+arg_8]
0x1800b0b56  mov     rcx, rbx; hLibModule
0x1800b0b59  call    cs:__imp_FreeLibrary
0x1800b0b5f  mov     eax, edi
0x1800b0b61  mov     rbx, [rsp+38h+arg_0]
0x1800b0b66  add     rsp, 30h
0x1800b0b6a  pop     rdi
0x1800b0b6b  retn
```
