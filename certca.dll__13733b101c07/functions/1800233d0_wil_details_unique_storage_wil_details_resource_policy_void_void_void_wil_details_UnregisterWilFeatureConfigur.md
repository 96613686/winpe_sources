# wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)

- ea: `0x1800233d0`
- end: `0x180023411`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180023320`
- `0x180023484`
- `0x180039450`
- `0x18003969b`
- `0x1800397ce`

## callees

- `0x18001d960`
- `0x1800233d0`
- `0x18003b010`

## string_xrefs

- `0x1800233ea`: `RtlUnregisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(
        __int64 *a1)
{
  __int64 v1; // rbx
  __int64 (*NtDllProcedureAddress)(void); // rax

  v1 = *a1;
  if ( *a1 )
  {
    NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlUnregisterFeatureConfigurationChangeNotification"),
          (g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64))NtDllProcedureAddress)(v1);
    }
  }
}

```

## disassembly

```asm
0x1800233d0  push    rbx
0x1800233d2  sub     rsp, 20h
0x1800233d6  mov     rbx, [rcx]
0x1800233d9  test    rbx, rbx
0x1800233dc  jz      short loc_18002340B
0x1800233de  mov     rax, cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification
0x1800233e5  test    rax, rax
0x1800233e8  jnz     short loc_180023402
0x1800233ea  lea     rcx, aRtlunregisterf; "RtlUnregisterFeatureConfigurationChange"...
0x1800233f1  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800233f6  mov     cs:g_wil_details_pfnRtlUnregisterFeatureConfigurationChangeNotification, rax
0x1800233fd  test    rax, rax
0x180023400  jz      short loc_18002340B
0x180023402  mov     rcx, rbx
0x180023405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002340a  nop
0x18002340b  add     rsp, 20h
0x18002340f  pop     rbx
0x180023410  retn
```
