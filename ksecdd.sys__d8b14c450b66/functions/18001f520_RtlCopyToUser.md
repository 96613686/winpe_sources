# RtlCopyToUser

- ea: `0x18001f520`
- end: `0x18001f57d`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000d01c`
- `0x18000d2f0`
- `0x180012020`

## callees

- `0x180007a4f`
- `0x180010870`
- `0x18001f520`

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
0x18001f520  mov     [rsp+arg_0], rbx
0x18001f525  mov     [rsp+arg_8], rsi
0x18001f52a  push    rdi
0x18001f52b  sub     rsp, 20h
0x18001f52f  mov     rax, cs:qword_18001C4A0
0x18001f536  mov     rbx, r8
0x18001f539  mov     rsi, rdx
0x18001f53c  mov     rdi, rcx
0x18001f53f  test    rax, rax
0x18001f542  jz      short loc_18001F54B
0x18001f544  call    rax ; qword_18001C4A0
0x18001f546  nop     dword ptr [rax]
0x18001f549  jmp     short loc_18001F56C
0x18001f54b  test    rbx, rbx
0x18001f54e  jz      short loc_18001F56C
0x18001f550  mov     r8d, 1; Alignment
0x18001f556  mov     rdx, rbx; Length
0x18001f559  call    ProbeForRead_0
0x18001f55e  mov     r8, rbx; Size
0x18001f561  mov     rdx, rsi; Src
0x18001f564  mov     rcx, rdi; void *
0x18001f567  call    RtlCopyVolatileMemory
0x18001f56c  mov     rbx, [rsp+28h+arg_0]
0x18001f571  mov     rsi, [rsp+28h+arg_8]
0x18001f576  add     rsp, 20h
0x18001f57a  pop     rdi
0x18001f57b  retn
```
