# CDlg::_DoModalDlg(HWND__ *,int)

- ea: `0x1400019ec`
- end: `0x140001a2c`
- name: `?_DoModalDlg@CDlg@@IEAA_JPEAUHWND__@@H@Z`
- size: `64`
- prototype: `__int64 __fastcall(LPARAM dwInitParam, HWND, int)`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001adc`
- `0x140001c68`
- `0x140001f30`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1400019ff`
- `KERNEL32!GetModuleHandleW` at `0x1400019ff`
- `USER32!DialogBoxParamW` at `0x140001a19`
- `USER32!DialogBoxParamW` at `0x140001a19`

## pseudocode

```c
__int64 __fastcall CDlg::_DoModalDlg(LPARAM dwInitParam, HWND a2, unsigned __int16 a3)
{
  unsigned int v4; // edi
  HMODULE ModuleHandleW; // rax

  v4 = a3;
  ModuleHandleW = GetModuleHandleW(0);
  return (int)DialogBoxParamW(ModuleHandleW, (LPCWSTR)v4, 0, (DLGPROC)CDlg::_DlgProc, dwInitParam);
}

```

## disassembly

```asm
0x1400019ec  mov     [rsp+arg_0], rbx
0x1400019f1  push    rdi
0x1400019f2  sub     rsp, 30h
0x1400019f6  mov     rbx, rcx
0x1400019f9  movzx   edi, r8w
0x1400019fd  xor     ecx, ecx; lpModuleName
0x1400019ff  call    cs:__imp_GetModuleHandleW
0x140001a05  lea     r9, ?_DlgProc@CDlg@@SA_JPEAUHWND__@@I_K_J@Z; lpDialogFunc
0x140001a0c  mov     [rsp+38h+dwInitParam], rbx; dwInitParam
0x140001a11  mov     rcx, rax; hInstance
0x140001a14  xor     r8d, r8d; hWndParent
0x140001a17  mov     edx, edi; lpTemplateName
0x140001a19  call    cs:__imp_DialogBoxParamW
0x140001a1f  mov     rbx, [rsp+38h+arg_0]
0x140001a24  cdqe
0x140001a26  add     rsp, 30h
0x140001a2a  pop     rdi
0x140001a2b  retn
```
