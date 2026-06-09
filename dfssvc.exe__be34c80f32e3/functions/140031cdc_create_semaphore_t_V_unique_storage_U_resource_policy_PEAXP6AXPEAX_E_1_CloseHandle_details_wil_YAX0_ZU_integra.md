# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z

- ea: `0x140031cdc`
- end: `0x140031d44`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z`
- size: `104`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1400290b4`

## callees

- `0x14002b118`
- `0x140031cdc`
- `0x140031f00`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031d11`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140031d11`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140031cfd`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x140031cfd`

## pseudocode

```c
__int64 __fastcall _create___semaphore_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJJJPEBGKPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(
        __int64 a1,
        LONG a2,
        LONG a3,
        const WCHAR *a4)
{
  unsigned int v5; // ebx
  wil::details *v6; // rcx
  HANDLE Semaphore; // rdi

  v5 = 0;
  Semaphore = CreateSemaphoreExW(0, a2, a3, a4, 0, 0x1F0003u);
  if ( Semaphore )
  {
    GetLastError();
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      a1,
      Semaphore);
  }
  else
  {
    return (unsigned int)wil::details::GetLastErrorFailHr(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x140031cdc  mov     rax, rsp
0x140031cdf  mov     [rax+8], rbx
0x140031ce3  mov     [rax+10h], rsi
0x140031ce7  push    rdi
0x140031ce8  sub     rsp, 30h
0x140031cec  mov     rsi, rcx
0x140031cef  mov     dword ptr [rax-10h], 1F0003h
0x140031cf6  xor     ebx, ebx
0x140031cf8  xor     ecx, ecx; lpSemaphoreAttributes
0x140031cfa  mov     [rax-18h], ebx
0x140031cfd  call    cs:__imp_CreateSemaphoreExW
0x140031d04  nop     dword ptr [rax+rax+00h]
0x140031d09  mov     rdi, rax
0x140031d0c  test    rax, rax
0x140031d0f  jz      short loc_140031D2A
0x140031d11  call    cs:__imp_GetLastError
0x140031d18  nop     dword ptr [rax+rax+00h]
0x140031d1d  mov     rdx, rdi
0x140031d20  mov     rcx, rsi
0x140031d23  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x140031d28  jmp     short loc_140031D31
0x140031d2a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x140031d2f  mov     ebx, eax
0x140031d31  mov     rsi, [rsp+38h+arg_8]
0x140031d36  mov     eax, ebx
0x140031d38  mov     rbx, [rsp+38h+arg_0]
0x140031d3d  add     rsp, 30h
0x140031d41  pop     rdi
0x140031d42  retn
```
