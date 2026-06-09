# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x180010980`
- end: `0x1800109b2`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `50`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x180012790`
- `0x180015a2c`
- `0x180015e98`

## callees

- `0x180010980`
- `0x1800150c0`

## pseudocode

```c
_QWORD *__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        _QWORD *a1,
        _QWORD *a2)
{
  if ( a1 != a2 )
  {
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      a1,
      *a2);
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180010980  mov     [rsp+arg_0], rbx
0x180010985  push    rdi
0x180010986  sub     rsp, 20h
0x18001098a  mov     rdi, rdx
0x18001098d  mov     rbx, rcx
0x180010990  cmp     rcx, rdx
0x180010993  jz      short loc_1800109A4
0x180010995  mov     rdx, [rdx]
0x180010998  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18001099d  mov     qword ptr [rdi], 0
0x1800109a4  mov     rax, rbx
0x1800109a7  mov     rbx, [rsp+28h+arg_0]
0x1800109ac  add     rsp, 20h
0x1800109b0  pop     rdi
0x1800109b1  retn
```
