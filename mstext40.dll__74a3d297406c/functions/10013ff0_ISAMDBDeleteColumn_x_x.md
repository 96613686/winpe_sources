# ISAMDBDeleteColumn(x,x)

- ea: `0x10013ff0`
- end: `0x10014066`
- name: `_ISAMDBDeleteColumn@8`
- size: `118`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1000f8f0`

## callees

- `0x1000b200`
- `0x1000bf80`
- `0x10013ff0`

## pseudocode

```c
int __stdcall ISAMDBDeleteColumn(int a1, int a2)
{
  _DWORD *v2; // esi
  _DWORD *v3; // edi
  int v5; // eax

  v2 = *(_DWORD **)(a1 + 916);
  v3 = 0;
  if ( !v2 )
    return -1507;
  while ( DBlstrcmpi(v2 + 9, a2) )
  {
    v3 = v2;
    v2 = (_DWORD *)*v2;
    if ( !v2 )
      return -1507;
  }
  v5 = *v2;
  if ( v3 )
  {
    *v3 = v5;
    --*(_DWORD *)(a1 + 912);
  }
  else
  {
    --*(_DWORD *)(a1 + 912);
    *(_DWORD *)(a1 + 916) = v5;
  }
  MemFree(v2);
  return 0;
}

```

## disassembly

```asm
0x10013ff0  push    ebx
0x10013ff1  mov     ebx, [esp+4+arg_0]
0x10013ff5  push    ebp
0x10013ff6  push    esi
0x10013ff7  push    edi
0x10013ff8  mov     esi, [ebx+394h]
0x10013ffe  xor     edi, edi
0x10014000  test    esi, esi
0x10014002  jz      short loc_1001401E
0x10014004  mov     ebp, [esp+10h+arg_4]
0x10014008  push    ebp
0x10014009  lea     eax, [esi+24h]
0x1001400c  push    eax
0x1001400d  call    _DBlstrcmpi@8; DBlstrcmpi(x,x)
0x10014012  test    eax, eax
0x10014014  jz      short loc_1001402A
0x10014016  mov     edi, esi
0x10014018  mov     esi, [esi]
0x1001401a  test    esi, esi
0x1001401c  jnz     short loc_10014008
0x1001401e  pop     edi
0x1001401f  pop     esi
0x10014020  pop     ebp
0x10014021  mov     eax, 0FFFFFA1Dh
0x10014026  pop     ebx
0x10014027  retn    8
0x1001402a  test    esi, esi
0x1001402c  jz      short loc_1001401E
0x1001402e  mov     eax, [esi]
0x10014030  test    edi, edi
0x10014032  jnz     short loc_1001404F
0x10014034  dec     dword ptr [ebx+390h]
0x1001403a  push    esi
0x1001403b  mov     [ebx+394h], eax
0x10014041  call    _MemFree@4; MemFree(x)
0x10014046  pop     edi
0x10014047  pop     esi
0x10014048  pop     ebp
0x10014049  xor     eax, eax
0x1001404b  pop     ebx
0x1001404c  retn    8
0x1001404f  mov     [edi], eax
0x10014051  dec     dword ptr [ebx+390h]
0x10014057  push    esi
0x10014058  call    _MemFree@4; MemFree(x)
0x1001405d  pop     edi
0x1001405e  pop     esi
0x1001405f  pop     ebp
0x10014060  xor     eax, eax
0x10014062  pop     ebx
0x10014063  retn    8
```
