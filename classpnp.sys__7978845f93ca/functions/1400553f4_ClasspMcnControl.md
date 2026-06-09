# ClasspMcnControl

- ea: `0x1400553f4`
- end: `0x1400554b9`
- name: `ClasspMcnControl`
- size: `197`
- prototype: `__int64 __fastcall(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PIRP Irp, PVOID P)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140019de0`

## callees

- `0x140005190`
- `0x1400134a0`
- `0x140016820`
- `0x140054010`
- `0x140054350`
- `0x1400553f4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140055482`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055482`

## pseudocode

```c
__int64 __fastcall ClasspMcnControl(PFUNCTIONAL_DEVICE_EXTENSION FdoExtension, PIRP Irp, PVOID P)
{
  _IRP *MasterIrp; // r15
  _FILE_OBJECT_EXTENSION *DictionaryEntry; // rbx
  unsigned int v8; // edi

  MasterIrp = Irp->AssociatedIrp.MasterIrp;
  if ( Irp->Tail.Overlay.CurrentStackLocation->FileObject )
  {
    DictionaryEntry = (_FILE_OBJECT_EXTENSION *)GetDictionaryEntry(&FdoExtension->CommonExtension.FileObjectDictionary);
  }
  else
  {
    if ( Irp->RequestorMode )
    {
LABEL_11:
      v8 = -1073741811;
      goto LABEL_12;
    }
    DictionaryEntry = &FdoExtension->KernelModeMcnContext;
  }
  if ( !DictionaryEntry )
    goto LABEL_11;
  v8 = 0;
  if ( LOBYTE(MasterIrp->Type) )
  {
    ClassDisableMediaChangeDetection(FdoExtension);
    _InterlockedIncrement((volatile signed __int32 *)&DictionaryEntry->McnDisableCount);
  }
  else if ( DictionaryEntry->McnDisableCount )
  {
    _InterlockedDecrement((volatile signed __int32 *)&DictionaryEntry->McnDisableCount);
    ClassEnableMediaChangeDetection(FdoExtension);
  }
  else
  {
    v8 = -1073741436;
  }
LABEL_12:
  Irp->IoStatus.Status = v8;
  if ( P )
    ExFreePoolWithTag(P, 0);
  ClassReleaseRemoveLock(FdoExtension->DeviceObject, Irp);
  ClassCompleteRequest(FdoExtension->DeviceObject, Irp, 0);
  return v8;
}

```

## disassembly

```asm
0x1400553f4  push    rbx
0x1400553f6  push    rbp
0x1400553f7  push    rsi
0x1400553f8  push    rdi
0x1400553f9  push    r14
0x1400553fb  push    r15
0x1400553fd  sub     rsp, 28h
0x140055401  mov     rax, [rdx+0B8h]
0x140055408  mov     rbp, rdx
0x14005540b  mov     r15, [rdx+18h]
0x14005540f  mov     r14, r8
0x140055412  mov     rsi, rcx
0x140055415  mov     rdx, [rax+30h]
0x140055419  test    rdx, rdx
0x14005541c  jz      short loc_14005542F
0x14005541e  add     rcx, 1A0h
0x140055425  call    GetDictionaryEntry
0x14005542a  mov     rbx, rax
0x14005542d  jmp     short loc_14005543C
0x14005542f  cmp     byte ptr [rbp+40h], 0
0x140055433  jnz     short loc_140055470
0x140055435  lea     rbx, [rcx+2A0h]
0x14005543c  test    rbx, rbx
0x14005543f  jz      short loc_140055470
0x140055441  xor     edi, edi
0x140055443  cmp     [r15], dil
0x140055446  jz      short loc_140055456
0x140055448  mov     rcx, rsi; FdoExtension
0x14005544b  call    ClassDisableMediaChangeDetection
0x140055450  lock inc dword ptr [rbx+14h]
0x140055454  jmp     short loc_140055475
0x140055456  cmp     [rbx+14h], edi
0x140055459  jnz     short loc_140055462
0x14005545b  mov     edi, 0C0000184h
0x140055460  jmp     short loc_140055475
0x140055462  lock dec dword ptr [rbx+14h]
0x140055466  mov     rcx, rsi; FdoExtension
0x140055469  call    ClassEnableMediaChangeDetection
0x14005546e  jmp     short loc_140055475
0x140055470  mov     edi, 0C000000Dh
0x140055475  mov     [rbp+30h], edi
0x140055478  test    r14, r14
0x14005547b  jz      short loc_14005548E
0x14005547d  xor     edx, edx; Tag
0x14005547f  mov     rcx, r14; P
0x140055482  call    cs:__imp_ExFreePoolWithTag
0x140055489  nop     dword ptr [rax+rax+00h]
0x14005548e  mov     rcx, [rsi+8]; DeviceObject
0x140055492  mov     rdx, rbp; Tag
0x140055495  call    ClassReleaseRemoveLock
0x14005549a  mov     rcx, [rsi+8]; DeviceObject
0x14005549e  xor     r8d, r8d; PriorityBoost
0x1400554a1  mov     rdx, rbp; Irp
0x1400554a4  call    ClassCompleteRequest
0x1400554a9  mov     eax, edi
0x1400554ab  add     rsp, 28h
0x1400554af  pop     r15
0x1400554b1  pop     r14
0x1400554b3  pop     rdi
0x1400554b4  pop     rsi
0x1400554b5  pop     rbp
0x1400554b6  pop     rbx
0x1400554b7  retn
```
