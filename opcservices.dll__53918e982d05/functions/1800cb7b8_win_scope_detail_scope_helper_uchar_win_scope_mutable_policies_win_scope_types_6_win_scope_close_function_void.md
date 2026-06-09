# win_scope::detail::scope_helper<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::safe_replace(win_scope::scope<uchar *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>> &)

- ea: `0x1800cb7b8`
- end: `0x1800cb7e6`
- name: `?safe_replace@?$scope_helper@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@detail@win_scope@@SAPEAPEAEAEAV?$scope@PEAEU?$mutable_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_auto_pointer@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Udefault_safe_types@detail@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@3@@Z`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009f5ac`

## callees

- `0x1800cb7b8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb7d0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cb7d0`

## pseudocode

```c
void **__fastcall win_scope::detail::scope_helper<unsigned char *,win_scope::mutable_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_auto_pointer,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::detail::default_safe_types>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::safe_replace(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  *a1 = 0;
  if ( v2 )
    CoTaskMemFree(v2);
  *a1 = 0;
  return a1;
}

```

## disassembly

```asm
0x1800cb7b8  push    rbx
0x1800cb7ba  sub     rsp, 20h
0x1800cb7be  mov     rbx, rcx
0x1800cb7c1  mov     rcx, [rcx]; pv
0x1800cb7c4  mov     qword ptr [rbx], 0
0x1800cb7cb  test    rcx, rcx
0x1800cb7ce  jz      short loc_1800CB7D6
0x1800cb7d0  call    cs:__imp_CoTaskMemFree
0x1800cb7d6  mov     qword ptr [rbx], 0
0x1800cb7dd  mov     rax, rbx
0x1800cb7e0  add     rsp, 20h
0x1800cb7e4  pop     rbx
0x1800cb7e5  retn
```
