# wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x18000a68c`
- end: `0x18000a715`
- name: `??0?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAA@$$QEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@1@@Z`
- size: `137`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18000b3e8`
- `0x180015e98`

## callees

- `0x180002f1c`
- `0x180009f58`
- `0x18000a68c`
- `0x18000c300`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v4; // rcx
  std::_Ref_count_base *v5; // rcx
  __int64 v6; // r8
  _DWORD *v8; // [rsp+30h] [rbp+8h]

  *a1 = 0;
  a1[1] = 0;
  if ( *a2 )
  {
    v8 = operator new(0x18u);
    *(_OWORD *)v8 = 0;
    v8[2] = 1;
    v8[3] = 1;
    *(_QWORD *)v8 = &std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::`vftable';
    std::_Construct_in_place<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(
      v8 + 4,
      a2);
    *a1 = v4;
    v5 = (std::_Ref_count_base *)a1[1];
    a1[1] = v6;
    if ( v5 )
      std::_Ref_count_base::_Decref(v5);
  }
  return a1;
}

```

## disassembly

```asm
0x18000a68c  mov     [rsp+arg_10], rbx
0x18000a691  mov     [rsp+arg_0], rcx
0x18000a696  push    rdi
0x18000a697  sub     rsp, 20h
0x18000a69b  mov     rdi, rdx
0x18000a69e  mov     rbx, rcx
0x18000a6a1  mov     qword ptr [rcx], 0
0x18000a6a8  mov     qword ptr [rcx+8], 0
0x18000a6b0  cmp     qword ptr [rdx], 0
0x18000a6b4  jz      short loc_18000A707
0x18000a6b6  mov     ecx, 18h; Size
0x18000a6bb  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6c0  mov     r8, rax
0x18000a6c3  mov     [rsp+28h+arg_0], rax
0x18000a6c8  xorps   xmm0, xmm0
0x18000a6cb  movups  xmmword ptr [rax], xmm0
0x18000a6ce  mov     eax, 1
0x18000a6d3  mov     [r8+8], eax
0x18000a6d7  mov     [r8+0Ch], eax
0x18000a6db  lea     rax, ??_7?$_Ref_count_obj2@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@6B@; const std::_Ref_count_obj2<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::`vftable'
0x18000a6e2  mov     [r8], rax
0x18000a6e5  lea     rcx, [r8+10h]
0x18000a6e9  mov     rdx, rdi
0x18000a6ec  call    ??$_Construct_in_place@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V12@@std@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@$$QEAV12@@Z; std::_Construct_in_place<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &&)
0x18000a6f1  mov     [rbx], rcx
0x18000a6f4  mov     rcx, [rbx+8]; this
0x18000a6f8  mov     [rbx+8], r8
0x18000a6fc  test    rcx, rcx
0x18000a6ff  jz      short loc_18000A707
0x18000a701  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a706  nop
0x18000a707  mov     rax, rbx
0x18000a70a  mov     rbx, [rsp+28h+arg_10]
0x18000a70f  add     rsp, 20h
0x18000a713  pop     rdi
0x18000a714  retn
```
