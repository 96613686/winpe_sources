# RtlCopyToUser

- ea: `0x14000e008`
- end: `0x14000e065`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140007020`
- `0x140011b00`

## callees

- `0x140002b06`
- `0x140005e40`
- `0x14000e008`

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
0x14000e008  mov     [rsp+arg_0], rbx
0x14000e00d  mov     [rsp+arg_8], rsi
0x14000e012  push    rdi
0x14000e013  sub     rsp, 20h
0x14000e017  mov     rax, cs:qword_14000C420
0x14000e01e  mov     rbx, r8
0x14000e021  mov     rsi, rdx
0x14000e024  mov     rdi, rcx
0x14000e027  test    rax, rax
0x14000e02a  jz      short loc_14000E033
0x14000e02c  call    rax ; qword_14000C420
0x14000e02e  nop     dword ptr [rax]
0x14000e031  jmp     short loc_14000E054
0x14000e033  test    rbx, rbx
0x14000e036  jz      short loc_14000E054
0x14000e038  mov     r8d, 1; Alignment
0x14000e03e  mov     rdx, rbx; Length
0x14000e041  call    ProbeForRead_0
0x14000e046  mov     r8, rbx; Size
0x14000e049  mov     rdx, rsi; Src
0x14000e04c  mov     rcx, rdi; void *
0x14000e04f  call    RtlCopyVolatileMemory
0x14000e054  mov     rbx, [rsp+28h+arg_0]
0x14000e059  mov     rsi, [rsp+28h+arg_8]
0x14000e05e  add     rsp, 20h
0x14000e062  pop     rdi
0x14000e063  retn
```
