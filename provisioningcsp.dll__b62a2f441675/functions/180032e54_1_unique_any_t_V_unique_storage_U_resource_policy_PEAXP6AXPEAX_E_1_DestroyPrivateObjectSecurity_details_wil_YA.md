# ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ

- ea: `0x180032e54`
- end: `0x180032e7c`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?DestroyPrivateObjectSecurity@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `40`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180037658`

## callees

- `0x180032e54`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180032e6a`
- `api-ms-win-security-base-l1-1-0!DestroyPrivateObjectSecurity` at `0x180032e6a`

## pseudocode

```c
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
0x180032e54  sub     rsp, 28h
0x180032e58  mov     rax, [rcx]
0x180032e5b  test    rax, rax
0x180032e5e  jz      short loc_180032E76
0x180032e60  lea     rcx, [rsp+28h+ObjectDescriptor]; ObjectDescriptor
0x180032e65  mov     [rsp+28h+ObjectDescriptor], rax
0x180032e6a  call    cs:__imp_DestroyPrivateObjectSecurity
0x180032e71  nop     dword ptr [rax+rax+00h]
0x180032e76  add     rsp, 28h
0x180032e7a  retn
```
