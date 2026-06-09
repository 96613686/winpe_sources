# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000c3ac`
- end: `0x14000c407`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400081c0`

## callees

- `0x14000bcc4`
- `0x14000c3ac`
- `0x140010010`

## string_xrefs

- `0x14000c3c8`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax

  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
    return ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64, _QWORD, __int64))NtDllProcedureAddress)(
             `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
             a2,
             0,
             a4);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(__int64 (__fastcall *)(), __int64, _QWORD, __int64))NtDllProcedureAddress)(
             `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock'::`5'::_lambda_1_::_lambda_invoker_cdecl_,
             a2,
             0,
             a4);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x14000c3ac  mov     [rsp+arg_0], rbx
0x14000c3b1  push    rdi
0x14000c3b2  sub     rsp, 30h
0x14000c3b6  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000c3bd  mov     rbx, r9
0x14000c3c0  mov     rdi, rdx
0x14000c3c3  test    rax, rax
0x14000c3c6  jnz     short loc_14000C3E7
0x14000c3c8  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000c3cf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000c3d4  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000c3db  test    rax, rax
0x14000c3de  jnz     short loc_14000C3E7
0x14000c3e0  mov     eax, 0C0000139h
0x14000c3e5  jmp     short loc_14000C3FC
0x14000c3e7  mov     r9, rbx
0x14000c3ea  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?4??EnsureSubscribedToStateChangesUnderLock@FeatureStateManager@details@wil@@CAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?UnregisterWilFeatureConfigurationChange@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@5@PEAX@Z@SA@1@Z; `wil::details::FeatureStateManager::EnsureSubscribedToStateChangesUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::UnregisterWilFeatureConfigurationChange(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &,void *)'::`5'::_lambda_1_::_lambda_invoker_cdecl_(void *)
0x14000c3f1  xor     r8d, r8d
0x14000c3f4  mov     rdx, rdi
0x14000c3f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c3fc  mov     rbx, [rsp+38h+arg_0]
0x14000c401  add     rsp, 30h
0x14000c405  pop     rdi
0x14000c406  retn
```
