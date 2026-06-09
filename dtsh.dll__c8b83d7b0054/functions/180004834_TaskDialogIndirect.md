# TaskDialogIndirect

- ea: `0x180004834`
- end: `0x180004896`
- name: `TaskDialogIndirect`
- size: `98`
- prototype: `HRESULT __stdcall(const TASKDIALOGCONFIG *pTaskConfig, int *pnButton, int *pnRadioButton, BOOL *pfVerificationFlagChecked)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180003b00`

## callees

- `0x180004834`
- `0x18000489c`
- `0x180005010`

## string_xrefs

- `0x180004856`: `TaskDialogIndirect`

## pseudocode

```c
HRESULT __stdcall TaskDialogIndirect(
        const TASKDIALOGCONFIG *pTaskConfig,
        int *pnButton,
        int *pnRadioButton,
        BOOL *pfVerificationFlagChecked)
{
  __int64 (__fastcall *v4)(const TASKDIALOGCONFIG *, int *, int *, BOOL *); // rax

  v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_180009160;
  if ( qword_180009160 == -1 )
  {
    GetProcFromComCtl32(&qword_180009160, "TaskDialogIndirect");
    v4 = (__int64 (__fastcall *)(const TASKDIALOGCONFIG *, int *, int *, BOOL *))qword_180009160;
  }
  if ( v4 )
    return v4(pTaskConfig, pnButton, pnRadioButton, pfVerificationFlagChecked);
  else
    return -2147467259;
}

```

## disassembly

```asm
0x180004834  push    rbx
0x180004836  push    rbp
0x180004837  push    rsi
0x180004838  push    rdi
0x180004839  sub     rsp, 38h
0x18000483d  mov     rax, cs:qword_180009160
0x180004844  mov     rbx, r9
0x180004847  mov     rdi, r8
0x18000484a  mov     rsi, rdx
0x18000484d  mov     rbp, rcx
0x180004850  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180004854  jnz     short loc_180004870
0x180004856  lea     rdx, aTaskdialogindi; "TaskDialogIndirect"
0x18000485d  lea     rcx, qword_180009160
0x180004864  call    _GetProcFromComCtl32
0x180004869  mov     rax, cs:qword_180009160
0x180004870  test    rax, rax
0x180004873  jz      short loc_180004888
0x180004875  mov     r9, rbx
0x180004878  mov     r8, rdi
0x18000487b  mov     rdx, rsi
0x18000487e  mov     rcx, rbp
0x180004881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004886  jmp     short loc_18000488D
0x180004888  mov     eax, 80004005h
0x18000488d  add     rsp, 38h
0x180004891  pop     rdi
0x180004892  pop     rsi
0x180004893  pop     rbp
0x180004894  pop     rbx
0x180004895  retn
```
