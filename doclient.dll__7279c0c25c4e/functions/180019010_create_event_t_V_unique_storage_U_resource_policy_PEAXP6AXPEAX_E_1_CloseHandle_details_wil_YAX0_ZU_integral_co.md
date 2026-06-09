# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180019010`
- end: `0x1800190cc`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@QEAAXW4EventOptions@2@PEB_WPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `188`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000516c`
- `0x1800947a0`
- `0x1800a8694`
- `0x1800cacd4`

## callees

- `0x18000a4e0`
- `0x180019010`
- `0x180019318`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001907a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001907a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001904d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001906f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001904d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001906f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019086`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180019086`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001903f`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18001903f`

## pseudocode

```c
void __fastcall _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil__QEAAXW4EventOptions_2_PEB_WPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        void **a1,
        char a2,
        const WCHAR *a3,
        struct _SECURITY_ATTRIBUTES *a4,
        bool *a5)
{
  void *v6; // rdx
  HANDLE Event; // rbp
  unsigned int v8; // r8d
  const char *v9; // r9
  DWORD LastError; // eax
  void *v11; // rbx
  DWORD v12; // esi
  unsigned int v13; // r8d
  const char *v14; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  Event = CreateEventExW(a4, a3, a2 & 3, 0x1F0003u);
  if ( !Event )
  {
    if ( a5 )
      *a5 = 0;
    wil::details::in1diag3::Throw_GetLastError(retaddr, v6, v8, v9);
  }
  LastError = GetLastError();
  if ( a5 )
    *a5 = LastError == 183;
  v11 = *a1;
  if ( *a1 )
  {
    v12 = GetLastError();
    if ( !CloseHandle(v11) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v13, v14);
    SetLastError(v12);
  }
  *a1 = Event;
}

```

## disassembly

```asm
0x180019010  mov     [rsp+arg_0], rbx
0x180019015  mov     [rsp+arg_8], rbp
0x18001901a  mov     [rsp+arg_10], rsi
0x18001901f  push    rdi
0x180019020  sub     rsp, 20h
0x180019024  and     edx, 3
0x180019027  mov     r10, r9
0x18001902a  mov     rax, r8
0x18001902d  mov     rdi, rcx
0x180019030  mov     r8d, edx; dwFlags
0x180019033  mov     r9d, 1F0003h; dwDesiredAccess
0x180019039  mov     rdx, rax; lpName
0x18001903c  mov     rcx, r10; lpEventAttributes
0x18001903f  call    cs:__imp_CreateEventExW
0x180019045  mov     rbp, rax
0x180019048  test    rax, rax
0x18001904b  jz      short loc_1800190B4
0x18001904d  call    cs:__imp_GetLastError
0x180019053  mov     rcx, [rsp+28h+arg_20]
0x180019058  test    rcx, rcx
0x18001905b  jz      short loc_180019067
0x18001905d  cmp     eax, 0B7h
0x180019062  setz    al
0x180019065  mov     [rcx], al
0x180019067  mov     rbx, [rdi]
0x18001906a  test    rbx, rbx
0x18001906d  jz      short loc_18001908C
0x18001906f  call    cs:__imp_GetLastError
0x180019075  mov     rcx, rbx; hObject
0x180019078  mov     esi, eax
0x18001907a  call    cs:__imp_CloseHandle
0x180019080  test    eax, eax
0x180019082  jz      short loc_1800190A4
0x180019084  mov     ecx, esi; dwErrCode
0x180019086  call    cs:__imp_SetLastError
0x18001908c  mov     rbx, [rsp+28h+arg_0]
0x180019091  mov     rsi, [rsp+28h+arg_10]
0x180019096  mov     [rdi], rbp
0x180019099  mov     rbp, [rsp+28h+arg_8]
0x18001909e  add     rsp, 20h
0x1800190a2  pop     rdi
0x1800190a3  retn
0x1800190a4  mov     rcx, [rsp+28h]; this
0x1800190a9  mov     edx, 9D1h; void *
0x1800190ae  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800190b4  mov     rax, [rsp+28h+arg_20]
0x1800190b9  test    rax, rax
0x1800190bc  jz      short loc_1800190C1
0x1800190be  mov     byte ptr [rax], 0
0x1800190c1  mov     rcx, [rsp+28h]; this
0x1800190c6  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
