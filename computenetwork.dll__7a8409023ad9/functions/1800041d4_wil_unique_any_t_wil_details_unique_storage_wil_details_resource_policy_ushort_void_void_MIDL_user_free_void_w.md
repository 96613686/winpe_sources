# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)

- ea: `0x1800041d4`
- end: `0x1800041ea`
- name: `??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?MIDL_user_free@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ`
- size: `22`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000d24d`
- `0x18000d294`
- `0x18000d2db`
- `0x18000d92e`
- `0x18000deef`
- `0x18000e00a`

## callees

- `0x1800041d4`
- `0x180009d10`

## pseudocode

```c
void __fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void MIDL_user_free(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    MIDL_user_free(v1);
}

```

## disassembly

```asm
0x1800041d4  sub     rsp, 28h
0x1800041d8  mov     rcx, [rcx]; void *
0x1800041db  test    rcx, rcx
0x1800041de  jz      short loc_1800041E5
0x1800041e0  call    MIDL_user_free
0x1800041e5  add     rsp, 28h
0x1800041e9  retn
```
