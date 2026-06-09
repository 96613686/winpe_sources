# AddCopyCell

- ea: `0x10031fd9`
- end: `0x1003204a`
- name: `AddCopyCell`
- size: `113`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x10032050`
- `0x10032097`
- `0x100320e5`
- `0x100321bc`
- `0x10032274`
- `0x10032705`

## callees

- `0x10025ab7`
- `0x10031fd9`

## pseudocode

```c
void __fastcall AddCopyCell(int a1, int a2)
{
  int *v4; // eax
  int v5; // ecx
  unsigned __int8 v6; // dl
  _DWORD *v7; // ecx
  int *v8; // esi
  _DWORD *v9; // [esp+8h] [ebp-4h]

  if ( a2 )
  {
    v4 = *(int **)(a1 + 40);
    if ( !v4 )
    {
      *(_DWORD *)(a1 + 40) = a2;
LABEL_6:
      *(_DWORD *)(a1 + 44) = a2;
      return;
    }
    v5 = *(_DWORD *)(a1 + 44);
    v6 = *(_BYTE *)(a2 + 4);
    if ( *(_BYTE *)(v5 + 4) < v6 )
    {
      *(_DWORD *)v5 = a2;
      goto LABEL_6;
    }
    v7 = 0;
    v9 = 0;
    while ( *((_BYTE *)v4 + 4) < v6 )
    {
      v7 = v4;
      v9 = v4;
      v4 = (int *)*v4;
      if ( !v4 )
      {
        *(_DWORD *)a2 = 0;
LABEL_14:
        *(_DWORD *)(a1 + 44) = a2;
        goto LABEL_15;
      }
    }
    if ( *((_BYTE *)v4 + 4) == v6 )
    {
      v8 = (int *)*v4;
      MemFree(v4);
      v7 = v9;
      v4 = v8;
    }
    *(_DWORD *)a2 = v4;
    if ( !v4 )
      goto LABEL_14;
LABEL_15:
    if ( v7 )
      *v7 = a2;
    else
      *(_DWORD *)(a1 + 40) = a2;
  }
}

```

## disassembly

```asm
0x10031fd9  mov     edi, edi
0x10031fdb  push    ebp
0x10031fdc  mov     ebp, esp
0x10031fde  push    ecx
0x10031fdf  push    ebx
0x10031fe0  push    edi
0x10031fe1  mov     edi, edx
0x10031fe3  mov     ebx, ecx
0x10031fe5  test    edi, edi
0x10031fe7  jz      short loc_10032046
0x10031fe9  mov     eax, [ebx+28h]
0x10031fec  test    eax, eax
0x10031fee  jnz     short loc_10031FF5
0x10031ff0  mov     [ebx+28h], edi
0x10031ff3  jmp     short loc_10032002
0x10031ff5  mov     ecx, [ebx+2Ch]
0x10031ff8  mov     dl, [edi+4]
0x10031ffb  cmp     [ecx+4], dl
0x10031ffe  jnb     short loc_10032007
0x10032000  mov     [ecx], edi
0x10032002  mov     [ebx+2Ch], edi
0x10032005  jmp     short loc_10032046
0x10032007  xor     ecx, ecx
0x10032009  mov     [ebp+var_4], ecx
0x1003200c  cmp     [eax+4], dl
0x1003200f  jnb     short loc_10032020
0x10032011  mov     ecx, eax
0x10032013  mov     [ebp+var_4], eax
0x10032016  mov     eax, [eax]
0x10032018  test    eax, eax
0x1003201a  jnz     short loc_1003200C
0x1003201c  mov     [edi], eax
0x1003201e  jmp     short loc_10032038
0x10032020  jnz     short loc_10032032
0x10032022  push    esi
0x10032023  mov     esi, [eax]
0x10032025  mov     ecx, eax
0x10032027  call    _MemFree@4; MemFree(x)
0x1003202c  mov     ecx, [ebp+var_4]
0x1003202f  mov     eax, esi
0x10032031  pop     esi
0x10032032  mov     [edi], eax
0x10032034  test    eax, eax
0x10032036  jnz     short loc_1003203B
0x10032038  mov     [ebx+2Ch], edi
0x1003203b  test    ecx, ecx
0x1003203d  jnz     short loc_10032044
0x1003203f  mov     [ebx+28h], edi
0x10032042  jmp     short loc_10032046
0x10032044  mov     [ecx], edi
0x10032046  pop     edi
0x10032047  pop     ebx
0x10032048  leave
0x10032049  retn
```
