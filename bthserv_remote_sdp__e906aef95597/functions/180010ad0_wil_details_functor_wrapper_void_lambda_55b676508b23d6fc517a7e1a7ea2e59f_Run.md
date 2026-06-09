# wil::details::functor_wrapper_void__lambda_55b676508b23d6fc517a7e1a7ea2e59f___::Run

- ea: `0x180010ad0`
- end: `0x180010b93`
- name: `wil::details::functor_wrapper_void__lambda_55b676508b23d6fc517a7e1a7ea2e59f___::Run`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000ab30`

## callees

- `0x180001b94`
- `0x180001bcc`
- `0x180010ad0`
- `0x18001eb6c`
- `0x18001f1cc`
- `0x18001f1e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180010b29`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180010b29`

## string_xrefs

- `0x180010b81`: `onecore\drivers\wdm\bluetooth\user\bthserv\server\dll\bthservdevicerefresher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 wil::details::functor_wrapper_void__lambda_55b676508b23d6fc517a7e1a7ea2e59f___::Run()
{
  void *v0; // rdi
  _QWORD *v1; // rax
  struct _TP_WORK *ThreadpoolWork; // rax
  const char *v3; // r9
  Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *v4; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = operator new(0x28u);
  *(_QWORD *)v0 = 0;
  *((_BYTE *)v0 + 8) = 0;
  *((_QWORD *)v0 + 2) = 0;
  *((_QWORD *)v0 + 3) = 0;
  v1 = operator new(0x20u);
  *v1 = v1;
  v1[1] = v1;
  *((_QWORD *)v0 + 2) = v1;
  *((_QWORD *)v0 + 4) = 0;
  ThreadpoolWork = CreateThreadpoolWork(
                     Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::RefreshBrServicesCallBack,
                     v0,
                     0);
  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    (struct _TP_WORK **)v0 + 4,
    ThreadpoolWork);
  if ( !*((_QWORD *)v0 + 4) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1D,
      (unsigned int)"onecore\\drivers\\wdm\\bluetooth\\user\\bthserv\\server\\dll\\bthservdevicerefresher.cpp",
      v3);
  v4 = (Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *)qword_180047110;
  qword_180047110 = (PSRWLOCK)v0;
  if ( v4 )
  {
    Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(v4);
    operator delete(v4, (const struct std::nothrow_t *)0x28);
  }
  return 0;
}

```

## disassembly

```asm
0x180010ad0  mov     [rsp+arg_8], rbx
0x180010ad5  mov     [rsp+arg_0], rcx
0x180010ada  push    rdi
0x180010adb  sub     rsp, 20h
0x180010adf  mov     ecx, 28h ; '('; Size
0x180010ae4  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010ae9  mov     rdi, rax
0x180010aec  mov     [rsp+28h+arg_0], rax
0x180010af1  xor     eax, eax
0x180010af3  mov     [rdi], rax
0x180010af6  mov     [rdi+8], al
0x180010af9  and     [rdi+10h], rax
0x180010afd  and     [rdi+18h], rax
0x180010b01  lea     ecx, [rax+20h]; Size
0x180010b04  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010b09  mov     [rax], rax
0x180010b0c  mov     [rax+8], rax
0x180010b10  mov     [rdi+10h], rax
0x180010b14  lea     rbx, [rdi+20h]
0x180010b18  and     qword ptr [rbx], 0
0x180010b1c  xor     r8d, r8d; pcbe
0x180010b1f  mov     rdx, rdi; pv
0x180010b22  lea     rcx, ?RefreshBrServicesCallBack@BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180010b29  call    cs:__imp_CreateThreadpoolWork
0x180010b30  nop     dword ptr [rax+rax+00h]
0x180010b35  mov     rdx, rax
0x180010b38  mov     rcx, rbx
0x180010b3b  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x180010b40  mov     rcx, [rsp+28h]; this
0x180010b45  cmp     qword ptr [rbx], 0
0x180010b49  jz      short loc_180010B81
0x180010b4b  mov     rbx, cs:qword_180047110
0x180010b52  mov     cs:qword_180047110, rdi
0x180010b59  test    rbx, rbx
0x180010b5c  jz      short loc_180010B73
0x180010b5e  mov     rcx, rbx; this
0x180010b61  call    ??1BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ; Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(void)
0x180010b66  mov     edx, 28h ; '('; struct std::nothrow_t *
0x180010b6b  mov     rcx, rbx; void *
0x180010b6e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180010b73  xor     eax, eax
0x180010b75  mov     rbx, [rsp+28h+arg_8]
0x180010b7a  add     rsp, 20h
0x180010b7e  pop     rdi
0x180010b7f  retn
0x180010b81  lea     r8, aOnecoreDrivers_10; "onecore\\drivers\\wdm\\bluetooth\\user"...
0x180010b88  mov     edx, 1Dh; void *
0x180010b8d  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
