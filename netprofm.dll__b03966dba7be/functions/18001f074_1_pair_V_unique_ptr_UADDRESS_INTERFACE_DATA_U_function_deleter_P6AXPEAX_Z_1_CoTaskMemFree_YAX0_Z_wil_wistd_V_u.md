# ??1?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ

- ea: `0x18001f074`
- end: `0x18001f0a1`
- name: `??1?$pair@V?$unique_ptr@UADDRESS_INTERFACE_DATA@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@XZ`
- size: `45`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e968`

## callees

- `0x18001f074`
- `0x18001f0d0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f095`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001f095`

## pseudocode

```c
void __fastcall __1__pair_V__unique_ptr_UADDRESS_INTERFACE_DATA__U__function_deleter_P6AXPEAX_Z_1_CoTaskMemFree__YAX0_Z_wil___wistd__V__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil___std__QEAA_XZ(
        void **a1)
{
  void *v2; // rcx

  __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseGetIPPhysicalInterfaceForDestination_PublicNetworkListManager__CAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(a1 + 1);
  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    CoTaskMemFree(v2);
}

```

## disassembly

```asm
0x18001f074  push    rbx
0x18001f076  sub     rsp, 20h
0x18001f07a  mov     rbx, rcx
0x18001f07d  add     rcx, 8
0x18001f081  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseGetIPPhysicalInterfaceForDestination@PublicNetworkListManager@@CAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001f086  mov     rcx, [rbx]; pv
0x18001f089  mov     qword ptr [rbx], 0
0x18001f090  test    rcx, rcx
0x18001f093  jz      short loc_18001F09B
0x18001f095  call    cs:__imp_CoTaskMemFree
0x18001f09b  add     rsp, 20h
0x18001f09f  pop     rbx
0x18001f0a0  retn
```
