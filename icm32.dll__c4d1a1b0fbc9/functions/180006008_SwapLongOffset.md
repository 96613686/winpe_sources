# SwapLongOffset

- ea: `0x180006008`
- end: `0x180006045`
- name: `SwapLongOffset`
- size: `61`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `13`
- callee_count: `1`
- tags: ``

## callers

- `0x1800042fc`
- `0x18000464c`
- `0x180005c70`
- `0x180007418`
- `0x18001bb30`
- `0x18001c4a0`
- `0x18001de14`
- `0x18001ef48`
- `0x18001f14c`
- `0x18001f23c`
- `0x180020828`
- `0x18002167c`
- `0x18003cb08`

## callees

- `0x180006008`

## pseudocode

```c
__int64 __fastcall SwapLongOffset(__int64 a1, unsigned int a2, unsigned int a3)
{
  unsigned __int64 v3; // r9
  unsigned __int8 *i; // r8
  __int64 result; // rax

  v3 = a1 + a3;
  for ( i = (unsigned __int8 *)(a1 + a2); (unsigned __int64)i < v3; i += 4 )
  {
    result = i[3];
    *(_DWORD *)i = result | ((i[2] | ((i[1] | (*i << 8)) << 8)) << 8);
  }
  return result;
}

```

## disassembly

```asm
0x180006008  mov     r9d, r8d
0x18000600b  add     r9, rcx
0x18000600e  mov     r8d, edx
0x180006011  add     r8, rcx
0x180006014  jmp     short loc_18000603F
0x180006016  movzx   eax, byte ptr [r8+1]
0x18000601b  movzx   ecx, byte ptr [r8]
0x18000601f  shl     ecx, 8
0x180006022  or      ecx, eax
0x180006024  movzx   eax, byte ptr [r8+2]
0x180006029  shl     ecx, 8
0x18000602c  or      ecx, eax
0x18000602e  movzx   eax, byte ptr [r8+3]
0x180006033  shl     ecx, 8
0x180006036  or      ecx, eax
0x180006038  mov     [r8], ecx
0x18000603b  add     r8, 4
0x18000603f  cmp     r8, r9
0x180006042  jb      short loc_180006016
0x180006044  retn
```
