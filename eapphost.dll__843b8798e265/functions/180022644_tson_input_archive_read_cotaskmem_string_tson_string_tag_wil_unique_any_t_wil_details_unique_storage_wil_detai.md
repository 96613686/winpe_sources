# tson::input_archive::read_cotaskmem_string<tson::string_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &)

- ea: `0x180022644`
- end: `0x1800226e6`
- name: `??$read_cotaskmem_string@Ustring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `162`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002d168`

## callees

- `0x180022644`
- `0x18002293c`
- `0x18002e120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022690`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022690`

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
0x180022644  mov     rax, rsp
0x180022647  mov     [rax+8], rbx
0x18002264b  push    rdi
0x18002264c  sub     rsp, 40h
0x180022650  mov     qword ptr [rax-28h], 0
0x180022658  lea     r8, [rsp+48h+var_28]
0x18002265d  mov     qword ptr [rax-20h], 0
0x180022665  mov     rdi, rdx
0x180022668  mov     byte ptr [rax-18h], 0
0x18002266c  mov     rbx, rcx
0x18002266f  xor     eax, eax
0x180022671  mov     [rsp+48h+var_17], eax
0x180022675  mov     [rsp+48h+var_13], ax
0x18002267a  mov     [rsp+48h+var_11], al
0x18002267e  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x180022683  mov     rcx, [rsp+48h+var_20]
0x180022688  test    rcx, rcx
0x18002268b  jz      short loc_1800226D0
0x18002268d  add     rcx, rcx; cb
0x180022690  call    cs:__imp_CoTaskMemAlloc
0x180022697  nop     dword ptr [rax+rax+00h]
0x18002269c  mov     rdx, rax
0x18002269f  mov     rcx, rdi
0x1800226a2  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x1800226a7  mov     rax, [rdi]
0x1800226aa  test    rax, rax
0x1800226ad  jz      short loc_1800226C3
0x1800226af  lea     r8, [rsp+48h+var_28]
0x1800226b4  mov     [rsp+48h+var_28], rax
0x1800226b9  mov     rcx, rbx; this
0x1800226bc  call    ??$read_string_two_phase@Ustring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUstring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::string_tag>(tson::details::archive_marker,tson::string_tag &)
0x1800226c1  jmp     short loc_1800226DA
0x1800226c3  cmp     dword ptr [rbx+8], 0
0x1800226c7  jl      short loc_1800226D0
0x1800226c9  mov     dword ptr [rbx+8], 8007000Eh
0x1800226d0  xor     edx, edx
0x1800226d2  mov     rcx, rdi
0x1800226d5  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x1800226da  mov     rbx, [rsp+48h+arg_0]
0x1800226df  add     rsp, 40h
0x1800226e3  pop     rdi
0x1800226e4  retn
```
