# wistd::__function::__func<`wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (ushort *,unsigned __int64,unsigned __int64 *)>::operator()(ushort * &&,unsigned __int64 &&,unsigned __int64 * &&)

- ea: `0x180009140`
- end: `0x180009189`
- name: `??R?$__func@V_lambda_1_@?1???$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAJ$$QEAPEAG$$QEA_K$$QEAPEA_K@Z`
- size: `73`
- prototype: `__int64 __fastcall(__int64, LPWSTR *, DWORD *, _QWORD **)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, service_task`

## callees

- `0x180005944`
- `0x180009140`

## import_xrefs

- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009156`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180009156`

## string_xrefs

- `0x18000916b`: `onecore\internal\sdk\inc\wil\opensource/wil/win32_helpers.h`

## pseudocode

```c
__int64 __fastcall __R____func_V_lambda_1___1____ExpandEnvironmentStringsW_V__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEBGAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___2__Z___A6AJPEAG_KPEA_K_Z___function_wistd__UEAAJ__QEAPEAG__QEA_K__QEAPEA_K_Z(
        __int64 a1,
        LPWSTR *a2,
        DWORD *a3,
        _QWORD **a4)
{
  _QWORD *v4; // rbx
  DWORD v5; // eax
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v4 = *a4;
  v5 = ExpandEnvironmentStringsW(**(LPCWSTR **)(a1 + 8), *a2, *a3);
  *v4 = v5;
  if ( v5 )
    return 0;
  else
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x191,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/win32_helpers.h",
             v6);
}

```

## disassembly

```asm
0x180009140  push    rbx
0x180009142  sub     rsp, 20h
0x180009146  mov     rcx, [rcx+8]
0x18000914a  mov     r8d, [r8]; nSize
0x18000914d  mov     rdx, [rdx]; lpDst
0x180009150  mov     rbx, [r9]
0x180009153  mov     rcx, [rcx]; lpSrc
0x180009156  call    cs:__imp_ExpandEnvironmentStringsW
0x18000915c  mov     eax, eax
0x18000915e  mov     [rbx], rax
0x180009161  test    rax, rax
0x180009164  jnz     short loc_180009181
0x180009166  mov     rcx, [rsp+28h]; this
0x18000916b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180009172  mov     edx, 191h; void *
0x180009177  add     rsp, 20h
0x18000917b  pop     rbx
0x18000917c  jmp     ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180009181  xor     eax, eax
0x180009183  add     rsp, 20h
0x180009187  pop     rbx
0x180009188  retn
```
