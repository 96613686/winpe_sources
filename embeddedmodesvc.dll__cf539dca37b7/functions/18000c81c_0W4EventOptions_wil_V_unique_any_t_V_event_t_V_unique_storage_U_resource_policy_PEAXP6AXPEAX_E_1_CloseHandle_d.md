# ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z

- ea: `0x18000c81c`
- end: `0x18000c87f`
- name: `??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z`
- size: `99`
- prototype: `_QWORD *__fastcall(_QWORD *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d2e8`
- `0x18001029c`

## callees

- `0x180006c14`
- `0x18000c26c`
- `0x18000c81c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000c846`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000c846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c854`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c854`

## pseudocode

```c
_QWORD *__fastcall ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
        _QWORD *a1,
        int *a2)
{
  int v3; // r8d
  void *v4; // rdx
  HANDLE Event; // rdi
  unsigned int v6; // r8d
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v3 = *a2;
  *a1 = 0;
  Event = CreateEventExW(0, 0, v3 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(retaddr, v4, v6, v7);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Event);
  return a1;
}

```

## disassembly

```asm
0x18000c81c  mov     [rsp+arg_8], rbx
0x18000c821  mov     [rsp+arg_0], rcx
0x18000c826  push    rdi
0x18000c827  sub     rsp, 20h
0x18000c82b  mov     rbx, rcx
0x18000c82e  mov     r8d, [rdx]
0x18000c831  mov     qword ptr [rcx], 0
0x18000c838  and     r8d, 3; dwFlags
0x18000c83c  xor     edx, edx; lpName
0x18000c83e  xor     ecx, ecx; lpEventAttributes
0x18000c840  mov     r9d, 1F0003h; dwDesiredAccess
0x18000c846  call    cs:__imp_CreateEventExW
0x18000c84c  mov     rdi, rax
0x18000c84f  test    rax, rax
0x18000c852  jz      short loc_18000C874
0x18000c854  call    cs:__imp_GetLastError
0x18000c85a  mov     rdx, rdi
0x18000c85d  mov     rcx, rbx
0x18000c860  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000c865  nop
0x18000c866  mov     rax, rbx
0x18000c869  mov     rbx, [rsp+28h+arg_8]
0x18000c86e  add     rsp, 20h
0x18000c872  pop     rdi
0x18000c873  retn
0x18000c874  mov     rcx, [rsp+28h]; this
0x18000c879  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
