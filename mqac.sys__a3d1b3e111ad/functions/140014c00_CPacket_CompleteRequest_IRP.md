# CPacket::CompleteRequest(_IRP *)

- ea: `0x140014c00`
- end: `0x140014c40`
- name: `?CompleteRequest@CPacket@@QEAAJPEAU_IRP@@@Z`
- size: `64`
- prototype: `int(CPacket *__hidden this, struct _IRP *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14001a09c`
- `0x14001e0c0`

## callees

- `0x140014c00`
- `0x140018a04`

## import_xrefs

- `ntoskrnl!IofCompleteRequest` at `0x140014c26`
- `ntoskrnl!IofCompleteRequest` at `0x140014c26`

## pseudocode

```c
__int64 __fastcall CPacket::CompleteRequest(CPacket *this, struct _IRP *a2)
{
  NTSTATUS v3; // eax
  unsigned int v4; // ebx

  v3 = CPacket::ProcessRequest(this, a2, 0);
  v4 = v3;
  if ( v3 != 259 )
  {
    a2->IoStatus.Status = v3;
    IofCompleteRequest(a2, 2);
  }
  return v4;
}

```

## disassembly

```asm
0x140014c00  mov     [rsp+arg_0], rbx
0x140014c05  push    rdi
0x140014c06  sub     rsp, 20h
0x140014c0a  xor     r8d, r8d; int
0x140014c0d  mov     rdi, rdx
0x140014c10  call    ?ProcessRequest@CPacket@@QEAAJPEAU_IRP@@H@Z; CPacket::ProcessRequest(_IRP *,int)
0x140014c15  mov     ebx, eax
0x140014c17  cmp     eax, 103h
0x140014c1c  jz      short loc_140014C32
0x140014c1e  mov     dl, 2; PriorityBoost
0x140014c20  mov     [rdi+30h], eax
0x140014c23  mov     rcx, rdi; Irp
0x140014c26  call    cs:__imp_IofCompleteRequest
0x140014c2d  nop     dword ptr [rax+rax+00h]
0x140014c32  mov     eax, ebx
0x140014c34  mov     rbx, [rsp+28h+arg_0]
0x140014c39  add     rsp, 20h
0x140014c3d  pop     rdi
0x140014c3e  retn
```
