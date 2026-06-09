# DisplayStatusDialog(void * *,ushort *,ushort *)

- ea: `0x14001c8d0`
- end: `0x14001c960`
- name: `?DisplayStatusDialog@@YAJPEAPEAXPEAG1@Z`
- size: `144`
- prototype: `HRESULT __fastcall(void **, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14001700c`

## callees

- `0x140010ad3`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001c904`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001c904`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14001c94e`
- `COMCTL32!__imp_TaskDialogIndirect` at `0x14001c94e`

## pseudocode

```c
HRESULT __fastcall DisplayStatusDialog(void **a1, unsigned __int16 *a2, unsigned __int16 *a3)
{
  HINSTANCE ModuleHandleW; // rax
  TASKDIALOGCONFIG pTaskConfig; // [rsp+20h] [rbp-69h] BYREF

  memset_0(&pTaskConfig.hwndParent, 0, 0x9Cu);
  pTaskConfig.cbSize = 160;
  ModuleHandleW = GetModuleHandleW(0);
  pTaskConfig.pszWindowTitle = a2;
  pTaskConfig.hInstance = ModuleHandleW;
  pTaskConfig.hMainIcon = 0;
  pTaskConfig.pfCallback = (PFTASKDIALOGCALLBACK)StatusTaskDialogCallback;
  pTaskConfig.pszMainInstruction = a3;
  pTaskConfig.dwCommonButtons = 8;
  pTaskConfig.nDefaultButton = 2;
  pTaskConfig.dwFlags = 7176;
  pTaskConfig.lpCallbackData = (LONG_PTR)a1;
  return TaskDialogIndirect(&pTaskConfig, 0, 0, 0);
}

```

## disassembly

```asm
0x14001c8d0  push    rbp
0x14001c8d2  push    rbx
0x14001c8d3  push    rsi
0x14001c8d4  push    rdi
0x14001c8d5  lea     rbp, [rsp-3Fh]
0x14001c8da  sub     rsp, 0C8h
0x14001c8e1  mov     rdi, r8
0x14001c8e4  mov     rbx, rdx
0x14001c8e7  mov     rsi, rcx
0x14001c8ea  xor     edx, edx; Val
0x14001c8ec  mov     r8d, 9Ch; Size
0x14001c8f2  lea     rcx, [rbp+57h+pTaskConfig.hwndParent]; void *
0x14001c8f6  call    memset_0
0x14001c8fb  xor     ecx, ecx; lpModuleName
0x14001c8fd  mov     [rbp+57h+pTaskConfig.cbSize], 0A0h
0x14001c904  call    cs:__imp_GetModuleHandleW
0x14001c90a  xor     r9d, r9d; pfVerificationFlagChecked
0x14001c90d  mov     [rbp+57h+pTaskConfig.pszWindowTitle], rbx
0x14001c911  mov     [rbp+57h+pTaskConfig.hInstance], rax
0x14001c915  lea     rcx, [rbp+57h+pTaskConfig]; pTaskConfig
0x14001c919  lea     rax, ?StatusTaskDialogCallback@@YAJPEAUHWND__@@I_K_J2@Z; StatusTaskDialogCallback(HWND__ *,uint,unsigned __int64,__int64,__int64)
0x14001c920  mov     qword ptr [rbp+57h+pTaskConfig.24h], 0
0x14001c928  xor     r8d, r8d; pnRadioButton
0x14001c92b  mov     [rbp+57h+pTaskConfig.pfCallback], rax
0x14001c92f  xor     edx, edx; pnButton
0x14001c931  mov     [rbp+57h+pTaskConfig.pszMainInstruction], rdi
0x14001c935  mov     [rbp+57h+pTaskConfig.dwCommonButtons], 8
0x14001c93c  mov     [rbp+57h+pTaskConfig.nDefaultButton], 2
0x14001c943  mov     [rbp+57h+pTaskConfig.dwFlags], 1C08h
0x14001c94a  mov     [rbp+57h+pTaskConfig.lpCallbackData], rsi
0x14001c94e  call    cs:__imp_TaskDialogIndirect
0x14001c954  add     rsp, 0C8h
0x14001c95b  pop     rdi
0x14001c95c  pop     rsi
0x14001c95d  pop     rbx
0x14001c95e  pop     rbp
0x14001c95f  retn
```
