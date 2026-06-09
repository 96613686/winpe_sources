# CVCompressFramesInfo(x,x)

- ea: `0x10004fcb`
- end: `0x10005108`
- name: `_CVCompressFramesInfo@8`
- size: `317`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x10004695`
- `0x1000fb09`

## callees

- `0x10004fcb`

## import_xrefs

- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1000503f`
- `api-ms-win-core-largeinteger-l1-1-0!MulDiv` at `0x1000503f`

## pseudocode

```c
int __fastcall CVCompressFramesInfo(int a1, int a2)
{
  __int16 v4; // ax
  __int16 v5; // ax
  int v6; // eax
  int v7; // eax
  int v8; // edx
  int v9; // edi
  int v10; // ecx
  int v11; // esi
  int v12; // edi
  __int16 i; // dx
  __int16 v14; // ax
  __int16 v16; // [esp+8h] [ebp-Ch]
  int v17; // [esp+Ch] [ebp-8h]

  if ( !a2 || !*(_DWORD *)(a2 + 16) && !*(_DWORD *)(a2 + 20) )
  {
    v14 = 0;
LABEL_15:
    *(_WORD *)(a1 + 212) = v14;
    return *(__int16 *)(a1 + 212);
  }
  v4 = *(_WORD *)(a2 + 12);
  *(_WORD *)(a1 + 214) = v4;
  if ( v4 <= 100 )
  {
    if ( v4 )
    {
      v5 = 0;
    }
    else
    {
      *(_WORD *)(a1 + 214) = 15;
      v5 = -1;
    }
    *(_WORD *)(a1 + 1032) = v5;
    v16 = *(_WORD *)(a1 + 214);
    v6 = v16 * MulDiv(*(_DWORD *)(a2 + 20), *(_DWORD *)(a2 + 8), *(_DWORD *)(a2 + 16));
    *(_DWORD *)(a1 + 216) = v6;
    v17 = v6;
    if ( (*(_BYTE *)a2 & 1) != 0 )
      v7 = *(_DWORD *)(a2 + 24);
    else
      v7 = 0;
    *(_DWORD *)(a1 + 220) = v7;
    *(_DWORD *)(a1 + 224) = *(_DWORD *)(a2 + 28);
    v8 = *(unsigned __int16 *)(a2 + 32);
    *(_WORD *)(a1 + 228) = v8;
    v9 = *(unsigned __int16 *)(a2 + 34);
    *(_WORD *)(a1 + 230) = v9;
    v10 = 1;
    v11 = v9 * v17 / (v8 + v9 * (v16 - 1));
    v12 = v8 * v11 / v9;
    for ( i = v16; v10 < i; i = *(_WORD *)(a1 + 214) )
      *(_DWORD *)(a1 + 8 * v10++ + 232) = v11;
    *(_DWORD *)(a1 + 236) = v12;
    *(_WORD *)(a1 + 1034) = 0;
    *(_DWORD *)(a1 + 232) = v12;
    *(_DWORD *)(a1 + 1036) = v11 * (i - 1);
    v14 = 1;
    goto LABEL_15;
  }
  return *(__int16 *)(a1 + 212);
}

```

## disassembly

```asm
0x10004fcb  mov     edi, edi
0x10004fcd  push    ebp
0x10004fce  mov     ebp, esp
0x10004fd0  sub     esp, 0Ch
0x10004fd3  push    ebx
0x10004fd4  push    esi
0x10004fd5  mov     esi, edx
0x10004fd7  mov     ebx, ecx
0x10004fd9  test    esi, esi
0x10004fdb  jz      loc_100050F4
0x10004fe1  cmp     dword ptr [esi+10h], 0
0x10004fe5  jnz     short loc_10004FF1
0x10004fe7  cmp     dword ptr [esi+14h], 0
0x10004feb  jz      loc_100050F4
0x10004ff1  movzx   eax, word ptr [esi+0Ch]
0x10004ff5  mov     [ebx+0D6h], ax
0x10004ffc  cmp     ax, 64h ; 'd'
0x10005000  jg      loc_100050FD
0x10005006  test    ax, ax
0x10005009  jnz     short loc_1000501A
0x1000500b  push    0Fh
0x1000500d  pop     eax
0x1000500e  mov     [ebx+0D6h], ax
0x10005015  or      eax, 0FFFFFFFFh
0x10005018  jmp     short loc_1000501C
0x1000501a  xor     eax, eax
0x1000501c  push    edi
0x1000501d  mov     [ebx+408h], ax
0x10005024  push    dword ptr [esi+10h]; nDenominator
0x10005027  movzx   eax, word ptr [ebx+0D6h]
0x1000502e  push    dword ptr [esi+8]; nNumerator
0x10005031  mov     edx, eax
0x10005033  movsx   edi, ax
0x10005036  push    dword ptr [esi+14h]; nNumber
0x10005039  mov     [ebp+var_C], edx
0x1000503c  mov     [ebp+var_4], edi
0x1000503f  call    ds:__imp__MulDiv@12; MulDiv(x,x,x)
0x10005045  imul    eax, edi
0x10005048  mov     [ebx+0D8h], eax
0x1000504e  test    byte ptr [esi], 1
0x10005051  mov     [ebp+var_8], eax
0x10005054  jz      short loc_1000505B
0x10005056  mov     eax, [esi+18h]
0x10005059  jmp     short loc_1000505D
0x1000505b  xor     eax, eax
0x1000505d  mov     [ebx+0DCh], eax
0x10005063  mov     eax, [esi+1Ch]
0x10005066  mov     [ebx+0E0h], eax
0x1000506c  movzx   edx, word ptr [esi+20h]
0x10005070  mov     eax, [ebp+var_8]
0x10005073  mov     [ebx+0E4h], dx
0x1000507a  movzx   ecx, word ptr [esi+22h]
0x1000507e  mov     esi, edx
0x10005080  mov     edi, ecx
0x10005082  mov     [ebx+0E6h], cx
0x10005089  mov     ecx, [ebp+var_4]
0x1000508c  imul    eax, edi
0x1000508f  dec     ecx
0x10005090  imul    ecx, edi
0x10005093  cdq
0x10005094  add     ecx, esi
0x10005096  idiv    ecx
0x10005098  mov     [ebp+var_8], eax
0x1000509b  imul    eax, esi
0x1000509e  xor     esi, esi
0x100050a0  inc     esi
0x100050a1  mov     ecx, esi
0x100050a3  cdq
0x100050a4  idiv    edi
0x100050a6  cmp     [ebp+var_4], esi
0x100050a9  mov     esi, [ebp+var_8]
0x100050ac  mov     edi, eax
0x100050ae  mov     eax, [ebp+var_C]
0x100050b1  movzx   edx, ax
0x100050b4  jle     short loc_100050CC
0x100050b6  mov     [ebx+ecx*8+0E8h], esi
0x100050bd  inc     ecx
0x100050be  movzx   eax, word ptr [ebx+0D6h]
0x100050c5  mov     edx, eax
0x100050c7  cwde
0x100050c8  cmp     ecx, eax
0x100050ca  jl      short loc_100050B6
0x100050cc  xor     eax, eax
0x100050ce  mov     [ebx+0ECh], edi
0x100050d4  mov     [ebx+40Ah], ax
0x100050db  movsx   eax, dx
0x100050de  dec     eax
0x100050df  mov     [ebx+0E8h], edi
0x100050e5  imul    eax, esi
0x100050e8  pop     edi
0x100050e9  mov     [ebx+40Ch], eax
0x100050ef  xor     eax, eax
0x100050f1  inc     eax
0x100050f2  jmp     short loc_100050F6
0x100050f4  xor     eax, eax
0x100050f6  mov     [ebx+0D4h], ax
0x100050fd  movsx   eax, word ptr [ebx+0D4h]
0x10005104  pop     esi
0x10005105  pop     ebx
0x10005106  leave
0x10005107  retn
```
