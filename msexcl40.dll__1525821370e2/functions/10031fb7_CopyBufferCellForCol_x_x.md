# CopyBufferCellForCol(x,x)

- ea: `0x10031fb7`
- end: `0x10031fd3`
- name: `_CopyBufferCellForCol@8`
- size: `28`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x10029aad`
- `0x1002c918`
- `0x1002cee0`
- `0x1002d380`
- `0x1002db68`

## callees

- `0x10031fb7`

## pseudocode

```c
int **__fastcall CopyBufferCellForCol(int **a1, __int16 a2)
{
  int **result; // eax

  for ( result = a1; result; result = (int **)*result )
  {
    if ( *((unsigned __int8 *)result + 4) == a2 )
      break;
  }
  return result;
}

```

## disassembly

```asm
0x10031fb7  mov     eax, ecx
0x10031fb9  movzx   ecx, dx
0x10031fbc  test    eax, eax
0x10031fbe  jnz     short loc_10031FC1
0x10031fc0  retn
0x10031fc1  movsx   edx, cx
0x10031fc4  movzx   ecx, byte ptr [eax+4]
0x10031fc8  cmp     ecx, edx
0x10031fca  jz      short locret_10031FD2
0x10031fcc  mov     eax, [eax]
0x10031fce  test    eax, eax
0x10031fd0  jnz     short loc_10031FC4
0x10031fd2  retn
```
