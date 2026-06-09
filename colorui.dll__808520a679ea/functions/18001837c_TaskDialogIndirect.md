# TaskDialogIndirect

- ea: `0x18001837c`
- end: `0x1800183de`
- name: `TaskDialogIndirect`
- size: `98`
- prototype: `HRESULT __stdcall(const TASKDIALOGCONFIG *pTaskConfig, int *pnButton, int *pnRadioButton, BOOL *pfVerificationFlagChecked)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000bd60`
- `0x18000e9d8`
- `0x180015cc8`
- `0x180015ecc`

## callees

- `0x18001837c`
- `0x1800183e4`
- `0x180019010`

## string_xrefs

- `0x18001839e`: `TaskDialogIndirect`

## pseudocode

```c
HRESULT __stdcall TaskDialogIndirect(
        const TASKDIALOGCONFIG *pTaskConfig,
        int *pnButton,
        int *pnRadioButton,
        BOOL *pfVerificationFlagChecked)
{
  __int64 (__fastcall *v4)(const TASKDIALOGCONFIG *, int *, int *, BOOL *); // rax

  v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_180021418;
  if ( qword_180021418 == -1 )
  {
    GetProcFromComCtl32((FARPROC *)&qword_180021418, "TaskDialogIndirect");
    v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_180021418;
  }
  if ( v4 )
    return v4(pTaskConfig, pnButton, pnRadioButton, pfVerificationFlagChecked);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x18001837c  push    rbx
0x18001837e  push    rbp
0x18001837f  push    rsi
0x180018380  push    rdi
0x180018381  sub     rsp, 38h
0x180018385  mov     rax, cs:qword_180021418
0x18001838c  mov     rbx, r9
0x18001838f  mov     rdi, r8
0x180018392  mov     rsi, rdx
0x180018395  mov     rbp, rcx
0x180018398  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001839c  jnz     short loc_1800183B8
0x18001839e  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x1800183a5  lea     rcx, qword_180021418
0x1800183ac  call    _GetProcFromComCtl32
0x1800183b1  mov     rax, cs:qword_180021418
0x1800183b8  test    rax, rax
0x1800183bb  jz      short loc_1800183D0
0x1800183bd  mov     r9, rbx
0x1800183c0  mov     r8, rdi
0x1800183c3  mov     rdx, rsi
0x1800183c6  mov     rcx, rbp
0x1800183c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800183ce  jmp     short loc_1800183D5
0x1800183d0  mov     eax, 80004005h
0x1800183d5  add     rsp, 38h
0x1800183d9  pop     rdi
0x1800183da  pop     rsi
0x1800183db  pop     rbp
0x1800183dc  pop     rbx
0x1800183dd  retn
```
