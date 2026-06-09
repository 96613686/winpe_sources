# DeleteCellFromWorksheet

- ea: `0x1000a000`
- end: `0x1000a1e7`
- name: `DeleteCellFromWorksheet`
- size: `487`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1000a1f0`

## callees

- `0x1000a000`
- `0x1002ed54`

## pseudocode

```c
int __fastcall DeleteCellFromWorksheet(int a1, int a2, int a3)
{
  _DWORD *v3; // esi
  _DWORD *v4; // edi
  int v5; // eax
  int v6; // eax
  int v8; // ecx
  int v9; // ebx
  int *v10; // esi
  unsigned __int16 v11; // ax
  int *v12; // edx
  char v13; // al
  int *v14; // eax
  __int16 v15; // ax
  int v16; // eax
  _DWORD *v17; // ecx
  _DWORD *i; // eax
  int v19; // eax
  _DWORD *v20; // [esp+4h] [ebp-14h]
  int *v23; // [esp+14h] [ebp-4h]

  v3 = *(_DWORD **)(a2 + 28);
  if ( v3 )
  {
    v4 = *(_DWORD **)(a2 + 32);
    v5 = v4[1];
    if ( (unsigned __int16)a3 >= v5 && (unsigned __int16)a3 < v5 + 32 )
    {
LABEL_9:
      if ( v4 )
      {
        v8 = a3 & 0x1F;
        *(_DWORD *)(a2 + 32) = v4;
        v9 = v4[v8 + 2];
        v20 = &v4[v8 + 2];
        if ( v9 )
        {
          v10 = *(int **)(v9 + 16);
          v23 = 0;
          if ( v10 )
          {
            while ( 1 )
            {
              v11 = *((unsigned __int8 *)v10 + 6);
              v12 = v23;
              if ( v11 == HIWORD(a3) || v11 > HIWORD(a3) )
                break;
              v23 = v10;
              v10 = (int *)*v10;
              if ( !v10 )
                return 0;
            }
            if ( *((unsigned __int8 *)v10 + 6) == HIWORD(a3) )
            {
              if ( *(int **)(a2 + 44) == v10 )
                *(_DWORD *)(a2 + 44) = 0;
              v13 = *((_BYTE *)v10 + 7);
              if ( v13 == 4 || v13 == 8 || v13 == 7 || v13 == 9 )
              {
                TextStorageDelete(*(_DWORD *)(a1 + 40), v10[2]);
                v12 = v23;
              }
              v14 = (int *)*v10;
              if ( v12 )
              {
                *v12 = (int)v14;
                if ( !*v10 )
                {
                  *(_BYTE *)(v9 + 1) = *((_BYTE *)v12 + 6);
                  *(_DWORD *)(v9 + 20) = v12;
                }
              }
              else if ( v14 )
              {
                *(_DWORD *)(v9 + 16) = v14;
                *(_BYTE *)v9 = *((_BYTE *)v14 + 6);
              }
              else
              {
                *(_DWORD *)(v9 + 16) = 0;
                *(_DWORD *)(v9 + 20) = 0;
                *(_WORD *)v9 = 0;
              }
              if ( !*(_DWORD *)(v9 + 16) && *(_WORD *)(v9 + 2) == 255 )
              {
                v15 = *(_WORD *)(v9 + 4);
                if ( (v15 & 0x80u) == 0 && (!v15 || v15 == 256) )
                {
                  *v20 = 0;
                  v16 = 0;
                  while ( 1 )
                  {
                    if ( v4[v16 + 2] )
                      return 0;
                    if ( v4[v16 + 3] )
                    {
                      ++v16;
                      goto LABEL_45;
                    }
                    if ( v4[v16 + 4] )
                      break;
                    if ( v4[v16 + 5] )
                    {
                      v16 += 3;
LABEL_45:
                      if ( v16 != 32 )
                        return 0;
                      v17 = 0;
                      for ( i = *(_DWORD **)(a2 + 28); i; i = (_DWORD *)*i )
                      {
                        if ( i == v4 )
                          break;
                        v17 = i;
                      }
                      v19 = *i;
                      if ( !v17 )
                      {
                        *(_DWORD *)(a2 + 28) = v19;
                        --*(_WORD *)(a2 + 24);
                        return 0;
                      }
                      *v17 = v19;
                      --*(_WORD *)(a2 + 24);
                      return 0;
                    }
                    v16 += 4;
                    if ( v16 >= 32 )
                      goto LABEL_45;
                  }
                  v16 += 2;
                  goto LABEL_45;
                }
              }
            }
          }
        }
      }
    }
    else
    {
      while ( 1 )
      {
        v6 = v3[1];
        if ( (unsigned __int16)a3 < v6 )
          break;
        if ( (unsigned __int16)a3 < v6 + 32 )
        {
          v4 = v3;
          goto LABEL_9;
        }
        v3 = (_DWORD *)*v3;
        if ( !v3 )
          return 0;
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1000a000  mov     edi, edi
0x1000a002  push    ebp
0x1000a003  mov     ebp, esp
0x1000a005  sub     esp, 14h
0x1000a008  push    esi
0x1000a009  mov     esi, [edx+1Ch]
0x1000a00c  mov     [ebp+var_C], edx
0x1000a00f  mov     [ebp+var_8], ecx
0x1000a012  test    esi, esi
0x1000a014  jz      loc_1000A1DE
0x1000a01a  movzx   ecx, [ebp+arg_0]
0x1000a01e  push    edi
0x1000a01f  mov     edi, [edx+20h]
0x1000a022  mov     eax, [edi+4]
0x1000a025  cmp     ecx, eax
0x1000a027  jl      short loc_1000A030
0x1000a029  add     eax, 20h ; ' '
0x1000a02c  cmp     ecx, eax
0x1000a02e  jl      short loc_1000A054
0x1000a030  mov     eax, [esi+4]
0x1000a033  cmp     ecx, eax
0x1000a035  jl      loc_1000A1DD
0x1000a03b  add     eax, 20h ; ' '
0x1000a03e  cmp     ecx, eax
0x1000a040  jl      short loc_1000A052
0x1000a042  mov     esi, [esi]
0x1000a044  test    esi, esi
0x1000a046  jnz     short loc_1000A030
0x1000a048  pop     edi
0x1000a049  xor     eax, eax
0x1000a04b  pop     esi
0x1000a04c  mov     esp, ebp
0x1000a04e  pop     ebp
0x1000a04f  retn    4
0x1000a052  mov     edi, esi
0x1000a054  test    edi, edi
0x1000a056  jz      loc_1000A1DD
0x1000a05c  and     ecx, 1Fh
0x1000a05f  mov     [edx+20h], edi
0x1000a062  push    ebx
0x1000a063  lea     eax, [ecx+2]
0x1000a066  mov     ebx, [edi+eax*4]
0x1000a069  lea     eax, [edi+eax*4]
0x1000a06c  mov     [ebp+var_14], eax
0x1000a06f  test    ebx, ebx
0x1000a071  jz      loc_1000A1DC
0x1000a077  mov     esi, [ebx+10h]
0x1000a07a  xor     edx, edx
0x1000a07c  mov     [ebp+var_4], edx
0x1000a07f  test    esi, esi
0x1000a081  jz      loc_1000A1DC
0x1000a087  mov     cx, [ebp+arg_2]
0x1000a08b  nop     dword ptr [eax+eax+00h]
0x1000a090  movzx   eax, byte ptr [esi+6]
0x1000a094  mov     edx, eax
0x1000a096  mov     [ebp+var_10], edx
0x1000a099  mov     edx, [ebp+var_4]
0x1000a09c  cmp     ax, cx
0x1000a09f  jz      short loc_1000A0B7
0x1000a0a1  ja      short loc_1000A0B7
0x1000a0a3  mov     [ebp+var_4], esi
0x1000a0a6  mov     esi, [esi]
0x1000a0a8  test    esi, esi
0x1000a0aa  jnz     short loc_1000A090
0x1000a0ac  pop     ebx
0x1000a0ad  pop     edi
0x1000a0ae  xor     eax, eax
0x1000a0b0  pop     esi
0x1000a0b1  mov     esp, ebp
0x1000a0b3  pop     ebp
0x1000a0b4  retn    4
0x1000a0b7  cmp     word ptr [ebp+var_10], cx
0x1000a0bb  jnz     loc_1000A1DC
0x1000a0c1  mov     eax, [ebp+var_C]
0x1000a0c4  cmp     [eax+2Ch], esi
0x1000a0c7  jnz     short loc_1000A0D0
0x1000a0c9  mov     dword ptr [eax+2Ch], 0
0x1000a0d0  mov     al, [esi+7]
0x1000a0d3  cmp     al, 4
0x1000a0d5  jz      short loc_1000A0E3
0x1000a0d7  cmp     al, 8
0x1000a0d9  jz      short loc_1000A0E3
0x1000a0db  cmp     al, 7
0x1000a0dd  jz      short loc_1000A0E3
0x1000a0df  cmp     al, 9
0x1000a0e1  jnz     short loc_1000A0F4
0x1000a0e3  mov     ecx, [ebp+var_8]
0x1000a0e6  mov     edx, [esi+8]
0x1000a0e9  mov     ecx, [ecx+28h]
0x1000a0ec  call    _TextStorageDelete@8; TextStorageDelete(x,x)
0x1000a0f1  mov     edx, [ebp+var_4]
0x1000a0f4  mov     eax, [esi]
0x1000a0f6  test    edx, edx
0x1000a0f8  jz      short loc_1000A10C
0x1000a0fa  mov     [edx], eax
0x1000a0fc  cmp     dword ptr [esi], 0
0x1000a0ff  jnz     short loc_1000A123
0x1000a101  mov     al, [edx+6]
0x1000a104  mov     [ebx+1], al
0x1000a107  mov     [ebx+14h], edx
0x1000a10a  jmp     short loc_1000A123
0x1000a10c  test    eax, eax
0x1000a10e  jnz     short loc_1000A11B
0x1000a110  mov     [ebx+10h], eax
0x1000a113  mov     [ebx+14h], eax
0x1000a116  mov     [ebx], ax
0x1000a119  jmp     short loc_1000A123
0x1000a11b  mov     [ebx+10h], eax
0x1000a11e  mov     al, [eax+6]
0x1000a121  mov     [ebx], al
0x1000a123  cmp     dword ptr [ebx+10h], 0
0x1000a127  jnz     loc_1000A1DC
0x1000a12d  mov     eax, 0FFh
0x1000a132  cmp     [ebx+2], ax
0x1000a136  jnz     loc_1000A1DC
0x1000a13c  movzx   eax, word ptr [ebx+4]
0x1000a140  test    al, al
0x1000a142  js      loc_1000A1DC
0x1000a148  test    ax, ax
0x1000a14b  jz      short loc_1000A15B
0x1000a14d  mov     ecx, 100h
0x1000a152  cmp     ax, cx
0x1000a155  jnz     loc_1000A1DC
0x1000a15b  mov     eax, [ebp+var_14]
0x1000a15e  mov     dword ptr [eax], 0
0x1000a164  xor     eax, eax
0x1000a166  cmp     dword ptr [edi+eax*4+8], 0
0x1000a16b  jnz     short loc_1000A1DC
0x1000a16d  cmp     dword ptr [edi+eax*4+0Ch], 0
0x1000a172  jnz     short loc_1000A196
0x1000a174  cmp     dword ptr [edi+eax*4+10h], 0
0x1000a179  jnz     short loc_1000A191
0x1000a17b  cmp     dword ptr [edi+eax*4+14h], 0
0x1000a180  jnz     short loc_1000A18C
0x1000a182  add     eax, 4
0x1000a185  cmp     eax, 20h ; ' '
0x1000a188  jl      short loc_1000A166
0x1000a18a  jmp     short loc_1000A197
0x1000a18c  add     eax, 3
0x1000a18f  jmp     short loc_1000A197
0x1000a191  add     eax, 2
0x1000a194  jmp     short loc_1000A197
0x1000a196  inc     eax
0x1000a197  cmp     eax, 20h ; ' '
0x1000a19a  jnz     short loc_1000A1DC
0x1000a19c  mov     edx, [ebp+var_C]
0x1000a19f  xor     ecx, ecx
0x1000a1a1  mov     eax, [edx+1Ch]
0x1000a1a4  test    eax, eax
0x1000a1a6  jz      short loc_1000A1B4
0x1000a1a8  cmp     eax, edi
0x1000a1aa  jz      short loc_1000A1B4
0x1000a1ac  mov     ecx, eax
0x1000a1ae  mov     eax, [eax]
0x1000a1b0  test    eax, eax
0x1000a1b2  jnz     short loc_1000A1A8
0x1000a1b4  mov     eax, [eax]
0x1000a1b6  test    ecx, ecx
0x1000a1b8  jnz     short loc_1000A1D1
0x1000a1ba  mov     [edx+1Ch], eax
0x1000a1bd  mov     eax, 0FFFFh
0x1000a1c2  add     [edx+18h], ax
0x1000a1c6  xor     eax, eax
0x1000a1c8  pop     ebx
0x1000a1c9  pop     edi
0x1000a1ca  pop     esi
0x1000a1cb  mov     esp, ebp
0x1000a1cd  pop     ebp
0x1000a1ce  retn    4
0x1000a1d1  mov     [ecx], eax
0x1000a1d3  mov     eax, 0FFFFh
0x1000a1d8  add     [edx+18h], ax
0x1000a1dc  pop     ebx
0x1000a1dd  pop     edi
0x1000a1de  xor     eax, eax
0x1000a1e0  pop     esi
0x1000a1e1  mov     esp, ebp
0x1000a1e3  pop     ebp
0x1000a1e4  retn    4
```
