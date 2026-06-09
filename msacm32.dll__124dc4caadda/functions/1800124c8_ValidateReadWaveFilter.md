# ValidateReadWaveFilter

- ea: `0x1800124c8`
- end: `0x180012501`
- name: `ValidateReadWaveFilter`
- size: `57`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e70`
- `0x1800119c0`

## callees

- `0x180003f10`
- `0x1800124c8`

## pseudocode

```c
_BOOL8 __fastcall ValidateReadWaveFilter(_DWORD *a1)
{
  return (unsigned int)ValidateReadPointer() && *a1 >= 0x20u && (unsigned int)ValidateReadPointer() != 0;
}

```

## disassembly

```asm
0x1800124c8  push    rbx
0x1800124ca  sub     rsp, 20h
0x1800124ce  mov     edx, 4
0x1800124d3  mov     rbx, rcx
0x1800124d6  call    ValidateReadPointer
0x1800124db  test    eax, eax
0x1800124dd  jz      short loc_1800124F9
0x1800124df  cmp     dword ptr [rbx], 20h ; ' '
0x1800124e2  jb      short loc_1800124F9
0x1800124e4  mov     edx, [rbx]
0x1800124e6  mov     rcx, rbx
0x1800124e9  call    ValidateReadPointer
0x1800124ee  xor     ecx, ecx
0x1800124f0  test    eax, eax
0x1800124f2  setnz   cl
0x1800124f5  mov     eax, ecx
0x1800124f7  jmp     short loc_1800124FB
0x1800124f9  xor     eax, eax
0x1800124fb  add     rsp, 20h
0x1800124ff  pop     rbx
0x180012500  retn
```
