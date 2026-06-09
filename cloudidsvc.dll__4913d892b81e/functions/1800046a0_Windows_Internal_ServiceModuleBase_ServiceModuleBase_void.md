# Windows::Internal::ServiceModuleBase::~ServiceModuleBase(void)

- ea: `0x1800046a0`
- end: `0x1800046ca`
- name: `??1ServiceModuleBase@Internal@Windows@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(Windows::Internal::ServiceModuleBase *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004678`
- `0x1800046d0`

## callees

- `0x1800044c0`
- `0x180006160`

## pseudocode

```c
void __fastcall Windows::Internal::ServiceModuleBase::~ServiceModuleBase(Windows::Internal::ServiceModuleBase *this)
{
  *(_QWORD *)this = &Windows::Internal::ServiceModuleBase::`vftable';
  Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease((char *)this + 24);
  wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&long CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>((char *)this + 8);
}

```

## disassembly

```asm
0x1800046a0  push    rbx
0x1800046a2  sub     rsp, 20h
0x1800046a6  lea     rax, ??_7ServiceModuleBase@Internal@Windows@@6B@; const Windows::Internal::ServiceModuleBase::`vftable'
0x1800046ad  mov     rbx, rcx
0x1800046b0  mov     [rcx], rax
0x1800046b3  add     rcx, 18h
0x1800046b7  call    ?InternalRelease@?$ComPtr@UIGlobalOptions@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IGlobalOptions>::InternalRelease(void)
0x1800046bc  lea     rcx, [rbx+8]
0x1800046c0  add     rsp, 20h
0x1800046c4  pop     rbx
0x1800046c5  jmp     ??1?$unique_storage@U?$resource_policy@PEAUCO_MTA_USAGE_COOKIE__@@P6AJPEAU1@@Z$1?CoDecrementMTAUsage@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<CO_MTA_USAGE_COOKIE__ *,long (*)(CO_MTA_USAGE_COOKIE__ *),&CoDecrementMTAUsage(CO_MTA_USAGE_COOKIE__ *),wistd::integral_constant<unsigned __int64,0>,CO_MTA_USAGE_COOKIE__ *,CO_MTA_USAGE_COOKIE__ *,0,std::nullptr_t>>(void)
```
