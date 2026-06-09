# ValidateReadPointer

- ea: `0x180003f10`
- end: `0x180003f2e`
- name: `ValidateReadPointer`
- size: `30`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034e0`
- `0x180003b40`
- `0x180005990`
- `0x1800124c8`

## callees

- `0x180003f10`

## pseudocode

```c
__int64 ValidateReadPointer()
{
  return 1;
}

```

## disassembly

```asm
0x180003f10  movzx   eax, byte ptr [rcx]
0x180003f13  mov     [rsp+arg_10], al
0x180003f17  lea     eax, [rdx-1]
0x180003f1a  movzx   eax, byte ptr [rax+rcx]
0x180003f1e  mov     [rsp+arg_10], al
0x180003f22  jmp     short loc_180003F28
0x180003f24  xor     eax, eax
0x180003f26  jmp     short locret_180003F2D
0x180003f28  mov     eax, 1
0x180003f2d  retn
```
