# MachineInfo::GetTelemetryLevel(void)

- ea: `0x18003c830`
- end: `0x18003c8f1`
- name: `?GetTelemetryLevel@MachineInfo@@AEBAIXZ`
- size: `193`
- prototype: `unsigned int __fastcall(MachineInfo *__hidden this)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callees

- `0x18003c830`
- `0x18003dc00`
- `0x18016796c`
- `0x18018e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c89d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003c89d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c8de`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003c8de`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c8bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c8bf`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x18003c859`
- `DiagnosticDataSettings!TelEvaluateActiveSettingAuthority` at `0x18003c859`

## string_xrefs

- `0x18003c896`: `AEPIC.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MachineInfo::GetTelemetryLevel(MachineInfo *this)
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
    AslLogCallPrintf(1, "MachineInfo::GetTelemetryLevel", 768, "TelEvaluateActiveSettingAuthority failed [%#x]", active);
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
0x18003c830  mov     [rsp+arg_0], rbx
0x18003c835  push    rdi
0x18003c836  sub     rsp, 30h
0x18003c83a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel> `wil::Feature<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::GetImpl(void)'::`2'::impl
0x18003c841  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Census_DirectTelemetryLevel@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Census_DirectTelemetryLevel>::__private_IsEnabled(void)
0x18003c846  mov     [rsp+38h+arg_8], 0
0x18003c84e  xor     edx, edx; hFile
0x18003c850  test    al, al
0x18003c852  jz      short loc_18003C890
0x18003c854  lea     rcx, [rsp+38h+arg_8]
0x18003c859  call    cs:__imp_TelEvaluateActiveSettingAuthority
0x18003c85f  test    eax, eax
0x18003c861  js      short loc_18003C869
0x18003c863  mov     eax, [rsp+38h+arg_8]
0x18003c867  jmp     short loc_18003C8E6
0x18003c869  mov     [rsp+38h+var_18], eax
0x18003c86d  lea     r9, aTelevaluateact_0; "TelEvaluateActiveSettingAuthority faile"...
0x18003c874  mov     r8d, 300h
0x18003c87a  lea     rdx, aMachineinfoGet_0; "MachineInfo::GetTelemetryLevel"
0x18003c881  mov     ecx, 1
0x18003c886  call    AslLogCallPrintf
0x18003c88b  or      eax, 0FFFFFFFFh
0x18003c88e  jmp     short loc_18003C8E6
0x18003c890  mov     r8d, 800h; dwFlags
0x18003c896  lea     rcx, aAepicDll_1; "AEPIC.dll"
0x18003c89d  call    cs:__imp_LoadLibraryExW
0x18003c8a3  mov     rbx, rax
0x18003c8a6  mov     [rsp+38h+arg_10], rax
0x18003c8ab  test    rax, rax
0x18003c8ae  jnz     short loc_18003C8B2
0x18003c8b0  jmp     short loc_18003C88B
0x18003c8b2  or      edi, 0FFFFFFFFh
0x18003c8b5  lea     rdx, aGetprivacyleve; "GetPrivacyLevel"
0x18003c8bc  mov     rcx, rbx; hModule
0x18003c8bf  call    cs:__imp_GetProcAddress
0x18003c8c5  test    rax, rax
0x18003c8c8  jz      short loc_18003C8DB
0x18003c8ca  lea     rcx, [rsp+38h+arg_8]
0x18003c8cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c8d4  test    eax, eax
0x18003c8d6  cmovns  edi, [rsp+38h+arg_8]
0x18003c8db  mov     rcx, rbx; hLibModule
0x18003c8de  call    cs:__imp_FreeLibrary
0x18003c8e4  mov     eax, edi
0x18003c8e6  mov     rbx, [rsp+38h+arg_0]
0x18003c8eb  add     rsp, 30h
0x18003c8ef  pop     rdi
0x18003c8f0  retn
```
