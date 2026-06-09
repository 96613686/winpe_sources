# ISAMDBDeleteColumn(x,x)

- ea: `0x1002ae15`
- end: `0x1002ae6a`
- name: `_ISAMDBDeleteColumn@8`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1002e8f0`

## callees

- `0x10025775`
- `0x10025ab7`
- `0x1002ae15`

## pseudocode

```c
int __fastcall ISAMDBDeleteColumn(int a1, int a2)
{
  int v3; // eax
  _DWORD *v4; // ebx
  _DWORD *i; // esi
  int v6; // eax
  _DWORD *v7; // ecx

  v3 = a2;
  v4 = 0;
  for ( i = *(_DWORD **)(a1 + 40); ; i = (_DWORD *)*i )
  {
    if ( !i )
      return -1507;
    v6 = DBlstrcmpi((int)i + 42, v3);
    v7 = (_DWORD *)*i;
    if ( !v6 )
      break;
    v3 = a2;
    v4 = i;
  }
  if ( v4 )
    *v4 = v7;
  else
    *(_DWORD *)(a1 + 40) = v7;
  --*(_DWORD *)(a1 + 36);
  MemFree(i);
  return 0;
}

```

## disassembly

```asm
0x1002ae15  mov     edi, edi
0x1002ae17  push    ebp
0x1002ae18  mov     ebp, esp
0x1002ae1a  push    ecx
0x1002ae1b  push    ebx
0x1002ae1c  push    esi
0x1002ae1d  push    edi
0x1002ae1e  mov     edi, ecx
0x1002ae20  mov     eax, edx
0x1002ae22  mov     [ebp+var_4], eax
0x1002ae25  xor     ebx, ebx
0x1002ae27  mov     esi, [edi+28h]
0x1002ae2a  jmp     short loc_1002AE43
0x1002ae2c  lea     ecx, [esi+2Ah]
0x1002ae2f  mov     edx, eax
0x1002ae31  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x1002ae36  mov     ecx, [esi]
0x1002ae38  test    eax, eax
0x1002ae3a  jz      short loc_1002AE51
0x1002ae3c  mov     eax, [ebp+var_4]
0x1002ae3f  mov     ebx, esi
0x1002ae41  mov     esi, ecx
0x1002ae43  test    esi, esi
0x1002ae45  jnz     short loc_1002AE2C
0x1002ae47  mov     eax, 0FFFFFA1Dh
0x1002ae4c  pop     edi
0x1002ae4d  pop     esi
0x1002ae4e  pop     ebx
0x1002ae4f  leave
0x1002ae50  retn
0x1002ae51  test    ebx, ebx
0x1002ae53  jnz     short loc_1002AE5A
0x1002ae55  mov     [edi+28h], ecx
0x1002ae58  jmp     short loc_1002AE5C
0x1002ae5a  mov     [ebx], ecx
0x1002ae5c  dec     dword ptr [edi+24h]
0x1002ae5f  mov     ecx, esi
0x1002ae61  call    _MemFree@4; MemFree(x)
0x1002ae66  xor     eax, eax
0x1002ae68  jmp     short loc_1002AE4C
```
