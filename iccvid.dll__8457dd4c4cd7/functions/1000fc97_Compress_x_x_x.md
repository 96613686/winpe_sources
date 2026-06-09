# Compress(x,x,x)

- ea: `0x1000fc97`
- end: `0x1000fded`
- name: `_Compress@12`
- size: `342`
- prototype: `HRESULT __stdcall(PVOID context, const BYTE *input_buffer, LONG input_buffer_size, PBYTE output_buffer, LONG output_buffer_size, PLONG input_used, PLONG output_used, INT compression_level)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x1000425b`
- `0x1000fa28`
- `0x1000fbcc`
- `0x1000fc97`

## pseudocode

```c
HRESULT __stdcall Compress(
        PVOID context,
        const BYTE *input_buffer,
        LONG input_buffer_size,
        PBYTE output_buffer,
        LONG output_buffer_size,
        PLONG input_used,
        PLONG output_used,
        INT compression_level)
{
  int v8; // edx
  int v9; // ecx
  int v10; // ebx
  int v11; // edi
  int v12; // esi
  int v13; // ecx
  HRESULT result; // eax
  _DWORD *v15; // eax
  bool v16; // al
  unsigned int v17; // eax
  char v18; // bl
  int v19; // eax
  int v20; // eax
  int v21; // eax
  int v22; // ecx
  _DWORD *v23; // eax
  int *v24; // ecx
  int v25; // eax
  int v26; // [esp-4h] [ebp-14h]
  int v27; // [esp+0h] [ebp-10h]
  char v28; // [esp+Ch] [ebp-4h]

  v11 = v9;
  v12 = v8;
  if ( !*(_BYTE *)(v9 + 4)
    || (v13 = *(_DWORD *)(v8 + 12), *(_DWORD *)(v13 + 4) != *(_DWORD *)(v11 + 16))
    || *(_DWORD *)(v13 + 8) != *(_DWORD *)(v11 + 20) )
  {
    result = CompressBegin(v11, *(__int16 **)(v8 + 12), *(_DWORD *)(v8 + 4));
    if ( result )
      return result;
  }
  result = CompressQuery(*(_DWORD *)(v12 + 4));
  if ( result )
    return result;
  v16 = (*(_BYTE *)v12 & 1) != 0
     || (v15 = *(_DWORD **)(v12 + 24)) != 0 && *v15 == 16
     || *(_DWORD *)(v11 + 28) != *(_DWORD *)(v12 + 28) - 1;
  *(_BYTE *)(v11 + 32) = v16;
  LOBYTE(v17) = TQuality;
  v26 = v10;
  v18 = -1;
  if ( TQuality != -1 )
    goto LABEL_16;
  v19 = *(_DWORD *)(v12 + 36);
  if ( v19 != -1 )
  {
    v17 = 1023 * v19 / 0x2710u;
LABEL_16:
    v28 = v17;
    goto LABEL_17;
  }
  v28 = -1;
LABEL_17:
  if ( SQuality == -1 )
  {
    v20 = *(_DWORD *)(v12 + 36);
    if ( v20 != -1 )
      v18 = 1023 * v20 / 0x2710u;
  }
  else
  {
    v18 = SQuality;
  }
  v21 = CVCompress(*(_DWORD *)(v12 + 8), v11 + 32, *(_DWORD *)(v12 + 32), v18, v28, v26, v27);
  v22 = v21;
  if ( v21 >= 0 )
  {
    *(_DWORD *)(v11 + 28) = *(_DWORD *)(v12 + 28);
    *(_DWORD *)(*(_DWORD *)(v12 + 4) + 20) = v21;
    v23 = *(_DWORD **)(v12 + 20);
    if ( v23 )
      *v23 = 25444;
    v24 = *(int **)(v12 + 24);
    if ( v24 )
    {
      v25 = 2;
      if ( *(_BYTE *)(v11 + 32) )
        v25 = 18;
      *v24 = v25;
    }
    return 0;
  }
  else
  {
    result = -100;
    *(_DWORD *)(v11 + 28) = -2;
    if ( v22 == -2 )
      return -10;
  }
  return result;
}

```

## disassembly

```asm
0x1000fc97  mov     edi, edi
0x1000fc99  push    ebp
0x1000fc9a  mov     ebp, esp
0x1000fc9c  push    ecx
0x1000fc9d  push    ecx
0x1000fc9e  push    esi
0x1000fc9f  push    edi
0x1000fca0  mov     edi, ecx
0x1000fca2  mov     esi, edx
0x1000fca4  cmp     byte ptr [edi+4], 0
0x1000fca8  jz      short loc_1000FCBD
0x1000fcaa  mov     ecx, [esi+0Ch]
0x1000fcad  mov     eax, [ecx+4]
0x1000fcb0  cmp     eax, [edi+10h]
0x1000fcb3  jnz     short loc_1000FCBD
0x1000fcb5  mov     eax, [ecx+8]
0x1000fcb8  cmp     eax, [edi+14h]
0x1000fcbb  jz      short loc_1000FCD2
0x1000fcbd  push    dword ptr [esi+4]
0x1000fcc0  mov     edx, [esi+0Ch]
0x1000fcc3  mov     ecx, edi
0x1000fcc5  call    _CompressBegin@12; CompressBegin(x,x,x)
0x1000fcca  test    eax, eax
0x1000fccc  jnz     loc_1000FDE7
0x1000fcd2  push    dword ptr [esi+4]
0x1000fcd5  mov     edx, [esi+0Ch]
0x1000fcd8  call    _CompressQuery@12; CompressQuery(x,x,x)
0x1000fcdd  test    eax, eax
0x1000fcdf  jnz     loc_1000FDE7
0x1000fce5  test    byte ptr [esi], 1
0x1000fce8  jnz     short loc_1000FD03
0x1000fcea  mov     eax, [esi+18h]
0x1000fced  test    eax, eax
0x1000fcef  jz      short loc_1000FCF6
0x1000fcf1  cmp     dword ptr [eax], 10h
0x1000fcf4  jz      short loc_1000FD03
0x1000fcf6  mov     eax, [esi+1Ch]
0x1000fcf9  dec     eax
0x1000fcfa  cmp     [edi+1Ch], eax
0x1000fcfd  jnz     short loc_1000FD03
0x1000fcff  xor     al, al
0x1000fd01  jmp     short loc_1000FD05
0x1000fd03  mov     al, 1
0x1000fd05  mov     ecx, [edi+14h]
0x1000fd08  mov     edx, 0FFFFh
0x1000fd0d  dec     ecx
0x1000fd0e  mov     [edi+20h], al
0x1000fd11  imul    ecx, [edi+18h]
0x1000fd15  mov     ax, _TQuality
0x1000fd1b  push    ebx
0x1000fd1c  mov     ebx, 3FFh
0x1000fd21  add     ecx, [esi+10h]
0x1000fd24  mov     [ebp+var_8], ecx
0x1000fd27  mov     ecx, 2710h
0x1000fd2c  cmp     ax, dx
0x1000fd2f  jnz     short loc_1000FD48
0x1000fd31  mov     eax, [esi+24h]
0x1000fd34  cmp     eax, 0FFFFFFFFh
0x1000fd37  jnz     short loc_1000FD3E
0x1000fd39  mov     [ebp+var_4], ebx
0x1000fd3c  jmp     short loc_1000FD4E
0x1000fd3e  imul    eax, 3FFh
0x1000fd44  xor     edx, edx
0x1000fd46  div     ecx
0x1000fd48  movzx   eax, ax
0x1000fd4b  mov     [ebp+var_4], eax
0x1000fd4e  mov     ecx, 0FFFFh
0x1000fd53  mov     eax, esi
0x1000fd55  push    24h ; '$'
0x1000fd57  pop     edx
0x1000fd58  cmp     _SQuality, cx
0x1000fd5f  jz      short loc_1000FD6A
0x1000fd61  movzx   ebx, _SQuality
0x1000fd68  jmp     short loc_1000FD84
0x1000fd6a  mov     eax, [eax+edx]
0x1000fd6d  cmp     eax, 0FFFFFFFFh
0x1000fd70  jz      short loc_1000FD84
0x1000fd72  imul    eax, 3FFh
0x1000fd78  xor     edx, edx
0x1000fd7a  mov     ecx, 2710h
0x1000fd7f  div     ecx
0x1000fd81  movzx   ebx, ax
0x1000fd84  push    [ebp+var_4]
0x1000fd87  mov     edx, [ebp+var_8]
0x1000fd8a  mov     ecx, [edi+8]
0x1000fd8d  push    ebx
0x1000fd8e  push    dword ptr [esi+20h]
0x1000fd91  lea     ebx, [edi+20h]
0x1000fd94  push    ebx
0x1000fd95  push    dword ptr [esi+8]
0x1000fd98  call    _CVCompress@28; CVCompress(x,x,x,x,x,x,x)
0x1000fd9d  mov     ecx, eax
0x1000fd9f  test    ecx, ecx
0x1000fda1  jns     short loc_1000FDB6
0x1000fda3  push    0FFFFFFFEh
0x1000fda5  pop     esi
0x1000fda6  push    0FFFFFF9Ch
0x1000fda8  pop     eax
0x1000fda9  push    0FFFFFFF6h
0x1000fdab  cmp     ecx, esi
0x1000fdad  mov     [edi+1Ch], esi
0x1000fdb0  pop     edx
0x1000fdb1  cmovz   eax, edx
0x1000fdb4  jmp     short loc_1000FDE6
0x1000fdb6  mov     eax, [esi+1Ch]
0x1000fdb9  mov     [edi+1Ch], eax
0x1000fdbc  mov     eax, [esi+4]
0x1000fdbf  mov     [eax+14h], ecx
0x1000fdc2  mov     eax, [esi+14h]
0x1000fdc5  test    eax, eax
0x1000fdc7  jz      short loc_1000FDCF
0x1000fdc9  mov     dword ptr [eax], 6364h
0x1000fdcf  mov     ecx, [esi+18h]
0x1000fdd2  test    ecx, ecx
0x1000fdd4  jz      short loc_1000FDE4
0x1000fdd6  cmp     byte ptr [ebx], 0
0x1000fdd9  push    2
0x1000fddb  pop     eax
0x1000fddc  push    12h
0x1000fdde  pop     edx
0x1000fddf  cmovnz  eax, edx
0x1000fde2  mov     [ecx], eax
0x1000fde4  xor     eax, eax
0x1000fde6  pop     ebx
0x1000fde7  pop     edi
0x1000fde8  pop     esi
0x1000fde9  leave
0x1000fdea  retn    4
```
