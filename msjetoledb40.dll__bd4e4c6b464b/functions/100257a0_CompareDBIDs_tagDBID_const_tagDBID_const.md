# CompareDBIDs(tagDBID const *,tagDBID const *)

- ea: `0x100257a0`
- end: `0x1002589e`
- name: `?CompareDBIDs@@YGJPBUtagDBID@@0@Z`
- size: `254`
- prototype: `int __cdecl(const struct tagDBID *, const struct tagDBID *)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10013890`
- `0x1001f130`
- `0x1002e3e0`
- `0x10044130`

## callees

- `0x100257a0`

## pseudocode

```c
BOOL __fastcall CompareDBIDs(int a1, int a2)
{
  int v4; // ecx
  int v5; // edx
  int v6; // eax
  int v7; // ecx
  _DWORD *v8; // edx
  _DWORD *v9; // ecx
  unsigned int v10; // esi
  bool v11; // cf
  const unsigned __int16 *v12; // ecx
  const unsigned __int16 *v13; // eax
  int v15; // [esp+Ch] [ebp-8h]
  char v16; // [esp+10h] [ebp-4h]

  if ( !a1 )
    return 1;
  if ( !a2 )
    return 1;
  v4 = *(_DWORD *)(a1 + 16);
  v5 = *(_DWORD *)(a2 + 16);
  if ( v4 != v5 && v4 != (unsigned __int8)byte_100058C8[v5] )
    return 1;
  v6 = 1 << v5;
  v7 = 1 << v4;
  v16 = v7;
  v15 = 1 << v5;
  if ( (v7 & 0x5B) != 0 )
  {
    if ( (v6 & 0x5B) != 0 )
    {
      if ( (v6 & 0x18) != 0 )
        v8 = *(_DWORD **)a2;
      else
        v8 = (_DWORD *)a2;
      if ( (v7 & 0x18) != 0 )
        v9 = *(_DWORD **)a1;
      else
        v9 = (_DWORD *)a1;
      v10 = 12;
      while ( *v9 == *v8 )
      {
        ++v9;
        ++v8;
        v11 = v10 < 4;
        v10 -= 4;
        if ( v11 )
        {
          LOBYTE(v6) = v15;
          LOBYTE(v7) = v16;
          goto LABEL_17;
        }
      }
    }
    return 1;
  }
LABEL_17:
  if ( (v7 & 0xD) != 0 )
  {
    if ( (v6 & 0xD) == 0 )
      return 1;
    v12 = *(const unsigned __int16 **)(a1 + 20);
    v13 = *(const unsigned __int16 **)(a2 + 20);
    if ( v12 )
    {
      if ( !v13 )
        return 1;
      v13 = (const unsigned __int16 *)wcscmp(v12, v13);
      if ( v13 )
        v13 = (const unsigned __int16 *)((int)v13 < 0 ? -1 : 1);
    }
    if ( v13 )
      return 1;
  }
  return (v16 & 0x32) != 0 && ((v15 & 0x32) == 0 || *(_DWORD *)(a1 + 20) != *(_DWORD *)(a2 + 20));
}

```

## disassembly

```asm
0x100257a0  mov     edi, edi
0x100257a2  push    ebp
0x100257a3  mov     ebp, esp
0x100257a5  sub     esp, 8
0x100257a8  push    ebx
0x100257a9  push    esi
0x100257aa  mov     ebx, ecx
0x100257ac  push    edi
0x100257ad  mov     edi, edx
0x100257af  test    ebx, ebx
0x100257b1  jz      loc_10025892
0x100257b7  test    edi, edi
0x100257b9  jz      loc_10025892
0x100257bf  mov     ecx, [ebx+10h]
0x100257c2  mov     edx, [edi+10h]
0x100257c5  cmp     ecx, edx
0x100257c7  jz      short loc_100257D8
0x100257c9  movzx   eax, ds:byte_100058C8[edx]
0x100257d0  cmp     ecx, eax
0x100257d2  jnz     loc_10025892
0x100257d8  mov     eax, 1
0x100257dd  shl     eax, cl
0x100257df  mov     ecx, edx
0x100257e1  mov     [ebp+var_4], eax
0x100257e4  mov     eax, 1
0x100257e9  shl     eax, cl
0x100257eb  mov     ecx, [ebp+var_4]
0x100257ee  mov     [ebp+var_8], eax
0x100257f1  test    cl, 5Bh
0x100257f4  jz      short loc_1002582F
0x100257f6  test    al, 5Bh
0x100257f8  jz      loc_10025892
0x100257fe  test    al, 18h
0x10025800  jz      short loc_10025806
0x10025802  mov     edx, [edi]
0x10025804  jmp     short loc_10025808
0x10025806  mov     edx, edi
0x10025808  test    cl, 18h
0x1002580b  jz      short loc_10025811
0x1002580d  mov     ecx, [ebx]
0x1002580f  jmp     short loc_10025813
0x10025811  mov     ecx, ebx
0x10025813  mov     esi, 0Ch
0x10025818  mov     eax, [ecx]
0x1002581a  cmp     eax, [edx]
0x1002581c  jnz     short loc_10025892
0x1002581e  add     ecx, 4
0x10025821  add     edx, 4
0x10025824  sub     esi, 4
0x10025827  jnb     short loc_10025818
0x10025829  mov     eax, [ebp+var_8]
0x1002582c  mov     ecx, [ebp+var_4]
0x1002582f  test    cl, 0Dh
0x10025832  jz      short loc_10025875
0x10025834  test    al, 0Dh
0x10025836  jz      short loc_10025892
0x10025838  mov     ecx, [ebx+14h]
0x1002583b  mov     eax, [edi+14h]
0x1002583e  test    ecx, ecx
0x10025840  jz      short loc_10025871
0x10025842  test    eax, eax
0x10025844  jz      short loc_10025892
0x10025846  mov     dx, [ecx]
0x10025849  cmp     dx, [eax]
0x1002584c  jnz     short loc_1002586C
0x1002584e  test    dx, dx
0x10025851  jz      short loc_10025868
0x10025853  mov     dx, [ecx+2]
0x10025857  cmp     dx, [eax+2]
0x1002585b  jnz     short loc_1002586C
0x1002585d  add     ecx, 4
0x10025860  add     eax, 4
0x10025863  test    dx, dx
0x10025866  jnz     short loc_10025846
0x10025868  xor     eax, eax
0x1002586a  jmp     short loc_10025871
0x1002586c  sbb     eax, eax
0x1002586e  or      eax, 1
0x10025871  test    eax, eax
0x10025873  jnz     short loc_10025892
0x10025875  test    byte ptr [ebp+var_4], 32h
0x10025879  jz      short loc_10025889
0x1002587b  test    byte ptr [ebp+var_8], 32h
0x1002587f  jz      short loc_10025892
0x10025881  mov     eax, [ebx+14h]
0x10025884  cmp     eax, [edi+14h]
0x10025887  jnz     short loc_10025892
0x10025889  pop     edi
0x1002588a  pop     esi
0x1002588b  xor     eax, eax
0x1002588d  pop     ebx
0x1002588e  mov     esp, ebp
0x10025890  pop     ebp
0x10025891  retn
0x10025892  pop     edi
0x10025893  pop     esi
0x10025894  mov     eax, 1
0x10025899  pop     ebx
0x1002589a  mov     esp, ebp
0x1002589c  pop     ebp
0x1002589d  retn
```
