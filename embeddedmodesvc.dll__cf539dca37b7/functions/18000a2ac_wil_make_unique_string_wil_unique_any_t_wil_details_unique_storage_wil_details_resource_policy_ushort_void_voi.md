# wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000a2ac`
- end: `0x18000a2e9`
- name: `??$make_unique_string@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `61`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `6`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x18000b3e8`
- `0x180010100`
- `0x180012790`
- `0x180015858`
- `0x180015a2c`
- `0x180015e98`

## callees

- `0x18000a2ac`
- `0x18000a2f0`
- `0x18000c518`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1)
{
  void *v2; // rdx
  unsigned int v3; // r8d
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(a1);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v2, v3, v4);
  return a1;
}

```

## disassembly

```asm
0x18000a2ac  mov     [rsp+arg_0], rcx
0x18000a2b1  push    rbx
0x18000a2b2  sub     rsp, 30h
0x18000a2b6  mov     rbx, rcx
0x18000a2b9  mov     [rsp+38h+var_18], 0
0x18000a2c1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18000a2c6  mov     [rsp+38h+var_18], 1
0x18000a2ce  mov     rcx, [rsp+38h]; this
0x18000a2d3  cmp     qword ptr [rbx], 0
0x18000a2d7  jnz     short loc_18000A2DF
0x18000a2d9  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x18000a2df  mov     rax, rbx
0x18000a2e2  add     rsp, 30h
0x18000a2e6  pop     rbx
0x18000a2e7  retn
```
