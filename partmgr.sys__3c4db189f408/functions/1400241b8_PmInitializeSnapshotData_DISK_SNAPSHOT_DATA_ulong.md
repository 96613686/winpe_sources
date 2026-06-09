# PmInitializeSnapshotData(_DISK_SNAPSHOT_DATA *,ulong)

- ea: `0x1400241b8`
- end: `0x14002420b`
- name: `?PmInitializeSnapshotData@@YAXPEAU_DISK_SNAPSHOT_DATA@@K@Z`
- size: `83`
- prototype: `void __fastcall(_QWORD *Buffer, size_t Size)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000d878`
- `0x140021c90`

## callees

- `0x140011440`

## import_xrefs

- `ntoskrnl!RtlComputeCrc32` at `0x1400241f5`
- `ntoskrnl!RtlComputeCrc32` at `0x1400241f5`

## pseudocode

```c
void __fastcall PmInitializeSnapshotData(_QWORD *Buffer, size_t Size)
{
  memset(Buffer, 0, (unsigned int)Size);
  *((_DWORD *)Buffer + 2) = 1;
  *Buffer = 0x5452415050414E53LL;
  *((_DWORD *)Buffer + 3) = 112;
  *((_DWORD *)Buffer + 5) = 0;
  *((_DWORD *)Buffer + 4) = RtlComputeCrc32(0, (PUCHAR)Buffer, 0x70u);
}

```

## disassembly

```asm
0x1400241b8  push    rbx
0x1400241ba  sub     rsp, 20h
0x1400241be  mov     r8d, edx; Size
0x1400241c1  mov     rbx, rcx
0x1400241c4  xor     edx, edx; Val
0x1400241c6  call    memset
0x1400241cb  mov     rax, 5452415050414E53h
0x1400241d5  mov     dword ptr [rbx+8], 1
0x1400241dc  mov     r8d, 70h ; 'p'; Length
0x1400241e2  mov     [rbx], rax
0x1400241e5  mov     rdx, rbx; Buffer
0x1400241e8  mov     [rbx+0Ch], r8d
0x1400241ec  xor     ecx, ecx; InitialCrc
0x1400241ee  mov     dword ptr [rbx+14h], 0
0x1400241f5  call    cs:__imp_RtlComputeCrc32
0x1400241fc  nop     dword ptr [rax+rax+00h]
0x140024201  mov     [rbx+10h], eax
0x140024204  add     rsp, 20h
0x140024208  pop     rbx
0x140024209  retn
```
