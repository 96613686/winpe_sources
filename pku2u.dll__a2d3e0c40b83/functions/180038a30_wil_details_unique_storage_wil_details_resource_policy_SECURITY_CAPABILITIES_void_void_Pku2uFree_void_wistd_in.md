# wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(void)

- ea: `0x180038a30`
- end: `0x180038a47`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_SECURITY_CAPABILITIES@@$$A6AXPEAX@Z$1?Pku2uFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800385ac`
- `0x18003866c`
- `0x18003872c`
- `0x1800387ec`
- `0x1800389c0`
- `0x1800394b8`
- `0x180039f20`

## callees

- `0x1800057f0`
- `0x180038a30`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_SECURITY_CAPABILITIES *,void (void *),&void Pku2uFree(void *),wistd::integral_constant<unsigned __int64,0>,_SECURITY_CAPABILITIES *,_SECURITY_CAPABILITIES *,0,std::nullptr_t>>(
        void **a1)
{
  void *v1; // rcx

  v1 = *a1;
  if ( v1 )
    Pku2uFree(v1);
}

```

## disassembly

```asm
0x180038a30  sub     rsp, 28h
0x180038a34  mov     rcx, [rcx]; void *
0x180038a37  test    rcx, rcx
0x180038a3a  jz      short loc_180038A42
0x180038a3c  call    ?Pku2uFree@@YAXPEAX@Z; Pku2uFree(void *)
0x180038a41  nop
0x180038a42  add     rsp, 28h
0x180038a46  retn
```
