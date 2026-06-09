# wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(_SC_NOTIFICATION_REGISTRATION *)

- ea: `0x1800074e0`
- end: `0x180007538`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_SC_NOTIFICATION_REGISTRATION@@P6AXPEAU1@@Z$1?UnsubscribeServiceChangeNotifications@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_SC_NOTIFICATION_REGISTRATION@@@Z`
- size: `88`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001f188`
- `0x180022b2c`
- `0x180026c04`
- `0x180029678`

## callees

- `0x1800074e0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007502`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007515`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007515`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18000750d`
- `api-ms-win-service-private-l1-1-0!UnsubscribeServiceChangeNotifications` at `0x18000750d`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_SC_NOTIFICATION_REGISTRATION *,void (*)(_SC_NOTIFICATION_REGISTRATION *),&void UnsubscribeServiceChangeNotifications(_SC_NOTIFICATION_REGISTRATION *),wistd::integral_constant<unsigned __int64,0>,_SC_NOTIFICATION_REGISTRATION *,_SC_NOTIFICATION_REGISTRATION *,0,std::nullptr_t>>::reset(
        __int64 *a1,
        __int64 a2)
{
  __int64 v2; // rsi
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    UnsubscribeServiceChangeNotifications(v2);
    SetLastError(LastError);
    *a1 = a2;
  }
  else
  {
    *a1 = a2;
  }
}

```

## disassembly

```asm
0x1800074e0  mov     [rsp+arg_8], rbx
0x1800074e5  mov     [rsp+arg_10], rbp
0x1800074ea  push    rsi
0x1800074eb  sub     rsp, 20h
0x1800074ef  mov     rsi, [rcx]
0x1800074f2  mov     rbp, rdx
0x1800074f5  mov     rbx, rcx
0x1800074f8  test    rsi, rsi
0x1800074fb  jz      short loc_180007533
0x1800074fd  mov     [rsp+28h+arg_0], rdi
0x180007502  call    cs:__imp_GetLastError
0x180007508  mov     rcx, rsi
0x18000750b  mov     edi, eax
0x18000750d  call    cs:__imp_UnsubscribeServiceChangeNotifications
0x180007513  mov     ecx, edi; dwErrCode
0x180007515  call    cs:__imp_SetLastError
0x18000751b  mov     rdi, [rsp+28h+arg_0]
0x180007520  mov     [rbx], rbp
0x180007523  mov     rbx, [rsp+28h+arg_8]
0x180007528  mov     rbp, [rsp+28h+arg_10]
0x18000752d  add     rsp, 20h
0x180007531  pop     rsi
0x180007532  retn
0x180007533  mov     [rcx], rbp
0x180007536  jmp     short loc_180007523
```
