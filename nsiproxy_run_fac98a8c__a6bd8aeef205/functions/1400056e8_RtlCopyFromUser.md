# RtlCopyFromUser

- ea: `0x1400056e8`
- end: `0x140005748`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `14`
- callee_count: `3`
- tags: ``

## callers

- `0x140001010`
- `0x140001880`
- `0x140002280`
- `0x140002850`
- `0x140002eb0`
- `0x1400033c0`
- `0x140003700`
- `0x140003af0`
- `0x140003e20`
- `0x1400043d0`
- `0x140004ca0`
- `0x140005c3c`
- `0x1400060e8`
- `0x140007010`

## callees

- `0x1400056cf`
- `0x1400056e8`
- `0x140006560`

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
0x1400056e8  mov     [rsp+arg_0], rbx
0x1400056ed  mov     [rsp+arg_8], rsi
0x1400056f2  push    rdi
0x1400056f3  sub     rsp, 20h
0x1400056f7  mov     rax, cs:__uma_functions
0x1400056fe  mov     rbx, r8
0x140005701  mov     rdi, rdx
0x140005704  mov     rsi, rcx
0x140005707  test    rax, rax
0x14000570a  jz      short loc_140005713
0x14000570c  call    rax ; __uma_functions
0x14000570e  nop     dword ptr [rax]
0x140005711  jmp     short loc_140005737
0x140005713  test    rbx, rbx
0x140005716  jz      short loc_140005737
0x140005718  mov     r8d, 1; Alignment
0x14000571e  mov     rdx, rbx; Length
0x140005721  mov     rcx, rdi; Address
0x140005724  call    ProbeForRead_0
0x140005729  mov     r8, rbx; Size
0x14000572c  mov     rdx, rdi; Src
0x14000572f  mov     rcx, rsi; void *
0x140005732  call    RtlCopyVolatileMemory
0x140005737  mov     rbx, [rsp+28h+arg_0]
0x14000573c  mov     rsi, [rsp+28h+arg_8]
0x140005741  add     rsp, 20h
0x140005745  pop     rdi
0x140005746  retn
```
