# RtlCopyToUser

- ea: `0x18003802c`
- end: `0x180038089`
- name: `RtlCopyToUser`
- size: `93`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1800085d8`
- `0x180029010`

## callees

- `0x18001cbf6`
- `0x180027bd0`
- `0x18003802c`

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
0x18003802c  mov     [rsp+arg_0], rbx
0x180038031  mov     [rsp+arg_8], rsi
0x180038036  push    rdi
0x180038037  sub     rsp, 20h
0x18003803b  mov     rax, cs:qword_180034560
0x180038042  mov     rbx, r8
0x180038045  mov     rsi, rdx
0x180038048  mov     rdi, rcx
0x18003804b  test    rax, rax
0x18003804e  jz      short loc_180038057
0x180038050  call    rax ; qword_180034560
0x180038052  nop     dword ptr [rax]
0x180038055  jmp     short loc_180038078
0x180038057  test    rbx, rbx
0x18003805a  jz      short loc_180038078
0x18003805c  mov     r8d, 1; Alignment
0x180038062  mov     rdx, rbx; Length
0x180038065  call    ProbeForRead_0
0x18003806a  mov     r8, rbx; Size
0x18003806d  mov     rdx, rsi; Src
0x180038070  mov     rcx, rdi; void *
0x180038073  call    RtlCopyVolatileMemory
0x180038078  mov     rbx, [rsp+28h+arg_0]
0x18003807d  mov     rsi, [rsp+28h+arg_8]
0x180038082  add     rsp, 20h
0x180038086  pop     rdi
0x180038087  retn
```
