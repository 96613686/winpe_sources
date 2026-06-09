# CKSThunkDevice::CreateFilterFile(_IRP *)

- ea: `0x140001e10`
- end: `0x140001e76`
- name: `?CreateFilterFile@CKSThunkDevice@@UEAAPEAVCKernelFilterFile@@PEAU_IRP@@@Z`
- size: `102`
- prototype: `struct CKernelFilterFile *__fastcall(CKSThunkDevice *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001e10`
- `0x140004540`
- `0x14000bbec`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001e37`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001e37`

## pseudocode

```c
struct CKernelFilterFile *__fastcall CKSThunkDevice::CreateFilterFile(CKSThunkDevice *this, struct _IRP *a2)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rsi
  struct _IRP *MasterIrp; // rbp
  struct CKernelFilterFile *result; // rax
  CKSThunkPin *v6; // rbx

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  result = (struct CKernelFilterFile *)ExAllocatePoolWithTag((POOL_TYPE)512, 0x78u, 0x774E434Bu);
  v6 = result;
  if ( result )
  {
    memset(result, 0, 0x78u);
    return CKSThunkPin::CKSThunkPin(
             v6,
             CurrentStackLocation->FileObject,
             this,
             (union KSDATAFORMAT *)&MasterIrp->UserIosb);
  }
  return result;
}

```

## disassembly

```asm
0x140001e10  push    rbx
0x140001e12  push    rbp
0x140001e13  push    rsi
0x140001e14  push    rdi
0x140001e15  sub     rsp, 28h
0x140001e19  mov     rsi, [rdx+0B8h]
0x140001e20  mov     rdi, rcx
0x140001e23  mov     rbp, [rdx+18h]
0x140001e27  mov     ecx, 200h; PoolType
0x140001e2c  mov     edx, 78h ; 'x'; NumberOfBytes
0x140001e31  mov     r8d, 774E434Bh; Tag
0x140001e37  call    cs:__imp_ExAllocatePoolWithTag
0x140001e3e  nop     dword ptr [rax+rax+00h]
0x140001e43  mov     rbx, rax
0x140001e46  test    rax, rax
0x140001e49  jz      short loc_140001E6C
0x140001e4b  xor     edx, edx; Val
0x140001e4d  mov     rcx, rax; void *
0x140001e50  lea     r8d, [rdx+78h]; Size
0x140001e54  call    memset
0x140001e59  mov     rdx, [rsi+30h]; struct _FILE_OBJECT *
0x140001e5d  lea     r9, [rbp+48h]; union KSDATAFORMAT *
0x140001e61  mov     r8, rdi; struct CKSThunkDevice *
0x140001e64  mov     rcx, rbx; this
0x140001e67  call    ??0CKSThunkPin@@QEAA@PEAU_FILE_OBJECT@@PEAVCKSThunkDevice@@PEATKSDATAFORMAT@@@Z; CKSThunkPin::CKSThunkPin(_FILE_OBJECT *,CKSThunkDevice *,KSDATAFORMAT *)
0x140001e6c  add     rsp, 28h
0x140001e70  pop     rdi
0x140001e71  pop     rsi
0x140001e72  pop     rbp
0x140001e73  pop     rbx
0x140001e74  retn
```
