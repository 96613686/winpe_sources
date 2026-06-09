# wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)

- ea: `0x18003672c`
- end: `0x180036779`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task`

## callers

- `0x1800325b4`
- `0x180033ba4`
- `0x180036060`

## callees

- `0x18000a810`
- `0x18000aaf4`
- `0x18003672c`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180036756`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180036756`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    UnsubscribeServiceChangeNotifications(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18003672c  mov     [rsp+arg_8], rbx
0x180036731  mov     [rsp+arg_10], rsi
0x180036736  push    rdi
0x180036737  sub     rsp, 20h
0x18003673b  mov     rdi, [rcx]
0x18003673e  mov     rsi, rdx
0x180036741  mov     rbx, rcx
0x180036744  test    rdi, rdi
0x180036747  jz      short loc_180036766
0x180036749  lea     rcx, [rsp+28h+arg_0]; this
0x18003674e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180036753  mov     rcx, rdi
0x180036756  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x18003675c  lea     rcx, [rsp+28h+arg_0]; this
0x180036761  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180036766  mov     [rbx], rsi
0x180036769  mov     rbx, [rsp+28h+arg_8]
0x18003676e  mov     rsi, [rsp+28h+arg_10]
0x180036773  add     rsp, 20h
0x180036777  pop     rdi
0x180036778  retn
```
