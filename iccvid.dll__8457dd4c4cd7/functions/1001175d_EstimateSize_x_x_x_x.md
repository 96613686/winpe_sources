# EstimateSize(x,x,x,x)

- ea: `0x1001175d`
- end: `0x10011805`
- name: `_EstimateSize@16`
- size: `168`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1001195d`
- `0x10011a4a`

## callees

- `0x1001175d`

## pseudocode

```c
unsigned int __fastcall EstimateSize(int a1, int a2, unsigned __int16 a3, unsigned __int16 a4)
{
  int v4; // edi
  int v6; // edx
  int v7; // esi
  unsigned __int16 *v8; // ebx
  int v9; // eax
  int v10; // edi
  unsigned __int16 v11; // cx
  int v12; // eax
  int v13; // ecx
  unsigned __int16 *v14; // edi
  unsigned __int16 v15; // ax
  int v17; // [esp+Ch] [ebp-Ch]
  unsigned __int16 *v18; // [esp+10h] [ebp-8h]

  v4 = a1;
  v6 = 0;
  v17 = a2;
  v7 = 0;
  v8 = *(unsigned __int16 **)(a1 + 112);
  if ( *(_BYTE *)(a1 + 82) )
  {
    v18 = *(unsigned __int16 **)(a1 + 108);
    v13 = *(_DWORD *)(a2 + 12);
    if ( v13 )
    {
      v14 = v18;
      do
      {
        v15 = *v14;
        --v13;
        ++v14;
        if ( v15 >= a3 )
        {
          if ( *v8 < a4 )
            ++v7;
          else
            ++v6;
        }
        ++v8;
      }
      while ( v13 );
      goto LABEL_17;
    }
  }
  else
  {
    v9 = *(_DWORD *)(a2 + 12);
    if ( v9 )
    {
      v10 = v9;
      do
      {
        v11 = *v8;
        v12 = v6 + 1;
        ++v8;
        if ( v11 < a4 )
          v12 = v6;
        v6 = v12;
        if ( v11 < a4 )
          ++v7;
        --v10;
      }
      while ( v10 );
LABEL_17:
      v4 = a1;
    }
  }
  *(_DWORD *)(v4 + 120) = v6;
  *(_DWORD *)(v4 + 116) = v6 + v7;
  return v7 + (((v7 + v6 + *(_DWORD *)(v17 + 12) + 31) >> 3) & 0xFFFFFFFC) + 4 * v6 + 4;
}

```

## disassembly

```asm
0x1001175d  mov     edi, edi
0x1001175f  push    ebp
0x10011760  mov     ebp, esp
0x10011762  sub     esp, 0Ch
0x10011765  push    ebx
0x10011766  push    esi
0x10011767  push    edi
0x10011768  mov     edi, ecx
0x1001176a  mov     eax, edx
0x1001176c  xor     edx, edx
0x1001176e  mov     [ebp+var_C], eax
0x10011771  mov     [ebp+var_4], edi
0x10011774  mov     esi, edx
0x10011776  mov     ebx, [edi+70h]
0x10011779  cmp     [edi+52h], dl
0x1001177c  jnz     short loc_100117A6
0x1001177e  mov     eax, [eax+0Ch]
0x10011781  test    eax, eax
0x10011783  jz      short loc_100117DA
0x10011785  mov     edi, eax
0x10011787  movzx   ecx, word ptr [ebx]
0x1001178a  lea     eax, [edx+1]
0x1001178d  cmp     cx, [ebp+arg_4]
0x10011791  lea     ebx, [ebx+2]
0x10011794  cmovb   eax, edx
0x10011797  mov     edx, eax
0x10011799  lea     eax, [esi+1]
0x1001179c  cmovb   esi, eax
0x1001179f  sub     edi, 1
0x100117a2  jnz     short loc_10011787
0x100117a4  jmp     short loc_100117D7
0x100117a6  mov     ecx, [edi+6Ch]
0x100117a9  mov     [ebp+var_8], ecx
0x100117ac  mov     ecx, [eax+0Ch]
0x100117af  test    ecx, ecx
0x100117b1  jz      short loc_100117DA
0x100117b3  mov     edi, [ebp+var_8]
0x100117b6  mov     ax, [edi]
0x100117b9  dec     ecx
0x100117ba  lea     edi, [edi+2]
0x100117bd  cmp     ax, [ebp+arg_0]
0x100117c1  jb      short loc_100117D0
0x100117c3  mov     ax, [ebp+arg_4]
0x100117c7  cmp     [ebx], ax
0x100117ca  jb      short loc_100117CF
0x100117cc  inc     edx
0x100117cd  jmp     short loc_100117D0
0x100117cf  inc     esi
0x100117d0  add     ebx, 2
0x100117d3  test    ecx, ecx
0x100117d5  jnz     short loc_100117B6
0x100117d7  mov     edi, [ebp+var_4]
0x100117da  lea     eax, [edx+esi]
0x100117dd  mov     [edi+78h], edx
0x100117e0  mov     [edi+74h], eax
0x100117e3  mov     eax, [ebp+var_C]
0x100117e6  pop     edi
0x100117e7  mov     eax, [eax+0Ch]
0x100117ea  add     eax, 1Fh
0x100117ed  add     eax, edx
0x100117ef  add     eax, esi
0x100117f1  sar     eax, 3
0x100117f4  and     eax, 0FFFFFFFCh
0x100117f7  add     eax, esi
0x100117f9  pop     esi
0x100117fa  pop     ebx
0x100117fb  lea     eax, [eax+edx*4]
0x100117fe  add     eax, 4
0x10011801  leave
0x10011802  retn    8
```
