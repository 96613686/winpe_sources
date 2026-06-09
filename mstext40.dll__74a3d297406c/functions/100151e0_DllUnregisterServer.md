# DllUnregisterServer()

- ea: `0x100151e0`
- end: `0x1001521f`
- name: `_DllUnregisterServer@0`
- size: `63`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1000a010`
- `0x1000a040`
- `0x100151e0`
- `0x10015240`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  int v0; // eax
  _DWORD **v1; // edi
  int v3; // esi

  v0 = SetupConfigurationSpec(1);
  v1 = (_DWORD **)v0;
  if ( !v0 )
    return -2147467259;
  v3 = ConfigUnregister(L"Software\\Microsoft\\Jet\\4.0", off_1003E460, 3, v0);
  ConfigRelease(v1);
  return v3 != 0 ? 0x80004005 : 0;
}

```

## disassembly

```asm
0x100151e0  push    edi
0x100151e1  push    1
0x100151e3  call    SetupConfigurationSpec
0x100151e8  mov     edi, eax
0x100151ea  test    edi, edi
0x100151ec  jnz     short loc_100151F5
0x100151ee  mov     eax, 80004005h
0x100151f3  pop     edi
0x100151f4  retn
0x100151f5  push    esi
0x100151f6  push    edi
0x100151f7  push    3
0x100151f9  push    offset off_1003E460; "Text"
0x100151fe  push    offset aSoftwareMicros_0; "Software\\Microsoft\\Jet\\4.0"
0x10015203  call    _ConfigUnregister@16; ConfigUnregister(x,x,x,x)
0x10015208  push    edi
0x10015209  mov     esi, eax
0x1001520b  call    _ConfigRelease@4; ConfigRelease(x)
0x10015210  neg     esi
0x10015212  sbb     esi, esi
0x10015214  and     esi, 80004005h
0x1001521a  mov     eax, esi
0x1001521c  pop     esi
0x1001521d  pop     edi
0x1001521e  retn
```
