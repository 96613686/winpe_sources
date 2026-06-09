# RtlCopyFromUser

- ea: `0x140003064`
- end: `0x1400030c4`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140007010`
- `0x14001a29c`
- `0x14001a41c`
- `0x14002a2ec`
- `0x14002aebc`

## callees

- `0x140003051`
- `0x140003064`
- `0x1400064b0`

## pseudocode

```c
__int64 (*__fastcall RtlCopyFromUser(void *a1, void *Src, size_t Size))(void)
{
  __int64 (*result)(void); // rax

  result = _uma_functions;
  if ( _uma_functions )
    return (__int64 (*)(void))_uma_functions();
  if ( Size )
  {
    ProbeForRead_0(Src, Size, 1u);
    return (__int64 (*)(void))RtlCopyVolatileMemory(a1, Src, Size);
  }
  return result;
}

```

## disassembly

```asm
0x140003064  mov     [rsp+arg_0], rbx
0x140003069  mov     [rsp+arg_8], rsi
0x14000306e  push    rdi
0x14000306f  sub     rsp, 20h
0x140003073  mov     rax, cs:__uma_functions
0x14000307a  mov     rbx, r8
0x14000307d  mov     rdi, rdx
0x140003080  mov     rsi, rcx
0x140003083  test    rax, rax
0x140003086  jz      short loc_14000308F
0x140003088  call    rax ; __uma_functions
0x14000308a  nop     dword ptr [rax]
0x14000308d  jmp     short loc_1400030B3
0x14000308f  test    rbx, rbx
0x140003092  jz      short loc_1400030B3
0x140003094  mov     r8d, 1; Alignment
0x14000309a  mov     rdx, rbx; Length
0x14000309d  mov     rcx, rdi; Address
0x1400030a0  call    ProbeForRead_0
0x1400030a5  mov     r8, rbx; Size
0x1400030a8  mov     rdx, rdi; Src
0x1400030ab  mov     rcx, rsi; void *
0x1400030ae  call    RtlCopyVolatileMemory
0x1400030b3  mov     rbx, [rsp+28h+arg_0]
0x1400030b8  mov     rsi, [rsp+28h+arg_8]
0x1400030bd  add     rsp, 20h
0x1400030c1  pop     rdi
0x1400030c2  retn
```
