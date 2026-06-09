# CAutoTask<DBCOLUMNUPDATEINFO>::~CAutoTask<DBCOLUMNUPDATEINFO>(void)

- ea: `0x180002798`
- end: `0x1800027a2`
- name: `??1?$CAutoTask@UDBCOLUMNUPDATEINFO@@@@QEAA@XZ`
- size: `10`
- prototype: ``
- caller_count: `12`
- callee_count: `0`
- tags: `service_task, installer_update`

## callers

- `0x18002f624`
- `0x18002f636`
- `0x18002f648`
- `0x18002f6b4`
- `0x18002f6c6`
- `0x18002f75f`
- `0x18002fb15`
- `0x18002fb9c`
- `0x18002fbf0`
- `0x18002fc02`
- `0x180030068`
- `0x18003007a`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000279b`

## pseudocode

```c
void __fastcall CAutoTask<DBCOLUMNUPDATEINFO>::~CAutoTask<DBCOLUMNUPDATEINFO>(LPVOID *a1)
{
  CoTaskMemFree(*a1);
}

```

## disassembly

```asm
0x180002798  mov     rcx, [rcx]
0x18000279b  jmp     cs:__imp_CoTaskMemFree
```
