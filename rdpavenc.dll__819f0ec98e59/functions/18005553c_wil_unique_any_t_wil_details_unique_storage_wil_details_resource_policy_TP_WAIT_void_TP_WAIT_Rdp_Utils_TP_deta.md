# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>(void)

- ea: `0x18005553c`
- end: `0x180055575`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `57`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180087850`
- `0x1800878d0`

## callees

- `0x18005553c`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055569`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055569`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180055552`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180055552`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180055560`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180055560`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>(
        PTP_WAIT *a1)
{
  struct _TP_WAIT *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SetThreadpoolWait(*a1, 0, 0);
    WaitForThreadpoolWaitCallbacks(v1, 1);
    CloseThreadpoolWait(v1);
  }
}

```

## disassembly

```asm
0x18005553c  push    rbx
0x18005553e  sub     rsp, 20h
0x180055542  mov     rbx, [rcx]
0x180055545  test    rbx, rbx
0x180055548  jz      short loc_18005556F
0x18005554a  xor     r8d, r8d; pftTimeout
0x18005554d  xor     edx, edx; h
0x18005554f  mov     rcx, rbx; pwa
0x180055552  call    cs:__imp_SetThreadpoolWait
0x180055558  mov     edx, 1; fCancelPendingCallbacks
0x18005555d  mov     rcx, rbx; pwa
0x180055560  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180055566  mov     rcx, rbx; pwa
0x180055569  call    cs:__imp_CloseThreadpoolWait
0x18005556f  add     rsp, 20h
0x180055573  pop     rbx
0x180055574  retn
```
