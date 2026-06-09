# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18000a09c`
- end: `0x18000a0e8`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006308`
- `0x180006498`
- `0x18000682c`
- `0x180009f9c`

## callees

- `0x1800032ec`
- `0x18000338c`
- `0x180006628`
- `0x18000a09c`

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
0x18000a09c  mov     [rsp+arg_8], rbx
0x18000a0a1  mov     [rsp+arg_10], rsi
0x18000a0a6  push    rdi
0x18000a0a7  sub     rsp, 20h
0x18000a0ab  mov     rdi, [rcx]
0x18000a0ae  mov     rsi, rdx
0x18000a0b1  mov     rbx, rcx
0x18000a0b4  test    rdi, rdi
0x18000a0b7  jz      short loc_18000A0D5
0x18000a0b9  lea     rcx, [rsp+28h+arg_0]; this
0x18000a0be  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a0c3  mov     rcx, rdi; this
0x18000a0c6  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000a0cb  lea     rcx, [rsp+28h+arg_0]; this
0x18000a0d0  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a0d5  mov     [rbx], rsi
0x18000a0d8  mov     rbx, [rsp+28h+arg_8]
0x18000a0dd  mov     rsi, [rsp+28h+arg_10]
0x18000a0e2  add     rsp, 20h
0x18000a0e6  pop     rdi
0x18000a0e7  retn
```
