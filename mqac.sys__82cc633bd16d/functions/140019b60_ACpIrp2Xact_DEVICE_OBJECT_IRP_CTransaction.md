# ACpIrp2Xact(_DEVICE_OBJECT *,_IRP *,CTransaction * *)

- ea: `0x140019b60`
- end: `0x140019c10`
- name: `?ACpIrp2Xact@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAPEAVCTransaction@@@Z`
- size: `176`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct CTransaction **)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140019f04`

## callees

- `0x140019b60`
- `0x14001fbb4`

## import_xrefs

- `ntoskrnl!ProbeForRead` at `0x140019bd7`
- `ntoskrnl!ProbeForRead` at `0x140019bd7`

## pseudocode

```c
__int64 __fastcall ACpIrp2Xact(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct CTransaction **a3)
{
  DWORD LowPart; // r9d
  PETHREAD Thread; // rbx
  struct CTransaction *v8; // rax

  *a3 = 0;
  LowPart = a2->Tail.Overlay.CurrentStackLocation->Parameters.Read.ByteOffset.LowPart;
  if ( LowPart == 426066256 || LowPart == 426066184 )
  {
    Thread = a2->AssociatedIrp.MasterIrp[1].Tail.Overlay.Thread;
  }
  else
  {
    if ( LowPart != 426066064 && LowPart != 426065992 )
      return 0;
    Thread = (PETHREAD)a2->AssociatedIrp.MasterIrp->Tail.Overlay.PacketType;
  }
  if ( !Thread )
    return 0;
  ProbeForRead(Thread, 0x10u, 1u);
  v8 = CTransaction::Find(a1, Thread);
  *a3 = v8;
  return v8 == 0 ? 0xC00E0051 : 0;
}

```

## disassembly

```asm
0x140019b60  mov     [rsp+arg_0], rbx
0x140019b65  mov     [rsp+arg_8], rsi
0x140019b6a  push    rdi
0x140019b6b  sub     rsp, 20h
0x140019b6f  mov     rdi, r8
0x140019b72  mov     rsi, rcx
0x140019b75  mov     qword ptr [r8], 0
0x140019b7c  mov     rax, [rdx+0B8h]
0x140019b83  mov     r9d, [rax+18h]
0x140019b87  cmp     r9d, 19654150h
0x140019b8e  jz      short loc_140019BB7
0x140019b90  cmp     r9d, 19654108h
0x140019b97  jz      short loc_140019BB7
0x140019b99  cmp     r9d, 19654090h
0x140019ba0  jz      short loc_140019BAB
0x140019ba2  cmp     r9d, 19654048h
0x140019ba9  jnz     short loc_140019BC7
0x140019bab  mov     rax, [rdx+18h]
0x140019baf  mov     ebx, [rax+0B8h]
0x140019bb5  jmp     short loc_140019BC2
0x140019bb7  mov     rax, [rdx+18h]
0x140019bbb  mov     rbx, [rax+168h]
0x140019bc2  test    rbx, rbx
0x140019bc5  jnz     short loc_140019BCB
0x140019bc7  xor     eax, eax
0x140019bc9  jmp     short loc_140019BFF
0x140019bcb  mov     edx, 10h; Length
0x140019bd0  lea     r8d, [rdx-0Fh]; Alignment
0x140019bd4  mov     rcx, rbx; Address
0x140019bd7  call    cs:__imp_ProbeForRead
0x140019bde  nop     dword ptr [rax+rax+00h]
0x140019be3  mov     rdx, rbx; struct BOID *
0x140019be6  mov     rcx, rsi; struct _DEVICE_OBJECT *
0x140019be9  call    ?Find@CTransaction@@SAPEAV1@PEAU_DEVICE_OBJECT@@PEBUBOID@@@Z; CTransaction::Find(_DEVICE_OBJECT *,BOID const *)
0x140019bee  mov     [rdi], rax
0x140019bf1  neg     rax
0x140019bf4  sbb     eax, eax
0x140019bf6  not     eax
0x140019bf8  and     eax, 0C00E0051h
0x140019bfd  jmp     short $+2
0x140019bff  mov     rbx, [rsp+28h+arg_0]
0x140019c04  mov     rsi, [rsp+28h+arg_8]
0x140019c09  add     rsp, 20h
0x140019c0d  pop     rdi
0x140019c0e  retn
```
