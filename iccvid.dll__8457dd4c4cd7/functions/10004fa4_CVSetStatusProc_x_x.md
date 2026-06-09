# CVSetStatusProc(x,x)

- ea: `0x10004fa4`
- end: `0x10004fc5`
- name: `_CVSetStatusProc@8`
- size: `33`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x10004695`
- `0x100093a0`

## callees

- `0x10004fa4`

## pseudocode

```c
int __fastcall CVSetStatusProc(int a1, int a2)
{
  int v2; // eax

  v2 = 0;
  if ( a2 && *(_DWORD *)(a2 + 8) )
  {
    *(_DWORD *)(a1 + 1040) = *(_DWORD *)(a2 + 4);
    v2 = *(_DWORD *)(a2 + 8);
  }
  *(_DWORD *)(a1 + 1044) = v2;
  return 1;
}

```

## disassembly

```asm
0x10004fa4  xor     eax, eax
0x10004fa6  test    edx, edx
0x10004fa8  jz      short loc_10004FBB
0x10004faa  cmp     [edx+8], eax
0x10004fad  jz      short loc_10004FBB
0x10004faf  mov     eax, [edx+4]
0x10004fb2  mov     [ecx+410h], eax
0x10004fb8  mov     eax, [edx+8]
0x10004fbb  mov     [ecx+414h], eax
0x10004fc1  xor     eax, eax
0x10004fc3  inc     eax
0x10004fc4  retn
```
