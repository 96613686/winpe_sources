# RtlCopyToUser

- ea: `0x14000a008`
- end: `0x14000a065`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140002dc8`
- `0x140004020`

## callees

- `0x140001044`
- `0x1400036c0`
- `0x14000a008`

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
0x14000a008  mov     [rsp+arg_0], rbx
0x14000a00d  mov     [rsp+arg_8], rsi
0x14000a012  push    rdi
0x14000a013  sub     rsp, 20h
0x14000a017  mov     rax, cs:qword_140009210
0x14000a01e  mov     rbx, r8
0x14000a021  mov     rsi, rdx
0x14000a024  mov     rdi, rcx
0x14000a027  test    rax, rax
0x14000a02a  jz      short loc_14000A033
0x14000a02c  call    rax ; qword_140009210
0x14000a02e  nop     dword ptr [rax]
0x14000a031  jmp     short loc_14000A054
0x14000a033  test    rbx, rbx
0x14000a036  jz      short loc_14000A054
0x14000a038  mov     r8d, 1; Alignment
0x14000a03e  mov     rdx, rbx; Length
0x14000a041  call    ProbeForRead_0
0x14000a046  mov     r8, rbx; Size
0x14000a049  mov     rdx, rsi; Src
0x14000a04c  mov     rcx, rdi; void *
0x14000a04f  call    RtlCopyVolatileMemory
0x14000a054  mov     rbx, [rsp+28h+arg_0]
0x14000a059  mov     rsi, [rsp+28h+arg_8]
0x14000a05e  add     rsp, 20h
0x14000a062  pop     rdi
0x14000a063  retn
```
