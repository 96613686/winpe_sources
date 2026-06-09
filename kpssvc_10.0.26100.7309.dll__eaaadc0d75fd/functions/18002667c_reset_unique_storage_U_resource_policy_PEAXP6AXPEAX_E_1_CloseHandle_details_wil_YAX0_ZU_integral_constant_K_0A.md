# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x18002667c`
- end: `0x1800266f6`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `122`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001c684`
- `0x18001ca7c`
- `0x18001ce90`
- `0x180024834`
- `0x1800249c4`

## callees

- `0x180026398`
- `0x18002667c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800266c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800266c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002669e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002669e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800266af`

## pseudocode

```c
void __fastcall _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
        void **a1,
        void *a2)
{
  void *v2; // rdi
  DWORD LastError; // ebp
  __int64 v6; // r8
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = *a1;
  if ( *a1 )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v2) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9DD, v6, v7);
    SetLastError(LastError);
  }
  *a1 = a2;
}

```

## disassembly

```asm
0x18002667c  mov     [rsp+arg_0], rbx
0x180026681  mov     [rsp+arg_8], rbp
0x180026686  mov     [rsp+arg_10], rsi
0x18002668b  push    rdi
0x18002668c  sub     rsp, 20h
0x180026690  mov     rdi, [rcx]
0x180026693  mov     rsi, rdx
0x180026696  mov     rbx, rcx
0x180026699  test    rdi, rdi
0x18002669c  jz      short loc_1800266CD
0x18002669e  call    cs:__imp_GetLastError
0x1800266a5  nop     dword ptr [rax+rax+00h]
0x1800266aa  mov     rcx, rdi; hObject
0x1800266ad  mov     ebp, eax
0x1800266af  call    cs:__imp_CloseHandle
0x1800266b6  nop     dword ptr [rax+rax+00h]
0x1800266bb  test    eax, eax
0x1800266bd  jz      short loc_1800266E6
0x1800266bf  mov     ecx, ebp; dwErrCode
0x1800266c1  call    cs:__imp_SetLastError
0x1800266c8  nop     dword ptr [rax+rax+00h]
0x1800266cd  mov     rbp, [rsp+28h+arg_8]
0x1800266d2  mov     [rbx], rsi
0x1800266d5  mov     rbx, [rsp+28h+arg_0]
0x1800266da  mov     rsi, [rsp+28h+arg_10]
0x1800266df  add     rsp, 20h
0x1800266e3  pop     rdi
0x1800266e4  retn
0x1800266e6  mov     rcx, [rsp+28h]; this
0x1800266eb  mov     edx, 9DDh; void *
0x1800266f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
