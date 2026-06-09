# CMachineInfoV2::GetTelemetryLevel(void)

- ea: `0x1800b09c0`
- end: `0x1800b0a81`
- name: `?GetTelemetryLevel@CMachineInfoV2@@QEBAIXZ`
- size: `193`
- prototype: `unsigned int __fastcall(CMachineInfoV2 *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18003dc00`
- `0x1800b09c0`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0a2d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b0a2d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0a6e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800b0a6e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a4f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800b0a4f`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x1800b09e9`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x1800b09e9`

## string_xrefs

- `0x1800b0a26`: `AEPIC.dll`

## pseudocode

```c
__int64 __fastcall CMachineInfoV2::GetTelemetryLevel(CMachineInfoV2 *this)
{
  char IsEnabled; // al
  int active; // eax
  HMODULE Library; // rax
  HMODULE v5; // rbx
  unsigned int v6; // edi
  FARPROC ProcAddress; // rax
  unsigned int v8; // [rsp+48h] [rbp+10h] BYREF
  HMODULE v9; // [rsp+50h] [rbp+18h]

  IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::GetImpl'::`2'::impl);
  v8 = 0;
  if ( IsEnabled )
  {
    active = TelEvaluateActiveSettingAuthority(&v8, 0);
    if ( active >= 0 )
      return v8;
    AslLogCallPrintf(
      1,
      "CMachineInfoV2::GetTelemetryLevel",
      783,
      "TelEvaluateActiveSettingAuthority failed [%#x]",
      active);
    return 0xFFFFFFFFLL;
  }
  Library = LoadLibraryExW(L"AEPIC.dll", 0, 0x800u);
  v5 = Library;
  v9 = Library;
  if ( !Library )
    return 0xFFFFFFFFLL;
  v6 = -1;
  ProcAddress = GetProcAddress(Library, "GetPrivacyLevel");
  if ( ProcAddress )
  {
    if ( ((int (__fastcall *)(unsigned int *))ProcAddress)(&v8) >= 0 )
      v6 = v8;
  }
  FreeLibrary(v5);
  return v6;
}

```

## disassembly

```asm
0x1800b09c0  mov     [rsp+arg_0], rbx
0x1800b09c5  push    rdi
0x1800b09c6  sub     rsp, 30h
0x1800b09ca  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel> `wil::Feature<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::GetImpl(void)'::`2'::impl
0x1800b09d1  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::__private_IsEnabled(void)
0x1800b09d6  mov     [rsp+38h+arg_8], 0
0x1800b09de  xor     edx, edx; hFile
0x1800b09e0  test    al, al
0x1800b09e2  jz      short loc_1800B0A20
0x1800b09e4  lea     rcx, [rsp+38h+arg_8]
0x1800b09e9  call    cs:__imp_TelEvaluateActiveSettingAuthority
0x1800b09ef  test    eax, eax
0x1800b09f1  js      short loc_1800B09F9
0x1800b09f3  mov     eax, [rsp+38h+arg_8]
0x1800b09f7  jmp     short loc_1800B0A76
0x1800b09f9  mov     [rsp+38h+var_18], eax
0x1800b09fd  lea     r9, aTelevaluateact_0; "TelEvaluateActiveSettingAuthority faile"...
0x1800b0a04  mov     r8d, 30Fh
0x1800b0a0a  lea     rdx, aCmachineinfov2_0; "CMachineInfoV2::GetTelemetryLevel"
0x1800b0a11  mov     ecx, 1
0x1800b0a16  call    AslLogCallPrintf
0x1800b0a1b  or      eax, 0FFFFFFFFh
0x1800b0a1e  jmp     short loc_1800B0A76
0x1800b0a20  mov     r8d, 800h; dwFlags
0x1800b0a26  lea     rcx, aAepicDll_1; "AEPIC.dll"
0x1800b0a2d  call    cs:__imp_LoadLibraryExW
0x1800b0a33  mov     rbx, rax
0x1800b0a36  mov     [rsp+38h+arg_10], rax
0x1800b0a3b  test    rax, rax
0x1800b0a3e  jnz     short loc_1800B0A42
0x1800b0a40  jmp     short loc_1800B0A1B
0x1800b0a42  or      edi, 0FFFFFFFFh
0x1800b0a45  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x1800b0a4c  mov     rcx, rbx; hModule
0x1800b0a4f  call    cs:__imp_GetProcAddress
0x1800b0a55  test    rax, rax
0x1800b0a58  jz      short loc_1800B0A6B
0x1800b0a5a  lea     rcx, [rsp+38h+arg_8]
0x1800b0a5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b0a64  test    eax, eax
0x1800b0a66  cmovns  edi, [rsp+38h+arg_8]
0x1800b0a6b  mov     rcx, rbx; hLibModule
0x1800b0a6e  call    cs:__imp_FreeLibrary
0x1800b0a74  mov     eax, edi
0x1800b0a76  mov     rbx, [rsp+38h+arg_0]
0x1800b0a7b  add     rsp, 30h
0x1800b0a7f  pop     rdi
0x1800b0a80  retn
```
