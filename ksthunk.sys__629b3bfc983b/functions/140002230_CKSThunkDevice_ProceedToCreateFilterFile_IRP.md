# CKSThunkDevice::ProceedToCreateFilterFile(_IRP *)

- ea: `0x140002230`
- end: `0x140002244`
- name: `?ProceedToCreateFilterFile@CKSThunkDevice@@UEAA_NPEAU_IRP@@@Z`
- size: `20`
- prototype: `bool __fastcall(CKSThunkDevice *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140002230`

## pseudocode

```c
bool __fastcall CKSThunkDevice::ProceedToCreateFilterFile(CKSThunkDevice *this, struct _IRP *a2)
{
  return (a2->Flags & 0x10) != 0 && a2->AssociatedIrp.MasterIrp != 0;
}

```

## disassembly

```asm
0x140002230  mov     eax, [rdx+10h]
0x140002233  test    al, 10h
0x140002235  jz      short loc_140002241
0x140002237  cmp     qword ptr [rdx+18h], 0
0x14000223c  setnz   al
0x14000223f  retn
0x140002241  xor     al, al
0x140002243  retn
```
