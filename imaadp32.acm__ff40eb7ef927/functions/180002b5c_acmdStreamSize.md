# acmdStreamSize

- ea: `0x180002b5c`
- end: `0x180002cc3`
- name: `acmdStreamSize`
- size: `359`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x1800020b0`
- `0x18000494c`

## callees

- `0x180002b5c`

## pseudocode

```c
__int64 __fastcall acmdStreamSize(__int64 a1, _DWORD *a2)
{
  _WORD *v3; // r9
  _WORD *v4; // r8
  unsigned int v6; // r11d
  unsigned int v7; // r8d
  unsigned __int64 v8; // r8
  __int64 v9; // rax
  unsigned int v10; // r11d
  unsigned int v11; // r8d
  unsigned __int64 v12; // r8
  bool v13; // cc
  unsigned int v14; // ecx
  int v15; // eax
  int v16; // edx
  __int64 v17; // rcx

  v3 = *(_WORD **)(a1 + 4);
  v4 = *(_WORD **)(a1 + 12);
  if ( (a2[1] & 0xF) == 0 )
  {
    if ( *v3 == 17 )
    {
      v10 = a2[2] / (unsigned int)(unsigned __int16)v3[6];
      if ( !v10 )
        return 512;
      v11 = (unsigned __int16)v3[9] * (unsigned __int16)v4[6];
      if ( 0xFFFFFFFF / v11 < v10 )
        return 512;
      if ( !(a2[2] % (unsigned int)(unsigned __int16)v3[6]) )
      {
        LODWORD(v12) = v10 * v11;
        goto LABEL_22;
      }
      v12 = v11 * (unsigned __int64)(v10 + 1);
      v13 = v12 <= 0xFFFFFFFF;
    }
    else
    {
      v14 = (unsigned __int16)v3[6] * (unsigned __int16)v4[9];
      v16 = a2[2] % v14;
      v15 = a2[2] / v14;
      v17 = (unsigned __int16)v4[6];
      if ( !v16 )
      {
        LODWORD(v12) = v15 * v17;
LABEL_22:
        if ( (_DWORD)v12 )
        {
          a2[3] = v12;
          return 0;
        }
        return 512;
      }
      v12 = v17 * (unsigned int)(v15 + 1);
      v13 = v12 <= 0xFFFFFFFF;
    }
    if ( !v13 )
      return 512;
    goto LABEL_22;
  }
  if ( (a2[1] & 0xF) != 1 )
    return 8;
  if ( *v4 == 17 )
  {
    v6 = a2[3] / (unsigned int)(unsigned __int16)v4[6];
    if ( v6 )
    {
      v7 = (unsigned __int16)v3[6] * (unsigned __int16)v4[9];
      if ( 0xFFFFFFFF / v7 >= v6 )
      {
        LODWORD(v8) = v6 * v7;
LABEL_10:
        a2[2] = v8;
        return 0;
      }
    }
  }
  else
  {
    v9 = a2[3] / ((unsigned __int16)v4[6] * (unsigned int)(unsigned __int16)v3[9]);
    if ( (_DWORD)v9 )
    {
      v8 = v9 * (unsigned __int16)v3[6];
      if ( v8 <= 0xFFFFFFFF )
        goto LABEL_10;
    }
  }
  return 512;
}

```

## disassembly

```asm
0x180002b5c  mov     [rsp+arg_0], rbx
0x180002b61  mov     eax, [rdx+4]
0x180002b64  mov     r10, rdx
0x180002b67  mov     r9, [rcx+4]
0x180002b6b  mov     r8, [rcx+0Ch]
0x180002b6f  and     eax, 0Fh
0x180002b72  jz      loc_180002C0F
0x180002b78  cmp     eax, 1
0x180002b7b  jz      short loc_180002B87
0x180002b7d  mov     eax, 8
0x180002b82  jmp     loc_180002CBD
0x180002b87  mov     ecx, 11h
0x180002b8c  xor     edx, edx
0x180002b8e  cmp     cx, [r8]
0x180002b92  jnz     short loc_180002BD1
0x180002b94  movzx   ecx, word ptr [r8+0Ch]
0x180002b99  mov     eax, [r10+0Ch]
0x180002b9d  div     ecx
0x180002b9f  mov     r11d, eax
0x180002ba2  test    eax, eax
0x180002ba4  jz      loc_180002CB8
0x180002baa  movzx   r8d, word ptr [r8+12h]
0x180002baf  xor     edx, edx
0x180002bb1  movzx   ecx, word ptr [r9+0Ch]
0x180002bb6  mov     eax, 0FFFFFFFFh
0x180002bbb  imul    r8d, ecx
0x180002bbf  div     r8d
0x180002bc2  cmp     eax, r11d
0x180002bc5  jb      loc_180002CB8
0x180002bcb  imul    r8d, r11d
0x180002bcf  jmp     short loc_180002C04
0x180002bd1  movzx   eax, word ptr [r8+0Ch]
0x180002bd6  movzx   ecx, word ptr [r9+12h]
0x180002bdb  imul    ecx, eax
0x180002bde  mov     eax, [r10+0Ch]
0x180002be2  div     ecx
0x180002be4  test    eax, eax
0x180002be6  jz      loc_180002CB8
0x180002bec  movzx   r8d, word ptr [r9+0Ch]
0x180002bf1  mov     r9d, 0FFFFFFFFh
0x180002bf7  imul    r8, rax
0x180002bfb  cmp     r8, r9
0x180002bfe  ja      loc_180002CB8
0x180002c04  mov     [r10+8], r8d
0x180002c08  xor     eax, eax
0x180002c0a  jmp     loc_180002CBD
0x180002c0f  mov     ecx, 11h
0x180002c14  xor     edx, edx
0x180002c16  cmp     cx, [r9]
0x180002c1a  jnz     short loc_180002C72
0x180002c1c  movzx   ecx, word ptr [r9+0Ch]
0x180002c21  mov     eax, [r10+8]
0x180002c25  div     ecx
0x180002c27  mov     ebx, edx
0x180002c29  mov     r11d, eax
0x180002c2c  test    eax, eax
0x180002c2e  jz      loc_180002CB8
0x180002c34  movzx   ecx, word ptr [r9+12h]
0x180002c39  xor     edx, edx
0x180002c3b  movzx   r8d, word ptr [r8+0Ch]
0x180002c40  mov     r9d, 0FFFFFFFFh
0x180002c46  imul    r8d, ecx
0x180002c4a  mov     eax, r9d
0x180002c4d  div     r8d
0x180002c50  cmp     eax, r11d
0x180002c53  jb      short loc_180002CB8
0x180002c55  test    ebx, ebx
0x180002c57  jnz     short loc_180002C5F
0x180002c59  imul    r8d, r11d
0x180002c5d  jmp     short loc_180002CAA
0x180002c5f  mov     eax, r8d
0x180002c62  lea     ecx, [r11+1]
0x180002c66  imul    rcx, rax
0x180002c6a  mov     r8, rcx
0x180002c6d  cmp     rcx, r9
0x180002c70  jmp     short loc_180002CA8
0x180002c72  movzx   ecx, word ptr [r8+12h]
0x180002c77  movzx   eax, word ptr [r9+0Ch]
0x180002c7c  imul    ecx, eax
0x180002c7f  mov     eax, [r10+8]
0x180002c83  div     ecx
0x180002c85  movzx   ecx, word ptr [r8+0Ch]
0x180002c8a  test    edx, edx
0x180002c8c  jnz     short loc_180002C97
0x180002c8e  mov     r8d, ecx
0x180002c91  imul    r8d, eax
0x180002c95  jmp     short loc_180002CAA
0x180002c97  lea     r8d, [rax+1]
0x180002c9b  mov     r9d, 0FFFFFFFFh
0x180002ca1  imul    r8, rcx
0x180002ca5  cmp     r8, r9
0x180002ca8  ja      short loc_180002CB8
0x180002caa  test    r8d, r8d
0x180002cad  jz      short loc_180002CB8
0x180002caf  mov     [r10+0Ch], r8d
0x180002cb3  jmp     loc_180002C08
0x180002cb8  mov     eax, 200h
0x180002cbd  mov     rbx, [rsp+arg_0]
0x180002cc2  retn
```
