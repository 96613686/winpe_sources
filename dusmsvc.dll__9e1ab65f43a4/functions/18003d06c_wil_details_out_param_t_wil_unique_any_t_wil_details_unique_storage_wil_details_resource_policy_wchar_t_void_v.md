# wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(void)

- ea: `0x18003d06c`
- end: `0x18003d0c0`
- name: `??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `84`
- prototype: `void __fastcall(void ***)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003d244`

## callees

- `0x18000a810`
- `0x18000aaf4`
- `0x18003d06c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d09d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003d09d`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
        void ***a1)
{
  void **v1; // rbx
  void **v2; // rsi
  void *v3; // rdi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = *a1;
    v2 = a1[1];
    v3 = **a1;
    if ( v3 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v4);
      CoTaskMemFree(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v4);
    }
    *v1 = v2;
  }
}

```

## disassembly

```asm
0x18003d06c  mov     [rsp+arg_8], rbx
0x18003d071  mov     [rsp+arg_10], rsi
0x18003d076  push    rdi
0x18003d077  sub     rsp, 20h
0x18003d07b  cmp     byte ptr [rcx+10h], 0
0x18003d07f  jz      short loc_18003D0B0
0x18003d081  mov     rbx, [rcx]
0x18003d084  mov     rsi, [rcx+8]
0x18003d088  mov     rdi, [rbx]
0x18003d08b  test    rdi, rdi
0x18003d08e  jz      short loc_18003D0AD
0x18003d090  lea     rcx, [rsp+28h+arg_0]; this
0x18003d095  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18003d09a  mov     rcx, rdi; pv
0x18003d09d  call    cs:__imp_CoTaskMemFree
0x18003d0a3  lea     rcx, [rsp+28h+arg_0]; this
0x18003d0a8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18003d0ad  mov     [rbx], rsi
0x18003d0b0  mov     rbx, [rsp+28h+arg_8]
0x18003d0b5  mov     rsi, [rsp+28h+arg_10]
0x18003d0ba  add     rsp, 20h
0x18003d0be  pop     rdi
0x18003d0bf  retn
```
