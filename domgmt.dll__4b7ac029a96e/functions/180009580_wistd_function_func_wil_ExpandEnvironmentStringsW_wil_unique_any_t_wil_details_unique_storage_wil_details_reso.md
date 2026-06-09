# wistd::__function::__func<`wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>,256>(ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)'::`2'::_lambda_1_,long (ushort *,unsigned __int64,unsigned __int64 *)>::`scalar deleting destructor'(uint)

- ea: `0x180009580`
- end: `0x1800095ab`
- name: `??_G?$__func@V_lambda_1_@?1???$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YAJPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@2@@Z@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, service_task`

## callees

- `0x180001f70`
- `0x180009580`

## pseudocode

```c
_QWORD *__fastcall ___G____func_V_lambda_1___1____ExpandEnvironmentStringsW_V__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___wil___0BAA__wil__YAJPEBGAEAV__unique_any_t_V__unique_storage_U__resource_policy_PEAGP6AXPEAX_Z_1_CoTaskMemFree__YAX0_ZU__integral_constant__K_0A__wistd__PEAGPEAG_0A___T_details_wil___details_wil___2__Z___A6AJPEAG_KPEA_K_Z___function_wistd__UEAAPEAXI_Z(
        _QWORD *a1,
        char a2)
{
  *a1 = &wistd::__function::__base<long (unsigned short *,unsigned __int64,unsigned __int64 *)>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180009580  push    rbx
0x180009582  sub     rsp, 20h
0x180009586  lea     rax, ??_7?$__base@$$A6AJPEAG_KPEA_K@Z@__function@wistd@@6B@; const wistd::__function::__base<long (ushort *,unsigned __int64,unsigned __int64 *)>::`vftable'
0x18000958d  mov     rbx, rcx
0x180009590  mov     [rcx], rax
0x180009593  test    dl, 1
0x180009596  jz      short loc_1800095A2
0x180009598  mov     edx, 10h; unsigned __int64
0x18000959d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800095a2  mov     rax, rbx
0x1800095a5  add     rsp, 20h
0x1800095a9  pop     rbx
0x1800095aa  retn
```
