# ?create@?$event_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJW4EventOptions@2@PBGPAU_SECURITY_ATTRIBUTES@@PA_N@Z

- ea: `0x1000f693`
- end: `0x1000f6ce`
- name: `?create@?$event_t@V?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QAEJW4EventOptions@2@PBGPAU_SECURITY_ATTRIBUTES@@PA_N@Z`
- size: `59`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1000f089`
- `0x10037a21`

## callees

- `0x10007173`
- `0x1000f693`
- `0x1000f6d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1000f6b1`
- `KERNEL32!GetLastError` at `0x1000f6b1`
- `KERNEL32!CreateEventExW` at `0x1000f6a5`
- `KERNEL32!CreateEventExW` at `0x1000f6a5`

## pseudocode

```c
int __thiscall _create___event_t_V__unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QAEJW4EventOptions_2_PBGPAU_SECURITY_ATTRIBUTES__PA_N_Z(
        void *this,
        int a2,
        int a3,
        int a4,
        int a5)
{
  HANDLE Event; // esi
  wil::details *v8; // [esp+0h] [ebp-Ch]

  Event = CreateEventExW(0, 0, 0, 0x1F0003u);
  if ( !Event )
    return wil::details::GetLastErrorFailHr(v8);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PAXP6GXPAX__E_1_CloseHandle_details_wil__YGX0_ZU__integral_constant_I_0A__wistd__PAXPAX_0A___T_details_wil___details_wil__QAEXPAX_Z(
    this,
    Event);
  return 0;
}

```

## disassembly

```asm
0x1000f693  mov     edi, edi
0x1000f695  push    ecx
0x1000f696  push    esi
0x1000f697  push    edi; this
0x1000f698  push    1F0003h; dwDesiredAccess
0x1000f69d  push    0; dwFlags
0x1000f69f  push    0; lpName
0x1000f6a1  push    0; lpEventAttributes
0x1000f6a3  mov     edi, ecx
0x1000f6a5  call    ds:__imp__CreateEventExW@16; CreateEventExW(x,x,x,x)
0x1000f6ab  mov     esi, eax
0x1000f6ad  test    esi, esi
0x1000f6af  jz      short loc_1000F6C3
0x1000f6b1  call    ds:__imp__GetLastError@0; GetLastError()
0x1000f6b7  push    esi
0x1000f6b8  mov     ecx, edi
0x1000f6ba  call    ?reset@?$unique_storage@U?$resource_policy@PAXP6GXPAX@_E$1?CloseHandle@details@wil@@YGX0@ZU?$integral_constant@I$0A@@wistd@@PAXPAX$0A@$$T@details@wil@@@details@wil@@QAEXPAX@Z
0x1000f6bf  xor     eax, eax
0x1000f6c1  jmp     short loc_1000F6C8
0x1000f6c3  call    ?GetLastErrorFailHr@details@wil@@YGJXZ; wil::details::GetLastErrorFailHr(void)
0x1000f6c8  pop     edi
0x1000f6c9  pop     esi
0x1000f6ca  pop     ecx
0x1000f6cb  retn    10h
```
