# SQLInstallODBC

- ea: `0x18000f5e0`
- end: `0x18000f5ef`
- name: `SQLInstallODBC`
- size: `15`
- prototype: `BOOL __stdcall(HWND, LPCSTR, LPCSTR, LPCSTR)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x1800093b0`

## pseudocode

```c
BOOL __stdcall SQLInstallODBC(HWND a1, LPCSTR a2, LPCSTR a3, LPCSTR a4)
{
  return SQLInstallODBCW(0, 0, 0, 0);
}

```

## disassembly

```asm
0x18000f5e0  xor     r9d, r9d
0x18000f5e3  xor     r8d, r8d
0x18000f5e6  xor     edx, edx
0x18000f5e8  xor     ecx, ecx
0x18000f5ea  jmp     SQLInstallODBCW
```
