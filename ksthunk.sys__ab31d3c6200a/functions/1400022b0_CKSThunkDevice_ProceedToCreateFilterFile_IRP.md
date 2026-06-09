# CKSThunkDevice::ProceedToCreateFilterFile(_IRP *)

- ea: `0x1400022b0`
- end: `0x1400022c4`
- name: `?ProceedToCreateFilterFile@CKSThunkDevice@@UEAA_NPEAU_IRP@@@Z`
- size: `20`
- prototype: `bool __fastcall(CKSThunkDevice *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x1400022b0`

## pseudocode

```c
bool __fastcall CKSThunkDevice::ProceedToCreateFilterFile(CKSThunkDevice *this, struct _IRP *a2)
{
  return (a2->Flags & 0x10) != 0 && a2->AssociatedIrp.MasterIrp != 0;
}

```

## disassembly

```asm
0x1400022b0  mov     eax, [rdx+10h]
0x1400022b3  test    al, 10h
0x1400022b5  jz      short loc_1400022C1
0x1400022b7  cmp     qword ptr [rdx+18h], 0
0x1400022bc  setnz   al
0x1400022bf  retn
0x1400022c1  xor     al, al
0x1400022c3  retn
```
