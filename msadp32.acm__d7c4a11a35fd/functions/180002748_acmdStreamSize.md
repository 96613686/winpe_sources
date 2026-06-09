# acmdStreamSize

- ea: `0x180002748`
- end: `0x1800028b0`
- name: `acmdStreamSize`
- size: `360`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x180001cd0`

## callees

- `0x180002748`

## pseudocode

```c
__int64 __fastcall acmdStreamSize(__int64 a1, __int64 a2, _DWORD *a3)
{
  _WORD *v3; // r9
  _WORD *v5; // r8
  unsigned int v7; // r11d
  unsigned int v8; // r8d
  unsigned __int64 v9; // r8
  __int64 v10; // rax
  unsigned int v11; // r11d
  unsigned int v12; // r8d
  unsigned __int64 v13; // r8
  bool v14; // cc
  unsigned int v15; // ecx
  int v16; // eax
  int v17; // edx
  __int64 v18; // rcx

  v3 = *(_WORD **)(a2 + 4);
  v5 = *(_WORD **)(a2 + 12);
  if ( (a3[1] & 0xF) == 0 )
  {
    if ( *v3 == 2 )
    {
      v11 = a3[2] / (unsigned int)(unsigned __int16)v3[6];
      if ( !v11 )
        return 512;
      v12 = (unsigned __int16)v3[9] * (unsigned __int16)v5[6];
      if ( 0xFFFFFFFF / v12 < v11 )
        return 512;
      if ( !(a3[2] % (unsigned int)(unsigned __int16)v3[6]) )
      {
        LODWORD(v13) = v11 * v12;
        goto LABEL_22;
      }
      v13 = v12 * (unsigned __int64)(v11 + 1);
      v14 = v13 <= 0xFFFFFFFF;
    }
    else
    {
      v15 = (unsigned __int16)v3[6] * (unsigned __int16)v5[9];
      v17 = a3[2] % v15;
      v16 = a3[2] / v15;
      v18 = (unsigned __int16)v5[6];
      if ( !v17 )
      {
        LODWORD(v13) = v16 * v18;
LABEL_22:
        if ( (_DWORD)v13 )
        {
          a3[3] = v13;
          return 0;
        }
        return 512;
      }
      v13 = v18 * (unsigned int)(v16 + 1);
      v14 = v13 <= 0xFFFFFFFF;
    }
    if ( !v14 )
      return 512;
    goto LABEL_22;
  }
  if ( (a3[1] & 0xF) != 1 )
    return 8;
  if ( *v5 == 2 )
  {
    v7 = a3[3] / (unsigned int)(unsigned __int16)v5[6];
    if ( v7 )
    {
      v8 = (unsigned __int16)v3[6] * (unsigned __int16)v5[9];
      if ( 0xFFFFFFFF / v8 >= v7 )
      {
        LODWORD(v9) = v7 * v8;
LABEL_10:
        a3[2] = v9;
        return 0;
      }
    }
  }
  else
  {
    v10 = a3[3] / ((unsigned __int16)v5[6] * (unsigned int)(unsigned __int16)v3[9]);
    if ( (_DWORD)v10 )
    {
      v9 = v10 * (unsigned __int16)v3[6];
      if ( v9 <= 0xFFFFFFFF )
        goto LABEL_10;
    }
  }
  return 512;
}

```

## disassembly

```asm
0x180002748  mov     [rsp+arg_0], rbx
0x18000274d  mov     r9, [rdx+4]
0x180002751  mov     r10, r8
0x180002754  mov     r8, [rdx+0Ch]
0x180002758  mov     eax, [r10+4]
0x18000275c  and     eax, 0Fh
0x18000275f  jz      loc_1800027FC
0x180002765  cmp     eax, 1
0x180002768  jz      short loc_180002774
0x18000276a  mov     eax, 8
0x18000276f  jmp     loc_1800028AA
0x180002774  mov     ecx, 2
0x180002779  xor     edx, edx
0x18000277b  cmp     cx, [r8]
0x18000277f  jnz     short loc_1800027BE
0x180002781  movzx   ecx, word ptr [r8+0Ch]
0x180002786  mov     eax, [r10+0Ch]
0x18000278a  div     ecx
0x18000278c  mov     r11d, eax
0x18000278f  test    eax, eax
0x180002791  jz      loc_1800028A5
0x180002797  movzx   r8d, word ptr [r8+12h]
0x18000279c  xor     edx, edx
0x18000279e  movzx   ecx, word ptr [r9+0Ch]
0x1800027a3  mov     eax, 0FFFFFFFFh
0x1800027a8  imul    r8d, ecx
0x1800027ac  div     r8d
0x1800027af  cmp     eax, r11d
0x1800027b2  jb      loc_1800028A5
0x1800027b8  imul    r8d, r11d
0x1800027bc  jmp     short loc_1800027F1
0x1800027be  movzx   eax, word ptr [r8+0Ch]
0x1800027c3  movzx   ecx, word ptr [r9+12h]
0x1800027c8  imul    ecx, eax
0x1800027cb  mov     eax, [r10+0Ch]
0x1800027cf  div     ecx
0x1800027d1  test    eax, eax
0x1800027d3  jz      loc_1800028A5
0x1800027d9  movzx   r8d, word ptr [r9+0Ch]
0x1800027de  mov     r9d, 0FFFFFFFFh
0x1800027e4  imul    r8, rax
0x1800027e8  cmp     r8, r9
0x1800027eb  ja      loc_1800028A5
0x1800027f1  mov     [r10+8], r8d
0x1800027f5  xor     eax, eax
0x1800027f7  jmp     loc_1800028AA
0x1800027fc  mov     ecx, 2
0x180002801  xor     edx, edx
0x180002803  cmp     cx, [r9]
0x180002807  jnz     short loc_18000285F
0x180002809  movzx   ecx, word ptr [r9+0Ch]
0x18000280e  mov     eax, [r10+8]
0x180002812  div     ecx
0x180002814  mov     ebx, edx
0x180002816  mov     r11d, eax
0x180002819  test    eax, eax
0x18000281b  jz      loc_1800028A5
0x180002821  movzx   ecx, word ptr [r9+12h]
0x180002826  xor     edx, edx
0x180002828  movzx   r8d, word ptr [r8+0Ch]
0x18000282d  mov     r9d, 0FFFFFFFFh
0x180002833  imul    r8d, ecx
0x180002837  mov     eax, r9d
0x18000283a  div     r8d
0x18000283d  cmp     eax, r11d
0x180002840  jb      short loc_1800028A5
0x180002842  test    ebx, ebx
0x180002844  jnz     short loc_18000284C
0x180002846  imul    r8d, r11d
0x18000284a  jmp     short loc_180002897
0x18000284c  mov     eax, r8d
0x18000284f  lea     ecx, [r11+1]
0x180002853  imul    rcx, rax
0x180002857  mov     r8, rcx
0x18000285a  cmp     rcx, r9
0x18000285d  jmp     short loc_180002895
0x18000285f  movzx   ecx, word ptr [r8+12h]
0x180002864  movzx   eax, word ptr [r9+0Ch]
0x180002869  imul    ecx, eax
0x18000286c  mov     eax, [r10+8]
0x180002870  div     ecx
0x180002872  movzx   ecx, word ptr [r8+0Ch]
0x180002877  test    edx, edx
0x180002879  jnz     short loc_180002884
0x18000287b  mov     r8d, ecx
0x18000287e  imul    r8d, eax
0x180002882  jmp     short loc_180002897
0x180002884  lea     r8d, [rax+1]
0x180002888  mov     r9d, 0FFFFFFFFh
0x18000288e  imul    r8, rcx
0x180002892  cmp     r8, r9
0x180002895  ja      short loc_1800028A5
0x180002897  test    r8d, r8d
0x18000289a  jz      short loc_1800028A5
0x18000289c  mov     [r10+0Ch], r8d
0x1800028a0  jmp     loc_1800027F5
0x1800028a5  mov     eax, 200h
0x1800028aa  mov     rbx, [rsp+arg_0]
0x1800028af  retn
```
