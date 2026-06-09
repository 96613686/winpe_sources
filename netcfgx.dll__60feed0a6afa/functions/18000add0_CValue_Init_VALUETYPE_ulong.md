# CValue::Init(VALUETYPE,ulong)

- ea: `0x18000add0`
- end: `0x18000ae07`
- name: `?Init@CValue@@QEAAXW4VALUETYPE@@K@Z`
- size: `55`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180008f28`
- `0x18000949c`
- `0x18000994c`
- `0x18000b4c4`

## callees

- `0x18000ab50`
- `0x18000add0`

## pseudocode

```c
__int64 __fastcall CValue::Init(__int64 a1, int a2, int a3)
{
  __int64 result; // rax

  *(_DWORD *)(a1 + 4) = a2;
  *(_DWORD *)(a1 + 24) = 0;
  result = (unsigned int)(a2 - 5);
  *(_DWORD *)a1 = 1;
  *(_QWORD *)(a1 + 16) = 1;
  if ( (unsigned int)result <= 2 )
  {
    *(_DWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 32) = 0;
    return CValue::FromString((CValue *)a1, 0);
  }
  else
  {
    *(_DWORD *)(a1 + 8) = 1;
    *(_DWORD *)(a1 + 32) = a3;
  }
  return result;
}

```

## disassembly

```asm
0x18000add0  xor     r9d, r9d
0x18000add3  mov     [rcx+4], edx
0x18000add6  mov     r10d, 1
0x18000addc  mov     [rcx+18h], r9d
0x18000ade0  lea     eax, [rdx-5]
0x18000ade3  mov     [rcx], r10d
0x18000ade6  mov     [rcx+10h], r10
0x18000adea  cmp     eax, 2
0x18000aded  jbe     short loc_18000ADF8
0x18000adef  mov     [rcx+8], r10d
0x18000adf3  mov     [rcx+20h], r8d
0x18000adf7  retn
0x18000adf8  xor     edx, edx; unsigned __int16 *
0x18000adfa  mov     [rcx+8], r9d
0x18000adfe  mov     [rcx+20h], r9
0x18000ae02  jmp     ?FromString@CValue@@QEAAHQEBG@Z; CValue::FromString(ushort const * const)
```
