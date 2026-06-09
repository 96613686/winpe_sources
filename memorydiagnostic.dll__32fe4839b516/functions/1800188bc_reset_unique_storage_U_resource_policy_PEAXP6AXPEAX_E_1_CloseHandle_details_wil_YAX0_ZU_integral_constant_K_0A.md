# ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z

- ea: `0x1800188bc`
- end: `0x180018936`
- name: `?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z`
- size: `122`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180007074`
- `0x180008cc4`
- `0x1800090b8`
- `0x18000a490`
- `0x180010788`
- `0x180010918`

## callees

- `0x1800162e8`
- `0x1800188bc`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800188ef`
- `KERNEL32!CloseHandle` at `0x1800188ef`
- `KERNEL32!GetLastError` at `0x1800188de`
- `KERNEL32!GetLastError` at `0x1800188de`
- `KERNEL32!SetLastError` at `0x180018901`
- `KERNEL32!SetLastError` at `0x180018901`

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
0x1800188bc  mov     [rsp+arg_0], rbx
0x1800188c1  mov     [rsp+arg_8], rbp
0x1800188c6  mov     [rsp+arg_10], rsi
0x1800188cb  push    rdi
0x1800188cc  sub     rsp, 20h
0x1800188d0  mov     rdi, [rcx]
0x1800188d3  mov     rsi, rdx
0x1800188d6  mov     rbx, rcx
0x1800188d9  test    rdi, rdi
0x1800188dc  jz      short loc_18001890D
0x1800188de  call    cs:__imp_GetLastError
0x1800188e5  nop     dword ptr [rax+rax+00h]
0x1800188ea  mov     rcx, rdi; hObject
0x1800188ed  mov     ebp, eax
0x1800188ef  call    cs:__imp_CloseHandle
0x1800188f6  nop     dword ptr [rax+rax+00h]
0x1800188fb  test    eax, eax
0x1800188fd  jz      short loc_180018926
0x1800188ff  mov     ecx, ebp; dwErrCode
0x180018901  call    cs:__imp_SetLastError
0x180018908  nop     dword ptr [rax+rax+00h]
0x18001890d  mov     rbp, [rsp+28h+arg_8]
0x180018912  mov     [rbx], rsi
0x180018915  mov     rbx, [rsp+28h+arg_0]
0x18001891a  mov     rsi, [rsp+28h+arg_10]
0x18001891f  add     rsp, 20h
0x180018923  pop     rdi
0x180018924  retn
0x180018926  mov     rcx, [rsp+28h]; this
0x18001892b  mov     edx, 9DDh; void *
0x180018930  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
