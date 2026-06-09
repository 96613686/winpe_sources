# MemError

- ea: `0x1800074c4`
- end: `0x1800074f0`
- name: `MemError`
- size: `44`
- prototype: `int()`
- caller_count: `9`
- callee_count: `0`
- tags: ``

## callers

- `0x1800017c0`
- `0x1800052b8`
- `0x180005530`
- `0x180005c00`
- `0x180005fd4`
- `0x180006184`
- `0x180006db8`
- `0x18000af80`
- `0x18000d208`

## import_xrefs

- `USER32!GetActiveWindow` at `0x1800074c8`
- `USER32!GetActiveWindow` at `0x1800074c8`
- `USER32!MessageBoxW` at `0x1800074e9`

## pseudocode

```c
int MemError()
{
  HWND ActiveWindow; // rax

  ActiveWindow = GetActiveWindow();
  return MessageBoxW(ActiveWindow, &szOOM, &szOOMTitle, 0x1010u);
}

```

## disassembly

```asm
0x1800074c4  sub     rsp, 28h
0x1800074c8  call    cs:__imp_GetActiveWindow
0x1800074ce  mov     r9d, 1010h
0x1800074d4  lea     r8, szOOMTitle
0x1800074db  mov     rcx, rax
0x1800074de  lea     rdx, szOOM
0x1800074e5  add     rsp, 28h
0x1800074e9  jmp     cs:__imp_MessageBoxW
```
