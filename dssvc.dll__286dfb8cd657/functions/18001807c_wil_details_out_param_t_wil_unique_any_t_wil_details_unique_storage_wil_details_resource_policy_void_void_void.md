# wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)

- ea: `0x18001807c`
- end: `0x1800180d0`
- name: `??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?FreeTransientObjectSecurityDescriptor@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ`
- size: `84`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800180f8`

## callees

- `0x1800041bc`
- `0x1800044f0`
- `0x18001807c`

## import_xrefs

- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800180ad`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x1800180ad`

## pseudocode

```c
void __fastcall wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void FreeTransientObjectSecurityDescriptor(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(
        __int64 **a1)
{
  __int64 *v1; // rbx
  __int64 *v2; // rsi
  __int64 v3; // rdi
  char v4; // [rsp+30h] [rbp+8h] BYREF

  if ( *((_BYTE *)a1 + 16) )
  {
    v1 = *a1;
    v2 = a1[1];
    v3 = **a1;
    if ( v3 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v4);
      FreeTransientObjectSecurityDescriptor(v3);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v4);
    }
    *v1 = (__int64)v2;
  }
}

```

## disassembly

```asm
0x18001807c  mov     [rsp+arg_8], rbx
0x180018081  mov     [rsp+arg_10], rsi
0x180018086  push    rdi
0x180018087  sub     rsp, 20h
0x18001808b  cmp     byte ptr [rcx+10h], 0
0x18001808f  jz      short loc_1800180C0
0x180018091  mov     rbx, [rcx]
0x180018094  mov     rsi, [rcx+8]
0x180018098  mov     rdi, [rbx]
0x18001809b  test    rdi, rdi
0x18001809e  jz      short loc_1800180BD
0x1800180a0  lea     rcx, [rsp+28h+arg_0]; this
0x1800180a5  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800180aa  mov     rcx, rdi
0x1800180ad  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x1800180b3  lea     rcx, [rsp+28h+arg_0]; this
0x1800180b8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800180bd  mov     [rbx], rsi
0x1800180c0  mov     rbx, [rsp+28h+arg_8]
0x1800180c5  mov     rsi, [rsp+28h+arg_10]
0x1800180ca  add     rsp, 20h
0x1800180ce  pop     rdi
0x1800180cf  retn
```
