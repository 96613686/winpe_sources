# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z

- ea: `0x1000f649`
- end: `0x1000f68d`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z`
- size: `68`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x10007923`

## callees

- `0x10007173`
- `0x1000f649`
- `0x1000f6d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000f670`
- `KERNEL32!GetLastError` at `0x1000f670`
- `KERNEL32!CreateSemaphoreExW` at `0x1000f664`
- `KERNEL32!CreateSemaphoreExW` at `0x1000f664`

## pseudocode

```c
int __thiscall _create___semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z(
        void *this,
        LONG lInitialCount,
        LONG lMaximumCount,
        const WCHAR *lpName,
        int a5,
        int a6,
        int a7)
{
  HANDLE Semaphore; // esi
  wil::details *v10; // [esp+0h] [ebp-8h]

  Semaphore = CreateSemaphoreExW(0, lInitialCount, lMaximumCount, lpName, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr(v10);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    this,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x1000f649  mov     edi, edi
0x1000f64b  push    ebp
0x1000f64c  mov     ebp, esp
0x1000f64e  push    esi
0x1000f64f  push    edi; this
0x1000f650  push    1F0003h; dwDesiredAccess
0x1000f655  push    0; dwFlags
0x1000f657  push    [ebp+lpName]; lpName
0x1000f65a  mov     edi, ecx
0x1000f65c  push    [ebp+lMaximumCount]; lMaximumCount
0x1000f65f  push    [ebp+lInitialCount]; lInitialCount
0x1000f662  push    0; lpSemaphoreAttributes
0x1000f664  call    ds:__imp__CreateSemaphoreExW@24; CreateSemaphoreExW(x,x,x,x,x,x)
0x1000f66a  mov     esi, eax
0x1000f66c  test    esi, esi
0x1000f66e  jz      short loc_1000F682
0x1000f670  call    ds:__imp__GetLastError@0; GetLastError()
0x1000f676  push    esi
0x1000f677  mov     ecx, edi
0x1000f679  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x1000f67e  xor     eax, eax
0x1000f680  jmp     short loc_1000F687
0x1000f682  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1000f687  pop     edi
0x1000f688  pop     esi
0x1000f689  pop     ebp
0x1000f68a  retn    18h
```
