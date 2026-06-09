# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x180009fe8`
- end: `0x18000a034`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `76`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800043f8`
- `0x180004564`
- `0x1800053fc`
- `0x180009df4`

## callees

- `0x180003c6c`
- `0x180004298`
- `0x180005180`
- `0x180009fe8`

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
0x180009fe8  mov     [rsp+arg_8], rbx
0x180009fed  mov     [rsp+arg_10], rsi
0x180009ff2  push    rdi
0x180009ff3  sub     rsp, 20h
0x180009ff7  mov     rdi, [rcx]
0x180009ffa  mov     rsi, rdx
0x180009ffd  mov     rbx, rcx
0x18000a000  test    rdi, rdi
0x18000a003  jz      short loc_18000A021
0x18000a005  lea     rcx, [rsp+28h+arg_0]; this
0x18000a00a  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a00f  mov     rcx, rdi; this
0x18000a012  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000a017  lea     rcx, [rsp+28h+arg_0]; this
0x18000a01c  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a021  mov     [rbx], rsi
0x18000a024  mov     rbx, [rsp+28h+arg_8]
0x18000a029  mov     rsi, [rsp+28h+arg_10]
0x18000a02e  add     rsp, 20h
0x18000a032  pop     rdi
0x18000a033  retn
```
