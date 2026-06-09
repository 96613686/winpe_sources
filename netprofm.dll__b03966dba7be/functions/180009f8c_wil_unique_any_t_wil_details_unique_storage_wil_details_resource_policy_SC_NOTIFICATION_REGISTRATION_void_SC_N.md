# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>(void)

- ea: `0x180009f8c`
- end: `0x180009f9c`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `16`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18004092e`

## callees

- `0x180009f8c`

## import_xrefs

- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x180009f95`

## pseudocode

```c
__int64 __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>>(
        _QWORD *a1)
{
  __int64 result; // rax

  if ( *a1 )
    return UnsubscribeServiceChangeNotifications();
  return result;
}

```

## disassembly

```asm
0x180009f8c  mov     rcx, [rcx]
0x180009f8f  test    rcx, rcx
0x180009f92  jnz     short loc_180009F95
0x180009f94  retn
0x180009f95  jmp     cs:__imp_UnsubscribeServiceChangeNotifications
```
