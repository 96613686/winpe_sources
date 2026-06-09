# tson::input_archive::read_cotaskmem_string<tson::ansistring_tag,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>> &)

- ea: `0x18002259c`
- end: `0x18002263b`
- name: `??$read_cotaskmem_string@Uansistring_tag@tson@@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@input_archive@tson@@AEAAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@Z`
- size: `159`
- prototype: `__int64 __fastcall(tson::input_archive *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021388`
- `0x180021920`

## callees

- `0x18002259c`
- `0x180022898`
- `0x18002e120`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800225e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800225e5`

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
0x18002259c  mov     rax, rsp
0x18002259f  mov     [rax+8], rbx
0x1800225a3  push    rdi
0x1800225a4  sub     rsp, 40h
0x1800225a8  mov     qword ptr [rax-28h], 0
0x1800225b0  lea     r8, [rsp+48h+var_28]
0x1800225b5  mov     qword ptr [rax-20h], 0
0x1800225bd  mov     rdi, rdx
0x1800225c0  mov     byte ptr [rax-18h], 0
0x1800225c4  mov     rbx, rcx
0x1800225c7  xor     eax, eax
0x1800225c9  mov     [rsp+48h+var_17], eax
0x1800225cd  mov     [rsp+48h+var_13], ax
0x1800225d2  mov     [rsp+48h+var_11], al
0x1800225d6  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x1800225db  mov     rcx, [rsp+48h+cb]; cb
0x1800225e0  test    rcx, rcx
0x1800225e3  jz      short loc_180022625
0x1800225e5  call    cs:__imp_CoTaskMemAlloc
0x1800225ec  nop     dword ptr [rax+rax+00h]
0x1800225f1  mov     rdx, rax
0x1800225f4  mov     rcx, rdi
0x1800225f7  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x1800225fc  mov     rax, [rdi]
0x1800225ff  test    rax, rax
0x180022602  jz      short loc_180022618
0x180022604  lea     r8, [rsp+48h+var_28]
0x180022609  mov     [rsp+48h+var_28], rax
0x18002260e  mov     rcx, rbx; this
0x180022611  call    ??$read_string_two_phase@Uansistring_tag@tson@@@input_archive@tson@@AEAAXW4archive_marker@details@1@AEAUansistring_tag@1@@Z; tson::input_archive::read_string_two_phase<tson::ansistring_tag>(tson::details::archive_marker,tson::ansistring_tag &)
0x180022616  jmp     short loc_18002262F
0x180022618  cmp     dword ptr [rbx+8], 0
0x18002261c  jl      short loc_180022625
0x18002261e  mov     dword ptr [rbx+8], 8007000Eh
0x180022625  xor     edx, edx
0x180022627  mov     rcx, rdi
0x18002262a  call    ?reset@?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@QEAAXPEAD@Z; wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>::reset(char *)
0x18002262f  mov     rbx, [rsp+48h+arg_0]
0x180022634  add     rsp, 40h
0x180022638  pop     rdi
0x180022639  retn
```
