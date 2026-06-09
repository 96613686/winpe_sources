# ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ

- ea: `0x18000f938`
- end: `0x18000f960`
- name: `??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000f92c`
- `0x1800153b8`
- `0x18001f7b0`

## callees

- `0x18000f938`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18000f94e`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x18000f94e`

## pseudocode

```c
int __fastcall __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_DestroyPrivateObjectSecurity_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
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
0x18000f938  sub     rsp, 28h
0x18000f93c  mov     rax, [rcx]
0x18000f93f  test    rax, rax
0x18000f942  jz      short loc_18000F95A
0x18000f944  lea     rcx, [rsp+28h+ObjectDescriptor]; ObjectDescriptor
0x18000f949  mov     [rsp+28h+ObjectDescriptor], rax
0x18000f94e  call    cs:__imp_DestroyPrivateObjectSecurity
0x18000f955  nop     dword ptr [rax+rax+00h]
0x18000f95a  add     rsp, 28h
0x18000f95e  retn
```
