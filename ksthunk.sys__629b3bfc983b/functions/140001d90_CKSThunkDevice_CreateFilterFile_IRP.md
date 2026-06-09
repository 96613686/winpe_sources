# CKSThunkDevice::CreateFilterFile(_IRP *)

- ea: `0x140001d90`
- end: `0x140001df6`
- name: `?CreateFilterFile@CKSThunkDevice@@UEAAPEAVCKernelFilterFile@@PEAU_IRP@@@Z`
- size: `102`
- prototype: `struct CKernelFilterFile *__fastcall(CKSThunkDevice *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140001d90`
- `0x140003ac0`
- `0x14000ac8c`

## import_xrefs

- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001db7`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140001db7`

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
0x140001d90  push    rbx
0x140001d92  push    rbp
0x140001d93  push    rsi
0x140001d94  push    rdi
0x140001d95  sub     rsp, 28h
0x140001d99  mov     rsi, [rdx+0B8h]
0x140001da0  mov     rdi, rcx
0x140001da3  mov     rbp, [rdx+18h]
0x140001da7  mov     ecx, 200h; PoolType
0x140001dac  mov     edx, 78h ; 'x'; NumberOfBytes
0x140001db1  mov     r8d, 774E434Bh; Tag
0x140001db7  call    cs:__imp_ExAllocatePoolWithTag
0x140001dbe  nop     dword ptr [rax+rax+00h]
0x140001dc3  mov     rbx, rax
0x140001dc6  test    rax, rax
0x140001dc9  jz      short loc_140001DEC
0x140001dcb  xor     edx, edx; Val
0x140001dcd  mov     rcx, rax; void *
0x140001dd0  lea     r8d, [rdx+78h]; Size
0x140001dd4  call    memset
0x140001dd9  mov     rdx, [rsi+30h]; struct _FILE_OBJECT *
0x140001ddd  lea     r9, [rbp+48h]; union KSDATAFORMAT *
0x140001de1  mov     r8, rdi; struct CKSThunkDevice *
0x140001de4  mov     rcx, rbx; this
0x140001de7  call    ??0CKSThunkPin@@QEAA@PEAU_FILE_OBJECT@@PEAVCKSThunkDevice@@PEATKSDATAFORMAT@@@Z; CKSThunkPin::CKSThunkPin(_FILE_OBJECT *,CKSThunkDevice *,KSDATAFORMAT *)
0x140001dec  add     rsp, 28h
0x140001df0  pop     rdi
0x140001df1  pop     rsi
0x140001df2  pop     rbp
0x140001df3  pop     rbx
0x140001df4  retn
```
