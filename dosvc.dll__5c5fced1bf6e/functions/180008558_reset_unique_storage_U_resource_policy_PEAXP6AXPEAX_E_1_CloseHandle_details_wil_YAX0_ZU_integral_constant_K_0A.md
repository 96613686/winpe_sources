# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180008558`
- end: `0x1800085a4`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006858`
- `0x18000789c`
- `0x180008500`

## callees

- `0x1800065d0`
- `0x1800067a4`
- `0x180006a08`
- `0x180008558`

## pseudocode

```c
void __fastcall _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        wil::details **a1,
        wil::details *a2)
{
  wil::details *v2; // rdi
  void *v5; // rdx
  char v6; // [rsp+30h] [rbp+8h] BYREF

  v2 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    wil::details::CloseHandle(v2, v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x180008558  mov     [rsp+arg_8], rbx
0x18000855d  mov     [rsp+arg_10], rsi
0x180008562  push    rdi
0x180008563  sub     rsp, 20h
0x180008567  mov     rdi, [rcx]
0x18000856a  mov     rsi, rdx
0x18000856d  mov     rbx, rcx
0x180008570  test    rdi, rdi
0x180008573  jz      short loc_180008591
0x180008575  lea     rcx, [rsp+28h+arg_0]; this
0x18000857a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000857f  mov     rcx, rdi; this
0x180008582  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008587  lea     rcx, [rsp+28h+arg_0]; this
0x18000858c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008591  mov     [rbx], rsi
0x180008594  mov     rbx, [rsp+28h+arg_8]
0x180008599  mov     rsi, [rsp+28h+arg_10]
0x18000859e  add     rsp, 20h
0x1800085a2  pop     rdi
0x1800085a3  retn
```
