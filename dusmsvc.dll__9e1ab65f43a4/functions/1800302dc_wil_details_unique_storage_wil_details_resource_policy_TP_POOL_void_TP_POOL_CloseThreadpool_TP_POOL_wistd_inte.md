# wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)

- ea: `0x1800302dc`
- end: `0x180030329`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z`
- size: `77`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002ec68`
- `0x18002f210`

## callees

- `0x18000a810`
- `0x18000aaf4`
- `0x1800302dc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180030306`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x180030306`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
        struct _TP_POOL **a1,
        struct _TP_POOL *a2)
{
  struct _TP_POOL *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CloseThreadpool(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800302dc  mov     [rsp+arg_8], rbx
0x1800302e1  mov     [rsp+arg_10], rsi
0x1800302e6  push    rdi
0x1800302e7  sub     rsp, 20h
0x1800302eb  mov     rdi, [rcx]
0x1800302ee  mov     rsi, rdx
0x1800302f1  mov     rbx, rcx
0x1800302f4  test    rdi, rdi
0x1800302f7  jz      short loc_180030316
0x1800302f9  lea     rcx, [rsp+28h+arg_0]; this
0x1800302fe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180030303  mov     rcx, rdi; ptpp
0x180030306  call    cs:__imp_CloseThreadpool
0x18003030c  lea     rcx, [rsp+28h+arg_0]; this
0x180030311  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180030316  mov     [rbx], rsi
0x180030319  mov     rbx, [rsp+28h+arg_8]
0x18003031e  mov     rsi, [rsp+28h+arg_10]
0x180030323  add     rsp, 20h
0x180030327  pop     rdi
0x180030328  retn
```
