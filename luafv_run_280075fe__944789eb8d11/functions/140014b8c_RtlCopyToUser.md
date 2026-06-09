# RtlCopyToUser

- ea: `0x140014b8c`
- end: `0x140014be9`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140007010`
- `0x1400240a0`
- `0x140024664`

## callees

- `0x1400022b6`
- `0x140005f60`
- `0x140014b8c`

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
0x140014b8c  mov     [rsp+arg_0], rbx
0x140014b91  mov     [rsp+arg_8], rsi
0x140014b96  push    rdi
0x140014b97  sub     rsp, 20h
0x140014b9b  mov     rax, cs:qword_1400125D0
0x140014ba2  mov     rbx, r8
0x140014ba5  mov     rsi, rdx
0x140014ba8  mov     rdi, rcx
0x140014bab  test    rax, rax
0x140014bae  jz      short loc_140014BB7
0x140014bb0  call    rax ; qword_1400125D0
0x140014bb2  nop     dword ptr [rax]
0x140014bb5  jmp     short loc_140014BD8
0x140014bb7  test    rbx, rbx
0x140014bba  jz      short loc_140014BD8
0x140014bbc  mov     r8d, 1; Alignment
0x140014bc2  mov     rdx, rbx; Length
0x140014bc5  call    ProbeForRead_0
0x140014bca  mov     r8, rbx; Size
0x140014bcd  mov     rdx, rsi; Src
0x140014bd0  mov     rcx, rdi; void *
0x140014bd3  call    RtlCopyVolatileMemory
0x140014bd8  mov     rbx, [rsp+28h+arg_0]
0x140014bdd  mov     rsi, [rsp+28h+arg_8]
0x140014be2  add     rsp, 20h
0x140014be6  pop     rdi
0x140014be7  retn
```
