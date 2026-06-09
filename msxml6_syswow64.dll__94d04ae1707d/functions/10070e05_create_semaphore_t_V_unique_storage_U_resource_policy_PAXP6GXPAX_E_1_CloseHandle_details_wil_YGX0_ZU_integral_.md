# ?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z

- ea: `0x10070e05`
- end: `0x10070e49`
- name: `?create@?$semaphore_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJJJPBGKPAU_SECURITY_ATTRIBUTES@@PA_N@Z`
- size: `68`
- prototype: `HRESULT __thiscall(wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__stdcall*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned int,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *this, int lInitialCount, int lMaximumCount, const wchar_t *name, unsigned int lInitialCount, _SECURITY_ATTRIBUTES *lMaximumCount, bool *name)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1006dde4`

## callees

- `0x1006e61f`
- `0x10070e05`
- `0x10070f4f`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x10070e20`
- `api-ms-win-core-synch-l1-1-0!CreateSemaphoreExW` at `0x10070e20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10070e2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x10070e2c`

## pseudocode

```c
HRESULT __thiscall _create___semaphore_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJJJPBGKPAU_SECURITY_ATTRIBUTES__PA_N_Z(
        wil::semaphore_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (__stdcall*)(void *) noexcept,&wil::details::CloseHandle,wistd::integral_constant<unsigned int,0>,void *,void *,0,std::nullptr_t> >,wil::err_returncode_policy> *this,
        LONG lInitialCount,
        LONG lMaximumCount,
        const wchar_t *name,
        unsigned int a5,
        _SECURITY_ATTRIBUTES *a6,
        bool *a7)
{
  HANDLE Semaphore; // esi

  Semaphore = CreateSemaphoreExW(0, lInitialCount, lMaximumCount, name, 0, 0x1F0003u);
  if ( !Semaphore )
    return wil::details::GetLastErrorFailHr();
  GetLastError();
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    this,
    Semaphore);
  return 0;
}

```

## disassembly

```asm
0x10070e05  mov     edi, edi
0x10070e07  push    ebp
0x10070e08  mov     ebp, esp
0x10070e0a  push    esi
0x10070e0b  push    edi
0x10070e0c  push    1F0003h; dwDesiredAccess
0x10070e11  push    0; dwFlags
0x10070e13  push    [ebp+name]; lpName
0x10070e16  mov     edi, this
0x10070e18  push    [ebp+lMaximumCount]; lMaximumCount
0x10070e1b  push    [ebp+lInitialCount]; lInitialCount
0x10070e1e  push    0; lpSemaphoreAttributes
0x10070e20  call    ds:__imp__CreateSemaphoreExW@24; CreateSemaphoreExW(x,x,x,x,x,x)
0x10070e26  mov     esi, eax
0x10070e28  test    esi, esi
0x10070e2a  jz      short loc_10070E3E
0x10070e2c  call    ds:__imp__GetLastError@0; GetLastError()
0x10070e32  push    esi; ptr
0x10070e33  mov     this, edi; this
0x10070e35  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x10070e3a  xor     eax, eax
0x10070e3c  jmp     short loc_10070E43
0x10070e3e  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x10070e43  pop     edi
0x10070e44  pop     esi
0x10070e45  pop     ebp
0x10070e46  retn    18h
```
