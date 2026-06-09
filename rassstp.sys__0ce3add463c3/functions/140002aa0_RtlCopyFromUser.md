# RtlCopyFromUser

- ea: `0x140002aa0`
- end: `0x140002b00`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x140007010`
- `0x140012290`
- `0x1400133f0`

## callees

- `0x140002aa0`
- `0x140002b06`
- `0x140005e40`

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
0x140002aa0  mov     [rsp+arg_0], rbx
0x140002aa5  mov     [rsp+arg_8], rsi
0x140002aaa  push    rdi
0x140002aab  sub     rsp, 20h
0x140002aaf  mov     rax, cs:__uma_functions
0x140002ab6  mov     rbx, r8
0x140002ab9  mov     rdi, rdx
0x140002abc  mov     rsi, rcx
0x140002abf  test    rax, rax
0x140002ac2  jz      short loc_140002ACB
0x140002ac4  call    rax ; __uma_functions
0x140002ac6  nop     dword ptr [rax]
0x140002ac9  jmp     short loc_140002AEF
0x140002acb  test    rbx, rbx
0x140002ace  jz      short loc_140002AEF
0x140002ad0  mov     r8d, 1; Alignment
0x140002ad6  mov     rdx, rbx; Length
0x140002ad9  mov     rcx, rdi; Address
0x140002adc  call    ProbeForRead_0
0x140002ae1  mov     r8, rbx; Size
0x140002ae4  mov     rdx, rdi; Src
0x140002ae7  mov     rcx, rsi; void *
0x140002aea  call    RtlCopyVolatileMemory
0x140002aef  mov     rbx, [rsp+28h+arg_0]
0x140002af4  mov     rsi, [rsp+28h+arg_8]
0x140002af9  add     rsp, 20h
0x140002afd  pop     rdi
0x140002afe  retn
```
