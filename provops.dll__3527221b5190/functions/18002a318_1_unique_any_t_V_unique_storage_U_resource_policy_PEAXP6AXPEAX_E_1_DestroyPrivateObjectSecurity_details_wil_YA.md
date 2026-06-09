# ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ

- ea: `0x18002a318`
- end: `0x18002a339`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `33`
- prototype: `int __fastcall(PSECURITY_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18003627f`

## callees

- `0x18002a318`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002a32e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18002a32e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
int __fastcall __1__unique_any_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil___wil__QEAA_XZ(
        PSECURITY_DESCRIPTOR *a1)
{
  PSECURITY_DESCRIPTOR v1; // rax
  PSECURITY_DESCRIPTOR ObjectDescriptor; // [rsp+30h] [rbp+8h] BYREF

  v1 = *a1;
  if ( *a1 )
  {
    ObjectDescriptor = *a1;
    LODWORD(v1) = DestroyPrivateObjectSecurity(&ObjectDescriptor);
  }
  return (int)v1;
}

```

## disassembly

```asm
0x18002a318  sub     rsp, 28h
0x18002a31c  mov     rax, [rcx]
0x18002a31f  test    rax, rax
0x18002a322  jz      short loc_18002A334
0x18002a324  lea     rcx, [rsp+28h+ObjectDescriptor]; ObjectDescriptor
0x18002a329  mov     [rsp+28h+ObjectDescriptor], rax
0x18002a32e  call    cs:__imp_DestroyPrivateObjectSecurity
0x18002a334  add     rsp, 28h
0x18002a338  retn
```
