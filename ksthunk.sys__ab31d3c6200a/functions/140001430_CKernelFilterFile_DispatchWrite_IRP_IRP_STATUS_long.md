# CKernelFilterFile::DispatchWrite(_IRP *,_IRP_STATUS,long *)

- ea: `0x140001430`
- end: `0x140001436`
- name: `?DispatchWrite@CKernelFilterFile@@UEAA?AW4_IRP_DISPOSITION@@PEAU_IRP@@W4_IRP_STATUS@@PEAJ@Z`
- size: `6`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `0`
- tags: `installer_update`

## pseudocode

```c
__int64 CKernelFilterFile::DispatchWrite()
{
  return 1;
}

```

## disassembly

```asm
0x140001430  mov     eax, 1
0x140001435  retn
```
