# CAdvancedConfig::ShowDialog(HWND__ *)

- ea: `0x18000b6d0`
- end: `0x18000b6d8`
- name: `?ShowDialog@CAdvancedConfig@@UEAAJPEAUHWND__@@@Z`
- size: `8`
- prototype: `__int64 __fastcall(CAdvancedConfig *this, HWND)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000da34`

## pseudocode

```c
__int64 __fastcall CAdvancedConfig::ShowDialog(CAdvancedConfig *this, HWND a2)
{
  return HrDoAdvCfgDlg(a2);
}

```

## disassembly

```asm
0x18000b6d0  mov     rcx, rdx; hWnd
0x18000b6d3  jmp     ?HrDoAdvCfgDlg@@YAJPEAUHWND__@@@Z; HrDoAdvCfgDlg(HWND__ *)
```
