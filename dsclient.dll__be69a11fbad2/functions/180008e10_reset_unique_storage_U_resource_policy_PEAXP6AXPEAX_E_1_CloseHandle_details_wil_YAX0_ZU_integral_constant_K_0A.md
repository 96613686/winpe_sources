# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180008e10`
- end: `0x180008e5c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180004ce0`
- `0x180004e48`
- `0x1800051dc`
- `0x180008c04`

## callees

- `0x1800046d0`
- `0x180004be4`
- `0x180005014`
- `0x180008e10`

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
0x180008e10  mov     [rsp+arg_8], rbx
0x180008e15  mov     [rsp+arg_10], rsi
0x180008e1a  push    rdi
0x180008e1b  sub     rsp, 20h
0x180008e1f  mov     rdi, [rcx]
0x180008e22  mov     rsi, rdx
0x180008e25  mov     rbx, rcx
0x180008e28  test    rdi, rdi
0x180008e2b  jz      short loc_180008E49
0x180008e2d  lea     rcx, [rsp+28h+arg_0]; this
0x180008e32  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180008e37  mov     rcx, rdi; this
0x180008e3a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180008e3f  lea     rcx, [rsp+28h+arg_0]; this
0x180008e44  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180008e49  mov     [rbx], rsi
0x180008e4c  mov     rbx, [rsp+28h+arg_8]
0x180008e51  mov     rsi, [rsp+28h+arg_10]
0x180008e56  add     rsp, 20h
0x180008e5a  pop     rdi
0x180008e5b  retn
```
