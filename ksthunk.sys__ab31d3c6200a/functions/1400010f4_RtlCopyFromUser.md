# RtlCopyFromUser

- ea: `0x1400010f4`
- end: `0x140001154`
- name: `RtlCopyFromUser`
- size: `96`
- prototype: `__int64 (*__fastcall(void *, void *Src, size_t Size))(void)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001ba0`
- `0x140003728`
- `0x140005010`
- `0x14000bfc4`

## callees

- `0x140001044`
- `0x1400010f4`
- `0x140004140`

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
0x1400010f4  mov     [rsp+arg_0], rbx
0x1400010f9  mov     [rsp+arg_8], rsi
0x1400010fe  push    rdi
0x1400010ff  sub     rsp, 20h
0x140001103  mov     rax, cs:__uma_functions
0x14000110a  mov     rbx, r8
0x14000110d  mov     rdi, rdx
0x140001110  mov     rsi, rcx
0x140001113  test    rax, rax
0x140001116  jz      short loc_14000111F
0x140001118  call    rax ; __uma_functions
0x14000111a  nop     dword ptr [rax]
0x14000111d  jmp     short loc_140001143
0x14000111f  test    rbx, rbx
0x140001122  jz      short loc_140001143
0x140001124  mov     r8d, 1; Alignment
0x14000112a  mov     rdx, rbx; Length
0x14000112d  mov     rcx, rdi; Address
0x140001130  call    ProbeForRead_0
0x140001135  mov     r8, rbx; Size
0x140001138  mov     rdx, rdi; Src
0x14000113b  mov     rcx, rsi; void *
0x14000113e  call    RtlCopyVolatileMemory
0x140001143  mov     rbx, [rsp+28h+arg_0]
0x140001148  mov     rsi, [rsp+28h+arg_8]
0x14000114d  add     rsp, 20h
0x140001151  pop     rdi
0x140001152  retn
```
