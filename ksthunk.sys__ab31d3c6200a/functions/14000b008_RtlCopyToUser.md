# RtlCopyToUser

- ea: `0x14000b008`
- end: `0x14000b065`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `void *__fastcall(void *, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003728`
- `0x140005020`

## callees

- `0x140001044`
- `0x140004140`
- `0x14000b008`

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
0x14000b008  mov     [rsp+arg_0], rbx
0x14000b00d  mov     [rsp+arg_8], rsi
0x14000b012  push    rdi
0x14000b013  sub     rsp, 20h
0x14000b017  mov     rax, cs:qword_14000A210
0x14000b01e  mov     rbx, r8
0x14000b021  mov     rsi, rdx
0x14000b024  mov     rdi, rcx
0x14000b027  test    rax, rax
0x14000b02a  jz      short loc_14000B033
0x14000b02c  call    rax ; qword_14000A210
0x14000b02e  nop     dword ptr [rax]
0x14000b031  jmp     short loc_14000B054
0x14000b033  test    rbx, rbx
0x14000b036  jz      short loc_14000B054
0x14000b038  mov     r8d, 1; Alignment
0x14000b03e  mov     rdx, rbx; Length
0x14000b041  call    ProbeForRead_0
0x14000b046  mov     r8, rbx; Size
0x14000b049  mov     rdx, rsi; Src
0x14000b04c  mov     rcx, rdi; void *
0x14000b04f  call    RtlCopyVolatileMemory
0x14000b054  mov     rbx, [rsp+28h+arg_0]
0x14000b059  mov     rsi, [rsp+28h+arg_8]
0x14000b05e  add     rsp, 20h
0x14000b062  pop     rdi
0x14000b063  retn
```
