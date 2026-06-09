# GetResString

- ea: `0x14000cd10`
- end: `0x14000cd3f`
- name: `GetResString`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140002f30`
- `0x140006394`
- `0x140008788`
- `0x14000998c`
- `0x14000dc24`

## callees

- `0x14000cd48`

## pseudocode

```c
__int64 *__fastcall GetResString(__int64 a1)
{
  return GetResString2FromModule(a1, a1, ++dword_140014210 % 0xAu + 4);
}

```

## disassembly

```asm
0x14000cd10  mov     r8d, cs:dword_140014210
0x14000cd17  mov     eax, 0CCCCCCCDh
0x14000cd1c  inc     r8d
0x14000cd1f  mul     r8d
0x14000cd22  mov     cs:dword_140014210, r8d
0x14000cd29  shr     edx, 3
0x14000cd2c  lea     eax, [rdx+rdx*4]
0x14000cd2f  mov     edx, ecx
0x14000cd31  add     eax, eax
0x14000cd33  sub     r8d, eax
0x14000cd36  add     r8d, 4
0x14000cd3a  jmp     GetResString2FromModule
```
