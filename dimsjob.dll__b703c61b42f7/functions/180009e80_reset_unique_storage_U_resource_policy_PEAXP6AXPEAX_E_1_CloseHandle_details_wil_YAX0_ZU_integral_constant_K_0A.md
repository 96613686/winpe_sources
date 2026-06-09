# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180009e80`
- end: `0x180009ecc`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: `void __fastcall(wil::details **, wil::details *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180005ca8`
- `0x180005e10`
- `0x18000613c`
- `0x180009a6c`

## callees

- `0x1800035bc`
- `0x180003640`
- `0x180005f78`
- `0x180009e80`

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
0x180009e80  mov     [rsp+arg_8], rbx
0x180009e85  mov     [rsp+arg_10], rsi
0x180009e8a  push    rdi
0x180009e8b  sub     rsp, 20h
0x180009e8f  mov     rdi, [rcx]
0x180009e92  mov     rsi, rdx
0x180009e95  mov     rbx, rcx
0x180009e98  test    rdi, rdi
0x180009e9b  jz      short loc_180009EB9
0x180009e9d  lea     rcx, [rsp+28h+arg_0]; this
0x180009ea2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180009ea7  mov     rcx, rdi; this
0x180009eaa  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x180009eaf  lea     rcx, [rsp+28h+arg_0]; this
0x180009eb4  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180009eb9  mov     [rbx], rsi
0x180009ebc  mov     rbx, [rsp+28h+arg_8]
0x180009ec1  mov     rsi, [rsp+28h+arg_10]
0x180009ec6  add     rsp, 20h
0x180009eca  pop     rdi
0x180009ecb  retn
```
