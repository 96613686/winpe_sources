# CKernelFilterDevice::CallbackClientOnCompletion(_DEVICE_OBJECT *,_IRP *,CKernelFilterDevice *)

- ea: `0x140001300`
- end: `0x140001318`
- name: `?CallbackClientOnCompletion@CKernelFilterDevice@@CAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAV1@@Z`
- size: `24`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct CKernelFilterDevice *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x140001440`

## pseudocode

```c
NTSTATUS __fastcall CKernelFilterDevice::CallbackClientOnCompletion(
        struct _DEVICE_OBJECT *a1,
        struct _IRP *a2,
        struct CKernelFilterDevice *a3)
{
  return CKernelFilterDevice::DispatchIrp(a3, a2, 1);
}

```

## disassembly

```asm
0x140001300  sub     rsp, 28h
0x140001304  mov     rcx, r8
0x140001307  mov     r8d, 1
0x14000130d  call    ?DispatchIrp@CKernelFilterDevice@@QEAAJPEAU_IRP@@W4_IRP_STATUS@@@Z; CKernelFilterDevice::DispatchIrp(_IRP *,_IRP_STATUS)
0x140001312  add     rsp, 28h
0x140001316  retn
```
