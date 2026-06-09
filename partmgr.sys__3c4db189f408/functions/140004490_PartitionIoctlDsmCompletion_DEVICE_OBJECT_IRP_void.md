# PartitionIoctlDsmCompletion(_DEVICE_OBJECT *,_IRP *,void *)

- ea: `0x140004490`
- end: `0x1400044fb`
- name: `?PartitionIoctlDsmCompletion@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@PEAX@Z`
- size: `107`
- prototype: `__int64 __fastcall(struct _DEVICE_OBJECT *, struct _IRP *, struct _IRP *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004490`
- `0x140011140`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400044c6`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400044c6`

## pseudocode

```c
__int64 __fastcall PartitionIoctlDsmCompletion(struct _DEVICE_OBJECT *a1, struct _IRP *a2, struct _IRP *a3)
{
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rcx
  struct _IRP *MasterIrp; // rsi
  size_t Length; // rax

  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  MasterIrp = a2->AssociatedIrp.MasterIrp;
  Length = CurrentStackLocation->Parameters.Read.Length;
  if ( a2->PendingReturned )
    CurrentStackLocation->Control |= 1u;
  if ( (_DWORD)Length )
    memmove(a3, MasterIrp, Length);
  a2->AssociatedIrp.MasterIrp = a3;
  ExFreePoolWithTag(MasterIrp, 0);
  return 0;
}

```

## disassembly

```asm
0x140004490  mov     [rsp+arg_0], rbx
0x140004495  mov     [rsp+arg_8], rsi
0x14000449a  push    rdi
0x14000449b  sub     rsp, 20h
0x14000449f  cmp     byte ptr [rdx+41h], 0
0x1400044a3  mov     rdi, r8
0x1400044a6  mov     rcx, [rdx+0B8h]
0x1400044ad  mov     rbx, rdx
0x1400044b0  mov     rsi, [rdx+18h]
0x1400044b4  mov     eax, [rcx+8]
0x1400044b7  jnz     short loc_1400044E5
0x1400044b9  test    eax, eax
0x1400044bb  jnz     short loc_1400044EB
0x1400044bd  xor     edx, edx; Tag
0x1400044bf  mov     [rbx+18h], rdi
0x1400044c3  mov     rcx, rsi; P
0x1400044c6  call    cs:__imp_ExFreePoolWithTag
0x1400044cd  nop     dword ptr [rax+rax+00h]
0x1400044d2  mov     rbx, [rsp+28h+arg_0]
0x1400044d7  xor     eax, eax
0x1400044d9  mov     rsi, [rsp+28h+arg_8]
0x1400044de  add     rsp, 20h
0x1400044e2  pop     rdi
0x1400044e3  retn
0x1400044e5  or      byte ptr [rcx+3], 1
0x1400044e9  jmp     short loc_1400044B9
0x1400044eb  mov     r8, rax; Size
0x1400044ee  mov     rdx, rsi; Src
0x1400044f1  mov     rcx, rdi; void *
0x1400044f4  call    memmove
0x1400044f9  jmp     short loc_1400044BD
```
