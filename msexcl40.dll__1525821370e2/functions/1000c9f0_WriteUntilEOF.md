# WriteUntilEOF

- ea: `0x1000c9f0`
- end: `0x1000ca7f`
- name: `WriteUntilEOF`
- size: `143`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1000ca90`

## callees

- `0x1000c9f0`
- `0x1002611f`

## pseudocode

```c
int __fastcall WriteUntilEOF(int a1, int a2, int **a3)
{
  int *v4; // esi
  _WORD *v5; // edi
  bool v6; // zf
  int v7; // eax
  int result; // eax

  v4 = *a3;
  while ( 1 )
  {
    v5 = v4 + 1;
    v6 = *(_DWORD *)(a2 + 24) == 1;
    *(_DWORD *)(a2 + 20) += *((__int16 *)v4 + 3) + 4;
    if ( v6 )
    {
      v7 = BFWriteFile(*(_DWORD *)(a1 + 20), (char *)v4 + 4, 4u);
      if ( v7 || (v7 = BFWriteFile(*(_DWORD *)(a1 + 20), (char *)v4 + 8, *((__int16 *)v4 + 3))) != 0 )
      {
        result = dword_10001970[abs32(v7)];
        if ( result == -10 )
          result = -10;
        if ( result )
          break;
      }
    }
    v4 = (int *)*v4;
    if ( *v5 == 10 )
    {
      *a3 = v4;
      return v4 == 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1000c9f0  mov     edi, edi
0x1000c9f2  push    ebp
0x1000c9f3  mov     ebp, esp
0x1000c9f5  sub     esp, 8
0x1000c9f8  push    ebx
0x1000c9f9  push    esi
0x1000c9fa  mov     esi, [ebp+arg_0]
0x1000c9fd  mov     ebx, edx
0x1000c9ff  push    edi
0x1000ca00  mov     [ebp+var_4], ecx
0x1000ca03  mov     esi, [esi]
0x1000ca05  mov     eax, [ebx+14h]
0x1000ca08  lea     edi, [esi+4]
0x1000ca0b  movsx   ecx, word ptr [edi+2]
0x1000ca0f  add     eax, 4
0x1000ca12  add     eax, ecx
0x1000ca14  cmp     dword ptr [ebx+18h], 1
0x1000ca18  mov     [ebx+14h], eax
0x1000ca1b  jnz     short loc_1000CA62
0x1000ca1d  mov     eax, [ebp+var_4]
0x1000ca20  mov     edx, edi
0x1000ca22  push    4
0x1000ca24  mov     ecx, [eax+14h]
0x1000ca27  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000ca2c  test    eax, eax
0x1000ca2e  jnz     short loc_1000CA47
0x1000ca30  movsx   eax, word ptr [edi+2]
0x1000ca34  lea     edx, [esi+8]
0x1000ca37  push    eax
0x1000ca38  mov     eax, [ebp+var_4]
0x1000ca3b  mov     ecx, [eax+14h]
0x1000ca3e  call    _BFWriteFile@12; BFWriteFile(x,x,x)
0x1000ca43  test    eax, eax
0x1000ca45  jz      short loc_1000CA62
0x1000ca47  cdq
0x1000ca48  mov     ecx, 0FFFFFFF6h
0x1000ca4d  xor     eax, edx
0x1000ca4f  sub     eax, edx
0x1000ca51  mov     eax, ds:dword_10001970[eax*4]
0x1000ca58  cmp     eax, 0FFFFFFF6h
0x1000ca5b  cmovz   eax, ecx
0x1000ca5e  test    eax, eax
0x1000ca60  jnz     short loc_1000CA76
0x1000ca62  cmp     word ptr [edi], 0Ah
0x1000ca66  mov     esi, [esi]
0x1000ca68  jnz     short loc_1000CA05
0x1000ca6a  mov     eax, [ebp+arg_0]
0x1000ca6d  mov     [eax], esi
0x1000ca6f  xor     eax, eax
0x1000ca71  test    esi, esi
0x1000ca73  setz    al
0x1000ca76  pop     edi
0x1000ca77  pop     esi
0x1000ca78  pop     ebx
0x1000ca79  mov     esp, ebp
0x1000ca7b  pop     ebp
0x1000ca7c  retn    4
```
