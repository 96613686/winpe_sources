# Intl_CreateTaskDialog(HWND__ *,ulong,ulong,ulong,ulong,ulong,_TASKDIALOGCONFIG *,int *)

- ea: `0x180024f50`
- end: `0x180024fd6`
- name: `?Intl_CreateTaskDialog@@YAJPEAUHWND__@@KKKKKPEAU_TASKDIALOGCONFIG@@PEAH@Z`
- size: `134`
- prototype: `__int64 __fastcall(HWND, unsigned int, unsigned int, unsigned int, unsigned int, unsigned int, TASKDIALOGCONFIG *pTaskConfig, int *pnButton)`
- caller_count: `3`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x180024490`
- `0x180025eb8`
- `0x180025f40`

## callees

- `0x180029dfc`

## pseudocode

```c
HRESULT __fastcall Intl_CreateTaskDialog(
        HWND a1,
        unsigned __int16 a2,
        unsigned __int16 a3,
        unsigned __int16 a4,
        unsigned __int16 a5,
        unsigned __int16 a6,
        TASKDIALOGCONFIG *pTaskConfig,
        int *pnButton)
{
  int v9; // [rsp+20h] [rbp-28h] BYREF
  __int64 v10; // [rsp+24h] [rbp-24h]
  int v11; // [rsp+2Ch] [rbp-1Ch]
  __int64 v12; // [rsp+30h] [rbp-18h]

  v10 = a2;
  v12 = a3;
  pTaskConfig->hInstance = hInstance;
  pTaskConfig->pszWindowTitle = (PCWSTR)a4;
  pTaskConfig->pszMainInstruction = (PCWSTR)a5;
  pTaskConfig->pszContent = (PCWSTR)a6;
  v11 = 2;
  pTaskConfig->hwndParent = a1;
  pTaskConfig->cButtons = 2;
  pTaskConfig->pButtons = (const TASKDIALOG_BUTTON *)&v9;
  v9 = 1;
  pTaskConfig->cbSize = 160;
  return TaskDialogIndirect(pTaskConfig, pnButton, 0, 0);
}

```

## disassembly

```asm
0x180024f50  sub     rsp, 48h
0x180024f54  mov     r10, [rsp+48h+pTaskConfig]
0x180024f5c  movzx   eax, dx
0x180024f5f  mov     edx, 2
0x180024f64  mov     [rsp+48h+var_24], rax
0x180024f69  movzx   eax, r8w
0x180024f6d  xor     r8d, r8d; pnRadioButton
0x180024f70  mov     [rsp+48h+var_18], rax
0x180024f75  mov     rax, cs:?hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * hInstance
0x180024f7c  mov     [r10+0Ch], rax
0x180024f80  movzx   eax, r9w
0x180024f84  xor     r9d, r9d; pfVerificationFlagChecked
0x180024f87  mov     [r10+1Ch], rax
0x180024f8b  movzx   eax, [rsp+48h+arg_20]
0x180024f90  mov     [r10+2Ch], rax
0x180024f94  movzx   eax, [rsp+48h+arg_28]
0x180024f99  mov     [r10+34h], rax
0x180024f9d  lea     rax, [rsp+48h+var_28]
0x180024fa2  mov     [rsp+48h+var_1C], edx
0x180024fa6  mov     [r10+4], rcx
0x180024faa  mov     rcx, r10; pTaskConfig
0x180024fad  mov     [r10+3Ch], edx
0x180024fb1  mov     rdx, [rsp+48h+pnButton]; pnButton
0x180024fb9  mov     [r10+40h], rax
0x180024fbd  mov     [rsp+48h+var_28], 1
0x180024fc5  mov     dword ptr [r10], 0A0h
0x180024fcc  call    TaskDialogIndirect
0x180024fd1  add     rsp, 48h
0x180024fd5  retn
```
