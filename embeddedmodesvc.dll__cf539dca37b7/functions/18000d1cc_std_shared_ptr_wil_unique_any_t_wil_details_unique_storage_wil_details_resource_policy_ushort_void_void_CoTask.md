# std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>> const &)

- ea: `0x18000d1cc`
- end: `0x18000d1fa`
- name: `??0?$shared_ptr@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@std@@QEAA@AEBV01@@Z`
- size: `46`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18000da64`
- `0x180010070`
- `0x180010100`
- `0x1800109b8`
- `0x180015858`
- `0x180015a2c`

## callees

- `0x18000d1cc`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::shared_ptr<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        _QWORD *a2)
{
  __int64 v2; // rax

  *a1 = 0;
  a1[1] = 0;
  v2 = a2[1];
  if ( v2 )
    _InterlockedIncrement((volatile signed __int32 *)(v2 + 8));
  *a1 = *a2;
  a1[1] = a2[1];
  return a1;
}

```

## disassembly

```asm
0x18000d1cc  mov     qword ptr [rcx], 0
0x18000d1d3  mov     qword ptr [rcx+8], 0
0x18000d1db  mov     rax, [rdx+8]
0x18000d1df  test    rax, rax
0x18000d1e2  jz      short loc_18000D1E8
0x18000d1e4  lock inc dword ptr [rax+8]
0x18000d1e8  mov     rax, [rdx]
0x18000d1eb  mov     [rcx], rax
0x18000d1ee  mov     rax, [rdx+8]
0x18000d1f2  mov     [rcx+8], rax
0x18000d1f6  mov     rax, rcx
0x18000d1f9  retn
```
