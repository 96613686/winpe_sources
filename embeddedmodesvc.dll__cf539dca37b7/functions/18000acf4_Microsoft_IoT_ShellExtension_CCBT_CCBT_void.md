# Microsoft::IoT::ShellExtension::CCBT::~CCBT(void)

- ea: `0x18000acf4`
- end: `0x18000ad26`
- name: `??1CCBT@ShellExtension@IoT@Microsoft@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(void **this)`
- caller_count: `12`
- callee_count: `2`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000a060`
- `0x1800103bc`
- `0x18001046c`
- `0x1800114f0`
- `0x180012c00`
- `0x180012f10`
- `0x180015000`
- `0x180015e98`
- `0x180019849`
- `0x180019b26`
- `0x180019b64`
- `0x180019d72`

## callees

- `0x18000aa70`
- `0x18000ab5c`

## pseudocode

```c
void __fastcall Microsoft::IoT::ShellExtension::CCBT::~CCBT(void **this)
{
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(this + 6);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(this + 5);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(this + 4);
  std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>((__int64)(this + 2));
}

```

## disassembly

```asm
0x18000acf4  push    rbx
0x18000acf6  sub     rsp, 20h
0x18000acfa  mov     rbx, rcx
0x18000acfd  add     rcx, 30h ; '0'
0x18000ad01  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ad06  lea     rcx, [rbx+28h]
0x18000ad0a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ad0f  lea     rcx, [rbx+20h]
0x18000ad13  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18000ad18  lea     rcx, [rbx+10h]
0x18000ad1c  add     rsp, 20h
0x18000ad20  pop     rbx
0x18000ad21  jmp     ??1?$shared_ptr@VMTAThread@Utility@IoT@Microsoft@@@std@@QEAA@XZ; std::shared_ptr<Microsoft::IoT::Utility::MTAThread>::~shared_ptr<Microsoft::IoT::Utility::MTAThread>(void)
```
