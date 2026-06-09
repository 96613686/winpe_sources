# IsWriteRangeInBuffer(x,x,x,x,x)

- ea: `0x10004100`
- end: `0x1000413c`
- name: `_IsWriteRangeInBuffer@20`
- size: `60`
- prototype: ``
- caller_count: `15`
- callee_count: `1`
- tags: ``

## callers

- `0x10004142`
- `0x10006e20`
- `0x10007170`
- `0x100072f0`
- `0x1000766a`
- `0x100076ec`
- `0x10007cf0`
- `0x10007ff0`
- `0x10008170`
- `0x100084b0`
- `0x10008720`
- `0x10008860`
- `0x10008b00`
- `0x10008e50`
- `0x10009010`

## callees

- `0x10004100`

## pseudocode

```c
BOOL __fastcall IsWriteRangeInBuffer(unsigned int a1, int a2, int a3, int a4, int a5)
{
  unsigned int v7; // edx
  unsigned int v8; // ecx
  BOOL result; // eax

  result = 0;
  if ( a3 )
  {
    v7 = a2 + a4;
    v8 = a2 + a5;
    if ( a1 <= a2 + a4 && v7 < v8 && v8 <= a1 + a3 - 1 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x10004100  mov     edi, edi
0x10004102  push    ebp
0x10004103  mov     ebp, esp
0x10004105  push    ebx
0x10004106  push    esi
0x10004107  mov     esi, [ebp+arg_0]
0x1000410a  mov     ebx, edx
0x1000410c  push    edi
0x1000410d  mov     edi, ecx
0x1000410f  test    esi, esi
0x10004111  jz      short loc_10004133
0x10004113  mov     edx, [ebp+arg_4]
0x10004116  mov     ecx, [ebp+arg_8]
0x10004119  add     edx, ebx
0x1000411b  add     ecx, ebx
0x1000411d  cmp     edi, edx
0x1000411f  ja      short loc_10004133
0x10004121  cmp     edx, ecx
0x10004123  jnb     short loc_10004133
0x10004125  lea     eax, [esi-1]
0x10004128  add     eax, edi
0x1000412a  cmp     ecx, eax
0x1000412c  ja      short loc_10004133
0x1000412e  xor     eax, eax
0x10004130  inc     eax
0x10004131  jmp     short loc_10004135
0x10004133  xor     eax, eax
0x10004135  pop     edi
0x10004136  pop     esi
0x10004137  pop     ebx
0x10004138  pop     ebp
0x10004139  retn    0Ch
```
