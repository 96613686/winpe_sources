# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x18000a610`
- end: `0x18000a68b`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000cd54`

## callees

- `0x18000a610`
- `0x18000a760`
- `0x18000a784`
- `0x18000bbc4`
- `0x18000ec48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a637`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000a637`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a645`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a645`

## pseudocode

```c
__int64 _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        wil::details **a1,
        char a2,
        __int64 a3,
        ...)
{
  wil::details *v4; // rcx
  wil::details *Event; // rsi
  wil::details *v6; // rbx
  void *v7; // rdx
  va_list va; // [rsp+48h] [rbp+20h] BYREF

  va_start(va, a3);
  Event = (wil::details *)CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v4);
  GetLastError();
  v6 = *a1;
  if ( *a1 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)va);
    wil::details::CloseHandle(v6, v7);
    wil::last_error_context::~last_error_context((wil::last_error_context *)va);
  }
  *a1 = Event;
  return 0;
}

```

## disassembly

```asm
0x18000a610  mov     [rsp+arg_0], rbx
0x18000a615  mov     [rsp+arg_8], rsi
0x18000a61a  mov     [rsp+arg_18], r9
0x18000a61f  push    rdi
0x18000a620  sub     rsp, 20h
0x18000a624  and     edx, 3
0x18000a627  mov     rdi, rcx
0x18000a62a  mov     r8d, edx; dwFlags
0x18000a62d  mov     r9d, 1F0003h; dwDesiredAccess
0x18000a633  xor     edx, edx; lpName
0x18000a635  xor     ecx, ecx; lpEventAttributes
0x18000a637  call    cs:__imp_CreateEventExW
0x18000a63d  mov     rsi, rax
0x18000a640  test    rax, rax
0x18000a643  jz      short loc_18000A676
0x18000a645  call    cs:__imp_GetLastError
0x18000a64b  mov     rbx, [rdi]
0x18000a64e  test    rbx, rbx
0x18000a651  jz      short loc_18000A66F
0x18000a653  lea     rcx, [rsp+28h+arg_18]; this
0x18000a658  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000a65d  mov     rcx, rbx; this
0x18000a660  call    ?CloseHandle@details@wil@@YAXPEAX@Z; wil::details::CloseHandle(void *)
0x18000a665  lea     rcx, [rsp+28h+arg_18]; this
0x18000a66a  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000a66f  mov     [rdi], rsi
0x18000a672  xor     eax, eax
0x18000a674  jmp     short loc_18000A67B
0x18000a676  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x18000a67b  mov     rbx, [rsp+28h+arg_0]
0x18000a680  mov     rsi, [rsp+28h+arg_8]
0x18000a685  add     rsp, 20h
0x18000a689  pop     rdi
0x18000a68a  retn
```
