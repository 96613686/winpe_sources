# Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(void)

- ea: `0x18001eb6c`
- end: `0x18001ebf1`
- name: `??1BthServDeviceRefresher@BthServ@Services@Bluetooth@Microsoft@@QEAA@XZ`
- size: `133`
- prototype: `void __fastcall(Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000b164`
- `0x18000b214`
- `0x1800101a4`
- `0x180010ad0`

## callees

- `0x180001b94`
- `0x18001eb6c`
- `0x18001f1e8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001eb95`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18001eb95`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001eba4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001eba4`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher::~BthServDeviceRefresher(
        Microsoft::Bluetooth::Services::BthServ::BthServDeviceRefresher *this)
{
  struct _TP_WORK *v2; // rbx
  _QWORD **v3; // rcx
  _QWORD *v4; // rcx
  _QWORD *v5; // rbx

  wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
    (char *)this + 32,
    0);
  v2 = (struct _TP_WORK *)*((_QWORD *)this + 4);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(*((PTP_WORK *)this + 4), 1);
    CloseThreadpoolWork(v2);
  }
  v3 = (_QWORD **)*((_QWORD *)this + 2);
  *v3[1] = 0;
  v4 = *v3;
  if ( v4 )
  {
    do
    {
      v5 = (_QWORD *)*v4;
      operator delete(v4, (const struct std::nothrow_t *)0x20);
      v4 = v5;
    }
    while ( v5 );
  }
  operator delete(*((void **)this + 2), (const struct std::nothrow_t *)0x20);
}

```

## disassembly

```asm
0x18001eb6c  mov     [rsp+arg_0], rbx
0x18001eb71  push    rdi
0x18001eb72  sub     rsp, 20h
0x18001eb76  mov     rdi, rcx
0x18001eb79  xor     edx, edx
0x18001eb7b  add     rcx, 20h ; ' '
0x18001eb7f  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18001eb84  mov     rbx, [rdi+20h]
0x18001eb88  test    rbx, rbx
0x18001eb8b  jz      short loc_18001EBB0
0x18001eb8d  mov     edx, 1; fCancelPendingCallbacks
0x18001eb92  mov     rcx, rbx; pwk
0x18001eb95  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18001eb9c  nop     dword ptr [rax+rax+00h]
0x18001eba1  mov     rcx, rbx; pwk
0x18001eba4  call    cs:__imp_CloseThreadpoolWork
0x18001ebab  nop     dword ptr [rax+rax+00h]
0x18001ebb0  mov     rcx, [rdi+10h]
0x18001ebb4  mov     rax, [rcx+8]
0x18001ebb8  and     qword ptr [rax], 0
0x18001ebbc  mov     rcx, [rcx]; void *
0x18001ebbf  test    rcx, rcx
0x18001ebc2  jz      short loc_18001EBD9
0x18001ebc4  mov     rbx, [rcx]
0x18001ebc7  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18001ebcc  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001ebd1  mov     rcx, rbx
0x18001ebd4  test    rbx, rbx
0x18001ebd7  jnz     short loc_18001EBC4
0x18001ebd9  mov     rcx, [rdi+10h]; void *
0x18001ebdd  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18001ebe2  mov     rbx, [rsp+28h+arg_0]
0x18001ebe7  add     rsp, 20h
0x18001ebeb  pop     rdi
0x18001ebec  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
