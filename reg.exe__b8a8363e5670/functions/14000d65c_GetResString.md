# GetResString

- ea: `0x14000d65c`
- end: `0x14000d68b`
- name: `GetResString`
- size: `47`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x140003068`
- `0x14000672c`
- `0x140008cbc`
- `0x140009f80`
- `0x14000e798`

## callees

- `0x14000d694`

## pseudocode

```c
__int64 *__fastcall GetResString(__int64 a1)
{
  return GetResString2FromModule(a1, a1, ++dword_140015210 % 0xAu + 4);
}

```

## disassembly

```asm
0x14000d65c  mov     r8d, cs:dword_140015210
0x14000d663  mov     eax, 0CCCCCCCDh
0x14000d668  inc     r8d
0x14000d66b  mul     r8d
0x14000d66e  mov     cs:dword_140015210, r8d
0x14000d675  shr     edx, 3
0x14000d678  lea     eax, [rdx+rdx*4]
0x14000d67b  mov     edx, ecx
0x14000d67d  add     eax, eax
0x14000d67f  sub     r8d, eax
0x14000d682  add     r8d, 4
0x14000d686  jmp     GetResString2FromModule
```
