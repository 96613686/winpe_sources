# List_Create

- ea: `0x180001344`
- end: `0x180001376`
- name: `List_Create`
- size: `50`
- prototype: `__int64 __fastcall(int)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x1800022c0`
- `0x180002eac`
- `0x1800042b0`

## callees

- `0x180001344`

## pseudocode

```c
__int64 __fastcall List_Create(int a1)
{
  unsigned int v1; // edx
  __int64 result; // rax

  v1 = 0;
  while ( *((_DWORD *)&arrayOfLists + 4 * v1) )
  {
    if ( (int)++v1 >= 500 )
      return 0xFFFFFFFFLL;
  }
  result = v1;
  *((_DWORD *)&arrayOfLists + 4 * v1) = a1;
  return result;
}

```

## disassembly

```asm
0x180001344  mov     r8d, ecx
0x180001347  lea     r9, arrayOfLists
0x18000134e  xor     edx, edx
0x180001350  mov     eax, edx
0x180001352  add     rax, rax
0x180001355  cmp     dword ptr [r9+rax*8], 0
0x18000135a  jz      short loc_18000136A
0x18000135c  inc     edx
0x18000135e  cmp     edx, 1F4h
0x180001364  jl      short loc_180001350
0x180001366  or      eax, 0FFFFFFFFh
0x180001369  retn
0x18000136a  mov     ecx, edx
0x18000136c  mov     eax, edx
0x18000136e  add     rcx, rcx
0x180001371  mov     [r9+rcx*8], r8d
0x180001375  retn
```
