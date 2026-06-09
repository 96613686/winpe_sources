# wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)

- ea: `0x1800125e8`
- end: `0x18001263e`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z`
- size: `86`
- prototype: `void __fastcall(struct _TP_WORK **, struct _TP_WORK *)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001ac4c`
- `0x18001af90`
- `0x18001b234`

## callees

- `0x1800125e8`
- `0x18001f68c`
- `0x18001f8c0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180012626`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180012626`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<2>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
        struct _TP_WORK **a1,
        struct _TP_WORK *a2)
{
  struct _TP_WORK *v2; // rdi
  char v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v5);
    CloseThreadpoolWork(v2);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v5);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x1800125e8  mov     [rsp+arg_8], rbx
0x1800125ed  mov     [rsp+arg_10], rsi
0x1800125f2  push    rdi
0x1800125f3  sub     rsp, 20h
0x1800125f7  mov     rdi, [rcx]
0x1800125fa  mov     rsi, rdx
0x1800125fd  mov     rbx, rcx
0x180012600  test    rdi, rdi
0x180012603  jnz     short loc_180012619
0x180012605  mov     [rbx], rsi
0x180012608  mov     rbx, [rsp+28h+arg_8]
0x18001260d  mov     rsi, [rsp+28h+arg_10]
0x180012612  add     rsp, 20h
0x180012616  pop     rdi
0x180012617  retn
0x180012619  lea     rcx, [rsp+28h+arg_0]; this
0x18001261e  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180012623  mov     rcx, rdi; pwk
0x180012626  call    cs:__imp_CloseThreadpoolWork
0x18001262d  nop     dword ptr [rax+rax+00h]
0x180012632  lea     rcx, [rsp+28h+arg_0]; this
0x180012637  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18001263c  jmp     short loc_180012605
```
