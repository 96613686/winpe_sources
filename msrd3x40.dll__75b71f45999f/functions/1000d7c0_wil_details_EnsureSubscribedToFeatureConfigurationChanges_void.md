# wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)

- ea: `0x1000d7c0`
- end: `0x1000d8c7`
- name: `?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YGIXZ`
- size: `263`
- prototype: `unsigned int __cdecl(wil::details *__hidden this)`
- caller_count: `15`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1000cc40`
- `0x1003ffc0`
- `0x100400b0`
- `0x100401a0`
- `0x10040290`
- `0x10040380`
- `0x10040470`
- `0x10040560`
- `0x10040650`
- `0x100407c0`
- `0x10040930`
- `0x10040aa0`
- `0x10040c10`
- `0x10040d80`
- `0x10040ef0`

## callees

- `0x1000d7c0`
- `0x1000e680`
- `0x1000eb60`
- `0x1005e3b0`
- `0x1005f064`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d808`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1000d808`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d880`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d8aa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d823`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d880`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1000d8aa`

## pseudocode

```c
int __cdecl wil::details::EnsureSubscribedToFeatureConfigurationChanges()
{
  int result; // eax
  int v1; // esi
  _DWORD *v2; // eax
  void (__thiscall *v3)(_DWORD, _DWORD *, _DWORD (__stdcall *)(wil::details::EnabledStateManager *), void *); // esi

  result = dword_10066550;
  if ( !dword_10066550 )
  {
    if ( wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_10066544);
      if ( dword_10066574 )
      {
        v1 = dword_10066550;
        ReleaseSRWLockExclusive(&stru_10066544);
        return v1;
      }
      v2 = (_DWORD *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (__stdcall *)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&void wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<unsigned int,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&();
      v3 = (void (__thiscall *)(_DWORD, _DWORD *, _DWORD (__stdcall *)(wil::details::EnabledStateManager *), void *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
      if ( g_wil_details_internalSubscribeFeatureStateChangeNotification
        || (v3 = (void (__thiscall *)(_DWORD, _DWORD *, _DWORD (__stdcall *)(wil::details::EnabledStateManager *), void *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
      {
        v3(
          v3,
          v2,
          _lambda_e09c5d17d5b6b284794848373a010ee8_::_lambda_invoker_stdcall_,
          &wil::details::g_enabledStateManager);
      }
      else
      {
        *v2 = 0;
      }
      if ( dword_10066574 )
      {
        dword_10066550 = 1;
        ReleaseSRWLockExclusive(&stru_10066544);
        return 1;
      }
      ReleaseSRWLockExclusive(&stru_10066544);
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1000d7c0  mov     edi, edi
0x1000d7c2  push    ebp
0x1000d7c3  mov     ebp, esp
0x1000d7c5  push    0FFFFFFFFh
0x1000d7c7  push    offset ??_ESysColCursor@@UAEPAXI@Z_SEH
0x1000d7cc  mov     eax, large fs:0
0x1000d7d2  push    eax
0x1000d7d3  push    esi
0x1000d7d4  mov     eax, ___security_cookie
0x1000d7d9  xor     eax, ebp
0x1000d7db  push    eax
0x1000d7dc  lea     eax, [ebp+var_C]
0x1000d7df  mov     large fs:0, eax
0x1000d7e5  mov     eax, dword_10066550
0x1000d7ea  nop
0x1000d7eb  test    eax, eax
0x1000d7ed  jnz     loc_1000D88A
0x1000d7f3  mov     [ebp+var_4], eax
0x1000d7f6  mov     eax, ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1000d7fb  test    eax, eax
0x1000d7fd  jz      loc_1000D886
0x1000d803  push    offset stru_10066544; SRWLock
0x1000d808  call    ds:__imp__AcquireSRWLockExclusive@4; AcquireSRWLockExclusive(x)
0x1000d80e  cmp     dword_10066574, 0
0x1000d815  jz      short loc_1000D83B
0x1000d817  mov     esi, dword_10066550
0x1000d81d  nop
0x1000d81e  push    offset stru_10066544; SRWLock
0x1000d823  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d829  mov     eax, esi
0x1000d82b  mov     ecx, [ebp+var_C]
0x1000d82e  mov     large fs:0, ecx
0x1000d835  pop     ecx
0x1000d836  pop     esi
0x1000d837  mov     esp, ebp
0x1000d839  pop     ebp
0x1000d83a  retn
0x1000d83b  mov     ecx, offset dword_10066574
0x1000d840  call    ??I?$unique_any_t@V?$unique_storage@U?$resource_policy@PAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6GXPAU1@@Z$1?WilApi_UnsubscribeFeatureStateChangeNotification@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAU1@PAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QAEPAPAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,void (*)(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),&wil::details::WilApi_UnsubscribeFeatureStateChangeNotification(FEATURE_STATE_CHANGE_SUBSCRIPTION__ *),wistd::integral_constant<uint,0>,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,FEATURE_STATE_CHANGE_SUBSCRIPTION__ *,0,std::nullptr_t>>>::operator&(void)
0x1000d845  mov     esi, _g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1000d84b  test    esi, esi
0x1000d84d  jz      short loc_1000D866
0x1000d84f  push    offset ?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1000d854  push    offset ?_lambda_invoker_stdcall_@_lambda_e09c5d17d5b6b284794848373a010ee8_@@CG@PAX@Z; unsigned int
0x1000d859  push    eax; void *
0x1000d85a  mov     ecx, esi
0x1000d85c  call    ds:___guard_check_icall_fptr; __empty_global_delete(void *,uint) ...
0x1000d862  call    esi ; _g_wil_details_internalSubscribeFeatureStateChangeNotification
0x1000d864  jmp     short loc_1000D872
0x1000d866  mov     esi, _g_wil_details_apiSubscribeFeatureStateChangeNotification
0x1000d86c  test    esi, esi
0x1000d86e  jnz     short loc_1000D84F
0x1000d870  mov     [eax], esi
0x1000d872  cmp     dword_10066574, 0
0x1000d879  jnz     short loc_1000D89A
0x1000d87b  push    offset stru_10066544; SRWLock
0x1000d880  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d886  xor     esi, esi
0x1000d888  mov     eax, esi
0x1000d88a  mov     ecx, [ebp+var_C]
0x1000d88d  mov     large fs:0, ecx
0x1000d894  pop     ecx
0x1000d895  pop     esi
0x1000d896  mov     esp, ebp
0x1000d898  pop     ebp
0x1000d899  retn
0x1000d89a  nop
0x1000d89b  push    offset stru_10066544; SRWLock
0x1000d8a0  mov     dword_10066550, 1
0x1000d8aa  call    ds:__imp__ReleaseSRWLockExclusive@4; ReleaseSRWLockExclusive(x)
0x1000d8b0  mov     esi, 1
0x1000d8b5  mov     eax, esi
0x1000d8b7  mov     ecx, [ebp+var_C]
0x1000d8ba  mov     large fs:0, ecx
0x1000d8c1  pop     ecx
0x1000d8c2  pop     esi
0x1000d8c3  mov     esp, ebp
0x1000d8c5  pop     ebp
0x1000d8c6  retn
0x1005f070  jmp     ds:__imp____std_terminate
0x1005f8f0  nop
0x1005f8f1  nop
0x1005f8f2  mov     edx, [esp-4+arg_4]
0x1005f8f6  lea     eax, [edx+0Ch]
0x1005f8f9  mov     ecx, [edx-8]
0x1005f8fc  xor     ecx, eax; StackCookie
0x1005f8fe  call    @__security_check_cookie@4; __security_check_cookie(x)
0x1005f903  mov     eax, offset stru_10062AD4
0x1005f908  jmp     ___CxxFrameHandler3
```
