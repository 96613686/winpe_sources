# RtlCopyToUser

- ea: `0x1400080c4`
- end: `0x140008121`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140002020`
- `0x14000aa00`
- `0x14000ce70`

## callees

- `0x14000113f`
- `0x140001500`
- `0x1400080c4`

## pseudocode

```c
void *__fastcall RtlCopyToUser(void *a1, void *Src, size_t Size)
{
  void *result; // rax

  result = 0;
  if ( Size )
  {
    ProbeForRead_0(a1, Size, 1u);
    return RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x1400080c4  mov     [rsp+arg_0], rbx
0x1400080c9  mov     [rsp+arg_8], rsi
0x1400080ce  push    rdi
0x1400080cf  sub     rsp, 20h
0x1400080d3  mov     rax, cs:qword_1400072B0
0x1400080da  mov     rbx, r8
0x1400080dd  mov     rsi, rdx
0x1400080e0  mov     rdi, rcx
0x1400080e3  test    rax, rax
0x1400080e6  jz      short loc_1400080EF
0x1400080e8  call    rax ; qword_1400072B0
0x1400080ea  nop     dword ptr [rax]
0x1400080ed  jmp     short loc_140008110
0x1400080ef  test    rbx, rbx
0x1400080f2  jz      short loc_140008110
0x1400080f4  mov     r8d, 1; Alignment
0x1400080fa  mov     rdx, rbx; Length
0x1400080fd  call    ProbeForRead_0
0x140008102  mov     r8, rbx; Size
0x140008105  mov     rdx, rsi; Src
0x140008108  mov     rcx, rdi; void *
0x14000810b  call    RtlCopyVolatileMemory
0x140008110  mov     rbx, [rsp+28h+arg_0]
0x140008115  mov     rsi, [rsp+28h+arg_8]
0x14000811a  add     rsp, 20h
0x14000811e  pop     rdi
0x14000811f  retn
```
