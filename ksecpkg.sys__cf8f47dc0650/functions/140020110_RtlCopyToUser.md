# RtlCopyToUser

- ea: `0x140020110`
- end: `0x14002016d`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14000b07c`
- `0x140011010`

## callees

- `0x140006f46`
- `0x140010190`
- `0x140020110`

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
0x140020110  mov     [rsp+arg_0], rbx
0x140020115  mov     [rsp+arg_8], rsi
0x14002011a  push    rdi
0x14002011b  sub     rsp, 20h
0x14002011f  mov     rax, cs:qword_14001D410
0x140020126  mov     rbx, r8
0x140020129  mov     rsi, rdx
0x14002012c  mov     rdi, rcx
0x14002012f  test    rax, rax
0x140020132  jz      short loc_14002013B
0x140020134  call    rax ; qword_14001D410
0x140020136  nop     dword ptr [rax]
0x140020139  jmp     short loc_14002015C
0x14002013b  test    rbx, rbx
0x14002013e  jz      short loc_14002015C
0x140020140  mov     r8d, 1; Alignment
0x140020146  mov     rdx, rbx; Length
0x140020149  call    ProbeForRead_0
0x14002014e  mov     r8, rbx; Size
0x140020151  mov     rdx, rsi; Src
0x140020154  mov     rcx, rdi; void *
0x140020157  call    RtlCopyVolatileMemory
0x14002015c  mov     rbx, [rsp+28h+arg_0]
0x140020161  mov     rsi, [rsp+28h+arg_8]
0x140020166  add     rsp, 20h
0x14002016a  pop     rdi
0x14002016b  retn
```
