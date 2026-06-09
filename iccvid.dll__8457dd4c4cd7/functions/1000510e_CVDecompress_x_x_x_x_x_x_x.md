# CVDecompress(x,x,x,x,x,x,x)

- ea: `0x1000510e`
- end: `0x100053ac`
- name: `_CVDecompress@28`
- size: `670`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1000510e`
- `0x10010520`

## callees

- `0x1000510e`
- `0x100130b0`
- `0x1001358d`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10005141`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x10005141`

## pseudocode

```c
int __fastcall CVDecompress(int a1, char *a2, unsigned int a3, int a4, int a5, int a6, int a7)
{
  void *v9; // ebx
  int v10; // ecx
  unsigned int v11; // ebx
  int v12; // ecx
  int v13; // edx
  _BYTE *v14; // esi
  unsigned int v15; // ebx
  int v16; // edx
  unsigned __int8 *v17; // ecx
  _BYTE *v18; // ebx
  unsigned int v19; // ecx
  unsigned int v20; // eax
  unsigned int v21; // eax
  unsigned int v22; // eax
  unsigned int v23; // eax
  unsigned int v24; // eax
  unsigned int v25; // eax
  unsigned int v26; // eax
  unsigned int v27; // eax
  unsigned int v28; // eax
  int v29; // eax
  int v31; // [esp+Ch] [ebp-2Ch]
  unsigned int v32; // [esp+10h] [ebp-28h]
  _BYTE *v33; // [esp+14h] [ebp-24h]
  _BYTE *v34; // [esp+18h] [ebp-20h]
  unsigned int v35; // [esp+1Ch] [ebp-1Ch]
  int v36; // [esp+20h] [ebp-18h]
  int v37; // [esp+24h] [ebp-14h]
  unsigned __int8 *v38; // [esp+28h] [ebp-10h]
  unsigned int v39; // [esp+2Ch] [ebp-Ch]
  unsigned int v40; // [esp+30h] [ebp-8h]
  char v41; // [esp+37h] [ebp-1h]

  v9 = *(void **)(a1 + 36);
  if ( v9 )
  {
    *(_DWORD *)(a1 + 36) = 0;
    CVDecompress(9286, 0, 0, 0, a7);
    LocalFree(v9);
  }
  if ( a3 < 0x20 )
    return 0;
  v10 = (unsigned __int8)a2[3] | (((unsigned __int8)a2[2] | ((unsigned __int8)a2[1] << 8)) << 8);
  if ( (int)a3 < v10 )
    return 0;
  v41 = *a2;
  if ( (unsigned int)v10 < 0xA )
    return 0;
  v11 = v10 - 10;
  v12 = (unsigned __int8)a2[9] | ((unsigned __int8)a2[8] << 8);
  v35 = v11;
  v31 = v12;
  if ( !v12 || (unsigned int)v12 > 3 )
    return 0;
  v13 = 0;
  v14 = a2 + 10;
  v36 = 0;
  v33 = v14;
  v34 = v14;
  do
  {
    if ( v11 < 0x16 )
      break;
    v15 = (unsigned __int8)v14[3] | (((unsigned __int8)v14[2] | ((unsigned __int8)v14[1] << 8)) << 8);
    v32 = v15;
    if ( v35 < v15 )
      break;
    if ( *v14 == 16 || *v14 == 17 )
    {
      if ( v15 < 0xC )
        return 0;
      v39 = v15 - 12;
      v16 = v36;
      v37 = (unsigned __int16)(*(_WORD *)(a1 + 46)
                             * (_byteswap_ushort(*((_WORD *)v14 + 4)) - _byteswap_ushort(*((_WORD *)v14 + 2))));
      if ( v36 && !v41 && *v14 == 17 )
      {
        memcpy(
          (void *)(*(_DWORD *)(a1 + 28) + (v36 << 13)),
          (const void *)(*(_DWORD *)(a1 + 28) + (v36 << 13) - 0x2000),
          0x2000u);
        v16 = v36;
      }
      v17 = v14 + 12;
      v38 = v14 + 12;
      *(_DWORD *)(a1 + 56) = *(_DWORD *)(a1 + 32) + (v16 << 13);
      *(_DWORD *)(a1 + 60) = a7;
      if ( v39 >= 4 )
      {
        v18 = v34 + 12;
        while ( 1 )
        {
          v19 = v38[3] | ((v38[2] | (v17[1] << 8)) << 8);
          v40 = v19;
          if ( v39 < v19 )
          {
LABEL_43:
            v15 = v32;
            v14 = v33;
            v16 = v36;
            break;
          }
          v20 = *v38;
          if ( v20 > 0x25 )
          {
            v25 = v20 - 38;
            if ( !v25 || (v26 = v25 - 1) == 0 )
            {
LABEL_38:
              (*(void (__thiscall **)(_DWORD, _BYTE *, int, _DWORD, _DWORD))(a1 + 4))(
                *(_DWORD *)(a1 + 4),
                v18,
                *(_DWORD *)(a1 + 56) + 4096,
                *(_DWORD *)(a1 + 52),
                *(_DWORD *)(a1 + 48));
              goto LABEL_39;
            }
            v27 = v26 - 9;
            if ( !v27 )
            {
              (*(void (__thiscall **)(_DWORD, int, _BYTE *, unsigned int, int, int, int, int))(a1 + 8))(
                *(_DWORD *)(a1 + 8),
                a1,
                v18 + 4,
                v19 - 4,
                a4,
                a5,
                a6,
                v37);
              goto LABEL_39;
            }
            v28 = v27 - 1;
            if ( !v28 )
            {
              (*(void (__thiscall **)(_DWORD, int, _BYTE *, unsigned int, int, int, int, int))(a1 + 16))(
                *(_DWORD *)(a1 + 16),
                a1,
                v18 + 4,
                v19 - 4,
                a4,
                a5,
                a6,
                v37);
              goto LABEL_39;
            }
            if ( v28 == 1 )
            {
              (*(void (__thiscall **)(_DWORD, int, _BYTE *, unsigned int, int, int, int, int))(a1 + 12))(
                *(_DWORD *)(a1 + 12),
                a1,
                v18 + 4,
                v19 - 4,
                a4,
                a5,
                a6,
                v37);
              goto LABEL_39;
            }
          }
          else
          {
            if ( v20 == 37 || (v21 = v20 - 32) == 0 || (v22 = v21 - 1) == 0 )
            {
LABEL_28:
              (*(void (__thiscall **)(_DWORD, _BYTE *, _DWORD, _DWORD, _DWORD))a1)(
                *(_DWORD *)a1,
                v18,
                *(_DWORD *)(a1 + 56),
                *(_DWORD *)(a1 + 52),
                *(_DWORD *)(a1 + 48));
LABEL_39:
              v19 = v40;
              goto LABEL_40;
            }
            v23 = v22 - 1;
            if ( !v23 )
              goto LABEL_38;
            v24 = v23 - 1;
            if ( !v24 )
              goto LABEL_38;
            if ( v24 == 1 )
              goto LABEL_28;
          }
LABEL_40:
          v38 += v19;
          v18 += v19;
          v29 = 1;
          if ( v19 > 1 )
            v29 = v19;
          v39 -= v29;
          v17 = v38;
          if ( v39 < 4 )
            goto LABEL_43;
        }
      }
      v12 = v31;
      a6 += a7 * (__int16)v37;
      v13 = v16 + 1;
      v36 = v13;
    }
    v34 += v15;
    v14 += v15;
    v35 -= v15;
    v11 = v35;
    v33 = v14;
  }
  while ( v13 < v12 );
  return 1;
}

```

## disassembly

```asm
0x1000510e  mov     edi, edi
0x10005110  push    ebp
0x10005111  mov     ebp, esp
0x10005113  sub     esp, 2Ch
0x10005116  push    ebx
0x10005117  push    esi
0x10005118  push    edi
0x10005119  mov     edi, ecx
0x1000511b  mov     esi, edx
0x1000511d  mov     ebx, [edi+24h]
0x10005120  test    ebx, ebx
0x10005122  jz      short loc_10005147
0x10005124  push    [ebp+arg_10]
0x10005127  mov     edx, ebx
0x10005129  mov     dword ptr [edi+24h], 0
0x10005130  push    0
0x10005132  push    0
0x10005134  push    0
0x10005136  push    2446h
0x1000513b  call    _CVDecompress@28; CVDecompress(x,x,x,x,x,x,x)
0x10005140  push    ebx; hMem
0x10005141  call    ds:__imp__LocalFree@4; LocalFree(x)
0x10005147  cmp     [ebp+arg_0], 20h ; ' '
0x1000514b  jb      loc_100053A3
0x10005151  movzx   ecx, byte ptr [esi+1]
0x10005155  movzx   eax, byte ptr [esi+2]
0x10005159  shl     ecx, 8
0x1000515c  or      ecx, eax
0x1000515e  movzx   eax, byte ptr [esi+3]
0x10005162  shl     ecx, 8
0x10005165  or      ecx, eax
0x10005167  cmp     [ebp+arg_0], ecx
0x1000516a  jl      loc_100053A3
0x10005170  mov     al, [esi]
0x10005172  mov     [ebp+var_1], al
0x10005175  cmp     ecx, 0Ah
0x10005178  jb      loc_100053A3
0x1000517e  movzx   eax, byte ptr [esi+9]
0x10005182  lea     ebx, [ecx-0Ah]
0x10005185  movzx   ecx, byte ptr [esi+8]
0x10005189  shl     ecx, 8
0x1000518c  or      ecx, eax
0x1000518e  mov     [ebp+var_1C], ebx
0x10005191  mov     [ebp+var_2C], ecx
0x10005194  cmp     ecx, 1
0x10005197  jb      loc_100053A3
0x1000519d  cmp     ecx, 3
0x100051a0  ja      loc_100053A3
0x100051a6  xor     edx, edx
0x100051a8  add     esi, 0Ah
0x100051ab  mov     [ebp+var_18], edx
0x100051ae  mov     [ebp+var_24], esi
0x100051b1  mov     [ebp+var_20], esi
0x100051b4  cmp     ebx, 16h
0x100051b7  jb      loc_1000539E
0x100051bd  movzx   ebx, byte ptr [esi+1]
0x100051c1  movzx   eax, byte ptr [esi+2]
0x100051c5  shl     ebx, 8
0x100051c8  or      ebx, eax
0x100051ca  movzx   eax, byte ptr [esi+3]
0x100051ce  shl     ebx, 8
0x100051d1  or      ebx, eax
0x100051d3  mov     [ebp+var_28], ebx
0x100051d6  cmp     [ebp+var_1C], ebx
0x100051d9  jb      loc_1000539E
0x100051df  mov     al, [esi]
0x100051e1  mov     [ebp+var_2], al
0x100051e4  cmp     al, 10h
0x100051e6  jz      short loc_100051F0
0x100051e8  cmp     al, 11h
0x100051ea  jnz     loc_10005388
0x100051f0  cmp     ebx, 0Ch
0x100051f3  jb      loc_100053A3
0x100051f9  movzx   edx, byte ptr [esi+8]
0x100051fd  lea     eax, [ebx-0Ch]
0x10005200  movzx   ecx, byte ptr [esi+4]
0x10005204  mov     [ebp+var_C], eax
0x10005207  movzx   eax, byte ptr [esi+9]
0x1000520b  shl     dx, 8
0x1000520f  or      dx, ax
0x10005212  shl     cx, 8
0x10005216  movzx   eax, byte ptr [esi+5]
0x1000521a  or      cx, ax
0x1000521d  movsx   eax, word ptr [edi+2Eh]
0x10005221  sub     dx, cx
0x10005224  movsx   ecx, dx
0x10005227  mov     edx, [ebp+var_18]
0x1000522a  imul    ecx, eax
0x1000522d  movzx   eax, cx
0x10005230  mov     [ebp+var_14], eax
0x10005233  test    edx, edx
0x10005235  jz      short loc_10005263
0x10005237  cmp     [ebp+var_1], 0
0x1000523b  jnz     short loc_10005263
0x1000523d  cmp     [ebp+var_2], 11h
0x10005241  jnz     short loc_10005263
0x10005243  mov     ecx, edx
0x10005245  shl     ecx, 0Dh
0x10005248  add     ecx, [edi+1Ch]
0x1000524b  push    2000h; Size
0x10005250  lea     eax, [ecx-2000h]
0x10005256  push    eax; Src
0x10005257  push    ecx; void *
0x10005258  call    _memcpy
0x1000525d  mov     edx, [ebp+var_18]
0x10005260  add     esp, 0Ch
0x10005263  mov     eax, [ebp+var_20]
0x10005266  lea     ecx, [esi+0Ch]
0x10005269  add     eax, 0Ch
0x1000526c  mov     [ebp+var_10], ecx
0x1000526f  mov     [ebp+var_8], eax
0x10005272  mov     eax, edx
0x10005274  shl     eax, 0Dh
0x10005277  add     eax, [edi+20h]
0x1000527a  cmp     [ebp+var_C], 4
0x1000527e  mov     [edi+38h], eax
0x10005281  mov     eax, [ebp+arg_10]
0x10005284  mov     [edi+3Ch], eax
0x10005287  jb      loc_10005376
0x1000528d  mov     ebx, [ebp+var_8]
0x10005290  mov     edx, [ebp+var_10]
0x10005293  movzx   ecx, byte ptr [ecx+1]
0x10005297  shl     ecx, 8
0x1000529a  movzx   eax, byte ptr [edx+2]
0x1000529e  or      ecx, eax
0x100052a0  movzx   eax, byte ptr [edx+3]
0x100052a4  shl     ecx, 8
0x100052a7  or      ecx, eax
0x100052a9  mov     [ebp+var_8], ecx
0x100052ac  cmp     [ebp+var_C], ecx
0x100052af  jb      loc_1000536D
0x100052b5  movzx   eax, byte ptr [edx]
0x100052b8  cmp     eax, 25h ; '%'
0x100052bb  ja      short loc_100052E5
0x100052bd  jz      short loc_100052D8
0x100052bf  sub     eax, 20h ; ' '
0x100052c2  jz      short loc_100052D8
0x100052c4  sub     eax, 1
0x100052c7  jz      short loc_100052D8
0x100052c9  sub     eax, 1
0x100052cc  jz      short loc_1000532C
0x100052ce  sub     eax, 1
0x100052d1  jz      short loc_1000532C
0x100052d3  sub     eax, 1
0x100052d6  jnz     short loc_1000534C
0x100052d8  push    dword ptr [edi+30h]
0x100052db  mov     esi, [edi]
0x100052dd  push    dword ptr [edi+34h]
0x100052e0  push    dword ptr [edi+38h]
0x100052e3  jmp     short loc_1000533E
0x100052e5  sub     eax, 26h ; '&'
0x100052e8  jz      short loc_1000532C
0x100052ea  sub     eax, 1
0x100052ed  jz      short loc_1000532C
0x100052ef  sub     eax, 9
0x100052f2  jz      short loc_10005327
0x100052f4  sub     eax, 1
0x100052f7  jz      short loc_10005322
0x100052f9  sub     eax, 1
0x100052fc  jnz     short loc_1000534C
0x100052fe  mov     esi, [edi+0Ch]
0x10005301  push    [ebp+var_14]
0x10005304  lea     eax, [ecx-4]
0x10005307  mov     ecx, esi
0x10005309  push    [ebp+arg_C]
0x1000530c  push    [ebp+arg_8]
0x1000530f  push    [ebp+arg_4]
0x10005312  push    eax
0x10005313  lea     eax, [ebx+4]
0x10005316  push    eax
0x10005317  push    edi
0x10005318  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x1000531e  call    esi
0x10005320  jmp     short loc_10005349
0x10005322  mov     esi, [edi+10h]
0x10005325  jmp     short loc_10005301
0x10005327  mov     esi, [edi+8]
0x1000532a  jmp     short loc_10005301
0x1000532c  push    dword ptr [edi+30h]
0x1000532f  mov     eax, [edi+38h]
0x10005332  push    dword ptr [edi+34h]
0x10005335  mov     esi, [edi+4]
0x10005338  add     eax, 1000h
0x1000533d  push    eax
0x1000533e  push    ebx
0x1000533f  mov     ecx, esi
0x10005341  call    ds:___guard_check_icall_fptr; _guard_check_icall_nop(x) ...
0x10005347  call    esi
0x10005349  mov     ecx, [ebp+var_8]
0x1000534c  add     [ebp+var_10], ecx
0x1000534f  xor     eax, eax
0x10005351  add     ebx, ecx
0x10005353  inc     eax
0x10005354  cmp     ecx, eax
0x10005356  cmova   eax, ecx
0x10005359  mov     ecx, [ebp+var_C]
0x1000535c  sub     ecx, eax
0x1000535e  mov     [ebp+var_C], ecx
0x10005361  cmp     ecx, 4
0x10005364  mov     ecx, [ebp+var_10]
0x10005367  jnb     loc_10005290
0x1000536d  mov     ebx, [ebp+var_28]
0x10005370  mov     esi, [ebp+var_24]
0x10005373  mov     edx, [ebp+var_18]
0x10005376  mov     eax, [ebp+var_14]
0x10005379  mov     ecx, [ebp+var_2C]
0x1000537c  cwde
0x1000537d  imul    eax, [ebp+arg_10]
0x10005381  add     [ebp+arg_C], eax
0x10005384  inc     edx
0x10005385  mov     [ebp+var_18], edx
0x10005388  add     [ebp+var_20], ebx
0x1000538b  add     esi, ebx
0x1000538d  sub     [ebp+var_1C], ebx
0x10005390  mov     ebx, [ebp+var_1C]
0x10005393  mov     [ebp+var_24], esi
0x10005396  cmp     edx, ecx
0x10005398  jl      loc_100051B4
0x1000539e  xor     eax, eax
0x100053a0  inc     eax
0x100053a1  jmp     short loc_100053A5
0x100053a3  xor     eax, eax
0x100053a5  pop     edi
0x100053a6  pop     esi
0x100053a7  pop     ebx
0x100053a8  leave
0x100053a9  retn    14h
```
