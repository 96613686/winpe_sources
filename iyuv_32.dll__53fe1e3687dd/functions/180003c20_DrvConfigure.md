# DrvConfigure

- ea: `0x180003c20`
- end: `0x180003c53`
- name: `DrvConfigure`
- size: `51`
- prototype: `__int64 __fastcall(HWND hWndParent)`
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x180002710`

## import_xrefs

- `USER32!DialogBoxParamW` at `0x180003c43`
- `USER32!DialogBoxParamW` at `0x180003c43`

## pseudocode

```c
__int64 __fastcall DrvConfigure(HWND hWndParent)
{
  DialogBoxParamW(hDriverModule, (LPCWSTR)0x6B, hWndParent, DriverDialogProc, 0);
  return 1;
}

```

## disassembly

```asm
0x180003c20  sub     rsp, 38h
0x180003c24  mov     r8, rcx; hWndParent
0x180003c27  mov     [rsp+38h+dwInitParam], 0; dwInitParam
0x180003c30  mov     rcx, cs:hDriverModule; hInstance
0x180003c37  lea     r9, DriverDialogProc; lpDialogFunc
0x180003c3e  mov     edx, 6Bh ; 'k'; lpTemplateName
0x180003c43  call    cs:__imp_DialogBoxParamW
0x180003c49  mov     eax, 1
0x180003c4e  add     rsp, 38h
0x180003c52  retn
```
