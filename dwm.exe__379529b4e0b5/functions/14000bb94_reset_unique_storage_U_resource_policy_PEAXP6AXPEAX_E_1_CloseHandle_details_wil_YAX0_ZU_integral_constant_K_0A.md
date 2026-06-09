# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x14000bb94`
- end: `0x14000bbe0`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140007adc`
- `0x140007c48`
- `0x140007f8c`
- `0x14000b948`
- `0x14000e534`

## callees

- `0x1400074b0`
- `0x14000782c`
- `0x140007db4`
- `0x14000bb94`

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
0x14000bb94  mov     [rsp+arg_8], rbx
0x14000bb99  mov     [rsp+arg_10], rsi
0x14000bb9e  push    rdi
0x14000bb9f  sub     rsp, 20h
0x14000bba3  mov     rdi, [rcx]
0x14000bba6  mov     rsi, rdx
0x14000bba9  mov     rbx, rcx
0x14000bbac  test    rdi, rdi
0x14000bbaf  jz      short loc_14000BBCD
0x14000bbb1  lea     rcx, [rsp+28h+arg_0]; this
0x14000bbb6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000bbbb  mov     rcx, rdi; this
0x14000bbbe  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x14000bbc3  lea     rcx, [rsp+28h+arg_0]; this
0x14000bbc8  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000bbcd  mov     [rbx], rsi
0x14000bbd0  mov     rbx, [rsp+28h+arg_8]
0x14000bbd5  mov     rsi, [rsp+28h+arg_10]
0x14000bbda  add     rsp, 20h
0x14000bbde  pop     rdi
0x14000bbdf  retn
```
