# WheaRecoveryBugCheck

- ea: `0x14068ec00`
- end: `0x14068ec62`
- name: `WheaRecoveryBugCheck`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140264f20`
- `0x1405ff3b0`

## callees

- `0x140265a08`
- `0x14068ecf0`
- `0x14068ee80`

## import_xrefs

- `PSHED!PshedWriteErrorRecord` at `0x14068ec2d`
- `PSHED!PshedWriteErrorRecord` at `0x14068ec2d`
- `PSHED!PshedBugCheckSystem` at `0x14068ec4a`
- `PSHED!PshedBugCheckSystem` at `0x14068ec4a`

## pseudocode

```c
__int64 __fastcall WheaRecoveryBugCheck(__int64 a1, __int64 a2)
{
  WheapCompressErrorRecord(3, a1);
  WheapPersistPageForMemoryError(a1);
  PshedWriteErrorRecord(0, *(unsigned int *)(a1 + 20), a1);
  WheapAddToDumpFile(a1, *(unsigned int *)(a1 + 20));
  return PshedBugCheckSystem(a2, a1);
}

```

## disassembly

```asm
0x14068ec00  mov     [rsp+arg_0], rbx
0x14068ec05  push    rdi
0x14068ec06  sub     rsp, 20h
0x14068ec0a  mov     rdi, rdx
0x14068ec0d  mov     rbx, rcx
0x14068ec10  mov     rdx, rcx
0x14068ec13  mov     ecx, 3
0x14068ec18  call    WheapCompressErrorRecord
0x14068ec1d  mov     rcx, rbx
0x14068ec20  call    WheapPersistPageForMemoryError
0x14068ec25  mov     edx, [rbx+14h]
0x14068ec28  mov     r8, rbx
0x14068ec2b  xor     ecx, ecx
0x14068ec2d  call    cs:__imp_PshedWriteErrorRecord
0x14068ec34  nop     dword ptr [rax+rax+00h]
0x14068ec39  mov     edx, [rbx+14h]
0x14068ec3c  mov     rcx, rbx
0x14068ec3f  call    WheapAddToDumpFile
0x14068ec44  mov     rdx, rbx
0x14068ec47  mov     rcx, rdi
0x14068ec4a  call    cs:__imp_PshedBugCheckSystem
0x14068ec51  nop     dword ptr [rax+rax+00h]
0x14068ec56  mov     rbx, [rsp+28h+arg_0]
0x14068ec5b  add     rsp, 20h
0x14068ec5f  pop     rdi
0x14068ec60  retn
```
