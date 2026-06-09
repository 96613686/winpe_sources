# CQueue::HandleCreatePacketCompletedFailureAsync(_IRP *)

- ea: `0x14001d320`
- end: `0x14001d387`
- name: `?HandleCreatePacketCompletedFailureAsync@CQueue@@UEAAXPEAU_IRP@@@Z`
- size: `103`
- prototype: `void __fastcall(CQueue *__hidden this, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x14000d728`
- `0x140012754`

## pseudocode

```c
void __fastcall CQueue::HandleCreatePacketCompletedFailureAsync(CQueue *this, struct _IRP *a2)
{
  CBaseObject *Information; // rdi
  __int64 v4; // [rsp+30h] [rbp+8h] BYREF
  CQueue *v5; // [rsp+38h] [rbp+10h] BYREF

  Information = (CBaseObject *)a2->IoStatus.Information;
  a2->IoStatus.Information = 0;
  CBaseObject::Release(Information);
  v4 = *((_QWORD *)Information + 5);
  v5 = this;
  *((_QWORD *)Information + 4) = 0;
  *((_QWORD *)Information + 5) = 0;
  CBaseObject::Release(Information);
  R<CTransaction>::~R<CTransaction>(&v4);
  R<CTransaction>::~R<CTransaction>(&v5);
}

```

## disassembly

```asm
0x14001d320  mov     [rsp+arg_10], rbx
0x14001d325  push    rdi
0x14001d326  sub     rsp, 20h
0x14001d32a  mov     rdi, [rdx+38h]
0x14001d32e  mov     rbx, rcx
0x14001d331  mov     rcx, rdi; this
0x14001d334  mov     qword ptr [rdx+38h], 0
0x14001d33c  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001d341  mov     rax, [rdi+28h]
0x14001d345  mov     rcx, rdi; this
0x14001d348  mov     [rsp+28h+arg_0], rax
0x14001d34d  mov     [rsp+28h+arg_8], rbx
0x14001d352  mov     qword ptr [rdi+20h], 0
0x14001d35a  mov     qword ptr [rdi+28h], 0
0x14001d362  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001d367  lea     rcx, [rsp+28h+arg_0]
0x14001d36c  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14001d371  lea     rcx, [rsp+28h+arg_8]
0x14001d376  call    ??1?$R@VCTransaction@@@@QEAA@XZ; R<CTransaction>::~R<CTransaction>(void)
0x14001d37b  mov     rbx, [rsp+28h+arg_10]
0x14001d380  add     rsp, 20h
0x14001d384  pop     rdi
0x14001d385  retn
```
