# Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::Close(void)

- ea: `0x180018d1c`
- end: `0x180018d74`
- name: `?Close@?$CFileChannel@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Driver@Stack@Rdp@@QEAAXXZ`
- size: `88`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x1800186b4`
- `0x18001a5f8`

## callees

- `0x18000f338`
- `0x18000fc30`
- `0x180011aa4`
- `0x1800129cc`
- `0x180018a0c`
- `0x180018d1c`

## pseudocode

```c
void __fastcall Rdp::Stack::Driver::CFileChannel<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::Close(
        __int64 a1)
{
  __int64 v2; // rdx
  wil::details *v3; // rcx
  void *v4; // rdx
  _BYTE v5[24]; // [rsp+20h] [rbp-18h] BYREF

  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    v5,
    a1 + 16);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    a1,
    -1);
  v2 = *(_QWORD *)(a1 + 8);
  *(_QWORD *)(a1 + 8) = 0;
  if ( v2 )
    std::default_delete<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&void Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::operator()();
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(v5);
  v3 = *(wil::details **)(a1 + 96);
  *(_DWORD *)(a1 + 104) = 0;
  wil::details::ResetEvent(v3, v4);
}

```

## disassembly

```asm
0x180018d1c  push    rbx
0x180018d1e  sub     rsp, 30h
0x180018d22  mov     rbx, rcx
0x180018d25  lea     rdx, [rcx+10h]
0x180018d29  lea     rcx, [rsp+38h+var_18]
0x180018d2e  call    ??0?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@@Z; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &)
0x180018d33  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180018d37  mov     rcx, rbx
0x180018d3a  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180018d3f  mov     rdx, [rbx+8]
0x180018d43  mov     qword ptr [rbx+8], 0
0x180018d4b  test    rdx, rdx
0x180018d4e  jz      short loc_180018D55
0x180018d50  call    ??R?$default_delete@V?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@std@@QEBAXPEAV?$CThreadPoolIo@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_IO@@P6AXPEAU1@@Z$1?DestroyThreadpoolIo@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@@Z; std::default_delete<Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>>>::operator()(Rdp::Utils::TP::details::CThreadPoolIo<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_IO *,void (*)(_TP_IO *),&Rdp::Utils::TP::details::DestroyThreadpoolIo(_TP_IO *),wistd::integral_constant<unsigned __int64,0>,_TP_IO *,_TP_IO *,0,std::nullptr_t>>>> *)
0x180018d55  lea     rcx, [rsp+38h+var_18]
0x180018d5a  call    ??1?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::~unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x180018d5f  mov     rcx, [rbx+60h]; this
0x180018d63  mov     dword ptr [rbx+68h], 0
0x180018d6a  add     rsp, 30h
0x180018d6e  pop     rbx
0x180018d6f  jmp     ?ResetEvent@details@wil@@YAXPEAX@Z; wil::details::ResetEvent(void *)
```
