# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x180021990`
- end: `0x180021a28`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `152`
- prototype: `__int64 __fastcall(tson::input_archive *this, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800207a0`
- `0x180020d20`

## callees

- `0x180021990`
- `0x180021c7c`
- `0x18002d0b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800219d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800219d9`

## pseudocode

```c
__int64 __fastcall tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        tson::input_archive *this,
        __int64 a2)
{
  tson::input_archive::read_string_two_phase<tson::ansistring_tag>(this);
  return wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(
           a2,
           0);
}

```

## disassembly

```asm
0x180021990  mov     rax, rsp
0x180021993  mov     [rax+8], rbx
0x180021997  push    rdi
0x180021998  sub     rsp, 40h
0x18002199c  mov     qword ptr [rax-28h], 0
0x1800219a4  lea     r8, [rsp+48h+var_28]
0x1800219a9  mov     qword ptr [rax-20h], 0
0x1800219b1  mov     rdi, rdx
0x1800219b4  mov     byte ptr [rax-18h], 0
0x1800219b8  mov     rbx, rcx
0x1800219bb  xor     eax, eax
0x1800219bd  mov     [rsp+48h+var_17], eax
0x1800219c1  mov     [rsp+48h+var_13], ax
0x1800219c6  mov     [rsp+48h+var_11], al
0x1800219ca  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x1800219cf  mov     rcx, [rsp+48h+cb]; cb
0x1800219d4  test    rcx, rcx
0x1800219d7  jz      short loc_180021A13
0x1800219d9  call    cs:__imp_CoTaskMemAlloc
0x1800219df  mov     rdx, rax
0x1800219e2  mov     rcx, rdi
0x1800219e5  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x1800219ea  mov     rax, [rdi]
0x1800219ed  test    rax, rax
0x1800219f0  jz      short loc_180021A06
0x1800219f2  lea     r8, [rsp+48h+var_28]
0x1800219f7  mov     [rsp+48h+var_28], rax
0x1800219fc  mov     rcx, rbx; this
0x1800219ff  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180021a04  jmp     short loc_180021A1D
0x180021a06  cmp     dword ptr [rbx+8], 0
0x180021a0a  jl      short loc_180021A13
0x180021a0c  mov     dword ptr [rbx+8], 8007000Eh
0x180021a13  xor     edx, edx
0x180021a15  mov     rcx, rdi
0x180021a18  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x180021a1d  mov     rbx, [rsp+48h+arg_0]
0x180021a22  add     rsp, 40h
0x180021a26  pop     rdi
0x180021a27  retn
```
