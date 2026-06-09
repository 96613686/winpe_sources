# PmPowerChanged(_DEVICE_EXTENSION *,_LIST_ENTRY *)

- ea: `0x140022cf0`
- end: `0x140022de1`
- name: `?PmPowerChanged@@YAXPEAU_DEVICE_EXTENSION@@PEAU_LIST_ENTRY@@@Z`
- size: `241`
- prototype: `void __fastcall(struct _DEVICE_EXTENSION *, struct _LIST_ENTRY *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1400087c0`

## callees

- `0x140022cf0`

## import_xrefs

- `ntoskrnl!IoForwardIrpSynchronously` at `0x140022db3`
- `ntoskrnl!IoForwardIrpSynchronously` at `0x140022db3`
- `ntoskrnl!IoReuseIrp` at `0x140022d62`
- `ntoskrnl!IoReuseIrp` at `0x140022d62`

## pseudocode

```c
void __fastcall PmPowerChanged(struct _DEVICE_EXTENSION *a1, struct _LIST_ENTRY *a2)
{
  struct _LIST_ENTRY *Flink; // rbx
  IRP *v5; // rcx
  __int64 v6; // rax
  IRP *v7; // rdx
  struct _DEVICE_OBJECT *Blink; // rcx
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int128 i; // [rsp+20h] [rbp-28h] BYREF
  __int64 v11; // [rsp+30h] [rbp-18h]

  Flink = a2->Flink;
  v11 = 0;
  for ( i = 0; Flink != a2; Flink = Flink->Flink )
  {
    if ( Flink[-1].Blink )
    {
      v5 = (IRP *)*((_QWORD *)a1 + 107);
      *(_QWORD *)&i = Flink[-7].Flink;
      *((_QWORD *)&i + 1) = *((_QWORD *)a1 + 3);
      LODWORD(v11) = *((_DWORD *)a1 + 152);
      IoReuseIrp(v5, -1073741637);
      v6 = *((_QWORD *)a1 + 107);
      --*(_BYTE *)(v6 + 67);
      *(_QWORD *)(v6 + 184) -= 72LL;
      v7 = (IRP *)*((_QWORD *)a1 + 107);
      Blink = (struct _DEVICE_OBJECT *)Flink[-1].Blink[2].Blink;
      CurrentStackLocation = v7->Tail.Overlay.CurrentStackLocation;
      CurrentStackLocation->MajorFunction = 15;
      v7->AssociatedIrp.MasterIrp = (struct _IRP *)&i;
      CurrentStackLocation->Parameters.Read.Length = 0;
      CurrentStackLocation->Parameters.Create.Options = 24;
      CurrentStackLocation->Parameters.Read.ByteOffset.LowPart = 7733288;
      IoForwardIrpSynchronously(Blink, v7);
    }
  }
}

```

## disassembly

```asm
0x140022cf0  mov     [rsp+arg_8], rbx
0x140022cf5  mov     [rsp+arg_10], rsi
0x140022cfa  push    rdi
0x140022cfb  sub     rsp, 40h
0x140022cff  mov     rbx, [rdx]
0x140022d02  xor     eax, eax
0x140022d04  mov     [rsp+48h+var_18], rax
0x140022d09  xorps   xmm0, xmm0
0x140022d0c  mov     rdi, rdx
0x140022d0f  mov     rsi, rcx
0x140022d12  movups  [rsp+48h+var_28], xmm0
0x140022d17  cmp     rbx, rdx
0x140022d1a  jz      loc_140022DD0
0x140022d20  mov     [rsp+48h+arg_0], rbp
0x140022d25  xor     ebp, ebp
0x140022d27  nop     word ptr [rax+rax+00000000h]
0x140022d30  cmp     [rbx-8], rbp
0x140022d34  jz      loc_140022DBF
0x140022d3a  mov     rax, [rbx-70h]
0x140022d3e  mov     edx, 0C00000BBh; Iostatus
0x140022d43  mov     rcx, [rsi+358h]; Irp
0x140022d4a  mov     qword ptr [rsp+48h+var_28], rax
0x140022d4f  mov     rax, [rsi+18h]
0x140022d53  mov     qword ptr [rsp+48h+var_28+8], rax
0x140022d58  mov     eax, [rsi+260h]
0x140022d5e  mov     dword ptr [rsp+48h+var_18], eax
0x140022d62  call    cs:__imp_IoReuseIrp
0x140022d69  nop     dword ptr [rax+rax+00h]
0x140022d6e  mov     rax, [rsi+358h]
0x140022d75  lea     r8, [rsp+48h+var_28]
0x140022d7a  dec     byte ptr [rax+43h]
0x140022d7d  add     qword ptr [rax+0B8h], 0FFFFFFFFFFFFFFB8h
0x140022d85  mov     rax, [rbx-8]
0x140022d89  mov     rdx, [rsi+358h]; Irp
0x140022d90  mov     rcx, [rax+28h]; DeviceObject
0x140022d94  mov     rax, [rdx+0B8h]
0x140022d9b  mov     byte ptr [rax], 0Fh
0x140022d9e  mov     [rdx+18h], r8
0x140022da2  mov     [rax+8], ebp
0x140022da5  mov     dword ptr [rax+10h], 18h
0x140022dac  mov     dword ptr [rax+18h], 760028h
0x140022db3  call    cs:__imp_IoForwardIrpSynchronously
0x140022dba  nop     dword ptr [rax+rax+00h]
0x140022dbf  mov     rbx, [rbx]
0x140022dc2  cmp     rbx, rdi
0x140022dc5  jnz     loc_140022D30
0x140022dcb  mov     rbp, [rsp+48h+arg_0]
0x140022dd0  mov     rbx, [rsp+48h+arg_8]
0x140022dd5  mov     rsi, [rsp+48h+arg_10]
0x140022dda  add     rsp, 40h
0x140022dde  pop     rdi
0x140022ddf  retn
```
