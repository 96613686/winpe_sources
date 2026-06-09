# CKsDevice::DispatchSystemControl(_DEVICE_OBJECT *,_IRP *)

- ea: `0x180049530`
- end: `0x18004956d`
- name: `?DispatchSystemControl@CKsDevice@@SAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `61`
- prototype: `NTSTATUS __fastcall(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180049530`
- `0x180049580`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x18004954f`
- `ntoskrnl!IofCompleteRequest` at `0x18004954f`

## pseudocode

```c
NTSTATUS __fastcall CKsDevice::DispatchSystemControl(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  if ( *(_DWORD *)a1->DeviceExtension != 1146114891 )
    return KsDefaultForwardIrp(a1, a2);
  a2->IoStatus.Status = -1073741637;
  IofCompleteRequest(a2, 0);
  return -1073741637;
}

```

## disassembly

```asm
0x180049530  sub     rsp, 28h
0x180049534  mov     rax, [rcx+40h]
0x180049538  mov     r8, rdx
0x18004953b  cmp     dword ptr [rax], 4450534Bh
0x180049541  jnz     short loc_180049566
0x180049543  mov     dword ptr [rdx+30h], 0C00000BBh
0x18004954a  mov     rcx, r8; Irp
0x18004954d  xor     edx, edx; PriorityBoost
0x18004954f  call    cs:__imp_IofCompleteRequest
0x180049556  nop     dword ptr [rax+rax+00h]
0x18004955b  mov     eax, 0C00000BBh
0x180049560  add     rsp, 28h
0x180049564  retn
0x180049566  call    KsDefaultForwardIrp
0x18004956b  jmp     short loc_180049560
```
