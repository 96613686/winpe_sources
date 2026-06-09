# wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)

- ea: `0x140005990`
- end: `0x1400059f5`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z`
- size: `101`
- prototype: `void __fastcall(struct _TP_TIMER **, struct _TP_TIMER *)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000d6e4`
- `0x14000d7c0`
- `0x140016cbc`

## callees

- `0x140005990`
- `0x1400059fc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400059d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400059d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400059c5`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        struct _TP_TIMER **a1,
        struct _TP_TIMER *a2)
{
  struct _TP_TIMER *v2; // rbp
  DWORD LastError; // edi

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(v2);
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
0x140005990  mov     [rsp+arg_8], rbx
0x140005995  mov     [rsp+arg_10], rbp
0x14000599a  push    rsi
0x14000599b  sub     rsp, 20h
0x14000599f  mov     rbp, [rcx]
0x1400059a2  mov     rsi, rdx
0x1400059a5  mov     rbx, rcx
0x1400059a8  test    rbp, rbp
0x1400059ab  jnz     short loc_1400059C0
0x1400059ad  mov     [rcx], rdx
0x1400059b0  mov     rbx, [rsp+28h+arg_8]
0x1400059b5  mov     rbp, [rsp+28h+arg_10]
0x1400059ba  add     rsp, 20h
0x1400059be  pop     rsi
0x1400059bf  retn
0x1400059c0  mov     [rsp+28h+arg_0], rdi
0x1400059c5  call    cs:__imp_GetLastError
0x1400059cb  mov     rcx, rbp; pti
0x1400059ce  mov     edi, eax
0x1400059d0  call    ?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAXPEAU_TP_TIMER@@@Z; wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *)
0x1400059d5  mov     ecx, edi; dwErrCode
0x1400059d7  call    cs:__imp_SetLastError
0x1400059dd  mov     rdi, [rsp+28h+arg_0]
0x1400059e2  mov     rbp, [rsp+28h+arg_10]
0x1400059e7  mov     [rbx], rsi
0x1400059ea  mov     rbx, [rsp+28h+arg_8]
0x1400059ef  add     rsp, 20h
0x1400059f3  pop     rsi
0x1400059f4  retn
```
