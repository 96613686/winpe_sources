# FatPrepareWriteVolumeFile

- ea: `0x1400244bc`
- end: `0x14002457d`
- name: `FatPrepareWriteVolumeFile`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140022870`
- `0x140022c48`

## callees

- `0x1400019b8`
- `0x1400244bc`

## import_xrefs

- `ntoskrnl!CcPinRead` at `0x140024530`
- `ntoskrnl!CcPinRead` at `0x140024530`
- `ntoskrnl!CcUnpinData` at `0x14005b7d0`
- `ntoskrnl!CcUnpinData` at `0x14005b7d0`
- `ntoskrnl!ExRaiseStatus` at `0x1400244ed`
- `ntoskrnl!ExRaiseStatus` at `0x140024548`
- `ntoskrnl!ExRaiseStatus` at `0x1400244ed`
- `ntoskrnl!ExRaiseStatus` at `0x140024548`

## pseudocode

```c
__int64 __fastcall FatPrepareWriteVolumeFile(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        ULONG a4,
        PVOID *Bcb,
        PVOID *Buffer,
        char a7)
{
  __int64 v9; // r9
  union _LARGE_INTEGER FileOffset; // [rsp+30h] [rbp-18h] BYREF

  if ( ((a3 ^ (a4 + a3 - 1)) & 0xFFFC0000) != 0 )
  {
    *(_DWORD *)(a1 + 72) = -1073741566;
    ExRaiseStatus(-1073741566);
  }
  FileOffset.QuadPart = a3;
  if ( !CcPinRead(*(PFILE_OBJECT *)(a2 + 728), &FileOffset, a4, (*(_DWORD *)(a1 + 68) >> 1) & 1, Bcb, Buffer) )
  {
    *(_DWORD *)(a1 + 72) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  LOBYTE(v9) = a7;
  return FatSetDirtyBcb(a1, *Bcb, a2, v9);
}

```

## disassembly

```asm
0x1400244bc  mov     [rsp+arg_0], rbx
0x1400244c1  mov     [rsp+arg_8], rsi
0x1400244c6  push    rdi
0x1400244c7  sub     rsp, 40h
0x1400244cb  mov     r10d, r9d
0x1400244ce  mov     rdi, rdx
0x1400244d1  mov     rbx, rcx
0x1400244d4  lea     eax, [r8-1]
0x1400244d8  add     eax, r9d
0x1400244db  xor     eax, r8d
0x1400244de  test    eax, 0FFFC0000h
0x1400244e3  jz      short loc_1400244FA
0x1400244e5  mov     ecx, 0C0000102h; Status
0x1400244ea  mov     [rbx+48h], ecx
0x1400244ed  call    cs:__imp_ExRaiseStatus
0x1400244fa  mov     eax, r8d
0x1400244fd  mov     qword ptr [rsp+48h+FileOffset], rax
0x140024502  mov     r9d, [rcx+44h]
0x140024506  shr     r9d, 1
0x140024509  and     r9d, 1; Flags
0x14002450d  mov     rax, [rsp+48h+arg_28]
0x140024512  mov     [rsp+48h+Buffer], rax; Buffer
0x140024517  mov     rsi, [rsp+48h+arg_20]
0x14002451c  mov     [rsp+48h+Bcb], rsi; Bcb
0x140024521  mov     r8d, r10d; Length
0x140024524  lea     rdx, [rsp+48h+FileOffset]; FileOffset
0x140024529  mov     rcx, [rdi+2D8h]; FileObject
0x140024530  call    cs:__imp_CcPinRead
0x140024537  nop     dword ptr [rax+rax+00h]
0x14002453c  test    al, al
0x14002453e  jnz     short loc_140024555
0x140024540  mov     ecx, 0C00000D8h; Status
0x140024545  mov     [rbx+48h], ecx
0x140024548  call    cs:__imp_ExRaiseStatus
0x140024555  mov     r9b, [rsp+48h+arg_30]
0x14002455d  mov     r8, rdi
0x140024560  mov     rdx, [rsi]
0x140024563  mov     rcx, rbx
0x140024566  call    FatSetDirtyBcb
0x14002456b  nop
0x14002456c  mov     rbx, [rsp+48h+arg_0]
0x140024571  mov     rsi, [rsp+48h+arg_8]
0x140024576  add     rsp, 40h
0x14002457a  pop     rdi
0x14002457b  retn
0x14005b7b5  push    rbx
0x14005b7b7  push    rbp
0x14005b7b8  sub     rsp, 38h
0x14005b7bc  mov     rbp, rdx
0x14005b7bf  test    cl, cl
0x14005b7c1  jz      short loc_14005B7E3
0x14005b7c3  mov     rbx, [rbp+70h]
0x14005b7c7  cmp     qword ptr [rbx], 0
0x14005b7cb  jz      short loc_14005B7E3
0x14005b7cd  mov     rcx, [rbx]; Bcb
0x14005b7d0  call    cs:__imp_CcUnpinData
0x14005b7d7  nop     dword ptr [rax+rax+00h]
0x14005b7dc  mov     qword ptr [rbx], 0
0x14005b7e3  add     rsp, 38h
0x14005b7e7  pop     rbp
0x14005b7e8  pop     rbx
0x14005b7e9  retn
```
