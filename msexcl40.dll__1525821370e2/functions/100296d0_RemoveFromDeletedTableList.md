# RemoveFromDeletedTableList

- ea: `0x100296d0`
- end: `0x1002971e`
- name: `RemoveFromDeletedTableList`
- size: `78`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x10029730`

## callees

- `0x10025775`
- `0x10025ab7`
- `0x100296d0`

## pseudocode

```c
void __fastcall RemoveFromDeletedTableList(int a1, int a2)
{
  _DWORD *v3; // edi
  _DWORD *v4; // esi
  int v5; // eax
  int v6; // eax
  int v7; // ecx
  int v8; // [esp+Ch] [ebp-4h]

  v3 = 0;
  v4 = *(_DWORD **)(a1 + 52);
  if ( v4 )
  {
    v5 = a2 + 104;
    v8 = a2 + 104;
    while ( 1 )
    {
      v6 = DBlstrcmpi((int)(v4 + 3), v5);
      v7 = *v4;
      if ( !v6 )
        break;
      v5 = v8;
      v3 = v4;
      v4 = (_DWORD *)*v4;
      if ( !v7 )
        return;
    }
    if ( v3 )
      *v3 = v7;
    else
      *(_DWORD *)(a1 + 52) = v7;
    MemFree(v4);
  }
}

```

## disassembly

```asm
0x100296d0  mov     edi, edi
0x100296d2  push    ebp
0x100296d3  mov     ebp, esp
0x100296d5  push    ecx
0x100296d6  push    ebx
0x100296d7  mov     ebx, ecx
0x100296d9  push    esi
0x100296da  push    edi
0x100296db  xor     edi, edi
0x100296dd  mov     esi, [ebx+34h]
0x100296e0  test    esi, esi
0x100296e2  jz      short loc_10029719
0x100296e4  lea     eax, [edx+68h]
0x100296e7  mov     [ebp+var_4], eax
0x100296ea  lea     ecx, [esi+0Ch]
0x100296ed  mov     edx, eax
0x100296ef  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x100296f4  mov     ecx, [esi]
0x100296f6  test    eax, eax
0x100296f8  jz      short loc_10029707
0x100296fa  mov     eax, [ebp+var_4]
0x100296fd  mov     edi, esi
0x100296ff  mov     esi, ecx
0x10029701  test    esi, esi
0x10029703  jnz     short loc_100296EA
0x10029705  jmp     short loc_10029719
0x10029707  test    edi, edi
0x10029709  jnz     short loc_10029710
0x1002970b  mov     [ebx+34h], ecx
0x1002970e  jmp     short loc_10029712
0x10029710  mov     [edi], ecx
0x10029712  mov     ecx, esi
0x10029714  call    _MemFree@4; MemFree(x)
0x10029719  pop     edi
0x1002971a  pop     esi
0x1002971b  pop     ebx
0x1002971c  leave
0x1002971d  retn
```
