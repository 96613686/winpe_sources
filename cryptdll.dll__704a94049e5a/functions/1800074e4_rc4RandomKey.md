# rc4RandomKey

- ea: `0x1800074e4`
- end: `0x180007505`
- name: `rc4RandomKey`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007370`
- `0x180007470`

## callees

- `0x180005800`

## pseudocode

```c
__int64 rc4RandomKey()
{
  return (unsigned __int8)CDGenerateRandomBits() == 0 ? 0xC00000E5 : 0;
}

```

## disassembly

```asm
0x1800074e4  sub     rsp, 28h
0x1800074e8  mov     rax, rdx
0x1800074eb  mov     edx, ecx
0x1800074ed  mov     rcx, rax
0x1800074f0  call    CDGenerateRandomBits
0x1800074f5  neg     al
0x1800074f7  sbb     eax, eax
0x1800074f9  not     eax
0x1800074fb  and     eax, 0C00000E5h
0x180007500  add     rsp, 28h
0x180007504  retn
```
