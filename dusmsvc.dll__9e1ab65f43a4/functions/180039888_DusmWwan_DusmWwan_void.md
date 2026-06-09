# DusmWwan::~DusmWwan(void)

- ea: `0x180039888`
- end: `0x1800398ba`
- name: `??1DusmWwan@@AEAA@XZ`
- size: `50`
- prototype: `void __fastcall(DusmWwan *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task`

## callers

- `0x18003b718`

## callees

- `0x18000effc`
- `0x1800303a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003989e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003989e`

## pseudocode

```c
void __fastcall DusmWwan::~DusmWwan(DusmWwan *this)
{
  std::shared_ptr<DusmNduTracker>::~shared_ptr<DusmNduTracker>((__int64)this + 64);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)this + 1);
  wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>((SC_HANDLE *)this);
}

```

## disassembly

```asm
0x180039888  push    rbx
0x18003988a  sub     rsp, 20h
0x18003988e  mov     rbx, rcx
0x180039891  add     rcx, 40h ; '@'
0x180039895  call    ??1?$shared_ptr@VDusmNduTracker@@@std@@QEAA@XZ; std::shared_ptr<DusmNduTracker>::~shared_ptr<DusmNduTracker>(void)
0x18003989a  lea     rcx, [rbx+18h]; lpCriticalSection
0x18003989e  call    cs:__imp_DeleteCriticalSection
0x1800398a4  lea     rcx, [rbx+8]
0x1800398a8  call    ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
0x1800398ad  mov     rcx, rbx
0x1800398b0  add     rsp, 20h
0x1800398b4  pop     rbx
0x1800398b5  jmp     ??1?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>(void)
```
