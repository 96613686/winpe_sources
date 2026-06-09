# RtlCopyToUser

- ea: `0x14000d08c`
- end: `0x14000d0e9`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `6`
- callee_count: `3`
- tags: ``

## callers

- `0x140001010`
- `0x140002280`
- `0x140002850`
- `0x140002eb0`
- `0x140005c3c`
- `0x140007020`

## callees

- `0x1400056cf`
- `0x140006560`
- `0x14000d08c`

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
0x14000d08c  mov     [rsp+arg_0], rbx
0x14000d091  mov     [rsp+arg_8], rsi
0x14000d096  push    rdi
0x14000d097  sub     rsp, 20h
0x14000d09b  mov     rax, cs:qword_14000C2A0
0x14000d0a2  mov     rbx, r8
0x14000d0a5  mov     rsi, rdx
0x14000d0a8  mov     rdi, rcx
0x14000d0ab  test    rax, rax
0x14000d0ae  jz      short loc_14000D0B7
0x14000d0b0  call    rax ; qword_14000C2A0
0x14000d0b2  nop     dword ptr [rax]
0x14000d0b5  jmp     short loc_14000D0D8
0x14000d0b7  test    rbx, rbx
0x14000d0ba  jz      short loc_14000D0D8
0x14000d0bc  mov     r8d, 1; Alignment
0x14000d0c2  mov     rdx, rbx; Length
0x14000d0c5  call    ProbeForRead_0
0x14000d0ca  mov     r8, rbx; Size
0x14000d0cd  mov     rdx, rsi; Src
0x14000d0d0  mov     rcx, rdi; void *
0x14000d0d3  call    RtlCopyVolatileMemory
0x14000d0d8  mov     rbx, [rsp+28h+arg_0]
0x14000d0dd  mov     rsi, [rsp+28h+arg_8]
0x14000d0e2  add     rsp, 20h
0x14000d0e6  pop     rdi
0x14000d0e7  retn
```
