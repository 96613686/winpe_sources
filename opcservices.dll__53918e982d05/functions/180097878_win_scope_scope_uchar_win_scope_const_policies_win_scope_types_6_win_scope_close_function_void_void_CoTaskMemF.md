# win_scope::scope<uchar *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<uchar *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(void)

- ea: `0x180097878`
- end: `0x18009789c`
- name: `??1?$scope@PEAEU?$const_policies@U?$types_6@U?$close_function@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@win_scope@@Uconvert_forbidden@2@Uacquire_none@2@U?$normal_store@U?$invalid_value_policy@Unull_t@win_scope@@@win_scope@@Usafe_types_detach_forbidden@2@@2@U?$unique_policy@$0A@@2@Ureport_policy_throw@2@@win_scope@@@win_scope@@@win_scope@@QEAA@XZ`
- size: `36`
- prototype: ``
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180118402`
- `0x18011b526`
- `0x180123139`
- `0x1801231ca`
- `0x18012352f`
- `0x180124d1e`
- `0x180128000`
- `0x18012877d`

## callees

- `0x180097878`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097889`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180097889`

## pseudocode

```c
void __fastcall win_scope::scope<unsigned char *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>::~scope<unsigned char *,win_scope::const_policies<win_scope::types_6<win_scope::close_function<void (*)(void *),&void CoTaskMemFree(void *)>,win_scope::convert_forbidden,win_scope::acquire_none,win_scope::normal_store<win_scope::invalid_value_policy<win_scope::null_t>,win_scope::safe_types_detach_forbidden>,win_scope::unique_policy<0>,win_scope::report_policy_throw>>>(
        void **a1)
{
  void *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    CoTaskMemFree(v2);
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180097878  push    rbx
0x18009787a  sub     rsp, 20h
0x18009787e  mov     rbx, rcx
0x180097881  mov     rcx, [rcx]; pv
0x180097884  test    rcx, rcx
0x180097887  jz      short loc_180097896
0x180097889  call    cs:__imp_CoTaskMemFree
0x18009788f  mov     qword ptr [rbx], 0
0x180097896  add     rsp, 20h
0x18009789a  pop     rbx
0x18009789b  retn
```
