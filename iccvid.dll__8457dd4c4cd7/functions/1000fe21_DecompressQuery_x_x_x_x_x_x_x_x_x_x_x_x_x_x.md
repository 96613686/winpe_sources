# DecompressQuery(x,x,x,x,x,x,x,x,x,x,x,x,x,x)

- ea: `0x1000fe21`
- end: `0x1000ff08`
- name: `_DecompressQuery@56`
- size: `231`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x1000f82f`
- `0x1000fe21`

## pseudocode

```c
int __stdcall DecompressQuery(
        int a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9,
        int a10,
        int a11,
        unsigned int a12)
{
  int v12; // ecx
  int v13; // edi
  int v14; // eax
  int v15; // ebx
  unsigned int v16; // esi
  int v17; // eax

  if ( !a1 )
    return -2;
  v12 = ((*(_BYTE *)(a1 + 14) & 0x1F) == 8) + 1;
  if ( *(_DWORD *)(a1 + 16) != 1684633187 )
    v12 = 0;
  if ( !v12 )
    return -2;
  v13 = a5;
  if ( a5 == -1 )
    v13 = *(_DWORD *)(a1 + 4);
  v14 = a6;
  if ( a6 == -1 )
  {
    v14 = *(_DWORD *)(a1 + 8);
    a6 = v14;
  }
  if ( !a3 && !a4 && v13 == *(_DWORD *)(a1 + 4) && v14 == *(_DWORD *)(a1 + 8) )
  {
    if ( !a7 )
      return 0;
    v15 = a11;
    if ( a11 == -1 )
      v15 = *(_DWORD *)(a7 + 4);
    v16 = a12;
    if ( a12 == -1 )
      v16 = abs32(*(_DWORD *)(a7 + 8));
    v17 = DecompressedDibType(a7);
    if ( v17 != -1
      && (v15 == v13 && v16 == a6 || !v17 && v15 == 2 * v13 && v16 == 2 * a6)
      && (v17 != 5 && v17 != 8 || (((unsigned __int8)v16 | (unsigned __int8)v15) & 3) == 0)
      && (v17 != 6 && v17 != 7 || (v15 & 1) == 0) )
    {
      return 0;
    }
    return -2;
  }
  return -6;
}

```

## disassembly

```asm
0x1000fe21  mov     edi, edi
0x1000fe23  push    ebp
0x1000fe24  mov     ebp, esp
0x1000fe26  mov     edx, [ebp+arg_0]
0x1000fe29  push    ebx
0x1000fe2a  push    esi
0x1000fe2b  push    edi
0x1000fe2c  test    edx, edx
0x1000fe2e  jz      loc_1000FEFE
0x1000fe34  mov     al, [edx+0Eh]
0x1000fe37  xor     ecx, ecx
0x1000fe39  and     al, 1Fh
0x1000fe3b  cmp     al, 8
0x1000fe3d  setz    cl
0x1000fe40  xor     eax, eax
0x1000fe42  inc     ecx
0x1000fe43  cmp     dword ptr [edx+10h], 64697663h
0x1000fe4a  cmovnz  ecx, eax
0x1000fe4d  test    ecx, ecx
0x1000fe4f  jz      loc_1000FEFE
0x1000fe55  mov     edi, [ebp+arg_10]
0x1000fe58  cmp     edi, 0FFFFFFFFh
0x1000fe5b  jnz     short loc_1000FE60
0x1000fe5d  mov     edi, [edx+4]
0x1000fe60  mov     eax, [ebp+arg_14]
0x1000fe63  cmp     eax, 0FFFFFFFFh
0x1000fe66  jnz     short loc_1000FE6E
0x1000fe68  mov     eax, [edx+8]
0x1000fe6b  mov     [ebp+arg_14], eax
0x1000fe6e  cmp     [ebp+arg_8], 0
0x1000fe72  jnz     loc_1000FEFA
0x1000fe78  cmp     [ebp+arg_C], 0
0x1000fe7c  jnz     short loc_1000FEFA
0x1000fe7e  cmp     edi, [edx+4]
0x1000fe81  jnz     short loc_1000FEFA
0x1000fe83  cmp     eax, [edx+8]
0x1000fe86  jnz     short loc_1000FEFA
0x1000fe88  mov     ecx, [ebp+arg_18]
0x1000fe8b  test    ecx, ecx
0x1000fe8d  jz      short loc_1000FEF6
0x1000fe8f  mov     ebx, [ebp+arg_28]
0x1000fe92  cmp     ebx, 0FFFFFFFFh
0x1000fe95  jnz     short loc_1000FE9A
0x1000fe97  mov     ebx, [ecx+4]
0x1000fe9a  mov     esi, [ebp+arg_2C]
0x1000fe9d  cmp     esi, 0FFFFFFFFh
0x1000fea0  jnz     short loc_1000FEAC
0x1000fea2  mov     eax, [ecx+8]
0x1000fea5  cdq
0x1000fea6  mov     esi, eax
0x1000fea8  xor     esi, edx
0x1000feaa  sub     esi, edx
0x1000feac  call    _DecompressedDibType@4; DecompressedDibType(x)
0x1000feb1  mov     ecx, eax
0x1000feb3  cmp     ecx, 0FFFFFFFFh
0x1000feb6  jz      short loc_1000FEFE
0x1000feb8  mov     edx, [ebp+arg_14]
0x1000febb  cmp     ebx, edi
0x1000febd  jnz     short loc_1000FEC3
0x1000febf  cmp     esi, edx
0x1000fec1  jz      short loc_1000FED5
0x1000fec3  test    ecx, ecx
0x1000fec5  jnz     short loc_1000FEFE
0x1000fec7  lea     eax, [edi+edi]
0x1000feca  cmp     ebx, eax
0x1000fecc  jnz     short loc_1000FEFE
0x1000fece  lea     eax, [edx+edx]
0x1000fed1  cmp     esi, eax
0x1000fed3  jnz     short loc_1000FEFE
0x1000fed5  cmp     ecx, 5
0x1000fed8  jz      short loc_1000FEDF
0x1000feda  cmp     ecx, 8
0x1000fedd  jnz     short loc_1000FEE7
0x1000fedf  mov     eax, ebx
0x1000fee1  or      eax, esi
0x1000fee3  test    al, 3
0x1000fee5  jnz     short loc_1000FEFE
0x1000fee7  cmp     ecx, 6
0x1000feea  jz      short loc_1000FEF1
0x1000feec  cmp     ecx, 7
0x1000feef  jnz     short loc_1000FEF6
0x1000fef1  test    bl, 1
0x1000fef4  jnz     short loc_1000FEFE
0x1000fef6  xor     eax, eax
0x1000fef8  jmp     short loc_1000FF01
0x1000fefa  push    0FFFFFFFAh
0x1000fefc  jmp     short loc_1000FF00
0x1000fefe  push    0FFFFFFFEh
0x1000ff00  pop     eax
0x1000ff01  pop     edi
0x1000ff02  pop     esi
0x1000ff03  pop     ebx
0x1000ff04  pop     ebp
0x1000ff05  retn    30h ; '0'
```
