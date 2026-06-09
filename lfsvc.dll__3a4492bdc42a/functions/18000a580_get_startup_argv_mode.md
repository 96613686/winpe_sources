# _get_startup_argv_mode

- ea: `0x18000a580`
- end: `0x18000a586`
- name: `_get_startup_argv_mode`
- size: `6`
- prototype: `HRESULT __stdcall(const IID *const rclsid, const IID *const riid, LPVOID *ppv)`
- caller_count: `1`
- callee_count: `0`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800043b8`

## pseudocode

```c
HRESULT __stdcall get_startup_argv_mode(const IID *const rclsid, const IID *const riid, LPVOID *ppv)
{
  return 1;
}

```

## disassembly

```asm
0x18000a580  mov     eax, 1; DllCanUnloadNow
0x18000a585  retn
```
