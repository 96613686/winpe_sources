# wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)

- ea: `0x1800033c8`
- end: `0x18000341a`
- name: `??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z`
- size: `82`
- prototype: `void **__fastcall(void **, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003030`

## callees

- `0x1800033c8`
- `0x1800065d0`
- `0x1800067a4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800033f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800033f4`

## pseudocode

```c
void **__fastcall wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        void **a1,
        void **a2)
{
  void *v4; // rsi
  void *v5; // rbp
  char v7; // [rsp+50h] [rbp+8h] BYREF

  if ( a1 != a2 )
  {
    v4 = *a1;
    v5 = *a2;
    if ( *a1 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
      CoTaskMemFree(v4);
      wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
    }
    *a1 = v5;
    *a2 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x1800033c8  push    rbx
0x1800033ca  push    rbp
0x1800033cb  push    rsi
0x1800033cc  push    rdi
0x1800033cd  sub     rsp, 28h
0x1800033d1  mov     rdi, rdx
0x1800033d4  mov     rbx, rcx
0x1800033d7  cmp     rcx, rdx
0x1800033da  jz      short loc_18000340E
0x1800033dc  mov     rsi, [rcx]
0x1800033df  mov     rbp, [rdx]
0x1800033e2  test    rsi, rsi
0x1800033e5  jz      short loc_180003404
0x1800033e7  lea     rcx, [rsp+48h+arg_0]; this
0x1800033ec  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800033f1  mov     rcx, rsi; pv
0x1800033f4  call    cs:__imp_CoTaskMemFree
0x1800033fa  lea     rcx, [rsp+48h+arg_0]; this
0x1800033ff  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180003404  mov     [rbx], rbp
0x180003407  mov     qword ptr [rdi], 0
0x18000340e  mov     rax, rbx
0x180003411  add     rsp, 28h
0x180003415  pop     rdi
0x180003416  pop     rsi
0x180003417  pop     rbp
0x180003418  pop     rbx
0x180003419  retn
```
