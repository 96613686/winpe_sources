# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180008714`
- end: `0x180008761`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `77`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004914`
- `0x1800066b8`
- `0x180008698`

## callees

- `0x180006414`
- `0x180006658`
- `0x1800068fc`
- `0x180008714`

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
0x180008714  mov     [rsp+arg_8], rbx
0x180008719  mov     [rsp+arg_10], rsi
0x18000871e  push    rdi
0x18000871f  sub     rsp, 20h
0x180008723  mov     rdi, [rcx]
0x180008726  mov     rsi, rdx
0x180008729  mov     rbx, rcx
0x18000872c  test    rdi, rdi
0x18000872f  jz      short loc_18000874D
0x180008731  lea     rcx, [rsp+28h+arg_0]; this
0x180008736  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000873b  mov     rcx, rdi; this
0x18000873e  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008743  lea     rcx, [rsp+28h+arg_0]; this
0x180008748  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000874d  mov     [rbx], rsi
0x180008750  mov     rbx, [rsp+28h+arg_8]
0x180008755  mov     rsi, [rsp+28h+arg_10]
0x18000875a  add     rsp, 20h
0x18000875e  pop     rdi
0x18000875f  retn
```
