# CQueue::CreateCursor(_IRP *,_FILE_OBJECT *)

- ea: `0x14001cbe0`
- end: `0x14001cc66`
- name: `?CreateCursor@CQueue@@UEAAJPEAU_IRP@@PEAU_FILE_OBJECT@@@Z`
- size: `134`
- prototype: `__int64 __fastcall(CQueue *__hidden this, struct _IRP *, struct _FILE_OBJECT *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x14000c914`
- `0x14000cb4c`
- `0x14001cbe0`

## pseudocode

```c
__int64 __fastcall CQueue::CreateCursor(struct _DEVICE_OBJECT **this, struct _IRP *a2, struct _FILE_OBJECT *a3)
{
  unsigned int v5; // eax
  __int64 result; // rax
  struct CCursor *v7; // rax
  int v8; // r8d
  CQueue **v9; // rdx
  CQueue *v10; // rax

  v5 = CCursor::Create((__int64)(this + 20), (__int64)a3, this[8], (CBaseObject *)this);
  if ( !v5 )
    return 3221225626LL;
  v7 = CCursor::Validate(this[8], v5);
  v9 = (CQueue **)this[10];
  if ( *v9 != (CQueue *)(this + 9) )
    __fastfail(3u);
  v10 = (struct CCursor *)((char *)v7 + 16);
  *((_QWORD *)v10 + 1) = v9;
  *(_QWORD *)v10 = this + 9;
  *v9 = v10;
  this[10] = (struct _DEVICE_OBJECT *)v10;
  *(_DWORD *)a2->AssociatedIrp.MasterIrp = v8;
  result = 0;
  a2->IoStatus.Information = 4;
  return result;
}

```

## disassembly

```asm
0x14001cbe0  mov     [rsp+arg_0], rbx
0x14001cbe5  push    rdi
0x14001cbe6  sub     rsp, 20h
0x14001cbea  mov     rbx, rcx
0x14001cbed  mov     rax, r8
0x14001cbf0  mov     rdi, rdx
0x14001cbf3  add     rcx, 0A0h
0x14001cbfa  mov     r9, rbx
0x14001cbfd  mov     rdx, rax
0x14001cc00  mov     r8, [rbx+40h]
0x14001cc04  call    ?Create@CCursor@@SAKAEBV?$CAVLTree1@VCPacket@@_KVCGetLookupId@1@V?$Less@_K@@$0EI@@@PEBU_FILE_OBJECT@@PEAU_DEVICE_OBJECT@@PEAVCUserQueue@@@Z; CCursor::Create(CAVLTree1<CPacket,unsigned __int64,CPacket::CGetLookupId,Less<unsigned __int64>,72> const &,_FILE_OBJECT const *,_DEVICE_OBJECT *,CUserQueue *)
0x14001cc09  mov     r8d, eax
0x14001cc0c  test    eax, eax
0x14001cc0e  jnz     short loc_14001CC17
0x14001cc10  mov     eax, 0C000009Ah
0x14001cc15  jmp     short loc_14001CC5A
0x14001cc17  mov     rcx, [rbx+40h]; struct _DEVICE_OBJECT *
0x14001cc1b  mov     edx, r8d; unsigned int
0x14001cc1e  call    ?Validate@CCursor@@SAPEAV1@PEAU_DEVICE_OBJECT@@K@Z; CCursor::Validate(_DEVICE_OBJECT *,ulong)
0x14001cc23  lea     rcx, [rbx+48h]
0x14001cc27  mov     rdx, [rcx+8]
0x14001cc2b  cmp     [rdx], rcx
0x14001cc2e  jz      short loc_14001CC37
0x14001cc30  mov     ecx, 3
0x14001cc35  int     29h; Win8: RtlFailFast(ecx)
0x14001cc37  add     rax, 10h
0x14001cc3b  mov     [rax+8], rdx
0x14001cc3f  mov     [rax], rcx
0x14001cc42  mov     [rdx], rax
0x14001cc45  mov     [rcx+8], rax
0x14001cc49  mov     rax, [rdi+18h]
0x14001cc4d  mov     [rax], r8d
0x14001cc50  xor     eax, eax
0x14001cc52  mov     qword ptr [rdi+38h], 4
0x14001cc5a  mov     rbx, [rsp+28h+arg_0]
0x14001cc5f  add     rsp, 20h
0x14001cc63  pop     rdi
0x14001cc64  retn
```
