# RtlCopyToUser

- ea: `0x140011bfc`
- end: `0x140011c59`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `void *__fastcall(void *, void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140007020`
- `0x140019220`
- `0x140019720`
- `0x140019aa4`
- `0x140019f18`

## callees

- `0x140003051`
- `0x1400064b0`
- `0x140011bfc`

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
0x140011bfc  mov     [rsp+arg_0], rbx
0x140011c01  mov     [rsp+arg_8], rsi
0x140011c06  push    rdi
0x140011c07  sub     rsp, 20h
0x140011c0b  mov     rax, cs:qword_14000F570
0x140011c12  mov     rbx, r8
0x140011c15  mov     rsi, rdx
0x140011c18  mov     rdi, rcx
0x140011c1b  test    rax, rax
0x140011c1e  jz      short loc_140011C27
0x140011c20  call    rax ; qword_14000F570
0x140011c22  nop     dword ptr [rax]
0x140011c25  jmp     short loc_140011C48
0x140011c27  test    rbx, rbx
0x140011c2a  jz      short loc_140011C48
0x140011c2c  mov     r8d, 1; Alignment
0x140011c32  mov     rdx, rbx; Length
0x140011c35  call    ProbeForRead_0
0x140011c3a  mov     r8, rbx; Size
0x140011c3d  mov     rdx, rsi; Src
0x140011c40  mov     rcx, rdi; void *
0x140011c43  call    RtlCopyVolatileMemory
0x140011c48  mov     rbx, [rsp+28h+arg_0]
0x140011c4d  mov     rsi, [rsp+28h+arg_8]
0x140011c52  add     rsp, 20h
0x140011c56  pop     rdi
0x140011c57  retn
```
