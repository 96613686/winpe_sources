# TaskDialog

- ea: `0x180029d60`
- end: `0x180029df4`
- name: `TaskDialog`
- size: `148`
- prototype: `HRESULT __stdcall(HWND hwndOwner, HINSTANCE hInstance, PCWSTR pszWindowTitle, PCWSTR pszMainInstruction, PCWSTR pszContent, TASKDIALOG_COMMON_BUTTON_FLAGS dwCommonButtons, PCWSTR pszIcon, int *pnButton)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180026d2c`

## callees

- `0x180029d60`
- `0x180029e64`
- `0x18002b010`

## string_xrefs

- `0x180029d82`: `TaskDialog`

## pseudocode

```c
HRESULT __stdcall TaskDialog(
        HWND hwndOwner,
        HINSTANCE hInstance,
        PCWSTR pszWindowTitle,
        PCWSTR pszMainInstruction,
        PCWSTR pszContent,
        TASKDIALOG_COMMON_BUTTON_FLAGS dwCommonButtons,
        PCWSTR pszIcon,
        int *pnButton)
{
  __int64 (__fastcall *v8)(HWND, HINSTANCE, PCWSTR, PCWSTR, PCWSTR, TASKDIALOG_COMMON_BUTTON_FLAGS, PCWSTR, int *); // rax

  v8 = (__int64 (__fastcall *)(HWND, HINSTANCE, PCWSTR, PCWSTR, PCWSTR, TASKDIALOG_COMMON_BUTTON_FLAGS, PCWSTR, int *))qword_18003A7F0;
  if ( qword_18003A7F0 == -1 )
  {
    GetProcFromComCtl32(&qword_18003A7F0, "TaskDialog");
    v8 = (__int64 (__fastcall *)(HWND, HINSTANCE, PCWSTR, PCWSTR, PCWSTR, TASKDIALOG_COMMON_BUTTON_FLAGS, PCWSTR, int *))qword_18003A7F0;
  }
  if ( v8 )
    return v8(hwndOwner, hInstance, pszWindowTitle, pszMainInstruction, pszContent, dwCommonButtons, pszIcon, pnButton);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x180029d60  push    rbx
0x180029d62  push    rbp
0x180029d63  push    rsi
0x180029d64  push    rdi
0x180029d65  sub     rsp, 58h
0x180029d69  mov     rax, cs:qword_18003A7F0
0x180029d70  mov     rbx, r9
0x180029d73  mov     rdi, r8
0x180029d76  mov     rsi, rdx
0x180029d79  mov     rbp, rcx
0x180029d7c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029d80  jnz     short loc_180029D9C
0x180029d82  lea     rdx, aTaskdialog; "TaskDialog"
0x180029d89  lea     rcx, qword_18003A7F0
0x180029d90  call    _GetProcFromComCtl32
0x180029d95  mov     rax, cs:qword_18003A7F0
0x180029d9c  test    rax, rax
0x180029d9f  jz      short loc_180029DE6
0x180029da1  mov     rcx, [rsp+78h+pnButton]
0x180029da9  mov     r9, rbx
0x180029dac  mov     [rsp+78h+var_40], rcx
0x180029db1  mov     r8, rdi
0x180029db4  mov     rcx, [rsp+78h+pszIcon]
0x180029dbc  mov     rdx, rsi
0x180029dbf  mov     [rsp+78h+var_48], rcx
0x180029dc4  mov     ecx, [rsp+78h+dwCommonButtons]
0x180029dcb  mov     [rsp+78h+var_50], ecx
0x180029dcf  mov     rcx, [rsp+78h+pszContent]
0x180029dd7  mov     [rsp+78h+var_58], rcx
0x180029ddc  mov     rcx, rbp
0x180029ddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029de4  jmp     short loc_180029DEB
0x180029de6  mov     eax, 80004005h
0x180029deb  add     rsp, 58h
0x180029def  pop     rdi
0x180029df0  pop     rsi
0x180029df1  pop     rbp
0x180029df2  pop     rbx
0x180029df3  retn
```
