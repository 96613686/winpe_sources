# __scrt_dllmain_uninitialize_c

- ea: `0x18000231c`
- end: `0x18000234c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001fb8`

## callees

- `0x18000231c`
- `0x180002a38`
- `0x180002ad2`
- `0x180002af6`
- `0x18000d5d0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeOptions,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions>::GetTrustLevel();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x18000231c  sub     rsp, 28h
0x180002320  call    __scrt_is_ucrt_dll_in_use
0x180002325  test    eax, eax
0x180002327  jz      short loc_180002339
0x180002329  lea     rcx, Table; Table
0x180002330  add     rsp, 28h
0x180002334  jmp     _execute_onexit_table
0x180002339  call    ?GetTrustLevel@?$root_implements@UEapTlsHandshakeOptions@implementation@Utility@Eap@Internal@Windows@winrt@@U134567@@impl@winrt@@MEBA?AW4TrustLevel@Foundation@Windows@3@XZ; winrt::impl::root_implements<winrt::Windows::Internal::Eap::Utility::implementation::EapTlsHandshakeOptions,winrt::Windows::Internal::Eap::Utility::EapTlsHandshakeOptions>::GetTrustLevel(void)
0x18000233e  test    eax, eax
0x180002340  jnz     short loc_180002347
0x180002342  call    _o__cexit_0
0x180002347  add     rsp, 28h
0x18000234b  retn
```
