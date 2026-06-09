# CdInitializeIo

- ea: `0x14000d440`
- end: `0x14000d490`
- name: `CdInitializeIo`
- size: `80`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x140008230`
- `0x14000c5c0`

## import_xrefs

- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000d47e`
- `ntoskrnl!ZwAllocateLocallyUniqueId` at `0x14000d47e`

## pseudocode

```c
NTSTATUS __fastcall CdInitializeIo(__int64 a1, __int64 a2, char a3, __int64 a4, __int64 a5, __int64 a6, __int64 a7)
{
  __int64 v7; // r10

  v7 = *(_QWORD *)(a1 + 184);
  *(_QWORD *)(v7 - 56) = a5;
  *(_QWORD *)(v7 - 48) = a6;
  *(_QWORD *)(v7 - 40) = a7;
  *(_BYTE *)(v7 - 72) = 15;
  *(_BYTE *)(v7 - 71) = a3;
  *(_QWORD *)(v7 - 64) = a2;
  *(_QWORD *)(a1 + 120) = a4;
  return ZwAllocateLocallyUniqueId((PLUID)(a1 + 136));
}

```

## disassembly

```asm
0x14000d440  sub     rsp, 28h
0x14000d444  mov     r10, [rcx+0B8h]
0x14000d44b  mov     rax, [rsp+28h+arg_20]
0x14000d450  mov     [r10-38h], rax
0x14000d454  mov     rax, [rsp+28h+arg_28]
0x14000d459  mov     [r10-30h], rax
0x14000d45d  mov     rax, [rsp+28h+arg_30]
0x14000d462  mov     [r10-28h], rax
0x14000d466  mov     byte ptr [r10-48h], 0Fh
0x14000d46b  mov     [r10-47h], r8b
0x14000d46f  mov     [r10-40h], rdx
0x14000d473  mov     [rcx+78h], r9
0x14000d477  add     rcx, 88h; Luid
0x14000d47e  call    cs:__imp_ZwAllocateLocallyUniqueId
0x14000d485  nop     dword ptr [rax+rax+00h]
0x14000d48a  add     rsp, 28h
0x14000d48e  retn
```
