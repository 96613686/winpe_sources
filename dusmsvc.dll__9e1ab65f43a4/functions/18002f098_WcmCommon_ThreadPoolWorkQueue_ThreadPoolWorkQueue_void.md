# WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(void)

- ea: `0x18002f098`
- end: `0x18002f0d7`
- name: `??1ThreadPoolWorkQueue@WcmCommon@@QEAA@XZ`
- size: `63`
- prototype: `void __fastcall(WcmCommon::ThreadPoolWorkQueue *__hidden this)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002f024`
- `0x1800325b4`
- `0x180048624`
- `0x180048636`

## callees

- `0x18002ef04`
- `0x18002efdc`
- `0x18002effc`
- `0x18002f210`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002f0d0`

## pseudocode

```c
void __fastcall WcmCommon::ThreadPoolWorkQueue::~ThreadPoolWorkQueue(WcmCommon::ThreadPoolWorkQueue *this)
{
  WcmCommon::ThreadPoolWorkQueue::Cancel(this);
  WcmCommon::ThreadPoolWorkQueue::_unnamed_type_m_lockedData_::__unnamed_type_m_lockedData_((char *)this + 152);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>((char *)this + 128);
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>((struct _TP_POOL **)this + 15);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x18002f098  push    rbx
0x18002f09a  sub     rsp, 20h
0x18002f09e  mov     rbx, rcx
0x18002f0a1  call    ?Cancel@ThreadPoolWorkQueue@WcmCommon@@QEAAXXZ; WcmCommon::ThreadPoolWorkQueue::Cancel(void)
0x18002f0a6  lea     rcx, [rbx+98h]
0x18002f0ad  call    WcmCommon__ThreadPoolWorkQueue___unnamed_type_m_lockedData_____unnamed_type_m_lockedData_
0x18002f0b2  lea     rcx, [rbx+80h]
0x18002f0b9  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18002f0be  lea     rcx, [rbx+78h]
0x18002f0c2  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)
0x18002f0c7  lea     rcx, [rbx+8]
0x18002f0cb  add     rsp, 20h
0x18002f0cf  pop     rbx
0x18002f0d0  jmp     cs:__imp_DeleteCriticalSection
```
