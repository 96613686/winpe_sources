# _DevhlprGetReaderImageNameInternal_::_1_::dtor$27

- ea: `0x180024880`
- end: `0x18002488c`
- name: `_DevhlprGetReaderImageNameInternal_::_1_::dtor$27`
- size: `12`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x180015bf8`

## pseudocode

```c
__int64 __fastcall DevhlprGetReaderImageNameInternal_::_1_::dtor_27(__int64 a1, __int64 a2)
{
  return wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&long SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>(a2 + 88);
}

```

## disassembly

```asm
0x180024880  lea     rcx, [rdx+58h]
0x180024887  jmp     ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@_KP6AJ_K@Z$1?SCardReleaseContext@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@_K_K$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned __int64,long (*)(unsigned __int64),&SCardReleaseContext(unsigned __int64),wistd::integral_constant<unsigned __int64,0>,unsigned __int64,unsigned __int64,0,std::nullptr_t>>>(void)
```
