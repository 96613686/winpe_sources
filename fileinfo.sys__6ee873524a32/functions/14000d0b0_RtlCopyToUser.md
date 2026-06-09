# RtlCopyToUser

- ea: `0x14000d0b0`
- end: `0x14000d10d`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140005020`
- `0x14000d8cc`
- `0x140016fa0`
- `0x140017284`

## callees

- `0x140003046`
- `0x140003950`
- `0x14000d0b0`

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
0x14000d0b0  mov     [rsp+arg_0], rbx
0x14000d0b5  mov     [rsp+arg_8], rsi
0x14000d0ba  push    rdi
0x14000d0bb  sub     rsp, 20h
0x14000d0bf  mov     rax, cs:qword_14000B4A0
0x14000d0c6  mov     rbx, r8
0x14000d0c9  mov     rsi, rdx
0x14000d0cc  mov     rdi, rcx
0x14000d0cf  test    rax, rax
0x14000d0d2  jz      short loc_14000D0DB
0x14000d0d4  call    rax ; qword_14000B4A0
0x14000d0d6  nop     dword ptr [rax]
0x14000d0d9  jmp     short loc_14000D0FC
0x14000d0db  test    rbx, rbx
0x14000d0de  jz      short loc_14000D0FC
0x14000d0e0  mov     r8d, 1; Alignment
0x14000d0e6  mov     rdx, rbx; Length
0x14000d0e9  call    ProbeForRead_0
0x14000d0ee  mov     r8, rbx; Size
0x14000d0f1  mov     rdx, rsi; Src
0x14000d0f4  mov     rcx, rdi; void *
0x14000d0f7  call    RtlCopyVolatileMemory
0x14000d0fc  mov     rbx, [rsp+28h+arg_0]
0x14000d101  mov     rsi, [rsp+28h+arg_8]
0x14000d106  add     rsp, 20h
0x14000d10a  pop     rdi
0x14000d10b  retn
```
