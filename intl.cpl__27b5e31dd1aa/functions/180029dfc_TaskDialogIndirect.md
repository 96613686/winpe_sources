# TaskDialogIndirect

- ea: `0x180029dfc`
- end: `0x180029e5e`
- name: `TaskDialogIndirect`
- size: `98`
- prototype: `HRESULT __stdcall(const TASKDIALOGCONFIG *pTaskConfig, int *pnButton, int *pnRadioButton, BOOL *pfVerificationFlagChecked)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024f50`

## callees

- `0x180029dfc`
- `0x180029e64`
- `0x18002b010`

## string_xrefs

- `0x180029e1e`: `TaskDialogIndirect`

## pseudocode

```c
HRESULT __stdcall TaskDialogIndirect(
        const TASKDIALOGCONFIG *pTaskConfig,
        int *pnButton,
        int *pnRadioButton,
        BOOL *pfVerificationFlagChecked)
{
  __int64 (__fastcall *v4)(const TASKDIALOGCONFIG *, int *, int *, BOOL *); // rax

  v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_18003A7F8;
  if ( qword_18003A7F8 == -1 )
  {
    GetProcFromComCtl32(&qword_18003A7F8, "TaskDialogIndirect");
    v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_18003A7F8;
  }
  if ( v4 )
    return v4(pTaskConfig, pnButton, pnRadioButton, pfVerificationFlagChecked);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x180029dfc  push    rbx
0x180029dfe  push    rbp
0x180029dff  push    rsi
0x180029e00  push    rdi
0x180029e01  sub     rsp, 38h
0x180029e05  mov     rax, cs:qword_18003A7F8
0x180029e0c  mov     rbx, r9
0x180029e0f  mov     rdi, r8
0x180029e12  mov     rsi, rdx
0x180029e15  mov     rbp, rcx
0x180029e18  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029e1c  jnz     short loc_180029E38
0x180029e1e  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x180029e25  lea     rcx, qword_18003A7F8
0x180029e2c  call    _GetProcFromComCtl32
0x180029e31  mov     rax, cs:qword_18003A7F8
0x180029e38  test    rax, rax
0x180029e3b  jz      short loc_180029E50
0x180029e3d  mov     r9, rbx
0x180029e40  mov     r8, rdi
0x180029e43  mov     rdx, rsi
0x180029e46  mov     rcx, rbp
0x180029e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029e4e  jmp     short loc_180029E55
0x180029e50  mov     eax, 80004005h
0x180029e55  add     rsp, 38h
0x180029e59  pop     rdi
0x180029e5a  pop     rsi
0x180029e5b  pop     rbp
0x180029e5c  pop     rbx
0x180029e5d  retn
```
