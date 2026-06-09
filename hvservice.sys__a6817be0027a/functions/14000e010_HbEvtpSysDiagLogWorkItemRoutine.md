# HbEvtpSysDiagLogWorkItemRoutine

- ea: `0x14000e010`
- end: `0x14000e05b`
- name: `HbEvtpSysDiagLogWorkItemRoutine`
- size: `75`
- prototype: `void __fastcall(PVOID IoObject, struct _IO_REMOVE_LOCK *Context, PIO_WORKITEM IoWorkItem)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140013ef0`

## import_xrefs

- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e043`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000e043`
- `ntoskrnl!IoFreeWorkItem` at `0x14000e02a`
- `ntoskrnl!IoFreeWorkItem` at `0x14000e02a`

## pseudocode

```c
void __fastcall HbEvtpSysDiagLogWorkItemRoutine(
        PVOID IoObject,
        struct _IO_REMOVE_LOCK *Context,
        PIO_WORKITEM IoWorkItem)
{
  HbEvtpProcessSystemDiagLog(0);
  IoFreeWorkItem(IoWorkItem);
  IoReleaseRemoveLockEx(Context + 2, Context, 0x20u);
}

```

## disassembly

```asm
0x14000e010  mov     [rsp+arg_0], rbx
0x14000e015  push    rdi
0x14000e016  sub     rsp, 20h
0x14000e01a  xor     ecx, ecx
0x14000e01c  mov     rbx, r8
0x14000e01f  mov     rdi, rdx
0x14000e022  call    HbEvtpProcessSystemDiagLog
0x14000e027  mov     rcx, rbx; IoWorkItem
0x14000e02a  call    cs:__imp_IoFreeWorkItem
0x14000e031  nop     dword ptr [rax+rax+00h]
0x14000e036  lea     rcx, [rdi+40h]; RemoveLock
0x14000e03a  mov     r8d, 20h ; ' '; RemlockSize
0x14000e040  mov     rdx, rdi; Tag
0x14000e043  call    cs:__imp_IoReleaseRemoveLockEx
0x14000e04a  nop     dword ptr [rax+rax+00h]
0x14000e04f  mov     rbx, [rsp+28h+arg_0]
0x14000e054  add     rsp, 20h
0x14000e058  pop     rdi
0x14000e059  retn
```
