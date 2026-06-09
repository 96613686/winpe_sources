# TextStorageDelete(x,x)

- ea: `0x1002ed54`
- end: `0x1002edcc`
- name: `_TextStorageDelete@8`
- size: `120`
- prototype: `int __fastcall(_DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x100077d0`
- `0x1000a000`

## callees

- `0x10025ab7`
- `0x1002ec2d`
- `0x1002ed54`

## pseudocode

```c
void __fastcall TextStorageDelete(int a1, unsigned __int16 *a2)
{
  __int16 v4; // ax
  unsigned int v5; // ebx
  unsigned __int16 *v6; // edx
  unsigned __int16 *i; // ecx
  unsigned __int16 *v8; // eax

  if ( a2 )
  {
    if ( a2 != (unsigned __int16 *)-1 )
    {
      v4 = a2[3] & 0x7F;
      if ( v4 != 127 )
      {
        if ( v4 )
        {
          a2[3] = (v4 - 1) | a2[3] & 0xFF80;
        }
        else
        {
          v5 = Hash(a2 + 7, a2[2]);
          v6 = 0;
          for ( i = *(unsigned __int16 **)(a1 + 4 * v5 + 8); i; i = *(unsigned __int16 **)i )
          {
            v8 = *(unsigned __int16 **)i;
            if ( i == a2 )
            {
              if ( v6 )
                *(_DWORD *)v6 = v8;
              else
                *(_DWORD *)(a1 + 4 * v5 + 8) = v8;
              if ( *((char *)i + 6) >= 0 )
                MemFree(i);
              return;
            }
            v6 = i;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x1002ed54  mov     edi, edi
0x1002ed56  push    esi
0x1002ed57  mov     esi, edx
0x1002ed59  push    edi
0x1002ed5a  mov     edi, ecx
0x1002ed5c  test    esi, esi
0x1002ed5e  jz      short loc_1002EDAF
0x1002ed60  cmp     esi, 0FFFFFFFFh
0x1002ed63  jz      short loc_1002EDAF
0x1002ed65  movzx   ecx, word ptr [esi+6]
0x1002ed69  push    7Fh
0x1002ed6b  pop     edx
0x1002ed6c  mov     eax, ecx
0x1002ed6e  and     eax, edx
0x1002ed70  cmp     ax, dx
0x1002ed73  jz      short loc_1002EDAF
0x1002ed75  test    ax, ax
0x1002ed78  jz      short loc_1002ED89
0x1002ed7a  and     ecx, 0FF80h
0x1002ed80  dec     eax
0x1002ed81  or      ecx, eax
0x1002ed83  mov     [esi+6], cx
0x1002ed87  jmp     short loc_1002EDAF
0x1002ed89  movzx   edx, word ptr [esi+4]
0x1002ed8d  lea     ecx, [esi+0Eh]
0x1002ed90  push    ebx
0x1002ed91  call    Hash
0x1002ed96  mov     ebx, eax
0x1002ed98  xor     edx, edx
0x1002ed9a  mov     ecx, [edi+ebx*4+8]
0x1002ed9e  jmp     short loc_1002EDAA
0x1002eda0  mov     eax, [ecx]
0x1002eda2  cmp     ecx, esi
0x1002eda4  jz      short loc_1002EDB2
0x1002eda6  mov     edx, ecx
0x1002eda8  mov     ecx, eax
0x1002edaa  test    ecx, ecx
0x1002edac  jnz     short loc_1002EDA0
0x1002edae  pop     ebx
0x1002edaf  pop     edi
0x1002edb0  pop     esi
0x1002edb1  retn
0x1002edb2  test    edx, edx
0x1002edb4  jnz     short loc_1002EDBC
0x1002edb6  mov     [edi+ebx*4+8], eax
0x1002edba  jmp     short loc_1002EDBE
0x1002edbc  mov     [edx], eax
0x1002edbe  test    byte ptr [ecx+6], 80h
0x1002edc2  jnz     short loc_1002EDAE
0x1002edc4  pop     ebx
0x1002edc5  pop     edi
0x1002edc6  pop     esi
0x1002edc7  jmp     _MemFree@4; MemFree(x)
```
