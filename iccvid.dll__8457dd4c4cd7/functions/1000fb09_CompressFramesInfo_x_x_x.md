# CompressFramesInfo(x,x,x)

- ea: `0x1000fb09`
- end: `0x1000fbc6`
- name: `_CompressFramesInfo@12`
- size: `189`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x100093a0`

## callees

- `0x10004fcb`
- `0x1000fb09`

## pseudocode

```c
int __fastcall CompressFramesInfo(int a1, int *a2, int a3)
{
  bool v3; // zf
  int v4; // ebx
  int v5; // esi
  int v6; // edi
  int v7; // edx
  int v9; // eax
  _DWORD v10[8]; // [esp+Ch] [ebp-38h] BYREF
  __int16 v11; // [esp+2Ch] [ebp-18h]
  __int16 v12; // [esp+2Eh] [ebp-16h]
  int v13; // [esp+30h] [ebp-14h]
  int v14; // [esp+34h] [ebp-10h]
  int v15; // [esp+38h] [ebp-Ch]
  int v16; // [esp+3Ch] [ebp-8h]
  int v17; // [esp+40h] [ebp-4h]

  v3 = *(_BYTE *)(a1 + 4) == 0;
  v17 = a2[9];
  v10[3] = v17;
  v16 = a2[10];
  v10[4] = v16;
  v15 = a2[11];
  v10[5] = v15;
  v11 = KeyToInterRatioUpper;
  v4 = a2[8];
  v14 = (unsigned __int16)KeyToInterRatioUpper;
  v5 = *a2;
  v6 = a2[7];
  v7 = a2[12];
  v12 = KeyToInterRatioLower;
  v10[0] = v5;
  v10[1] = v6;
  v10[2] = v4;
  v10[6] = 2048;
  v10[7] = v7;
  v13 = (unsigned __int16)KeyToInterRatioLower;
  if ( !v3 )
    return CVCompressFramesInfo(*(_DWORD *)(a1 + 8), (int)v10) != 0 ? 0 : -100;
  v9 = v17;
  *(_DWORD *)(a1 + 44) = v5;
  *(_DWORD *)(a1 + 48) = v6;
  *(_DWORD *)(a1 + 52) = v4;
  *(_DWORD *)(a1 + 56) = v9;
  *(_DWORD *)(a1 + 60) = v16;
  *(_DWORD *)(a1 + 64) = v15;
  LOWORD(v9) = v14;
  *(_DWORD *)(a1 + 68) = 2048;
  *(_DWORD *)(a1 + 72) = v7;
  *(_WORD *)(a1 + 76) = v9;
  *(_WORD *)(a1 + 78) = v13;
  return 0;
}

```

## disassembly

```asm
0x1000fb09  mov     edi, edi
0x1000fb0b  push    ebp
0x1000fb0c  mov     ebp, esp
0x1000fb0e  sub     esp, 38h
0x1000fb11  cmp     byte ptr [ecx+4], 0
0x1000fb15  mov     eax, [edx+24h]
0x1000fb18  mov     [ebp+var_4], eax
0x1000fb1b  mov     [ebp+var_2C], eax
0x1000fb1e  mov     eax, [edx+28h]
0x1000fb21  mov     [ebp+var_8], eax
0x1000fb24  mov     [ebp+var_28], eax
0x1000fb27  mov     eax, [edx+2Ch]
0x1000fb2a  mov     [ebp+var_C], eax
0x1000fb2d  mov     [ebp+var_24], eax
0x1000fb30  mov     ax, _KeyToInterRatioUpper
0x1000fb36  mov     [ebp+var_18], ax
0x1000fb3a  movzx   eax, ax
0x1000fb3d  push    ebx
0x1000fb3e  mov     ebx, [edx+20h]
0x1000fb41  mov     [ebp+var_10], eax
0x1000fb44  mov     ax, _KeyToInterRatioLower
0x1000fb4a  push    esi
0x1000fb4b  mov     esi, [edx]
0x1000fb4d  push    edi
0x1000fb4e  mov     edi, [edx+1Ch]
0x1000fb51  mov     edx, [edx+30h]
0x1000fb54  mov     [ebp+var_16], ax
0x1000fb58  movzx   eax, ax
0x1000fb5b  mov     [ebp+var_38], esi
0x1000fb5e  mov     [ebp+var_34], edi
0x1000fb61  mov     [ebp+var_30], ebx
0x1000fb64  mov     [ebp+var_20], 800h
0x1000fb6b  mov     [ebp+var_1C], edx
0x1000fb6e  mov     [ebp+var_14], eax
0x1000fb71  jz      short loc_1000FB8A
0x1000fb73  mov     ecx, [ecx+8]
0x1000fb76  lea     edx, [ebp+var_38]
0x1000fb79  call    _CVCompressFramesInfo@8; CVCompressFramesInfo(x,x)
0x1000fb7e  neg     eax
0x1000fb80  sbb     eax, eax
0x1000fb82  and     eax, 64h
0x1000fb85  add     eax, 0FFFFFF9Ch
0x1000fb88  jmp     short loc_1000FBBF
0x1000fb8a  mov     eax, [ebp+var_4]
0x1000fb8d  mov     [ecx+2Ch], esi
0x1000fb90  mov     [ecx+30h], edi
0x1000fb93  mov     [ecx+34h], ebx
0x1000fb96  mov     [ecx+38h], eax
0x1000fb99  mov     eax, [ebp+var_8]
0x1000fb9c  mov     [ecx+3Ch], eax
0x1000fb9f  mov     eax, [ebp+var_C]
0x1000fba2  mov     [ecx+40h], eax
0x1000fba5  mov     eax, [ebp+var_10]
0x1000fba8  mov     dword ptr [ecx+44h], 800h
0x1000fbaf  mov     [ecx+48h], edx
0x1000fbb2  mov     [ecx+4Ch], ax
0x1000fbb6  mov     eax, [ebp+var_14]
0x1000fbb9  mov     [ecx+4Eh], ax
0x1000fbbd  xor     eax, eax
0x1000fbbf  pop     edi
0x1000fbc0  pop     esi
0x1000fbc1  pop     ebx
0x1000fbc2  leave
0x1000fbc3  retn    4
```
