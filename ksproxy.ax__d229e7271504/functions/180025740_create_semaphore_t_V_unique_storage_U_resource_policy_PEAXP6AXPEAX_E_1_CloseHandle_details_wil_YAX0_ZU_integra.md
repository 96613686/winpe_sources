# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x180025740`
- end: `0x18002579f`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `95`
- prototype: `signed int __fastcall(wil::details **, LONG, LONG, const WCHAR *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180021658`

## callees

- `0x180007318`
- `0x18001b77c`
- `0x180025740`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025773`
- `KERNEL32!GetLastError` at `0x180025773`
- `KERNEL32!CreateSemaphoreExW` at `0x18002575f`
- `KERNEL32!CreateSemaphoreExW` at `0x18002575f`

## pseudocode

```c
signed int __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        wil::details **a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  __int64 v5; // rdx
  wil::details *v6; // rcx
  wil::details *Semaphore; // rbx
  __int64 v8; // r8
  const char *v9; // r9

  Semaphore = (wil::details *)CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v6, v5, v8, v9);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    a1,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x180025740  mov     [rsp+arg_0], rbx
0x180025745  push    rdi
0x180025746  sub     rsp, 30h
0x18002574a  mov     rdi, rcx
0x18002574d  mov     [rsp+38h+dwDesiredAccess], 1F0003h; dwDesiredAccess
0x180025755  xor     ecx, ecx; lpSemaphoreAttributes
0x180025757  mov     [rsp+38h+dwFlags], 0; dwFlags
0x18002575f  call    cs:__imp_CreateSemaphoreExW
0x180025766  nop     dword ptr [rax+rax+00h]
0x18002576b  mov     rbx, rax
0x18002576e  test    rax, rax
0x180025771  jz      short loc_18002578E
0x180025773  call    cs:__imp_GetLastError
0x18002577a  nop     dword ptr [rax+rax+00h]
0x18002577f  mov     rdx, rbx
0x180025782  mov     rcx, rdi
0x180025785  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18002578a  xor     eax, eax
0x18002578c  jmp     short loc_180025793
0x18002578e  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180025793  mov     rbx, [rsp+38h+arg_0]
0x180025798  add     rsp, 30h
0x18002579c  pop     rdi
0x18002579d  retn
```
