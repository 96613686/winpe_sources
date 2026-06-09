# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x1400053e0`
- end: `0x14000542c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140002f70`
- `0x14000486c`
- `0x140005388`

## callees

- `0x140002d44`
- `0x140002f50`
- `0x14000310c`
- `0x1400053e0`

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
0x1400053e0  mov     [rsp+arg_8], rbx
0x1400053e5  mov     [rsp+arg_10], rsi
0x1400053ea  push    rdi
0x1400053eb  sub     rsp, 20h
0x1400053ef  mov     rdi, [rcx]
0x1400053f2  mov     rsi, rdx
0x1400053f5  mov     rbx, rcx
0x1400053f8  test    rdi, rdi
0x1400053fb  jz      short loc_140005419
0x1400053fd  lea     rcx, [rsp+28h+arg_0]; this
0x140005402  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x140005407  mov     rcx, rdi; this
0x14000540a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000540f  lea     rcx, [rsp+28h+arg_0]; this
0x140005414  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140005419  mov     [rbx], rsi
0x14000541c  mov     rbx, [rsp+28h+arg_8]
0x140005421  mov     rsi, [rsp+28h+arg_10]
0x140005426  add     rsp, 20h
0x14000542a  pop     rdi
0x14000542b  retn
```
