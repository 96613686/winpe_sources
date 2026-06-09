# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)

- ea: `0x180021a30`
- end: `0x180021acb`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `155`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c1c4`

## callees

- `0x180021a30`
- `0x180021d20`
- `0x18002d0b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021a7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180021a7c`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::string_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180021a30  mov     rax, rsp
0x180021a33  mov     [rax+8], rbx
0x180021a37  push    rdi
0x180021a38  sub     rsp, 40h
0x180021a3c  mov     qword ptr [rax-28h], 0
0x180021a44  lea     r8, [rsp+48h+var_28]
0x180021a49  mov     qword ptr [rax-20h], 0
0x180021a51  mov     rdi, rdx
0x180021a54  mov     byte ptr [rax-18h], 0
0x180021a58  mov     rbx, rcx
0x180021a5b  xor     eax, eax
0x180021a5d  mov     [rsp+48h+var_17], eax
0x180021a61  mov     [rsp+48h+var_13], ax
0x180021a66  mov     [rsp+48h+var_11], al
0x180021a6a  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180021a6f  mov     rcx, [rsp+48h+var_20]
0x180021a74  test    rcx, rcx
0x180021a77  jz      short loc_180021AB6
0x180021a79  add     rcx, rcx; cb
0x180021a7c  call    cs:__imp_CoTaskMemAlloc
0x180021a82  mov     rdx, rax
0x180021a85  mov     rcx, rdi
0x180021a88  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180021a8d  mov     rax, [rdi]
0x180021a90  test    rax, rax
0x180021a93  jz      short loc_180021AA9
0x180021a95  lea     r8, [rsp+48h+var_28]
0x180021a9a  mov     [rsp+48h+var_28], rax
0x180021a9f  mov     rcx, rbx; this
0x180021aa2  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180021aa7  jmp     short loc_180021AC0
0x180021aa9  cmp     dword ptr [rbx+8], 0
0x180021aad  jl      short loc_180021AB6
0x180021aaf  mov     dword ptr [rbx+8], 8007000Eh
0x180021ab6  xor     edx, edx
0x180021ab8  mov     rcx, rdi
0x180021abb  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180021ac0  mov     rbx, [rsp+48h+arg_0]
0x180021ac5  add     rsp, 40h
0x180021ac9  pop     rdi
0x180021aca  retn
```
