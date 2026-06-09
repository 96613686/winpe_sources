# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180046dbc`
- end: `0x180046e4b`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `143`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180045c80`
- `0x180054ee0`
- `0x18005e3a0`
- `0x18005ed58`
- `0x18007dcd8`

## callees

- `0x18001017c`
- `0x1800115c4`
- `0x180046dbc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180046dd8`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180046dd8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046e0b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180046e0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046df4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046de6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180046df4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046dff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180046dff`

## string_xrefs

- `0x180046e22`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180046e39`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2)
{
  HANDLE Event; // rbp
  const char *v4; // r9
  void *v5; // rbx
  DWORD LastError; // esi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  Event = CreateEventExW(0, 0, a2 & 3, 0x1F0003u);
  if ( !Event )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v4);
  GetLastError();
  v5 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(LastError);
  }
  *a1 = Event;
}

```

## disassembly

```asm
0x180046dbc  push    rbx
0x180046dbe  push    rbp
0x180046dbf  push    rsi
0x180046dc0  push    rdi
0x180046dc1  sub     rsp, 28h
0x180046dc5  and     edx, 3
0x180046dc8  mov     rdi, rcx
0x180046dcb  mov     r8d, edx; dwFlags
0x180046dce  mov     r9d, 1F0003h; dwDesiredAccess
0x180046dd4  xor     edx, edx; lpName
0x180046dd6  xor     ecx, ecx; lpEventAttributes
0x180046dd8  call    cs:__imp_CreateEventExW
0x180046dde  mov     rbp, rax
0x180046de1  test    rax, rax
0x180046de4  jz      short loc_180046E34
0x180046de6  call    cs:__imp_GetLastError
0x180046dec  mov     rbx, [rdi]
0x180046def  test    rbx, rbx
0x180046df2  jz      short loc_180046E11
0x180046df4  call    cs:__imp_GetLastError
0x180046dfa  mov     rcx, rbx; hObject
0x180046dfd  mov     esi, eax
0x180046dff  call    cs:__imp_CloseHandle
0x180046e05  test    eax, eax
0x180046e07  jz      short loc_180046E1D
0x180046e09  mov     ecx, esi; dwErrCode
0x180046e0b  call    cs:__imp_SetLastError
0x180046e11  mov     [rdi], rbp
0x180046e14  add     rsp, 28h
0x180046e18  pop     rdi
0x180046e19  pop     rsi
0x180046e1a  pop     rbp
0x180046e1b  pop     rbx
0x180046e1c  retn
0x180046e1d  mov     rcx, [rsp+48h]; this
0x180046e22  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180046e29  mov     edx, 0A0Bh; void *
0x180046e2e  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180046e34  mov     rcx, [rsp+48h]; this
0x180046e39  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180046e40  mov     edx, 1CC8h; void *
0x180046e45  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
