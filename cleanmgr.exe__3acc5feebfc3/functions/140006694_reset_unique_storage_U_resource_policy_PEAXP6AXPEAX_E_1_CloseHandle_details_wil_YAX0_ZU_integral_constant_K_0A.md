# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x140006694`
- end: `0x1400066e0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140004238`
- `0x140004510`
- `0x140006628`
- `0x140007260`

## callees

- `0x140003eb4`
- `0x14000418c`
- `0x1400043b4`
- `0x140006694`

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
0x140006694  mov     [rsp+arg_8], rbx
0x140006699  mov     [rsp+arg_10], rsi
0x14000669e  push    rdi
0x14000669f  sub     rsp, 20h
0x1400066a3  mov     rdi, [rcx]
0x1400066a6  mov     rsi, rdx
0x1400066a9  mov     rbx, rcx
0x1400066ac  test    rdi, rdi
0x1400066af  jz      short loc_1400066CD
0x1400066b1  lea     rcx, [rsp+28h+arg_0]; this
0x1400066b6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400066bb  mov     rcx, rdi; this
0x1400066be  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x1400066c3  lea     rcx, [rsp+28h+arg_0]; this
0x1400066c8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1400066cd  mov     [rbx], rsi
0x1400066d0  mov     rbx, [rsp+28h+arg_8]
0x1400066d5  mov     rsi, [rsp+28h+arg_10]
0x1400066da  add     rsp, 20h
0x1400066de  pop     rdi
0x1400066df  retn
```
