# CCreatePacketComplete::HandleNotification(_DEVICE_OBJECT *,_IRP *)

- ea: `0x140012368`
- end: `0x14001244a`
- name: `?HandleNotification@CCreatePacketComplete@@QEAAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `226`
- prototype: `void __fastcall(CCreatePacketComplete *__hidden this, struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400051d8`

## callees

- `0x140009a54`
- `0x14000a1d4`
- `0x140012368`
- `0x1400124d0`
- `0x14001255c`
- `0x1400126fc`
- `0x140012754`

## pseudocode

```c
void __fastcall CCreatePacketComplete::HandleNotification(
        CCreatePacketComplete *this,
        struct _DEVICE_OBJECT *a2,
        struct _IRP *a3)
{
  char *DeviceExtension; // r14
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  struct _NAMED_PIPE_CREATE_PARAMETERS *UserBuffer; // rbp
  struct CPacket *v8; // rdi
  struct CPacket *v9; // rbx
  __int64 v10; // rax

  DeviceExtension = (char *)a2->DeviceExtension;
  CurrentStackLocation = a3->Tail.Overlay.CurrentStackLocation;
  UserBuffer = (struct _NAMED_PIPE_CREATE_PARAMETERS *)a3->UserBuffer;
  v8 = 0;
  v9 = CPacketHandleToCPacket(
         (struct CDeviceExt *)DeviceExtension,
         CurrentStackLocation->Parameters.CreatePipe.Parameters);
  if ( UserBuffer )
    v8 = CPacketHandleToCPacket((struct CDeviceExt *)DeviceExtension, UserBuffer);
  CQEntry::ReleaseBuffer(v9);
  if ( v8 )
  {
    CQEntry::ReleaseBuffer(v8);
    if ( CCreatePacket::ReplaceCreatePacketRequestContext((CCreatePacket *)(DeviceExtension + 416), v9, v8) )
    {
      *((_QWORD *)v8 + 4) = *((_QWORD *)v9 + 4);
      v10 = *((_QWORD *)v9 + 5);
      *((_QWORD *)v9 + 4) = 0;
      *((_QWORD *)v8 + 5) = v10;
      *((_QWORD *)v9 + 5) = 0;
      CBaseObject::AddRef(v8);
      CBaseObject::AddRef(v8);
      CBaseObject::Release(v9);
      CBaseObject::Release(v9);
    }
    CBaseObject::Release(v9);
    a3->UserBuffer = 0;
    CurrentStackLocation->Parameters.CreatePipe.Parameters = UserBuffer;
  }
  CCreatePacketComplete::HoldNotification(this, a3);
}

```

## disassembly

```asm
0x140012368  push    rbx
0x14001236a  push    rbp
0x14001236b  push    rsi
0x14001236c  push    rdi
0x14001236d  push    r12
0x14001236f  push    r14
0x140012371  push    r15
0x140012373  sub     rsp, 20h
0x140012377  mov     r14, [rdx+40h]
0x14001237b  mov     r12, rcx
0x14001237e  mov     r15, [r8+0B8h]
0x140012385  mov     rcx, r14; struct CDeviceExt *
0x140012388  mov     rbp, [r8+70h]
0x14001238c  mov     rsi, r8
0x14001238f  mov     rdx, [r15+20h]; void *
0x140012393  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAUCDeviceExt@@PEAX@Z; CPacketHandleToCPacket(CDeviceExt *,void *)
0x140012398  xor     edi, edi
0x14001239a  mov     rbx, rax
0x14001239d  test    rbp, rbp
0x1400123a0  jz      short loc_1400123B0
0x1400123a2  mov     rdx, rbp; void *
0x1400123a5  mov     rcx, r14; struct CDeviceExt *
0x1400123a8  call    ?CPacketHandleToCPacket@@YAPEAVCPacket@@PEAUCDeviceExt@@PEAX@Z; CPacketHandleToCPacket(CDeviceExt *,void *)
0x1400123ad  mov     rdi, rax
0x1400123b0  mov     rcx, rbx; this
0x1400123b3  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x1400123b8  test    rdi, rdi
0x1400123bb  jz      short loc_14001242F
0x1400123bd  mov     rcx, rdi; this
0x1400123c0  call    ?ReleaseBuffer@CQEntry@@QEBAXXZ; CQEntry::ReleaseBuffer(void)
0x1400123c5  lea     rcx, [r14+1A0h]; this
0x1400123cc  mov     r8, rdi; struct CPacket *
0x1400123cf  mov     rdx, rbx; struct CPacket *
0x1400123d2  call    ?ReplaceCreatePacketRequestContext@CCreatePacket@@QEAA_NPEAVCPacket@@0@Z; CCreatePacket::ReplaceCreatePacketRequestContext(CPacket *,CPacket *)
0x1400123d7  test    al, al
0x1400123d9  jz      short loc_14001241B
0x1400123db  mov     rax, [rbx+20h]
0x1400123df  mov     rcx, rdi; this
0x1400123e2  mov     [rdi+20h], rax
0x1400123e6  mov     rax, [rbx+28h]
0x1400123ea  mov     qword ptr [rbx+20h], 0
0x1400123f2  mov     [rdi+28h], rax
0x1400123f6  mov     qword ptr [rbx+28h], 0
0x1400123fe  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x140012403  mov     rcx, rdi; this
0x140012406  call    ?AddRef@CBaseObject@@QEAAKXZ; CBaseObject::AddRef(void)
0x14001240b  mov     rcx, rbx; this
0x14001240e  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140012413  mov     rcx, rbx; this
0x140012416  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x14001241b  mov     rcx, rbx; this
0x14001241e  call    ?Release@CBaseObject@@QEAAKXZ; CBaseObject::Release(void)
0x140012423  mov     qword ptr [rsi+70h], 0
0x14001242b  mov     [r15+20h], rbp
0x14001242f  mov     rdx, rsi; struct _IRP *
0x140012432  mov     rcx, r12; this
0x140012435  call    ?HoldNotification@CCreatePacketComplete@@AEAAXPEAU_IRP@@@Z; CCreatePacketComplete::HoldNotification(_IRP *)
0x14001243a  add     rsp, 20h
0x14001243e  pop     r15
0x140012440  pop     r14
0x140012442  pop     r12
0x140012444  pop     rdi
0x140012445  pop     rsi
0x140012446  pop     rbp
0x140012447  pop     rbx
0x140012448  retn
```
