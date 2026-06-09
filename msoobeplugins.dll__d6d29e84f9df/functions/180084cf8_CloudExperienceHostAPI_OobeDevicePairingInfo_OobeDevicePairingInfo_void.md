# CloudExperienceHostAPI::OobeDevicePairingInfo::~OobeDevicePairingInfo(void)

- ea: `0x180084cf8`
- end: `0x180084da4`
- name: `??1OobeDevicePairingInfo@CloudExperienceHostAPI@@UEAA@XZ`
- size: `172`
- prototype: `void __fastcall(CloudExperienceHostAPI::OobeDevicePairingInfo *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180085450`

## callees

- `0x18001ad08`
- `0x18001e9a4`
- `0x1800587dc`
- `0x180084b58`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d4a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d6e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180084d80`

## pseudocode

```c
void __fastcall CloudExperienceHostAPI::OobeDevicePairingInfo::~OobeDevicePairingInfo(HSTRING *this)
{
  Microsoft::WRL::EventSource<CloudExperienceHostAPI::IOobeZdpStatusChangeHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<CloudExperienceHostAPI::IOobeZdpStatusChangeHandler,Microsoft::WRL::InvokeModeOptions<-2>>(this + 18);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(this + 16);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(this + 15);
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(this + 14);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(this + 13);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(this + 12);
  wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(this + 11);
  WindowsDeleteString(this[10]);
  this[10] = 0;
  WindowsDeleteString(this[9]);
  this[9] = 0;
  WindowsDeleteString(this[8]);
  this[8] = 0;
  WindowsDeleteString(this[7]);
  this[7] = 0;
  wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(this + 5);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CloudExperienceHostAPI::IOobeDisplayLanguageElevatedManager,INamedPropertyStore>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CloudExperienceHostAPI::IOobeDisplayLanguageElevatedManager,INamedPropertyStore>(this);
}

```

## disassembly

```asm
0x180084cf8  push    rbx
0x180084cfa  sub     rsp, 20h
0x180084cfe  mov     rbx, rcx
0x180084d01  add     rcx, 90h
0x180084d08  call    ??1?$EventSource@UIOobeZdpStatusChangeHandler@CloudExperienceHostAPI@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<CloudExperienceHostAPI::IOobeZdpStatusChangeHandler,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<CloudExperienceHostAPI::IOobeZdpStatusChangeHandler,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180084d0d  lea     rcx, [rbx+80h]
0x180084d14  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180084d19  lea     rcx, [rbx+78h]
0x180084d1d  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180084d22  lea     rcx, [rbx+70h]
0x180084d26  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180084d2b  lea     rcx, [rbx+68h]
0x180084d2f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180084d34  lea     rcx, [rbx+60h]
0x180084d38  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180084d3d  lea     rcx, [rbx+58h]
0x180084d41  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180084d46  mov     rcx, [rbx+50h]; string
0x180084d4a  call    cs:__imp_WindowsDeleteString
0x180084d50  mov     qword ptr [rbx+50h], 0
0x180084d58  mov     rcx, [rbx+48h]; string
0x180084d5c  call    cs:__imp_WindowsDeleteString
0x180084d62  mov     qword ptr [rbx+48h], 0
0x180084d6a  mov     rcx, [rbx+40h]; string
0x180084d6e  call    cs:__imp_WindowsDeleteString
0x180084d74  mov     qword ptr [rbx+40h], 0
0x180084d7c  mov     rcx, [rbx+38h]; string
0x180084d80  call    cs:__imp_WindowsDeleteString
0x180084d86  lea     rcx, [rbx+28h]
0x180084d8a  mov     qword ptr [rbx+38h], 0
0x180084d92  call    ??1?$com_ptr_t@UIUsoCallback@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUsoCallback,wil::err_returncode_policy>::~com_ptr_t<IUsoCallback,wil::err_returncode_policy>(void)
0x180084d97  mov     rcx, rbx
0x180084d9a  add     rsp, 20h
0x180084d9e  pop     rbx
0x180084d9f  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIOobeDisplayLanguageElevatedManager@CloudExperienceHostAPI@@UINamedPropertyStore@@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CloudExperienceHostAPI::IOobeDisplayLanguageElevatedManager,INamedPropertyStore>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,CloudExperienceHostAPI::IOobeDisplayLanguageElevatedManager,INamedPropertyStore>(void)
```
