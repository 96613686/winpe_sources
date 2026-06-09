# WriteFileBlock

- ea: `0x1001da60`
- end: `0x1001daf3`
- name: `WriteFileBlock`
- size: `147`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1001d440`
- `0x1001d6a0`
- `0x1001d770`
- `0x1001d870`

## callees

- `0x1000ba90`
- `0x1000bd80`
- `0x1001da60`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1001da9f`
- `KERNEL32!GetLastError` at `0x1001da9f`

## pseudocode

```c
int __stdcall WriteFileBlock(int a1)
{
  void *v1; // ecx
  DWORD v2; // edi
  DWORD v3; // ecx
  DWORD v4; // eax
  int result; // eax
  int v6; // eax

  DOSSetFilePosition(*(HANDLE *)(a1 + 20), 0, *(_DWORD *)(a1 + 72));
  if ( *(_DWORD *)(a1 + 60) == 1 && *(_DWORD *)(a1 + 64) == 1 )
    v2 = *(_DWORD *)(a1 + 56) - *(_DWORD *)(a1 + 4);
  else
    v2 = *(_DWORD *)a1;
  v3 = DOSWriteFile(v1, *(HANDLE *)(a1 + 20), *(LPCVOID *)(a1 + 4), v2);
  if ( v3 == 0xFFFF )
  {
    if ( GetLastError() != 112 )
      return -5;
    v3 = 0;
  }
  v4 = v3 + *(_DWORD *)(a1 + 72);
  *(_DWORD *)(a1 + 68) = v4;
  *(_DWORD *)(a1 + 72) = v4;
  if ( v3 != v2 )
    return -12;
  v6 = *(_DWORD *)(a1 + 4);
  *(_DWORD *)(a1 + 8) = v6;
  *(_DWORD *)(a1 + 56) = v6;
  result = 0;
  *(_DWORD *)a1 = 0;
  *(_DWORD *)(a1 + 80) = 0;
  *(_DWORD *)(a1 + 64) = 1;
  return result;
}

```

## disassembly

```asm
0x1001da60  push    esi
0x1001da61  mov     esi, [esp+4+arg_0]
0x1001da65  push    edi
0x1001da66  push    dword ptr [esi+48h]; lDistanceToMove
0x1001da69  push    0; dwMoveMethod
0x1001da6b  push    dword ptr [esi+14h]; hFile
0x1001da6e  call    _DOSSetFilePosition@12; DOSSetFilePosition(x,x,x)
0x1001da73  cmp     dword ptr [esi+3Ch], 1
0x1001da77  jnz     short loc_1001DA87
0x1001da79  cmp     dword ptr [esi+40h], 1
0x1001da7d  jnz     short loc_1001DA87
0x1001da7f  mov     edi, [esi+38h]
0x1001da82  sub     edi, [esi+4]
0x1001da85  jmp     short loc_1001DA89
0x1001da87  mov     edi, [esi]
0x1001da89  push    edi; nNumberOfBytesToWrite
0x1001da8a  push    dword ptr [esi+4]; lpBuffer
0x1001da8d  push    dword ptr [esi+14h]; hFile
0x1001da90  call    _DOSWriteFile@12; DOSWriteFile(x,x,x)
0x1001da95  mov     ecx, eax
0x1001da97  cmp     ecx, 0FFFFh
0x1001da9d  jnz     short loc_1001DAAC
0x1001da9f  call    ds:__imp__GetLastError@0; GetLastError()
0x1001daa5  cmp     eax, 70h ; 'p'
0x1001daa8  jnz     short loc_1001DAC5
0x1001daaa  xor     ecx, ecx
0x1001daac  mov     eax, [esi+48h]
0x1001daaf  add     eax, ecx
0x1001dab1  mov     [esi+44h], eax
0x1001dab4  mov     [esi+48h], eax
0x1001dab7  cmp     ecx, edi
0x1001dab9  jz      short loc_1001DACF
0x1001dabb  pop     edi
0x1001dabc  mov     eax, 0FFFFFFF4h
0x1001dac1  pop     esi
0x1001dac2  retn    4
0x1001dac5  pop     edi
0x1001dac6  mov     eax, 0FFFFFFFBh
0x1001dacb  pop     esi
0x1001dacc  retn    4
0x1001dacf  mov     eax, [esi+4]
0x1001dad2  mov     [esi+8], eax
0x1001dad5  mov     [esi+38h], eax
0x1001dad8  xor     eax, eax
0x1001dada  pop     edi
0x1001dadb  mov     dword ptr [esi], 0
0x1001dae1  mov     dword ptr [esi+50h], 0
0x1001dae8  mov     dword ptr [esi+40h], 1
0x1001daef  pop     esi
0x1001daf0  retn    4
```
