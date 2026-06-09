# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x1800060e0`
- end: `0x18000612c`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180003a38`
- `0x18000525c`
- `0x180006088`
- `0x180008c58`

## callees

- `0x180003760`
- `0x18000398c`
- `0x180003be8`
- `0x1800060e0`

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
0x1800060e0  mov     [rsp+arg_8], rbx
0x1800060e5  mov     [rsp+arg_10], rsi
0x1800060ea  push    rdi
0x1800060eb  sub     rsp, 20h
0x1800060ef  mov     rdi, [rcx]
0x1800060f2  mov     rsi, rdx
0x1800060f5  mov     rbx, rcx
0x1800060f8  test    rdi, rdi
0x1800060fb  jz      short loc_180006119
0x1800060fd  lea     rcx, [rsp+28h+arg_0]; this
0x180006102  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180006107  mov     rcx, rdi; this
0x18000610a  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000610f  lea     rcx, [rsp+28h+arg_0]; this
0x180006114  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180006119  mov     [rbx], rsi
0x18000611c  mov     rbx, [rsp+28h+arg_8]
0x180006121  mov     rsi, [rsp+28h+arg_10]
0x180006126  add     rsp, 20h
0x18000612a  pop     rdi
0x18000612b  retn
```
