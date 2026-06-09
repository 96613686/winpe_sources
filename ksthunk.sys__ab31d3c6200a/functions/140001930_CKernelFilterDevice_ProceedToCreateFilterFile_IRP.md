# CKernelFilterDevice::ProceedToCreateFilterFile(_IRP *)

- ea: `0x140001930`
- end: `0x140001933`
- name: `?ProceedToCreateFilterFile@CKernelFilterDevice@@MEAA_NPEAU_IRP@@@Z`
- size: `3`
- prototype: `char __fastcall(CKernelFilterDevice *this, struct _IRP *)`
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
char __fastcall CKernelFilterDevice::ProceedToCreateFilterFile(CKernelFilterDevice *this, struct _IRP *a2)
{
  return 1;
}

```

## disassembly

```asm
0x140001930  mov     al, 1
0x140001932  retn
```
